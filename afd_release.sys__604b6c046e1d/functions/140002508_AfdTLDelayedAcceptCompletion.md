# AfdTLDelayedAcceptCompletion

- ea: `0x140002508`
- end: `0x140002713`
- name: `AfdTLDelayedAcceptCompletion`
- size: `523`
- prototype: `__int64 __fastcall(__int64, _QWORD *, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003d20`
- `0x14004d210`
- `0x14004d360`

## callees

- `0x140002220`
- `0x140002508`
- `0x14000271c`
- `0x14000f390`
- `0x140044cb0`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140002624`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140002624`
- `ntoskrnl!IofCompleteRequest` at `0x1400026ac`
- `ntoskrnl!IofCompleteRequest` at `0x1400026ac`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140002614`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140002614`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400025bb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400026c8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400025bb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400026c8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000253a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000253a`

## pseudocode

```c
__int64 __fastcall AfdTLDelayedAcceptCompletion(__int64 a1, _QWORD *a2, int a3)
{
  _QWORD *i; // rcx
  _QWORD *v7; // rdi
  _QWORD *v8; // rax
  _QWORD *v9; // rcx
  _QWORD *v10; // rdx
  int v11; // eax
  int v12; // ecx
  __int64 v13; // rbx
  __int64 (__fastcall **v14)(); // rax
  __int64 v15; // r8
  int restarted; // eax
  int v18; // ecx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-38h] BYREF
  KIRQL Irql; // [rsp+70h] [rbp+8h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
  for ( i = *(_QWORD **)(a1 + 144); ; i = (_QWORD *)*i )
  {
    if ( i == (_QWORD *)(a1 + 144) )
      goto LABEL_24;
    v7 = i - 22;
    if ( *(i - 15) == *a2 )
      break;
  }
  if ( i == (_QWORD *)176 )
  {
LABEL_24:
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    AFDETW_TRACECONNECT_INDICATION(v18, 6508, a1, -1073741254, a2[3], a2[6]);
    return 3221226042LL;
  }
  v8 = i;
  v9 = (_QWORD *)*i;
  if ( (_QWORD *)v9[1] != v7 + 22 || (v10 = (_QWORD *)v7[23], (_QWORD *)*v10 != v8) )
    __fastfail(3u);
  *v10 = v9;
  v9[1] = v10;
  v11 = *((_DWORD *)v7 + 1);
  if ( (v11 & 0x40000) != 0 )
  {
    *((_DWORD *)v7 + 1) = v11 & 0xFFFBFFFF;
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 176));
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  AFDETW_TRACECONNECT_INDICATION(v12, 6509, a1, a3, a2[3], a2[6]);
  v7[8] = v7 + 7;
  v7[7] = v7 + 7;
  AfdDereferenceEndpoint(a1);
  v13 = v7[5];
  if ( !_InterlockedExchange64((volatile __int64 *)(v13 + 104), 0) )
  {
    Irql = 0;
    IoAcquireCancelSpinLock(&Irql);
    IoReleaseCancelSpinLock(Irql);
  }
  *(_DWORD *)(v13 + 48) = a3;
  if ( !a3 )
  {
    v7[3] = a2[5];
    v7[2] = a2[4];
    v14 = AfdTlClientConnectDispatch;
    a2[7] = v7;
    if ( (*(_BYTE *)(a1 + 7) & 0x10) != 0 )
      v14 = AfdRioTlClientConnectDispatch;
    a2[8] = v14;
  }
  v15 = *(_QWORD *)(v13 + 184);
  if ( *(_BYTE *)v15 == 15 && *(_BYTE *)(v15 + 1) == 32 )
    restarted = AfdRestartDelayedSuperAccept(0, v13, *(_QWORD *)(v15 + 32));
  else
    restarted = AfdRestartDelayedAccept(0, v13, *(_QWORD **)(v13 + 144));
  if ( restarted != -1073741802 )
    IofCompleteRequest((PIRP)v13, AfdPriorityBoost);
  return 0;
}

