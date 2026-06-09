# AfdSanFastUnlockAll

- ea: `0x14005d0f0`
- end: `0x14005d418`
- name: `AfdSanFastUnlockAll`
- size: `808`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x140019190`
- `0x1400191f0`
- `0x140041928`
- `0x140041a14`
- `0x14005d0f0`
- `0x140093008`
- `0x14009304c`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!IoSetIoCompletion` at `0x14005d22b`
- `ntoskrnl!IoSetIoCompletion` at `0x14005d302`
- `ntoskrnl!IoSetIoCompletion` at `0x14005d22b`
- `ntoskrnl!IoSetIoCompletion` at `0x14005d302`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d1d5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d1d5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d1ad`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d1ad`

## pseudocode

```c
char __fastcall AfdSanFastUnlockAll(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v7; // rsi
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
0x14005d0f0  push    rbx
0x14005d0f2  push    rbp
0x14005d0f3  push    rsi
0x14005d0f4  push    rdi
0x14005d0f5  push    r13
0x14005d0f7  push    r14
0x14005d0f9  push    r15
0x14005d0fb  sub     rsp, 50h
0x14005d0ff  mov     rbx, [rcx+18h]
0x14005d103  mov     rdi, rcx
0x14005d106  mov     rcx, rbx
0x14005d109  mov     r15, r8
0x14005d10c  mov     r14, rdx
0x14005d10f  call    AfdLockEndpointContext
0x14005d114  mov     rsi, rax
0x14005d117  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d11e  lea     rbp, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005d125  mov     r13d, 413h
0x14005d12b  jz      short loc_14005D140
0x14005d12d  mov     edx, 29h ; ')'
0x14005d132  mov     ecx, r13d
0x14005d135  mov     r9, rbx
0x14005d138  mov     r8, rbp
0x14005d13b  call    WPP_SF_q
0x14005d140  movzx   eax, word ptr [rbx]
0x14005d143  mov     ecx, 1AFDh
0x14005d148  cmp     ax, cx
0x14005d14b  jnz     loc_14005D395
0x14005d151  mov     rax, [rbx+60h]
0x14005d155  cmp     [rax+30h], r14
0x14005d159  jnz     loc_14005D291
0x14005d15f  mov     ebp, 0C0000120h
0x14005d164  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d16b  jz      short loc_14005D184
0x14005d16d  mov     edx, 2Ah ; '*'
0x14005d172  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005d179  mov     ecx, r13d
0x14005d17c  mov     r9, rbx
0x14005d17f  call    WPP_SF_q
0x14005d184  mov     rax, cs:AfdSanServiceHelper
0x14005d18b  cmp     [rbx+60h], rax
0x14005d18f  jz      loc_14005D277
0x14005d195  xorps   xmm0, xmm0
0x14005d198  lea     rcx, [rbx+38h]; SpinLock
0x14005d19c  xor     eax, eax
0x14005d19e  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x14005d1a3  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x14005d1a8  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x14005d1ad  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005d1b4  nop     dword ptr [rax+rax+00h]
0x14005d1b9  mov     edi, [rbx+9Ch]
0x14005d1bf  mov     r13d, 103h
0x14005d1c5  test    edi, edi
0x14005d1c7  jnz     short loc_14005D1D0
0x14005d1c9  mov     [rbx+9Ch], r13d
0x14005d1d0  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14005d1d5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005d1dc  nop     dword ptr [rax+rax+00h]
0x14005d1e1  cmp     edi, r13d
0x14005d1e4  jz      short loc_14005D23D
0x14005d1e6  cmp     edi, 0C0000016h
0x14005d1ec  jz      short loc_14005D23D
0x14005d1ee  test    edi, edi
0x14005d1f0  js      loc_14005D277
0x14005d1f6  mov     rdi, [rbx+60h]
0x14005d1fa  mov     eax, 2
0x14005d1ff  lock xadd [rdi+84h], eax
0x14005d207  test    al, 1
0x14005d209  jnz     short loc_14005D24D
0x14005d20b  mov     rax, cs:AfdSanServicePid
0x14005d212  xor     r9d, r9d
0x14005d215  mov     rdx, [rbx+70h]
0x14005d219  mov     rcx, [rdi+70h]
0x14005d21d  mov     [rsp+88h+var_60], 0
0x14005d222  lea     r8d, [r9+3]
0x14005d226  mov     [rsp+88h+var_68], rax
0x14005d22b  call    cs:__imp_IoSetIoCompletion
0x14005d232  nop     dword ptr [rax+rax+00h]
0x14005d237  mov     ebp, eax
0x14005d239  test    eax, eax
0x14005d23b  js      short loc_14005D26F
0x14005d23d  mov     rdx, rsi
0x14005d240  mov     rcx, rbx
0x14005d243  call    AfdUnlockEndpointContext
0x14005d248  jmp     loc_14005D3F7
0x14005d24d  test    byte ptr cs:xmmword_1400875D0+0Ah, 8
0x14005d254  jz      short loc_14005D26F
0x14005d256  mov     edx, 2Bh ; '+'
0x14005d25b  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005d262  mov     ecx, 313h
0x14005d267  mov     r9, r14
0x14005d26a  call    WPP_SF_q
0x14005d26f  lock add dword ptr [rdi+84h], 0FFFFFFFEh
0x14005d277  mov     rdx, rsi
0x14005d27a  mov     rcx, rbx
0x14005d27d  call    AfdUnlockEndpointContext
0x14005d282  mov     edx, ebp
0x14005d284  mov     rcx, rbx
0x14005d287  call    AfdSanRestartRequestProcessing
0x14005d28c  jmp     loc_14005D3F7
0x14005d291  cmp     byte ptr [rbx+0A0h], 0
0x14005d298  mov     rdx, rsi
0x14005d29b  mov     rcx, rbx
0x14005d29e  jz      loc_14005D380
0x14005d2a4  call    AfdUnlockEndpointContext
0x14005d2a9  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d2b0  jz      short loc_14005D2C5
0x14005d2b2  mov     edx, 2Ch ; ','
0x14005d2b7  mov     ecx, r13d
0x14005d2ba  mov     r9, rbx
0x14005d2bd  mov     r8, rbp
0x14005d2c0  call    WPP_SF_q
0x14005d2c5  cmp     qword ptr [rdi-28h], 1
0x14005d2ca  jnz     loc_14005D359
0x14005d2d0  mov     edx, 0C0000120h
0x14005d2d5  mov     rcx, rbx
0x14005d2d8  call    AfdSanRestartRequestProcessing
0x14005d2dd  test    eax, eax
0x14005d2df  js      short loc_14005D32C
0x14005d2e1  mov     rcx, [rbx+60h]
0x14005d2e5  xor     r9d, r9d
0x14005d2e8  mov     rdx, [rbx+70h]
0x14005d2ec  mov     [rsp+88h+var_60], 0
0x14005d2f1  mov     [rsp+88h+var_68], 0
0x14005d2fa  mov     rcx, [rcx+70h]
0x14005d2fe  lea     r8d, [r9+6]
0x14005d302  call    cs:__imp_IoSetIoCompletion
0x14005d309  nop     dword ptr [rax+rax+00h]
0x14005d30e  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d315  jz      loc_14005D3F7
0x14005d31b  mov     edx, 2Dh ; '-'
0x14005d320  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005d327  jmp     loc_14005D3EC
0x14005d32c  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d333  jz      loc_14005D3F7
0x14005d339  mov     edx, 2Eh ; '.'
0x14005d33e  mov     dword ptr [rsp+88h+var_68], eax
0x14005d342  mov     ecx, r13d
0x14005d345  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005d34c  mov     r9, rbx
0x14005d34f  call    WPP_SF_qD
0x14005d354  jmp     loc_14005D3F7
0x14005d359  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d360  jz      loc_14005D3F7
0x14005d366  mov     edx, 2Fh ; '/'
0x14005d36b  mov     [rsp+88h+var_68], rdi
0x14005d370  mov     ecx, r13d
0x14005d373  mov     r9, rbx
0x14005d376  mov     r8, rbp
0x14005d379  call    WPP_SF_qq
0x14005d37e  jmp     short loc_14005D3F7
0x14005d380  call    AfdUnlockEndpointContext
0x14005d385  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d38c  jz      short loc_14005D3F7
0x14005d38e  mov     edx, 30h ; '0'
0x14005d393  jmp     short loc_14005D3E9
0x14005d395  mov     ecx, 0AFDh
0x14005d39a  mov     rdx, rsi
0x14005d39d  cmp     ax, cx
0x14005d3a0  mov     rcx, rbx
0x14005d3a3  jnz     short loc_14005D3D6
0x14005d3a5  call    AfdUnlockEndpointContext
0x14005d3aa  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d3b1  jz      short loc_14005D3C6
0x14005d3b3  mov     edx, 31h ; '1'
0x14005d3b8  mov     ecx, r13d
0x14005d3bb  mov     r9, rbx
0x14005d3be  mov     r8, rbp
0x14005d3c1  call    WPP_SF_q
0x14005d3c6  cmp     [rbx+30h], r14
0x14005d3ca  jnz     short loc_14005D3F7
0x14005d3cc  mov     rcx, rbx
0x14005d3cf  call    AfdSanHelperCleanup
0x14005d3d4  jmp     short loc_14005D3F7
0x14005d3d6  call    AfdUnlockEndpointContext
0x14005d3db  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005d3e2  jz      short loc_14005D3F7
0x14005d3e4  mov     edx, 32h ; '2'
0x14005d3e9  mov     r8, rbp
0x14005d3ec  mov     r9, rbx
0x14005d3ef  mov     ecx, r13d
0x14005d3f2  call    WPP_SF_q
0x14005d3f7  mov     dword ptr [r15], 0
0x14005d3fe  mov     al, 1
0x14005d400  mov     qword ptr [r15+8], 0
0x14005d408  add     rsp, 50h
0x14005d40c  pop     r15
0x14005d40e  pop     r14
0x14005d410  pop     r13
0x14005d412  pop     rdi
0x14005d413  pop     rsi
0x14005d414  pop     rbp
0x14005d415  pop     rbx
0x14005d416  retn
```
