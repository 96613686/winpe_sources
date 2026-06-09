# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::StorageSenseHandlers::MultiSelectionListBase<unsigned __int64>>::StartGetValueAsyncWork(ushort const *,SystemSettings::DataModel::CSettingBase *)

- ea: `0x180067e70`
- end: `0x180068014`
- name: `?StartGetValueAsyncWork@?$CGetValueAsyncHelper@V?$MultiSelectionListBase@_K@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEBGPEAVCSettingBase@23@@Z`
- size: `420`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000733c`
- `0x1800188d4`
- `0x180029210`
- `0x180029e1c`
- `0x180035b90`
- `0x1800636bc`
- `0x180067e70`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180067fb4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180067fb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067fdb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180067f81`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180067f81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180067f6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180067f6c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180067fd1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180067fd1`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180067f57`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180067f57`

## pseudocode

```c
int __fastcall SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::StorageSenseHandlers::MultiSelectionListBase<unsigned __int64>>::StartGetValueAsyncWork(
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
  result = _InterlockedExchange(a1 + 60, 1);
  if ( !result )
  {
    LOBYTE(a2) = 1;
    (*(void (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a3 + 168LL))(a3, a2);
    v7 = (char *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( !v7 )
      return SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::StorageSenseHandlers::MultiSelectionListBase<unsigned __int64>>::DoAsyncWorkInternal(
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
      (LPCWSTR)SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::StorageSenseHandlers::MultiSelectionListBase<std::wstring>>::s_GetValueAsyncThread,
      &phModule);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(&v14);
    result = QueueUserWorkItem(
               SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::StorageSenseHandlers::MultiSelectionListBase<std::wstring>>::s_GetValueAsyncThread,
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
        return SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::StorageSenseHandlers::MultiSelectionListBase<unsigned __int64>>::DoAsyncWorkInternal(
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
0x180067e70  push    rbx
0x180067e72  push    rbp
0x180067e73  push    rsi
0x180067e74  push    rdi
0x180067e75  push    r14
0x180067e77  push    r15
0x180067e79  sub     rsp, 48h
0x180067e7d  mov     r14, r8
0x180067e80  mov     rbp, rdx
0x180067e83  mov     rsi, rcx
0x180067e86  mov     eax, 1
0x180067e8b  xchg    eax, [rcx+0F0h]
0x180067e91  test    eax, eax
0x180067e93  jnz     loc_180068007
0x180067e99  mov     rax, [r8]
0x180067e9c  mov     dl, 1
0x180067e9e  mov     rcx, r8
0x180067ea1  mov     rax, [rax+0A8h]
0x180067ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ead  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180067eb4  mov     ecx, 30h ; '0'; unsigned __int64
0x180067eb9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180067ebe  mov     rdi, rax
0x180067ec1  mov     [rsp+78h+arg_0], rax
0x180067ec9  test    rax, rax
0x180067ecc  jz      loc_180067FF9
0x180067ed2  mov     qword ptr [rax], 0
0x180067ed9  mov     qword ptr [rax+8], 0
0x180067ee1  mov     qword ptr [rax+10h], 0
0x180067ee9  mov     qword ptr [rax+18h], 0
0x180067ef1  mov     qword ptr [rax+28h], 0
0x180067ef9  test    rax, rax
0x180067efc  jz      loc_180067FF9
0x180067f02  xor     r15d, r15d
0x180067f05  lea     rcx, [rax+8]
0x180067f09  mov     rdx, r14
0x180067f0c  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x180067f11  cmp     [rdi], rsi
0x180067f14  jz      short loc_180067F43
0x180067f16  test    rsi, rsi
0x180067f19  jz      short loc_180067F2B
0x180067f1b  mov     rax, [rsi]
0x180067f1e  mov     rcx, rsi
0x180067f21  mov     rax, [rax+8]
0x180067f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f2a  nop
0x180067f2b  mov     rcx, [rdi]
0x180067f2e  mov     [rdi], rsi
0x180067f31  test    rcx, rcx
0x180067f34  jz      short loc_180067F43
0x180067f36  mov     rax, [rcx]
0x180067f39  mov     rax, [rax+10h]
0x180067f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f42  nop
0x180067f43  mov     qword ptr [rdi+20h], 0
0x180067f4b  test    rbp, rbp
0x180067f4e  jz      short loc_180067F60
0x180067f50  lea     rdx, [rdi+10h]; ppwsz
0x180067f54  mov     rcx, rbp; psz
0x180067f57  call    cs:__imp_SHStrDupW
0x180067f5d  mov     r15d, eax
0x180067f60  lea     rcx, [rdi+18h]
0x180067f64  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x180067f69  mov     rbx, rax
0x180067f6c  call    cs:__imp_GetCurrentThread
0x180067f72  mov     r9, rbx; TokenHandle
0x180067f75  mov     edx, 0Ch; DesiredAccess
0x180067f7a  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180067f7e  mov     rcx, rax; ThreadHandle
0x180067f81  call    cs:__imp_OpenThreadToken
0x180067f87  test    r15d, r15d
0x180067f8a  js      short loc_180067FF1
0x180067f8c  lea     rax, [rdi+28h]
0x180067f90  mov     [rsp+78h+var_58], rax
0x180067f95  mov     [rsp+78h+phModule], 0
0x180067f9e  mov     [rsp+78h+var_48], 1
0x180067fa3  lea     r8, [rsp+78h+phModule]; phModule
0x180067fa8  lea     rdx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@V?$MultiSelectionListBase@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpModuleName
0x180067faf  mov     ecx, 4; dwFlags
0x180067fb4  call    cs:__imp_GetModuleHandleExW
0x180067fba  lea     rcx, [rsp+78h+var_58]
0x180067fbf  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(void)
0x180067fc4  xor     r8d, r8d; Flags
0x180067fc7  mov     rdx, rdi; Context
0x180067fca  lea     rcx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@V?$MultiSelectionListBase@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; Function
0x180067fd1  call    cs:__imp_QueueUserWorkItem
0x180067fd7  test    eax, eax
0x180067fd9  jnz     short loc_180068007
0x180067fdb  call    cs:__imp_GetLastError
0x180067fe1  test    eax, eax
0x180067fe3  jle     short loc_180067FEF
0x180067fe5  movzx   eax, ax
0x180067fe8  or      eax, 80070000h
0x180067fed  test    eax, eax
0x180067fef  jns     short loc_180068007
0x180067ff1  mov     rcx, rdi; void *
0x180067ff4  call    ??_GASYNC_PARAMS@?$CGetValueAsyncHelper@V?$CCollectionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x180067ff9  mov     r8, rbp
0x180067ffc  mov     rdx, r14
0x180067fff  mov     rcx, rsi
0x180068002  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@V?$MultiSelectionListBase@_K@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::StorageSenseHandlers::MultiSelectionListBase<unsigned __int64>>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x180068007  add     rsp, 48h
0x18006800b  pop     r15
0x18006800d  pop     r14
0x18006800f  pop     rdi
0x180068010  pop     rsi
0x180068011  pop     rbp
0x180068012  pop     rbx
0x180068013  retn
```
