# Concurrency::task<uchar>::_ContinuationTaskHandle<void,bool,std::function<bool (void)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x1801a76cc`
- end: `0x1801a779c`
- name: `?_Continue@?$_ContinuationTaskHandle@X_NV?$function@$$A6A_NXZ@std@@U?$integral_constant@_N$0A@@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801a97f0`

## callees

- `0x1800d84e0`
- `0x1800fbc44`
- `0x180119d1c`
- `0x1801a2588`
- `0x1801a76cc`
- `0x1801fa010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801a7740`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801a7740`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a775d`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a775d`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a772a`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a772a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,bool,std::function<bool (void)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // rbp
  char v3; // di
  Concurrency::details::_TaskEventLogger *v4; // rsi
  __int64 result; // rax
  _BYTE *v6; // rdx
  _BYTE v7[8]; // [rsp+20h] [rbp-B8h] BYREF
  __int64 v8; // [rsp+28h] [rbp-B0h]
  _BYTE v9[56]; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE *v10; // [rsp+68h] [rbp-70h]
  _BYTE v11[104]; // [rsp+70h] [rbp-68h] BYREF

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  v3 = *(_BYTE *)(*(_QWORD *)(a1 + 56) + 368LL);
  v8 = std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(
         v11,
         a1 + 72);
  Concurrency::details::_MakeUnitToTFunc<bool>(v9, v8);
  std::_Func_class<bool,std::wstring const &>::_Tidy(v8);
  v4 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  v8 = (__int64)v4;
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v4);
  v7[0] = v3;
  if ( !v10 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v10 + 16LL))(v10, v7);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v4);
  result = Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v2);
  if ( v10 )
  {
    v6 = v9;
    LOBYTE(v6) = v10 != v9;
    return (*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v10 + 32LL))(v10, v6);
  }
  return result;
}

```

## disassembly

```asm
0x1801a76cc  push    rbx
0x1801a76ce  push    rbp
0x1801a76cf  push    rsi
0x1801a76d0  push    rdi
0x1801a76d1  sub     rsp, 0B8h
0x1801a76d8  mov     rsi, rcx
0x1801a76db  mov     rbp, [rcx+28h]
0x1801a76df  mov     rax, [rcx+38h]
0x1801a76e3  mov     dil, [rax+170h]
0x1801a76ea  lea     rdx, [rcx+48h]
0x1801a76ee  lea     rcx, [rsp+0D8h+var_68]
0x1801a76f3  call    ??0?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@2@@Z@std@@QEAA@AEBV01@@Z; std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)> const &)
0x1801a76f8  mov     rbx, rax
0x1801a76fb  mov     [rsp+0D8h+var_B0], rax
0x1801a7700  mov     rdx, rax
0x1801a7703  lea     rcx, [rsp+0D8h+var_A8]
0x1801a7708  call    ??$_MakeUnitToTFunc@_N@details@Concurrency@@YA?AV?$function@$$A6A_NE@Z@std@@AEBV?$function@$$A6A_NXZ@3@@Z; Concurrency::details::_MakeUnitToTFunc<bool>(std::function<bool (void)> const &)
0x1801a770d  nop
0x1801a770e  mov     rcx, rbx
0x1801a7711  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x1801a7716  nop
0x1801a7717  mov     rsi, [rsi+28h]
0x1801a771b  add     rsi, 160h
0x1801a7722  mov     [rsp+0D8h+var_B0], rsi
0x1801a7727  mov     rcx, rsi
0x1801a772a  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1801a7730  nop
0x1801a7731  mov     [rsp+0D8h+var_B8], dil
0x1801a7736  mov     rcx, [rsp+0D8h+var_70]
0x1801a773b  test    rcx, rcx
0x1801a773e  jnz     short loc_1801A7747
0x1801a7740  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1801a7746  int     3; Trap to Debugger
0x1801a7747  mov     rax, [rcx]
0x1801a774a  lea     rdx, [rsp+0D8h+var_B8]
0x1801a774f  mov     rax, [rax+10h]
0x1801a7753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a7758  mov     bl, al
0x1801a775a  mov     rcx, rsi
0x1801a775d  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1801a7763  nop
0x1801a7764  mov     dl, bl
0x1801a7766  mov     rcx, rbp; this
0x1801a7769  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x1801a776e  nop
0x1801a776f  mov     rcx, [rsp+0D8h+var_70]
0x1801a7774  test    rcx, rcx
0x1801a7777  jz      short loc_1801A7790
0x1801a7779  mov     rax, [rcx]
0x1801a777c  lea     rdx, [rsp+0D8h+var_A8]
0x1801a7781  cmp     rcx, rdx
0x1801a7784  setnz   dl
0x1801a7787  mov     rax, [rax+20h]
0x1801a778b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a7790  add     rsp, 0B8h
0x1801a7797  pop     rdi
0x1801a7798  pop     rsi
0x1801a7799  pop     rbp
0x1801a779a  pop     rbx
0x1801a779b  retn
```
