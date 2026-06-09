# _lambda_0f17ac5bb141cf2bc7352f8cf74b5f7d_::operator()(Windows::Foundation::IAsyncOperation<bool> *,Windows::Foundation::AsyncStatus)

- ea: `0x1400161c4`
- end: `0x1400163c8`
- name: `??R_lambda_0f17ac5bb141cf2bc7352f8cf74b5f7d_@@QEAA@PE$AAU?$IAsyncOperation@_N@Foundation@Windows@@W4AsyncStatus@23@@Z`
- size: `516`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140017ae0`

## callees

- `0x1400086b0`
- `0x1400161c4`
- `0x14001aa8c`
- `0x14001cda8`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140016335`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140016335`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001631c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001632b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001631c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001632b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001630b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001630b`
- `wincorlib!?ReCreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x14001627e`
- `wincorlib!?ReCreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x14001627e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall _lambda_0f17ac5bb141cf2bc7352f8cf74b5f7d_::operator()(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r9
  __int64 v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rdi
  int v8; // eax
  int v9; // eax
  __int64 Exception; // rsi
  int v11; // eax
  struct _RTL_CRITICAL_SECTION *v12; // rcx
  volatile signed __int32 *v13; // rbx
  unsigned int v14; // [rsp+30h] [rbp-58h] BYREF
  __int64 v15; // [rsp+38h] [rbp-50h]
  __int64 v16; // [rsp+40h] [rbp-48h]
  char v17; // [rsp+48h] [rbp-40h] BYREF
  __int64 v18; // [rsp+50h] [rbp-38h] BYREF
  _BYTE v19[8]; // [rsp+58h] [rbp-30h] BYREF

  v3 = a2;
  v5 = *a1;
  if ( (_DWORD)a3 == 2 )
  {
    v6 = v5 + 24;
    LOBYTE(v6) = 1;
    (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v5 + 8LL))(v5, v6, 0, 0, v5 + 24);
  }
  else if ( (_DWORD)a3 == 3 )
  {
    v7 = 0;
    v18 = 0;
    if ( a2 )
    {
      v8 = (**(__int64 (__fastcall ***)(__int64, char *, __int64 *))a2)(
             a2,
             _uuidof__AUIAsyncInfo_Foundation_Windows__,
             &v18);
      if ( v8 < 0 )
        __abi_WinRTraiseException(v8);
      v7 = v18;
    }
    v15 = v7;
    v14 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *, __int64, __int64))(*(_QWORD *)v7 + 64LL))(v7, &v14, a3, v3);
    if ( v9 < 0 )
      __abi_WinRTraiseException(v9);
    Exception = Platform::Exception::ReCreateException(v14);
    v16 = Exception;
    Concurrency::details::_Task_impl_base::_CancelWithException((_QWORD *)v5, Exception);
    if ( Exception )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)Exception + 16LL))(Exception);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  else
  {
    v19[0] = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 64LL))(a2, v19);
    if ( v11 < 0 )
      __abi_WinRTraiseException(v11);
    *(_BYTE *)(v5 + 160) = v19[0];
    if ( (char *)(v5 + 176) != &v17 )
      *(_QWORD *)(v5 + 176) = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 40));
    v12 = (struct _RTL_CRITICAL_SECTION *)(v5 + 40);
    if ( *(_DWORD *)(v5 + 16) == 4 )
    {
      LeaveCriticalSection(v12);
    }
    else
    {
      *(_DWORD *)(v5 + 16) = 3;
      LeaveCriticalSection(v12);
      SetEvent(*(HANDLE *)(v5 + 8));
      Concurrency::details::_Task_impl_base::_RunTaskContinuations((Concurrency::details::_Task_impl_base *)v5);
    }
  }
  v13 = (volatile signed __int32 *)a1[1];
  a1[1] = 0;
  *a1 = 0;
  if ( v13 && _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
    if ( !_InterlockedDecrement(v13 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
  }
}

```

## disassembly