```

## disassembly

```asm
0x140002508  mov     r11, rsp
0x14000250b  mov     [r11+10h], rbx
0x14000250f  mov     [r11+18h], rbp
0x140002513  push    rsi
0x140002514  push    rdi
0x140002515  push    r14
0x140002517  sub     rsp, 50h
0x14000251b  xorps   xmm0, xmm0
0x14000251e  mov     rsi, rdx
0x140002521  mov     rbp, rcx
0x140002524  lea     rdx, [r11-38h]; LockHandle
0x140002528  xor     eax, eax
0x14000252a  add     rcx, 38h ; '8'; SpinLock
0x14000252e  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x140002533  mov     [r11-28h], rax
0x140002537  mov     r14d, r8d
0x14000253a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002541  nop     dword ptr [rax+rax+00h]
0x140002546  lea     rdx, [rbp+90h]
0x14000254d  mov     rcx, [rdx]
0x140002550  cmp     rcx, rdx
0x140002553  jz      loc_1400026C3
0x140002559  mov     rax, [rsi]
0x14000255c  lea     rdi, [rcx-0B0h]
0x140002563  cmp     [rdi+38h], rax
0x140002567  jz      short loc_14000256E
0x140002569  mov     rcx, [rcx]
0x14000256c  jmp     short loc_140002550
0x14000256e  test    rdi, rdi
0x140002571  jz      loc_1400026C3
0x140002577  lea     rax, [rdi+0B0h]
0x14000257e  mov     rcx, [rax]
0x140002581  cmp     [rcx+8], rax
0x140002585  jnz     loc_1400026BC
0x14000258b  mov     rdx, [rax+8]
0x14000258f  cmp     [rdx], rax
0x140002592  jnz     loc_1400026BC
0x140002598  mov     [rdx], rcx
0x14000259b  mov     [rcx+8], rdx
0x14000259f  mov     eax, [rdi+4]
0x1400025a2  bt      eax, 12h
0x1400025a6  jnb     short loc_1400025B6
0x1400025a8  btr     eax, 12h
0x1400025ac  mov     [rdi+4], eax
0x1400025af  lock dec dword ptr [rbp+0B0h]
0x1400025b6  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x1400025bb  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400025c2  nop     dword ptr [rax+rax+00h]
0x1400025c7  mov     rax, [rsi+30h]
0x1400025cb  mov     r9d, r14d
0x1400025ce  mov     [rsp+68h+var_40], rax
0x1400025d3  mov     r8, rbp
0x1400025d6  mov     rax, [rsi+18h]
0x1400025da  mov     edx, 196Dh
0x1400025df  mov     [rsp+68h+var_48], rax
0x1400025e4  call    AFDETW_TRACECONNECT_INDICATION
0x1400025e9  lea     rax, [rdi+38h]
0x1400025ed  mov     rcx, rbp
0x1400025f0  mov     [rax+8], rax
0x1400025f4  mov     [rax], rax
0x1400025f7  call    AfdDereferenceEndpoint
0x1400025fc  mov     rbx, [rdi+28h]
0x140002600  xor     eax, eax
0x140002602  xchg    rax, [rbx+68h]
0x140002606  test    rax, rax
0x140002609  jnz     short loc_140002630
0x14000260b  lea     rcx, [rsp+68h+Irql]; Irql
0x140002610  mov     [rsp+68h+Irql], al
0x140002614  call    cs:__imp_IoAcquireCancelSpinLock
0x14000261b  nop     dword ptr [rax+rax+00h]
0x140002620  mov     cl, [rsp+68h+Irql]; Irql
0x140002624  call    cs:__imp_IoReleaseCancelSpinLock
0x14000262b  nop     dword ptr [rax+rax+00h]
0x140002630  mov     [rbx+30h], r14d
0x140002634  test    r14d, r14d
0x140002637  jnz     short loc_140002667
0x140002639  mov     rax, [rsi+28h]
0x14000263d  lea     rcx, AfdRioTlClientConnectDispatch
0x140002644  mov     [rdi+18h], rax
0x140002648  mov     rax, [rsi+20h]
0x14000264c  mov     [rdi+10h], rax
0x140002650  lea     rax, AfdTlClientConnectDispatch
0x140002657  mov     [rsi+38h], rdi
0x14000265b  test    byte ptr [rbp+7], 10h
0x14000265f  cmovnz  rax, rcx
0x140002663  mov     [rsi+40h], rax
0x140002667  mov     r8, [rbx+0B8h]
0x14000266e  cmp     byte ptr [r8], 0Fh
0x140002672  jnz     short loc_14000268B
0x140002674  cmp     byte ptr [r8+1], 20h ; ' '
0x140002679  jnz     short loc_14000268B
0x14000267b  mov     r8, [r8+20h]
0x14000267f  mov     rdx, rbx
0x140002682  xor     ecx, ecx
0x140002684  call    AfdRestartDelayedSuperAccept
0x140002689  jmp     short loc_14000269C
0x14000268b  mov     r8, [rbx+90h]
0x140002692  mov     rdx, rbx
0x140002695  xor     ecx, ecx
0x140002697  call    AfdRestartDelayedAccept
0x14000269c  cmp     eax, 0C0000016h
0x1400026a1  jz      short loc_1400026B8
0x1400026a3  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x1400026a9  mov     rcx, rbx; Irp
0x1400026ac  call    cs:__imp_IofCompleteRequest
0x1400026b3  nop     dword ptr [rax+rax+00h]
0x1400026b8  xor     eax, eax
0x1400026ba  jmp     short loc_1400026FD
0x1400026bc  mov     ecx, 3
0x1400026c1  int     29h; Win8: RtlFailFast(ecx)
0x1400026c3  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x1400026c8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400026cf  nop     dword ptr [rax+rax+00h]
0x1400026d4  mov     rax, [rsi+30h]
0x1400026d8  mov     ebx, 0C000023Ah
0x1400026dd  mov     [rsp+68h+var_40], rax
0x1400026e2  mov     r9d, ebx
0x1400026e5  mov     rax, [rsi+18h]
0x1400026e9  mov     r8, rbp
0x1400026ec  mov     edx, 196Ch
0x1400026f1  mov     [rsp+68h+var_48], rax
0x1400026f6  call    AFDETW_TRACECONNECT_INDICATION
0x1400026fb  mov     eax, ebx
0x1400026fd  lea     r11, [rsp+68h+var_18]
0x140002702  mov     rbx, [r11+28h]
0x140002706  mov     rbp, [r11+30h]
0x14000270a  mov     rsp, r11
0x14000270d  pop     r14
0x14000270f  pop     rdi
0x140002710  pop     rsi
0x140002711  retn
```
