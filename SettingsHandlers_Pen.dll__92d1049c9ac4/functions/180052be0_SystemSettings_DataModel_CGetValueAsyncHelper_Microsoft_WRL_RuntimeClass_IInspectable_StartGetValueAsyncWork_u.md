# SystemSettings::DataModel::CGetValueAsyncHelper<Microsoft::WRL::RuntimeClass<IInspectable>>::StartGetValueAsyncWork(ushort const *,SystemSettings::DataModel::CSettingBase *)

- ea: `0x180052be0`
- end: `0x180052dbc`
- name: `?StartGetValueAsyncWork@?$CGetValueAsyncHelper@V?$RuntimeClass@UIInspectable@@@WRL@Microsoft@@@DataModel@SystemSettings@@UEAAXPEBGPEAVCSettingBase@23@@Z`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003110`
- `0x180005af0`
- `0x180006240`
- `0x180011488`
- `0x1800349e8`
- `0x18003558c`
- `0x180051534`
- `0x180052be0`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180052d50`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180052d50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180052d08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180052d08`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180052d1d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180052d1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052cf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052cf1`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180052cca`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180052cca`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180052d6d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180052d6d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SystemSettings::DataModel::CGetValueAsyncHelper<Microsoft::WRL::RuntimeClass<IInspectable>>::StartGetValueAsyncWork(
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
  result = _InterlockedExchange(a1 + 8, 1);
  if ( !result )
  {
    LOBYTE(a2) = 1;
    (*(void (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a3 + 168LL))(a3, a2);
    v7 = (char *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    v17 = v7;
    if ( !v7 )
      return SystemSettings::DataModel::CGetValueAsyncHelper<Microsoft::WRL::RuntimeClass<IInspectable>>::DoAsyncWorkInternal(
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
      (LPCWSTR)SystemSettings::DataModel::CGetValueAsyncHelper<Microsoft::WRL::RuntimeClass<IInspectable>>::s_GetValueAsyncThread,
      &phModule);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(&v14);
    result = QueueUserWorkItem(
               SystemSettings::DataModel::CGetValueAsyncHelper<Microsoft::WRL::RuntimeClass<IInspectable>>::s_GetValueAsyncThread,
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
        SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>>::ASYNC_PARAMS::`scalar deleting destructor'(v8);
        return SystemSettings::DataModel::CGetValueAsyncHelper<Microsoft::WRL::RuntimeClass<IInspectable>>::DoAsyncWorkInternal(
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
0x180052be0  mov     [rsp+arg_8], rbx
0x180052be5  mov     [rsp+arg_10], rbp
0x180052bea  push    rsi
0x180052beb  push    rdi
0x180052bec  push    r12
0x180052bee  push    r14
0x180052bf0  push    r15
0x180052bf2  sub     rsp, 40h
0x180052bf6  mov     r15, r8
0x180052bf9  mov     r14, rdx
0x180052bfc  mov     rdi, rcx
0x180052bff  mov     eax, 1
0x180052c04  xchg    eax, [rcx+20h]
0x180052c07  test    eax, eax
0x180052c09  jnz     loc_180052DA3
0x180052c0f  mov     rax, [r8]
0x180052c12  mov     dl, 1
0x180052c14  mov     rcx, r8
0x180052c17  mov     rax, [rax+0A8h]
0x180052c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c23  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180052c2a  mov     ecx, 30h ; '0'; unsigned __int64
0x180052c2f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180052c34  mov     rbx, rax
0x180052c37  mov     [rsp+68h+arg_0], rax
0x180052c3c  test    rax, rax
0x180052c3f  jz      loc_180052D95
0x180052c45  mov     qword ptr [rax], 0
0x180052c4c  mov     qword ptr [rax+8], 0
0x180052c54  mov     qword ptr [rax+10h], 0
0x180052c5c  mov     qword ptr [rax+18h], 0
0x180052c64  mov     qword ptr [rax+28h], 0
0x180052c6c  test    rax, rax
0x180052c6f  jz      loc_180052D95
0x180052c75  xor     r12d, r12d
0x180052c78  lea     rcx, [rax+8]
0x180052c7c  mov     rdx, r15
0x180052c7f  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x180052c84  cmp     [rbx], rdi
0x180052c87  jz      short loc_180052CB6
0x180052c89  test    rdi, rdi
0x180052c8c  jz      short loc_180052C9E
0x180052c8e  mov     rax, [rdi]
0x180052c91  mov     rcx, rdi
0x180052c94  mov     rax, [rax+8]
0x180052c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c9d  nop
0x180052c9e  mov     rcx, [rbx]
0x180052ca1  mov     [rbx], rdi
0x180052ca4  test    rcx, rcx
0x180052ca7  jz      short loc_180052CB6
0x180052ca9  mov     rax, [rcx]
0x180052cac  mov     rax, [rax+10h]
0x180052cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052cb5  nop
0x180052cb6  mov     qword ptr [rbx+20h], 0
0x180052cbe  test    r14, r14
0x180052cc1  jz      short loc_180052CD3
0x180052cc3  lea     rdx, [rbx+10h]; ppwsz
0x180052cc7  mov     rcx, r14; psz
0x180052cca  call    cs:__imp_SHStrDupW
0x180052cd0  mov     r12d, eax
0x180052cd3  lea     rsi, [rbx+18h]
0x180052cd7  mov     rbp, [rsi]
0x180052cda  lea     rdx, [rbp-1]
0x180052cde  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180052ce2  ja      short loc_180052D01
0x180052ce4  lea     rcx, [rsp+68h+arg_0]; this
0x180052ce9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180052cee  mov     rcx, rbp; hObject
0x180052cf1  call    cs:__imp_CloseHandle
0x180052cf7  lea     rcx, [rsp+68h+arg_0]; this
0x180052cfc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180052d01  mov     qword ptr [rsi], 0
0x180052d08  call    cs:__imp_GetCurrentThread
0x180052d0e  mov     r9, rsi; TokenHandle
0x180052d11  mov     edx, 0Ch; DesiredAccess
0x180052d16  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180052d1a  mov     rcx, rax; ThreadHandle
0x180052d1d  call    cs:__imp_OpenThreadToken
0x180052d23  test    r12d, r12d
0x180052d26  js      short loc_180052D8D
0x180052d28  lea     rax, [rbx+28h]
0x180052d2c  mov     [rsp+68h+var_48], rax
0x180052d31  mov     [rsp+68h+phModule], 0
0x180052d3a  mov     [rsp+68h+var_38], 1
0x180052d3f  lea     r8, [rsp+68h+phModule]; phModule
0x180052d44  lea     rdx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@V?$RuntimeClass@UIInspectable@@@WRL@Microsoft@@@DataModel@SystemSettings@@CAKPEAX@Z; lpModuleName
0x180052d4b  mov     ecx, 4; dwFlags
0x180052d50  call    cs:__imp_GetModuleHandleExW
0x180052d56  lea     rcx, [rsp+68h+var_48]
0x180052d5b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(void)
0x180052d60  xor     r8d, r8d; Flags
0x180052d63  mov     rdx, rbx; Context
0x180052d66  lea     rcx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@V?$RuntimeClass@UIInspectable@@@WRL@Microsoft@@@DataModel@SystemSettings@@CAKPEAX@Z; Function
0x180052d6d  call    cs:__imp_QueueUserWorkItem
0x180052d73  test    eax, eax
0x180052d75  jnz     short loc_180052DA3
0x180052d77  call    cs:__imp_GetLastError
0x180052d7d  test    eax, eax
0x180052d7f  jle     short loc_180052D8B
0x180052d81  movzx   eax, ax
0x180052d84  or      eax, 80070000h
0x180052d89  test    eax, eax
0x180052d8b  jns     short loc_180052DA3
0x180052d8d  mov     rcx, rbx; Block
0x180052d90  call    ??_GASYNC_PARAMS@?$CGetValueAsyncHelper@V?$CGenericAsyncHelper@VCBoolSetting_False@DataModel@SystemSettings@@@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x180052d95  mov     r8, r14
0x180052d98  mov     rdx, r15
0x180052d9b  mov     rcx, rdi
0x180052d9e  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@V?$RuntimeClass@UIInspectable@@@WRL@Microsoft@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<Microsoft::WRL::RuntimeClass<IInspectable>>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x180052da3  lea     r11, [rsp+68h+var_28]
0x180052da8  mov     rbx, [r11+38h]
0x180052dac  mov     rbp, [r11+40h]
0x180052db0  mov     rsp, r11
0x180052db3  pop     r15
0x180052db5  pop     r14
0x180052db7  pop     r12
0x180052db9  pop     rdi
0x180052dba  pop     rsi
0x180052dbb  retn
```
