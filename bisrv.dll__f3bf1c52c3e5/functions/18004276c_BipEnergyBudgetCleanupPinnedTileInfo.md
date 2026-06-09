# BipEnergyBudgetCleanupPinnedTileInfo

- ea: `0x18004276c`
- end: `0x18004281e`
- name: `BipEnergyBudgetCleanupPinnedTileInfo`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004938`
- `0x1800814a4`

## callees

- `0x18004276c`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x180042808`
- `ntdll!RtlDeleteHashTable` at `0x180042808`
- `ntdll!RtlEnumerateEntryHashTable` at `0x1800427af`
- `ntdll!RtlEnumerateEntryHashTable` at `0x1800427c8`
- `ntdll!RtlEnumerateEntryHashTable` at `0x1800427af`
- `ntdll!RtlEnumerateEntryHashTable` at `0x1800427c8`
- `ntdll!RtlInitEnumerationHashTable` at `0x18004279d`
- `ntdll!RtlInitEnumerationHashTable` at `0x18004279d`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800427da`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800427da`
- `ntdll!RtlFreeHeap` at `0x1800427ec`
- `ntdll!RtlFreeHeap` at `0x1800427ec`
- `ntdll!RtlEndEnumerationHashTable` at `0x1800427ff`
- `ntdll!RtlEndEnumerationHashTable` at `0x1800427ff`

## pseudocode

```c
void __fastcall BipEnergyBudgetCleanupPinnedTileInfo(__int64 a1)
{
  __int64 v2; // rsi
  void *v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rdx
  _OWORD v6[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v7; // [rsp+40h] [rbp-18h]

  if ( a1 )
  {
    memset(v6, 0, sizeof(v6));
    v7 = 0;
    if ( (unsigned __int8)RtlInitEnumerationHashTable(a1, v6) )
    {
      v2 = RtlEnumerateEntryHashTable(a1, v6);
      while ( v2 )
      {
        v3 = (void *)v2;
        v4 = RtlEnumerateEntryHashTable(a1, v6);
        v5 = v2;
        v2 = v4;
        RtlRemoveEntryHashTable(a1, v5, 0);
        RtlFreeHeap(BipHeap, 0, v3);
      }
      RtlEndEnumerationHashTable(a1, v6);
      RtlDeleteHashTable(a1);
    }
  }
}

```

## disassembly

```asm
0x18004276c  test    rcx, rcx
0x18004276f  jnz     short loc_180042772
0x180042771  retn
0x180042772  mov     [rsp+arg_0], rbx
0x180042777  mov     [rsp+arg_8], rsi
0x18004277c  push    rdi
0x18004277d  sub     rsp, 50h
0x180042781  xorps   xmm0, xmm0
0x180042784  lea     rdx, [rsp+58h+var_38]
0x180042789  xor     eax, eax
0x18004278b  mov     rdi, rcx
0x18004278e  movups  [rsp+58h+var_38], xmm0
0x180042793  mov     [rsp+58h+var_18], rax
0x180042798  movups  [rsp+58h+var_28], xmm0
0x18004279d  call    cs:__imp_RtlInitEnumerationHashTable
0x1800427a3  test    al, al
0x1800427a5  jz      short loc_18004280E
0x1800427a7  lea     rdx, [rsp+58h+var_38]
0x1800427ac  mov     rcx, rdi
0x1800427af  call    cs:__imp_RtlEnumerateEntryHashTable
0x1800427b5  mov     rsi, rax
0x1800427b8  test    rax, rax
0x1800427bb  jz      short loc_1800427F7
0x1800427bd  lea     rdx, [rsp+58h+var_38]
0x1800427c2  mov     rcx, rdi
0x1800427c5  mov     rbx, rsi
0x1800427c8  call    cs:__imp_RtlEnumerateEntryHashTable
0x1800427ce  xor     r8d, r8d
0x1800427d1  mov     rdx, rbx
0x1800427d4  mov     rcx, rdi
0x1800427d7  mov     rsi, rax
0x1800427da  call    cs:__imp_RtlRemoveEntryHashTable
0x1800427e0  mov     rcx, cs:BipHeap; HeapHandle
0x1800427e7  mov     r8, rbx; P
0x1800427ea  xor     edx, edx; Flags
0x1800427ec  call    cs:__imp_RtlFreeHeap
0x1800427f2  test    rsi, rsi
0x1800427f5  jnz     short loc_1800427BD
0x1800427f7  lea     rdx, [rsp+58h+var_38]
0x1800427fc  mov     rcx, rdi
0x1800427ff  call    cs:__imp_RtlEndEnumerationHashTable
0x180042805  mov     rcx, rdi
0x180042808  call    cs:__imp_RtlDeleteHashTable
0x18004280e  mov     rbx, [rsp+58h+arg_0]
0x180042813  mov     rsi, [rsp+58h+arg_8]
0x180042818  add     rsp, 50h
0x18004281c  pop     rdi
0x18004281d  retn
```
