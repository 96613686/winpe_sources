# CSxFunctionTracer::~CSxFunctionTracer(void)

- ea: `0x14000e41c`
- end: `0x14000e66c`
- name: `??1CSxFunctionTracer@@QEAA@XZ`
- size: `592`
- prototype: `void __fastcall(CSxFunctionTracer *__hidden this)`
- caller_count: `50`
- callee_count: `5`
- tags: ``

## callers

- `0x140001b3c`
- `0x140001dec`
- `0x1400020c4`
- `0x1400022c0`
- `0x140002484`
- `0x140002670`
- `0x1400029b4`
- `0x140002ae8`
- `0x140002f30`
- `0x14000312c`
- `0x140003320`
- `0x140003584`
- `0x14000372c`
- `0x1400039e4`
- `0x140003dc4`
- `0x140003e70`
- `0x1400041ec`
- `0x140004410`
- `0x1400047e4`
- `0x140004a70`
- `0x1400050f0`
- `0x140005784`
- `0x14000595c`
- `0x140005ac0`
- `0x140005c10`
- `0x140005eb0`
- `0x140006018`
- `0x140006334`
- `0x1400066e0`
- `0x1400068d4`
- `0x140006ab0`
- `0x140006e40`
- `0x140007030`
- `0x1400074d8`
- `0x1400075cc`
- `0x14000771c`
- `0x140007954`
- `0x14000d688`
- `0x14000de58`
- `0x14000e0f0`
- `0x14000ec40`
- `0x14000ed4c`
- `0x14000ef3c`
- `0x14000f0b0`
- `0x14000f188`
- `0x14000f24c`
- `0x14000f510`
- `0x14000f7a0`
- `0x14000fa1c`
- `0x14000fd0c`

## callees

- `0x140006660`
- `0x14000e41c`
- `0x14000ea74`
- `0x14000ead8`
- `0x14000eb68`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000e4c1`
- `KERNEL32!LocalFree` at `0x14000e62d`
- `KERNEL32!LocalFree` at `0x14000e653`
- `KERNEL32!LocalFree` at `0x14000e4c1`
- `KERNEL32!LocalFree` at `0x14000e62d`
- `KERNEL32!LocalFree` at `0x14000e653`
- `SPP!SxTracerDebuggerBreak` at `0x14000e579`
- `SPP!SxTracerDebuggerBreak` at `0x14000e579`
- `SPP!SxTracerShouldTrackFailure` at `0x14000e437`
- `SPP!SxTracerShouldTrackFailure` at `0x14000e437`

## pseudocode

```c
void __fastcall CSxFunctionTracer::~CSxFunctionTracer(CSxFunctionTracer *this, __int64 a2, __int64 a3)
{
  int v4; // edx
  int ShouldTrackFailure; // ebp
  int v6; // r8d
  const char *v7; // rcx
  _QWORD *v8; // r10
  void *v9; // rcx
  int v10; // eax
  __int64 v11; // rax
  __int64 i; // rsi
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  void *v17; // rcx

  if ( *(int *)this >= 0 )
  {
    if ( *((_WORD *)this + 6) )
    {
      if ( *((_WORD *)this + 6) == 1 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) == 0 )
        {
          goto LABEL_40;
        }
        v14 = 17;
      }
      else
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) == 0 )
        {
          goto LABEL_40;
        }
        v14 = 18;
      }
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0 )
      {
        goto LABEL_40;
      }
      v14 = 16;
    }
    WPP_SF_s(v13[2], v14, a3, *((_QWORD *)this + 2));
    goto LABEL_40;
  }
  ShouldTrackFailure = SxTracerShouldTrackFailure();
  v7 = "FAILED[TRACK]";
  if ( !ShouldTrackFailure )
    v7 = "FAILED";
  if ( !*((_DWORD *)this + 2) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) == 0 )
      goto LABEL_9;
    WPP_SF_sdsdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *((unsigned __int16 *)this + 3),
      *((unsigned __int16 *)this + 2),
      *((_QWORD *)this + 2),
      *((_WORD *)this + 2),
      (__int64)v7,
      *((_WORD *)this + 3),
      *(_DWORD *)this);
  }
  v8 = WPP_GLOBAL_Control;
