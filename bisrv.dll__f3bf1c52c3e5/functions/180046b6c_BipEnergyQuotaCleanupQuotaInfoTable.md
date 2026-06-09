# BipEnergyQuotaCleanupQuotaInfoTable

- ea: `0x180046b6c`
- end: `0x180046c20`
- name: `BipEnergyQuotaCleanupQuotaInfoTable`
- size: `180`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004be40`
- `0x180062998`
- `0x180064db0`

## callees

- `0x180046b6c`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x180046c0a`
- `ntdll!RtlDeleteHashTable` at `0x180046c0a`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180046bb1`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180046bca`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180046bb1`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180046bca`
- `ntdll!RtlInitEnumerationHashTable` at `0x180046b9f`
- `ntdll!RtlInitEnumerationHashTable` at `0x180046b9f`
- `ntdll!RtlRemoveEntryHashTable` at `0x180046bdc`
- `ntdll!RtlRemoveEntryHashTable` at `0x180046bdc`
- `ntdll!RtlFreeHeap` at `0x180046bee`
- `ntdll!RtlFreeHeap` at `0x180046bee`
- `ntdll!RtlEndEnumerationHashTable` at `0x180046c01`
- `ntdll!RtlEndEnumerationHashTable` at `0x180046c01`

## pseudocode

```c
void __fastcall BipEnergyQuotaCleanupQuotaInfoTable(__int64 a1)
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
0x180046b6c  test    rcx, rcx
0x180046b6f  jz      locret_180046C1F
0x180046b75  mov     r11, rsp
0x180046b78  mov     [r11+8], rbx
0x180046b7c  mov     [r11+10h], rsi
0x180046b80  push    rdi
0x180046b81  sub     rsp, 50h
0x180046b85  xorps   xmm0, xmm0
0x180046b88  lea     rdx, [r11-38h]
0x180046b8c  xor     eax, eax
0x180046b8e  mov     rdi, rcx
0x180046b91  movups  [rsp+58h+var_38], xmm0
0x180046b96  movups  [rsp+58h+var_28], xmm0
0x180046b9b  mov     [r11-18h], rax
0x180046b9f  call    cs:__imp_RtlInitEnumerationHashTable
0x180046ba5  test    al, al
0x180046ba7  jz      short loc_180046C10
0x180046ba9  lea     rdx, [rsp+58h+var_38]
0x180046bae  mov     rcx, rdi
0x180046bb1  call    cs:__imp_RtlEnumerateEntryHashTable
0x180046bb7  mov     rsi, rax
0x180046bba  test    rax, rax
0x180046bbd  jz      short loc_180046BF9
0x180046bbf  lea     rdx, [rsp+58h+var_38]
0x180046bc4  mov     rcx, rdi
0x180046bc7  mov     rbx, rsi
0x180046bca  call    cs:__imp_RtlEnumerateEntryHashTable
0x180046bd0  xor     r8d, r8d
0x180046bd3  mov     rdx, rbx
0x180046bd6  mov     rcx, rdi
0x180046bd9  mov     rsi, rax
0x180046bdc  call    cs:__imp_RtlRemoveEntryHashTable
0x180046be2  mov     rcx, cs:BipHeap; HeapHandle
0x180046be9  mov     r8, rbx; P
0x180046bec  xor     edx, edx; Flags
0x180046bee  call    cs:__imp_RtlFreeHeap
0x180046bf4  test    rsi, rsi
0x180046bf7  jnz     short loc_180046BBF
0x180046bf9  lea     rdx, [rsp+58h+var_38]
0x180046bfe  mov     rcx, rdi
0x180046c01  call    cs:__imp_RtlEndEnumerationHashTable
0x180046c07  mov     rcx, rdi
0x180046c0a  call    cs:__imp_RtlDeleteHashTable
0x180046c10  mov     rbx, [rsp+58h+arg_0]
0x180046c15  mov     rsi, [rsp+58h+arg_8]
0x180046c1a  add     rsp, 50h
0x180046c1e  pop     rdi
0x180046c1f  retn
```
