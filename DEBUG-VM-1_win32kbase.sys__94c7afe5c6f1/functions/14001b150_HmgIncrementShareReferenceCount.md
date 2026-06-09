# HmgIncrementShareReferenceCount

- ea: `0x14001b150`
- end: `0x14001b36c`
- name: `HmgIncrementShareReferenceCount`
- size: `540`
- prototype: ``
- caller_count: `13`
- callee_count: `5`
- tags: ``

## callers

- `0x1400112e0`
- `0x140025378`
- `0x140025bf8`
- `0x140033530`
- `0x140036940`
- `0x1400927a0`
- `0x140092a60`
- `0x1400ffa80`
- `0x140163cfc`
- `0x140174c2c`
- `0x140185938`
- `0x1401e5988`
- `0x1401f2214`

## callees

- `0x14001b150`
- `0x14001bf04`
- `0x14001d250`
- `0x14003bf24`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14001b316`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001b316`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b26f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b2be`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b26f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b2be`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001b325`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001b342`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001b325`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001b342`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001b333`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001b333`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001b1a9`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001b1a9`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14001b19a`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14001b19a`

## pseudocode

```c
void __fastcall HmgIncrementShareReferenceCount(__int64 a1, unsigned int *a2)
{
  unsigned int v2; // eax
  unsigned int v4; // edi
  __int64 v5; // r13
  unsigned int v6; // edi
  _QWORD *CurrentThreadWin32ThreadAndEnterCriticalRegion; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r15
  __int64 v13; // rcx
  int v14; // ebx
  unsigned int *v15; // rax
  unsigned int *v16; // rsi
  char v17; // al
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 *v20; // rdi
  __int64 v21; // rbx
  __int64 v22; // rax
  ThreadRestrictNewHandlesRegion *v23; // rcx
  __int64 CurrentProcess; // rax
  int ProcessSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  unsigned int *v27; // [rsp+20h] [rbp-48h] BYREF
  int v28; // [rsp+28h] [rbp-40h]
  __int16 v29; // [rsp+2Ch] [rbp-3Ch]
  __int64 v30; // [rsp+30h] [rbp-38h]
  __int64 v31; // [rsp+70h] [rbp+8h] BYREF

  v2 = *a2;
  v4 = *a2;
  v30 = a1;
  v5 = a1;
  v6 = (unsigned __int16)v2 | (v4 >> 8) & 0xFF0000;
  v29 = 0;
  v31 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (_QWORD *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v31);
  if ( (!(unsigned __int8)KeIsAttachedProcess()
     || (CurrentProcess = PsGetCurrentProcess(v10, v9, v11),
         ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess),
         CurrentThreadProcess = PsGetCurrentThreadProcess(),
         ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)))
    && CurrentThreadWin32ThreadAndEnterCriticalRegion
    && *CurrentThreadWin32ThreadAndEnterCriticalRegion )
  {
    v12 = *CurrentThreadWin32ThreadAndEnterCriticalRegion + 8LL;
  }
  else
  {
    v12 = 0;
  }
  v13 = *(_QWORD *)(a1 + 8);
  v14 = 1;
  v28 = 1;
  v15 = (unsigned int *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 40LL))(v13, v6);
  v27 = v15;
  v16 = v15;
  if ( v15 )
  {
    _m_prefetchw(v15 + 2);
    if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 96LL))(
                       *(_QWORD *)(a1 + 8),
                       *v15)
                   + 14)
        & 0x20) != 0
      && (!v12
       || (v23 = *(ThreadRestrictNewHandlesRegion **)(v12 + 328)) == 0
       || !*((_BYTE *)v23 + 80)
       || !ThreadRestrictNewHandlesRegion::InRegion(v23, v6)) )
    {
      LOBYTE(v29) = 1;
      HANDLELOCK::vUnlock((HANDLELOCK *)&v27);
      v5 = v30;
      v14 = v28;
      v16 = v27;
    }
  }
  else
  {
    v14 = 0;
    KeLeaveCriticalRegion();
  }
  if ( v14 )
  {
    v17 = *((_BYTE *)v16 + 14);
    switch ( v17 )
    {
      case 5:
        v18 = *((_QWORD *)a2 + 91);
        v19 = 3;
        break;
      case 4:
        v18 = *((_QWORD *)a2 + 14);
        v19 = 2;
        break;
      case 16:
        v18 = *((_QWORD *)a2 + 17);
        v19 = 0;
        break;
      default:
        goto LABEL_11;
    }
    TrackObjectReferenceIncrement(a1, v19, v18);
LABEL_11:
    ++a2[2];
    v20 = *(__int64 **)(v5 + 8);
    v21 = *v20;
    v22 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v20 + 96))(v20, *v16);
    (*(void (__fastcall **)(__int64 *, __int64))(v21 + 48))(v20, v22);
    KeLeaveCriticalRegion();
    return;
  }
  (*(void (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8), a2);
}

```

