# GetFindMyDeviceEnabled

- ea: `0x180095728`
- end: `0x180095839`
- name: `GetFindMyDeviceEnabled`
- size: `273`
- prototype: `bool()`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003aa00`
- `0x1800d8bc0`

## callees

- `0x18001bb40`
- `0x18001be08`
- `0x180095728`
- `0x1800a98c0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180095760`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180095760`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180095818`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180095818`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095781`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095781`

## string_xrefs

- `0x180095759`: `mdmcommon.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool GetFindMyDeviceEnabled()
{
  HMODULE Library; // rax
  HMODULE v1; // rbx
  FARPROC ProcAddress; // rax
  int v3; // eax
  bool v4; // di
  char *v6; // [rsp+28h] [rbp-30h]
  int v7; // [rsp+30h] [rbp-28h]
  int v8; // [rsp+38h] [rbp-20h] BYREF
  int v9; // [rsp+3Ch] [rbp-1Ch] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = 0;
  v9 = 0;
  Library = LoadLibraryExW(L"mdmcommon.dll", 0, 0x800u);
  v1 = Library;
  v7 = (int)Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "MdmIsFindMyDeviceEnabled");
    if ( ProcAddress )
    {
      v3 = ((__int64 (__fastcall *)(int *, int *))ProcAddress)(&v8, &v9);
      if ( v3 < 0 )
      {
        LODWORD(v6) = v3;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x5F,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationsignalmanager.cpp",
          "GetFindMyDeviceEnabled",
          "pfnMdmIsFindMyDeviceEnabled(&enabled, &overriddenByPolicyUnused)",
          v6,
          v7);
        v8 = 0;
      }
    }
    else
    {
      LODWORD(v6) = -2147467261;
      wil::details::in1diag5::Log_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationsignalmanager.cpp",
        "GetFindMyDeviceEnabled",
        "E_POINTER",
        v6,
        v7);
    }
  }
  v4 = v8 != 0;
  if ( v1 )
    FreeLibrary(v1);
  return v4;
}

```

## disassembly

```asm
0x180095728  mov     [rsp+arg_0], rbx
0x18009572d  push    rdi
0x18009572e  sub     rsp, 50h
0x180095732  mov     rax, cs:__security_cookie
0x180095739  xor     rax, rsp
0x18009573c  mov     [rsp+58h+var_18], rax
0x180095741  mov     [rsp+58h+var_20], 0
0x180095749  mov     [rsp+58h+var_1C], 0
0x180095751  xor     edx, edx; hFile
0x180095753  mov     r8d, 800h; dwFlags
0x180095759  lea     rcx, aMdmcommonDll; "mdmcommon.dll"
0x180095760  call    cs:__imp_LoadLibraryExW
0x180095766  mov     rbx, rax
0x180095769  mov     qword ptr [rsp+58h+var_28], rax; int
0x18009576e  test    rax, rax
0x180095771  jz      loc_180095807
0x180095777  lea     rdx, aMdmisfindmydev; "MdmIsFindMyDeviceEnabled"
0x18009577e  mov     rcx, rax; hModule
0x180095781  call    cs:__imp_GetProcAddress
0x180095787  test    rax, rax
0x18009578a  jz      short loc_1800957D6
0x18009578c  lea     rdx, [rsp+58h+var_1C]
0x180095791  lea     rcx, [rsp+58h+var_20]
0x180095796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009579b  mov     rcx, [rsp+58h]; this
0x1800957a0  test    eax, eax
0x1800957a2  jns     short loc_180095807
0x1800957a4  mov     dword ptr [rsp+58h+var_30], eax; char *
0x1800957a8  lea     rax, aPfnmdmisfindmy; "pfnMdmIsFindMyDeviceEnabled(&enabled, &"...
0x1800957af  mov     [rsp+58h+var_38], rax; char *
0x1800957b4  lea     r9, aGetfindmydevic; "GetFindMyDeviceEnabled"
0x1800957bb  lea     r8, aOnecoreuapDriv_1; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800957c2  mov     edx, 5Fh ; '_'; void *
0x1800957c7  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800957cc  mov     [rsp+58h+var_20], 0
0x1800957d4  jmp     short loc_180095807
0x1800957d6  mov     rcx, [rsp+58h]; this
0x1800957db  mov     dword ptr [rsp+58h+var_30], 80004003h; char *
0x1800957e3  lea     rax, aEPointer; "E_POINTER"
0x1800957ea  mov     [rsp+58h+var_38], rax; char *
0x1800957ef  lea     r9, aGetfindmydevic; "GetFindMyDeviceEnabled"
0x1800957f6  lea     r8, aOnecoreuapDriv_1; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800957fd  mov     edx, 66h ; 'f'; void *
0x180095802  call    ?Log_Hr@in1diag5@details@wil@@YAJPEAXIPEBD11J@Z; wil::details::in1diag5::Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180095807  cmp     [rsp+58h+var_20], 0
0x18009580c  setnz   dil
0x180095810  test    rbx, rbx
0x180095813  jz      short loc_18009581E
0x180095815  mov     rcx, rbx; hLibModule
0x180095818  call    cs:__imp_FreeLibrary
0x18009581e  mov     al, dil
0x180095821  mov     rcx, [rsp+58h+var_18]
0x180095826  xor     rcx, rsp; StackCookie
0x180095829  call    __security_check_cookie
0x18009582e  mov     rbx, [rsp+58h+arg_0]
0x180095833  add     rsp, 50h
0x180095837  pop     rdi
0x180095838  retn
```
