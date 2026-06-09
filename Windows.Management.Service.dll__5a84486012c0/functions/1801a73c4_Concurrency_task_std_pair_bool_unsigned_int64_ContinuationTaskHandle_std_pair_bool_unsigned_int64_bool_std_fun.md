# Concurrency::task<std::pair<bool,unsigned __int64>>::_ContinuationTaskHandle<std::pair<bool,unsigned __int64>,bool,std::function<bool (std::pair<bool,unsigned __int64>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x1801a73c4`
- end: `0x1801a74fc`
- name: `?_Continue@?$_ContinuationTaskHandle@U?$pair@_N_K@std@@_NV?$function@$$A6A_NU?$pair@_N_K@std@@@Z@2@U?$integral_constant@_N$0A@@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@U?$pair@_N_K@std@@@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801a96f0`

## callees

- `0x18000b820`
- `0x1800d84e0`
- `0x1800fbc44`
- `0x180119d1c`
- `0x1801a73c4`
- `0x1801fa010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801a7496`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801a7496`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a74b3`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a74b3`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a747c`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a747c`

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
  __int128 v9; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v10[64]; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v11[56]; // [rsp+80h] [rbp-68h] BYREF
  __int64 v12; // [rsp+B8h] [rbp-30h]

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  v3 = *(_OWORD *)(*(_QWORD *)(a1 + 56) + 368LL);
  v4 = std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(
         v10,
         a1 + 72);
  v5 = v4;
  v12 = 0;
  v6 = *(_QWORD *)(v4 + 56);
  if ( v6 )
  {
    if ( v6 == v4 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v6 + 8LL))(v6, v11);
      std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
    }
    else
    {
      v12 = *(_QWORD *)(v4 + 56);
      *(_QWORD *)(v4 + 56) = 0;
    }
  }
  std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
  v7 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v7);
  v9 = v3;
  if ( !v12 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v12 + 16LL))(v12, &v9);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v7);
  Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v2);
  return std::_Func_class<bool,std::wstring const &>::_Tidy(v11);
}

```

## disassembly

```asm
0x1801a73c4  mov     rax, rsp
0x1801a73c7  mov     [rax+10h], rbx
0x1801a73cb  mov     [rax+18h], rsi
0x1801a73cf  push    rdi
0x1801a73d0  sub     rsp, 0E0h
0x1801a73d7  movaps  xmmword ptr [rax-18h], xmm6
0x1801a73db  mov     rax, cs:__security_cookie
0x1801a73e2  xor     rax, rsp
0x1801a73e5  mov     [rsp+0E8h+var_28], rax
0x1801a73ed  mov     rdi, rcx
0x1801a73f0  mov     rsi, [rcx+28h]
0x1801a73f4  mov     rax, [rcx+38h]
0x1801a73f8  movups  xmm6, xmmword ptr [rax+170h]
0x1801a73ff  lea     rdx, [rcx+48h]
0x1801a7403  lea     rcx, [rsp+0E8h+var_A8]
0x1801a7408  call    ??0?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@2@@Z@std@@QEAA@AEBV01@@Z; std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)> const &)
0x1801a740d  mov     rbx, rax
0x1801a7410  mov     [rsp+0E8h+var_30], 0
0x1801a741c  mov     rcx, [rax+38h]
0x1801a7420  test    rcx, rcx
0x1801a7423  jz      short loc_1801A7460
0x1801a7425  cmp     rcx, rax
0x1801a7428  jnz     short loc_1801A7450
0x1801a742a  mov     rdx, [rcx]
0x1801a742d  mov     rax, [rdx+8]
0x1801a7431  lea     rdx, [rsp+0E8h+var_68]
0x1801a7439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a743e  mov     [rsp+0E8h+var_30], rax
0x1801a7446  mov     rcx, rbx
0x1801a7449  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x1801a744e  jmp     short loc_1801A7460
0x1801a7450  mov     [rsp+0E8h+var_30], rcx
0x1801a7458  mov     qword ptr [rax+38h], 0
0x1801a7460  mov     rcx, rbx
0x1801a7463  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x1801a7468  nop
0x1801a7469  mov     rdi, [rdi+28h]
0x1801a746d  add     rdi, 160h
0x1801a7474  mov     [rsp+0E8h+var_C8], rdi
0x1801a7479  mov     rcx, rdi
0x1801a747c  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1801a7482  nop
0x1801a7483  movdqa  [rsp+0E8h+var_B8], xmm6
0x1801a7489  mov     rcx, [rsp+0E8h+var_30]
0x1801a7491  test    rcx, rcx
0x1801a7494  jnz     short loc_1801A749D
0x1801a7496  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1801a749c  int     3; Trap to Debugger
0x1801a749d  mov     rax, [rcx]
0x1801a74a0  lea     rdx, [rsp+0E8h+var_B8]
0x1801a74a5  mov     rax, [rax+10h]
0x1801a74a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a74ae  mov     bl, al
0x1801a74b0  mov     rcx, rdi
0x1801a74b3  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1801a74b9  nop
0x1801a74ba  mov     dl, bl
0x1801a74bc  mov     rcx, rsi; this
0x1801a74bf  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x1801a74c4  nop
0x1801a74c5  lea     rcx, [rsp+0E8h+var_68]
0x1801a74cd  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x1801a74d2  mov     rcx, [rsp+0E8h+var_28]
0x1801a74da  xor     rcx, rsp; StackCookie
0x1801a74dd  call    __security_check_cookie
0x1801a74e2  lea     r11, [rsp+0E8h+var_8]
0x1801a74ea  mov     rbx, [r11+18h]
0x1801a74ee  mov     rsi, [r11+20h]
0x1801a74f2  movaps  xmm6, xmmword ptr [r11-10h]
0x1801a74f7  mov     rsp, r11
0x1801a74fa  pop     rdi
0x1801a74fb  retn
```
