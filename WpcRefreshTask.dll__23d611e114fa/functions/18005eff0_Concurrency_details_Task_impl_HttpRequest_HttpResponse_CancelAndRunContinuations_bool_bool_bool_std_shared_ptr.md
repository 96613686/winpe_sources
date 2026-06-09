# Concurrency::details::_Task_impl<HttpRequest::HttpResponse>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x18005eff0`
- end: `0x18005f192`
- name: `?_CancelAndRunContinuations@?$_Task_impl@VHttpResponse@HttpRequest@@@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `418`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800060a0`
- `0x180017b64`
- `0x18001aba4`
- `0x18001cad4`
- `0x18005eff0`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18005f0dd`
- `msvcp_win!_Mtx_unlock` at `0x18005f16d`
- `msvcp_win!_Mtx_unlock` at `0x18005f0dd`
- `msvcp_win!_Mtx_unlock` at `0x18005f16d`
- `msvcp_win!_Mtx_lock` at `0x18005f02c`
- `msvcp_win!_Mtx_lock` at `0x18005f02c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005f03b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005f057`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005f03b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005f057`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005f0d3`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005f0d3`

## pseudocode

```c
char __fastcall Concurrency::details::_Task_impl<HttpRequest::HttpResponse>::_CancelAndRunContinuations(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v8; // rsi
  int v9; // eax
  int v10; // edi
  int v11; // edi
  __int64 v12; // rcx
  _QWORD *v13; // rdx
  _QWORD v15[7]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD *v16; // [rsp+68h] [rbp-50h]

  v8 = a1 + 32;
  if ( _Mtx_lock((_Mtx_t)(a1 + 32)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v8 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v8 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v9 = *(_DWORD *)(a1 + 8);
  if ( !a3 )
  {
    if ( v9 != 3 && *(_DWORD *)(a1 + 8) != 4 && (*(_DWORD *)(a1 + 8) != 2 || a2) )
      goto LABEL_12;
LABEL_25:
    _Mtx_unlock((_Mtx_t)v8);
    return 0;
  }
  if ( v9 == 4 )
    goto LABEL_25;
  std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(a1 + 16, a5);
LABEL_12:
  if ( a2 )
  {
    *(_DWORD *)(a1 + 8) = 4;
    v10 = 1;
  }
  else
  {
    v10 = 0;
    if ( *(_DWORD *)(a1 + 8) == 1 )
      v10 = 2;
    *(_DWORD *)(a1 + 8) = 2;
    Concurrency::details::_TaskEventLogger::_LogCancelTask((Concurrency::details::_TaskEventLogger *)(a1 + 352));
  }
  _Mtx_unlock((_Mtx_t)v8);
  v11 = v10 - 1;
  if ( v11 )
  {
    if ( v11 == 1 )
    {
      v12 = *(_QWORD *)(a1 + 480);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  else
  {
    Concurrency::details::_TaskCollectionBaseImpl::_Complete((_Cnd_t)(a1 + 136));
    if ( *(_QWORD *)(a1 + 112) )
    {
      v15[0] = &std::_Func_impl_no_alloc<_lambda_0eca18b9299534febb6cd2c81392266d_,void,>::`vftable';
      v15[1] = a1;
      v16 = v15;
      Concurrency::details::_ScheduleFuncWithAutoInline(v15, 16);
      if ( v16 )
      {
        v13 = v15;
        LOBYTE(v13) = v16 != v15;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v16 + 32LL))(v16, v13);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18005eff0  push    rbx
