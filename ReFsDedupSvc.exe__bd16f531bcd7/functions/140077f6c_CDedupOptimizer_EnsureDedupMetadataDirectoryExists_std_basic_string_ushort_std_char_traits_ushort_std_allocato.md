# CDedupOptimizer::EnsureDedupMetadataDirectoryExists(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140077f6c`
- end: `0x14007815d`
- name: `?EnsureDedupMetadataDirectoryExists@CDedupOptimizer@@AEAAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting`

## callers

- `0x1400793e8`

## callees

- `0x140004870`
- `0x140019600`
- `0x14001983c`
- `0x14004f0a0`
- `0x140063bbc`
- `0x140069d88`
- `0x140069dc8`
- `0x1400742e8`
- `0x140077f6c`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x140077fec`
- `ntdll!RtlDoesFileExists_U` at `0x1400780b6`
- `ntdll!RtlDoesFileExists_U` at `0x140077fec`
- `ntdll!RtlDoesFileExists_U` at `0x1400780b6`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x140078071`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x140078071`
- `ntdll!RtlNtStatusToDosError` at `0x140078033`
- `ntdll!RtlNtStatusToDosError` at `0x140078033`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x140078063`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x140078063`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14007801e`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14007801e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007807d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400780e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007807d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400780e4`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400780d4`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400780d4`

## string_xrefs

- `0x1400780fc`: `Failed to create directory %s, error = 0x%x\n`
- `0x1400780a1`: `Failed to create System Volume Information folder, path: %s, error = 0x%x\n`

## pseudocode

```c
__int64 __fastcall CDedupOptimizer::EnsureDedupMetadataDirectoryExists(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  ULONG v4; // ebx
  const WCHAR *v5; // rax
  __int64 v6; // rax
  NTSTATUS v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  NTSTATUS v10; // eax
  DWORD LastError; // eax
  __int64 v12; // rax
  const wchar_t *v13; // rdx
  const WCHAR *v14; // rax
  const WCHAR *v15; // rax
  DWORD v17; // [rsp+20h] [rbp-39h] BYREF
  __int64 v18; // [rsp+28h] [rbp-31h] BYREF
  UNICODE_STRING VolumeRootPath; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v20[32]; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v22[32]; // [rsp+80h] [rbp+27h] BYREF

  std::operator+<unsigned short>(v21, a2, L"System Volume Information");
  v3 = std::operator+<unsigned short>(v22, v21, L"\\");
  std::operator+<unsigned short>(v20, v3, L"NativeDedup");
  std::wstring::_Tidy_deallocate(v22);
  VolumeRootPath = 0;
  v4 = 0;
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
  if ( !RtlDoesFileExists_U(v5) )
  {
    RefsDedup::ustring::FreeString((RefsDedup::ustring *)&VolumeRootPath);
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v7 = RtlDosPathNameToNtPathName_U_WithStatus(v6, &VolumeRootPath, 0, 0);
    v17 = v7;
    if ( v7 < 0 )
    {
      v4 = RtlNtStatusToDosError(v7);
      v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      ((void (__fastcall *)(__int64, __int64, __int64 *, DWORD *))DedupUtil::Print<unsigned short const *,long &>)(
        v9,
        v8,
        &v18,
        &v17);
      goto LABEL_11;
    }
    v10 = RtlCreateSystemVolumeInformationFolder(&VolumeRootPath);
    RtlSetLastWin32ErrorAndNtStatusFromNtStatus(v10);
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError )
    {
      v4 = 183;
      if ( LastError != 183 )
      {
        v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
        v13 = L"Failed to create System Volume Information folder, path: %s, error = 0x%x\n";
LABEL_10:
        v18 = v12;
        DedupUtil::Print<unsigned short const *,unsigned long &>(6, v13, &v18, &v17);
        v4 = v17;
        goto LABEL_11;
      }
    }
  }
  v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
  if ( !RtlDoesFileExists_U(v14) )
  {
    v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
    if ( !CreateDirectoryW(v15, 0) )
    {
      v17 = GetLastError();
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
      v13 = L"Failed to create directory %s, error = 0x%x\n";
      goto LABEL_10;
    }
  }
LABEL_11:
  RefsDedup::ustring::FreeString((RefsDedup::ustring *)&VolumeRootPath);
  std::wstring::_Tidy_deallocate(v20);
  std::wstring::_Tidy_deallocate(v21);
  return v4;
}

