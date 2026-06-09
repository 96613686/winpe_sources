# BipCleanupHashTable

- ea: `0x18004d764`
- end: `0x18004d80f`
- name: `BipCleanupHashTable`
- size: `171`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180083ea0`
- `0x180086d18`

## callees

- `0x18004d764`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x18004d7f9`
- `ntdll!RtlDeleteHashTable` at `0x18004d7f9`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18004d7a0`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18004d7b9`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18004d7a0`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18004d7b9`
- `ntdll!RtlInitEnumerationHashTable` at `0x18004d78e`
- `ntdll!RtlInitEnumerationHashTable` at `0x18004d78e`
- `ntdll!RtlRemoveEntryHashTable` at `0x18004d7cb`
- `ntdll!RtlRemoveEntryHashTable` at `0x18004d7cb`
- `ntdll!RtlFreeHeap` at `0x18004d7dd`
- `ntdll!RtlFreeHeap` at `0x18004d7dd`
- `ntdll!RtlEndEnumerationHashTable` at `0x18004d7f0`
- `ntdll!RtlEndEnumerationHashTable` at `0x18004d7f0`

## pseudocode

```c
__int64 __fastcall BipCleanupHashTable(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rsi
  void *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rdx
  _OWORD v7[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v8; // [rsp+40h] [rbp-18h]

  memset(v7, 0, sizeof(v7));
  v8 = 0;
  result = RtlInitEnumerationHashTable(a1, v7);
  if ( (_BYTE)result )
  {
    v3 = RtlEnumerateEntryHashTable(a1, v7);
    while ( v3 )
    {
      v4 = (void *)v3;
      v5 = RtlEnumerateEntryHashTable(a1, v7);
      v6 = v3;
      v3 = v5;
      RtlRemoveEntryHashTable(a1, v6, 0);
      RtlFreeHeap(BipHeap, 0, v4);
    }
    RtlEndEnumerationHashTable(a1, v7);
    return RtlDeleteHashTable(a1);
  }
  return result;
}

```

## disassembly

```asm
0x18004d764  mov     r11, rsp
0x18004d767  mov     [r11+8], rbx
0x18004d76b  mov     [r11+10h], rsi
0x18004d76f  push    rdi
0x18004d770  sub     rsp, 50h
0x18004d774  xorps   xmm0, xmm0
0x18004d777  lea     rdx, [r11-38h]
0x18004d77b  xor     eax, eax
0x18004d77d  mov     rdi, rcx
0x18004d780  movups  [rsp+58h+var_38], xmm0
0x18004d785  movups  [rsp+58h+var_28], xmm0
0x18004d78a  mov     [r11-18h], rax
0x18004d78e  call    cs:__imp_RtlInitEnumerationHashTable
0x18004d794  test    al, al
0x18004d796  jz      short loc_18004D7FF
0x18004d798  lea     rdx, [rsp+58h+var_38]
0x18004d79d  mov     rcx, rdi
0x18004d7a0  call    cs:__imp_RtlEnumerateEntryHashTable
0x18004d7a6  mov     rsi, rax
0x18004d7a9  test    rax, rax
0x18004d7ac  jz      short loc_18004D7E8
0x18004d7ae  lea     rdx, [rsp+58h+var_38]
0x18004d7b3  mov     rcx, rdi
0x18004d7b6  mov     rbx, rsi
0x18004d7b9  call    cs:__imp_RtlEnumerateEntryHashTable
0x18004d7bf  xor     r8d, r8d
0x18004d7c2  mov     rdx, rbx
0x18004d7c5  mov     rcx, rdi
0x18004d7c8  mov     rsi, rax
0x18004d7cb  call    cs:__imp_RtlRemoveEntryHashTable
0x18004d7d1  mov     rcx, cs:BipHeap; HeapHandle
0x18004d7d8  mov     r8, rbx; P
0x18004d7db  xor     edx, edx; Flags
0x18004d7dd  call    cs:__imp_RtlFreeHeap
0x18004d7e3  test    rsi, rsi
0x18004d7e6  jnz     short loc_18004D7AE
0x18004d7e8  lea     rdx, [rsp+58h+var_38]
0x18004d7ed  mov     rcx, rdi
0x18004d7f0  call    cs:__imp_RtlEndEnumerationHashTable
0x18004d7f6  mov     rcx, rdi
0x18004d7f9  call    cs:__imp_RtlDeleteHashTable
0x18004d7ff  mov     rbx, [rsp+58h+arg_0]
0x18004d804  mov     rsi, [rsp+58h+arg_8]
0x18004d809  add     rsp, 50h
0x18004d80d  pop     rdi
0x18004d80e  retn
```
