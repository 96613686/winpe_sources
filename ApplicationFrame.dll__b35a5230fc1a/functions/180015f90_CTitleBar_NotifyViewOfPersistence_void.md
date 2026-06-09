# CTitleBar::_NotifyViewOfPersistence(void)

- ea: `0x180015f90`
- end: `0x180016145`
- name: `?_NotifyViewOfPersistence@CTitleBar@@AEAAJXZ`
- size: `437`
- prototype: `int(CTitleBar *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180057ee8`
- `0x180057f98`

## callees

- `0x180004c98`
- `0x180015f90`
- `0x180024184`
- `0x180040270`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015fc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015fc8`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180015fbc`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180015fbc`
- `TWINAPI!__imp_QueryWindowService` at `0x180015feb`
- `TWINAPI!__imp_QueryWindowService` at `0x180015feb`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CTitleBar::_NotifyViewOfPersistence(HWND *this)
{
  DWORD WindowThreadProcessId; // ebx
  __int64 (__fastcall ***v3)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rdi
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rcx
  int v11; // eax
  __int64 v12; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v15; // [rsp+40h] [rbp+20h] BYREF
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp+28h] BYREF

  v16 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v16);
  WindowThreadProcessId = GetWindowThreadProcessId(this[63], 0);
  if ( GetCurrentThreadId() == WindowThreadProcessId )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1347,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)0x80070057LL,
      savedregs);
  if ( (int)QueryWindowService(
              this[63],
              &GUID_006d35e3_e1f1_431b_9508_29b96926ac53,
              &GUID_006d35e3_e1f1_431b_9508_29b96926ac53,
              &v16) < 0 )
    goto LABEL_4;
  v15 = 0;
  v5 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v16;
  v6 = **v16;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v15);
  v7 = v6(v5, &GUID_6e470d39_e79f_453c_92ef_6310edefd440, &v15);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x136B,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)(unsigned int)v7,
      savedregs);
    v9 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v16;
    if ( v16 )
    {
      v16 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v10)[2])(v10);
    }
    return v8;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 88LL))(v15, *((unsigned __int8 *)this + 566));
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x136D,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)(unsigned int)v11,
      savedregs);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v15);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v16);
    return v8;
  }
  v12 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
LABEL_4:
  v3 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v16;
  if ( v16 )
  {
    v16 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v3)[2])(v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180015f90  mov     [rsp-18h+arg_10], rbx
0x180015f95  push    rbp
0x180015f96  push    rsi
0x180015f97  push    rdi; int
0x180015f98  mov     rbp, rsp
0x180015f9b  sub     rsp, 20h
0x180015f9f  mov     rsi, rcx
0x180015fa2  mov     [rbp+arg_8], 0
0x180015faa  lea     rcx, [rbp+arg_8]
0x180015fae  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180015fb3  xor     edx, edx; lpdwProcessId
0x180015fb5  mov     rcx, [rsi+1F8h]; hWnd
0x180015fbc  call    cs:__imp_GetWindowThreadProcessId
0x180015fc2  mov     ebx, eax
0x180015fc4  mov     rdi, [rbp+18h]
0x180015fc8  call    cs:__imp_GetCurrentThreadId
0x180015fce  cmp     eax, ebx
0x180015fd0  jz      loc_1800160F5
0x180015fd6  lea     r9, [rbp+arg_8]
0x180015fda  lea     rdx, _GUID_006d35e3_e1f1_431b_9508_29b96926ac53
0x180015fe1  mov     r8, rdx
0x180015fe4  mov     rcx, [rsi+1F8h]
0x180015feb  call    cs:__imp_QueryWindowService
0x180015ff1  test    eax, eax
0x180015ff3  jns     short loc_180016022
0x180015ff5  mov     rcx, [rbp+arg_8]
0x180015ff9  test    rcx, rcx
0x180015ffc  jz      short loc_180016013
0x180015ffe  mov     [rbp+arg_8], 0
0x180016006  mov     rax, [rcx]
0x180016009  mov     rax, [rax+10h]
0x18001600d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016012  nop
0x180016013  xor     eax, eax
0x180016015  mov     rbx, [rsp+20h+arg_10]
0x18001601a  add     rsp, 20h
0x18001601e  pop     rdi
0x18001601f  pop     rsi
0x180016020  pop     rbp
0x180016021  retn
0x180016022  mov     [rbp+arg_0], 0
0x18001602a  mov     rbx, [rbp+arg_8]
0x18001602e  mov     rax, [rbx]
0x180016031  mov     rdi, [rax]
0x180016034  lea     rcx, [rbp+arg_0]
0x180016038  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18001603d  lea     r8, [rbp+arg_0]
0x180016041  lea     rdx, _GUID_6e470d39_e79f_453c_92ef_6310edefd440
0x180016048  mov     rcx, rbx
0x18001604b  mov     rax, rdi
0x18001604e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016053  mov     ebx, eax
0x180016055  test    eax, eax
0x180016057  jns     short loc_1800160B5
0x180016059  mov     rcx, [rbp+18h]; this
0x18001605d  mov     r9d, eax; char *
0x180016060  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180016067  mov     edx, 136Bh; void *
0x18001606c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016071  nop
0x180016072  mov     rcx, [rbp+arg_0]
0x180016076  test    rcx, rcx
0x180016079  jz      short loc_180016090
0x18001607b  mov     [rbp+arg_0], 0
0x180016083  mov     rax, [rcx]
0x180016086  mov     rax, [rax+10h]
0x18001608a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001608f  nop
0x180016090  mov     rcx, [rbp+arg_8]
0x180016094  test    rcx, rcx
0x180016097  jz      short loc_1800160AE
0x180016099  mov     [rbp+arg_8], 0
0x1800160a1  mov     rax, [rcx]
0x1800160a4  mov     rax, [rax+10h]
0x1800160a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160ad  nop
0x1800160ae  mov     eax, ebx
0x1800160b0  jmp     loc_180016015
0x1800160b5  mov     rcx, [rbp+arg_0]
0x1800160b9  mov     rax, [rcx]
0x1800160bc  movzx   edx, byte ptr [rsi+236h]
0x1800160c3  mov     rax, [rax+58h]
0x1800160c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160cc  mov     ebx, eax
0x1800160ce  test    eax, eax
0x1800160d0  js      short loc_180016114
0x1800160d2  mov     rcx, [rbp+arg_0]
0x1800160d6  test    rcx, rcx
0x1800160d9  jz      short loc_1800160F0
0x1800160db  mov     [rbp+arg_0], 0
0x1800160e3  mov     rax, [rcx]
0x1800160e6  mov     rax, [rax+10h]
0x1800160ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160ef  nop
0x1800160f0  jmp     loc_180015FF5
0x1800160f5  mov     r9d, 80070057h; char *
0x1800160fb  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180016102  mov     edx, 1347h; void *
0x180016107  mov     rcx, rdi; this
0x18001610a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001610f  jmp     loc_180015FD6
0x180016114  mov     rcx, [rbp+18h]; this
0x180016118  mov     r9d, ebx; char *
0x18001611b  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180016122  mov     edx, 136Dh; void *
0x180016127  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001612c  nop
0x18001612d  lea     rcx, [rbp+arg_0]
0x180016131  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180016136  nop
0x180016137  lea     rcx, [rbp+arg_8]
0x18001613b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180016140  jmp     loc_1800160AE
```
