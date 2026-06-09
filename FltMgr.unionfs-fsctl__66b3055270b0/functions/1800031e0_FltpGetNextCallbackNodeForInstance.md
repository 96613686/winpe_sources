# FltpGetNextCallbackNodeForInstance

- ea: `0x1800031e0`
- end: `0x18000336c`
- name: `FltpGetNextCallbackNodeForInstance`
- size: `396`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180002a40`
- `0x1800034c0`
- `0x1800047e0`
- `0x18000c950`
- `0x1800128f0`
- `0x180022370`
- `0x18005d850`

## callees

- `0x1800031e0`
- `0x180024c00`

## import_xrefs

- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180003226`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180003226`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180003284`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180003284`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180003266`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180003266`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800032db`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800032db`
- `ntoskrnl!ExReleaseFastResource` at `0x1800032cf`
- `ntoskrnl!ExReleaseFastResource` at `0x1800032cf`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x180003257`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x180003257`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180003246`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180003246`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18000334b`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18000334b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180003322`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180003322`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x180003316`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x180003316`

## pseudocode

```c
__int64 __fastcall FltpGetNextCallbackNodeForInstance(__int64 a1, unsigned int a2, char a3)
{
  __int64 v3; // rdi
  __int64 v6; // rbp
  __int64 v7; // r14
  __int64 v8; // rbx
  __int64 v9; // r13
  __int64 v10; // r8
  __int64 *i; // rbx
  _BYTE v13[80]; // [rsp+20h] [rbp-78h] BYREF

  v3 = 0;
  v6 = a2;
  memset(v13, 0, 0x48u);
  ExInitializeFastOwnerEntry(v13);
  v7 = *(_QWORD *)(a1 + 64);
  if ( a3 )
  {
    v9 = 0;
  }
  else
  {
    v8 = qword_18003E9A0;
    KeEnterGuardedRegion();
    v9 = ExAcquireCacheAwarePushLockSharedEx(v8, 0);
  }
  KeEnterCriticalRegion();
  LOBYTE(v10) = 1;
  ExAcquireFastResourceShared(v7 + 192, v13, v10);
  for ( i = *(__int64 **)(a1 + 16); i != (__int64 *)(v7 + 296); v3 = 0 )
  {
    if ( (i[8] & 6) == 0 )
    {
      v3 = i[v6 + 36];
      if ( v3 )
      {
        if ( a3 || ExAcquireRundownProtectionCacheAwareEx((PEX_RUNDOWN_REF_CACHE_AWARE)i[5], 1u) )
          break;
      }
    }
    i = (__int64 *)*i;
  }
  ExReleaseFastResource(v7 + 192, v13);
  KeLeaveCriticalRegion();
  if ( !a3 )
  {
    ExReleaseCacheAwarePushLockSharedEx(v9, 0);
    KeLeaveGuardedRegion();
  }
  return v3;
}

```

## disassembly

```asm
0x1800031e0  mov     rax, rsp
0x1800031e3  push    rdi
0x1800031e4  push    r13
0x1800031e6  sub     rsp, 88h
0x1800031ed  mov     [rax+8], rbx
0x1800031f1  xor     edi, edi
0x1800031f3  mov     [rax+10h], rbp
0x1800031f7  mov     [rax+18h], rsi
0x1800031fb  mov     rsi, rcx
0x1800031fe  mov     [rax-18h], r12
0x180003202  lea     rcx, [rax-78h]; void *
0x180003206  mov     [rax-20h], r14
0x18000320a  mov     [rax-28h], r15
0x18000320e  movzx   r15d, r8b
0x180003212  mov     ebp, edx
0x180003214  mov     r8d, 48h ; 'H'; Size
0x18000321a  xor     edx, edx; Val
0x18000321c  call    memset
0x180003221  lea     rcx, [rsp+98h+var_78]
0x180003226  call    cs:__imp_ExInitializeFastOwnerEntry
0x18000322d  nop     dword ptr [rax+rax+00h]
0x180003232  mov     r14, [rsi+40h]
0x180003236  test    r15b, r15b
0x180003239  jnz     loc_180003364
0x18000323f  mov     rbx, cs:qword_18003E9A0
0x180003246  call    cs:__imp_KeEnterGuardedRegion
0x18000324d  nop     dword ptr [rax+rax+00h]
0x180003252  xor     edx, edx
0x180003254  mov     rcx, rbx
0x180003257  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x18000325e  nop     dword ptr [rax+rax+00h]
0x180003263  mov     r13, rax
0x180003266  call    cs:__imp_KeEnterCriticalRegion
0x18000326d  nop     dword ptr [rax+rax+00h]
0x180003272  lea     r12, [r14+0C0h]
0x180003279  mov     r8b, 1
0x18000327c  mov     rcx, r12
0x18000327f  lea     rdx, [rsp+98h+var_78]
0x180003284  call    cs:__imp_ExAcquireFastResourceShared
0x18000328b  nop     dword ptr [rax+rax+00h]
0x180003290  mov     rbx, [rsi+10h]
0x180003294  lea     rsi, [r14+128h]
0x18000329b  mov     r14, [rsp+98h+var_20]
0x1800032a0  cmp     rbx, rsi
0x1800032a3  jz      short loc_1800032C7
0x1800032a5  mov     eax, [rbx+40h]
0x1800032a8  test    al, 6
0x1800032aa  jnz     short loc_1800032BD
0x1800032ac  mov     rdi, [rbx+rbp*8+120h]
0x1800032b4  test    rdi, rdi
0x1800032b7  jnz     loc_18000333D
0x1800032bd  mov     rbx, [rbx]
0x1800032c0  xor     edi, edi
0x1800032c2  cmp     rbx, rsi
0x1800032c5  jnz     short loc_1800032A5
0x1800032c7  lea     rdx, [rsp+98h+var_78]
0x1800032cc  mov     rcx, r12
0x1800032cf  call    cs:__imp_ExReleaseFastResource
0x1800032d6  nop     dword ptr [rax+rax+00h]
0x1800032db  call    cs:__imp_KeLeaveCriticalRegion
0x1800032e2  nop     dword ptr [rax+rax+00h]
0x1800032e7  mov     r12, [rsp+98h+var_18]
0x1800032ef  test    r15b, r15b
0x1800032f2  mov     r15, [rsp+98h+var_28]
0x1800032f7  mov     rsi, [rsp+98h+arg_10]
0x1800032ff  mov     rbp, [rsp+98h+arg_8]
0x180003307  mov     rbx, [rsp+98h+arg_0]
0x18000330f  jnz     short loc_18000332E
0x180003311  xor     edx, edx
0x180003313  mov     rcx, r13
0x180003316  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x18000331d  nop     dword ptr [rax+rax+00h]
0x180003322  call    cs:__imp_KeLeaveGuardedRegion
0x180003329  nop     dword ptr [rax+rax+00h]
0x18000332e  mov     rax, rdi
0x180003331  add     rsp, 88h
0x180003338  pop     r13
0x18000333a  pop     rdi
0x18000333b  retn
0x18000333d  test    r15b, r15b
0x180003340  jnz     short loc_1800032C7
0x180003342  mov     rcx, [rbx+28h]; RunRefCacheAware
0x180003346  mov     edx, 1; Count
0x18000334b  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x180003352  nop     dword ptr [rax+rax+00h]
0x180003357  test    al, al
0x180003359  jz      loc_1800032BD
0x18000335f  jmp     loc_1800032C7
0x180003364  xor     r13d, r13d
0x180003367  jmp     loc_180003266
```
