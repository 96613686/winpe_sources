# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CListSetting>::StartGetValueAsyncWork(ushort const *,SystemSettings::DataModel::CSettingBase *)

- ea: `0x18001e180`
- end: `0x18001e349`
- name: `?StartGetValueAsyncWork@?$CGetValueAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEBGPEAVCSettingBase@23@@Z`
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
- `0x180013a34`
- `0x18001e180`
- `0x180021d6c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001e2d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001e2d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e309`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e29d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e29d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e281`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e281`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18001e2f9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18001e2f9`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18001e267`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18001e267`

## pseudocode

```c
int __fastcall SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CListSetting>::StartGetValueAsyncWork(
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
  result = _InterlockedExchange(a1 + 52, 1);
  if ( !result )
  {
    LOBYTE(a2) = 1;
    (*(void (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a3 + 168LL))(a3, a2);
    v7 = (char *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
    v8 = v7;
    if ( !v7 )
      return SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CListSetting>::DoAsyncWorkInternal(
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
      (LPCWSTR)SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CListSetting>::s_GetValueAsyncThread,
      &phModule);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(&v13);
    result = QueueUserWorkItem(
               SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CListSetting>::s_GetValueAsyncThread,
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
        return SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CListSetting>::DoAsyncWorkInternal(
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
0x18001e180  push    rbx
0x18001e182  push    rbp
0x18001e183  push    rsi
0x18001e184  push    rdi
0x18001e185  push    r14
0x18001e187  push    r15
0x18001e189  sub     rsp, 48h
0x18001e18d  mov     r14, r8
0x18001e190  mov     rbp, rdx
0x18001e193  mov     rsi, rcx
0x18001e196  mov     eax, 1
0x18001e19b  xchg    eax, [rcx+0D0h]
0x18001e1a1  test    eax, eax
0x18001e1a3  jnz     loc_18001E33B
0x18001e1a9  mov     rax, [r8]
0x18001e1ac  mov     dl, 1
0x18001e1ae  mov     rcx, r8
0x18001e1b1  mov     rax, [rax+0A8h]
0x18001e1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e1c4  mov     ecx, 30h ; '0'; unsigned __int64
0x18001e1c9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e1ce  mov     rdi, rax
0x18001e1d1  mov     [rsp+78h+arg_0], rax
0x18001e1d9  test    rax, rax
0x18001e1dc  jz      loc_18001E32D
0x18001e1e2  mov     qword ptr [rax], 0
0x18001e1e9  mov     qword ptr [rax+8], 0
0x18001e1f1  mov     qword ptr [rax+10h], 0
0x18001e1f9  mov     qword ptr [rax+18h], 0
0x18001e201  mov     qword ptr [rax+28h], 0
0x18001e209  test    rax, rax
0x18001e20c  jz      loc_18001E32D
0x18001e212  xor     r15d, r15d
0x18001e215  lea     rcx, [rax+8]
0x18001e219  mov     rdx, r14
0x18001e21c  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x18001e221  cmp     [rdi], rsi
0x18001e224  jz      short loc_18001E253
0x18001e226  test    rsi, rsi
0x18001e229  jz      short loc_18001E23B
0x18001e22b  mov     rax, [rsi]
0x18001e22e  mov     rcx, rsi
0x18001e231  mov     rax, [rax+8]
0x18001e235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e23a  nop
0x18001e23b  mov     rcx, [rdi]
0x18001e23e  mov     [rdi], rsi
0x18001e241  test    rcx, rcx
0x18001e244  jz      short loc_18001E253
0x18001e246  mov     rax, [rcx]
0x18001e249  mov     rax, [rax+10h]
0x18001e24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e252  nop
0x18001e253  mov     qword ptr [rdi+20h], 0
0x18001e25b  test    rbp, rbp
0x18001e25e  jz      short loc_18001E276
0x18001e260  lea     rdx, [rdi+10h]; ppwsz
0x18001e264  mov     rcx, rbp; psz
0x18001e267  call    cs:__imp_SHStrDupW
0x18001e26e  nop     dword ptr [rax+rax+00h]
0x18001e273  mov     r15d, eax
0x18001e276  xor     edx, edx
0x18001e278  lea     rcx, [rdi+18h]
0x18001e27c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001e281  call    cs:__imp_GetCurrentThread
0x18001e288  nop     dword ptr [rax+rax+00h]
0x18001e28d  lea     r9, [rdi+18h]; TokenHandle
0x18001e291  mov     edx, 0Ch; DesiredAccess
0x18001e296  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18001e29a  mov     rcx, rax; ThreadHandle
0x18001e29d  call    cs:__imp_OpenThreadToken
0x18001e2a4  nop     dword ptr [rax+rax+00h]
0x18001e2a9  test    r15d, r15d
0x18001e2ac  js      short loc_18001E325
0x18001e2ae  lea     rax, [rdi+28h]
0x18001e2b2  mov     [rsp+78h+var_58], rax
0x18001e2b7  mov     [rsp+78h+phModule], 0
0x18001e2c0  mov     [rsp+78h+var_48], 1
0x18001e2c5  lea     r8, [rsp+78h+phModule]; phModule
0x18001e2ca  lea     rdx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpModuleName
0x18001e2d1  mov     ecx, 4; dwFlags
0x18001e2d6  call    cs:__imp_GetModuleHandleExW
0x18001e2dd  nop     dword ptr [rax+rax+00h]
0x18001e2e2  lea     rcx, [rsp+78h+var_58]
0x18001e2e7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(void)
0x18001e2ec  xor     r8d, r8d; Flags
0x18001e2ef  mov     rdx, rdi; Context
0x18001e2f2  lea     rcx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; Function
0x18001e2f9  call    cs:__imp_QueueUserWorkItem
0x18001e300  nop     dword ptr [rax+rax+00h]
0x18001e305  test    eax, eax
0x18001e307  jnz     short loc_18001E33B
0x18001e309  call    cs:__imp_GetLastError
0x18001e310  nop     dword ptr [rax+rax+00h]
0x18001e315  test    eax, eax
0x18001e317  jle     short loc_18001E323
0x18001e319  movzx   eax, ax
0x18001e31c  or      eax, 80070000h
0x18001e321  test    eax, eax
0x18001e323  jns     short loc_18001E33B
0x18001e325  mov     rcx, rdi
0x18001e328  call    ??_GASYNC_PARAMS@?$CGetValueAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CListSetting>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x18001e32d  mov     r8, rbp
0x18001e330  mov     rdx, r14
0x18001e333  mov     rcx, rsi
0x18001e336  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CListSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x18001e33b  add     rsp, 48h
0x18001e33f  pop     r15
0x18001e341  pop     r14
0x18001e343  pop     rdi
0x18001e344  pop     rsi
0x18001e345  pop     rbp
0x18001e346  pop     rbx
0x18001e347  retn
```