## disassembly

```asm
0x14001b150  mov     [rsp+arg_10], rbx
0x14001b155  push    rbp
0x14001b156  push    rsi
0x14001b157  push    rdi
0x14001b158  push    r13
0x14001b15a  push    r14
0x14001b15c  sub     rsp, 40h
0x14001b160  mov     eax, [rdx]
0x14001b162  mov     rbp, rcx
0x14001b165  mov     edi, eax
0x14001b167  mov     [rsp+68h+var_38], rcx
0x14001b16c  shr     edi, 8
0x14001b16f  mov     r13, rcx
0x14001b172  movzx   eax, ax
0x14001b175  lea     rcx, [rsp+68h+arg_0]
0x14001b17a  and     edi, 0FF0000h
0x14001b180  mov     [rsp+68h+arg_8], r15
0x14001b185  or      edi, eax
0x14001b187  mov     [rsp+68h+var_3C], 0
0x14001b18e  mov     r14, rdx
0x14001b191  mov     [rsp+68h+arg_0], 0
0x14001b19a  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x14001b1a1  nop     dword ptr [rax+rax+00h]
0x14001b1a6  mov     rsi, rax
0x14001b1a9  call    cs:__imp_KeIsAttachedProcess
0x14001b1b0  nop     dword ptr [rax+rax+00h]
0x14001b1b5  test    al, al
0x14001b1b7  jnz     loc_14001B316
0x14001b1bd  test    rsi, rsi
0x14001b1c0  jz      loc_14001B356
0x14001b1c6  mov     rax, [rsi]
0x14001b1c9  test    rax, rax
0x14001b1cc  jz      loc_14001B356
0x14001b1d2  lea     r15, [rax+8]
0x14001b1d6  mov     rcx, [rbp+8]
0x14001b1da  mov     ebx, 1
0x14001b1df  mov     edx, edi
0x14001b1e1  mov     [rsp+68h+var_40], ebx
0x14001b1e5  mov     rax, [rcx]
0x14001b1e8  mov     rax, [rax+28h]
0x14001b1ec  call    _guard_dispatch_icall
0x14001b1f1  mov     [rsp+68h+var_48], rax
0x14001b1f6  mov     rsi, rax
0x14001b1f9  test    rax, rax
0x14001b1fc  jz      loc_14001B2BC
0x14001b202  prefetchw byte ptr [rax+8]
0x14001b206  mov     rcx, [rbp+8]
0x14001b20a  mov     edx, [rsi]
0x14001b20c  mov     rax, [rcx]
0x14001b20f  mov     rax, [rax+60h]
0x14001b213  call    _guard_dispatch_icall
0x14001b218  test    byte ptr [rax+0Eh], 20h
0x14001b21c  jnz     loc_14001B2CF
0x14001b222  mov     r15, [rsp+68h+arg_8]
0x14001b227  test    ebx, ebx
0x14001b229  jz      short loc_14001B290
0x14001b22b  movzx   eax, byte ptr [rsi+0Eh]
0x14001b22f  cmp     al, 5
0x14001b231  jnz     short loc_14001B2A5
0x14001b233  mov     r8, [r14+2D8h]
0x14001b23a  mov     edx, 3
0x14001b23f  mov     rcx, rbp
0x14001b242  call    ?TrackObjectReferenceIncrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceIncrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x14001b247  inc     dword ptr [r14+8]
0x14001b24b  mov     rdi, [r13+8]
0x14001b24f  mov     edx, [rsi]
0x14001b251  mov     rcx, rdi
0x14001b254  mov     rbx, [rdi]
0x14001b257  mov     rax, [rbx+60h]
0x14001b25b  call    _guard_dispatch_icall
0x14001b260  mov     rdx, rax
0x14001b263  mov     rcx, rdi
0x14001b266  mov     rax, [rbx+30h]
0x14001b26a  call    _guard_dispatch_icall
0x14001b26f  call    cs:__imp_KeLeaveCriticalRegion
0x14001b276  nop     dword ptr [rax+rax+00h]
0x14001b27b  mov     rbx, [rsp+68h+arg_10]
0x14001b283  add     rsp, 40h
0x14001b287  pop     r14
0x14001b289  pop     r13
0x14001b28b  pop     rdi
0x14001b28c  pop     rsi
0x14001b28d  pop     rbp
0x14001b28e  retn
0x14001b290  mov     rcx, [rbp+8]
0x14001b294  mov     rdx, r14
0x14001b297  mov     rax, [rcx]
0x14001b29a  mov     rax, [rax+8]
0x14001b29e  call    _guard_dispatch_icall
0x14001b2a3  jmp     short loc_14001B27B
0x14001b2a5  cmp     al, 4
0x14001b2a7  jz      loc_14001B35E
0x14001b2ad  cmp     al, 10h
0x14001b2af  jnz     short loc_14001B247
0x14001b2b1  mov     r8, [r14+88h]
0x14001b2b8  xor     edx, edx
0x14001b2ba  jmp     short loc_14001B23F
0x14001b2bc  xor     ebx, ebx
0x14001b2be  call    cs:__imp_KeLeaveCriticalRegion
0x14001b2c5  nop     dword ptr [rax+rax+00h]
0x14001b2ca  jmp     loc_14001B222
0x14001b2cf  test    r15, r15
0x14001b2d2  jz      short loc_14001B2F5
0x14001b2d4  mov     rcx, [r15+148h]; this
0x14001b2db  test    rcx, rcx
0x14001b2de  jz      short loc_14001B2F5
0x14001b2e0  cmp     byte ptr [rcx+50h], 0
0x14001b2e4  jz      short loc_14001B2F5
0x14001b2e6  mov     edx, edi; unsigned int
0x14001b2e8  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x14001b2ed  test    al, al
0x14001b2ef  jnz     loc_14001B222
0x14001b2f5  mov     byte ptr [rsp+68h+var_3C], bl
0x14001b2f9  lea     rcx, [rsp+68h+var_48]; this
0x14001b2fe  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x14001b303  mov     r13, [rsp+68h+var_38]
0x14001b308  mov     ebx, [rsp+68h+var_40]
0x14001b30c  mov     rsi, [rsp+68h+var_48]
0x14001b311  jmp     loc_14001B222
0x14001b316  call    cs:__imp_PsGetCurrentProcess
0x14001b31d  nop     dword ptr [rax+rax+00h]
0x14001b322  mov     rcx, rax
0x14001b325  call    cs:__imp_PsGetProcessSessionIdEx
0x14001b32c  nop     dword ptr [rax+rax+00h]
0x14001b331  mov     ebx, eax
0x14001b333  call    cs:__imp_PsGetCurrentThreadProcess
0x14001b33a  nop     dword ptr [rax+rax+00h]
0x14001b33f  mov     rcx, rax
0x14001b342  call    cs:__imp_PsGetProcessSessionIdEx
0x14001b349  nop     dword ptr [rax+rax+00h]
0x14001b34e  cmp     ebx, eax
0x14001b350  jz      loc_14001B1BD
0x14001b356  xor     r15d, r15d
0x14001b359  jmp     loc_14001B1D6
0x14001b35e  mov     r8, [r14+70h]
0x14001b362  mov     edx, 2
0x14001b367  jmp     loc_14001B23F
```
