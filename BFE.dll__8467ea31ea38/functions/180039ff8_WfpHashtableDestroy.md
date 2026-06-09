# WfpHashtableDestroy

- ea: `0x180039ff8`
- end: `0x18003a095`
- name: `WfpHashtableDestroy`
- size: `157`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003e120`
- `0x18006624c`
- `0x180067fac`
- `0x1800694a4`
- `0x180069888`
- `0x18006b948`
- `0x180087b68`

## callees

- `0x180039ff8`
- `0x18008b010`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x18003a05d`
- `ntdll!RtlDeleteHashTable` at `0x18003a05d`
- `ntdll!RtlRemoveEntryHashTable` at `0x18003a07c`
- `ntdll!RtlRemoveEntryHashTable` at `0x18003a07c`
- `ntdll!RtlInitEnumerationHashTable` at `0x18003a02b`
- `ntdll!RtlInitEnumerationHashTable` at `0x18003a02b`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18003a03d`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18003a03d`
- `ntdll!RtlEndEnumerationHashTable` at `0x18003a054`
- `ntdll!RtlEndEnumerationHashTable` at `0x18003a054`

## pseudocode

```c
__int64 __fastcall WfpHashtableDestroy(__int64 a1, void (__fastcall *a2)(__int64 *))
{
  __int64 v4; // rax
  _OWORD v6[3]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v7; // [rsp+60h] [rbp+10h] BYREF

  v7 = 0;
  memset(v6, 0, sizeof(v6));
  RtlInitEnumerationHashTable(a1, (char *)v6 + 8);
  while ( 1 )
  {
    v4 = RtlEnumerateEntryHashTable(a1, (char *)v6 + 8);
    v7 = v4;
    if ( !v4 )
      break;
    RtlRemoveEntryHashTable(a1, v4, 0);
    if ( a2 )
      a2(&v7);
  }
  RtlEndEnumerationHashTable(a1, (char *)v6 + 8);
  return RtlDeleteHashTable(a1);
}

```

## disassembly

```asm
0x180039ff8  mov     [rsp-8+arg_8], rbx
0x180039ffd  mov     [rsp-8+arg_10], rdi
0x18003a002  push    rbp
0x18003a003  mov     rbp, rsp
0x18003a006  sub     rsp, 50h
0x18003a00a  xorps   xmm0, xmm0
0x18003a00d  mov     [rbp+arg_0], 0
0x18003a015  mov     rdi, rdx
0x18003a018  mov     rbx, rcx
0x18003a01b  lea     rdx, [rbp+var_28]
0x18003a01f  movups  xmmword ptr [rbp-30h], xmm0
0x18003a023  movups  [rbp+var_20], xmm0
0x18003a027  movups  [rbp+var_10], xmm0
0x18003a02b  call    cs:__imp_RtlInitEnumerationHashTable
0x18003a031  mov     [rbp+var_30], rbx
0x18003a035  mov     rcx, [rbp+var_30]
0x18003a039  lea     rdx, [rbp+var_28]
0x18003a03d  call    cs:__imp_RtlEnumerateEntryHashTable
0x18003a043  mov     [rbp+arg_0], rax
0x18003a047  test    rax, rax
0x18003a04a  jnz     short loc_18003A073
0x18003a04c  mov     rcx, [rbp+var_30]
0x18003a050  lea     rdx, [rbp+var_28]
0x18003a054  call    cs:__imp_RtlEndEnumerationHashTable
0x18003a05a  mov     rcx, rbx
0x18003a05d  call    cs:__imp_RtlDeleteHashTable
0x18003a063  mov     rbx, [rsp+50h+arg_8]
0x18003a068  mov     rdi, [rsp+50h+arg_10]
0x18003a06d  add     rsp, 50h
0x18003a071  pop     rbp
0x18003a072  retn
0x18003a073  xor     r8d, r8d
0x18003a076  mov     rdx, rax
0x18003a079  mov     rcx, rbx
0x18003a07c  call    cs:__imp_RtlRemoveEntryHashTable
0x18003a082  test    rdi, rdi
0x18003a085  jz      short loc_18003A035
0x18003a087  lea     rcx, [rbp+arg_0]
0x18003a08b  mov     rax, rdi
0x18003a08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a093  jmp     short loc_18003A035
```
