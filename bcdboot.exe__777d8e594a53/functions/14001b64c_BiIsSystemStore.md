# BiIsSystemStore

- ea: `0x14001b64c`
- end: `0x14001b6e3`
- name: `BiIsSystemStore`
- size: `151`
- prototype: `bool __fastcall(unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14001a8c4`
- `0x14001acec`
- `0x14001b354`
- `0x14001b764`
- `0x14001bd44`
- `0x1400214ec`

## callees

- `0x14001b64c`
- `0x14001b6ec`
- `0x14001f324`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x14001b6c1`
- `ntdll!RtlFreeHeap` at `0x14001b6c1`

## pseudocode

```c
bool __fastcall BiIsSystemStore(unsigned __int64 a1)
{
  char v2; // di
  int v3; // ebx
  ULONG v5; // [rsp+48h] [rbp+10h] BYREF
  PVOID P; // [rsp+50h] [rbp+18h] BYREF

  P = 0;
  v5 = 0;
  v2 = 0;
  if ( (unsigned __int8)BiIsSystemStoreCandidate()
    && (int)BiGetRegistryValue(a1, L"TreatAsSystem", (__int64)L"Description", 4u, &P, &v5) >= 0 )
  {
    v3 = *(_DWORD *)P;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    return v3 != 0;
  }
  return v2;
}

```

## disassembly

```asm
0x14001b64c  mov     [rsp+arg_0], rbx
0x14001b651  push    rdi
0x14001b652  sub     rsp, 30h
0x14001b656  mov     rbx, rcx
0x14001b659  mov     [rsp+38h+P], 0
0x14001b662  mov     [rsp+38h+arg_8], 0
0x14001b66a  xor     dil, dil
0x14001b66d  call    BiIsSystemStoreCandidate
0x14001b672  test    al, al
0x14001b674  jz      short loc_14001B6D5
0x14001b676  lea     rax, [rsp+38h+arg_8]
0x14001b67b  mov     r9d, 4
0x14001b681  mov     [rsp+38h+var_10], rax
0x14001b686  lea     r8, aDescription; "Description"
0x14001b68d  lea     rax, [rsp+38h+P]
0x14001b692  mov     rcx, rbx
0x14001b695  lea     rdx, aTreatassystem; "TreatAsSystem"
0x14001b69c  mov     [rsp+38h+var_18], rax
0x14001b6a1  call    BiGetRegistryValue
0x14001b6a6  test    eax, eax
0x14001b6a8  js      short loc_14001B6D5
0x14001b6aa  mov     rcx, gs:60h
0x14001b6b3  xor     edx, edx; Flags
0x14001b6b5  mov     r8, [rsp+38h+P]; P
0x14001b6ba  mov     rcx, [rcx+30h]; HeapHandle
0x14001b6be  mov     ebx, [r8]
0x14001b6c1  call    cs:__imp_RtlFreeHeap
0x14001b6c7  test    ebx, ebx
0x14001b6c9  movzx   edi, dil
0x14001b6cd  mov     eax, 1
0x14001b6d2  cmovnz  edi, eax
0x14001b6d5  mov     rbx, [rsp+38h+arg_0]
0x14001b6da  mov     al, dil
0x14001b6dd  add     rsp, 30h
0x14001b6e1  pop     rdi
0x14001b6e2  retn
```
