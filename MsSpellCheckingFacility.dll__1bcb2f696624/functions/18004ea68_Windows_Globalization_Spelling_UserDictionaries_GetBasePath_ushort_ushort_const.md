# Windows::Globalization::Spelling::UserDictionaries::GetBasePath(ushort *,ushort const *)

- ea: `0x18004ea68`
- end: `0x18004eaef`
- name: `?GetBasePath@UserDictionaries@Spelling@Globalization@Windows@@SAJPEAGPEBG@Z`
- size: `135`
- prototype: `__int64 __fastcall(LPWSTR pszDest, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180021b80`
- `0x18002c1ac`
- `0x18007ee64`

## callees

- `0x1800206ec`
- `0x18004ea68`
- `0x18006a0e4`
- `0x180075078`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004eadc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004eadc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18004eab8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18004eab8`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::UserDictionaries::GetBasePath(
        LPWSTR pszDest,
        const unsigned __int16 *a2)
{
  int RoamingAppDataPath; // eax
  unsigned int v4; // ebx
  unsigned int v5; // r8d
  const char *v6; // r9
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPCWSTR pszDir; // [rsp+40h] [rbp+18h] BYREF

  pszDir = 0;
  RoamingAppDataPath = Windows::Globalization::Spelling::SpellerUDFiles::GetRoamingAppDataPath(
                         (unsigned __int16 **)&pszDir,
                         a2);
  v4 = RoamingAppDataPath;
  if ( RoamingAppDataPath >= 0 )
  {
    if ( !PathCombineW(pszDest, pszDir, L"Microsoft\\Spelling") )
    {
      wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x307, v5, v6);
      v4 = -2147467259;
    }
    CoTaskMemFree((LPVOID)pszDir);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2FF,
      (unsigned int)"OnecoreUAP\\private\\Base\\inc\\SpellerUserDictionaries.h",
      (const char *)(unsigned int)RoamingAppDataPath,
      v8);
  }
  return v4;
}

```

## disassembly

```asm
0x18004ea68  mov     [rsp+arg_0], rbx
0x18004ea6d  push    rdi; int
0x18004ea6e  sub     rsp, 20h
0x18004ea72  mov     rdi, rcx
0x18004ea75  mov     [rsp+28h+pszDir], 0
0x18004ea7e  lea     rcx, [rsp+28h+pszDir]; unsigned __int16 **
0x18004ea83  call    ?GetRoamingAppDataPath@SpellerUDFiles@Spelling@Globalization@Windows@@SAJPEAPEAGPEBG@Z; Windows::Globalization::Spelling::SpellerUDFiles::GetRoamingAppDataPath(ushort * *,ushort const *)
0x18004ea88  mov     ebx, eax
0x18004ea8a  test    eax, eax
0x18004ea8c  jns     short loc_18004EAA9
0x18004ea8e  mov     rcx, [rsp+28h]; this
0x18004ea93  lea     r8, aOnecoreuapPriv; "OnecoreUAP\\private\\Base\\inc\\Speller"...
0x18004ea9a  mov     r9d, eax; char *
0x18004ea9d  mov     edx, 2FFh; void *
0x18004eaa2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004eaa7  jmp     short loc_18004EAE2
0x18004eaa9  mov     rdx, [rsp+28h+pszDir]; pszDir
0x18004eaae  lea     r8, pszFile; "Microsoft\\Spelling"
0x18004eab5  mov     rcx, rdi; pszDest
0x18004eab8  call    cs:__imp_PathCombineW
0x18004eabe  test    rax, rax
0x18004eac1  jnz     short loc_18004EAD7
0x18004eac3  mov     rcx, [rsp+28h]; this
0x18004eac8  mov     edx, 307h; void *
0x18004eacd  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18004ead2  mov     ebx, 80004005h
0x18004ead7  mov     rcx, [rsp+28h+pszDir]; pv
0x18004eadc  call    cs:__imp_CoTaskMemFree
0x18004eae2  mov     eax, ebx
0x18004eae4  mov     rbx, [rsp+28h+arg_0]
0x18004eae9  add     rsp, 20h
0x18004eaed  pop     rdi
0x18004eaee  retn
```
