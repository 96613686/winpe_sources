# Windows::Globalization::Spelling::CSpellerDecorator::RemoteCall(std::function<long (void)> const &)

- ea: `0x180029e0c`
- end: `0x180029ed8`
- name: `?RemoteCall@CSpellerDecorator@Spelling@Globalization@Windows@@AEAAJAEBV?$function@$$A6AJXZ@std@@@Z`
- size: `204`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180029840`
- `0x180029940`
- `0x180029a40`
- `0x180056240`
- `0x180056b80`
- `0x18005ab60`
- `0x18005b710`
- `0x18005bb60`
- `0x18005e3c0`

## callees

- `0x180029e0c`
- `0x18002a30c`
- `0x180061320`
- `0x1800c0010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180029e5a`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180029e5a`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180029e7e`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180029e7e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180029e93`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180029e93`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Globalization::Spelling::CSpellerDecorator::RemoteCall(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  _QWORD *v3; // rdx
  _BYTE v5[8]; // [rsp+20h] [rbp-19h] BYREF
  int v6; // [rsp+28h] [rbp-11h]
  HANDLE Timer; // [rsp+30h] [rbp-9h]
  _QWORD v8[7]; // [rsp+40h] [rbp+7h] BYREF
  _QWORD *v9; // [rsp+78h] [rbp+3Fh]

  v8[0] = &std::_Func_impl_no_alloc<_lambda_df0bb537e9b1ba65d8e1356f7bb25b0d_,long,>::`vftable';
  v8[1] = a2;
  v8[2] = a1;
  v9 = v8;
  CRPCTimeout::CRPCTimeout((CRPCTimeout *)v5);
  if ( !v9 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v2 = (*(__int64 (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
  if ( v6 >= 0 )
  {
    v6 = -2147467259;
    CoDisableCallCancellation(0);
    if ( Timer )
      DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  }
  if ( v9 )
  {
    v3 = v8;
    LOBYTE(v3) = v9 != v8;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v9 + 32LL))(v9, v3);
  }
  return v2;
}

```

## disassembly

```asm
0x180029e0c  mov     [rsp-8+arg_0], rbx
0x180029e11  push    rbp
0x180029e12  lea     rbp, [rsp-57h]
0x180029e17  sub     rsp, 90h
0x180029e1e  mov     rax, cs:__security_cookie
0x180029e25  xor     rax, rsp
0x180029e28  mov     [rbp+57h+var_10], rax
0x180029e2c  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_df0bb537e9b1ba65d8e1356f7bb25b0d_@@J$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_df0bb537e9b1ba65d8e1356f7bb25b0d_,long,>::`vftable'
0x180029e33  mov     [rbp+57h+var_50], rax
0x180029e37  mov     [rbp+57h+var_48], rdx
0x180029e3b  mov     [rbp+57h+var_40], rcx
0x180029e3f  lea     rax, [rbp+57h+var_50]
0x180029e43  mov     [rbp+57h+var_18], rax
0x180029e47  lea     rcx, [rbp+57h+var_70]; this
0x180029e4b  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x180029e50  nop
0x180029e51  mov     rcx, [rbp+57h+var_18]
0x180029e55  test    rcx, rcx
0x180029e58  jnz     short loc_180029E61
0x180029e5a  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180029e60  int     3; Trap to Debugger
0x180029e61  mov     rax, [rcx]
0x180029e64  mov     rax, [rax+10h]
0x180029e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e6d  mov     ebx, eax
0x180029e6f  cmp     [rbp+57h+var_68], 0
0x180029e73  jl      short loc_180029E9A
0x180029e75  mov     [rbp+57h+var_68], 80004005h
0x180029e7c  xor     ecx, ecx; pReserved
0x180029e7e  call    cs:__imp_CoDisableCallCancellation
0x180029e84  mov     rdx, [rbp+57h+Timer]; Timer
0x180029e88  test    rdx, rdx
0x180029e8b  jz      short loc_180029E9A
0x180029e8d  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180029e91  xor     ecx, ecx; TimerQueue
0x180029e93  call    cs:__imp_DeleteTimerQueueTimer
0x180029e99  nop
0x180029e9a  mov     rcx, [rbp+57h+var_18]
0x180029e9e  test    rcx, rcx
0x180029ea1  jz      short loc_180029EB9
0x180029ea3  mov     rax, [rcx]
0x180029ea6  lea     rdx, [rbp+57h+var_50]
0x180029eaa  cmp     rcx, rdx
0x180029ead  setnz   dl
0x180029eb0  mov     rax, [rax+20h]
0x180029eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029eb9  mov     eax, ebx
0x180029ebb  mov     rcx, [rbp+57h+var_10]
0x180029ebf  xor     rcx, rsp; StackCookie
0x180029ec2  call    __security_check_cookie
0x180029ec7  mov     rbx, [rsp+90h+arg_0]
0x180029ecf  add     rsp, 90h
0x180029ed6  pop     rbp
0x180029ed7  retn
```
