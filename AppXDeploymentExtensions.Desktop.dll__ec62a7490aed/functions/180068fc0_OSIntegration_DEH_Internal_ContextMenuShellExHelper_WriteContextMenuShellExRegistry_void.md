# OSIntegration::DEH::Internal::ContextMenuShellExHelper::WriteContextMenuShellExRegistry(void)

- ea: `0x180068fc0`
- end: `0x180069275`
- name: `?WriteContextMenuShellExRegistry@ContextMenuShellExHelper@Internal@DEH@OSIntegration@@QEAAJXZ`
- size: `693`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::ContextMenuShellExHelper *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008ccc0`
- `0x180117fd0`

## callees

- `0x18001adb4`
- `0x18003193c`
- `0x180033ca0`
- `0x180068fc0`
- `0x180069eb4`
- `0x1800af1bc`
- `0x1801189c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180069052`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180069052`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800690ac`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180069169`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800690ac`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180069169`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006910c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006910c`

## string_xrefs

- `0x18006915e`: `CoCreateCLSIDOOP`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSIntegration::DEH::Internal::ContextMenuShellExHelper::WriteContextMenuShellExRegistry(
        OSIntegration::DEH::Internal::ContextMenuShellExHelper *this)
{
  unsigned int v2; // ebx
  unsigned __int64 i; // rbx
  _QWORD *v5; // rcx
  int v6; // eax
  unsigned int v7; // esi
  HKEY *v8; // rax
  unsigned int v9; // eax
  HKEY *phkResult; // rax
  unsigned int Key; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rax
  DWORD v14; // edx
  __int64 v15; // rax
  HKEY *v16; // rax
  unsigned int v17; // eax
  const struct std::nothrow_t *v18; // rdx
  __int64 v19; // rdx
  const struct std::nothrow_t *v20; // rdx
  const struct std::nothrow_t *v21; // rdx
  unsigned int dwOptions; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-50h]
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-20h] BYREF
  int v25; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  HKEY v27; // [rsp+90h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+28h] BYREF
  __int64 v29; // [rsp+A0h] [rbp+30h] BYREF

  if ( *((_QWORD *)this + 4) )
  {
    for ( i = 0; ; ++i )
    {
      v5 = (_QWORD *)*((_QWORD *)this + 4);
      if ( i >= v5[2] )
        return 0;
      *(_OWORD *)lpSubKey = 0;
      v25 = 0;
      v6 = OSIntegration::DEH::Internal::ConstructContextMenuShellExRegkey(
             *(_QWORD *)(*v5 + 8 * i),
             *(unsigned int *)this,
             (char *)this + 8,
             lpSubKey);
      v7 = v6;
      if ( v6 < 0 )
        break;
      hKey = 0;
      v8 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
      v9 = RegOpenCurrentUser(0xF003Fu, v8);
      if ( v9 )
      {
        v2 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xB1,
               (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\contextmenushellexhandler\\contextmenushellexhelper.cpp",
               (const char *)v9,
               dwOptions);
        goto LABEL_26;
      }
      v27 = 0;
      phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v27);
      Key = RegCreateKeyExW(hKey, lpSubKey[1], 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
      if ( Key )
      {
        v19 = 181;
LABEL_23:
        v2 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v19,
               (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\contextmenushellexhandler\\contextmenushellexhelper.cpp",
               (const char *)Key,
               dwOptionsa);
LABEL_24:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
LABEL_26:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        if ( lpSubKey[1] )
          operator delete((void *)lpSubKey[1], v20);
        return v2;
      }
      v12 = (_QWORD *)*((_QWORD *)this + 4);
      if ( i < v12[2] )
        v13 = *(_QWORD *)(*v12 + 8 * i);
      else
        v13 = 0;
      v14 = 2 * *(_DWORD *)(v13 + 24) + 2;
      if ( i < v12[2] )
        v15 = *(_QWORD *)(*v12 + 8 * i);
      else
        v15 = 0;
      Key = RegSetKeyValueW(v27, 0, 0, 1u, *(LPCVOID *)(v15 + 32), v14);
      if ( Key )
      {
        v19 = 190;
        goto LABEL_23;
      }
      v29 = 0;
      v16 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v29);
      v17 = RegCreateKeyExW(v27, L"CoCreateCLSIDOOP", 0, 0, 0, 0xF003Fu, 0, v16, 0);
      if ( v17 )
      {
        v2 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xC4,
               (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\contextmenushellexhandler\\contextmenushellexhelper.cpp",
               (const char *)v17,
               dwOptions);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v29);
        goto LABEL_24;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v29);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( lpSubKey[1] )
        operator delete((void *)lpSubKey[1], v18);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\contextmenushellexhandler\\contextmenushellexhelper.cpp",
      (const char *)(unsigned int)v6,
      dwOptions);
    if ( lpSubKey[1] )
      operator delete((void *)lpSubKey[1], v21);
    return v7;
  }
  else
  {
    v2 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\contextmenushellexhandler\\contextmenushellexhelper.cpp",
      (const char *)0x8000FFFFLL,
      dwOptions);
    return v2;
  }
}

```

