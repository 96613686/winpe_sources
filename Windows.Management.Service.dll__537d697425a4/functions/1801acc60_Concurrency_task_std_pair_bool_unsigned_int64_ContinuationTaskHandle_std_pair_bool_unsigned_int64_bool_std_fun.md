# Concurrency::task<std::pair<bool,unsigned __int64>>::_ContinuationTaskHandle<std::pair<bool,unsigned __int64>,bool,std::function<bool (std::pair<bool,unsigned __int64>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x1801acc60`
- end: `0x1801acdab`
- name: `?_Continue@?$_ContinuationTaskHandle@U?$pair@_N_K@std@@_NV?$function@$$A6A_NU?$pair@_N_K@std@@@Z@2@U?$integral_constant@_N$0A@@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@U?$pair@_N_K@std@@@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801af0e0`

## callees

- `0x18000b8f0`
- `0x1800dabf0`
- `0x1800fed34`
- `0x18011d5b4`
- `0x1801acc60`
- `0x180200010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801acd38`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801acd38`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801acd5b`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801acd5b`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801acd18`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801acd18`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::task<std::pair<bool,unsigned __int64>>::_ContinuationTaskHandle<std::pair<bool,unsigned __int64>,bool,std::function<bool (std::pair<bool,unsigned __int64>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // rsi
  __int128 v3; // xmm6
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rcx
  Concurrency::details::_TaskEventLogger *v7; // rdi
  __int64 v8; // rcx
  __int128 v10; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v11[64]; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v12[56]; // [rsp+80h] [rbp-68h] BYREF
  __int64 v13; // [rsp+B8h] [rbp-30h]

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  v3 = *(_OWORD *)(*(_QWORD *)(a1 + 56) + 368LL);
  v4 = std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(
         v11,
         a1 + 72);
  v5 = v4;
  v13 = 0;
  v6 = *(_QWORD *)(v4 + 56);
  if ( v6 )
  {
    if ( v6 == v4 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v6 + 8LL))(v6, v12);
      std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
    }
    else
    {
      v13 = *(_QWORD *)(v4 + 56);
      *(_QWORD *)(v4 + 56) = 0;
    }
  }
  std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
  v7 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v7);
  v10 = v3;
  v8 = v13;
  if ( !v13 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v8 + 16LL))(v8, &v10);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v7);
  Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v2);
  return std::_Func_class<bool,std::wstring const &>::_Tidy(v12);
}

```

## disassembly

```asm
0x1801acc60  mov     rax, rsp
0x1801acc63  mov     [rax+10h], rbx
0x1801acc67  mov     [rax+18h], rsi
0x1801acc6b  push    rdi
0x1801acc6c  sub     rsp, 0E0h
0x1801acc73  movaps  xmmword ptr [rax-18h], xmm6
0x1801acc77  mov     rax, cs:__security_cookie
0x1801acc7e  xor     rax, rsp
0x1801acc81  mov     [rsp+0E8h+var_28], rax
0x1801acc89  mov     rdi, rcx
0x1801acc8c  mov     rsi, [rcx+28h]
0x1801acc90  mov     rax, [rcx+38h]
0x1801acc94  movups  xmm6, xmmword ptr [rax+170h]
0x1801acc9b  lea     rdx, [rcx+48h]
0x1801acc9f  lea     rcx, [rsp+0E8h+var_A8]
0x1801acca4  call    ??0?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@2@@Z@std@@QEAA@AEBV01@@Z; std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)> const &)
0x1801acca9  mov     rbx, rax
0x1801accac  mov     [rsp+0E8h+var_30], 0
0x1801accb8  mov     rcx, [rax+38h]
0x1801accbc  test    rcx, rcx
0x1801accbf  jz      short loc_1801ACCFC
0x1801accc1  cmp     rcx, rax
0x1801accc4  jnz     short loc_1801ACCEC
0x1801accc6  mov     rdx, [rcx]
0x1801accc9  mov     rax, [rdx+8]
0x1801acccd  lea     rdx, [rsp+0E8h+var_68]
0x1801accd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801accda  mov     [rsp+0E8h+var_30], rax
0x1801acce2  mov     rcx, rbx
0x1801acce5  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x1801accea  jmp     short loc_1801ACCFC
0x1801accec  mov     [rsp+0E8h+var_30], rcx
0x1801accf4  mov     qword ptr [rax+38h], 0
0x1801accfc  mov     rcx, rbx
0x1801accff  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x1801acd04  nop
0x1801acd05  mov     rdi, [rdi+28h]
0x1801acd09  add     rdi, 160h
0x1801acd10  mov     [rsp+0E8h+var_C8], rdi
0x1801acd15  mov     rcx, rdi
0x1801acd18  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1801acd1f  nop     dword ptr [rax+rax+00h]
0x1801acd24  nop
0x1801acd25  movdqa  [rsp+0E8h+var_B8], xmm6
0x1801acd2b  mov     rcx, [rsp+0E8h+var_30]
0x1801acd33  test    rcx, rcx
0x1801acd36  jnz     short loc_1801ACD45
0x1801acd38  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1801acd3f  nop     dword ptr [rax+rax+00h]
0x1801acd44  int     3; Trap to Debugger
0x1801acd45  mov     rax, [rcx]
0x1801acd48  lea     rdx, [rsp+0E8h+var_B8]
0x1801acd4d  mov     rax, [rax+10h]
0x1801acd51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801acd56  mov     bl, al
0x1801acd58  mov     rcx, rdi
0x1801acd5b  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1801acd62  nop     dword ptr [rax+rax+00h]
0x1801acd67  nop
0x1801acd68  mov     dl, bl
0x1801acd6a  mov     rcx, rsi; this
0x1801acd6d  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x1801acd72  nop
0x1801acd73  lea     rcx, [rsp+0E8h+var_68]
0x1801acd7b  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x1801acd80  mov     rcx, [rsp+0E8h+var_28]
0x1801acd88  xor     rcx, rsp; StackCookie
0x1801acd8b  call    __security_check_cookie
0x1801acd90  lea     r11, [rsp+0E8h+var_8]
0x1801acd98  mov     rbx, [r11+18h]
0x1801acd9c  mov     rsi, [r11+20h]
0x1801acda0  movaps  xmm6, xmmword ptr [r11-10h]
0x1801acda5  mov     rsp, r11
0x1801acda8  pop     rdi
0x1801acda9  retn
```
