# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::StartGetValueAsyncWork(ushort const *,SystemSettings::DataModel::CSettingBase *)

- ea: `0x18001df90`
- end: `0x18001e159`
- name: `?StartGetValueAsyncWork@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEBGPEAVCSettingBase@23@@Z`
- size: `457`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800034b8`
- `0x1800107f8`
- `0x180011350`
- `0x180011b34`
- `0x1800139d4`
- `0x18001df90`
- `0x180021d6c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001e0e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001e0e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e119`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e0ad`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e0ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e091`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e091`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18001e109`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18001e109`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18001e077`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18001e077`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::StartGetValueAsyncWork(
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
  HANDLE CurrentThread; // rax
  bool v12; // sf
  char *v13; // [rsp+20h] [rbp-58h] BYREF
  HMODULE phModule; // [rsp+28h] [rbp-50h] BYREF
  char v15; // [rsp+30h] [rbp-48h]

  v4 = a2;
  result = _InterlockedExchange(a1 + 56, 1);
  if ( !result )
  {
    LOBYTE(a2) = 1;
    (*(void (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a3 + 168LL))(a3, a2);
    v7 = (char *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
    v8 = v7;
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
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v8 + 24,
      0);
    CurrentThread = GetCurrentThread();
    OpenThreadToken(CurrentThread, 0xCu, 1, (PHANDLE)v8 + 3);
    if ( v9 < 0 )
      goto LABEL_15;
    v13 = v8 + 40;
    phModule = 0;
    v15 = 1;
    GetModuleHandleExW(
      4u,
      (LPCWSTR)SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::s_GetValueAsyncThread,
      &phModule);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(&v13);
    result = QueueUserWorkItem(
               SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::s_GetValueAsyncThread,
               v8,
               0);
    if ( !result )
    {
      result = GetLastError();
      v12 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v12 = result < 0;
      }
      if ( v12 )
      {
LABEL_15:
        SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CListSetting>::ASYNC_PARAMS::`scalar deleting destructor'(v8);
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
0x18001df90  push    rbx
0x18001df92  push    rbp
0x18001df93  push    rsi
0x18001df94  push    rdi
0x18001df95  push    r14
0x18001df97  push    r15
0x18001df99  sub     rsp, 48h
0x18001df9d  mov     r14, r8
0x18001dfa0  mov     rbp, rdx
0x18001dfa3  mov     rsi, rcx
0x18001dfa6  mov     eax, 1
0x18001dfab  xchg    eax, [rcx+0E0h]
0x18001dfb1  test    eax, eax
0x18001dfb3  jnz     loc_18001E14B
0x18001dfb9  mov     rax, [r8]
0x18001dfbc  mov     dl, 1
0x18001dfbe  mov     rcx, r8
0x18001dfc1  mov     rax, [rax+0A8h]
0x18001dfc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfcd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001dfd4  mov     ecx, 30h ; '0'; unsigned __int64
0x18001dfd9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001dfde  mov     rdi, rax
0x18001dfe1  mov     [rsp+78h+arg_0], rax
0x18001dfe9  test    rax, rax
0x18001dfec  jz      loc_18001E13D
0x18001dff2  mov     qword ptr [rax], 0
0x18001dff9  mov     qword ptr [rax+8], 0
0x18001e001  mov     qword ptr [rax+10h], 0
0x18001e009  mov     qword ptr [rax+18h], 0
0x18001e011  mov     qword ptr [rax+28h], 0
0x18001e019  test    rax, rax
0x18001e01c  jz      loc_18001E13D
0x18001e022  xor     r15d, r15d
0x18001e025  lea     rcx, [rax+8]
0x18001e029  mov     rdx, r14
0x18001e02c  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x18001e031  cmp     [rdi], rsi
0x18001e034  jz      short loc_18001E063
0x18001e036  test    rsi, rsi
0x18001e039  jz      short loc_18001E04B
0x18001e03b  mov     rax, [rsi]
0x18001e03e  mov     rcx, rsi
0x18001e041  mov     rax, [rax+8]
0x18001e045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e04a  nop
0x18001e04b  mov     rcx, [rdi]
0x18001e04e  mov     [rdi], rsi
0x18001e051  test    rcx, rcx
0x18001e054  jz      short loc_18001E063
0x18001e056  mov     rax, [rcx]
0x18001e059  mov     rax, [rax+10h]
0x18001e05d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e062  nop
0x18001e063  mov     qword ptr [rdi+20h], 0
0x18001e06b  test    rbp, rbp
0x18001e06e  jz      short loc_18001E086
0x18001e070  lea     rdx, [rdi+10h]; ppwsz
0x18001e074  mov     rcx, rbp; psz
0x18001e077  call    cs:__imp_SHStrDupW
0x18001e07e  nop     dword ptr [rax+rax+00h]
0x18001e083  mov     r15d, eax
0x18001e086  xor     edx, edx
0x18001e088  lea     rcx, [rdi+18h]
0x18001e08c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001e091  call    cs:__imp_GetCurrentThread
0x18001e098  nop     dword ptr [rax+rax+00h]
0x18001e09d  lea     r9, [rdi+18h]; TokenHandle
0x18001e0a1  mov     edx, 0Ch; DesiredAccess
0x18001e0a6  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18001e0aa  mov     rcx, rax; ThreadHandle
0x18001e0ad  call    cs:__imp_OpenThreadToken
0x18001e0b4  nop     dword ptr [rax+rax+00h]
0x18001e0b9  test    r15d, r15d
0x18001e0bc  js      short loc_18001E135
0x18001e0be  lea     rax, [rdi+28h]
0x18001e0c2  mov     [rsp+78h+var_58], rax
0x18001e0c7  mov     [rsp+78h+phModule], 0
0x18001e0d0  mov     [rsp+78h+var_48], 1
0x18001e0d5  lea     r8, [rsp+78h+phModule]; phModule
0x18001e0da  lea     rdx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpModuleName
0x18001e0e1  mov     ecx, 4; dwFlags
0x18001e0e6  call    cs:__imp_GetModuleHandleExW
0x18001e0ed  nop     dword ptr [rax+rax+00h]
0x18001e0f2  lea     rcx, [rsp+78h+var_58]
0x18001e0f7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(void)
0x18001e0fc  xor     r8d, r8d; Flags
0x18001e0ff  mov     rdx, rdi; Context
0x18001e102  lea     rcx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; Function
0x18001e109  call    cs:__imp_QueueUserWorkItem
0x18001e110  nop     dword ptr [rax+rax+00h]
0x18001e115  test    eax, eax
0x18001e117  jnz     short loc_18001E14B
0x18001e119  call    cs:__imp_GetLastError
0x18001e120  nop     dword ptr [rax+rax+00h]
0x18001e125  test    eax, eax
0x18001e127  jle     short loc_18001E133
0x18001e129  movzx   eax, ax
0x18001e12c  or      eax, 80070000h
0x18001e131  test    eax, eax
0x18001e133  jns     short loc_18001E14B
0x18001e135  mov     rcx, rdi
0x18001e138  call    ??_GASYNC_PARAMS@?$CGetValueAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CListSetting>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x18001e13d  mov     r8, rbp
0x18001e140  mov     rdx, r14
0x18001e143  mov     rcx, rsi
0x18001e146  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x18001e14b  add     rsp, 48h
0x18001e14f  pop     r15
0x18001e151  pop     r14
0x18001e153  pop     rdi
0x18001e154  pop     rsi
0x18001e155  pop     rbp
0x18001e156  pop     rbx
0x18001e157  retn
```
