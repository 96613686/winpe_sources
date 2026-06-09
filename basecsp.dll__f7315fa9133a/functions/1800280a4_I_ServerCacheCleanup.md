# I_ServerCacheCleanup

- ea: `0x1800280a4`
- end: `0x180028129`
- name: `I_ServerCacheCleanup`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800282ac`
- `0x180028810`

## callees

- `0x18000de80`
- `0x1800280a4`
- `0x180028130`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800280b1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800280b1`

## pseudocode

```c
__int64 (__fastcall *__fastcall I_ServerCacheCleanup(
        struct _RTL_CRITICAL_SECTION *a1))(struct _RTL_CRITICAL_SECTION *, ULONG_PTR)
{
  ULONG_PTR SpinCount; // rdx
  ULONG_PTR v3; // rbx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r14
  __int64 i; // rsi
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 (__fastcall *result)(struct _RTL_CRITICAL_SECTION *, ULONG_PTR); // rax

  DeleteCriticalSection(a1);
  SpinCount = a1[1].SpinCount;
  if ( SpinCount )
  {
    do
    {
      v3 = *(_QWORD *)(SpinCount + 48);
      I_ServerCacheFreeItem(a1);
      a1[1].SpinCount = v3;
      SpinCount = v3;
    }
    while ( v3 );
  }
  DebugInfo = a1[1].DebugInfo;
  if ( DebugInfo )
  {
    for ( i = 0; i != 16; ++i )
    {
      v6 = *((_QWORD *)&DebugInfo->Type + i);
      if ( v6 )
      {
        do
        {
          v7 = *(_QWORD *)(v6 + 16);
          CspFreeH(v6);
          v6 = v7;
        }
        while ( v7 );
      }
    }
    CspFreeH(DebugInfo);
  }
  result = (__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, ULONG_PTR))a1[1].OwningThread;
  if ( result )
    return (__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, ULONG_PTR))result(a1, SpinCount);
  return result;
}

```

## disassembly

```asm
0x1800280a4  push    rbx
0x1800280a6  push    rsi
0x1800280a7  push    rdi
0x1800280a8  push    r14
0x1800280aa  sub     rsp, 28h
0x1800280ae  mov     rdi, rcx
0x1800280b1  call    cs:__imp_DeleteCriticalSection
0x1800280b7  mov     rdx, [rdi+48h]
0x1800280bb  test    rdx, rdx
0x1800280be  jz      short loc_1800280D8
0x1800280c0  mov     rbx, [rdx+30h]
0x1800280c4  mov     rcx, rdi
0x1800280c7  call    I_ServerCacheFreeItem
0x1800280cc  mov     [rdi+48h], rbx
0x1800280d0  mov     rdx, rbx
0x1800280d3  test    rbx, rbx
0x1800280d6  jnz     short loc_1800280C0
0x1800280d8  mov     r14, [rdi+28h]
0x1800280dc  test    r14, r14
0x1800280df  jz      short loc_18002810E
0x1800280e1  xor     esi, esi
0x1800280e3  mov     rcx, [r14+rsi*8]
0x1800280e7  test    rcx, rcx
0x1800280ea  jz      short loc_1800280FD
0x1800280ec  mov     rbx, [rcx+10h]
0x1800280f0  call    CspFreeH
0x1800280f5  mov     rcx, rbx
0x1800280f8  test    rbx, rbx
0x1800280fb  jnz     short loc_1800280EC
0x1800280fd  inc     rsi
0x180028100  cmp     rsi, 10h
0x180028104  jnz     short loc_1800280E3
0x180028106  mov     rcx, r14
0x180028109  call    CspFreeH
0x18002810e  mov     rax, [rdi+38h]
0x180028112  test    rax, rax
0x180028115  jz      short loc_18002811F
0x180028117  mov     rcx, rdi
0x18002811a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002811f  add     rsp, 28h
0x180028123  pop     r14
0x180028125  pop     rdi
0x180028126  pop     rsi
0x180028127  pop     rbx
0x180028128  retn
```
