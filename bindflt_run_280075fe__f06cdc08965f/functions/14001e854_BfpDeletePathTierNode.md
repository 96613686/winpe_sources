# BfpDeletePathTierNode

- ea: `0x14001e854`
- end: `0x14001e8b8`
- name: `BfpDeletePathTierNode`
- size: `100`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x14000f3d0`
- `0x140019c44`
- `0x14001cd84`
- `0x14001e818`
- `0x140020228`

## callees

- `0x1400172f0`
- `0x14001732c`
- `0x14001e854`
- `0x14001e8c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001e894`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e894`

## pseudocode

```c
void __fastcall BfpDeletePathTierNode(_QWORD *P)
{
  void *v2; // rcx
  __int64 v3; // rcx

  if ( (*(_DWORD *)P & 0xA) == 0 )
  {
    v2 = (void *)P[10];
    if ( v2 )
    {
      BfpDeletePathTree(v2);
      P[10] = 0;
    }
  }
  v3 = P[9];
  if ( v3 )
    BfReleaseMappingInformation(v3);
  BfFreeUnicodeString(P + 4);
  BfFreeUnicodeString(P + 7);
  ExFreePoolWithTag(P, 0x706D4642u);
}

```

## disassembly

```asm
0x14001e854  push    rbx
0x14001e856  sub     rsp, 20h
0x14001e85a  mov     eax, [rcx]
0x14001e85c  mov     rbx, rcx
0x14001e85f  test    al, 0Ah
0x14001e861  jnz     short loc_14001E86C
0x14001e863  mov     rcx, [rcx+50h]; P
0x14001e867  test    rcx, rcx
0x14001e86a  jnz     short loc_14001E8A7
0x14001e86c  mov     rcx, [rbx+48h]
0x14001e870  test    rcx, rcx
0x14001e873  jz      short loc_14001E87A
0x14001e875  call    BfReleaseMappingInformation
0x14001e87a  lea     rcx, [rbx+20h]
0x14001e87e  call    BfFreeUnicodeString
0x14001e883  lea     rcx, [rbx+38h]
0x14001e887  call    BfFreeUnicodeString
0x14001e88c  mov     edx, 706D4642h; Tag
0x14001e891  mov     rcx, rbx; P
0x14001e894  call    cs:__imp_ExFreePoolWithTag
0x14001e89b  nop     dword ptr [rax+rax+00h]
0x14001e8a0  add     rsp, 20h
0x14001e8a4  pop     rbx
0x14001e8a5  retn
0x14001e8a7  xor     edx, edx
0x14001e8a9  call    BfpDeletePathTree
0x14001e8ae  mov     qword ptr [rbx+50h], 0
0x14001e8b6  jmp     short loc_14001E86C
```
