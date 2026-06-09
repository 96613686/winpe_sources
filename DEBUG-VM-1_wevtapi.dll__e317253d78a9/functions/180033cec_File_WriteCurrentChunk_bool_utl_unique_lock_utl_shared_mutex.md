# File::WriteCurrentChunk(bool,utl::unique_lock<utl::shared_mutex> &)

- ea: `0x180033cec`
- end: `0x180033fa1`
- name: `?WriteCurrentChunk@File@@AEAAK_NAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z`
- size: `693`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x18003218c`
- `0x1800322f0`
- `0x1800323a4`
- `0x180032794`
- `0x180032bb8`
- `0x180032f54`

## callees

- `0x18000a0d0`
- `0x180023548`
- `0x180033cec`
- `0x180034818`
- `0x180034848`
- `0x180034fc0`
- `0x180034fe4`
- `0x180035278`
- `0x180035884`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033f02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033f02`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033f15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033f15`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180033db6`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180033db6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180033f81`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180033f81`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180033f0b`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180033f0b`

## pseudocode

```c
__int64 __fastcall File::WriteCurrentChunk(__int64 a1, char a2, __int64 a3)
{
  HANDLE *v3; // rbx
  HANDLE v7; // rdx
  unsigned int v8; // eax
  unsigned int v9; // edi
  void *v11; // rcx
  unsigned int v12; // ebp
  unsigned int v13; // r12d
  unsigned int v14; // r15d
  HANDLE v15; // rbx
  unsigned int v16; // r8d
  void *v17; // rdx
  FileView *v18; // rcx
  unsigned int v19; // r9d
  struct _TP_TIMER *v20; // rcx
  _BYTE v21[8]; // [rsp+20h] [rbp-78h] BYREF
  __int64 v22; // [rsp+28h] [rbp-70h]
  __int64 v23; // [rsp+30h] [rbp-68h]
  unsigned int v24; // [rsp+40h] [rbp-58h]
  char v25; // [rsp+49h] [rbp-4Fh]

  v3 = (HANDLE *)(a1 + 672);
  if ( *(_BYTE *)(a1 + 831) )
  {
    v23 = *(_QWORD *)(a1 + 144);
    v24 = 128;
    v22 = -1;
    v25 = 0;
    FileView::SetPointers((FileView *)v21);
    v7 = *v3;
    v22 = 0;
    v8 = FileView::ActualWrite((FileView *)v21, v7, 0, v24);
    v9 = v8;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, v8);
      }
      FileView::~FileView((FileView *)v21);
      return v9;
    }
    FlushFileBuffers(*v3);
    *(_BYTE *)(a1 + 831) = 0;
    v11 = *(void **)(a1 + 144);
    *(_QWORD *)(a1 + 144) = 0;
    if ( v11 )
      operator delete(v11, 0x80u);
    FileView::~FileView((FileView *)v21);
  }
  if ( !*(_BYTE *)(a1 + 827) )
  {
    *(_DWORD *)(a1 + 812) = 0;
    return 0;
  }
  if ( !*(_QWORD *)(a1 + 176) )
    return 0;
  WriteFileView::UpdateBothCRCValues((WriteFileView *)(a1 + 152));
  *(_BYTE *)(a1 + 838) = 1;
  if ( a2 )
  {
    if ( *(_BYTE *)(a1 + 829) )
      utl::unique_lock<utl::shared_mutex>::unlock(a3);
    v12 = FileView::ActualWrite((FileView *)(a1 + 160), *v3, 0, *(_DWORD *)(a1 + 192));
    if ( *(_BYTE *)(a1 + 829) )
      utl::unique_lock<utl::shared_mutex>::lock(a3);
    if ( !v12 )
    {
      *(_DWORD *)(a1 + 812) = 0;
      *(_BYTE *)(a1 + 827) = 0;
    }
    goto LABEL_32;
  }
  v13 = *(_DWORD *)(a1 + 812);
  v14 = *(_DWORD *)(*(_QWORD *)(a1 + 160) + 48LL);
  if ( *(_BYTE *)(a1 + 829) )
    utl::unique_lock<utl::shared_mutex>::unlock(a3);
  v15 = *v3;
  v16 = 0;
  v17 = v15;
  v18 = (FileView *)(a1 + 160);
  if ( !v13 )
  {
    v19 = v14;
LABEL_27:
    v12 = FileView::ActualWrite(v18, v17, v16, v19);
    goto LABEL_28;
  }
  v12 = FileView::ActualWrite((FileView *)(a1 + 160), v15, 0, 0x200u);
  if ( !v12 )
  {
    v16 = v13;
    v19 = v14 - v13;
    v17 = v15;
    v18 = (FileView *)(a1 + 160);
    goto LABEL_27;
  }
LABEL_28:
  if ( *(_BYTE *)(a1 + 829) )
    utl::unique_lock<utl::shared_mutex>::lock(a3);
  if ( !v12 )
    *(_DWORD *)(a1 + 812) = v14;
LABEL_32:
  *(_BYTE *)(a1 + 838) = 0;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 752));
  WakeAllConditionVariable((PCONDITION_VARIABLE)(a1 + 744));
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 752));
  if ( !v12 )
  {
    v20 = *(struct _TP_TIMER **)(a1 + 656);
    if ( v20 && *(_BYTE *)(a1 + 837) )
    {
      *(_BYTE *)(a1 + 837) = 0;
      SetThreadpoolTimer(v20, 0, 0, 0);
    }
    *(_BYTE *)(a1 + 826) = 0;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180033cec  mov     r11, rsp
0x180033cef  push    rbx
0x180033cf0  push    rbp
0x180033cf1  push    rsi
0x180033cf2  push    rdi
0x180033cf3  push    r12
0x180033cf5  push    r13
0x180033cf7  push    r14
0x180033cf9  push    r15
0x180033cfb  sub     rsp, 58h
0x180033cff  xor     r13d, r13d
0x180033d02  lea     rbx, [rcx+2A0h]
0x180033d09  mov     r14, r8
0x180033d0c  mov     bpl, dl
0x180033d0f  mov     rsi, rcx
0x180033d12  cmp     [rcx+33Fh], r13b
0x180033d19  jz      loc_180033DE8
0x180033d1f  mov     rax, [rcx+90h]
0x180033d26  mov     r15d, 80h
0x180033d2c  lea     rcx, [r11-78h]; this
0x180033d30  mov     [r11-68h], rax
0x180033d34  mov     [r11-58h], r15d
0x180033d38  mov     qword ptr [r11-70h], 0FFFFFFFFFFFFFFFFh
0x180033d40  mov     [r11-4Fh], r13b
0x180033d44  call    ?SetPointers@FileView@@QEAAXXZ; FileView::SetPointers(void)
0x180033d49  mov     rdx, [rbx]; void *
0x180033d4c  lea     rcx, [rsp+98h+var_78]; this
0x180033d51  mov     r9d, [rsp+98h+var_58]; unsigned int
0x180033d56  xor     r8d, r8d; unsigned int
0x180033d59  mov     [rsp+98h+var_70], r13
0x180033d5e  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x180033d63  mov     edi, eax
0x180033d65  test    eax, eax
0x180033d67  jz      short loc_180033DB3
0x180033d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d70  lea     rdx, WPP_GLOBAL_Control
0x180033d77  cmp     rcx, rdx
0x180033d7a  jz      short loc_180033DA2
0x180033d7c  test    dword ptr [rcx+1Ch], 8000h
0x180033d83  jz      short loc_180033DA2
0x180033d85  cmp     byte ptr [rcx+19h], 2
0x180033d89  jb      short loc_180033DA2
0x180033d8b  mov     rcx, [rcx+10h]
0x180033d8f  lea     edx, [r13+2Ah]
0x180033d93  mov     r9d, eax
0x180033d96  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180033d9d  call    WPP_SF_D
0x180033da2  lea     rcx, [rsp+98h+var_78]; this
0x180033da7  call    ??1FileView@@QEAA@XZ; FileView::~FileView(void)
0x180033dac  mov     eax, edi
0x180033dae  jmp     loc_180033F90
0x180033db3  mov     rcx, [rbx]; hFile
0x180033db6  call    cs:__imp_FlushFileBuffers
0x180033dbc  mov     [rsi+33Fh], r13b
0x180033dc3  mov     rcx, [rsi+90h]; void *
0x180033dca  mov     [rsi+90h], r13
0x180033dd1  test    rcx, rcx
0x180033dd4  jz      short loc_180033DDE
0x180033dd6  mov     rdx, r15; unsigned __int64
0x180033dd9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180033dde  lea     rcx, [rsp+98h+var_78]; this
0x180033de3  call    ??1FileView@@QEAA@XZ; FileView::~FileView(void)
0x180033de8  cmp     [rsi+33Bh], r13b
0x180033def  jnz     short loc_180033DFD
0x180033df1  mov     [rsi+32Ch], r13d
0x180033df8  jmp     loc_180033F8E
0x180033dfd  lea     rdi, [rsi+98h]
0x180033e04  cmp     [rdi+18h], r13
0x180033e08  jz      loc_180033F8E
0x180033e0e  mov     rcx, rdi; this
0x180033e11  call    ?UpdateBothCRCValues@WriteFileView@@QEAAXXZ; WriteFileView::UpdateBothCRCValues(void)
0x180033e16  add     rdi, 8
0x180033e1a  mov     byte ptr [rsi+346h], 1
0x180033e21  test    bpl, bpl
0x180033e24  jz      short loc_180033E74
0x180033e26  cmp     [rsi+33Dh], r13b
0x180033e2d  jz      short loc_180033E37
0x180033e2f  mov     rcx, r14
0x180033e32  call    ?unlock@?$unique_lock@Vshared_mutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::shared_mutex>::unlock(void)
0x180033e37  mov     r9d, [rdi+20h]; unsigned int
0x180033e3b  xor     r8d, r8d; unsigned int
0x180033e3e  mov     rdx, [rbx]; void *
0x180033e41  mov     rcx, rdi; this
0x180033e44  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x180033e49  mov     ebp, eax
0x180033e4b  cmp     [rsi+33Dh], r13b
0x180033e52  jz      short loc_180033E5C
0x180033e54  mov     rcx, r14
0x180033e57  call    ?lock@?$unique_lock@Vshared_mutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::shared_mutex>::lock(void)
0x180033e5c  test    ebp, ebp
0x180033e5e  jnz     loc_180033EF0
0x180033e64  mov     [rsi+32Ch], r13d
0x180033e6b  mov     [rsi+33Bh], r13b
0x180033e72  jmp     short loc_180033EF0
0x180033e74  mov     rax, [rsi+0A0h]
0x180033e7b  mov     r12d, [rsi+32Ch]
0x180033e82  mov     r15d, [rax+30h]
0x180033e86  cmp     [rsi+33Dh], r13b
0x180033e8d  jz      short loc_180033E97
0x180033e8f  mov     rcx, r14
0x180033e92  call    ?unlock@?$unique_lock@Vshared_mutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::shared_mutex>::unlock(void)
0x180033e97  mov     rbx, [rbx]
0x180033e9a  xor     r8d, r8d; unsigned int
0x180033e9d  mov     rdx, rbx; void *
0x180033ea0  mov     rcx, rdi; this
0x180033ea3  test    r12d, r12d
0x180033ea6  jnz     short loc_180033EAD
0x180033ea8  mov     r9d, r15d
0x180033eab  jmp     short loc_180033ECD
0x180033ead  mov     r9d, 200h; unsigned int
0x180033eb3  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x180033eb8  mov     ebp, eax
0x180033eba  test    eax, eax
0x180033ebc  jnz     short loc_180033ED4
0x180033ebe  mov     r9d, r15d
0x180033ec1  mov     r8d, r12d; unsigned int
0x180033ec4  sub     r9d, r12d; unsigned int
0x180033ec7  mov     rdx, rbx; void *
0x180033eca  mov     rcx, rdi; this
0x180033ecd  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x180033ed2  mov     ebp, eax
0x180033ed4  cmp     [rsi+33Dh], r13b
0x180033edb  jz      short loc_180033EE5
0x180033edd  mov     rcx, r14
0x180033ee0  call    ?lock@?$unique_lock@Vshared_mutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::shared_mutex>::lock(void)
0x180033ee5  test    ebp, ebp
0x180033ee7  jnz     short loc_180033EF0
0x180033ee9  mov     [rsi+32Ch], r15d
0x180033ef0  lea     rbx, [rsi+2E8h]
0x180033ef7  mov     [rsi+346h], r13b
0x180033efe  lea     rcx, [rbx+8]; SRWLock
0x180033f02  call    cs:__imp_AcquireSRWLockExclusive
0x180033f08  mov     rcx, rbx; ConditionVariable
0x180033f0b  call    cs:__imp_WakeAllConditionVariable
0x180033f11  lea     rcx, [rbx+8]; SRWLock
0x180033f15  call    cs:__imp_ReleaseSRWLockExclusive
0x180033f1b  test    ebp, ebp
0x180033f1d  jz      short loc_180033F5D
0x180033f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f26  lea     rdx, WPP_GLOBAL_Control
0x180033f2d  cmp     rcx, rdx
0x180033f30  jz      short loc_180033F59
0x180033f32  test    dword ptr [rcx+1Ch], 8000h
0x180033f39  jz      short loc_180033F59
0x180033f3b  cmp     byte ptr [rcx+19h], 2
0x180033f3f  jb      short loc_180033F59
0x180033f41  mov     rcx, [rcx+10h]
0x180033f45  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180033f4c  mov     edx, 2Bh ; '+'
0x180033f51  mov     r9d, ebp
0x180033f54  call    WPP_SF_D
0x180033f59  mov     eax, ebp
0x180033f5b  jmp     short loc_180033F90
0x180033f5d  mov     rcx, [rsi+290h]; pti
0x180033f64  test    rcx, rcx
0x180033f67  jz      short loc_180033F87
0x180033f69  cmp     [rsi+345h], r13b
0x180033f70  jz      short loc_180033F87
0x180033f72  xor     r9d, r9d; msWindowLength
0x180033f75  mov     [rsi+345h], r13b
0x180033f7c  xor     r8d, r8d; msPeriod
0x180033f7f  xor     edx, edx; pftDueTime
0x180033f81  call    cs:__imp_SetThreadpoolTimer
0x180033f87  mov     [rsi+33Ah], r13b
0x180033f8e  xor     eax, eax
0x180033f90  add     rsp, 58h
0x180033f94  pop     r15
0x180033f96  pop     r14
0x180033f98  pop     r13
0x180033f9a  pop     r12
0x180033f9c  pop     rdi
0x180033f9d  pop     rsi
0x180033f9e  pop     rbp
0x180033f9f  pop     rbx
0x180033fa0  retn
```
