# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::StartGetValueAsyncWork(ushort const *,SystemSettings::DataModel::CSettingBase *)

- ea: `0x180029400`
- end: `0x1800295df`
- name: `?StartGetValueAsyncWork@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEBGPEAVCSettingBase@23@@Z`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000a000`
- `0x18000b198`
- `0x18000b85c`
- `0x18001a34c`
- `0x18001aee0`
- `0x18001b6c0`
- `0x18001d5d4`
- `0x180029400`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180029573`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180029573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002959a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002959a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002952b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002952b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180029540`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180029540`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029514`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029514`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180029590`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180029590`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800294ed`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800294ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::StartGetValueAsyncWork(
        volatile __int32 *a1,
        const WCHAR *a2,
        __int64 a3)
{
  const WCHAR *v4; // r14
  int result; // eax
  __int64 *v7; // rax
  __int64 *v8; // rbx
  HRESULT v9; // r12d
  volatile __int32 *v10; // rcx
  char *v11; // rbp
  HANDLE CurrentThread; // rax
  bool v13; // sf
  char *v14; // [rsp+20h] [rbp-48h] BYREF
  HMODULE phModule; // [rsp+28h] [rbp-40h] BYREF
  char v16; // [rsp+30h] [rbp-38h]
  __int64 *v17; // [rsp+70h] [rbp+8h] BYREF

  v4 = a2;
  result = _InterlockedExchange(a1 + 56, 1);
  if ( !result )
  {
    LOBYTE(a2) = 1;
    (*(void (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a3 + 168LL))(a3, a2);
    v7 = (__int64 *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
    v8 = v7;
    v17 = v7;
    if ( !v7 )
      return SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::DoAsyncWorkInternal(
               a1,
               a3,
               v4);
    *v7 = 0;
    v7[1] = 0;
    v7[2] = 0;
    v7[3] = 0;
    v7[5] = 0;
    v9 = 0;
    Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(v7 + 1, a3);
    if ( (volatile __int32 *)*v8 != a1 )
    {
      if ( a1 )
        (*(void (__fastcall **)(volatile __int32 *))(*(_QWORD *)a1 + 8LL))(a1);
      v10 = (volatile __int32 *)*v8;
      *v8 = (__int64)a1;
      if ( v10 )
        (*(void (__fastcall **)(volatile __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
    }
    v8[4] = 0;
    if ( v4 )
      v9 = SHStrDupW(v4, (LPWSTR *)v8 + 2);
    v11 = (char *)v8[3];
    if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v17);
      CloseHandle(v11);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v17);
    }
    v8[3] = 0;
    CurrentThread = GetCurrentThread();
    OpenThreadToken(CurrentThread, 0xCu, 1, (PHANDLE)v8 + 3);
    if ( v9 < 0 )
      goto LABEL_17;
    v14 = (char *)(v8 + 5);
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
        SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::ASYNC_PARAMS::`scalar deleting destructor'(v8);
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
0x180029400  mov     [rsp+arg_8], rbx
0x180029405  mov     [rsp+arg_10], rbp
0x18002940a  push    rsi
0x18002940b  push    rdi
0x18002940c  push    r12
0x18002940e  push    r14
0x180029410  push    r15
0x180029412  sub     rsp, 40h
0x180029416  mov     r15, r8
0x180029419  mov     r14, rdx
0x18002941c  mov     rdi, rcx
0x18002941f  mov     eax, 1
0x180029424  xchg    eax, [rcx+0E0h]
0x18002942a  test    eax, eax
0x18002942c  jnz     loc_1800295C6
0x180029432  mov     rax, [r8]
0x180029435  mov     dl, 1
0x180029437  mov     rcx, r8
0x18002943a  mov     rax, [rax+0A8h]
0x180029441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029446  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002944d  mov     ecx, 30h ; '0'; unsigned __int64
0x180029452  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180029457  mov     rbx, rax
0x18002945a  mov     [rsp+68h+arg_0], rax
0x18002945f  test    rax, rax
0x180029462  jz      loc_1800295B8
0x180029468  mov     qword ptr [rax], 0
0x18002946f  mov     qword ptr [rax+8], 0
0x180029477  mov     qword ptr [rax+10h], 0
0x18002947f  mov     qword ptr [rax+18h], 0
0x180029487  mov     qword ptr [rax+28h], 0
0x18002948f  test    rax, rax
0x180029492  jz      loc_1800295B8
0x180029498  xor     r12d, r12d
0x18002949b  lea     rcx, [rax+8]
0x18002949f  mov     rdx, r15
0x1800294a2  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x1800294a7  cmp     [rbx], rdi
0x1800294aa  jz      short loc_1800294D9
0x1800294ac  test    rdi, rdi
0x1800294af  jz      short loc_1800294C1
0x1800294b1  mov     rax, [rdi]
0x1800294b4  mov     rcx, rdi
0x1800294b7  mov     rax, [rax+8]
0x1800294bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294c0  nop
0x1800294c1  mov     rcx, [rbx]
0x1800294c4  mov     [rbx], rdi
0x1800294c7  test    rcx, rcx
0x1800294ca  jz      short loc_1800294D9
0x1800294cc  mov     rax, [rcx]
0x1800294cf  mov     rax, [rax+10h]
0x1800294d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294d8  nop
0x1800294d9  mov     qword ptr [rbx+20h], 0
0x1800294e1  test    r14, r14
0x1800294e4  jz      short loc_1800294F6
0x1800294e6  lea     rdx, [rbx+10h]; ppwsz
0x1800294ea  mov     rcx, r14; psz
0x1800294ed  call    cs:__imp_SHStrDupW
0x1800294f3  mov     r12d, eax
0x1800294f6  lea     rsi, [rbx+18h]
0x1800294fa  mov     rbp, [rsi]
0x1800294fd  lea     rdx, [rbp-1]
0x180029501  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180029505  ja      short loc_180029524
0x180029507  lea     rcx, [rsp+68h+arg_0]; this
0x18002950c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180029511  mov     rcx, rbp; hObject
0x180029514  call    cs:__imp_CloseHandle
0x18002951a  lea     rcx, [rsp+68h+arg_0]; this
0x18002951f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180029524  mov     qword ptr [rsi], 0
0x18002952b  call    cs:__imp_GetCurrentThread
0x180029531  mov     r9, rsi; TokenHandle
0x180029534  mov     edx, 0Ch; DesiredAccess
0x180029539  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18002953d  mov     rcx, rax; ThreadHandle
0x180029540  call    cs:__imp_OpenThreadToken
0x180029546  test    r12d, r12d
0x180029549  js      short loc_1800295B0
0x18002954b  lea     rax, [rbx+28h]
0x18002954f  mov     [rsp+68h+var_48], rax
0x180029554  mov     [rsp+68h+phModule], 0
0x18002955d  mov     [rsp+68h+var_38], 1
0x180029562  lea     r8, [rsp+68h+phModule]; phModule
0x180029567  lea     rdx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpModuleName
0x18002956e  mov     ecx, 4; dwFlags
0x180029573  call    cs:__imp_GetModuleHandleExW
0x180029579  lea     rcx, [rsp+68h+var_48]
0x18002957e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(void)
0x180029583  xor     r8d, r8d; Flags
0x180029586  mov     rdx, rbx; Context
0x180029589  lea     rcx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; Function
0x180029590  call    cs:__imp_QueueUserWorkItem
0x180029596  test    eax, eax
0x180029598  jnz     short loc_1800295C6
0x18002959a  call    cs:__imp_GetLastError
0x1800295a0  test    eax, eax
0x1800295a2  jle     short loc_1800295AE
0x1800295a4  movzx   eax, ax
0x1800295a7  or      eax, 80070000h
0x1800295ac  test    eax, eax
0x1800295ae  jns     short loc_1800295C6
0x1800295b0  mov     rcx, rbx; void *
0x1800295b3  call    ??_GASYNC_PARAMS@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x1800295b8  mov     r8, r14
0x1800295bb  mov     rdx, r15
0x1800295be  mov     rcx, rdi
0x1800295c1  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x1800295c6  lea     r11, [rsp+68h+var_28]
0x1800295cb  mov     rbx, [r11+38h]
0x1800295cf  mov     rbp, [r11+40h]
0x1800295d3  mov     rsp, r11
0x1800295d6  pop     r15
0x1800295d8  pop     r14
0x1800295da  pop     r12
0x1800295dc  pop     rdi
0x1800295dd  pop     rsi
0x1800295de  retn
```
