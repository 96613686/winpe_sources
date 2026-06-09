# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>>::StartGetValueAsyncWork(ushort const *,SystemSettings::DataModel::CSettingBase *)

- ea: `0x18003a630`
- end: `0x18003a80f`
- name: `?StartGetValueAsyncWork@?$CGetValueAsyncHelper@V?$CGenericAsyncHelper@VCBoolSetting_False@DataModel@SystemSettings@@@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEBGPEAVCSettingBase@23@@Z`
- size: `479`
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
- `0x180036980`
- `0x18003a630`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003a7a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003a7a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a7ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a7ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003a75b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003a75b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003a770`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003a770`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a744`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a744`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18003a71d`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18003a71d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18003a7c0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18003a7c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>>::StartGetValueAsyncWork(
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
  result = _InterlockedExchange(a1 + 58, 1);
  if ( !result )
  {
    LOBYTE(a2) = 1;
    (*(void (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a3 + 168LL))(a3, a2);
    v7 = (char *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    v17 = v7;
    if ( !v7 )
      return SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>>::DoAsyncWorkInternal(
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
      (LPCWSTR)SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>>::s_GetValueAsyncThread,
      &phModule);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(&v14);
    result = QueueUserWorkItem(
               SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>>::s_GetValueAsyncThread,
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
        return SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>>::DoAsyncWorkInternal(
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
0x18003a630  mov     [rsp+arg_8], rbx
0x18003a635  mov     [rsp+arg_10], rbp
0x18003a63a  push    rsi
0x18003a63b  push    rdi
0x18003a63c  push    r12
0x18003a63e  push    r14
0x18003a640  push    r15
0x18003a642  sub     rsp, 40h
0x18003a646  mov     r15, r8
0x18003a649  mov     r14, rdx
0x18003a64c  mov     rdi, rcx
0x18003a64f  mov     eax, 1
0x18003a654  xchg    eax, [rcx+0E8h]
0x18003a65a  test    eax, eax
0x18003a65c  jnz     loc_18003A7F6
0x18003a662  mov     rax, [r8]
0x18003a665  mov     dl, 1
0x18003a667  mov     rcx, r8
0x18003a66a  mov     rax, [rax+0A8h]
0x18003a671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a676  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003a67d  mov     ecx, 30h ; '0'; unsigned __int64
0x18003a682  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003a687  mov     rbx, rax
0x18003a68a  mov     [rsp+68h+arg_0], rax
0x18003a68f  test    rax, rax
0x18003a692  jz      loc_18003A7E8
0x18003a698  mov     qword ptr [rax], 0
0x18003a69f  mov     qword ptr [rax+8], 0
0x18003a6a7  mov     qword ptr [rax+10h], 0
0x18003a6af  mov     qword ptr [rax+18h], 0
0x18003a6b7  mov     qword ptr [rax+28h], 0
0x18003a6bf  test    rax, rax
0x18003a6c2  jz      loc_18003A7E8
0x18003a6c8  xor     r12d, r12d
0x18003a6cb  lea     rcx, [rax+8]
0x18003a6cf  mov     rdx, r15
0x18003a6d2  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x18003a6d7  cmp     [rbx], rdi
0x18003a6da  jz      short loc_18003A709
0x18003a6dc  test    rdi, rdi
0x18003a6df  jz      short loc_18003A6F1
0x18003a6e1  mov     rax, [rdi]
0x18003a6e4  mov     rcx, rdi
0x18003a6e7  mov     rax, [rax+8]
0x18003a6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6f0  nop
0x18003a6f1  mov     rcx, [rbx]
0x18003a6f4  mov     [rbx], rdi
0x18003a6f7  test    rcx, rcx
0x18003a6fa  jz      short loc_18003A709
0x18003a6fc  mov     rax, [rcx]
0x18003a6ff  mov     rax, [rax+10h]
0x18003a703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a708  nop
0x18003a709  mov     qword ptr [rbx+20h], 0
0x18003a711  test    r14, r14
0x18003a714  jz      short loc_18003A726
0x18003a716  lea     rdx, [rbx+10h]; ppwsz
0x18003a71a  mov     rcx, r14; psz
0x18003a71d  call    cs:__imp_SHStrDupW
0x18003a723  mov     r12d, eax
0x18003a726  lea     rsi, [rbx+18h]
0x18003a72a  mov     rbp, [rsi]
0x18003a72d  lea     rdx, [rbp-1]
0x18003a731  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003a735  ja      short loc_18003A754
0x18003a737  lea     rcx, [rsp+68h+arg_0]; this
0x18003a73c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003a741  mov     rcx, rbp; hObject
0x18003a744  call    cs:__imp_CloseHandle
0x18003a74a  lea     rcx, [rsp+68h+arg_0]; this
0x18003a74f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003a754  mov     qword ptr [rsi], 0
0x18003a75b  call    cs:__imp_GetCurrentThread
0x18003a761  mov     r9, rsi; TokenHandle
0x18003a764  mov     edx, 0Ch; DesiredAccess
0x18003a769  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18003a76d  mov     rcx, rax; ThreadHandle
0x18003a770  call    cs:__imp_OpenThreadToken
0x18003a776  test    r12d, r12d
0x18003a779  js      short loc_18003A7E0
0x18003a77b  lea     rax, [rbx+28h]
0x18003a77f  mov     [rsp+68h+var_48], rax
0x18003a784  mov     [rsp+68h+phModule], 0
0x18003a78d  mov     [rsp+68h+var_38], 1
0x18003a792  lea     r8, [rsp+68h+phModule]; phModule
0x18003a797  lea     rdx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@V?$CGenericAsyncHelper@VCBoolSetting_False@DataModel@SystemSettings@@@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpModuleName
0x18003a79e  mov     ecx, 4; dwFlags
0x18003a7a3  call    cs:__imp_GetModuleHandleExW
0x18003a7a9  lea     rcx, [rsp+68h+var_48]
0x18003a7ae  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(void)
0x18003a7b3  xor     r8d, r8d; Flags
0x18003a7b6  mov     rdx, rbx; Context
0x18003a7b9  lea     rcx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@V?$CGenericAsyncHelper@VCBoolSetting_False@DataModel@SystemSettings@@@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; Function
0x18003a7c0  call    cs:__imp_QueueUserWorkItem
0x18003a7c6  test    eax, eax
0x18003a7c8  jnz     short loc_18003A7F6
0x18003a7ca  call    cs:__imp_GetLastError
0x18003a7d0  test    eax, eax
0x18003a7d2  jle     short loc_18003A7DE
0x18003a7d4  movzx   eax, ax
0x18003a7d7  or      eax, 80070000h
0x18003a7dc  test    eax, eax
0x18003a7de  jns     short loc_18003A7F6
0x18003a7e0  mov     rcx, rbx; Block
0x18003a7e3  call    ??_GASYNC_PARAMS@?$CGetValueAsyncHelper@V?$CGenericAsyncHelper@VCBoolSetting_False@DataModel@SystemSettings@@@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x18003a7e8  mov     r8, r14
0x18003a7eb  mov     rdx, r15
0x18003a7ee  mov     rcx, rdi
0x18003a7f1  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@V?$CGenericAsyncHelper@VCBoolSetting_False@DataModel@SystemSettings@@@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x18003a7f6  lea     r11, [rsp+68h+var_28]
0x18003a7fb  mov     rbx, [r11+38h]
0x18003a7ff  mov     rbp, [r11+40h]
0x18003a803  mov     rsp, r11
0x18003a806  pop     r15
0x18003a808  pop     r14
0x18003a80a  pop     r12
0x18003a80c  pop     rdi
0x18003a80d  pop     rsi
0x18003a80e  retn
```
