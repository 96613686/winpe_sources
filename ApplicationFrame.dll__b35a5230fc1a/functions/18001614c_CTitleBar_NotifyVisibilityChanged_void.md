# CTitleBar::_NotifyVisibilityChanged(void)

- ea: `0x18001614c`
- end: `0x18001630b`
- name: `?_NotifyVisibilityChanged@CTitleBar@@AEAAJXZ`
- size: `447`
- prototype: `__int64 __fastcall(CTitleBar *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180057f98`
- `0x180059c10`

## callees

- `0x180004c98`
- `0x18001614c`
- `0x180024184`
- `0x180033320`
- `0x180040270`
- `0x18005660c`
- `0x180057160`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800161a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800161a0`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180016194`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180016194`
- `TWINAPI!__imp_QueryWindowService` at `0x1800161c3`
- `TWINAPI!__imp_QueryWindowService` at `0x1800161c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTitleBar::_NotifyVisibilityChanged(CTitleBar *this)
{
  DWORD WindowThreadProcessId; // ebx
  __int64 (__fastcall ***v4)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v5)(_QWORD, GUID *, __int64 *); // rdi
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rcx
  int v15[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  bool v17; // [rsp+50h] [rbp+20h] BYREF
  __int64 v18; // [rsp+58h] [rbp+28h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp+30h] BYREF

  if ( *((_BYTE *)this + 558) || *((_BYTE *)this + 576) )
    return 0;
  v19 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v19);
  WindowThreadProcessId = GetWindowThreadProcessId(*((HWND *)this + 63), 0);
  if ( GetCurrentThreadId() == WindowThreadProcessId )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1347,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)0x80070057LL,
      v15[0]);
  if ( (int)QueryWindowService(
              *((_QWORD *)this + 63),
              &GUID_006d35e3_e1f1_431b_9508_29b96926ac53,
              &GUID_006d35e3_e1f1_431b_9508_29b96926ac53,
              &v19) < 0 )
  {
LABEL_14:
    v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v19;
    if ( v19 )
    {
      v19 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v14)[2])(v14);
    }
    return 0;
  }
  v18 = 0;
  v4 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v19;
  v5 = **v19;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v18);
  v6 = v5(v4, &GUID_6e470d39_e79f_453c_92ef_6310edefd440, &v18);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v17 = *((_DWORD *)this + 138) == 0;
    v10 = lambda_1a980e294fe5b227acc771db7133a118_::_lambda_1a980e294fe5b227acc771db7133a118_(v15, &v18, &v17);
    Windows::Internal::ComTaskPool::QueueTask__lambda_1a980e294fe5b227acc771db7133a118___(
      v12,
      v11,
      *((unsigned int *)this + 374),
      v10);
    Microsoft::WRL::ComPtr<IApplicationViewArrangePosition>::~ComPtr<IApplicationViewArrangePosition>(v15);
    v13 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    goto LABEL_14;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11C1,
    (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
    (const char *)(unsigned int)v6,
    v15[0]);
  v8 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v19;
  if ( v19 )
  {
    v19 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v9)[2])(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18001614c  mov     [rsp-18h+arg_18], rbx
0x180016151  push    rbp
0x180016152  push    rsi
0x180016153  push    rdi
0x180016154  mov     rbp, rsp
0x180016157  sub     rsp, 30h
0x18001615b  mov     rsi, rcx
0x18001615e  cmp     byte ptr [rcx+22Eh], 0
0x180016165  jz      loc_1800162DA
0x18001616b  xor     eax, eax
0x18001616d  mov     rbx, [rsp+30h+arg_18]
0x180016172  add     rsp, 30h
0x180016176  pop     rdi
0x180016177  pop     rsi
0x180016178  pop     rbp
0x180016179  retn
0x18001617a  mov     [rbp+arg_10], 0
0x180016182  lea     rcx, [rbp+arg_10]
0x180016186  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18001618b  xor     edx, edx; lpdwProcessId
0x18001618d  mov     rcx, [rsi+1F8h]; hWnd
0x180016194  call    cs:__imp_GetWindowThreadProcessId
0x18001619a  mov     ebx, eax
0x18001619c  mov     rdi, [rbp+18h]
0x1800161a0  call    cs:__imp_GetCurrentThreadId
0x1800161a6  cmp     eax, ebx
0x1800161a8  jz      loc_1800162EC
0x1800161ae  lea     r9, [rbp+arg_10]
0x1800161b2  lea     rdx, _GUID_006d35e3_e1f1_431b_9508_29b96926ac53
0x1800161b9  mov     r8, rdx
0x1800161bc  mov     rcx, [rsi+1F8h]
0x1800161c3  call    cs:__imp_QueryWindowService
0x1800161c9  test    eax, eax
0x1800161cb  js      loc_1800162B7
0x1800161d1  mov     [rbp+arg_8], 0
0x1800161d9  mov     rbx, [rbp+arg_10]
0x1800161dd  mov     rax, [rbx]
0x1800161e0  mov     rdi, [rax]
0x1800161e3  lea     rcx, [rbp+arg_8]
0x1800161e7  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800161ec  lea     r8, [rbp+arg_8]
0x1800161f0  lea     rdx, _GUID_6e470d39_e79f_453c_92ef_6310edefd440
0x1800161f7  mov     rcx, rbx
0x1800161fa  mov     rax, rdi
0x1800161fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016202  mov     ebx, eax
0x180016204  test    eax, eax
0x180016206  jns     short loc_180016264
0x180016208  mov     rcx, [rbp+18h]; this
0x18001620c  mov     r9d, eax; char *
0x18001620f  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180016216  mov     edx, 11C1h; void *
0x18001621b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016220  nop
0x180016221  mov     rcx, [rbp+arg_8]
0x180016225  test    rcx, rcx
0x180016228  jz      short loc_18001623F
0x18001622a  mov     [rbp+arg_8], 0
0x180016232  mov     rax, [rcx]
0x180016235  mov     rax, [rax+10h]
0x180016239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001623e  nop
0x18001623f  mov     rcx, [rbp+arg_10]
0x180016243  test    rcx, rcx
0x180016246  jz      short loc_18001625D
0x180016248  mov     [rbp+arg_10], 0
0x180016250  mov     rax, [rcx]
0x180016253  mov     rax, [rax+10h]
0x180016257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001625c  nop
0x18001625d  mov     eax, ebx
0x18001625f  jmp     loc_18001616D
0x180016264  cmp     dword ptr [rsi+228h], 0
0x18001626b  setz    [rbp+arg_0]
0x18001626f  lea     r8, [rbp+arg_0]
0x180016273  lea     rdx, [rbp+arg_8]
0x180016277  lea     rcx, [rbp+var_10]
0x18001627b  call    _lambda_1a980e294fe5b227acc771db7133a118____lambda_1a980e294fe5b227acc771db7133a118_
0x180016280  mov     r9, rax
0x180016283  mov     r8d, [rsi+5D8h]
0x18001628a  call    Windows__Internal__ComTaskPool__QueueTask__lambda_1a980e294fe5b227acc771db7133a118___
0x18001628f  lea     rcx, [rbp+var_10]
0x180016293  call    ??1?$ComPtr@UIApplicationViewArrangePosition@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IApplicationViewArrangePosition>::~ComPtr<IApplicationViewArrangePosition>(void)
0x180016298  nop
0x180016299  mov     rcx, [rbp+arg_8]
0x18001629d  test    rcx, rcx
0x1800162a0  jz      short loc_1800162B7
0x1800162a2  mov     [rbp+arg_8], 0
0x1800162aa  mov     rax, [rcx]
0x1800162ad  mov     rax, [rax+10h]
0x1800162b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162b6  nop
0x1800162b7  mov     rcx, [rbp+arg_10]
0x1800162bb  test    rcx, rcx
0x1800162be  jz      short loc_1800162D5
0x1800162c0  mov     [rbp+arg_10], 0
0x1800162c8  mov     rax, [rcx]
0x1800162cb  mov     rax, [rax+10h]
0x1800162cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162d4  nop
0x1800162d5  jmp     loc_18001616B
0x1800162da  cmp     byte ptr [rcx+240h], 0
0x1800162e1  jnz     loc_18001616B
0x1800162e7  jmp     loc_18001617A
0x1800162ec  mov     r9d, 80070057h; char *
0x1800162f2  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x1800162f9  mov     edx, 1347h; void *
0x1800162fe  mov     rcx, rdi; this
0x180016301  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016306  jmp     loc_1800161AE
```