## disassembly

```asm
0x180068fc0  mov     [rsp-18h+arg_18], rbx
0x180068fc5  push    rbp
0x180068fc6  push    rsi
0x180068fc7  push    rdi
0x180068fc8  mov     rbp, rsp
0x180068fcb  sub     rsp, 70h
0x180068fcf  mov     rdi, rcx
0x180068fd2  cmp     qword ptr [rcx+20h], 0
0x180068fd7  jnz     short loc_180068FFD
0x180068fd9  mov     rcx, [rbp+18h]; this
0x180068fdd  mov     ebx, 8000FFFFh
0x180068fe2  mov     r9d, ebx; char *
0x180068fe5  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180068fec  mov     edx, 0A4h; void *
0x180068ff1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068ff6  mov     eax, ebx
0x180068ff8  jmp     loc_180069264
0x180068ffd  xor     ebx, ebx
0x180068fff  mov     rcx, [rdi+20h]
0x180069003  cmp     rbx, [rcx+10h]
0x180069007  jnb     loc_180069262
0x18006900d  xor     eax, eax
0x18006900f  xorps   xmm0, xmm0
0x180069012  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x180069016  mov     [rbp+var_10], eax
0x180069019  lea     r8, [rdi+8]
0x18006901d  mov     rcx, [rcx]
0x180069020  lea     r9, [rbp+lpSubKey]
0x180069024  mov     edx, [rdi]
0x180069026  mov     rcx, [rcx+rbx*8]
0x18006902a  call    ?ConstructContextMenuShellExRegkey@Internal@DEH@OSIntegration@@YAJPEAUCOMMON_STRING@Common@@W4ContextMenuShellExCategory@123@0PEAVStringBuffer@5@@Z; OSIntegration::DEH::Internal::ConstructContextMenuShellExRegkey(Common::COMMON_STRING *,OSIntegration::DEH::Internal::ContextMenuShellExCategory,Common::COMMON_STRING *,Common::StringBuffer *)
0x18006902f  mov     esi, eax
0x180069031  test    eax, eax
0x180069033  js      loc_180069237
0x180069039  mov     [rbp+hKey], 0
0x180069041  lea     rcx, [rbp+hKey]
0x180069045  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18006904a  mov     rdx, rax; phkResult
0x18006904d  mov     ecx, 0F003Fh; samDesired
0x180069052  call    cs:__imp_RegOpenCurrentUser
0x180069059  nop     dword ptr [rax+rax+00h]
0x18006905e  test    eax, eax
0x180069060  jnz     loc_1800691FC
0x180069066  mov     [rbp+arg_0], 0
0x18006906e  lea     rcx, [rbp+arg_0]
0x180069072  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180069077  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x180069080  mov     [rsp+70h+phkResult], rax; phkResult
0x180069085  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006908e  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x180069096  mov     [rsp+70h+dwOptions], 0; unsigned int
0x18006909e  xor     r9d, r9d; lpClass
0x1800690a1  xor     r8d, r8d; Reserved
0x1800690a4  mov     rdx, [rbp+lpSubKey+8]; lpSubKey
0x1800690a8  mov     rcx, [rbp+hKey]; hKey
0x1800690ac  call    cs:__imp_RegCreateKeyExW
0x1800690b3  nop     dword ptr [rax+rax+00h]
0x1800690b8  test    eax, eax
0x1800690ba  jnz     loc_1800691D7
0x1800690c0  mov     rcx, [rdi+20h]
0x1800690c4  cmp     rbx, [rcx+10h]
0x1800690c8  jb      short loc_1800690CE
0x1800690ca  xor     eax, eax
0x1800690cc  jmp     short loc_1800690D5
0x1800690ce  mov     rax, [rcx]
0x1800690d1  mov     rax, [rax+rbx*8]
0x1800690d5  mov     eax, [rax+18h]
0x1800690d8  lea     edx, ds:2[rax*2]
0x1800690df  cmp     rbx, [rcx+10h]
0x1800690e3  jb      short loc_1800690E9
0x1800690e5  xor     eax, eax
0x1800690e7  jmp     short loc_1800690F0
0x1800690e9  mov     rax, [rcx]
0x1800690ec  mov     rax, [rax+rbx*8]
0x1800690f0  mov     [rsp+70h+samDesired], edx; cbData
0x1800690f4  mov     rax, [rax+20h]
0x1800690f8  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x1800690fd  mov     r9d, 1; dwType
0x180069103  xor     r8d, r8d; lpValueName
0x180069106  xor     edx, edx; lpSubKey
0x180069108  mov     rcx, [rbp+arg_0]; hKey
0x18006910c  call    cs:__imp_RegSetKeyValueW
0x180069113  nop     dword ptr [rax+rax+00h]
0x180069118  test    eax, eax
0x18006911a  jnz     loc_1800691D0
0x180069120  mov     [rbp+arg_10], 0
0x180069128  lea     rcx, [rbp+arg_10]
0x18006912c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180069131  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x18006913a  mov     [rsp+70h+phkResult], rax; phkResult
0x18006913f  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180069148  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x180069150  mov     [rsp+70h+dwOptions], 0; unsigned int
0x180069158  xor     r9d, r9d; lpClass
0x18006915b  xor     r8d, r8d; Reserved
0x18006915e  lea     rdx, aCocreateclsido; "CoCreateCLSIDOOP"
0x180069165  mov     rcx, [rbp+arg_0]; hKey
0x180069169  call    cs:__imp_RegCreateKeyExW
0x180069170  nop     dword ptr [rax+rax+00h]
0x180069175  test    eax, eax
0x180069177  jnz     short loc_1800691AB
0x180069179  lea     rcx, [rbp+arg_10]
0x18006917d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180069182  lea     rcx, [rbp+arg_0]
0x180069186  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006918b  lea     rcx, [rbp+hKey]
0x18006918f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180069194  nop
0x180069195  mov     rcx, [rbp+lpSubKey+8]; void *
0x180069199  test    rcx, rcx
0x18006919c  jz      short loc_1800691A3
0x18006919e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800691a3  inc     rbx
0x1800691a6  jmp     loc_180068FFF
0x1800691ab  mov     rcx, [rbp+18h]; this
0x1800691af  mov     r9d, eax; char *
0x1800691b2  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800691b9  mov     edx, 0C4h; void *
0x1800691be  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800691c3  mov     ebx, eax
0x1800691c5  lea     rcx, [rbp+arg_10]
0x1800691c9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800691ce  jmp     short loc_1800691F1
0x1800691d0  mov     edx, 0BEh
0x1800691d5  jmp     short loc_1800691DC
0x1800691d7  mov     edx, 0B5h; void *
0x1800691dc  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800691e3  mov     r9d, eax; char *
0x1800691e6  mov     rcx, [rbp+18h]; this
0x1800691ea  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800691ef  mov     ebx, eax
0x1800691f1  lea     rcx, [rbp+arg_0]
0x1800691f5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800691fa  jmp     short loc_180069216
0x1800691fc  mov     rcx, [rbp+18h]; this
0x180069200  mov     r9d, eax; char *
0x180069203  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006920a  mov     edx, 0B1h; void *
0x18006920f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180069214  mov     ebx, eax
0x180069216  lea     rcx, [rbp+hKey]
0x18006921a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006921f  nop
0x180069220  mov     rcx, [rbp+lpSubKey+8]; void *
0x180069224  test    rcx, rcx
0x180069227  jz      loc_180068FF6
0x18006922d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180069232  jmp     loc_180068FF6
0x180069237  mov     rcx, [rbp+18h]; this
0x18006923b  mov     r9d, esi; char *
0x18006923e  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180069245  mov     edx, 0ADh; void *
0x18006924a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006924f  nop
0x180069250  mov     rcx, [rbp+lpSubKey+8]; void *
0x180069254  test    rcx, rcx
0x180069257  jz      short loc_18006925E
0x180069259  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006925e  mov     eax, esi
0x180069260  jmp     short loc_180069264
0x180069262  xor     eax, eax
0x180069264  mov     rbx, [rsp+70h+arg_18]
0x18006926c  add     rsp, 70h
0x180069270  pop     rdi
0x180069271  pop     rsi
0x180069272  pop     rbp
0x180069273  retn
```
