# Concurrency::task_bool_::_ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync_::_Continue

- ea: `0x14001afc0`
- end: `0x14001b238`
- name: `Concurrency::task_bool_::_ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync_::_Continue`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1400167e4`

## callees

- `0x1400016e8`
- `0x140001710`
- `0x1400017a0`
- `0x14001afc0`
- `0x14001cda8`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001b1b2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001b1b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001b199`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001b1a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001b199`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001b1a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001b188`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001b188`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall Concurrency::task_bool_::_ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync_::_Continue(
        __int64 a1)
{
  __int64 v2; // rbx
  char *v3; // rax
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  __int64 v6; // rax
  _QWORD *v7; // rdx
  _BYTE *v8; // rdx
  _BYTE *v9; // rdx
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  _BYTE *v11; // rcx
  _BYTE *v12; // rdx
  _BYTE *v13; // rdx
  _BYTE v14[24]; // [rsp+28h] [rbp-51h] BYREF
  _BYTE *v15; // [rsp+40h] [rbp-39h]
  _BYTE *v16; // [rsp+48h] [rbp-31h]
  _BYTE *v17; // [rsp+50h] [rbp-29h]
  _BYTE v18[24]; // [rsp+58h] [rbp-21h] BYREF
  _BYTE *v19; // [rsp+70h] [rbp-9h]
  _BYTE v20[24]; // [rsp+78h] [rbp-1h] BYREF
  _BYTE *v21; // [rsp+90h] [rbp+17h]
  _QWORD *v22; // [rsp+98h] [rbp+1Fh]
  char v23; // [rsp+A0h] [rbp+27h] BYREF
  _BYTE v24[8]; // [rsp+A8h] [rbp+2Fh] BYREF

  v2 = *(_QWORD *)(a1 + 48);
  v16 = v18;
  v19 = 0;
  v3 = (char *)operator new(0x20u);
  if ( !v3 )
    std::_Xbad_alloc();
  *(_QWORD *)v3 = &off_1400492F0;
  *(_OWORD *)(v3 + 8) = *(_OWORD *)(a1 + 80);
  v19 = v3;
  v16 = v18;
  v17 = v14;
  v15 = 0;
  v15 = (_BYTE *)off_1400492F0();
  v21 = 0;
  v4 = operator new(0x30u);
  v5 = v4;
  if ( !v4 )
    std::_Xbad_alloc();
  v17 = v4;
  *v4 = &std::_Func_impl<std::_Callable_obj<_lambda_5113901b37f823c98e9e2d5d7c1b7cd5_,0>,std::allocator<std::_Func_class<unsigned char,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,unsigned char,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
  v22 = v4 + 1;
  v4[4] = 0;
  if ( v15 )
  {
    if ( v15 == v14 )
      v7 = v4 + 1;
    else
      v7 = 0;
    v6 = (**(__int64 (__fastcall ***)(_BYTE *, _QWORD *))v15)(v15, v7);
  }
  else
  {
    v6 = 0;
  }
  v5[4] = v6;
  v21 = v5;
  if ( v15 )
  {
    v8 = v14;
    LOBYTE(v8) = v15 != v14;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v15 + 32LL))(v15, v8);
    v15 = 0;
  }
  if ( v19 )
  {
    v9 = v18;
    LOBYTE(v9) = v19 != v18;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v19 + 32LL))(v19, v9);
    v19 = 0;
  }
  v24[0] = *(_BYTE *)(*(_QWORD *)(a1 + 64) + 160LL);
  if ( !v21 )
    std::_Xbad_function_call();
  *(_BYTE *)(v2 + 160) = (*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v21 + 16LL))(v21, v24);
  if ( (char *)(v2 + 176) != &v23 )
    *(_QWORD *)(v2 + 176) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 40));
  v10 = (struct _RTL_CRITICAL_SECTION *)(v2 + 40);
  if ( *(_DWORD *)(v2 + 16) == 4 )
  {
    LeaveCriticalSection(v10);
  }
  else
  {
    *(_DWORD *)(v2 + 16) = 3;
    LeaveCriticalSection(v10);
    SetEvent(*(HANDLE *)(v2 + 8));
    Concurrency::details::_Task_impl_base::_RunTaskContinuations((Concurrency::details::_Task_impl_base *)v2);
  }
  v11 = v21;
  if ( v21 )
  {
    v12 = v20;
    LOBYTE(v12) = v21 != v20;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v21 + 32LL))(v21, v12);
    v11 = 0;
    v21 = 0;
  }
  if ( v11 )
  {
    v13 = v20;
    LOBYTE(v13) = v11 != v20;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v11 + 32LL))(v11, v13);
  }
}

```