```

## disassembly

```asm
0x140077f6c  mov     [rsp-8+arg_0], rbx
0x140077f71  mov     [rsp-8+arg_10], rdi
0x140077f76  push    rbp
0x140077f77  lea     rbp, [rsp-57h]
0x140077f7c  sub     rsp, 0B0h
0x140077f83  mov     rax, cs:__security_cookie
0x140077f8a  xor     rax, rsp
0x140077f8d  mov     [rbp+57h+var_10], rax
0x140077f91  mov     rdi, rdx
0x140077f94  lea     r8, aSystemVolumeIn; "System Volume Information"
0x140077f9b  lea     rcx, [rbp+57h+var_50]
0x140077f9f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x140077fa4  nop
0x140077fa5  lea     r8, StringValue; "\\"
0x140077fac  lea     rdx, [rbp+57h+var_50]
0x140077fb0  lea     rcx, [rbp+57h+var_30]
0x140077fb4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x140077fb9  nop
0x140077fba  lea     r8, aNativededup; "NativeDedup"
0x140077fc1  mov     rdx, rax
0x140077fc4  lea     rcx, [rbp+57h+var_70]
0x140077fc8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x140077fcd  nop
0x140077fce  lea     rcx, [rbp+57h+var_30]
0x140077fd2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140077fd7  xorps   xmm0, xmm0
0x140077fda  movups  xmmword ptr [rbp+57h+VolumeRootPath.Length], xmm0
0x140077fde  xor     ebx, ebx
0x140077fe0  lea     rcx, [rbp+57h+var_50]
0x140077fe4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140077fe9  mov     rcx, rax; FileName
0x140077fec  call    cs:__imp_RtlDoesFileExists_U
0x140077ff3  nop     dword ptr [rax+rax+00h]
0x140077ff8  test    al, al
0x140077ffa  jnz     loc_1400780AA
0x140078000  lea     rcx, [rbp+57h+VolumeRootPath]; this
0x140078004  call    ?FreeString@ustring@RefsDedup@@AEAAXXZ; RefsDedup::ustring::FreeString(void)
0x140078009  mov     rcx, rdi
0x14007800c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140078011  xor     r9d, r9d
0x140078014  xor     r8d, r8d
0x140078017  lea     rdx, [rbp+57h+VolumeRootPath]
0x14007801b  mov     rcx, rax
0x14007801e  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x140078025  nop     dword ptr [rax+rax+00h]
0x14007802a  mov     [rbp+57h+var_90], eax
0x14007802d  test    eax, eax
0x14007802f  jns     short loc_14007805F
0x140078031  mov     ecx, eax; Status
0x140078033  call    cs:__imp_RtlNtStatusToDosError
0x14007803a  nop     dword ptr [rax+rax+00h]
0x14007803f  mov     ebx, eax
0x140078041  mov     rcx, rdi
0x140078044  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140078049  mov     [rbp+57h+var_88], rax
0x14007804d  lea     r9, [rbp+57h+var_90]
0x140078051  lea     r8, [rbp+57h+var_88]
0x140078055  call    ??$Print@PEBGAEAJ@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAPEBGAEAJ@Z; DedupUtil::Print<ushort const *,long &>(DedupUtil::MessageType,ushort const *,ushort const * &&,long &)
0x14007805a  jmp     loc_14007811C
0x14007805f  lea     rcx, [rbp+57h+VolumeRootPath]; VolumeRootPath
0x140078063  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x14007806a  nop     dword ptr [rax+rax+00h]
0x14007806f  mov     ecx, eax; Status
0x140078071  call    cs:__imp_RtlSetLastWin32ErrorAndNtStatusFromNtStatus
0x140078078  nop     dword ptr [rax+rax+00h]
0x14007807d  call    cs:__imp_GetLastError
0x140078084  nop     dword ptr [rax+rax+00h]
0x140078089  mov     [rbp+57h+var_90], eax
0x14007808c  test    eax, eax
0x14007808e  jz      short loc_1400780AA
0x140078090  mov     ebx, 0B7h
0x140078095  cmp     eax, ebx
0x140078097  jz      short loc_1400780AA
0x140078099  mov     rcx, rdi
0x14007809c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400780a1  lea     rdx, aFailedToCreate_5; "Failed to create System Volume Informat"...
0x1400780a8  jmp     short loc_140078103
0x1400780aa  lea     rcx, [rbp+57h+var_70]
0x1400780ae  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400780b3  mov     rcx, rax; FileName
0x1400780b6  call    cs:__imp_RtlDoesFileExists_U
0x1400780bd  nop     dword ptr [rax+rax+00h]
0x1400780c2  test    al, al
0x1400780c4  jnz     short loc_14007811C
0x1400780c6  lea     rcx, [rbp+57h+var_70]
0x1400780ca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400780cf  mov     rcx, rax; lpPathName
0x1400780d2  xor     edx, edx; lpSecurityAttributes
0x1400780d4  call    cs:__imp_CreateDirectoryW
0x1400780db  nop     dword ptr [rax+rax+00h]
0x1400780e0  test    eax, eax
0x1400780e2  jnz     short loc_14007811C
0x1400780e4  call    cs:__imp_GetLastError
0x1400780eb  nop     dword ptr [rax+rax+00h]
0x1400780f0  mov     [rbp+57h+var_90], eax
0x1400780f3  lea     rcx, [rbp+57h+var_70]
0x1400780f7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400780fc  lea     rdx, aFailedToCreate; "Failed to create directory %s, error = "...
0x140078103  mov     [rbp+57h+var_88], rax
0x140078107  lea     r9, [rbp+57h+var_90]
0x14007810b  lea     r8, [rbp+57h+var_88]
0x14007810f  mov     ecx, 6
0x140078114  call    ??$Print@PEBGAEAK@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAPEBGAEAK@Z; DedupUtil::Print<ushort const *,ulong &>(DedupUtil::MessageType,ushort const *,ushort const * &&,ulong &)
0x140078119  mov     ebx, [rbp+57h+var_90]
0x14007811c  lea     rcx, [rbp+57h+VolumeRootPath]; this
0x140078120  call    ?FreeString@ustring@RefsDedup@@AEAAXXZ; RefsDedup::ustring::FreeString(void)
0x140078125  nop
0x140078126  lea     rcx, [rbp+57h+var_70]
0x14007812a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007812f  nop
0x140078130  lea     rcx, [rbp+57h+var_50]
0x140078134  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140078139  mov     eax, ebx
0x14007813b  mov     rcx, [rbp+57h+var_10]
0x14007813f  xor     rcx, rsp; StackCookie
0x140078142  call    __security_check_cookie
0x140078147  lea     r11, [rsp+0B0h+var_s0]
0x14007814f  mov     rbx, [r11+10h]
0x140078153  mov     rdi, [r11+20h]
0x140078157  mov     rsp, r11
0x14007815a  pop     rbp
0x14007815b  retn
```
