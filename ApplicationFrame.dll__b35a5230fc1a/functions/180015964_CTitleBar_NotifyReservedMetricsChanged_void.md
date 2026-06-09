# CTitleBar::_NotifyReservedMetricsChanged(void)

- ea: `0x180015964`
- end: `0x180015c4b`
- name: `?_NotifyReservedMetricsChanged@CTitleBar@@AEAAJXZ`
- size: `743`
- prototype: `__int64 __fastcall(CTitleBar *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016f14`
- `0x180057f98`
- `0x180059ae0`

## callees

- `0x180004c98`
- `0x180015964`
- `0x180024184`
- `0x180040270`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015b32`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015b48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015c11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015b32`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015b48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015c11`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015a4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015a4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800159d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800159d5`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800159c9`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800159c9`
- `TWINAPI!__imp_QueryWindowService` at `0x1800159f8`
- `TWINAPI!__imp_QueryWindowService` at `0x1800159f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CTitleBar::_NotifyReservedMetricsChanged(CTitleBar *this)
{
  DWORD WindowThreadProcessId; // ebx
  __int64 (__fastcall ***v4)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v5)(_QWORD, GUID *, __int64 *); // rdi
  int v6; // eax
  unsigned int v7; // ebx
  double v8; // xmm8_8
  double v9; // xmm6_8
  double v10; // xmm7_8
  int v11; // eax
  unsigned int v12; // r14d
  __int64 v13; // rcx
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v15; // rcx
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v17; // rcx
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rcx
  int v19; // [rsp+20h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  __int64 v21; // [rsp+90h] [rbp+30h] BYREF
  __int64 (__fastcall ***v22)(_QWORD, GUID *, __int64 *); // [rsp+98h] [rbp+38h] BYREF
  char *v23; // [rsp+A0h] [rbp+40h]

  if ( *((_BYTE *)this + 558) || *((_BYTE *)this + 576) )
    return 0;
  v22 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v22);
  WindowThreadProcessId = GetWindowThreadProcessId(*((HWND *)this + 63), 0);
  if ( GetCurrentThreadId() == WindowThreadProcessId )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1347,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)0x80070057LL,
      v19);
  if ( (int)QueryWindowService(
              *((_QWORD *)this + 63),
              &GUID_006d35e3_e1f1_431b_9508_29b96926ac53,
              &GUID_006d35e3_e1f1_431b_9508_29b96926ac53,
              &v22) < 0 )
  {
LABEL_16:
    v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v22;
    if ( v22 )
    {
      v22 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v14)[2])(v14);
    }
    return 0;
  }
  v21 = 0;
  v4 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v22;
  v5 = **v22;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v21);
  v6 = v5(v4, &GUID_6e470d39_e79f_453c_92ef_6310edefd440, &v21);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11A8,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)(unsigned int)v6,
      v19);
    v15 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v22;
    if ( v22 )
    {
      v22 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v16)[2])(v16);
    }
    return v7;
  }
  else
  {
    AcquireSRWLockShared((PSRWLOCK)this + 191);
    v23 = (char *)this + 1528;
    v8 = *((double *)this + 195);
    v9 = *((double *)this + 196);
    v10 = *((double *)this + 197);
    if ( this != (CTitleBar *)-1528LL )
    {
      ReleaseSRWLockShared((PSRWLOCK)this + 191);
      v23 = 0;
    }
    if ( MEMORY[8] == v8 && MEMORY[0x10] == v9 && MEMORY[0x18] == v10 )
      goto LABEL_14;
    v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 56LL))(v21);
    v12 = v11;
    if ( v11 >= 0 )
    {
      MEMORY[8] = *(_QWORD *)&v8;
      MEMORY[0x10] = *(_QWORD *)&v9;
      MEMORY[0x18] = *(_QWORD *)&v10;
LABEL_14:
      v13 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      goto LABEL_16;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11B1,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)(unsigned int)v11,
      v19);
    v17 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v22;
    if ( v22 )
    {
      v22 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v18)[2])(v18);
    }
    return v12;
  }
}

```

## disassembly

