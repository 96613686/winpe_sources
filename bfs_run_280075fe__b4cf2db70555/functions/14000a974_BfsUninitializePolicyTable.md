# BfsUninitializePolicyTable

- ea: `0x14000a974`
- end: `0x14000aa49`
- name: `BfsUninitializePolicyTable`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001e020`
- `0x14001f078`

## callees

- `0x140006040`
- `0x14000a974`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x14000aa1c`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000aa1c`
- `ntoskrnl!ExDeleteTimer` at `0x14000a9af`
- `ntoskrnl!ExDeleteTimer` at `0x14000a9af`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000a9d1`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000a9d1`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000a9f2`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000a9f2`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000aa0c`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000aa0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa2e`

## pseudocode

```c
void __fastcall BfsUninitializePolicyTable(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE *v5; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v6; // rax
  __int128 v7; // [rsp+20h] [rbp-48h] BYREF
  __int64 v8; // [rsp+30h] [rbp-38h]
  _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+38h] [rbp-30h] BYREF

  v4 = *(_QWORD *)(a1 + 32);
  v8 = 0;
  memset(&Enumerator, 0, sizeof(Enumerator));
  v7 = 0;
  if ( v4 )
  {
    LOBYTE(a3) = 1;
    LOBYTE(a2) = 1;
    ((void (__fastcall *)(__int64, __int64, __int64, __int128 *))ExDeleteTimer)(v4, a2, a3, &v7);
    *(_QWORD *)(a1 + 32) = 0;
  }
  v5 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 8);
  if ( v5 )
  {
    RtlInitEnumerationHashTable(v5, &Enumerator);
    while ( 1 )
    {
      v6 = RtlEnumerateEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), &Enumerator);
      if ( !v6 )
        break;
      BfsDereferencePolicyEntryEx(v6);
    }
    RtlEndEnumerationHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), &Enumerator);
    RtlDeleteHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8));
    ExFreePoolWithTag(*(PVOID *)(a1 + 8), 0);
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x14000a974  push    rbx
0x14000a976  sub     rsp, 60h
0x14000a97a  xor     eax, eax
0x14000a97c  xorps   xmm0, xmm0
0x14000a97f  mov     rbx, rcx
0x14000a982  mov     qword ptr [rsp+68h+Enumerator.BucketIndex], rax
0x14000a987  mov     rcx, [rcx+20h]
0x14000a98b  mov     [rsp+68h+var_38], rax
0x14000a990  movups  xmmword ptr [rsp+68h+Enumerator], xmm0
0x14000a995  movups  xmmword ptr [rsp+68h+Enumerator+10h], xmm0
0x14000a99a  movups  [rsp+68h+var_48], xmm0
0x14000a99f  test    rcx, rcx
0x14000a9a2  jz      short loc_14000A9C3
0x14000a9a4  mov     r8b, 1
0x14000a9a7  lea     r9, [rsp+68h+var_48]
0x14000a9ac  mov     dl, r8b
0x14000a9af  call    cs:__imp_ExDeleteTimer
0x14000a9b6  nop     dword ptr [rax+rax+00h]
0x14000a9bb  mov     qword ptr [rbx+20h], 0
0x14000a9c3  mov     rcx, [rbx+8]; HashTable
0x14000a9c7  test    rcx, rcx
0x14000a9ca  jz      short loc_14000AA42
0x14000a9cc  lea     rdx, [rsp+68h+Enumerator]; Enumerator
0x14000a9d1  call    cs:__imp_RtlInitEnumerationHashTable
0x14000a9d8  nop     dword ptr [rax+rax+00h]
0x14000a9dd  jmp     short loc_14000A9E9
0x14000a9df  mov     dl, 1
0x14000a9e1  mov     rcx, rax; P
0x14000a9e4  call    BfsDereferencePolicyEntryEx
0x14000a9e9  mov     rcx, [rbx+8]; HashTable
0x14000a9ed  lea     rdx, [rsp+68h+Enumerator]; Enumerator
0x14000a9f2  call    cs:__imp_RtlEnumerateEntryHashTable
0x14000a9f9  nop     dword ptr [rax+rax+00h]
0x14000a9fe  test    rax, rax
0x14000aa01  jnz     short loc_14000A9DF
0x14000aa03  mov     rcx, [rbx+8]; HashTable
0x14000aa07  lea     rdx, [rsp+68h+Enumerator]; Enumerator
0x14000aa0c  call    cs:__imp_RtlEndEnumerationHashTable
0x14000aa13  nop     dword ptr [rax+rax+00h]
0x14000aa18  mov     rcx, [rbx+8]; HashTable
0x14000aa1c  call    cs:__imp_RtlDeleteHashTable
0x14000aa23  nop     dword ptr [rax+rax+00h]
0x14000aa28  mov     rcx, [rbx+8]; P
0x14000aa2c  xor     edx, edx; Tag
0x14000aa2e  call    cs:__imp_ExFreePoolWithTag
0x14000aa35  nop     dword ptr [rax+rax+00h]
0x14000aa3a  mov     qword ptr [rbx+8], 0
0x14000aa42  add     rsp, 60h
0x14000aa46  pop     rbx
0x14000aa47  retn
```
