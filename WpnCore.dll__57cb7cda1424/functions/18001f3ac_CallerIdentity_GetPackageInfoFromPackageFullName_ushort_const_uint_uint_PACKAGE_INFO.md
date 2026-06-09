# CallerIdentity::GetPackageInfoFromPackageFullName(ushort const *,uint,uint *,PACKAGE_INFO * *)

- ea: `0x18001f3ac`
- end: `0x18001f4e6`
- name: `?GetPackageInfoFromPackageFullName@CallerIdentity@@YAJPEBGIPEAIPEAPEAUPACKAGE_INFO@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, UINT32 flags, unsigned int, unsigned int *, struct PACKAGE_INFO **)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ea90`
- `0x1800c5510`

## callees

- `0x180011618`
- `0x18001f3ac`
- `0x18001f4ec`
- `0x18001f5bc`
- `0x18009abf8`
- `0x1800f53f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f444`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f444`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f4cc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f4cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f47a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f47a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f404`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f404`

## string_xrefs

- `0x18001f421`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageInfoFromPackageFullName(
        CallerIdentity *this,
        UINT32 flags,
        _DWORD *a3,
        unsigned int *a4)
{
  unsigned int v5; // r14d
  const char *v8; // r9
  bool v9; // di
  int LastError; // eax
  unsigned int v11; // ebx
  HANDLE CurrentProcess; // rax
  unsigned __int16 **v13; // r8
  int PackageFullNameFromProcess; // eax
  void *v15; // rbx
  int PackageInfoFromCurrentProcess; // eax
  unsigned int v17; // edi
  struct PACKAGE_INFO **v19; // r9
  struct PACKAGE_INFO **bIgnoreCase; // [rsp+20h] [rbp-58h]
  LPVOID pv[9]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v23; // [rsp+90h] [rbp+18h] BYREF
  DWORD v24; // [rsp+98h] [rbp+20h] BYREF

  *a3 = 0;
  *(_QWORD *)a4 = 0;
  v23 = 0;
  v5 = (unsigned int)a3;
  v24 = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenIsAppContainer, &v23, 4u, &v24) )
  {
    v9 = v23 != 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x298,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v8);
    v9 = 0;
    v11 = LastError;
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_package.cpp",
        (const char *)(unsigned int)LastError,
        (int)bIgnoreCase);
      return v11;
    }
  }
  pv[0] = 0;
  CurrentProcess = GetCurrentProcess();
  PackageFullNameFromProcess = CallerIdentity::GetPackageFullNameFromProcess(CurrentProcess, pv, v13);
  v15 = pv[0];
  if ( PackageFullNameFromProcess >= 0 && v9 && CompareStringOrdinal((LPCWCH)this, -1, (LPCWCH)pv[0], -1, 1) == 2 )
    PackageInfoFromCurrentProcess = CallerIdentity::GetPackageInfoFromCurrentProcess(flags, v5, a4, v19);
  else
    PackageInfoFromCurrentProcess = CallerIdentity::GetPackageInfoFromPackageFullNameWithoutInProcessCache(
                                      this,
                                      (const unsigned __int16 *)flags,
                                      v5,
                                      a4,
                                      bIgnoreCase);
  v17 = PackageInfoFromCurrentProcess;
  if ( v15 )
    CoTaskMemFree(v15);
  return v17;
}

```

## disassembly

