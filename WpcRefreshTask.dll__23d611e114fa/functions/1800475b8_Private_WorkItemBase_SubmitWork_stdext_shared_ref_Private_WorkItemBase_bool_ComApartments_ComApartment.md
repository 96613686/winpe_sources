# Private::WorkItemBase::SubmitWork(stdext::shared_ref<Private::WorkItemBase>,bool,ComApartments::ComApartment)

- ea: `0x1800475b8`
- end: `0x18004782f`
- name: `?SubmitWork@WorkItemBase@Private@@SAXV?$shared_ref@VWorkItemBase@Private@@@stdext@@_NW4ComApartment@ComApartments@@@Z`
- size: `631`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180038bb4`
- `0x180038ce4`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x18000ecc0`
- `0x180035e0c`
- `0x180037750`
- `0x1800377c0`
- `0x180046890`
- `0x1800475b8`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800477cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800477cc`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180047711`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180047711`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Private::WorkItemBase::SubmitWork(_QWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  __int64 v4; // rax
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // rdx
  signed __int32 v8; // eax
  signed __int32 v9; // ett
  unsigned __int128 v10; // kr00_16
  __int64 v11; // r14
  _QWORD *v12; // rcx
  struct _TP_CALLBACK_ENVIRON_V3 *v13; // r8
  unsigned __int64 v14; // rsi
  volatile signed __int32 *v15; // rbx
  signed int LastError; // eax
  unsigned int v17; // ebx
  unsigned __int128 v18; // [rsp+20h] [rbp-79h] BYREF
  __int64 v19; // [rsp+30h] [rbp-69h] BYREF
  _QWORD *v20; // [rsp+38h] [rbp-61h]
  _QWORD *v21; // [rsp+40h] [rbp-59h]
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v23[64]; // [rsp+70h] [rbp-29h] BYREF

  v21 = a1;
  *(_BYTE *)(*a1 + 24LL) = 1;
  *(_DWORD *)(*a1 + 28LL) = 0;
  v2 = a1[1];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  v3 = *a1;
  v4 = a1[1];
  *(_QWORD *)(v3 + 48) = v3;
  v5 = *(volatile signed __int32 **)(v3 + 56);
  *(_QWORD *)(v3 + 56) = v4;
  if ( v5 )
  {
    if ( !_InterlockedDecrement(v5 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( !_InterlockedDecrement(v5 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  *(_QWORD *)&v18 = a1;
  ScopeGuard::ScopeGuard__lambda_db7cd3f6d2f340133d3914887c407899___(v23, &v18);
  v6 = *a1;
  v18 = 0;
  v7 = *(_QWORD *)(v6 + 40);
  if ( v7 )
  {
    v8 = *(_DWORD *)(v7 + 8);
    while ( v8 )
    {
      v9 = v8;
      v8 = _InterlockedCompareExchange((volatile signed __int32 *)(v7 + 8), v8 + 1, v8);
      if ( v9 == v8 )
      {
        v14 = *(_QWORD *)(v6 + 32);
        *(_QWORD *)&v18 = v14;
        *((_QWORD *)&v18 + 1) = *(_QWORD *)(v6 + 40);
        v10 = __PAIR128__(*((unsigned __int64 *)&v18 + 1), v14);
        goto LABEL_12;
      }
    }
  }
  v10 = v18;
LABEL_12:
  if ( (_QWORD)v10 )
  {
    v11 = *a1;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v10 + 88) + 48LL))(v10 + 88, &v19);
    v12 = v20;
    if ( *v20 )
    {
      *(_QWORD *)(*v20 + 80LL) = v11;
      v12 = v20;
    }
    *(_QWORD *)(v11 + 80) = 0;
    *(_QWORD *)(v11 + 88) = *v12;
    *v12 = v11;
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 24LL))(v19);
    v13 = (struct _TP_CALLBACK_ENVIRON_V3 *)(v10 + 8);
  }
  else
  {
    v13 = 0;
  }
  if ( !TrySubmitThreadpoolCallback(Private::WorkItemBase::WorkCallback, (PVOID)*a1, v13) )
  {
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids, v17);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v17);
    throw (ErrorCodeException *)pExceptionObject;
  }
  ScopeGuard::Dismiss((ScopeGuard *)v23);
  if ( *((_QWORD *)&v10 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v10 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (***((void (__fastcall ****)(_QWORD))&v10 + 1))(*((_QWORD *)&v10 + 1));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v10 + 1) + 12LL), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v10 + 1) + 8LL))(*((_QWORD *)&v10 + 1));
    }
  }
  ScopeGuard::~ScopeGuard((ScopeGuard *)v23);
  v15 = (volatile signed __int32 *)a1[1];
  if ( v15 && !_InterlockedDecrement(v15 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
    if ( !_InterlockedDecrement(v15 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
  }
}

```

