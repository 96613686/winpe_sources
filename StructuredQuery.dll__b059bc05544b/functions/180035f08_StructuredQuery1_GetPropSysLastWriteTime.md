# StructuredQuery1::GetPropSysLastWriteTime

- ea: `0x180035f08`
- end: `0x180035fa4`
- name: `StructuredQuery1::GetPropSysLastWriteTime`
- size: `156`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1800354d4`

## callees

- `0x180035f08`
- `0x18005daf0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180035f79`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180035f79`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180035f35`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180035f35`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180035f50`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180035f50`

## string_xrefs

- `0x180035f3f`: `propsys.dll`

## pseudocode

```c
int __fastcall StructuredQuery1::GetPropSysLastWriteTime(_QWORD *a1)
{
  int result; // eax
  __int128 FileInformation; // [rsp+20h] [rbp-258h] BYREF
  __int128 v4; // [rsp+30h] [rbp-248h]
  int v5; // [rsp+40h] [rbp-238h]
  WCHAR Buffer[264]; // [rsp+50h] [rbp-228h] BYREF

  *a1 = 0;
  result = GetSystemDirectoryW(Buffer, 0x104u);
  if ( result )
  {
    result = PathCchAppend(Buffer, 0x104u, L"propsys.dll");
    if ( result >= 0 )
    {
      v5 = 0;
      FileInformation = 0;
      v4 = 0;
      result = GetFileAttributesExW(Buffer, GetFileExInfoStandard, &FileInformation);
      if ( result )
      {
        result = DWORD1(v4);
        *a1 = *(_QWORD *)((char *)&v4 + 4);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180035f08  push    rbx
0x180035f0a  sub     rsp, 270h
0x180035f11  mov     rax, cs:__security_cookie
0x180035f18  xor     rax, rsp
0x180035f1b  mov     [rsp+278h+var_18], rax
0x180035f23  xor     eax, eax
0x180035f25  mov     rbx, rcx
0x180035f28  mov     [rcx], rax
0x180035f2b  mov     edx, 104h; uSize
0x180035f30  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x180035f35  call    cs:__imp_GetSystemDirectoryW
0x180035f3b  test    eax, eax
0x180035f3d  jz      short loc_180035F8B
0x180035f3f  lea     r8, aPropsysDll_0; "propsys.dll"
0x180035f46  mov     edx, 104h; cchPath
0x180035f4b  lea     rcx, [rsp+278h+Buffer]; pszPath
0x180035f50  call    cs:__imp_PathCchAppend
0x180035f56  test    eax, eax
0x180035f58  js      short loc_180035F8B
0x180035f5a  xorps   xmm0, xmm0
0x180035f5d  lea     r8, [rsp+278h+FileInformation]; lpFileInformation
0x180035f62  xor     eax, eax
0x180035f64  lea     rcx, [rsp+278h+Buffer]; lpFileName
0x180035f69  xor     edx, edx; fInfoLevelId
0x180035f6b  mov     [rsp+278h+var_238], eax
0x180035f6f  movups  [rsp+278h+FileInformation], xmm0
0x180035f74  movups  [rsp+278h+var_248], xmm0
0x180035f79  call    cs:__imp_GetFileAttributesExW
0x180035f7f  test    eax, eax
0x180035f81  jz      short loc_180035F8B
0x180035f83  mov     rax, qword ptr [rsp+278h+var_248+4]
0x180035f88  mov     [rbx], rax
0x180035f8b  mov     rcx, [rsp+278h+var_18]
0x180035f93  xor     rcx, rsp; StackCookie
0x180035f96  call    __security_check_cookie
0x180035f9b  add     rsp, 270h
0x180035fa2  pop     rbx
0x180035fa3  retn
```
