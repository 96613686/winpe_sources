# NLG::FindProof::GetModuleFilePath(ushort *,int,HINSTANCE__ *)

- ea: `0x180049b2c`
- end: `0x180049bf8`
- name: `?GetModuleFilePath@FindProof@NLG@@SAHPEAGHPEAUHINSTANCE__@@@Z`
- size: `204`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, HINSTANCE)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180016bf4`

## callees

- `0x180016258`
- `0x1800162e4`
- `0x180049b2c`
- `0x18009e300`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x180049ba4`
- `msvcrt!_wsplitpath_s` at `0x180049ba4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180049b55`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180049b55`

## pseudocode

```c
DWORD __fastcall NLG::FindProof::GetModuleFilePath(unsigned __int16 *a1, __int64 a2, HINSTANCE a3)
{
  DWORD result; // eax
  wchar_t Drive[8]; // [rsp+50h] [rbp-238h] BYREF
  wchar_t Dir[264]; // [rsp+60h] [rbp-228h] BYREF

  result = GetModuleFileNameW(0, a1, 0x410u);
  if ( result )
  {
    _wsplitpath_s(a1, Drive, 4u, Dir, 0x105u, 0, 0, 0, 0);
    return StringCchCopyW(a1, 0x410u, Drive) >= 0 && StringCchCatW(a1, 0x410u, Dir) >= 0;
  }
  else
  {
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180049b2c  push    rbx
0x180049b2e  sub     rsp, 280h
0x180049b35  mov     rax, cs:__security_cookie
0x180049b3c  xor     rax, rsp
0x180049b3f  mov     [rsp+288h+var_18], rax
0x180049b47  mov     rbx, rcx
0x180049b4a  mov     rdx, rcx; lpFilename
0x180049b4d  xor     ecx, ecx; hModule
0x180049b4f  mov     r8d, 410h; nSize
0x180049b55  call    cs:__imp_GetModuleFileNameW
0x180049b5b  test    eax, eax
0x180049b5d  jnz     short loc_180049B64
0x180049b5f  mov     [rbx], ax
0x180049b62  jmp     short loc_180049BDF
0x180049b64  mov     [rsp+288h+ExtCount], 0; ExtCount
0x180049b6d  lea     r9, [rsp+288h+Dir]; Dir
0x180049b72  mov     [rsp+288h+Ext], 0; Ext
0x180049b7b  lea     rdx, [rsp+288h+Drive]; Drive
0x180049b80  mov     [rsp+288h+FilenameCount], 0; FilenameCount
0x180049b89  mov     r8d, 4; DriveCount
0x180049b8f  mov     [rsp+288h+Filename], 0; Filename
0x180049b98  mov     rcx, rbx; FullPath
0x180049b9b  mov     [rsp+288h+DirCount], 105h; DirCount
0x180049ba4  call    cs:__imp__wsplitpath_s
0x180049baa  lea     r8, [rsp+288h+Drive]; unsigned __int16 *
0x180049baf  mov     edx, 410h; unsigned __int64
0x180049bb4  mov     rcx, rbx; unsigned __int16 *
0x180049bb7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180049bbc  test    eax, eax
0x180049bbe  js      short loc_180049BDD
0x180049bc0  lea     r8, [rsp+288h+Dir]; unsigned __int16 *
0x180049bc5  mov     edx, 410h; unsigned __int64
0x180049bca  mov     rcx, rbx; unsigned __int16 *
0x180049bcd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180049bd2  test    eax, eax
0x180049bd4  js      short loc_180049BDD
0x180049bd6  mov     eax, 1
0x180049bdb  jmp     short loc_180049BDF
0x180049bdd  xor     eax, eax
0x180049bdf  mov     rcx, [rsp+288h+var_18]
0x180049be7  xor     rcx, rsp; StackCookie
0x180049bea  call    __security_check_cookie
0x180049bef  add     rsp, 280h
0x180049bf6  pop     rbx
0x180049bf7  retn
```
