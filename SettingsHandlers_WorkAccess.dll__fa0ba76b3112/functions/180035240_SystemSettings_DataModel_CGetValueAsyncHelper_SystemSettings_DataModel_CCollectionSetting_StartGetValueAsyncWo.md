# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::StartGetValueAsyncWork(ushort const *,SystemSettings::DataModel::CSettingBase *)

- ea: `0x180035240`
- end: `0x18003544a`
- name: `?StartGetValueAsyncWork@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEBGPEAVCSettingBase@23@@Z`
- size: `522`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800042b4`
- `0x18000526c`
- `0x1800058fc`
- `0x1800105a4`
- `0x18002ebec`
- `0x18002ff6c`
- `0x180031854`
- `0x180035240`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800353cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800353cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800353fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800353fe`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035392`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035392`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035377`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035377`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003535a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003535a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800353ee`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800353ee`
- `api-ms-win-shlwapi-ie-l1-1-0!SHStrDupW` at `0x18003532d`
- `api-ms-win-shlwapi-ie-l1-1-0!SHStrDupW` at `0x18003532d`

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
0x180035240  mov     [rsp+arg_8], rbx
0x180035245  mov     [rsp+arg_10], rbp
0x18003524a  push    rsi
0x18003524b  push    rdi
0x18003524c  push    r12
0x18003524e  push    r14
0x180035250  push    r15
0x180035252  sub     rsp, 40h
0x180035256  mov     r15, r8
0x180035259  mov     r14, rdx
0x18003525c  mov     rdi, rcx
0x18003525f  mov     eax, 1
0x180035264  xchg    eax, [rcx+0E0h]
0x18003526a  test    eax, eax
0x18003526c  jnz     loc_180035430
0x180035272  mov     rax, [r8]
0x180035275  mov     dl, 1
0x180035277  mov     rcx, r8
0x18003527a  mov     rax, [rax+0A8h]
0x180035281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035286  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003528d  mov     ecx, 30h ; '0'; unsigned __int64
0x180035292  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035297  mov     rbx, rax
0x18003529a  mov     [rsp+68h+arg_0], rax
0x18003529f  test    rax, rax
0x1800352a2  jz      loc_180035422
0x1800352a8  mov     qword ptr [rax], 0
0x1800352af  mov     qword ptr [rax+8], 0
0x1800352b7  mov     qword ptr [rax+10h], 0
0x1800352bf  mov     qword ptr [rax+18h], 0
0x1800352c7  mov     qword ptr [rax+28h], 0
0x1800352cf  test    rax, rax
0x1800352d2  jz      loc_180035422
0x1800352d8  xor     r12d, r12d
0x1800352db  lea     rcx, [rax+8]
0x1800352df  mov     rdx, r15
0x1800352e2  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x1800352e7  cmp     [rbx], rdi
0x1800352ea  jz      short loc_180035319
0x1800352ec  test    rdi, rdi
0x1800352ef  jz      short loc_180035301
0x1800352f1  mov     rax, [rdi]
0x1800352f4  mov     rcx, rdi
0x1800352f7  mov     rax, [rax+8]
0x1800352fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035300  nop
0x180035301  mov     rcx, [rbx]
0x180035304  mov     [rbx], rdi
0x180035307  test    rcx, rcx
0x18003530a  jz      short loc_180035319
0x18003530c  mov     rax, [rcx]
0x18003530f  mov     rax, [rax+10h]
0x180035313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035318  nop
0x180035319  mov     qword ptr [rbx+20h], 0
0x180035321  test    r14, r14
0x180035324  jz      short loc_18003533C
0x180035326  lea     rdx, [rbx+10h]; ppwsz
0x18003532a  mov     rcx, r14; psz
0x18003532d  call    cs:__imp_SHStrDupW
0x180035334  nop     dword ptr [rax+rax+00h]
0x180035339  mov     r12d, eax
0x18003533c  lea     rsi, [rbx+18h]
0x180035340  mov     rbp, [rsi]
0x180035343  lea     rdx, [rbp-1]
0x180035347  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003534b  ja      short loc_180035370
0x18003534d  lea     rcx, [rsp+68h+arg_0]; this
0x180035352  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180035357  mov     rcx, rbp; hObject
0x18003535a  call    cs:__imp_CloseHandle
0x180035361  nop     dword ptr [rax+rax+00h]
0x180035366  lea     rcx, [rsp+68h+arg_0]; this
0x18003536b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180035370  mov     qword ptr [rsi], 0
0x180035377  call    cs:__imp_GetCurrentThread
0x18003537e  nop     dword ptr [rax+rax+00h]
0x180035383  mov     r9, rsi; TokenHandle
0x180035386  mov     edx, 0Ch; DesiredAccess
0x18003538b  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18003538f  mov     rcx, rax; ThreadHandle
0x180035392  call    cs:__imp_OpenThreadToken
0x180035399  nop     dword ptr [rax+rax+00h]
0x18003539e  test    r12d, r12d
0x1800353a1  js      short loc_18003541A
0x1800353a3  lea     rax, [rbx+28h]
0x1800353a7  mov     [rsp+68h+var_48], rax
0x1800353ac  mov     [rsp+68h+phModule], 0
0x1800353b5  mov     [rsp+68h+var_38], 1
0x1800353ba  lea     r8, [rsp+68h+phModule]; phModule
0x1800353bf  lea     rdx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpModuleName
0x1800353c6  mov     ecx, 4; dwFlags
0x1800353cb  call    cs:__imp_GetModuleHandleExW
0x1800353d2  nop     dword ptr [rax+rax+00h]
0x1800353d7  lea     rcx, [rsp+68h+var_48]
0x1800353dc  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(void)
0x1800353e1  xor     r8d, r8d; Flags
0x1800353e4  mov     rdx, rbx; Context
0x1800353e7  lea     rcx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; Function
0x1800353ee  call    cs:__imp_QueueUserWorkItem
0x1800353f5  nop     dword ptr [rax+rax+00h]
0x1800353fa  test    eax, eax
0x1800353fc  jnz     short loc_180035430
0x1800353fe  call    cs:__imp_GetLastError
0x180035405  nop     dword ptr [rax+rax+00h]
0x18003540a  test    eax, eax
0x18003540c  jle     short loc_180035418
0x18003540e  movzx   eax, ax
0x180035411  or      eax, 80070000h
0x180035416  test    eax, eax
0x180035418  jns     short loc_180035430
0x18003541a  mov     rcx, rbx; void *
0x18003541d  call    ??_GASYNC_PARAMS@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x180035422  mov     r8, r14
0x180035425  mov     rdx, r15
0x180035428  mov     rcx, rdi
0x18003542b  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x180035430  lea     r11, [rsp+68h+var_28]
0x180035435  mov     rbx, [r11+38h]
0x180035439  mov     rbp, [r11+40h]
0x18003543d  mov     rsp, r11
0x180035440  pop     r15
0x180035442  pop     r14
0x180035444  pop     r12
0x180035446  pop     rdi
0x180035447  pop     rsi
0x180035448  retn
```
