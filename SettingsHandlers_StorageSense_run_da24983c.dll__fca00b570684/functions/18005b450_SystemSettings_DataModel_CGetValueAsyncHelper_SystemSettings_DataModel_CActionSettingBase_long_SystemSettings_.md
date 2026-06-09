# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>>::StartGetValueAsyncWork(ushort const *,SystemSettings::DataModel::CSettingBase *)

- ea: `0x18005b450`
- end: `0x18005b5f4`
- name: `?StartGetValueAsyncWork@?$CGetValueAsyncHelper@V?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEBGPEAVCSettingBase@23@@Z`
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
- `0x180051aac`
- `0x18005b450`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005b594`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005b594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b5bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b5bb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005b561`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005b561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005b54c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005b54c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18005b5b1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18005b5b1`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18005b537`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18005b537`

## pseudocode

```c
int __fastcall SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>>::StartGetValueAsyncWork(
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
  result = _InterlockedExchange(a1 + 54, 1);
  if ( !result )
  {
    LOBYTE(a2) = 1;
    (*(void (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a3 + 168LL))(a3, a2);
    v7 = (char *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( !v7 )
      return SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CActionSetting>::DoAsyncWorkInternal(
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
      (LPCWSTR)SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>>::s_GetValueAsyncThread,
      &phModule);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(&v14);
    result = QueueUserWorkItem(
               SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>>::s_GetValueAsyncThread,
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
        return SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CActionSetting>::DoAsyncWorkInternal(
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
0x18005b450  push    rbx
0x18005b452  push    rbp
0x18005b453  push    rsi
0x18005b454  push    rdi
0x18005b455  push    r14
0x18005b457  push    r15
0x18005b459  sub     rsp, 48h
0x18005b45d  mov     r14, r8
0x18005b460  mov     rbp, rdx
0x18005b463  mov     rsi, rcx
0x18005b466  mov     eax, 1
0x18005b46b  xchg    eax, [rcx+0D8h]
0x18005b471  test    eax, eax
0x18005b473  jnz     loc_18005B5E7
0x18005b479  mov     rax, [r8]
0x18005b47c  mov     dl, 1
0x18005b47e  mov     rcx, r8
0x18005b481  mov     rax, [rax+0A8h]
0x18005b488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b48d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005b494  mov     ecx, 30h ; '0'; unsigned __int64
0x18005b499  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005b49e  mov     rdi, rax
0x18005b4a1  mov     [rsp+78h+arg_0], rax
0x18005b4a9  test    rax, rax
0x18005b4ac  jz      loc_18005B5D9
0x18005b4b2  mov     qword ptr [rax], 0
0x18005b4b9  mov     qword ptr [rax+8], 0
0x18005b4c1  mov     qword ptr [rax+10h], 0
0x18005b4c9  mov     qword ptr [rax+18h], 0
0x18005b4d1  mov     qword ptr [rax+28h], 0
0x18005b4d9  test    rax, rax
0x18005b4dc  jz      loc_18005B5D9
0x18005b4e2  xor     r15d, r15d
0x18005b4e5  lea     rcx, [rax+8]
0x18005b4e9  mov     rdx, r14
0x18005b4ec  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x18005b4f1  cmp     [rdi], rsi
0x18005b4f4  jz      short loc_18005B523
0x18005b4f6  test    rsi, rsi
0x18005b4f9  jz      short loc_18005B50B
0x18005b4fb  mov     rax, [rsi]
0x18005b4fe  mov     rcx, rsi
0x18005b501  mov     rax, [rax+8]
0x18005b505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b50a  nop
0x18005b50b  mov     rcx, [rdi]
0x18005b50e  mov     [rdi], rsi
0x18005b511  test    rcx, rcx
0x18005b514  jz      short loc_18005B523
0x18005b516  mov     rax, [rcx]
0x18005b519  mov     rax, [rax+10h]
0x18005b51d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b522  nop
0x18005b523  mov     qword ptr [rdi+20h], 0
0x18005b52b  test    rbp, rbp
0x18005b52e  jz      short loc_18005B540
0x18005b530  lea     rdx, [rdi+10h]; ppwsz
0x18005b534  mov     rcx, rbp; psz
0x18005b537  call    cs:__imp_SHStrDupW
0x18005b53d  mov     r15d, eax
0x18005b540  lea     rcx, [rdi+18h]
0x18005b544  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18005b549  mov     rbx, rax
0x18005b54c  call    cs:__imp_GetCurrentThread
0x18005b552  mov     r9, rbx; TokenHandle
0x18005b555  mov     edx, 0Ch; DesiredAccess
0x18005b55a  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18005b55e  mov     rcx, rax; ThreadHandle
0x18005b561  call    cs:__imp_OpenThreadToken
0x18005b567  test    r15d, r15d
0x18005b56a  js      short loc_18005B5D1
0x18005b56c  lea     rax, [rdi+28h]
0x18005b570  mov     [rsp+78h+var_58], rax
0x18005b575  mov     [rsp+78h+phModule], 0
0x18005b57e  mov     [rsp+78h+var_48], 1
0x18005b583  lea     r8, [rsp+78h+phModule]; phModule
0x18005b588  lea     rdx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@V?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpModuleName
0x18005b58f  mov     ecx, 4; dwFlags
0x18005b594  call    cs:__imp_GetModuleHandleExW
0x18005b59a  lea     rcx, [rsp+78h+var_58]
0x18005b59f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(void)
0x18005b5a4  xor     r8d, r8d; Flags
0x18005b5a7  mov     rdx, rdi; Context
0x18005b5aa  lea     rcx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@V?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; Function
0x18005b5b1  call    cs:__imp_QueueUserWorkItem
0x18005b5b7  test    eax, eax
0x18005b5b9  jnz     short loc_18005B5E7
0x18005b5bb  call    cs:__imp_GetLastError
0x18005b5c1  test    eax, eax
0x18005b5c3  jle     short loc_18005B5CF
0x18005b5c5  movzx   eax, ax
0x18005b5c8  or      eax, 80070000h
0x18005b5cd  test    eax, eax
0x18005b5cf  jns     short loc_18005B5E7
0x18005b5d1  mov     rcx, rdi; void *
0x18005b5d4  call    ??_GASYNC_PARAMS@?$CGetValueAsyncHelper@V?$CCollectionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x18005b5d9  mov     r8, rbp
0x18005b5dc  mov     rdx, r14
0x18005b5df  mov     rcx, rsi
0x18005b5e2  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@VCActionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CActionSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x18005b5e7  add     rsp, 48h
0x18005b5eb  pop     r15
0x18005b5ed  pop     r14
0x18005b5ef  pop     rdi
0x18005b5f0  pop     rsi
0x18005b5f1  pop     rbp
0x18005b5f2  pop     rbx
0x18005b5f3  retn
```