```asm
0x180015964  push    rbp
0x180015966  push    rbx
0x180015967  push    rsi
0x180015968  push    rdi
0x180015969  push    r14
0x18001596b  mov     rbp, rsp
0x18001596e  sub     rsp, 60h
0x180015972  movaps  [rsp+60h+var_10], xmm6
0x180015977  movaps  [rsp+60h+var_20], xmm7
0x18001597c  movaps  [rsp+60h+var_30], xmm8
0x180015982  mov     rsi, rcx
0x180015985  cmp     byte ptr [rcx+22Eh], 0
0x18001598c  jz      loc_180015C19
0x180015992  xor     eax, eax
0x180015994  movaps  xmm6, [rsp+60h+var_10]
0x180015999  movaps  xmm7, [rsp+60h+var_20]
0x18001599e  movaps  xmm8, [rsp+60h+var_30]
0x1800159a4  add     rsp, 60h
0x1800159a8  pop     r14
0x1800159aa  pop     rdi
0x1800159ab  pop     rsi
0x1800159ac  pop     rbx
0x1800159ad  pop     rbp
0x1800159ae  retn
0x1800159af  mov     [rbp+arg_8], 0
0x1800159b7  lea     rcx, [rbp+arg_8]
0x1800159bb  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800159c0  xor     edx, edx; lpdwProcessId
0x1800159c2  mov     rcx, [rsi+1F8h]; hWnd
0x1800159c9  call    cs:__imp_GetWindowThreadProcessId
0x1800159cf  mov     ebx, eax
0x1800159d1  mov     rdi, [rbp+28h]
0x1800159d5  call    cs:__imp_GetCurrentThreadId
0x1800159db  cmp     eax, ebx
0x1800159dd  jz      loc_180015C2B
0x1800159e3  lea     r9, [rbp+arg_8]
0x1800159e7  lea     rdx, _GUID_006d35e3_e1f1_431b_9508_29b96926ac53
0x1800159ee  mov     r8, rdx
0x1800159f1  mov     rcx, [rsi+1F8h]
0x1800159f8  call    cs:__imp_QueryWindowService
0x1800159fe  test    eax, eax
0x180015a00  js      loc_180015B0C
0x180015a06  mov     [rbp+arg_0], 0
0x180015a0e  mov     rbx, [rbp+arg_8]
0x180015a12  mov     rax, [rbx]
0x180015a15  mov     rdi, [rax]
0x180015a18  lea     rcx, [rbp+arg_0]
0x180015a1c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180015a21  lea     r8, [rbp+arg_0]
0x180015a25  lea     rdx, _GUID_6e470d39_e79f_453c_92ef_6310edefd440
0x180015a2c  mov     rcx, rbx
0x180015a2f  mov     rax, rdi
0x180015a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a37  mov     ebx, eax
0x180015a39  test    eax, eax
0x180015a3b  js      loc_180015B50
0x180015a41  lea     rbx, [rsi+5F8h]
0x180015a48  mov     rcx, rbx; SRWLock
0x180015a4b  call    cs:__imp_AcquireSRWLockShared
0x180015a51  mov     [rbp+arg_10], rbx
0x180015a55  movsd   xmm8, qword ptr [rsi+618h]
0x180015a5e  movsd   xmm6, qword ptr [rsi+620h]
0x180015a66  movsd   xmm7, qword ptr [rsi+628h]
0x180015a6e  test    rbx, rbx
0x180015a71  jnz     loc_180015B2F
0x180015a77  mov     rdi, rbx
0x180015a7a  movsd   xmm0, qword ptr [rsi+600h]
0x180015a82  ucomisd xmm0, xmm8
0x180015a87  jp      short loc_180015AAB
0x180015a89  jnz     short loc_180015AAB
0x180015a8b  movsd   xmm0, qword ptr [rsi+608h]
0x180015a93  ucomisd xmm0, xmm6
0x180015a97  jp      short loc_180015AAB
0x180015a99  jnz     short loc_180015AAB
0x180015a9b  movsd   xmm0, qword ptr [rsi+610h]
0x180015aa3  ucomisd xmm0, xmm7
0x180015aa7  jp      short loc_180015AAB
0x180015aa9  jz      short loc_180015AE9
0x180015aab  mov     rcx, [rbp+arg_0]
0x180015aaf  mov     rax, [rcx]
0x180015ab2  movaps  xmm3, xmm7
0x180015ab5  movaps  xmm2, xmm6
0x180015ab8  movaps  xmm1, xmm8
0x180015abc  mov     rax, [rax+38h]
0x180015ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ac5  mov     r14d, eax
0x180015ac8  test    eax, eax
0x180015aca  js      loc_180015BAC
0x180015ad0  movsd   qword ptr [rsi+600h], xmm8
0x180015ad9  movsd   qword ptr [rsi+608h], xmm6
0x180015ae1  movsd   qword ptr [rsi+610h], xmm7
0x180015ae9  test    rdi, rdi
0x180015aec  jnz     short loc_180015B45
0x180015aee  mov     rcx, [rbp+arg_0]
0x180015af2  test    rcx, rcx
0x180015af5  jz      short loc_180015B0C
0x180015af7  mov     [rbp+arg_0], 0
0x180015aff  mov     rax, [rcx]
0x180015b02  mov     rax, [rax+10h]
0x180015b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b0b  nop
0x180015b0c  mov     rcx, [rbp+arg_8]
0x180015b10  test    rcx, rcx
0x180015b13  jz      short loc_180015B2A
0x180015b15  mov     [rbp+arg_8], 0
0x180015b1d  mov     rax, [rcx]
0x180015b20  mov     rax, [rax+10h]
0x180015b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b29  nop
0x180015b2a  jmp     loc_180015992
0x180015b2f  mov     rcx, rbx; SRWLock
0x180015b32  call    cs:__imp_ReleaseSRWLockShared
0x180015b38  xor     ebx, ebx
0x180015b3a  mov     [rbp+arg_10], rbx
0x180015b3e  xor     edi, edi
0x180015b40  jmp     loc_180015A7A
0x180015b45  mov     rcx, rbx; SRWLock
0x180015b48  call    cs:__imp_ReleaseSRWLockShared
0x180015b4e  jmp     short loc_180015AEE
0x180015b50  mov     rcx, [rbp+28h]; this
0x180015b54  mov     r9d, ebx; char *
0x180015b57  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180015b5e  mov     edx, 11A8h; void *
0x180015b63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015b68  nop
0x180015b69  mov     rcx, [rbp+arg_0]
0x180015b6d  test    rcx, rcx
0x180015b70  jz      short loc_180015B87
0x180015b72  mov     [rbp+arg_0], 0
0x180015b7a  mov     rax, [rcx]
0x180015b7d  mov     rax, [rax+10h]
0x180015b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b86  nop
0x180015b87  mov     rcx, [rbp+arg_8]
0x180015b8b  test    rcx, rcx
0x180015b8e  jz      short loc_180015BA5
0x180015b90  mov     [rbp+arg_8], 0
0x180015b98  mov     rax, [rcx]
0x180015b9b  mov     rax, [rax+10h]
0x180015b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ba4  nop
0x180015ba5  mov     eax, ebx
0x180015ba7  jmp     loc_180015994
0x180015bac  mov     rcx, [rbp+28h]; this
0x180015bb0  mov     r9d, r14d; char *
0x180015bb3  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180015bba  mov     edx, 11B1h; void *
0x180015bbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015bc4  nop
0x180015bc5  test    rdi, rdi
0x180015bc8  jnz     short loc_180015C0E
0x180015bca  mov     rcx, [rbp+arg_0]
0x180015bce  test    rcx, rcx
0x180015bd1  jz      short loc_180015BE8
0x180015bd3  mov     [rbp+arg_0], 0
0x180015bdb  mov     rax, [rcx]
0x180015bde  mov     rax, [rax+10h]
0x180015be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015be7  nop
0x180015be8  mov     rcx, [rbp+arg_8]
0x180015bec  test    rcx, rcx
0x180015bef  jz      short loc_180015C06
0x180015bf1  mov     [rbp+arg_8], 0
0x180015bf9  mov     rax, [rcx]
0x180015bfc  mov     rax, [rax+10h]
0x180015c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c05  nop
0x180015c06  mov     eax, r14d
0x180015c09  jmp     loc_180015994
0x180015c0e  mov     rcx, rbx; SRWLock
0x180015c11  call    cs:__imp_ReleaseSRWLockShared
0x180015c17  jmp     short loc_180015BCA
0x180015c19  cmp     byte ptr [rcx+240h], 0
0x180015c20  jnz     loc_180015992
0x180015c26  jmp     loc_1800159AF
0x180015c2b  mov     r9d, 80070057h; char *
0x180015c31  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180015c38  mov     edx, 1347h; void *
0x180015c3d  mov     rcx, rdi; this
0x180015c40  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015c45  jmp     loc_1800159E3
```
