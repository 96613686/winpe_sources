# CBlockHashGen::OnRun(_TP_CALLBACK_INSTANCE *)

- ea: `0x1800a1ac0`
- end: `0x1800a1c29`
- name: `?OnRun@CBlockHashGen@@EEAAXPEAU_TP_CALLBACK_INSTANCE@@@Z`
- size: `361`
- prototype: `void __fastcall(CBlockHashGen *__hidden this, struct _TP_CALLBACK_INSTANCE *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800082d0`
- `0x18000e58c`
- `0x1800a1ac0`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a1b26`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a1c05`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a1b26`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a1c05`
- `KERNEL32!GetCurrentThread` at `0x1800a1b18`
- `KERNEL32!GetCurrentThread` at `0x1800a1bf7`
- `KERNEL32!GetCurrentThread` at `0x1800a1b18`
- `KERNEL32!GetCurrentThread` at `0x1800a1bf7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CBlockHashGen::OnRun(CSegmentGenWaiter **this, struct _TP_CALLBACK_INSTANCE *a2)
{
  CBlockHashGen *v2; // rsi
  HANDLE CurrentThread; // rax
  __int64 (__fastcall ***v4)(_QWORD, __int64); // r14
  unsigned int **v5; // rdi
  unsigned int *v6; // rdi
  __int64 v7; // rax
  int v8; // r15d
  unsigned int *v9; // rbx
  HANDLE v10; // rax
  CSegmentGenWaiter *v11; // rbx
  int v12; // eax
  _BYTE *v13; // [rsp+30h] [rbp-38h]
  Exception *v14; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v17; // [rsp+80h] [rbp+18h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, __int64); // [rsp+88h] [rbp+20h] BYREF

  v2 = (CBlockHashGen *)this;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, WPP_be010a277ea839fa2e7c6f971aad6610_Traceguids);
  }
  v13 = (char *)v2 + 104;
  if ( *((_BYTE *)v2 + 104) )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, 0x10000);
  }
  try
  {
    v4 = (__int64 (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v2 + 10) + 40LL))(
                                                      *((_QWORD *)v2 + 10),
                                                      0,
                                                      0);
    v18 = v4;
    v5 = (unsigned int **)*((_QWORD *)v2 + 6);
    v9 = *v5;
    v6 = v5[1];
    v8 = 0;
    while ( v9 != v6 )
    {
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64), _QWORD, _QWORD))(*v4)[1])(
        v4,
        v9[3],
        *(_QWORD *)(*(_QWORD *)v9 + 16LL) + v9[2]);
      v8 += v9[3];
      v9 += 4;
    }
    v17 = 0;
    v7 = (*v4)[2](v4, (__int64)&v17);
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int))(**((_QWORD **)v2 + 8) + 8LL))(
      *((_QWORD *)v2 + 8),
      v7,
      v17,
      *((_QWORD *)v2 + 5),
      v8);
    std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(&v18);
  }
  catch ( Exception *v14 )
  {
    (*(void (__fastcall **)(CSegmentGenWaiter *))(*(_QWORD *)this[8] + 24LL))(this[8]);
    v11 = this[9];
    v12 = (*(__int64 (__fastcall **)(Exception *))(*(_QWORD *)v14 + 8LL))(v14);
    CSegmentGenWaiter::ReportFailure(v11, v12);
    v2 = (CBlockHashGen *)this;
  }
  catch ( std::bad_alloc )
  {
    (*(void (__fastcall **)(CSegmentGenWaiter *))(*(_QWORD *)this[8] + 24LL))(this[8]);
    CSegmentGenWaiter::ReportFailure(this[9], -2147024882);
    v2 = (CBlockHashGen *)this;
  }
  catch ( ... )
  {
    (*(void (__fastcall **)(CSegmentGenWaiter *))(*(_QWORD *)this[8] + 24LL))(this[8]);
    CSegmentGenWaiter::ReportFailure(this[9], -2147024122);
    v2 = (CBlockHashGen *)this;
  }
  if ( *v13 )
  {
    v10 = GetCurrentThread();
    SetThreadPriority(v10, 0x20000);
  }
  (**(void (__fastcall ***)(CBlockHashGen *, __int64))v2)(v2, 1);
}

```

## disassembly