```asm
0x18001f3ac  mov     r11, rsp
0x18001f3af  mov     [r11+8], rbx
0x18001f3b3  push    rbp
0x18001f3b4  push    rsi
0x18001f3b5  push    rdi
0x18001f3b6  push    r14
0x18001f3b8  push    r15
0x18001f3ba  sub     rsp, 50h
0x18001f3be  mov     dword ptr [r8], 0
0x18001f3c5  lea     rax, [r11+20h]
0x18001f3c9  mov     qword ptr [r9], 0
0x18001f3d0  mov     rsi, r9
0x18001f3d3  mov     r9d, 4; TokenInformationLength
0x18001f3d9  mov     dword ptr [r11+18h], 0
0x18001f3e1  mov     r14, r8
0x18001f3e4  mov     dword ptr [r11+20h], 0
0x18001f3ec  mov     ebp, edx
0x18001f3ee  mov     [r11-58h], rax
0x18001f3f2  mov     r15, rcx
0x18001f3f5  lea     r8, [r11+18h]; TokenInformation
0x18001f3f9  lea     edx, [r9+19h]; TokenInformationClass
0x18001f3fd  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18001f404  call    cs:__imp_GetTokenInformation
0x18001f40a  test    eax, eax
0x18001f40c  jz      short loc_18001F41C
0x18001f40e  cmp     [rsp+78h+arg_10], 0
0x18001f416  setnz   dil
0x18001f41a  jmp     short loc_18001F43B
0x18001f41c  mov     rcx, [rsp+78h]; this
0x18001f421  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f428  mov     edx, 298h; void *
0x18001f42d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f432  xor     dil, dil
0x18001f435  mov     ebx, eax
0x18001f437  test    eax, eax
0x18001f439  js      short loc_18001F496
0x18001f43b  mov     [rsp+78h+pv], 0
0x18001f444  call    cs:__imp_GetCurrentProcess
0x18001f44a  mov     rcx, rax; hProcess
0x18001f44d  lea     rdx, [rsp+78h+pv]; void *
0x18001f452  call    ?GetPackageFullNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPackageFullNameFromProcess(void *,ushort * *)
0x18001f457  mov     rbx, [rsp+78h+pv]
0x18001f45c  test    eax, eax
0x18001f45e  jns     short loc_18001F4B3
0x18001f460  mov     r9, rsi; unsigned int *
0x18001f463  mov     r8, r14; unsigned int
0x18001f466  mov     edx, ebp; unsigned __int16 *
0x18001f468  mov     rcx, r15; this
0x18001f46b  call    ?GetPackageInfoFromPackageFullNameWithoutInProcessCache@CallerIdentity@@YAJPEBGIPEAIPEAPEAUPACKAGE_INFO@@@Z; CallerIdentity::GetPackageInfoFromPackageFullNameWithoutInProcessCache(ushort const *,uint,uint *,PACKAGE_INFO * *)
0x18001f470  mov     edi, eax
0x18001f472  test    rbx, rbx
0x18001f475  jz      short loc_18001F480
0x18001f477  mov     rcx, rbx; pv
0x18001f47a  call    cs:__imp_CoTaskMemFree
0x18001f480  mov     eax, edi
0x18001f482  mov     rbx, [rsp+78h+arg_0]
0x18001f48a  add     rsp, 50h
0x18001f48e  pop     r15
0x18001f490  pop     r14
0x18001f492  pop     rdi
0x18001f493  pop     rsi
0x18001f494  pop     rbp
0x18001f495  retn
0x18001f496  mov     rcx, [rsp+78h]; this
0x18001f49b  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18001f4a2  mov     r9d, ebx; char *
0x18001f4a5  mov     edx, 42h ; 'B'; void *
0x18001f4aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f4af  mov     eax, ebx
0x18001f4b1  jmp     short loc_18001F482
0x18001f4b3  test    dil, dil
0x18001f4b6  jz      short loc_18001F460
0x18001f4b8  or      edx, 0FFFFFFFFh; cchCount1
0x18001f4bb  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18001f4c3  mov     r9d, edx; cchCount2
0x18001f4c6  mov     r8, rbx; lpString2
0x18001f4c9  mov     rcx, r15; lpString1
0x18001f4cc  call    cs:__imp_CompareStringOrdinal
0x18001f4d2  cmp     eax, 2
0x18001f4d5  jnz     short loc_18001F460
0x18001f4d7  mov     r8, rsi; unsigned int *
0x18001f4da  mov     rdx, r14; unsigned int
0x18001f4dd  mov     ecx, ebp; flags
0x18001f4df  call    ?GetPackageInfoFromCurrentProcess@CallerIdentity@@YAJIPEAIPEAPEAUPACKAGE_INFO@@@Z; CallerIdentity::GetPackageInfoFromCurrentProcess(uint,uint *,PACKAGE_INFO * *)
0x18001f4e4  jmp     short loc_18001F470
```
