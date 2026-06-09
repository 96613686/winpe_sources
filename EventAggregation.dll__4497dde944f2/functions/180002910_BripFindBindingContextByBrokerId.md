# BripFindBindingContextByBrokerId

- ea: `0x180002910`
- end: `0x1800029a1`
- name: `BripFindBindingContextByBrokerId`
- size: `145`
- prototype: `__int64 __fastcall(void *Source1)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c80`
- `0x1800026f0`
- `0x1800089c0`
- `0x180008af0`

## callees

- `0x180002910`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x18000293a`
- `ntdll!RtlComputeCrc32` at `0x18000293a`
- `ntdll!RtlGetNextEntryHashTable` at `0x180002997`
- `ntdll!RtlGetNextEntryHashTable` at `0x180002997`
- `ntdll!RtlLookupEntryHashTable` at `0x180002956`
- `ntdll!RtlLookupEntryHashTable` at `0x180002956`
- `ntdll!RtlCompareMemory` at `0x180002971`
- `ntdll!RtlCompareMemory` at `0x180002971`

## pseudocode

```c
__int64 __fastcall BripFindBindingContextByBrokerId(UCHAR *Source1)
{
  ULONG v2; // eax
  __int64 v3; // rdx
  __int64 result; // rax
  __int64 v5; // rbx
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+30h] [rbp-18h]

  v7 = 0;
  v6 = 0;
  v2 = RtlComputeCrc32(0, Source1, 0x10u);
  v3 = 1;
  if ( v2 )
    v3 = v2;
  for ( result = RtlLookupEntryHashTable(BrokerBindingTable, v3, &v6);
        ;
        result = RtlGetNextEntryHashTable(BrokerBindingTable, &v6) )
  {
    v5 = result;
    if ( !result )
      break;
    if ( RtlCompareMemory(Source1, (const void *)(result + 24), 0x10u) == 16 )
      return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180002910  mov     [rsp+arg_0], rbx
0x180002915  push    rdi
0x180002916  sub     rsp, 40h
0x18000291a  mov     rdi, rcx
0x18000291d  mov     [rsp+48h+var_18], 0
0x180002926  xorps   xmm0, xmm0
0x180002929  mov     rdx, rcx; Buffer
0x18000292c  xor     ecx, ecx; InitialCrc
0x18000292e  mov     r8d, 10h; Length
0x180002934  movdqu  [rsp+48h+var_28], xmm0
0x18000293a  call    cs:__imp_RtlComputeCrc32
0x180002940  mov     rcx, cs:BrokerBindingTable
0x180002947  lea     r8, [rsp+48h+var_28]
0x18000294c  test    eax, eax
0x18000294e  mov     edx, 1
0x180002953  cmovnz  edx, eax
0x180002956  call    cs:__imp_RtlLookupEntryHashTable
0x18000295c  mov     rbx, rax
0x18000295f  test    rax, rax
0x180002962  jz      short loc_18000299F
0x180002964  lea     rdx, [rax+18h]; Source2
0x180002968  mov     r8d, 10h; Length
0x18000296e  mov     rcx, rdi; Source1
0x180002971  call    cs:__imp_RtlCompareMemory
0x180002977  cmp     rax, 10h
0x18000297b  jnz     short loc_18000298B
0x18000297d  mov     rax, rbx
0x180002980  mov     rbx, [rsp+48h+arg_0]
0x180002985  add     rsp, 40h
0x180002989  pop     rdi
0x18000298a  retn
0x18000298b  mov     rcx, cs:BrokerBindingTable
0x180002992  lea     rdx, [rsp+48h+var_28]
0x180002997  call    cs:__imp_RtlGetNextEntryHashTable
0x18000299d  jmp     short loc_18000295C
0x18000299f  jmp     short loc_180002980
```
