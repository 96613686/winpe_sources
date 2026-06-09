# EnterpriseFeatureControl::ReadSkuUpdateManagementGroup(bool *)

- ea: `0x18001a144`
- end: `0x18001a22d`
- name: `?ReadSkuUpdateManagementGroup@EnterpriseFeatureControl@@CAJPEA_N@Z`
- size: `233`
- prototype: `static int(bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180018ff4`

## callees

- `0x18000970c`
- `0x18000972c`
- `0x18001295c`
- `0x18001a144`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a1b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a1b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a190`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a190`

## string_xrefs

- `0x18001a189`: `ext-ms-win-security-slc-l1-1-0`
- `0x18001a1db`: `UpdatePolicy-UpdateManagementGroup`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnterpriseFeatureControl::ReadSkuUpdateManagementGroup(bool *a1)
{
  unsigned int LastError; // ebx
  HMODULE Library; // rax
  const char *v4; // r9
  __int64 v5; // rdx
  FARPROC ProcAddress; // rax
  int v7; // eax
  unsigned int v8; // edi
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v12; // [rsp+30h] [rbp+8h] BYREF
  HMODULE v13; // [rsp+38h] [rbp+10h] BYREF

  v12 = 0;
  if ( a1 )
  {
    Library = LoadLibraryExW(L"ext-ms-win-security-slc-l1-1-0", 0, 0x800u);
    v13 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "SLGetWindowsInformationDWORD");
      if ( ProcAddress )
      {
        v7 = ((__int64 (__fastcall *)(const wchar_t *, int *))ProcAddress)(L"UpdatePolicy-UpdateManagementGroup", &v12);
        v8 = v7;
        if ( v7 >= 0 )
        {
          *a1 = v12 == 0;
          LastError = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBF,
            (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
            (const char *)(unsigned int)v7,
            v10);
          LastError = v8;
        }
        goto LABEL_11;
      }
      v5 = 190;
    }
    else
    {
      v5 = 186;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
                  v4);
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v13);
    return LastError;
  }
  LastError = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB7,
    (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
    (const char *)0x80004003LL,
    v10);
  return LastError;
}

```

## disassembly

```asm
0x18001a144  mov     [rsp+arg_10], rbx
0x18001a149  push    rdi; int
0x18001a14a  sub     rsp, 20h
0x18001a14e  mov     rbx, rcx
0x18001a151  mov     [rsp+28h+arg_0], 0
0x18001a159  test    rcx, rcx
0x18001a15c  jnz     short loc_18001A181
0x18001a15e  mov     rcx, [rsp+28h]; this
0x18001a163  mov     ebx, 80004003h
0x18001a168  mov     r9d, ebx; char *
0x18001a16b  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18001a172  mov     edx, 0B7h; void *
0x18001a177  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a17c  jmp     loc_18001A220
0x18001a181  xor     edx, edx; hFile
0x18001a183  mov     r8d, 800h; dwFlags
0x18001a189  lea     rcx, aExtMsWinSecuri; "ext-ms-win-security-slc-l1-1-0"
0x18001a190  call    cs:__imp_LoadLibraryExW
0x18001a196  mov     [rsp+28h+arg_8], rax
0x18001a19b  test    rax, rax
0x18001a19e  jnz     short loc_18001A1A7
0x18001a1a0  mov     edx, 0BAh
0x18001a1a5  jmp     short loc_18001A1C1
0x18001a1a7  lea     rdx, aSlgetwindowsin; "SLGetWindowsInformationDWORD"
0x18001a1ae  mov     rcx, rax; hModule
0x18001a1b1  call    cs:__imp_GetProcAddress
0x18001a1b7  test    rax, rax
0x18001a1ba  jnz     short loc_18001A1D6
0x18001a1bc  mov     edx, 0BEh; void *
0x18001a1c1  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18001a1c8  mov     rcx, [rsp+28h]; this
0x18001a1cd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a1d2  mov     ebx, eax
0x18001a1d4  jmp     short loc_18001A216
0x18001a1d6  lea     rdx, [rsp+28h+arg_0]
0x18001a1db  lea     rcx, aUpdatepolicyUp; "UpdatePolicy-UpdateManagementGroup"
0x18001a1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1e7  mov     edi, eax
0x18001a1e9  test    eax, eax
0x18001a1eb  jns     short loc_18001A20A
0x18001a1ed  mov     rcx, [rsp+28h]; this
0x18001a1f2  mov     r9d, eax; char *
0x18001a1f5  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18001a1fc  mov     edx, 0BFh; void *
0x18001a201  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a206  mov     ebx, edi
0x18001a208  jmp     short loc_18001A216
0x18001a20a  cmp     [rsp+28h+arg_0], 0
0x18001a20f  setz    al
0x18001a212  mov     [rbx], al
0x18001a214  xor     ebx, ebx
0x18001a216  lea     rcx, [rsp+28h+arg_8]
0x18001a21b  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18001a220  mov     eax, ebx
0x18001a222  mov     rbx, [rsp+28h+arg_10]
0x18001a227  add     rsp, 20h
0x18001a22b  pop     rdi
0x18001a22c  retn
```