0x18005eff2  push    rbp
0x18005eff3  push    rsi
0x18005eff4  push    rdi
0x18005eff5  push    r14
0x18005eff7  push    r15
0x18005eff9  sub     rsp, 88h
0x18005f000  mov     rax, cs:__security_cookie
0x18005f007  xor     rax, rsp
0x18005f00a  mov     [rsp+0B8h+var_48], rax
0x18005f00f  mov     bpl, r8b
0x18005f012  mov     dil, dl
0x18005f015  mov     rbx, rcx
0x18005f018  mov     r14, [rsp+0B8h+arg_20]
0x18005f020  lea     rsi, [rcx+20h]
0x18005f024  mov     [rsp+0B8h+var_98], rsi
0x18005f029  mov     rcx, rsi; _Mtx_t
0x18005f02c  call    cs:__imp__Mtx_lock
0x18005f032  test    eax, eax
0x18005f034  jz      short loc_18005F042
0x18005f036  mov     ecx, 5
0x18005f03b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005f041  int     3; Trap to Debugger
0x18005f042  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x18005f049  jnz     short loc_18005F05E
0x18005f04b  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x18005f052  mov     ecx, 6
0x18005f057  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005f05d  nop
0x18005f05e  mov     r15d, 2
0x18005f064  mov     eax, [rbx+8]
0x18005f067  test    bpl, bpl
0x18005f06a  jz      short loc_18005F083
0x18005f06c  cmp     eax, 4
0x18005f06f  jz      loc_18005F16A
0x18005f075  lea     rcx, [rbx+10h]
0x18005f079  mov     rdx, r14
0x18005f07c  call    ??4?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)
0x18005f081  jmp     short loc_18005F0A9
0x18005f083  cmp     eax, 3
0x18005f086  jz      loc_18005F16A
0x18005f08c  mov     eax, [rbx+8]
0x18005f08f  cmp     eax, 4
0x18005f092  jz      loc_18005F16A
0x18005f098  mov     eax, [rbx+8]
0x18005f09b  cmp     eax, r15d
0x18005f09e  jnz     short loc_18005F0A9
0x18005f0a0  test    dil, dil
0x18005f0a3  jz      loc_18005F16A
0x18005f0a9  test    dil, dil
0x18005f0ac  jz      short loc_18005F0BC
0x18005f0ae  mov     dword ptr [rbx+8], 4
0x18005f0b5  mov     edi, 1
0x18005f0ba  jmp     short loc_18005F0DA
0x18005f0bc  mov     eax, [rbx+8]
0x18005f0bf  xor     edi, edi
0x18005f0c1  cmp     eax, 1
0x18005f0c4  cmovz   edi, r15d
0x18005f0c8  mov     [rbx+8], r15d
0x18005f0cc  lea     rcx, [rbx+160h]
0x18005f0d3  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x18005f0d9  nop
0x18005f0da  mov     rcx, rsi; _Mtx_t
0x18005f0dd  call    cs:__imp__Mtx_unlock
0x18005f0e3  sub     edi, 1
0x18005f0e6  jz      short loc_18005F107
0x18005f0e8  cmp     edi, 1
0x18005f0eb  jnz     short loc_18005F166
0x18005f0ed  mov     rcx, [rbx+1E0h]
0x18005f0f4  test    rcx, rcx
0x18005f0f7  jz      short loc_18005F166
0x18005f0f9  mov     rax, [rcx]
0x18005f0fc  mov     rax, [rax+10h]
0x18005f100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f105  jmp     short loc_18005F166
0x18005f107  lea     rcx, [rbx+88h]; this
0x18005f10e  call    ?_Complete@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskCollectionBaseImpl::_Complete(void)
0x18005f113  cmp     qword ptr [rbx+70h], 0
0x18005f118  jz      short loc_18005F166
0x18005f11a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_0eca18b9299534febb6cd2c81392266d_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_0eca18b9299534febb6cd2c81392266d_,void,>::`vftable'
0x18005f121  mov     [rsp+0B8h+var_88], rax
0x18005f126  mov     [rsp+0B8h+var_80], rbx
0x18005f12b  lea     rax, [rsp+0B8h+var_88]
0x18005f130  mov     [rsp+0B8h+var_50], rax
0x18005f135  mov     edx, 10h
0x18005f13a  lea     rcx, [rsp+0B8h+var_88]
0x18005f13f  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18005f144  nop
0x18005f145  mov     rcx, [rsp+0B8h+var_50]
0x18005f14a  test    rcx, rcx
0x18005f14d  jz      short loc_18005F166
0x18005f14f  mov     rax, [rcx]
0x18005f152  lea     rdx, [rsp+0B8h+var_88]
0x18005f157  cmp     rcx, rdx
0x18005f15a  setnz   dl
0x18005f15d  mov     rax, [rax+20h]
0x18005f161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f166  mov     al, 1
0x18005f168  jmp     short loc_18005F175
0x18005f16a  mov     rcx, rsi; _Mtx_t
0x18005f16d  call    cs:__imp__Mtx_unlock
0x18005f173  xor     al, al
0x18005f175  mov     rcx, [rsp+0B8h+var_48]
0x18005f17a  xor     rcx, rsp; StackCookie
0x18005f17d  call    __security_check_cookie
0x18005f182  add     rsp, 88h
0x18005f189  pop     r15
0x18005f18b  pop     r14
0x18005f18d  pop     rdi
0x18005f18e  pop     rsi
0x18005f18f  pop     rbp
0x18005f190  pop     rbx
0x18005f191  retn
```
