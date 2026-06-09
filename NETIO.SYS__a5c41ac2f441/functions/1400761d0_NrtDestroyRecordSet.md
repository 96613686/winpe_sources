# NrtDestroyRecordSet

- ea: `0x1400761d0`
- end: `0x14007627d`
- name: `NrtDestroyRecordSet`
- size: `173`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140075fb0`
- `0x140076cd0`

## callees

- `0x1400761d0`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x1400761ec`
- `ntoskrnl!RtlDeleteHashTable` at `0x14007620b`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400761ec`
- `ntoskrnl!RtlDeleteHashTable` at `0x14007620b`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x14007626b`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x14007626b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076223`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076223`
- `cng!BCryptCloseAlgorithmProvider` at `0x140076248`
- `cng!BCryptCloseAlgorithmProvider` at `0x140076248`

## pseudocode

```c
void NrtDestroyRecordSet()
{
  struct _RTL_DYNAMIC_HASH_TABLE *v0; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE *v1; // rcx

  if ( NrtRecordSet )
  {
    v0 = (struct _RTL_DYNAMIC_HASH_TABLE *)NrtRecordSet[40];
    if ( v0 )
      RtlDeleteHashTable(v0);
    v1 = (struct _RTL_DYNAMIC_HASH_TABLE *)NrtRecordSet[41];
    if ( v1 )
      RtlDeleteHashTable(v1);
    ExFreePoolWithTag(NrtRecordSet, 0x7274724Eu);
    NrtRecordSet = 0;
  }
  if ( NrtRngHandle )
  {
    BCryptCloseAlgorithmProvider(NrtRngHandle, 0);
    NrtRngHandle = 0;
  }
  if ( NrtContainerRestoreWnfSubscription )
    ExUnsubscribeWnfStateChange();
}

```

## disassembly

```asm
0x1400761d0  sub     rsp, 28h
0x1400761d4  mov     rax, cs:NrtRecordSet
0x1400761db  test    rax, rax
0x1400761de  jz      short loc_14007623A
0x1400761e0  mov     rcx, [rax+140h]; HashTable
0x1400761e7  test    rcx, rcx
0x1400761ea  jz      short loc_1400761F8
0x1400761ec  call    cs:__imp_RtlDeleteHashTable
0x1400761f3  nop     dword ptr [rax+rax+00h]
0x1400761f8  mov     rax, cs:NrtRecordSet
0x1400761ff  mov     rcx, [rax+148h]; HashTable
0x140076206  test    rcx, rcx
0x140076209  jz      short loc_140076217
0x14007620b  call    cs:__imp_RtlDeleteHashTable
0x140076212  nop     dword ptr [rax+rax+00h]
0x140076217  mov     rcx, cs:NrtRecordSet; P
0x14007621e  mov     edx, 7274724Eh; Tag
0x140076223  call    cs:__imp_ExFreePoolWithTag
0x14007622a  nop     dword ptr [rax+rax+00h]
0x14007622f  mov     cs:NrtRecordSet, 0
0x14007623a  mov     rcx, cs:NrtRngHandle; hAlgorithm
0x140076241  test    rcx, rcx
0x140076244  jz      short loc_14007625F
0x140076246  xor     edx, edx; dwFlags
0x140076248  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14007624f  nop     dword ptr [rax+rax+00h]
0x140076254  mov     cs:NrtRngHandle, 0
0x14007625f  mov     rcx, cs:NrtContainerRestoreWnfSubscription
0x140076266  test    rcx, rcx
0x140076269  jz      short loc_140076277
0x14007626b  call    cs:__imp_ExUnsubscribeWnfStateChange
0x140076272  nop     dword ptr [rax+rax+00h]
0x140076277  add     rsp, 28h
0x14007627b  retn
```