LABEL_9:
  if ( *((_QWORD *)this + 5) )
  {
    v7 = (const char *)*((_QWORD *)this + 4);
    if ( *(_DWORD *)this != *((_DWORD *)v7 + 6) )
    {
      v9 = (void *)*((_QWORD *)v7 + 2);
      if ( v9 )
      {
        LocalFree(v9);
        *(_QWORD *)(*((_QWORD *)this + 4) + 16LL) = 0;
      }
      *(_DWORD *)(*((_QWORD *)this + 4) + 4LL) = *((_DWORD *)this + 12);
      *(_QWORD *)(*((_QWORD *)this + 4) + 16LL) = *((_QWORD *)this + 5);
      v7 = (const char *)*((_QWORD *)this + 4);
      v10 = *(_DWORD *)this;
      *((_QWORD *)this + 5) = 0;
      *((_DWORD *)v7 + 6) = v10;
      v8 = WPP_GLOBAL_Control;
    }
  }
  v11 = *((_QWORD *)this + 4);
  if ( !v11 || *(_DWORD *)this != *(_DWORD *)(v11 + 8) )
  {
    if ( !*((_DWORD *)this + 2) )
    {
      for ( i = *((_QWORD *)this + 3); i; i = *(_QWORD *)(i + 24) )
      {
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
        {
          WPP_SF_sdd(v8[2], v4, v6, *(_QWORD *)(i + 16), *(_WORD *)(i + 4), *(_DWORD *)i);
          v8 = WPP_GLOBAL_Control;
        }
      }
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
        WPP_SF_sd(v8[2], v4, v6, *((_QWORD *)this + 2), *((_WORD *)this + 3));
    }
    if ( ShouldTrackFailure )
      SxTracerDebuggerBreak(v7);
  }