## disassembly

```asm
0x14001afc0  mov     [rsp-8+arg_8], rbx
0x14001afc5  mov     [rsp-8+arg_10], rsi
0x14001afca  push    rbp
0x14001afcb  push    rdi
0x14001afcc  push    r14
0x14001afce  lea     rbp, [rsp-47h]
0x14001afd3  sub     rsp, 0C0h
0x14001afda  mov     rax, cs:__security_cookie
0x14001afe1  xor     rax, rsp
0x14001afe4  mov     [rbp+57h+var_20], rax
0x14001afe8  mov     r14, rcx
0x14001afeb  mov     [rbp+57h+var_B0], 0
0x14001aff2  mov     rbx, [rcx+30h]
0x14001aff6  lea     rax, [rbp+57h+var_78]
0x14001affa  mov     [rbp+57h+var_88], rax
0x14001affe  mov     [rbp+57h+var_60], 0
0x14001b006  mov     ecx, 20h ; ' '; Size
0x14001b00b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001b010  test    rax, rax
0x14001b013  jz      loc_14001B22C
0x14001b019  lea     rcx, off_1400492F0
0x14001b020  mov     [rax], rcx
0x14001b023  movups  xmm0, xmmword ptr [r14+50h]
0x14001b028  movdqu  xmmword ptr [rax+8], xmm0
0x14001b02d  mov     [rbp+57h+var_60], rax
0x14001b031  lea     rcx, [rbp+57h+var_78]
0x14001b035  mov     [rbp+57h+var_88], rcx
0x14001b039  lea     rcx, [rbp+57h+var_A8]
0x14001b03d  mov     [rbp+57h+var_80], rcx
0x14001b041  mov     [rbp+57h+var_90], 0
0x14001b049  mov     r8, cs:off_1400492F0
0x14001b050  lea     rcx, [rbp+57h+var_78]
0x14001b054  cmp     rax, rcx
0x14001b057  mov     rcx, rax
0x14001b05a  mov     rax, r8
0x14001b05d  jnz     short loc_14001B065
0x14001b05f  lea     rdx, [rbp+57h+var_A8]
0x14001b063  jmp     short loc_14001B067
0x14001b065  xor     edx, edx
0x14001b067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b06c  nop
0x14001b06d  mov     [rbp+57h+var_90], rax
0x14001b071  mov     [rbp+57h+var_40], 0
0x14001b079  mov     ecx, 30h ; '0'; Size
0x14001b07e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001b083  mov     rdi, rax
0x14001b086  test    rax, rax
0x14001b089  jz      loc_14001B232
0x14001b08f  mov     [rbp+57h+var_80], rax
0x14001b093  lea     rax, ??_7?$_Func_impl@U?$_Callable_obj@V_lambda_5113901b37f823c98e9e2d5d7c1b7cd5_@@$0A@@std@@V?$allocator@V?$_Func_class@E_NU_Nil@std@@U12@U12@U12@U12@U12@@std@@@2@E_NU_Nil@2@U42@U42@U42@U42@U42@@std@@6B@; const std::_Func_impl<std::_Callable_obj<_lambda_5113901b37f823c98e9e2d5d7c1b7cd5_,0>,std::allocator<std::_Func_class<uchar,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,uchar,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable'
0x14001b09a  mov     [rdi], rax
0x14001b09d  lea     rsi, [rdi+8]
0x14001b0a1  mov     [rbp+57h+var_38], rsi
0x14001b0a5  mov     qword ptr [rsi+18h], 0
0x14001b0ad  mov     rcx, [rbp+57h+var_90]
0x14001b0b1  test    rcx, rcx
0x14001b0b4  jnz     short loc_14001B0BA
0x14001b0b6  xor     eax, eax
0x14001b0b8  jmp     short loc_14001B0D6
0x14001b0ba  mov     rax, [rcx]
0x14001b0bd  mov     rax, [rax]
0x14001b0c0  lea     rdx, [rbp+57h+var_A8]
0x14001b0c4  cmp     rcx, rdx
0x14001b0c7  jnz     short loc_14001B0CE
0x14001b0c9  mov     rdx, rsi
0x14001b0cc  jmp     short loc_14001B0D0
0x14001b0ce  xor     edx, edx
0x14001b0d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b0d5  nop
0x14001b0d6  mov     [rsi+18h], rax
0x14001b0da  mov     [rbp+57h+var_40], rdi
0x14001b0de  mov     [rbp+57h+var_B0], 2
0x14001b0e5  mov     rcx, [rbp+57h+var_90]
0x14001b0e9  test    rcx, rcx
0x14001b0ec  jz      short loc_14001B10C
0x14001b0ee  mov     rax, [rcx]
0x14001b0f1  lea     rdx, [rbp+57h+var_A8]
0x14001b0f5  cmp     rcx, rdx
0x14001b0f8  setnz   dl
0x14001b0fb  mov     rax, [rax+20h]
0x14001b0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b104  mov     [rbp+57h+var_90], 0
0x14001b10c  mov     [rbp+57h+var_B0], 1
0x14001b113  mov     rcx, [rbp+57h+var_60]
0x14001b117  test    rcx, rcx
0x14001b11a  jz      short loc_14001B13A
0x14001b11c  mov     rax, [rcx]
0x14001b11f  lea     rdx, [rbp+57h+var_78]
0x14001b123  cmp     rcx, rdx
0x14001b126  setnz   dl
0x14001b129  mov     rax, [rax+20h]
0x14001b12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b132  mov     [rbp+57h+var_60], 0
0x14001b13a  mov     rax, [r14+40h]
0x14001b13e  mov     cl, [rax+0A0h]
0x14001b144  mov     [rbp+57h+var_28], cl
0x14001b147  mov     rcx, [rbp+57h+var_40]
0x14001b14b  test    rcx, rcx
0x14001b14e  jz      loc_14001B226
0x14001b154  mov     rax, [rcx]
0x14001b157  lea     rdx, [rbp+57h+var_28]
0x14001b15b  mov     rax, [rax+10h]
0x14001b15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b164  mov     [rbx+0A0h], al
0x14001b16a  lea     rax, [rbx+0B0h]
0x14001b171  lea     rcx, [rbp+57h+var_30]
0x14001b175  cmp     rax, rcx
0x14001b178  jz      short loc_14001B181
0x14001b17a  mov     qword ptr [rax], 0
0x14001b181  lea     rdi, [rbx+28h]
0x14001b185  mov     rcx, rdi; lpCriticalSection
0x14001b188  call    cs:__imp_EnterCriticalSection
0x14001b18e  mov     eax, [rbx+10h]
0x14001b191  mov     rcx, rdi; lpCriticalSection
0x14001b194  cmp     eax, 4
0x14001b197  jnz     short loc_14001B1A1
0x14001b199  call    cs:__imp_LeaveCriticalSection
0x14001b19f  jmp     short loc_14001B1C1
0x14001b1a1  mov     dword ptr [rbx+10h], 3
0x14001b1a8  call    cs:__imp_LeaveCriticalSection
0x14001b1ae  mov     rcx, [rbx+8]; hEvent
0x14001b1b2  call    cs:__imp_SetEvent
0x14001b1b8  mov     rcx, rbx; this
0x14001b1bb  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x14001b1c0  nop
0x14001b1c1  mov     rcx, [rbp+57h+var_40]
0x14001b1c5  test    rcx, rcx
0x14001b1c8  jz      short loc_14001B1E6
0x14001b1ca  mov     rax, [rcx]
0x14001b1cd  lea     rdx, [rbp+57h+var_58]
0x14001b1d1  cmp     rcx, rdx
0x14001b1d4  setnz   dl
0x14001b1d7  mov     rax, [rax+20h]
0x14001b1db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b1e0  xor     ecx, ecx
0x14001b1e2  mov     [rbp+57h+var_40], rcx
0x14001b1e6  test    rcx, rcx
0x14001b1e9  jz      short loc_14001B202
0x14001b1eb  mov     rax, [rcx]
0x14001b1ee  lea     rdx, [rbp+57h+var_58]
0x14001b1f2  cmp     rcx, rdx
0x14001b1f5  setnz   dl
0x14001b1f8  mov     rax, [rax+20h]
0x14001b1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b201  nop
0x14001b202  mov     rcx, [rbp+57h+var_20]
0x14001b206  xor     rcx, rsp; StackCookie
0x14001b209  call    __security_check_cookie
0x14001b20e  lea     r11, [rsp+0D0h+var_10]
0x14001b216  mov     rbx, [r11+28h]
0x14001b21a  mov     rsi, [r11+30h]
0x14001b21e  mov     rsp, r11
0x14001b221  pop     r14
0x14001b223  pop     rdi
0x14001b224  pop     rbp
0x14001b225  retn
0x14001b226  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x14001b22c  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x14001b232  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
