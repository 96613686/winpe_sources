# operator delete(void *,std::nothrow_t const &)

- ea: `0x18000c11c`
- end: `0x18000c149`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `45`
- prototype: `void __fastcall(PVOID P, const struct std::nothrow_t *)`
- caller_count: `146`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180003d3c`
- `0x180003d5c`
- `0x180003e28`
- `0x180004050`
- `0x180004310`
- `0x180004350`
- `0x180004390`
- `0x1800043e0`
- `0x180004c30`
- `0x180004eec`
- `0x180005854`
- `0x18000739c`
- `0x18000a710`
- `0x18000ac9c`
- `0x18000bb88`
- `0x18000bc50`
- `0x18000c00c`
- `0x18000c0ac`
- `0x18000cc28`
- `0x18000d480`
- `0x18000d870`
- `0x18000e804`
- `0x18000ea74`
- `0x18000f588`
- `0x18000f670`
- `0x18000f6dc`
- `0x18000f760`
- `0x18000f800`
- `0x18000fde4`
- `0x18000fe98`
- `0x1800100ec`
- `0x180010710`
- `0x180010760`
- `0x180010790`
- `0x1800107d0`
- `0x180010820`
- `0x180010860`
- `0x1800108a0`
- `0x180010dc0`
- `0x180011be0`
- `0x180011c7c`
- `0x180011f48`
- `0x180012684`
- `0x180012ac4`
- `0x180012d70`
- `0x180013ef0`
- `0x180014718`
- `0x1800148d0`
- `0x180016558`
- `0x180018390`

## callees

- `0x18000c11c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000c137`
- `ntdll!RtlFreeHeap` at `0x18000c137`

## pseudocode

```c
void __fastcall operator delete(PVOID P, const struct std::nothrow_t *a2)
{
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
}

```

## disassembly

```asm
0x18000c11c  sub     rsp, 28h
0x18000c120  mov     r8, rcx; P
0x18000c123  test    rcx, rcx
0x18000c126  jz      short loc_18000C143
0x18000c128  mov     rcx, gs:60h
0x18000c131  xor     edx, edx; Flags
0x18000c133  mov     rcx, [rcx+30h]; HeapHandle
0x18000c137  call    cs:__imp_RtlFreeHeap
0x18000c13e  nop     dword ptr [rax+rax+00h]
0x18000c143  add     rsp, 28h
0x18000c147  retn
```
