# EnterpriseFeatureControl::ReadSkuUpdateManagementGroup(bool *)

- ea: `0x180068288`
- end: `0x180068371`
- name: `?ReadSkuUpdateManagementGroup@EnterpriseFeatureControl@@CAJPEA_N@Z`
- size: `233`
- prototype: `static int(bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180066bf4`

## callees

- `0x1800077c8`
- `0x18003169c`
- `0x18006031c`
- `0x180068288`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800682d4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800682d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800682f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800682f5`

## string_xrefs

- `0x1800682cd`: `ext-ms-win-security-slc-l1-1-0`
- `0x18006831f`: `UpdatePolicy-UpdateManagementGroup`

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
0x180068288  mov     [rsp+arg_10], rbx
0x18006828d  push    rdi; int
0x18006828e  sub     rsp, 20h
0x180068292  mov     rbx, rcx
0x180068295  mov     [rsp+28h+arg_0], 0
0x18006829d  test    rcx, rcx
0x1800682a0  jnz     short loc_1800682C5
0x1800682a2  mov     rcx, [rsp+28h]; this
0x1800682a7  mov     ebx, 80004003h
0x1800682ac  mov     r9d, ebx; char *
0x1800682af  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800682b6  mov     edx, 0B7h; void *
0x1800682bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800682c0  jmp     loc_180068364
0x1800682c5  xor     edx, edx; hFile
0x1800682c7  mov     r8d, 800h; dwFlags
0x1800682cd  lea     rcx, aExtMsWinSecuri; "ext-ms-win-security-slc-l1-1-0"
0x1800682d4  call    cs:__imp_LoadLibraryExW
0x1800682da  mov     [rsp+28h+arg_8], rax
0x1800682df  test    rax, rax
0x1800682e2  jnz     short loc_1800682EB
0x1800682e4  mov     edx, 0BAh
0x1800682e9  jmp     short loc_180068305
0x1800682eb  lea     rdx, aSlgetwindowsin; "SLGetWindowsInformationDWORD"
0x1800682f2  mov     rcx, rax; hModule
0x1800682f5  call    cs:__imp_GetProcAddress
0x1800682fb  test    rax, rax
0x1800682fe  jnz     short loc_18006831A
0x180068300  mov     edx, 0BEh; void *
0x180068305  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18006830c  mov     rcx, [rsp+28h]; this
0x180068311  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180068316  mov     ebx, eax
0x180068318  jmp     short loc_18006835A
0x18006831a  lea     rdx, [rsp+28h+arg_0]
0x18006831f  lea     rcx, aUpdatepolicyUp; "UpdatePolicy-UpdateManagementGroup"
0x180068326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006832b  mov     edi, eax
0x18006832d  test    eax, eax
0x18006832f  jns     short loc_18006834E
0x180068331  mov     rcx, [rsp+28h]; this
0x180068336  mov     r9d, eax; char *
0x180068339  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180068340  mov     edx, 0BFh; void *
0x180068345  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006834a  mov     ebx, edi
0x18006834c  jmp     short loc_18006835A
0x18006834e  cmp     [rsp+28h+arg_0], 0
0x180068353  setz    al
0x180068356  mov     [rbx], al
0x180068358  xor     ebx, ebx
0x18006835a  lea     rcx, [rsp+28h+arg_8]
0x18006835f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180068364  mov     eax, ebx
0x180068366  mov     rbx, [rsp+28h+arg_10]
0x18006836b  add     rsp, 20h
0x18006836f  pop     rdi
0x180068370  retn
```
