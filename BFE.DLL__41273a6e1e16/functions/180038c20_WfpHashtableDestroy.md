# WfpHashtableDestroy

- ea: `0x180038c20`
- end: `0x180038cdc`
- name: `WfpHashtableDestroy`
- size: `188`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003f370`
- `0x180068764`
- `0x18006a534`
- `0x18006ba58`
- `0x18006be5c`
- `0x18006df70`
- `0x18008ab08`

## callees

- `0x180038c20`
- `0x18008e010`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x180038c97`
- `ntdll!RtlDeleteHashTable` at `0x180038c97`
- `ntdll!RtlRemoveEntryHashTable` at `0x180038cbd`
- `ntdll!RtlRemoveEntryHashTable` at `0x180038cbd`
- `ntdll!RtlInitEnumerationHashTable` at `0x180038c53`
- `ntdll!RtlInitEnumerationHashTable` at `0x180038c53`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180038c6b`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180038c6b`
- `ntdll!RtlEndEnumerationHashTable` at `0x180038c88`
- `ntdll!RtlEndEnumerationHashTable` at `0x180038c88`

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
0x180038c20  mov     [rsp-8+arg_8], rbx
0x180038c25  mov     [rsp-8+arg_10], rdi
0x180038c2a  push    rbp
0x180038c2b  mov     rbp, rsp
0x180038c2e  sub     rsp, 50h
0x180038c32  xorps   xmm0, xmm0
0x180038c35  mov     [rbp+arg_0], 0
0x180038c3d  mov     rdi, rdx
0x180038c40  mov     rbx, rcx
0x180038c43  lea     rdx, [rbp+var_28]
0x180038c47  movups  xmmword ptr [rbp-30h], xmm0
0x180038c4b  movups  [rbp+var_20], xmm0
0x180038c4f  movups  [rbp+var_10], xmm0
0x180038c53  call    cs:__imp_RtlInitEnumerationHashTable
0x180038c5a  nop     dword ptr [rax+rax+00h]
0x180038c5f  mov     [rbp+var_30], rbx
0x180038c63  mov     rcx, [rbp+var_30]
0x180038c67  lea     rdx, [rbp+var_28]
0x180038c6b  call    cs:__imp_RtlEnumerateEntryHashTable
0x180038c72  nop     dword ptr [rax+rax+00h]
0x180038c77  mov     [rbp+arg_0], rax
0x180038c7b  test    rax, rax
0x180038c7e  jnz     short loc_180038CB4
0x180038c80  mov     rcx, [rbp+var_30]
0x180038c84  lea     rdx, [rbp+var_28]
0x180038c88  call    cs:__imp_RtlEndEnumerationHashTable
0x180038c8f  nop     dword ptr [rax+rax+00h]
0x180038c94  mov     rcx, rbx
0x180038c97  call    cs:__imp_RtlDeleteHashTable
0x180038c9e  nop     dword ptr [rax+rax+00h]
0x180038ca3  mov     rbx, [rsp+50h+arg_8]
0x180038ca8  mov     rdi, [rsp+50h+arg_10]
0x180038cad  add     rsp, 50h
0x180038cb1  pop     rbp
0x180038cb2  retn
0x180038cb4  xor     r8d, r8d
0x180038cb7  mov     rdx, rax
0x180038cba  mov     rcx, rbx
0x180038cbd  call    cs:__imp_RtlRemoveEntryHashTable
0x180038cc4  nop     dword ptr [rax+rax+00h]
0x180038cc9  test    rdi, rdi
0x180038ccc  jz      short loc_180038C63
0x180038cce  lea     rcx, [rbp+arg_0]
0x180038cd2  mov     rax, rdi
0x180038cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038cda  jmp     short loc_180038C63
```
