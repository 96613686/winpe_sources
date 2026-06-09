# CdsToPenSettingTaskHandler::Start(IUnknown *,ushort *)

- ea: `0x180040b40`
- end: `0x180040cc9`
- name: `?Start@CdsToPenSettingTaskHandler@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `393`
- prototype: `__int64 __fastcall(CdsToPenSettingTaskHandler *this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800030e0`
- `0x1800102f4`
- `0x180010380`
- `0x180010ea8`
- `0x180019fcc`
- `0x18001a274`
- `0x18001a378`
- `0x18001dd44`
- `0x18003105c`
- `0x18003b2e4`
- `0x18003b33c`
- `0x18003b394`
- `0x18003b3e8`
- `0x18003bcf0`
- `0x18003e308`
- `0x18003eb08`
- `0x180040b40`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040c34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040c34`
- `OLEAUT32!__imp_SysStringLen` at `0x180040bae`
- `OLEAUT32!__imp_SysStringLen` at `0x180040bae`

## string_xrefs

- `0x180040cb6`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180040b62`: `Entering CdsToPenSettingTaskHandler`
- `0x180040c56`: `shellcommon\shell\settingshandlers\pen\lib\cdstopensettingtaskhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CdsToPenSettingTaskHandler::Start(
        CdsToPenSettingTaskHandler *this,
        struct IUnknown *a2,
        unsigned __int16 *a3)
{
  int v5; // eax
  __int64 v6; // r8
  __int64 v7; // rax
  const char *v8; // r9
  __int64 result; // rax
  DWORD CurrentThreadId; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // [rsp+20h] [rbp-68h]
  __int64 v15; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v16[16]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v17; // [rsp+40h] [rbp-48h]
  _BYTE v18[8]; // [rsp+50h] [rbp-38h] BYREF
  _BYTE v19[32]; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  PenSettingsTelemetry::CloudPenSettingsTask<unsigned short const (&)[36]>(L"Entering CdsToPenSettingTaskHandler");
  BYTE1(v14) = 1;
  PenSettingsTelemetry::CloudPenSettingsTask<unsigned short const (&)[47]>();
  v15 = 0;
  try
  {
    v5 = ((__int64 (*)(void))a2->lpVtbl->QueryInterface)();
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v5,
        v14);
    v6 = SysStringLen(a3);
    std::wstring::wstring(v16, a3, v6);
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v7, v17, L"SYNC_PEN_SETTINGS", 17) )
    {
      PenSettingsTelemetry::CloudPenSettingsTask<unsigned short const (&)[24]>();
      wil::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy>::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy>(
        v18,
        &v15);
      std::wstring::wstring(v19, v16);
      CurrentThreadId = GetCurrentThreadId();
      v13 = Windows::Internal::ComTaskPool::QueueTask__lambda_536eb1c8974d2b35d088cee14bcb25f5___(
              v12,
              v11,
              CurrentThreadId,
              v18);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x99,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\cdstopensettingtaskhandler.cpp",
          (const char *)(unsigned int)v13,
          v14);
      lambda_536eb1c8974d2b35d088cee14bcb25f5_::__lambda_536eb1c8974d2b35d088cee14bcb25f5_(v18);
      std::wstring::_Tidy_deallocate(v16);
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v15);
      PenSettingsTelemetry::CloudPenSettingsTask<unsigned short const (&)[35]>();
      result = 0;
    }
    else
    {
      std::wstring::_Tidy_deallocate(v16);
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v15);
      PenSettingsTelemetry::CloudPenSettingsTask<unsigned short const (&)[35]>();
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x9D,
                           (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\cdstopensettingtaskhandler.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180040b40  mov     [rsp+arg_0], rbx
0x180040b45  push    rdi
0x180040b46  sub     rsp, 80h
0x180040b4d  mov     rax, cs:__security_cookie
0x180040b54  xor     rax, rsp
0x180040b57  mov     [rsp+88h+var_10], rax
0x180040b5c  mov     rbx, r8
0x180040b5f  mov     rdi, rdx
0x180040b62  lea     rcx, aEnteringCdstop; "Entering CdsToPenSettingTaskHandler"
0x180040b69  call    ??$CloudPenSettingsTask@AEAY0CE@$$CBG@PenSettingsTelemetry@@SAXAEAY0CE@$$CBG@Z; PenSettingsTelemetry::CloudPenSettingsTask<ushort const (&)[36]>(ushort const (&)[36])
0x180040b6e  mov     [rsp+88h+var_67], 1
0x180040b73  call    ??$CloudPenSettingsTask@AEAY0CP@$$CBG@PenSettingsTelemetry@@SAXAEAY0CP@$$CBG@Z; PenSettingsTelemetry::CloudPenSettingsTask<ushort const (&)[47]>(ushort const (&)[47])
0x180040b78  mov     [rsp+88h+var_60], 0
0x180040b81  mov     rax, [rdi]
0x180040b84  lea     r8, [rsp+88h+var_60]
0x180040b89  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180040b90  mov     rcx, rdi
0x180040b93  mov     rax, [rax]
0x180040b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b9b  mov     rcx, [rsp+88h]; this
0x180040ba3  test    eax, eax
0x180040ba5  js      loc_180040CB3
0x180040bab  mov     rcx, rbx; pbstr
0x180040bae  call    cs:__imp_SysStringLen
0x180040bb4  mov     r8d, eax
0x180040bb7  mov     rdx, rbx
0x180040bba  lea     rcx, [rsp+88h+var_58]
0x180040bbf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x180040bc4  nop
0x180040bc5  lea     rcx, [rsp+88h+var_58]
0x180040bca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180040bcf  mov     rcx, rax
0x180040bd2  mov     r9d, 11h
0x180040bd8  lea     r8, aSyncPenSetting; "SYNC_PEN_SETTINGS"
0x180040bdf  mov     rdx, [rsp+88h+var_48]
0x180040be4  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180040be9  test    al, al
0x180040beb  jnz     short loc_180040C0F
0x180040bed  lea     rcx, [rsp+88h+var_58]
0x180040bf2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040bf7  nop
0x180040bf8  lea     rcx, [rsp+88h+var_60]
0x180040bfd  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180040c02  nop
0x180040c03  call    ??$CloudPenSettingsTask@AEAY0CD@$$CBG@PenSettingsTelemetry@@SAXAEAY0CD@$$CBG@Z; PenSettingsTelemetry::CloudPenSettingsTask<ushort const (&)[35]>(ushort const (&)[35])
0x180040c08  xor     eax, eax
0x180040c0a  jmp     loc_180040C95
0x180040c0f  call    ??$CloudPenSettingsTask@AEAY0BI@$$CBG@PenSettingsTelemetry@@SAXAEAY0BI@$$CBG@Z; PenSettingsTelemetry::CloudPenSettingsTask<ushort const (&)[24]>(ushort const (&)[24])
0x180040c14  lea     rdx, [rsp+88h+var_60]
0x180040c19  lea     rcx, [rsp+88h+var_38]
0x180040c1e  call    ??0?$com_ptr_t@UITaskHandlerStatus@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy>::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy>(wil::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy> const &)
0x180040c23  nop
0x180040c24  lea     rdx, [rsp+88h+var_58]
0x180040c29  lea     rcx, [rsp+88h+var_30]
0x180040c2e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180040c33  nop
0x180040c34  call    cs:__imp_GetCurrentThreadId
0x180040c3a  lea     r9, [rsp+88h+var_38]
0x180040c3f  mov     r8d, eax
0x180040c42  call    Windows__Internal__ComTaskPool__QueueTask__lambda_536eb1c8974d2b35d088cee14bcb25f5___
0x180040c47  mov     rcx, [rsp+88h]; this
0x180040c4f  test    eax, eax
0x180040c51  jns     short loc_180040C67
0x180040c53  mov     r9d, eax; char *
0x180040c56  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\p"...
0x180040c5d  mov     edx, 99h; void *
0x180040c62  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040c67  lea     rcx, [rsp+88h+var_38]
0x180040c6c  call    _lambda_536eb1c8974d2b35d088cee14bcb25f5_____lambda_536eb1c8974d2b35d088cee14bcb25f5_
0x180040c71  nop
0x180040c72  lea     rcx, [rsp+88h+var_58]
0x180040c77  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040c7c  nop
0x180040c7d  lea     rcx, [rsp+88h+var_60]
0x180040c82  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180040c87  nop
0x180040c88  call    ??$CloudPenSettingsTask@AEAY0CD@$$CBG@PenSettingsTelemetry@@SAXAEAY0CD@$$CBG@Z; PenSettingsTelemetry::CloudPenSettingsTask<ushort const (&)[35]>(ushort const (&)[35])
0x180040c8d  xor     eax, eax
0x180040c8f  jmp     short loc_180040C95
0x180040c91  mov     eax, [rsp+20h]
0x180040c95  mov     rcx, [rsp+88h+var_10]
0x180040c9a  xor     rcx, rsp; StackCookie
0x180040c9d  call    __security_check_cookie
0x180040ca2  mov     rbx, [rsp+88h+arg_0]
0x180040caa  add     rsp, 80h
0x180040cb1  pop     rdi
0x180040cb2  retn
0x180040cb3  mov     r9d, eax; char *
0x180040cb6  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180040cbd  mov     edx, 1CBEh; void *
0x180040cc2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