## disassembly

```asm
0x1800475b8  push    rbp
0x1800475ba  push    rbx
0x1800475bb  push    rsi
0x1800475bc  push    rdi
0x1800475bd  push    r14
0x1800475bf  push    r15
0x1800475c1  lea     rbp, [rsp-2Fh]
0x1800475c6  sub     rsp, 0C8h
0x1800475cd  mov     rax, cs:__security_cookie
0x1800475d4  xor     rax, rsp
0x1800475d7  mov     [rbp+57h+var_40], rax
0x1800475db  mov     rdi, rcx
0x1800475de  mov     [rbp+57h+var_B0], rcx
0x1800475e2  mov     rax, [rcx]
0x1800475e5  mov     byte ptr [rax+18h], 1
0x1800475e9  mov     rax, [rcx]
0x1800475ec  mov     dword ptr [rax+1Ch], 0
0x1800475f3  mov     rax, [rcx+8]
0x1800475f7  test    rax, rax
0x1800475fa  jz      short loc_180047600
0x1800475fc  lock inc dword ptr [rax+8]
0x180047600  mov     rcx, [rcx]
0x180047603  mov     rax, [rdi+8]
0x180047607  mov     [rcx+30h], rcx
0x18004760b  mov     rbx, [rcx+38h]
0x18004760f  mov     [rcx+38h], rax
0x180047613  or      r15d, 0FFFFFFFFh
0x180047617  test    rbx, rbx
0x18004761a  jz      short loc_180047653
0x18004761c  mov     eax, r15d
0x18004761f  lock xadd [rbx+8], eax
0x180047624  add     eax, r15d
0x180047627  jnz     short loc_180047653
0x180047629  mov     rax, [rbx]
0x18004762c  mov     rcx, rbx
0x18004762f  mov     rax, [rax]
0x180047632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047637  mov     eax, r15d
0x18004763a  lock xadd [rbx+0Ch], eax
0x18004763f  add     eax, r15d
0x180047642  jnz     short loc_180047653
0x180047644  mov     rax, [rbx]
0x180047647  mov     rcx, rbx
0x18004764a  mov     rax, [rax+8]
0x18004764e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047653  mov     qword ptr [rbp+57h+var_D0], rdi
0x180047657  lea     rdx, [rbp+57h+var_D0]
0x18004765b  lea     rcx, [rbp+57h+var_80]
0x18004765f  call    ScopeGuard__ScopeGuard__lambda_db7cd3f6d2f340133d3914887c407899___
0x180047664  nop
0x180047665  mov     rbx, [rdi]
0x180047668  xorps   xmm0, xmm0
0x18004766b  movdqu  [rbp+57h+var_D0], xmm0
0x180047670  mov     rdx, [rbx+28h]
0x180047674  test    rdx, rdx
0x180047677  jz      short loc_18004768C
0x180047679  mov     eax, [rdx+8]
0x18004767c  jmp     short loc_180047688
0x18004767e  lea     ecx, [rax+1]
0x180047681  lock cmpxchg [rdx+8], ecx
0x180047686  jz      short loc_1800476F2
0x180047688  test    eax, eax
0x18004768a  jnz     short loc_18004767E
0x18004768c  mov     rsi, qword ptr [rbp+57h+var_D0]
0x180047690  mov     rbx, qword ptr [rbp+57h+var_D0+8]
0x180047694  test    rsi, rsi
0x180047697  jz      short loc_180047704
0x180047699  mov     r14, [rdi]
0x18004769c  lea     rcx, [rsi+58h]
0x1800476a0  mov     rax, [rcx]
0x1800476a3  lea     rdx, [rbp+57h+var_C0]
0x1800476a7  mov     rax, [rax+30h]
0x1800476ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476b0  mov     rcx, [rbp+57h+var_B8]
0x1800476b4  mov     rax, [rcx]
0x1800476b7  test    rax, rax
0x1800476ba  jz      short loc_1800476C4
0x1800476bc  mov     [rax+50h], r14
0x1800476c0  mov     rcx, [rbp+57h+var_B8]
0x1800476c4  mov     qword ptr [r14+50h], 0
0x1800476cc  mov     rax, [rcx]
0x1800476cf  mov     [r14+58h], rax
0x1800476d3  mov     [rcx], r14
0x1800476d6  mov     rcx, [rbp+57h+var_C0]
0x1800476da  test    rcx, rcx
0x1800476dd  jz      short loc_1800476EC
0x1800476df  mov     rax, [rcx]
0x1800476e2  mov     rax, [rax+18h]
0x1800476e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476eb  nop
0x1800476ec  lea     r8, [rsi+8]
0x1800476f0  jmp     short loc_180047707
0x1800476f2  mov     rsi, [rbx+20h]
0x1800476f6  mov     qword ptr [rbp+57h+var_D0], rsi
0x1800476fa  mov     rbx, [rbx+28h]
0x1800476fe  mov     qword ptr [rbp+57h+var_D0+8], rbx
0x180047702  jmp     short loc_180047694
0x180047704  xor     r8d, r8d; pcbe
0x180047707  mov     rdx, [rdi]; pv
0x18004770a  lea     rcx, ?WorkCallback@WorkItemBase@Private@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180047711  call    cs:__imp_TrySubmitThreadpoolCallback
0x180047717  test    eax, eax
0x180047719  jz      loc_1800477CC
0x18004771f  lea     rcx, [rbp+57h+var_80]; this
0x180047723  call    ?Dismiss@ScopeGuard@@QEAAXXZ; ScopeGuard::Dismiss(void)
0x180047728  nop
0x180047729  test    rbx, rbx
0x18004772c  jz      short loc_180047766
0x18004772e  mov     eax, r15d
0x180047731  lock xadd [rbx+8], eax
0x180047736  add     eax, r15d
0x180047739  jnz     short loc_180047766
0x18004773b  mov     rax, [rbx]
0x18004773e  mov     rcx, rbx
0x180047741  mov     rax, [rax]
0x180047744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047749  mov     eax, r15d
0x18004774c  lock xadd [rbx+0Ch], eax
0x180047751  add     eax, r15d
0x180047754  jnz     short loc_180047766
0x180047756  mov     rax, [rbx]
0x180047759  mov     rcx, rbx
0x18004775c  mov     rax, [rax+8]
0x180047760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047765  nop
0x180047766  lea     rcx, [rbp+57h+var_80]; this
0x18004776a  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x18004776f  nop
0x180047770  mov     rbx, [rdi+8]
0x180047774  test    rbx, rbx
0x180047777  jz      short loc_1800477B0
0x180047779  mov     eax, r15d
0x18004777c  lock xadd [rbx+8], eax
0x180047781  add     eax, r15d
0x180047784  jnz     short loc_1800477B0
0x180047786  mov     rax, [rbx]
0x180047789  mov     rcx, rbx
0x18004778c  mov     rax, [rax]
0x18004778f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047794  mov     eax, r15d
0x180047797  lock xadd [rbx+0Ch], eax
0x18004779c  add     eax, r15d
0x18004779f  jnz     short loc_1800477B0
0x1800477a1  mov     rax, [rbx]
0x1800477a4  mov     rcx, rbx
0x1800477a7  mov     rax, [rax+8]
0x1800477ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477b0  mov     rcx, [rbp+57h+var_40]
0x1800477b4  xor     rcx, rsp; StackCookie
0x1800477b7  call    __security_check_cookie
0x1800477bc  add     rsp, 0C8h
0x1800477c3  pop     r15
0x1800477c5  pop     r14
0x1800477c7  pop     rdi
0x1800477c8  pop     rsi
0x1800477c9  pop     rbx
0x1800477ca  pop     rbp
0x1800477cb  retn
0x1800477cc  call    cs:__imp_GetLastError
0x1800477d2  nop
0x1800477d3  mov     ebx, eax
0x1800477d5  test    eax, eax
0x1800477d7  jle     short loc_1800477E2
0x1800477d9  movzx   ebx, ax
0x1800477dc  or      ebx, 80070000h
0x1800477e2  lea     rax, WPP_GLOBAL_Control
0x1800477e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800477f0  cmp     rcx, rax
0x1800477f3  jz      short loc_180047813
0x1800477f5  test    byte ptr [rcx+1Ch], 1
0x1800477f9  jz      short loc_180047813
0x1800477fb  mov     edx, 0Bh
0x180047800  mov     r9d, ebx
0x180047803  lea     r8, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids
0x18004780a  mov     rcx, [rcx+10h]
0x18004780e  call    WPP_SF_d
0x180047813  mov     edx, ebx; int
0x180047815  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180047819  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004781e  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180047825  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180047829  call    _CxxThrowException_0
```