```asm
0x1800a1ac0  mov     [rsp+arg_0], rcx
0x1800a1ac5  push    rbx
0x1800a1ac6  push    rsi
0x1800a1ac7  push    rdi
0x1800a1ac8  push    r14
0x1800a1aca  push    r15
0x1800a1acc  sub     rsp, 40h
0x1800a1ad0  mov     rsi, rcx
0x1800a1ad3  lea     rax, WPP_GLOBAL_Control
0x1800a1ada  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1ae1  cmp     rcx, rax
0x1800a1ae4  jz      short loc_1800A1B0A
0x1800a1ae6  test    byte ptr [rcx+6Ch], 1
0x1800a1aea  jz      short loc_1800A1B0A
0x1800a1aec  cmp     byte ptr [rcx+69h], 4
0x1800a1af0  jb      short loc_1800A1B0A
0x1800a1af2  mov     edx, 0Ch
0x1800a1af7  mov     r9, rsi
0x1800a1afa  lea     r8, WPP_be010a277ea839fa2e7c6f971aad6610_Traceguids
0x1800a1b01  mov     rcx, [rcx+60h]
0x1800a1b05  call    WPP_SF_q
0x1800a1b0a  lea     rax, [rsi+68h]
0x1800a1b0e  mov     [rsp+68h+var_38], rax
0x1800a1b13  cmp     byte ptr [rax], 0
0x1800a1b16  jz      short loc_1800A1B2D
0x1800a1b18  call    cs:__imp_GetCurrentThread
0x1800a1b1e  mov     rcx, rax; hThread
0x1800a1b21  mov     edx, 10000h; nPriority
0x1800a1b26  call    cs:__imp_SetThreadPriority
0x1800a1b2c  nop
0x1800a1b2d  mov     rcx, [rsi+50h]
0x1800a1b31  mov     rax, [rcx]
0x1800a1b34  xor     r8d, r8d
0x1800a1b37  xor     edx, edx
0x1800a1b39  mov     rax, [rax+28h]
0x1800a1b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1b42  mov     r14, rax
0x1800a1b45  mov     [rsp+68h+arg_18], rax
0x1800a1b4d  mov     rdi, [rsi+30h]
0x1800a1b51  mov     rbx, [rdi]
0x1800a1b54  mov     rdi, [rdi+8]
0x1800a1b58  xor     r15d, r15d
0x1800a1b5b  cmp     rbx, rdi
0x1800a1b5e  jnz     short loc_1800A1BBA
0x1800a1b60  mov     [rsp+68h+arg_10], 0
0x1800a1b6b  mov     rax, [r14]
0x1800a1b6e  lea     rdx, [rsp+68h+arg_10]
0x1800a1b76  mov     rcx, r14
0x1800a1b79  mov     rax, [rax+10h]
0x1800a1b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1b82  mov     r10, rax
0x1800a1b85  mov     rcx, [rsi+40h]
0x1800a1b89  mov     rdx, [rcx]
0x1800a1b8c  mov     rax, [rdx+8]
0x1800a1b90  mov     [rsp+68h+var_48], r15d
0x1800a1b95  mov     r9, [rsi+28h]
0x1800a1b99  mov     r8d, [rsp+68h+arg_10]
0x1800a1ba1  mov     rdx, r10
0x1800a1ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1ba9  nop
0x1800a1baa  lea     rcx, [rsp+68h+arg_18]
0x1800a1bb2  call    ??1?$auto_ptr@VCRepubCacheMigrateWorkItem@@@std@@QEAA@XZ; std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(void)
0x1800a1bb7  nop
0x1800a1bb8  jmp     short loc_1800A1BED
0x1800a1bba  mov     rcx, [r14]
0x1800a1bbd  mov     r8d, [rbx+8]
0x1800a1bc1  mov     rax, [rbx]
0x1800a1bc4  add     r8, [rax+10h]
0x1800a1bc8  mov     rax, [rcx+8]
0x1800a1bcc  mov     edx, [rbx+0Ch]
0x1800a1bcf  mov     rcx, r14
0x1800a1bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1bd7  add     r15d, [rbx+0Ch]
0x1800a1bdb  add     rbx, 10h
0x1800a1bdf  jmp     loc_1800A1B5B
0x1800a1be4  jmp     short loc_1800A1BE8
0x1800a1be6  jmp     short $+2
0x1800a1be8  mov     rsi, [rsp+68h+arg_0]
0x1800a1bed  mov     rax, [rsp+68h+var_38]
0x1800a1bf2  cmp     byte ptr [rax], 0
0x1800a1bf5  jz      short loc_1800A1C0B
0x1800a1bf7  call    cs:__imp_GetCurrentThread
0x1800a1bfd  mov     rcx, rax; hThread
0x1800a1c00  mov     edx, 20000h; nPriority
0x1800a1c05  call    cs:__imp_SetThreadPriority
0x1800a1c0b  mov     rax, [rsi]
0x1800a1c0e  mov     edx, 1
0x1800a1c13  mov     rcx, rsi
0x1800a1c16  mov     rax, [rax]
0x1800a1c19  add     rsp, 40h
0x1800a1c1d  pop     r15
0x1800a1c1f  pop     r14
0x1800a1c21  pop     rdi
0x1800a1c22  pop     rsi
0x1800a1c23  pop     rbx
0x1800a1c24  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
