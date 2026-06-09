# AfdSanFastUnlockAll

- ea: `0x14005d290`
- end: `0x14005d5b8`
- name: `AfdSanFastUnlockAll`
- size: `808`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x140019190`
- `0x1400191f0`
- `0x140041948`
- `0x140041a34`
- `0x14005d290`
- `0x140093008`
- `0x14009304c`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!IoSetIoCompletion` at `0x14005d3cb`
- `ntoskrnl!IoSetIoCompletion` at `0x14005d4a2`
- `ntoskrnl!IoSetIoCompletion` at `0x14005d3cb`
- `ntoskrnl!IoSetIoCompletion` at `0x14005d4a2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d375`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d375`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d34d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d34d`

## pseudocode

```c
char __fastcall AfdSanFastUnlockAll(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  unsigned __int64 v7; // rsi
  int v8; // ebp
  int v9; // edi
  __int64 v10; // rdi
  int restarted; // eax
  __int64 v12; // rdx
  char result; // al
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-58h] BYREF

  v3 = *(_QWORD *)(a1 + 24);
  v7 = AfdLockEndpointContext(v3);
  if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
    WPP_SF_q(1043, 41, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v3);
  if ( *(_WORD *)v3 == 6909 )
  {
    if ( *(_QWORD *)(*(_QWORD *)(v3 + 96) + 48LL) == a2 )
    {
      v8 = -1073741536;
      if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
        WPP_SF_q(1043, 42, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v3);
      if ( *(_QWORD *)(v3 + 96) != AfdSanServiceHelper )
      {
        memset(&LockHandle, 0, sizeof(LockHandle));
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 56), &LockHandle);
        v9 = *(_DWORD *)(v3 + 156);
        if ( !v9 )
          *(_DWORD *)(v3 + 156) = 259;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        if ( v9 == 259 || v9 == -1073741802 )
          goto LABEL_15;
        if ( v9 >= 0 )
        {
          v10 = *(_QWORD *)(v3 + 96);
          if ( (_InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 132), 2u) & 1) != 0 )
          {
            if ( (BYTE10(xmmword_1400875D0) & 8) != 0 )
              WPP_SF_q(787, 43, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, a2);
          }
          else
          {
            v8 = IoSetIoCompletion(*(_QWORD *)(v10 + 112), *(_QWORD *)(v3 + 112), 3);
            if ( v8 >= 0 )
            {
LABEL_15:
              AfdUnlockEndpointContext(v3, v7);
              goto LABEL_41;
            }
          }
          _InterlockedAdd((volatile signed __int32 *)(v10 + 132), 0xFFFFFFFE);
        }
      }
      AfdUnlockEndpointContext(v3, v7);
      AfdSanRestartRequestProcessing(v3, (unsigned int)v8);
      goto LABEL_41;
    }
    if ( !*(_BYTE *)(v3 + 160) )
    {
      AfdUnlockEndpointContext(v3, v7);
      if ( (BYTE2(xmmword_1400875E0) & 8) == 0 )
        goto LABEL_41;
      v12 = 48;
      goto LABEL_40;
    }
    AfdUnlockEndpointContext(v3, v7);
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_q(1043, 44, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v3);
    if ( *(_QWORD *)(a1 - 40) == 1 )
    {
      restarted = AfdSanRestartRequestProcessing(v3, 3221225760LL);
      if ( restarted >= 0 )
      {
        IoSetIoCompletion(*(_QWORD *)(*(_QWORD *)(v3 + 96) + 112LL), *(_QWORD *)(v3 + 112), 6);
        if ( (BYTE2(xmmword_1400875E0) & 8) == 0 )
          goto LABEL_41;
        v12 = 45;
LABEL_40:
        WPP_SF_q(1043, v12, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v3);
        goto LABEL_41;
      }
      if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
        WPP_SF_qD(1043, 46, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v3, restarted);
    }
    else if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
    {
      WPP_SF_qq(1043, 47, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v3, a1);
    }
  }
  else
  {
    if ( *(_WORD *)v3 != 2813 )
    {
      AfdUnlockEndpointContext(v3, v7);
      if ( (BYTE2(xmmword_1400875E0) & 8) == 0 )
        goto LABEL_41;
      v12 = 50;
      goto LABEL_40;
    }
    AfdUnlockEndpointContext(v3, v7);
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_q(1043, 49, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v3);
    if ( *(_QWORD *)(v3 + 48) == a2 )
      AfdSanHelperCleanup(v3);
  }
LABEL_41:
  *(_DWORD *)a3 = 0;
  result = 1;
  *(_QWORD *)(a3 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x14005d290  push    rbx
0x14005d292  push    rbp
0x14005d293  push    rsi
0x14005d294  push    rdi
0x14005d295  push    r13
0x14005d297  push    r14
0x14005d299  push    r15
0x14005d29b  sub     rsp, 50h
0x14005d29f  mov     rbx, [rcx+18h]
0x14005d2a3  mov     rdi, rcx
0x14005d2a6  mov     rcx, rbx
0x14005d2a9  mov     r15, r8
0x14005d2ac  mov     r14, rdx
0x14005d2af  call    AfdLockEndpointContext
0x14005d2b4  mov     rsi, rax
0x14005d2b7  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d2be  lea     rbp, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005d2c5  mov     r13d, 413h
0x14005d2cb  jz      short loc_14005D2E0
0x14005d2cd  mov     edx, 29h ; ')'
0x14005d2d2  mov     ecx, r13d
0x14005d2d5  mov     r9, rbx
0x14005d2d8  mov     r8, rbp
0x14005d2db  call    WPP_SF_q
0x14005d2e0  movzx   eax, word ptr [rbx]
0x14005d2e3  mov     ecx, 1AFDh
0x14005d2e8  cmp     ax, cx
0x14005d2eb  jnz     loc_14005D535
0x14005d2f1  mov     rax, [rbx+60h]
0x14005d2f5  cmp     [rax+30h], r14
0x14005d2f9  jnz     loc_14005D431
0x14005d2ff  mov     ebp, 0C0000120h
0x14005d304  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d30b  jz      short loc_14005D324
0x14005d30d  mov     edx, 2Ah ; '*'
0x14005d312  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005d319  mov     ecx, r13d
0x14005d31c  mov     r9, rbx
0x14005d31f  call    WPP_SF_q
0x14005d324  mov     rax, cs:AfdSanServiceHelper
0x14005d32b  cmp     [rbx+60h], rax
0x14005d32f  jz      loc_14005D417
0x14005d335  xorps   xmm0, xmm0
0x14005d338  lea     rcx, [rbx+38h]; SpinLock
0x14005d33c  xor     eax, eax
0x14005d33e  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x14005d343  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x14005d348  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x14005d34d  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005d354  nop     dword ptr [rax+rax+00h]
0x14005d359  mov     edi, [rbx+9Ch]
0x14005d35f  mov     r13d, 103h
0x14005d365  test    edi, edi
0x14005d367  jnz     short loc_14005D370
0x14005d369  mov     [rbx+9Ch], r13d
0x14005d370  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14005d375  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005d37c  nop     dword ptr [rax+rax+00h]
0x14005d381  cmp     edi, r13d
0x14005d384  jz      short loc_14005D3DD
0x14005d386  cmp     edi, 0C0000016h
0x14005d38c  jz      short loc_14005D3DD
0x14005d38e  test    edi, edi
0x14005d390  js      loc_14005D417
0x14005d396  mov     rdi, [rbx+60h]
0x14005d39a  mov     eax, 2
0x14005d39f  lock xadd [rdi+84h], eax
0x14005d3a7  test    al, 1
0x14005d3a9  jnz     short loc_14005D3ED
0x14005d3ab  mov     rax, cs:AfdSanServicePid
0x14005d3b2  xor     r9d, r9d
0x14005d3b5  mov     rdx, [rbx+70h]
0x14005d3b9  mov     rcx, [rdi+70h]
0x14005d3bd  mov     [rsp+88h+var_60], 0
0x14005d3c2  lea     r8d, [r9+3]
0x14005d3c6  mov     [rsp+88h+var_68], rax
0x14005d3cb  call    cs:__imp_IoSetIoCompletion
0x14005d3d2  nop     dword ptr [rax+rax+00h]
0x14005d3d7  mov     ebp, eax
0x14005d3d9  test    eax, eax
0x14005d3db  js      short loc_14005D40F
0x14005d3dd  mov     rdx, rsi
0x14005d3e0  mov     rcx, rbx
0x14005d3e3  call    AfdUnlockEndpointContext
0x14005d3e8  jmp     loc_14005D597
0x14005d3ed  test    byte ptr cs:xmmword_1400875D0+0Ah, 8
0x14005d3f4  jz      short loc_14005D40F
0x14005d3f6  mov     edx, 2Bh ; '+'
0x14005d3fb  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005d402  mov     ecx, 313h
0x14005d407  mov     r9, r14
0x14005d40a  call    WPP_SF_q
0x14005d40f  lock add dword ptr [rdi+84h], 0FFFFFFFEh
0x14005d417  mov     rdx, rsi
0x14005d41a  mov     rcx, rbx
0x14005d41d  call    AfdUnlockEndpointContext
0x14005d422  mov     edx, ebp
0x14005d424  mov     rcx, rbx
0x14005d427  call    AfdSanRestartRequestProcessing
0x14005d42c  jmp     loc_14005D597
0x14005d431  cmp     byte ptr [rbx+0A0h], 0
0x14005d438  mov     rdx, rsi
0x14005d43b  mov     rcx, rbx
0x14005d43e  jz      loc_14005D520
0x14005d444  call    AfdUnlockEndpointContext
0x14005d449  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d450  jz      short loc_14005D465
0x14005d452  mov     edx, 2Ch ; ','
0x14005d457  mov     ecx, r13d
0x14005d45a  mov     r9, rbx
0x14005d45d  mov     r8, rbp
0x14005d460  call    WPP_SF_q
0x14005d465  cmp     qword ptr [rdi-28h], 1
0x14005d46a  jnz     loc_14005D4F9
0x14005d470  mov     edx, 0C0000120h
0x14005d475  mov     rcx, rbx
0x14005d478  call    AfdSanRestartRequestProcessing
0x14005d47d  test    eax, eax
0x14005d47f  js      short loc_14005D4CC
0x14005d481  mov     rcx, [rbx+60h]
0x14005d485  xor     r9d, r9d
0x14005d488  mov     rdx, [rbx+70h]
0x14005d48c  mov     [rsp+88h+var_60], 0
0x14005d491  mov     [rsp+88h+var_68], 0
0x14005d49a  mov     rcx, [rcx+70h]
0x14005d49e  lea     r8d, [r9+6]
0x14005d4a2  call    cs:__imp_IoSetIoCompletion
0x14005d4a9  nop     dword ptr [rax+rax+00h]
0x14005d4ae  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d4b5  jz      loc_14005D597
0x14005d4bb  mov     edx, 2Dh ; '-'
0x14005d4c0  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005d4c7  jmp     loc_14005D58C
0x14005d4cc  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d4d3  jz      loc_14005D597
0x14005d4d9  mov     edx, 2Eh ; '.'
0x14005d4de  mov     dword ptr [rsp+88h+var_68], eax
0x14005d4e2  mov     ecx, r13d
0x14005d4e5  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005d4ec  mov     r9, rbx
0x14005d4ef  call    WPP_SF_qD
0x14005d4f4  jmp     loc_14005D597
0x14005d4f9  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d500  jz      loc_14005D597
0x14005d506  mov     edx, 2Fh ; '/'
0x14005d50b  mov     [rsp+88h+var_68], rdi
0x14005d510  mov     ecx, r13d
0x14005d513  mov     r9, rbx
0x14005d516  mov     r8, rbp
0x14005d519  call    WPP_SF_qq
0x14005d51e  jmp     short loc_14005D597
0x14005d520  call    AfdUnlockEndpointContext
0x14005d525  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d52c  jz      short loc_14005D597
0x14005d52e  mov     edx, 30h ; '0'
0x14005d533  jmp     short loc_14005D589
0x14005d535  mov     ecx, 0AFDh
0x14005d53a  mov     rdx, rsi
0x14005d53d  cmp     ax, cx
0x14005d540  mov     rcx, rbx
0x14005d543  jnz     short loc_14005D576
0x14005d545  call    AfdUnlockEndpointContext
0x14005d54a  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d551  jz      short loc_14005D566
0x14005d553  mov     edx, 31h ; '1'
0x14005d558  mov     ecx, r13d
0x14005d55b  mov     r9, rbx
0x14005d55e  mov     r8, rbp
0x14005d561  call    WPP_SF_q
0x14005d566  cmp     [rbx+30h], r14
0x14005d56a  jnz     short loc_14005D597
0x14005d56c  mov     rcx, rbx
0x14005d56f  call    AfdSanHelperCleanup
0x14005d574  jmp     short loc_14005D597
0x14005d576  call    AfdUnlockEndpointContext
0x14005d57b  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d582  jz      short loc_14005D597
0x14005d584  mov     edx, 32h ; '2'
0x14005d589  mov     r8, rbp
0x14005d58c  mov     r9, rbx
0x14005d58f  mov     ecx, r13d
0x14005d592  call    WPP_SF_q
0x14005d597  mov     dword ptr [r15], 0
0x14005d59e  mov     al, 1
0x14005d5a0  mov     qword ptr [r15+8], 0
0x14005d5a8  add     rsp, 50h
0x14005d5ac  pop     r15
0x14005d5ae  pop     r14
0x14005d5b0  pop     r13
0x14005d5b2  pop     rdi
0x14005d5b3  pop     rsi
0x14005d5b4  pop     rbp
0x14005d5b5  pop     rbx
0x14005d5b6  retn
```
