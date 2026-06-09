# RegInstallW

- ea: `0x180003be0`
- end: `0x180003cd9`
- name: `RegInstallW`
- size: `249`
- prototype: `HRESULT __stdcall(HMODULE hmod, LPCWSTR pszSection, const STRTABLEW *pstTable)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180003b50`

## callees

- `0x180002928`
- `0x180002ad4`
- `0x180003978`
- `0x180003a5c`
- `0x180003be0`
- `0x18000c574`
- `0x18001b980`

## import_xrefs

- `KERNEL32!WritePrivateProfileStringW` at `0x180003c7f`
- `KERNEL32!WritePrivateProfileStringW` at `0x180003c7f`
- `KERNEL32!DeleteFileW` at `0x180003ca1`
- `KERNEL32!DeleteFileW` at `0x180003ca1`

## string_xrefs

- `0x180003c06`: `RegInstall: Section=%1\n`
- `0x180003caa`: `RegInstall: Section=%1 End hr=%2!x!\n`

## pseudocode

```c
HRESULT __stdcall RegInstallW(HMODULE hmod, LPCWSTR pszSection, const STRTABLEW *pstTable)
{
  HRESULT InfFile; // ebx
  unsigned int v8[4]; // [rsp+20h] [rbp-258h] BYREF
  WCHAR FileName[264]; // [rsp+30h] [rbp-248h] BYREF

  v8[0] = 0;
  AdvWriteToLog(L"RegInstall: Section=%1\r\n");
  FileName[0] = 0;
  InfFile = CreateInfFile(hmod, FileName, v8);
  if ( InfFile >= 0 )
  {
    InfFile = WritePredefinedStrings(FileName, hmod, v8[0]);
    if ( InfFile >= 0 )
    {
      if ( !pstTable || (InfFile = WriteCallerStrings(FileName, hmod, pstTable, v8[0]), InfFile >= 0) )
      {
        WritePrivateProfileStringW(0, 0, 0, FileName);
        InfFile = ExecuteInfSection(FileName, (WCHAR *)pszSection);
      }
    }
  }
  if ( FileName[0] )
    DeleteFileW(FileName);
  AdvWriteToLog(L"RegInstall: Section=%1 End hr=%2!x!\r\n", pszSection, (unsigned int)InfFile);
  return InfFile;
}

```

## disassembly

```asm
0x180003be0  push    rbx
0x180003be2  push    rbp
0x180003be3  push    rsi
0x180003be4  push    rdi
0x180003be5  push    r14
0x180003be7  sub     rsp, 250h
0x180003bee  mov     rax, cs:__security_cookie
0x180003bf5  xor     rax, rsp
0x180003bf8  mov     [rsp+278h+var_38], rax
0x180003c00  mov     rbp, rcx
0x180003c03  xor     r14d, r14d
0x180003c06  lea     rcx, aReginstallSect; "RegInstall: Section=%1\r\n"
0x180003c0d  mov     [rsp+278h+var_258], r14d
0x180003c12  mov     rsi, r8
0x180003c15  mov     rdi, rdx
0x180003c18  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180003c1d  lea     r8, [rsp+278h+var_258]; unsigned int *
0x180003c22  mov     [rsp+278h+FileName], r14w
0x180003c28  lea     rdx, [rsp+278h+FileName]; lpFileName
0x180003c2d  mov     rcx, rbp; hModule
0x180003c30  call    ?CreateInfFile@@YAJPEAUHINSTANCE__@@PEAGPEAK@Z; CreateInfFile(HINSTANCE__ *,ushort *,ulong *)
0x180003c35  mov     ebx, eax
0x180003c37  test    eax, eax
0x180003c39  js      short loc_180003C94
0x180003c3b  mov     r8d, [rsp+278h+var_258]; unsigned int
0x180003c40  lea     rcx, [rsp+278h+FileName]; unsigned __int16 *
0x180003c45  mov     rdx, rbp; hModule
0x180003c48  call    ?WritePredefinedStrings@@YAJPEBGPEAUHINSTANCE__@@K@Z; WritePredefinedStrings(ushort const *,HINSTANCE__ *,ulong)
0x180003c4d  mov     ebx, eax
0x180003c4f  test    eax, eax
0x180003c51  js      short loc_180003C94
0x180003c53  test    rsi, rsi
0x180003c56  jz      short loc_180003C73
0x180003c58  mov     r9d, [rsp+278h+var_258]; unsigned int
0x180003c5d  lea     rcx, [rsp+278h+FileName]; unsigned __int16 *
0x180003c62  mov     r8, rsi; struct _StrTableW *
0x180003c65  mov     rdx, rbp; hInstance
0x180003c68  call    ?WriteCallerStrings@@YAJPEBGPEAUHINSTANCE__@@PEBU_StrTableW@@K@Z; WriteCallerStrings(ushort const *,HINSTANCE__ *,_StrTableW const *,ulong)
0x180003c6d  mov     ebx, eax
0x180003c6f  test    eax, eax
0x180003c71  js      short loc_180003C94
0x180003c73  lea     r9, [rsp+278h+FileName]; lpFileName
0x180003c78  xor     r8d, r8d; lpString
0x180003c7b  xor     edx, edx; lpKeyName
0x180003c7d  xor     ecx, ecx; lpAppName
0x180003c7f  call    cs:__imp_WritePrivateProfileStringW
0x180003c85  mov     rdx, rdi; lpAppName
0x180003c88  lea     rcx, [rsp+278h+FileName]; unsigned __int16 *
0x180003c8d  call    ?ExecuteInfSection@@YAJPEBG0@Z; ExecuteInfSection(ushort const *,ushort const *)
0x180003c92  mov     ebx, eax
0x180003c94  cmp     [rsp+278h+FileName], r14w
0x180003c9a  jz      short loc_180003CA7
0x180003c9c  lea     rcx, [rsp+278h+FileName]; lpFileName
0x180003ca1  call    cs:__imp_DeleteFileW
0x180003ca7  mov     r8d, ebx
0x180003caa  lea     rcx, aReginstallSect_0; "RegInstall: Section=%1 End hr=%2!x!\r\n"
0x180003cb1  mov     rdx, rdi
0x180003cb4  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180003cb9  mov     eax, ebx
0x180003cbb  mov     rcx, [rsp+278h+var_38]
0x180003cc3  xor     rcx, rsp; StackCookie
0x180003cc6  call    __security_check_cookie
0x180003ccb  add     rsp, 250h
0x180003cd2  pop     r14
0x180003cd4  pop     rdi
0x180003cd5  pop     rsi
0x180003cd6  pop     rbp
0x180003cd7  pop     rbx
0x180003cd8  retn
```
