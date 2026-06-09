# I_ServerCacheCleanup

- ea: `0x180030c0c`
- end: `0x180030c91`
- name: `I_ServerCacheCleanup`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180030c98`
- `0x180030d4c`

## callees

- `0x180014dc0`
- `0x180018514`
- `0x180030c0c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030c19`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030c19`

## pseudocode

```c
__int64 (__fastcall *__fastcall I_ServerCacheCleanup(
        struct _RTL_CRITICAL_SECTION *a1))(struct _RTL_CRITICAL_SECTION *, ULONG_PTR)
{
  ULONG_PTR SpinCount; // rdx
  ULONG_PTR v3; // rbx
  unsigned __int16 *p_Type; // r14
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
      I_ServerCacheFreeItem(a1, SpinCount);
      a1[1].SpinCount = v3;
      SpinCount = v3;
    }
    while ( v3 );
  }
  p_Type = &a1[1].DebugInfo->Type;
  if ( p_Type )
  {
    for ( i = 0; i != 16; ++i )
    {
      v6 = *(_QWORD *)&p_Type[4 * i];
      if ( v6 )
      {
        do
        {
          v7 = *(_QWORD *)(v6 + 16);
          ConstStringHeapFree((unsigned __int16 *)v6);
          v6 = v7;
        }
        while ( v7 );
      }
    }
    ConstStringHeapFree(p_Type);
  }
  result = (__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, ULONG_PTR))a1[1].OwningThread;
  if ( result )
    return (__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, ULONG_PTR))result(a1, SpinCount);
  return result;
}

```

## disassembly

```asm
0x180030c0c  push    rbx
0x180030c0e  push    rsi
0x180030c0f  push    rdi
0x180030c10  push    r14
0x180030c12  sub     rsp, 28h
0x180030c16  mov     rdi, rcx
0x180030c19  call    cs:__imp_DeleteCriticalSection
0x180030c1f  mov     rdx, [rdi+48h]
0x180030c23  test    rdx, rdx
0x180030c26  jz      short loc_180030C40
0x180030c28  mov     rbx, [rdx+30h]
0x180030c2c  mov     rcx, rdi
0x180030c2f  call    I_ServerCacheFreeItem
0x180030c34  mov     [rdi+48h], rbx
0x180030c38  mov     rdx, rbx
0x180030c3b  test    rbx, rbx
0x180030c3e  jnz     short loc_180030C28
0x180030c40  mov     r14, [rdi+28h]
0x180030c44  test    r14, r14
0x180030c47  jz      short loc_180030C76
0x180030c49  xor     esi, esi
0x180030c4b  mov     rcx, [r14+rsi*8]; unsigned __int16 *
0x180030c4f  test    rcx, rcx
0x180030c52  jz      short loc_180030C65
0x180030c54  mov     rbx, [rcx+10h]
0x180030c58  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x180030c5d  mov     rcx, rbx
0x180030c60  test    rbx, rbx
0x180030c63  jnz     short loc_180030C54
0x180030c65  inc     rsi
0x180030c68  cmp     rsi, 10h
0x180030c6c  jnz     short loc_180030C4B
0x180030c6e  mov     rcx, r14; unsigned __int16 *
0x180030c71  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x180030c76  mov     rax, [rdi+38h]
0x180030c7a  test    rax, rax
0x180030c7d  jz      short loc_180030C87
0x180030c7f  mov     rcx, rdi
0x180030c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c87  add     rsp, 28h
0x180030c8b  pop     r14
0x180030c8d  pop     rdi
0x180030c8e  pop     rsi
0x180030c8f  pop     rbx
0x180030c90  retn
```
