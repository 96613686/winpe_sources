# BfpDeleteMappingInformation

- ea: `0x14001e998`
- end: `0x14001ea07`
- name: `BfpDeleteMappingInformation`
- size: `111`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140014a70`
- `0x14001732c`
- `0x14001d194`

## callees

- `0x1400172f0`
- `0x14001e998`
- `0x14001ea10`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001e9ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e9ef`

## pseudocode

```c
void __fastcall BfpDeleteMappingInformation(char *P)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rcx
  _QWORD *v4; // rax

  v2 = P + 64;
  while ( (_QWORD *)*v2 != v2 )
  {
    v3 = (_QWORD *)v2[1];
    if ( (_QWORD *)*v3 != v2 || (v4 = (_QWORD *)v3[1], (_QWORD *)*v4 != v3) )
      __fastfail(3u);
    v2[1] = v4;
    *v4 = v2;
    BfpDeleteTargetEntry(v3);
  }
  BfFreeUnicodeString(P + 16);
  BfFreeUnicodeString(P + 32);
  ExFreePoolWithTag(P, 0x706D4642u);
}

```

## disassembly

```asm
0x14001e998  mov     [rsp+arg_0], rbx
0x14001e99d  push    rdi
0x14001e99e  sub     rsp, 20h
0x14001e9a2  mov     rdi, rcx
0x14001e9a5  lea     rbx, [rcx+40h]
0x14001e9a9  cmp     [rbx], rbx
0x14001e9ac  jz      short loc_14001E9D5
0x14001e9ae  mov     rcx, [rbx+8]; P
0x14001e9b2  cmp     [rcx], rbx
0x14001e9b5  jnz     short loc_14001E9C0
0x14001e9b7  mov     rax, [rcx+8]
0x14001e9bb  cmp     [rax], rcx
0x14001e9be  jz      short loc_14001E9C7
0x14001e9c0  mov     ecx, 3
0x14001e9c5  int     29h; Win8: RtlFailFast(ecx)
0x14001e9c7  mov     [rbx+8], rax
0x14001e9cb  mov     [rax], rbx
0x14001e9ce  call    BfpDeleteTargetEntry
0x14001e9d3  jmp     short loc_14001E9A9
0x14001e9d5  lea     rcx, [rdi+10h]
0x14001e9d9  call    BfFreeUnicodeString
0x14001e9de  lea     rcx, [rdi+20h]
0x14001e9e2  call    BfFreeUnicodeString
0x14001e9e7  mov     edx, 706D4642h; Tag
0x14001e9ec  mov     rcx, rdi; P
0x14001e9ef  call    cs:__imp_ExFreePoolWithTag
0x14001e9f6  nop     dword ptr [rax+rax+00h]
0x14001e9fb  mov     rbx, [rsp+28h+arg_0]
0x14001ea00  add     rsp, 20h
0x14001ea04  pop     rdi
0x14001ea05  retn
```
