# UbpmRunConsumerQueuedActions

- ea: `0x18000e0a8`
- end: `0x18000e19b`
- name: `UbpmRunConsumerQueuedActions`
- size: `243`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000f880`
- `0x18002fde0`
- `0x180038380`

## callees

- `0x18000e0a8`
- `0x18000e1b0`
- `0x180037e9c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000e171`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000e101`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000e101`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e117`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e117`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e14f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e14f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e123`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e123`

## pseudocode

```c
__int64 __fastcall UbpmRunConsumerQueuedActions(__int64 a1, unsigned int a2, char a3)
{
  struct _GUID *v4; // rcx
  unsigned int v5; // ebx
  unsigned __int64 v8; // rax
  unsigned int v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = 0;
  v4 = (struct _GUID *)(*(_QWORD *)(a1 + 24) + 84LL);
  v5 = 0;
  v8 = -*(_QWORD *)&v4->Data1;
  if ( !*(_QWORD *)&v4->Data1 )
    v8 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] - *(_QWORD *)v4->Data4;
  if ( v8 && (int)UbpmUtilIsNetworkConnected(v4, &v10) >= 0 )
    LOBYTE(v5) = v10 != 0;
  v10 = v5;
  RtlAcquireSRWLockShared(a1 + 48);
  RtlAcquireSRWLockExclusive(a1 + 208);
  *(_DWORD *)(a1 + 216) = GetCurrentThreadId();
  UbpmpRunConsumerQueuedActions(a1, (struct _UBPM_CONSTRAINT_PRECHECK_INFO *)&v10, a2, a3);
  *(_DWORD *)(a1 + 216) = 0;
  RtlReleaseSRWLockExclusive(a1 + 208);
  return RtlReleaseSRWLockShared(a1 + 48);
}

```

## disassembly

```asm
0x18000e0a8  mov     [rsp+arg_8], rbx
0x18000e0ad  mov     [rsp+arg_10], rbp
0x18000e0b2  push    rsi
0x18000e0b3  push    rdi
0x18000e0b4  push    r14
0x18000e0b6  sub     rsp, 20h
0x18000e0ba  mov     rsi, rcx
0x18000e0bd  mov     [rsp+38h+arg_0], 0
0x18000e0c5  mov     rcx, [rcx+18h]
0x18000e0c9  xorps   xmm0, xmm0
0x18000e0cc  add     rcx, 54h ; 'T'; struct _GUID *
0x18000e0d0  xor     ebx, ebx
0x18000e0d2  movq    rax, xmm0
0x18000e0d7  mov     bpl, r8b
0x18000e0da  mov     r14d, edx
0x18000e0dd  sub     rax, [rcx]
0x18000e0e0  jnz     short loc_18000E0F0
0x18000e0e2  psrldq  xmm0, 8
0x18000e0e7  movq    rax, xmm0
0x18000e0ec  sub     rax, [rcx+8]
0x18000e0f0  test    rax, rax
0x18000e0f3  jnz     loc_18000E17D
0x18000e0f9  mov     [rsp+38h+arg_0], ebx
0x18000e0fd  lea     rcx, [rsi+30h]
0x18000e101  call    cs:__imp_RtlAcquireSRWLockShared
0x18000e108  nop     dword ptr [rax+rax+00h]
0x18000e10d  lea     rbx, [rsi+0D0h]
0x18000e114  mov     rcx, rbx
0x18000e117  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000e11e  nop     dword ptr [rax+rax+00h]
0x18000e123  call    cs:__imp_GetCurrentThreadId
0x18000e12a  nop     dword ptr [rax+rax+00h]
0x18000e12f  mov     r9b, bpl
0x18000e132  lea     rdx, [rsp+38h+arg_0]
0x18000e137  mov     r8d, r14d
0x18000e13a  mov     [rbx+8], eax
0x18000e13d  mov     rcx, rsi
0x18000e140  call    ?UbpmpRunConsumerQueuedActions@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@W4_UBPM_QUEUED_ACTION_QUEUE_REASON@@E@Z; UbpmpRunConsumerQueuedActions(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,_UBPM_QUEUED_ACTION_QUEUE_REASON,uchar)
0x18000e145  mov     rcx, rbx
0x18000e148  mov     dword ptr [rbx+8], 0
0x18000e14f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e156  nop     dword ptr [rax+rax+00h]
0x18000e15b  lea     rcx, [rsi+30h]
0x18000e15f  mov     rbx, [rsp+38h+arg_8]
0x18000e164  mov     rbp, [rsp+38h+arg_10]
0x18000e169  add     rsp, 20h
0x18000e16d  pop     r14
0x18000e16f  pop     rdi
0x18000e170  pop     rsi
0x18000e171  jmp     cs:__imp_RtlReleaseSRWLockShared
0x18000e17d  lea     rdx, [rsp+38h+arg_0]; unsigned int *
0x18000e182  call    ?UbpmUtilIsNetworkConnected@@YAJPEAU_GUID@@PEAK@Z; UbpmUtilIsNetworkConnected(_GUID *,ulong *)
0x18000e187  test    eax, eax
0x18000e189  js      loc_18000E0F9
0x18000e18f  cmp     [rsp+38h+arg_0], ebx
0x18000e193  setnz   bl
0x18000e196  jmp     loc_18000E0F9
```
