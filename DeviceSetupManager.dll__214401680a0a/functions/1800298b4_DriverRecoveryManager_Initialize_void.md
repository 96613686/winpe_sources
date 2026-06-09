# DriverRecoveryManager::Initialize(void)

- ea: `0x1800298b4`
- end: `0x180029999`
- name: `?Initialize@DriverRecoveryManager@@QEAAJXZ`
- size: `229`
- prototype: `__int64 __fastcall(DriverRecoveryManager *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180024374`

## callees

- `0x18000e1d8`
- `0x18000fbf8`
- `0x1800112a4`
- `0x1800112c8`
- `0x180029438`
- `0x1800298b4`
- `0x18004088c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800298fe`
- `OLEAUT32!__imp_SysAllocString` at `0x180029956`
- `OLEAUT32!__imp_SysAllocString` at `0x1800298fe`
- `OLEAUT32!__imp_SysAllocString` at `0x180029956`

## string_xrefs

- `0x1800298e1`: `onecoreuap\base\devices\setup\dsm\service\driverrecovery.cpp`
- `0x180029937`: `onecoreuap\base\devices\setup\dsm\service\driverrecovery.cpp`

## pseudocode

```c
__int64 __fastcall DriverRecoveryManager::Initialize(DriverRecoveryManager *this)
{
  const char *v2; // r9
  __int64 v4; // rdx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  BSTR v7; // [rsp+38h] [rbp+10h] BYREF

  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180059110);
  DrvRecoverySpUtilsInitialized = pSetupInitializeUtils();
  if ( !DrvRecoverySpUtilsInitialized )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xB9,
             (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\driverrecovery.cpp",
             v2);
  v7 = SysAllocString(L"\\Microsoft\\Windows\\Device Setup");
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    (char *)this + 184,
    &v7);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v7);
  if ( !*((_QWORD *)this + 23) )
  {
    v4 = 188;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\driverrecovery.cpp",
      (const char *)0x8007000ELL,
      v5);
    return 2147942414LL;
  }
  v7 = SysAllocString(L"Driver Recovery on Reboot");
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    (char *)this + 192,
    &v7);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v7);
  if ( !*((_QWORD *)this + 24) )
  {
    v4 = 191;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x1800298b4  mov     [rsp+arg_0], rbx
0x1800298b9  push    rdi; int
0x1800298ba  sub     rsp, 20h
0x1800298be  mov     rdi, rcx
0x1800298c1  lea     rcx, dword_180059110; CallbackContext
0x1800298c8  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800298cd  call    pSetupInitializeUtils
0x1800298d2  mov     cs:?DrvRecoverySpUtilsInitialized@@3HA, eax; int DrvRecoverySpUtilsInitialized
0x1800298d8  test    eax, eax
0x1800298da  jnz     short loc_1800298F7
0x1800298dc  mov     rcx, [rsp+28h]; this
0x1800298e1  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x1800298e8  mov     edx, 0B9h; void *
0x1800298ed  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800298f2  jmp     loc_18002998E
0x1800298f7  lea     rcx, psz; "\\Microsoft\\Windows\\Device Setup"
0x1800298fe  call    cs:__imp_SysAllocString
0x180029904  mov     [rsp+28h+arg_8], rax
0x180029909  lea     rbx, [rdi+0B8h]
0x180029910  lea     rdx, [rsp+28h+arg_8]
0x180029915  mov     rcx, rbx
0x180029918  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002991d  lea     rcx, [rsp+28h+arg_8]
0x180029922  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029927  cmp     qword ptr [rbx], 0
0x18002992b  jnz     short loc_18002994F
0x18002992d  mov     edx, 0BCh; void *
0x180029932  mov     ebx, 8007000Eh
0x180029937  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18002993e  mov     r9d, ebx; char *
0x180029941  mov     rcx, [rsp+28h]; this
0x180029946  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002994b  mov     eax, ebx
0x18002994d  jmp     short loc_18002998E
0x18002994f  lea     rcx, aDriverRecovery; "Driver Recovery on Reboot"
0x180029956  call    cs:__imp_SysAllocString
0x18002995c  mov     [rsp+28h+arg_8], rax
0x180029961  lea     rbx, [rdi+0C0h]
0x180029968  lea     rdx, [rsp+28h+arg_8]
0x18002996d  mov     rcx, rbx
0x180029970  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180029975  lea     rcx, [rsp+28h+arg_8]
0x18002997a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002997f  cmp     qword ptr [rbx], 0
0x180029983  jnz     short loc_18002998C
0x180029985  mov     edx, 0BFh
0x18002998a  jmp     short loc_180029932
0x18002998c  xor     eax, eax
0x18002998e  mov     rbx, [rsp+28h+arg_0]
0x180029993  add     rsp, 20h
0x180029997  pop     rdi
0x180029998  retn
```
