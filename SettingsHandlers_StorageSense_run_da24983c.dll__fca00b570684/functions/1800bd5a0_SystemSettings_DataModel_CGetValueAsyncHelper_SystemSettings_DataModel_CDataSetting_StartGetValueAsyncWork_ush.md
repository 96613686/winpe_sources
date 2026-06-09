# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CDataSetting>::StartGetValueAsyncWork(ushort const *,SystemSettings::DataModel::CSettingBase *)

- ea: `0x1800bd5a0`
- end: `0x1800bd744`
- name: `?StartGetValueAsyncWork@?$CGetValueAsyncHelper@VCDataSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEBGPEAVCSettingBase@23@@Z`
- size: `420`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000733c`
- `0x1800188d4`
- `0x180029210`
- `0x180029e1c`
- `0x180035b90`
- `0x1800bbbdc`
- `0x1800bd5a0`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800bd6e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800bd6e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd70b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd70b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bd6b1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bd6b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bd69c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bd69c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800bd701`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800bd701`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800bd687`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800bd687`

## pseudocode

```c
int __fastcall SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CDataSetting>::StartGetValueAsyncWork(
        volatile __int32 *a1,
        const WCHAR *a2,
        __int64 a3)
{
  const WCHAR *v4; // rbp
  int result; // eax
  char *v7; // rax
  char *v8; // rdi
  HRESULT v9; // r15d
  volatile __int32 *v10; // rcx
  void **v11; // rbx
  HANDLE CurrentThread; // rax
  bool v13; // sf
  char *v14; // [rsp+20h] [rbp-58h] BYREF
  HMODULE phModule; // [rsp+28h] [rbp-50h] BYREF
  char v16; // [rsp+30h] [rbp-48h]

  v4 = a2;
  result = _InterlockedExchange(a1 + 52, 1);
  if ( !result )
  {
    LOBYTE(a2) = 1;
    (*(void (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a3 + 168LL))(a3, a2);
    v7 = (char *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( !v7 )
      return SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CDataSetting>::DoAsyncWorkInternal(
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
    v11 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(v8 + 24);
    CurrentThread = GetCurrentThread();
    OpenThreadToken(CurrentThread, 0xCu, 1, v11);
    if ( v9 < 0 )
      goto LABEL_15;
    v14 = v8 + 40;
    phModule = 0;
    v16 = 1;
    GetModuleHandleExW(
      4u,
      (LPCWSTR)SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CDataSetting>::s_GetValueAsyncThread,
      &phModule);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(&v14);
    result = QueueUserWorkItem(
               SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CDataSetting>::s_GetValueAsyncThread,
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
LABEL_15:
        SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>>::ASYNC_PARAMS::`scalar deleting destructor'(v8);
        return SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CDataSetting>::DoAsyncWorkInternal(
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
0x1800bd5a0  push    rbx
0x1800bd5a2  push    rbp
0x1800bd5a3  push    rsi
0x1800bd5a4  push    rdi
0x1800bd5a5  push    r14
0x1800bd5a7  push    r15
0x1800bd5a9  sub     rsp, 48h
0x1800bd5ad  mov     r14, r8
0x1800bd5b0  mov     rbp, rdx
0x1800bd5b3  mov     rsi, rcx
0x1800bd5b6  mov     eax, 1
0x1800bd5bb  xchg    eax, [rcx+0D0h]
0x1800bd5c1  test    eax, eax
0x1800bd5c3  jnz     loc_1800BD737
0x1800bd5c9  mov     rax, [r8]
0x1800bd5cc  mov     dl, 1
0x1800bd5ce  mov     rcx, r8
0x1800bd5d1  mov     rax, [rax+0A8h]
0x1800bd5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd5dd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bd5e4  mov     ecx, 30h ; '0'; unsigned __int64
0x1800bd5e9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800bd5ee  mov     rdi, rax
0x1800bd5f1  mov     [rsp+78h+arg_0], rax
0x1800bd5f9  test    rax, rax
0x1800bd5fc  jz      loc_1800BD729
0x1800bd602  mov     qword ptr [rax], 0
0x1800bd609  mov     qword ptr [rax+8], 0
0x1800bd611  mov     qword ptr [rax+10h], 0
0x1800bd619  mov     qword ptr [rax+18h], 0
0x1800bd621  mov     qword ptr [rax+28h], 0
0x1800bd629  test    rax, rax
0x1800bd62c  jz      loc_1800BD729
0x1800bd632  xor     r15d, r15d
0x1800bd635  lea     rcx, [rax+8]
0x1800bd639  mov     rdx, r14
0x1800bd63c  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x1800bd641  cmp     [rdi], rsi
0x1800bd644  jz      short loc_1800BD673
0x1800bd646  test    rsi, rsi
0x1800bd649  jz      short loc_1800BD65B
0x1800bd64b  mov     rax, [rsi]
0x1800bd64e  mov     rcx, rsi
0x1800bd651  mov     rax, [rax+8]
0x1800bd655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd65a  nop
0x1800bd65b  mov     rcx, [rdi]
0x1800bd65e  mov     [rdi], rsi
0x1800bd661  test    rcx, rcx
0x1800bd664  jz      short loc_1800BD673
0x1800bd666  mov     rax, [rcx]
0x1800bd669  mov     rax, [rax+10h]
0x1800bd66d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd672  nop
0x1800bd673  mov     qword ptr [rdi+20h], 0
0x1800bd67b  test    rbp, rbp
0x1800bd67e  jz      short loc_1800BD690
0x1800bd680  lea     rdx, [rdi+10h]; ppwsz
0x1800bd684  mov     rcx, rbp; psz
0x1800bd687  call    cs:__imp_SHStrDupW
0x1800bd68d  mov     r15d, eax
0x1800bd690  lea     rcx, [rdi+18h]
0x1800bd694  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1800bd699  mov     rbx, rax
0x1800bd69c  call    cs:__imp_GetCurrentThread
0x1800bd6a2  mov     r9, rbx; TokenHandle
0x1800bd6a5  mov     edx, 0Ch; DesiredAccess
0x1800bd6aa  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x1800bd6ae  mov     rcx, rax; ThreadHandle
0x1800bd6b1  call    cs:__imp_OpenThreadToken
0x1800bd6b7  test    r15d, r15d
0x1800bd6ba  js      short loc_1800BD721
0x1800bd6bc  lea     rax, [rdi+28h]
0x1800bd6c0  mov     [rsp+78h+var_58], rax
0x1800bd6c5  mov     [rsp+78h+phModule], 0
0x1800bd6ce  mov     [rsp+78h+var_48], 1
0x1800bd6d3  lea     r8, [rsp+78h+phModule]; phModule
0x1800bd6d8  lea     rdx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCDataSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpModuleName
0x1800bd6df  mov     ecx, 4; dwFlags
0x1800bd6e4  call    cs:__imp_GetModuleHandleExW
0x1800bd6ea  lea     rcx, [rsp+78h+var_58]
0x1800bd6ef  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(void)
0x1800bd6f4  xor     r8d, r8d; Flags
0x1800bd6f7  mov     rdx, rdi; Context
0x1800bd6fa  lea     rcx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCDataSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; Function
0x1800bd701  call    cs:__imp_QueueUserWorkItem
0x1800bd707  test    eax, eax
0x1800bd709  jnz     short loc_1800BD737
0x1800bd70b  call    cs:__imp_GetLastError
0x1800bd711  test    eax, eax
0x1800bd713  jle     short loc_1800BD71F
0x1800bd715  movzx   eax, ax
0x1800bd718  or      eax, 80070000h
0x1800bd71d  test    eax, eax
0x1800bd71f  jns     short loc_1800BD737
0x1800bd721  mov     rcx, rdi; void *
0x1800bd724  call    ??_GASYNC_PARAMS@?$CGetValueAsyncHelper@V?$CCollectionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x1800bd729  mov     r8, rbp
0x1800bd72c  mov     rdx, r14
0x1800bd72f  mov     rcx, rsi
0x1800bd732  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@VCDataSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CDataSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x1800bd737  add     rsp, 48h
0x1800bd73b  pop     r15
0x1800bd73d  pop     r14
0x1800bd73f  pop     rdi
0x1800bd740  pop     rsi
0x1800bd741  pop     rbp
0x1800bd742  pop     rbx
0x1800bd743  retn
```
