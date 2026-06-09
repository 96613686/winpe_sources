# LogonSound::WaitForLogoffSound(uint)

- ea: `0x180083d10`
- end: `0x180083e6b`
- name: `?WaitForLogoffSound@LogonSound@@QEAAJI@Z`
- size: `347`
- prototype: `__int64 __fastcall(LogonSound *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002cd60`

## callees

- `0x18002a8b0`
- `0x18002e820`
- `0x180047304`
- `0x18005d488`
- `0x18005f1f8`
- `0x180066384`
- `0x180083d10`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180083e44`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180083e44`
- `KERNEL32!CreateThreadpoolTimer` at `0x180083d86`
- `KERNEL32!CreateThreadpoolTimer` at `0x180083d86`
- `KERNEL32!SetThreadpoolTimer` at `0x180083de2`
- `KERNEL32!SetThreadpoolTimer` at `0x180083e36`
- `KERNEL32!SetThreadpoolTimer` at `0x180083de2`
- `KERNEL32!SetThreadpoolTimer` at `0x180083e36`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LogonSound::WaitForLogoffSound(LogonSound *this, unsigned int a2)
{
  __int64 v2; // r14
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdi
  PTP_TIMER v7; // rax
  struct _TP_TIMER *v8; // rbx
  __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // edi
  int v13; // [rsp+20h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  PTP_TIMER pti; // [rsp+70h] [rbp+30h] BYREF
  __int64 v17; // [rsp+80h] [rbp+40h] BYREF
  __int64 pv; // [rsp+88h] [rbp+48h] BYREF

  v2 = a2;
  if ( *((_QWORD *)this + 13) )
  {
    v17 = 0;
    v4 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
           &v17,
           1);
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\logonsound.cpp",
        (const char *)(unsigned int)v4,
        v13);
LABEL_8:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
      return v5;
    }
    pti = 0;
    v6 = v17;
    pv = v17;
    v7 = CreateThreadpoolTimer(lambda_ae4dca90e75eae5c1af6058694cb6af3_::_lambda_invoker_cdecl_, &pv, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&void CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      &pti,
      v7);
    v8 = pti;
    if ( !pti )
    {
      v5 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\logonsound.cpp",
        (const char *)0x8007000ELL,
        v13);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&void CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&void CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&pti);
      goto LABEL_8;
    }
    pftDueTime = (struct _FILETIME)(-10000 * v2);
    SetThreadpoolTimer(pti, &pftDueTime, 0, 0);
    v10 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
            *((_QWORD *)this + 13),
            v9,
            v6);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\logonsound.cpp",
        (const char *)(unsigned int)v10,
        v13);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&void CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&void CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&pti);
      v5 = v11;
      goto LABEL_8;
    }
    SetThreadpoolTimer(v8, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v8, 1);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&void CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&void CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&pti);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  }
  return 0;
}

```

## disassembly

```asm
0x180083d10  push    rbp
0x180083d12  push    rbx
0x180083d13  push    rsi
0x180083d14  push    rdi
0x180083d15  push    r14
0x180083d17  mov     rbp, rsp
0x180083d1a  sub     rsp, 40h
0x180083d1e  mov     r14d, edx
0x180083d21  mov     rsi, rcx
0x180083d24  cmp     qword ptr [rcx+68h], 0
0x180083d29  jz      loc_180083E5E
0x180083d2f  mov     [rbp+arg_10], 0
0x180083d37  mov     edx, 1
0x180083d3c  lea     rcx, [rbp+arg_10]
0x180083d40  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180083d45  mov     ebx, eax
0x180083d47  test    eax, eax
0x180083d49  jns     short loc_180083D68
0x180083d4b  mov     rcx, [rbp+28h]; this
0x180083d4f  mov     r9d, eax; char *
0x180083d52  lea     r8, aPcshellShellAu; "pcshell\\shell\\auth\\authux\\controlle"...
0x180083d59  mov     edx, 34h ; '4'; void *
0x180083d5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083d63  jmp     loc_180083E1E
0x180083d68  mov     [rbp+pti], 0
0x180083d70  mov     rdi, [rbp+arg_10]
0x180083d74  mov     [rbp+pv], rdi
0x180083d78  xor     r8d, r8d; pcbe
0x180083d7b  lea     rdx, [rbp+pv]; pv
0x180083d7f  lea     rcx, _lambda_ae4dca90e75eae5c1af6058694cb6af3____lambda_invoker_cdecl_; pfnti
0x180083d86  call    cs:__imp_CreateThreadpoolTimer
0x180083d8c  mov     rdx, rax
0x180083d8f  lea     rcx, [rbp+pti]
0x180083d93  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?CloseThreadpoolTimer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180083d98  mov     rbx, [rbp+pti]
0x180083d9c  test    rbx, rbx
0x180083d9f  jnz     short loc_180083DCA
0x180083da1  mov     rcx, [rbp+28h]; this
0x180083da5  mov     ebx, 8007000Eh
0x180083daa  mov     r9d, ebx; char *
0x180083dad  lea     r8, aPcshellShellAu; "pcshell\\shell\\auth\\authux\\controlle"...
0x180083db4  mov     edx, 3Eh ; '>'; void *
0x180083db9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083dbe  nop
0x180083dbf  lea     rcx, [rbp+pti]
0x180083dc3  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?CloseThreadpoolTimer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x180083dc8  jmp     short loc_180083E1E
0x180083dca  imul    rcx, r14, 0FFFFFFFFFFFFD8F0h
0x180083dd1  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rcx
0x180083dd5  xor     r9d, r9d; msWindowLength
0x180083dd8  xor     r8d, r8d; msPeriod
0x180083ddb  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x180083ddf  mov     rcx, rbx; pti
0x180083de2  call    cs:__imp_SetThreadpoolTimer
0x180083de8  mov     r8, rdi
0x180083deb  mov     rcx, [rsi+68h]
0x180083def  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x180083df4  mov     edi, eax
0x180083df6  test    eax, eax
0x180083df8  jns     short loc_180083E2B
0x180083dfa  mov     rcx, [rbp+28h]; this
0x180083dfe  mov     r9d, eax; char *
0x180083e01  lea     r8, aPcshellShellAu; "pcshell\\shell\\auth\\authux\\controlle"...
0x180083e08  mov     edx, 45h ; 'E'; void *
0x180083e0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083e12  nop
0x180083e13  lea     rcx, [rbp+pti]
0x180083e17  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?CloseThreadpoolTimer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x180083e1c  mov     ebx, edi
0x180083e1e  lea     rcx, [rbp+arg_10]
0x180083e22  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180083e27  mov     eax, ebx
0x180083e29  jmp     short loc_180083E60
0x180083e2b  xor     r9d, r9d; msWindowLength
0x180083e2e  xor     r8d, r8d; msPeriod
0x180083e31  xor     edx, edx; pftDueTime
0x180083e33  mov     rcx, rbx; pti
0x180083e36  call    cs:__imp_SetThreadpoolTimer
0x180083e3c  mov     edx, 1; fCancelPendingCallbacks
0x180083e41  mov     rcx, rbx; pti
0x180083e44  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180083e4a  nop
0x180083e4b  lea     rcx, [rbp+pti]
0x180083e4f  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?CloseThreadpoolTimer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x180083e54  nop
0x180083e55  lea     rcx, [rbp+arg_10]
0x180083e59  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180083e5e  xor     eax, eax
0x180083e60  add     rsp, 40h
0x180083e64  pop     r14
0x180083e66  pop     rdi
0x180083e67  pop     rsi
0x180083e68  pop     rbx
0x180083e69  pop     rbp
0x180083e6a  retn
```
