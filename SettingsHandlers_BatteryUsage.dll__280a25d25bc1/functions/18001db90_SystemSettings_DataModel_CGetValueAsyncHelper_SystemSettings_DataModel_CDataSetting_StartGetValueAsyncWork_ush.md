# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CDataSetting>::StartGetValueAsyncWork(ushort const *,SystemSettings::DataModel::CSettingBase *)

- ea: `0x18001db90`
- end: `0x18001dd6f`
- name: `?StartGetValueAsyncWork@?$CGetValueAsyncHelper@VCDataSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEBGPEAVCSettingBase@23@@Z`
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
- `0x180017cfc`
- `0x18001db90`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001dcd0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001dcd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001dcbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001dcbb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001dd03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001dd03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dca4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dca4`
- `SHCORE!SHStrDupW` at `0x18001dc7d`
- `SHCORE!SHStrDupW` at `0x18001dc7d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18001dd20`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18001dd20`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CDataSetting>::StartGetValueAsyncWork(
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
  result = _InterlockedExchange(a1 + 52, 1);
  if ( !result )
  {
    LOBYTE(a2) = 1;
    (*(void (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a3 + 168LL))(a3, a2);
    v7 = (char *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
    v8 = v7;
    v17 = v7;
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
LABEL_17:
        SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CDataSetting>::ASYNC_PARAMS::`scalar deleting destructor'(v8);
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
0x18001db90  mov     [rsp+arg_8], rbx
0x18001db95  mov     [rsp+arg_10], rbp
0x18001db9a  push    rsi
0x18001db9b  push    rdi
0x18001db9c  push    r12
0x18001db9e  push    r14
0x18001dba0  push    r15
0x18001dba2  sub     rsp, 40h
0x18001dba6  mov     r15, r8
0x18001dba9  mov     r14, rdx
0x18001dbac  mov     rdi, rcx
0x18001dbaf  mov     eax, 1
0x18001dbb4  xchg    eax, [rcx+0D0h]
0x18001dbba  test    eax, eax
0x18001dbbc  jnz     loc_18001DD56
0x18001dbc2  mov     rax, [r8]
0x18001dbc5  mov     dl, 1
0x18001dbc7  mov     rcx, r8
0x18001dbca  mov     rax, [rax+0A8h]
0x18001dbd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbd6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001dbdd  mov     ecx, 30h ; '0'; unsigned __int64
0x18001dbe2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001dbe7  mov     rbx, rax
0x18001dbea  mov     [rsp+68h+arg_0], rax
0x18001dbef  test    rax, rax
0x18001dbf2  jz      loc_18001DD48
0x18001dbf8  mov     qword ptr [rax], 0
0x18001dbff  mov     qword ptr [rax+8], 0
0x18001dc07  mov     qword ptr [rax+10h], 0
0x18001dc0f  mov     qword ptr [rax+18h], 0
0x18001dc17  mov     qword ptr [rax+28h], 0
0x18001dc1f  test    rax, rax
0x18001dc22  jz      loc_18001DD48
0x18001dc28  xor     r12d, r12d
0x18001dc2b  lea     rcx, [rax+8]
0x18001dc2f  mov     rdx, r15
0x18001dc32  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x18001dc37  cmp     [rbx], rdi
0x18001dc3a  jz      short loc_18001DC69
0x18001dc3c  test    rdi, rdi
0x18001dc3f  jz      short loc_18001DC51
0x18001dc41  mov     rax, [rdi]
0x18001dc44  mov     rcx, rdi
0x18001dc47  mov     rax, [rax+8]
0x18001dc4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc50  nop
0x18001dc51  mov     rcx, [rbx]
0x18001dc54  mov     [rbx], rdi
0x18001dc57  test    rcx, rcx
0x18001dc5a  jz      short loc_18001DC69
0x18001dc5c  mov     rax, [rcx]
0x18001dc5f  mov     rax, [rax+10h]
0x18001dc63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc68  nop
0x18001dc69  mov     qword ptr [rbx+20h], 0
0x18001dc71  test    r14, r14
0x18001dc74  jz      short loc_18001DC86
0x18001dc76  lea     rdx, [rbx+10h]; ppwsz
0x18001dc7a  mov     rcx, r14; psz
0x18001dc7d  call    cs:__imp_SHStrDupW
0x18001dc83  mov     r12d, eax
0x18001dc86  lea     rsi, [rbx+18h]
0x18001dc8a  mov     rbp, [rsi]
0x18001dc8d  lea     rdx, [rbp-1]
0x18001dc91  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001dc95  ja      short loc_18001DCB4
0x18001dc97  lea     rcx, [rsp+68h+arg_0]; this
0x18001dc9c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001dca1  mov     rcx, rbp; hObject
0x18001dca4  call    cs:__imp_CloseHandle
0x18001dcaa  lea     rcx, [rsp+68h+arg_0]; this
0x18001dcaf  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001dcb4  mov     qword ptr [rsi], 0
0x18001dcbb  call    cs:__imp_GetCurrentThread
0x18001dcc1  mov     r9, rsi; TokenHandle
0x18001dcc4  mov     edx, 0Ch; DesiredAccess
0x18001dcc9  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18001dccd  mov     rcx, rax; ThreadHandle
0x18001dcd0  call    cs:__imp_OpenThreadToken
0x18001dcd6  test    r12d, r12d
0x18001dcd9  js      short loc_18001DD40
0x18001dcdb  lea     rax, [rbx+28h]
0x18001dcdf  mov     [rsp+68h+var_48], rax
0x18001dce4  mov     [rsp+68h+phModule], 0
0x18001dced  mov     [rsp+68h+var_38], 1
0x18001dcf2  lea     r8, [rsp+68h+phModule]; phModule
0x18001dcf7  lea     rdx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCDataSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpModuleName
0x18001dcfe  mov     ecx, 4; dwFlags
0x18001dd03  call    cs:__imp_GetModuleHandleExW
0x18001dd09  lea     rcx, [rsp+68h+var_48]
0x18001dd0e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(void)
0x18001dd13  xor     r8d, r8d; Flags
0x18001dd16  mov     rdx, rbx; Context
0x18001dd19  lea     rcx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCDataSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; Function
0x18001dd20  call    cs:__imp_QueueUserWorkItem
0x18001dd26  test    eax, eax
0x18001dd28  jnz     short loc_18001DD56
0x18001dd2a  call    cs:__imp_GetLastError
0x18001dd30  test    eax, eax
0x18001dd32  jle     short loc_18001DD3E
0x18001dd34  movzx   eax, ax
0x18001dd37  or      eax, 80070000h
0x18001dd3c  test    eax, eax
0x18001dd3e  jns     short loc_18001DD56
0x18001dd40  mov     rcx, rbx; void *
0x18001dd43  call    ??_GASYNC_PARAMS@?$CGetValueAsyncHelper@VCDataSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CDataSetting>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x18001dd48  mov     r8, r14
0x18001dd4b  mov     rdx, r15
0x18001dd4e  mov     rcx, rdi
0x18001dd51  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@VCDataSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CDataSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x18001dd56  lea     r11, [rsp+68h+var_28]
0x18001dd5b  mov     rbx, [r11+38h]
0x18001dd5f  mov     rbp, [r11+40h]
0x18001dd63  mov     rsp, r11
0x18001dd66  pop     r15
0x18001dd68  pop     r14
0x18001dd6a  pop     r12
0x18001dd6c  pop     rdi
0x18001dd6d  pop     rsi
0x18001dd6e  retn
```