LABEL_40:
  v15 = *((_QWORD *)this + 4);
  if ( v15 )
  {
    *(_QWORD *)(v15 + 32) = *((_QWORD *)this + 3);
    v16 = *((_QWORD *)this + 4);
    if ( *((_QWORD *)this + 3) )
    {
      *(_DWORD *)(v16 + 8) = *(_DWORD *)this;
    }
    else
    {
      *(_DWORD *)(v16 + 8) = 0;
      LocalFree(*(HLOCAL *)(*((_QWORD *)this + 4) + 16LL));
      *(_QWORD *)(*((_QWORD *)this + 4) + 16LL) = 0;
      *(_DWORD *)(*((_QWORD *)this + 4) + 24LL) = 0;
    }
  }
  v17 = (void *)*((_QWORD *)this + 5);
  if ( v17 )
  {
    LocalFree(v17);
    *((_QWORD *)this + 5) = 0;
  }
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x14000e41c  push    rbx
0x14000e41e  push    rbp
0x14000e41f  push    rsi
0x14000e420  push    rdi
0x14000e421  push    r14
0x14000e423  sub     rsp, 40h
0x14000e427  mov     rbx, rcx
0x14000e42a  xor     r14d, r14d
0x14000e42d  mov     ecx, [rcx]
0x14000e42f  test    ecx, ecx
0x14000e431  jns     loc_14000E584
0x14000e437  call    cs:__imp_SxTracerShouldTrackFailure
0x14000e43d  mov     ebp, eax
0x14000e43f  lea     rcx, aFailedTrack; "FAILED[TRACK]"
0x14000e446  test    ebp, ebp
0x14000e448  lea     rax, aFailed; "FAILED"
0x14000e44f  lea     rdi, WPP_GLOBAL_Control
0x14000e456  cmovz   rcx, rax
0x14000e45a  cmp     [rbx+8], r14d
0x14000e45e  jnz     short loc_14000E4A0
0x14000e460  mov     r10, cs:WPP_GLOBAL_Control
0x14000e467  cmp     r10, rdi
0x14000e46a  jz      short loc_14000E4A7
0x14000e46c  test    dword ptr [r10+1Ch], 2000000h
0x14000e474  jz      short loc_14000E4A7
0x14000e476  movzx   edx, word ptr [rbx+6]
0x14000e47a  mov     eax, [rbx]
0x14000e47c  movzx   r8d, word ptr [rbx+4]
0x14000e481  mov     r9, [rbx+10h]
0x14000e485  mov     [rsp+68h+var_30], eax
0x14000e489  mov     [rsp+68h+var_38], edx
0x14000e48d  mov     [rsp+68h+var_40], rcx
0x14000e492  mov     rcx, [r10+10h]
0x14000e496  mov     [rsp+68h+var_48], r8d
0x14000e49b  call    WPP_SF_sdsdd
0x14000e4a0  mov     r10, cs:WPP_GLOBAL_Control
0x14000e4a7  cmp     [rbx+28h], r14
0x14000e4ab  jz      short loc_14000E4F9
0x14000e4ad  mov     rcx, [rbx+20h]
0x14000e4b1  mov     eax, [rcx+18h]
0x14000e4b4  cmp     [rbx], eax
0x14000e4b6  jz      short loc_14000E4F9
0x14000e4b8  mov     rcx, [rcx+10h]; hMem
0x14000e4bc  test    rcx, rcx
0x14000e4bf  jz      short loc_14000E4CF
0x14000e4c1  call    cs:__imp_LocalFree
0x14000e4c7  mov     rax, [rbx+20h]
0x14000e4cb  mov     [rax+10h], r14
0x14000e4cf  mov     rcx, [rbx+20h]
0x14000e4d3  mov     eax, [rbx+30h]
0x14000e4d6  mov     [rcx+4], eax
0x14000e4d9  mov     rax, [rbx+28h]
0x14000e4dd  mov     rcx, [rbx+20h]
0x14000e4e1  mov     [rcx+10h], rax
0x14000e4e5  mov     rcx, [rbx+20h]
0x14000e4e9  mov     eax, [rbx]
0x14000e4eb  mov     [rbx+28h], r14
0x14000e4ef  mov     [rcx+18h], eax
0x14000e4f2  mov     r10, cs:WPP_GLOBAL_Control
0x14000e4f9  mov     rax, [rbx+20h]
0x14000e4fd  test    rax, rax
0x14000e500  jz      short loc_14000E50D
0x14000e502  mov     eax, [rax+8]
0x14000e505  cmp     [rbx], eax
0x14000e507  jz      loc_14000E606
0x14000e50d  cmp     [rbx+8], r14d
0x14000e511  jnz     short loc_14000E571
0x14000e513  mov     rsi, [rbx+18h]
0x14000e517  jmp     short loc_14000E54B
0x14000e519  cmp     r10, rdi
0x14000e51c  jz      short loc_14000E547
0x14000e51e  test    byte ptr [r10+1Ch], 1
0x14000e523  jz      short loc_14000E547
0x14000e525  movzx   ecx, word ptr [rsi+4]
0x14000e529  mov     eax, [rsi]
0x14000e52b  mov     r9, [rsi+10h]
0x14000e52f  mov     dword ptr [rsp+68h+var_40], eax
0x14000e533  mov     [rsp+68h+var_48], ecx
0x14000e537  mov     rcx, [r10+10h]
0x14000e53b  call    WPP_SF_sdd
0x14000e540  mov     r10, cs:WPP_GLOBAL_Control
0x14000e547  mov     rsi, [rsi+18h]
0x14000e54b  test    rsi, rsi
0x14000e54e  jnz     short loc_14000E519
0x14000e550  cmp     r10, rdi
0x14000e553  jz      short loc_14000E571
0x14000e555  test    byte ptr [r10+1Ch], 1
0x14000e55a  jz      short loc_14000E571
0x14000e55c  movzx   eax, word ptr [rbx+6]
0x14000e560  mov     r9, [rbx+10h]
0x14000e564  mov     rcx, [r10+10h]
0x14000e568  mov     [rsp+68h+var_48], eax
0x14000e56c  call    WPP_SF_sd
0x14000e571  test    ebp, ebp
0x14000e573  jz      loc_14000E606
0x14000e579  call    cs:__imp_SxTracerDebuggerBreak
0x14000e57f  jmp     loc_14000E606
0x14000e584  cmp     [rbx+0Ch], r14w
0x14000e589  jnz     short loc_14000E5AE
0x14000e58b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e592  lea     rdi, WPP_GLOBAL_Control
0x14000e599  cmp     rcx, rdi
0x14000e59c  jz      short loc_14000E606
0x14000e59e  test    dword ptr [rcx+1Ch], 8000000h
0x14000e5a5  jz      short loc_14000E606
0x14000e5a7  mov     edx, 10h
0x14000e5ac  jmp     short loc_14000E5F9
0x14000e5ae  cmp     word ptr [rbx+0Ch], 1
0x14000e5b3  jnz     short loc_14000E5D8
0x14000e5b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e5bc  lea     rdi, WPP_GLOBAL_Control
0x14000e5c3  cmp     rcx, rdi
0x14000e5c6  jz      short loc_14000E606
0x14000e5c8  test    dword ptr [rcx+1Ch], 20000000h
0x14000e5cf  jz      short loc_14000E606
0x14000e5d1  mov     edx, 11h
0x14000e5d6  jmp     short loc_14000E5F9
0x14000e5d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e5df  lea     rdi, WPP_GLOBAL_Control
0x14000e5e6  cmp     rcx, rdi
0x14000e5e9  jz      short loc_14000E606
0x14000e5eb  test    dword ptr [rcx+1Ch], 20000h
0x14000e5f2  jz      short loc_14000E606
0x14000e5f4  mov     edx, 12h
0x14000e5f9  mov     r9, [rbx+10h]
0x14000e5fd  mov     rcx, [rcx+10h]
0x14000e601  call    WPP_SF_s
0x14000e606  mov     rcx, [rbx+20h]
0x14000e60a  test    rcx, rcx
0x14000e60d  jz      short loc_14000E64A
0x14000e60f  mov     rax, [rbx+18h]
0x14000e613  mov     [rcx+20h], rax
0x14000e617  mov     rcx, [rbx+20h]
0x14000e61b  cmp     [rbx+18h], r14
0x14000e61f  jnz     short loc_14000E645
0x14000e621  mov     [rcx+8], r14d
0x14000e625  mov     rcx, [rbx+20h]
0x14000e629  mov     rcx, [rcx+10h]; hMem
0x14000e62d  call    cs:__imp_LocalFree
0x14000e633  mov     rax, [rbx+20h]
0x14000e637  mov     [rax+10h], r14
0x14000e63b  mov     rax, [rbx+20h]
0x14000e63f  mov     [rax+18h], r14d
0x14000e643  jmp     short loc_14000E64A
0x14000e645  mov     eax, [rbx]
0x14000e647  mov     [rcx+8], eax
0x14000e64a  mov     rcx, [rbx+28h]; hMem
0x14000e64e  test    rcx, rcx
0x14000e651  jz      short loc_14000E65D
0x14000e653  call    cs:__imp_LocalFree
0x14000e659  mov     [rbx+28h], r14
0x14000e65d  mov     [rbx+18h], r14
0x14000e661  add     rsp, 40h
0x14000e665  pop     r14
0x14000e667  pop     rdi
0x14000e668  pop     rsi
0x14000e669  pop     rbp
0x14000e66a  pop     rbx
0x14000e66b  retn
```
