# EnterpriseFeatureControl::ReadSkuUpdateManagementGroup(bool *)

- ea: `0x180036dd0`
- end: `0x180036ef5`
- name: `?ReadSkuUpdateManagementGroup@EnterpriseFeatureControl@@CAJPEA_N@Z`
- size: `293`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800359e4`

## callees

- `0x180007660`
- `0x1800183d4`
- `0x1800183f4`
- `0x180036dd0`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180036e32`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180036e32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036e68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036e68`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180036ed0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180036ed0`

## string_xrefs

- `0x180036e2b`: `ext-ms-win-security-slc-l1-1-0`
- `0x180036e92`: `UpdatePolicy-UpdateManagementGroup`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EnterpriseFeatureControl::ReadSkuUpdateManagementGroup(bool *a1)
{
  HMODULE Library; // rax
  const char *v4; // r9
  HMODULE v5; // rbx
  FARPROC ProcAddress; // rax
  const char *v7; // r9
  unsigned int LastError; // edi
  int v9; // eax
  int v10; // esi
  int v11; // [rsp+20h] [rbp-28h]
  int v12; // [rsp+20h] [rbp-28h]
  int v13; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v13 = 0;
  if ( a1 )
  {
    Library = LoadLibraryExW(L"ext-ms-win-security-slc-l1-1-0", 0, 0x800u);
    v5 = Library;
    v12 = (int)Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "SLGetWindowsInformationDWORD");
      if ( ProcAddress )
      {
        v9 = ((__int64 (__fastcall *)(const wchar_t *, int *))ProcAddress)(L"UpdatePolicy-UpdateManagementGroup", &v13);
        v10 = v9;
        if ( v9 >= 0 )
        {
          *a1 = v13 == 0;
          LastError = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBF,
            (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
            (const char *)(unsigned int)v9,
            v12);
          LastError = v10;
        }
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xBE,
                      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
                      v7);
      }
      FreeLibrary(v5);
      return LastError;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xBA,
               (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
               v4);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)0x80004003LL,
      v11);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180036dd0  mov     [rsp+arg_8], rbx
0x180036dd5  mov     [rsp+arg_10], rsi
0x180036dda  push    rdi
0x180036ddb  sub     rsp, 40h
0x180036ddf  mov     rax, cs:__security_cookie
0x180036de6  xor     rax, rsp
0x180036de9  mov     [rsp+48h+var_18], rax
0x180036dee  mov     rdi, rcx
0x180036df1  mov     [rsp+48h+var_20], 0
0x180036df9  test    rcx, rcx
0x180036dfc  jnz     short loc_180036E23
0x180036dfe  mov     rcx, [rsp+48h]; this
0x180036e03  mov     ebx, 80004003h
0x180036e08  mov     r9d, ebx; char *
0x180036e0b  lea     r8, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180036e12  mov     edx, 0B7h; void *
0x180036e17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036e1c  mov     eax, ebx
0x180036e1e  jmp     loc_180036ED8
0x180036e23  xor     edx, edx; hFile
0x180036e25  mov     r8d, 800h; dwFlags
0x180036e2b  lea     rcx, aExtMsWinSecuri; "ext-ms-win-security-slc-l1-1-0"
0x180036e32  call    cs:__imp_LoadLibraryExW
0x180036e38  mov     rbx, rax
0x180036e3b  mov     qword ptr [rsp+48h+var_28], rax; int
0x180036e40  test    rax, rax
0x180036e43  jnz     short loc_180036E5E
0x180036e45  mov     rcx, [rsp+48h]; this
0x180036e4a  lea     r8, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180036e51  mov     edx, 0BAh; void *
0x180036e56  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036e5b  nop
0x180036e5c  jmp     short loc_180036ED8
0x180036e5e  lea     rdx, aSlgetwindowsin; "SLGetWindowsInformationDWORD"
0x180036e65  mov     rcx, rbx; hModule
0x180036e68  call    cs:__imp_GetProcAddress
0x180036e6e  test    rax, rax
0x180036e71  jnz     short loc_180036E8D
0x180036e73  mov     rcx, [rsp+48h]; this
0x180036e78  lea     r8, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180036e7f  mov     edx, 0BEh; void *
0x180036e84  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036e89  mov     edi, eax
0x180036e8b  jmp     short loc_180036ECD
0x180036e8d  lea     rdx, [rsp+48h+var_20]
0x180036e92  lea     rcx, aUpdatepolicyUp; "UpdatePolicy-UpdateManagementGroup"
0x180036e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e9e  mov     esi, eax
0x180036ea0  test    eax, eax
0x180036ea2  jns     short loc_180036EC1
0x180036ea4  mov     rcx, [rsp+48h]; this
0x180036ea9  mov     r9d, eax; char *
0x180036eac  lea     r8, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180036eb3  mov     edx, 0BFh; void *
0x180036eb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036ebd  mov     edi, esi
0x180036ebf  jmp     short loc_180036ECD
0x180036ec1  cmp     [rsp+48h+var_20], 0
0x180036ec6  setz    al
0x180036ec9  mov     [rdi], al
0x180036ecb  xor     edi, edi
0x180036ecd  mov     rcx, rbx; hLibModule
0x180036ed0  call    cs:__imp_FreeLibrary
0x180036ed6  mov     eax, edi
0x180036ed8  mov     rcx, [rsp+48h+var_18]
0x180036edd  xor     rcx, rsp; StackCookie
0x180036ee0  call    __security_check_cookie
0x180036ee5  mov     rbx, [rsp+48h+arg_8]
0x180036eea  mov     rsi, [rsp+48h+arg_10]
0x180036eef  add     rsp, 40h
0x180036ef3  pop     rdi
0x180036ef4  retn
```
