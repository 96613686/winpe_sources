# SrpPolicyTransactionCommit

- ea: `0x140024184`
- end: `0x14002420f`
- name: `SrpPolicyTransactionCommit`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140033f50`

## callees

- `0x140024044`
- `0x140024184`

## import_xrefs

- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400241e1`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400241e1`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14002419a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14002419a`

## pseudocode

```c
__int64 __fastcall SrpPolicyTransactionCommit(_QWORD *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax

  v2 = 0;
  ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
  v3 = *a1 - xmmword_1400193E0;
  if ( *a1 == (_QWORD)xmmword_1400193E0 )
    v3 = a1[1] - *((_QWORD *)&xmmword_1400193E0 + 1);
  if ( !v3 )
  {
    v2 = qword_1400193D8;
    xmmword_1400193E0 = 0;
    qword_1400193D8 = 0;
  }
  ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  if ( !v2 )
    return 3221226002LL;
  ReplacePolicyRef(v2);
  return 0;
}

```

## disassembly

```asm
0x140024184  mov     [rsp+arg_0], rbx
0x140024189  push    rdi
0x14002418a  sub     rsp, 20h
0x14002418e  mov     rdi, rcx
0x140024191  xor     ebx, ebx
0x140024193  lea     rcx, Resource; Resource
0x14002419a  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400241a1  nop     dword ptr [rax+rax+00h]
0x1400241a6  mov     rax, [rdi]
0x1400241a9  sub     rax, qword ptr cs:xmmword_1400193E0
0x1400241b0  jnz     short loc_1400241BD
0x1400241b2  mov     rax, [rdi+8]
0x1400241b6  sub     rax, qword ptr cs:xmmword_1400193E0+8
0x1400241bd  test    rax, rax
0x1400241c0  jnz     short loc_1400241DA
0x1400241c2  mov     rbx, cs:qword_1400193D8
0x1400241c9  xorps   xmm0, xmm0
0x1400241cc  movups  cs:xmmword_1400193E0, xmm0
0x1400241d3  mov     cs:qword_1400193D8, rax
0x1400241da  lea     rcx, Resource; Resource
0x1400241e1  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400241e8  nop     dword ptr [rax+rax+00h]
0x1400241ed  test    rbx, rbx
0x1400241f0  jnz     short loc_1400241F9
0x1400241f2  mov     eax, 0C0000212h
0x1400241f7  jmp     short loc_140024203
0x1400241f9  mov     rcx, rbx
0x1400241fc  call    ReplacePolicyRef
0x140024201  xor     eax, eax
0x140024203  mov     rbx, [rsp+28h+arg_0]
0x140024208  add     rsp, 20h
0x14002420c  pop     rdi
0x14002420d  retn
```