```asm
0x1400161c4  mov     [rsp+arg_10], rbx
0x1400161c9  push    rsi
0x1400161ca  push    rdi
0x1400161cb  push    r14
0x1400161cd  sub     rsp, 70h
0x1400161d1  mov     rax, cs:__security_cookie
0x1400161d8  xor     rax, rsp
0x1400161db  mov     [rsp+88h+var_28], rax
0x1400161e0  mov     r9, rdx
0x1400161e3  mov     r14, rcx
0x1400161e6  mov     rbx, [rcx]
0x1400161e9  cmp     r8d, 2
0x1400161ed  jnz     short loc_140016214
0x1400161ef  mov     rax, [rbx]
0x1400161f2  lea     rdx, [rbx+18h]
0x1400161f6  mov     [rsp+88h+var_68], rdx
0x1400161fb  xor     r9d, r9d
0x1400161fe  xor     r8d, r8d
0x140016201  mov     dl, 1
0x140016203  mov     rcx, rbx
0x140016206  mov     rax, [rax+8]
0x14001620a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001620f  jmp     loc_140016343
0x140016214  cmp     r8d, 3
0x140016218  jnz     loc_1400162C1
0x14001621e  xor     edi, edi
0x140016220  mov     [rsp+88h+var_38], rdi
0x140016225  test    r9, r9
0x140016228  jz      short loc_140016251
0x14001622a  mov     rax, [rdx]
0x14001622d  lea     r8, [rsp+88h+var_38]
0x140016232  lea     rdx, __uuidof_?AUIAsyncInfo@Foundation@Windows@@
0x140016239  mov     rcx, r9
0x14001623c  mov     rax, [rax]
0x14001623f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016244  test    eax, eax
0x140016246  js      loc_1400163B8
0x14001624c  mov     rdi, [rsp+88h+var_38]
0x140016251  mov     [rsp+88h+var_50], rdi
0x140016256  mov     [rsp+88h+var_58], 0
0x14001625e  mov     rax, [rdi]
0x140016261  lea     rdx, [rsp+88h+var_58]
0x140016266  mov     rcx, rdi
0x140016269  mov     rax, [rax+40h]
0x14001626d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016272  test    eax, eax
0x140016274  js      loc_1400163C0
0x14001627a  mov     ecx, [rsp+88h+var_58]
0x14001627e  call    cs:__imp_?ReCreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::ReCreateException(int)
0x140016284  mov     rsi, rax
0x140016287  mov     [rsp+88h+var_48], rax
0x14001628c  mov     rdx, rax
0x14001628f  mov     rcx, rbx
0x140016292  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NPE$AAVException@Platform@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(Platform::Exception *)
0x140016297  nop
0x140016298  test    rsi, rsi
0x14001629b  jz      short loc_1400162AD
0x14001629d  mov     rdx, [rsi]
0x1400162a0  mov     rcx, rsi
0x1400162a3  mov     rax, [rdx+10h]
0x1400162a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400162ac  nop
0x1400162ad  mov     rax, [rdi]
0x1400162b0  mov     rcx, rdi
0x1400162b3  mov     rax, [rax+10h]
0x1400162b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400162bc  jmp     loc_140016343
0x1400162c1  mov     [rsp+88h+var_30], 0
0x1400162c6  mov     rax, [rdx]
0x1400162c9  lea     rdx, [rsp+88h+var_30]
0x1400162ce  mov     rcx, r9
0x1400162d1  mov     rax, [rax+40h]
0x1400162d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400162da  test    eax, eax
0x1400162dc  js      loc_1400163B0
0x1400162e2  mov     al, [rsp+88h+var_30]
0x1400162e6  mov     [rbx+0A0h], al
0x1400162ec  lea     rax, [rbx+0B0h]
0x1400162f3  lea     rcx, [rsp+88h+var_40]
0x1400162f8  cmp     rax, rcx
0x1400162fb  jz      short loc_140016304
0x1400162fd  mov     qword ptr [rax], 0
0x140016304  lea     rdi, [rbx+28h]
0x140016308  mov     rcx, rdi; lpCriticalSection
0x14001630b  call    cs:__imp_EnterCriticalSection
0x140016311  mov     eax, [rbx+10h]
0x140016314  mov     rcx, rdi; lpCriticalSection
0x140016317  cmp     eax, 4
0x14001631a  jnz     short loc_140016324
0x14001631c  call    cs:__imp_LeaveCriticalSection
0x140016322  jmp     short loc_140016343
0x140016324  mov     dword ptr [rbx+10h], 3
0x14001632b  call    cs:__imp_LeaveCriticalSection
0x140016331  mov     rcx, [rbx+8]; hEvent
0x140016335  call    cs:__imp_SetEvent
0x14001633b  mov     rcx, rbx; this
0x14001633e  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x140016343  mov     rbx, [r14+8]
0x140016347  mov     qword ptr [r14+8], 0
0x14001634f  mov     qword ptr [r14], 0
0x140016356  test    rbx, rbx
0x140016359  jz      short loc_140016392
0x14001635b  or      edi, 0FFFFFFFFh
0x14001635e  mov     eax, edi
0x140016360  lock xadd [rbx+8], eax
0x140016365  add     eax, edi
0x140016367  jnz     short loc_140016392
0x140016369  mov     rax, [rbx]
0x14001636c  mov     rcx, rbx
0x14001636f  mov     rax, [rax]
0x140016372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016377  mov     eax, edi
0x140016379  lock xadd [rbx+0Ch], eax
0x14001637e  add     eax, edi
0x140016380  jnz     short loc_140016392
0x140016382  mov     rax, [rbx]
0x140016385  mov     rcx, rbx
0x140016388  mov     rax, [rax+8]
0x14001638c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016391  nop
0x140016392  mov     rcx, [rsp+88h+var_28]
0x140016397  xor     rcx, rsp; StackCookie
0x14001639a  call    __security_check_cookie
0x14001639f  mov     rbx, [rsp+88h+arg_10]
0x1400163a7  add     rsp, 70h
0x1400163ab  pop     r14
0x1400163ad  pop     rdi
0x1400163ae  pop     rsi
0x1400163af  retn
0x1400163b0  mov     ecx, eax; int
0x1400163b2  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1400163b8  mov     ecx, eax; int
0x1400163ba  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1400163c0  mov     ecx, eax; int
0x1400163c2  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
