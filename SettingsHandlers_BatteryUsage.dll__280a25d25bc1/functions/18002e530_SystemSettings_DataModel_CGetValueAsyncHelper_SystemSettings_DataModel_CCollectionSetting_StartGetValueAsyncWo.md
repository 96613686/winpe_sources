# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::StartGetValueAsyncWork(ushort const *,SystemSettings::DataModel::CSettingBase *)

- ea: `0x18002e530`
- end: `0x18002e70f`
- name: `?StartGetValueAsyncWork@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEBGPEAVCSettingBase@23@@Z`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800042d8`
- `0x180005d28`
- `0x1800063a4`
- `0x18000e0f4`
- `0x180015b30`
- `0x18001665c`
- `0x18002c560`
- `0x18002e530`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002e670`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002e670`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e65b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e65b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002e6a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002e6a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e6ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e6ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e644`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e644`
- `SHCORE!SHStrDupW` at `0x18002e61d`
- `SHCORE!SHStrDupW` at `0x18002e61d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18002e6c0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18002e6c0`

## pseudocode

```c
int __fastcall SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::StartGetValueAsyncWork(
        volatile __int32 *a1,
        const WCHAR *a2,
        __int64 a3)
{
  const WCHAR *v4; // r14
  int result; // eax
  char *v7; // rax
  char *v8; // rbx
  HRESULT v9; // r12d
  volatile __int32 *v10; // rcx
  char *v11; // rbp
  HANDLE CurrentThread; // rax
  bool v13; // sf
  char *v14; // [rsp+20h] [rbp-48h] BYREF
  HMODULE phModule; // [rsp+28h] [rbp-40h] BYREF
  char v16; // [rsp+30h] [rbp-38h]
  char *v17; // [rsp+70h] [rbp+8h] BYREF

  v4 = a2;
  result = _InterlockedExchange(a1 + 56, 1);
  if ( !result )
  {
    LOBYTE(a2) = 1;
    (*(void (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a3 + 168LL))(a3, a2);
    v7 = (char *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
    v8 = v7;
    v17 = v7;
    if ( !v7 )
      return SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::DoAsyncWorkInternal(
               a1,
               a3,
               v4);
    *(_QWORD *)v7 = 0;
    *((_QWORD *)v7 + 1) = 0;
    *((_QWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 5) = 0;
    v9 = 0;
    Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(v7 + 8, a3);
    if ( *(volatile __int32 **)v8 != a1 )
    {
      if ( a1 )
        (*(void (__fastcall **)(volatile __int32 *))(*(_QWORD *)a1 + 8LL))(a1);
      v10 = *(volatile __int32 **)v8;
      *(_QWORD *)v8 = a1;
      if ( v10 )
        (*(void (__fastcall **)(volatile __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
    }
    *((_QWORD *)v8 + 4) = 0;
    if ( v4 )
      v9 = SHStrDupW(v4, (LPWSTR *)v8 + 2);
    v11 = (char *)*((_QWORD *)v8 + 3);
    if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v17);
      CloseHandle(v11);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v17);
    }
    *((_QWORD *)v8 + 3) = 0;
    CurrentThread = GetCurrentThread();
    OpenThreadToken(CurrentThread, 0xCu, 1, (PHANDLE)v8 + 3);
    if ( v9 < 0 )
      goto LABEL_17;
    v14 = v8 + 40;
    phModule = 0;
    v16 = 1;
    GetModuleHandleExW(
      4u,
      (LPCWSTR)SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::s_GetValueAsyncThread,
      &phModule);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(&v14);
    result = QueueUserWorkItem(
               SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::s_GetValueAsyncThread,
               v8,
               0);
    if ( !result )
    {
      result = GetLastError();
      v13 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v13 = result < 0;
      }
      if ( v13 )
      {
LABEL_17:
        SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CDataSetting>::ASYNC_PARAMS::`scalar deleting destructor'(v8);
        return SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::DoAsyncWorkInternal(
                 a1,
                 a3,
                 v4);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002e530  mov     [rsp+arg_8], rbx
0x18002e535  mov     [rsp+arg_10], rbp
0x18002e53a  push    rsi
0x18002e53b  push    rdi
0x18002e53c  push    r12
0x18002e53e  push    r14
0x18002e540  push    r15
0x18002e542  sub     rsp, 40h
0x18002e546  mov     r15, r8
0x18002e549  mov     r14, rdx
0x18002e54c  mov     rdi, rcx
0x18002e54f  mov     eax, 1
0x18002e554  xchg    eax, [rcx+0E0h]
0x18002e55a  test    eax, eax
0x18002e55c  jnz     loc_18002E6F6
0x18002e562  mov     rax, [r8]
0x18002e565  mov     dl, 1
0x18002e567  mov     rcx, r8
0x18002e56a  mov     rax, [rax+0A8h]
0x18002e571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e576  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e57d  mov     ecx, 30h ; '0'; unsigned __int64
0x18002e582  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002e587  mov     rbx, rax
0x18002e58a  mov     [rsp+68h+arg_0], rax
0x18002e58f  test    rax, rax
0x18002e592  jz      loc_18002E6E8
0x18002e598  mov     qword ptr [rax], 0
0x18002e59f  mov     qword ptr [rax+8], 0
0x18002e5a7  mov     qword ptr [rax+10h], 0
0x18002e5af  mov     qword ptr [rax+18h], 0
0x18002e5b7  mov     qword ptr [rax+28h], 0
0x18002e5bf  test    rax, rax
0x18002e5c2  jz      loc_18002E6E8
0x18002e5c8  xor     r12d, r12d
0x18002e5cb  lea     rcx, [rax+8]
0x18002e5cf  mov     rdx, r15
0x18002e5d2  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x18002e5d7  cmp     [rbx], rdi
0x18002e5da  jz      short loc_18002E609
0x18002e5dc  test    rdi, rdi
0x18002e5df  jz      short loc_18002E5F1
0x18002e5e1  mov     rax, [rdi]
0x18002e5e4  mov     rcx, rdi
0x18002e5e7  mov     rax, [rax+8]
0x18002e5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5f0  nop
0x18002e5f1  mov     rcx, [rbx]
0x18002e5f4  mov     [rbx], rdi
0x18002e5f7  test    rcx, rcx
0x18002e5fa  jz      short loc_18002E609
0x18002e5fc  mov     rax, [rcx]
0x18002e5ff  mov     rax, [rax+10h]
0x18002e603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e608  nop
0x18002e609  mov     qword ptr [rbx+20h], 0
0x18002e611  test    r14, r14
0x18002e614  jz      short loc_18002E626
0x18002e616  lea     rdx, [rbx+10h]; ppwsz
0x18002e61a  mov     rcx, r14; psz
0x18002e61d  call    cs:__imp_SHStrDupW
0x18002e623  mov     r12d, eax
0x18002e626  lea     rsi, [rbx+18h]
0x18002e62a  mov     rbp, [rsi]
0x18002e62d  lea     rdx, [rbp-1]
0x18002e631  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002e635  ja      short loc_18002E654
0x18002e637  lea     rcx, [rsp+68h+arg_0]; this
0x18002e63c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002e641  mov     rcx, rbp; hObject
0x18002e644  call    cs:__imp_CloseHandle
0x18002e64a  lea     rcx, [rsp+68h+arg_0]; this
0x18002e64f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002e654  mov     qword ptr [rsi], 0
0x18002e65b  call    cs:__imp_GetCurrentThread
0x18002e661  mov     r9, rsi; TokenHandle
0x18002e664  mov     edx, 0Ch; DesiredAccess
0x18002e669  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18002e66d  mov     rcx, rax; ThreadHandle
0x18002e670  call    cs:__imp_OpenThreadToken
0x18002e676  test    r12d, r12d
0x18002e679  js      short loc_18002E6E0
0x18002e67b  lea     rax, [rbx+28h]
0x18002e67f  mov     [rsp+68h+var_48], rax
0x18002e684  mov     [rsp+68h+phModule], 0
0x18002e68d  mov     [rsp+68h+var_38], 1
0x18002e692  lea     r8, [rsp+68h+phModule]; phModule
0x18002e697  lea     rdx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpModuleName
0x18002e69e  mov     ecx, 4; dwFlags
0x18002e6a3  call    cs:__imp_GetModuleHandleExW
0x18002e6a9  lea     rcx, [rsp+68h+var_48]
0x18002e6ae  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(void)
0x18002e6b3  xor     r8d, r8d; Flags
0x18002e6b6  mov     rdx, rbx; Context
0x18002e6b9  lea     rcx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; Function
0x18002e6c0  call    cs:__imp_QueueUserWorkItem
0x18002e6c6  test    eax, eax
0x18002e6c8  jnz     short loc_18002E6F6
0x18002e6ca  call    cs:__imp_GetLastError
0x18002e6d0  test    eax, eax
0x18002e6d2  jle     short loc_18002E6DE
0x18002e6d4  movzx   eax, ax
0x18002e6d7  or      eax, 80070000h
0x18002e6dc  test    eax, eax
0x18002e6de  jns     short loc_18002E6F6
0x18002e6e0  mov     rcx, rbx; void *
0x18002e6e3  call    ??_GASYNC_PARAMS@?$CGetValueAsyncHelper@VCDataSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CDataSetting>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x18002e6e8  mov     r8, r14
0x18002e6eb  mov     rdx, r15
0x18002e6ee  mov     rcx, rdi
0x18002e6f1  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x18002e6f6  lea     r11, [rsp+68h+var_28]
0x18002e6fb  mov     rbx, [r11+38h]
0x18002e6ff  mov     rbp, [r11+40h]
0x18002e703  mov     rsp, r11
0x18002e706  pop     r15
0x18002e708  pop     r14
0x18002e70a  pop     r12
0x18002e70c  pop     rdi
0x18002e70d  pop     rsi
0x18002e70e  retn
```
