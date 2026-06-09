# Windows::FileSystem::ReFs::VolumePath::EnsureSVI(void)

- ea: `0x14004ed00`
- end: `0x14004edb8`
- name: `?EnsureSVI@VolumePath@ReFs@FileSystem@Windows@@QEBAXXZ`
- size: `184`
- prototype: `void __fastcall(Windows::FileSystem::ReFs::VolumePath *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callers

- `0x1400299a8`
- `0x140029a38`
- `0x140029ae0`
- `0x14003d700`

## callees

- `0x140019600`
- `0x140019970`
- `0x14002c5b0`
- `0x14004ed00`
- `0x14004f0a0`
- `0x14005088c`

## import_xrefs

- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x14004ed4c`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x14004ed4c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14004ed32`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14004ed32`

## string_xrefs

- `0x14004ed85`: `Failed to create 'System Volume Information' for volume %ws`

## pseudocode

```c
void __fastcall Windows::FileSystem::ReFs::VolumePath::EnsureSVI(Windows::FileSystem::ReFs::VolumePath *this)
{
  char *v1; // rbx
  __int64 v2; // rax
  int v3; // eax
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  const char *v7; // rax
  const char *v8; // r9
  int v9; // [rsp+20h] [rbp-28h]
  UNICODE_STRING VolumeRootPath; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  VolumeRootPath = 0;
  v1 = (char *)this + 32;
  RefsDedup::ustring::FreeString((RefsDedup::ustring *)&VolumeRootPath);
  v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v1);
  v3 = RtlDosPathNameToNtPathName_U_WithStatus(v2, &VolumeRootPath, 0, 0);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x145,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\svclib\\lib\\volumehelpers.cpp",
      (const char *)(unsigned int)v3,
      v9);
  v4 = RtlCreateSystemVolumeInformationFolder(&VolumeRootPath);
  if ( (v4 & 0xBFFFFFFF) != 0 )
  {
    v7 = (const char *)std::wstring::c_str(v1, v5, v6, v4);
    wil::details::in1diag3::Throw_NtStatusMsg(
      retaddr,
      (void *)0x14A,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\svclib\\lib\\volumehelpers.cpp",
      v8,
      (int)"Failed to create 'System Volume Information' for volume %ws",
      v7);
  }
  RefsDedup::ustring::FreeString((RefsDedup::ustring *)&VolumeRootPath);
}

```

## disassembly

```asm
0x14004ed00  push    rbx
0x14004ed02  sub     rsp, 40h
0x14004ed06  xorps   xmm0, xmm0
0x14004ed09  movups  xmmword ptr [rsp+48h+VolumeRootPath.Length], xmm0
0x14004ed0e  lea     rbx, [rcx+20h]
0x14004ed12  lea     rcx, [rsp+48h+VolumeRootPath]; this
0x14004ed17  call    ?FreeString@ustring@RefsDedup@@AEAAXXZ; RefsDedup::ustring::FreeString(void)
0x14004ed1c  mov     rcx, rbx
0x14004ed1f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14004ed24  xor     r9d, r9d
0x14004ed27  xor     r8d, r8d
0x14004ed2a  lea     rdx, [rsp+48h+VolumeRootPath]
0x14004ed2f  mov     rcx, rax
0x14004ed32  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x14004ed39  nop     dword ptr [rax+rax+00h]
0x14004ed3e  mov     rcx, [rsp+48h]; this
0x14004ed43  test    eax, eax
0x14004ed45  js      short loc_14004EDA3
0x14004ed47  lea     rcx, [rsp+48h+VolumeRootPath]; VolumeRootPath
0x14004ed4c  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x14004ed53  nop     dword ptr [rax+rax+00h]
0x14004ed58  mov     r9d, eax
0x14004ed5b  test    eax, 0BFFFFFFFh
0x14004ed60  jnz     short loc_14004ED73
0x14004ed62  lea     rcx, [rsp+48h+VolumeRootPath]; this
0x14004ed67  call    ?FreeString@ustring@RefsDedup@@AEAAXXZ; RefsDedup::ustring::FreeString(void)
0x14004ed6c  add     rsp, 40h
0x14004ed70  pop     rbx
0x14004ed71  retn
0x14004ed73  mov     rcx, rbx
0x14004ed76  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x14004ed7b  mov     rcx, [rsp+48h]; this
0x14004ed80  mov     [rsp+48h+var_20], rax; char *
0x14004ed85  lea     rax, aFailedToCreate_4; "Failed to create 'System Volume Informa"...
0x14004ed8c  mov     qword ptr [rsp+48h+var_28], rax; int
0x14004ed91  lea     r8, aOnecoreBaseFsR_2; "onecore\\base\\fs\\refsdedupsvc\\svclib"...
0x14004ed98  mov     edx, 14Ah; void *
0x14004ed9d  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x14004eda3  mov     r9d, eax; char *
0x14004eda6  lea     r8, aOnecoreBaseFsR_2; "onecore\\base\\fs\\refsdedupsvc\\svclib"...
0x14004edad  mov     edx, 145h; void *
0x14004edb2  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
