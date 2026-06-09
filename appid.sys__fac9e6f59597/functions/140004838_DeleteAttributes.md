# DeleteAttributes

- ea: `0x140004838`
- end: `0x1400048b1`
- name: `DeleteAttributes`
- size: `121`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140005568`
- `0x1400058c8`
- `0x140005994`

## callees

- `0x140004838`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000486a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004883`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004894`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000486a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004883`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004894`

## pseudocode

```c
void __fastcall DeleteAttributes(PVOID P)
{
  __int64 i; // rsi
  void *v3; // rcx

  if ( P )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)P + 1); i = (unsigned int)(i + 1) )
    {
      v3 = *(void **)(*((_QWORD *)P + 1) + 40 * i + 32);
      if ( v3 )
        ExFreePoolWithTag(v3, 0);
    }
    ExFreePoolWithTag(*((PVOID *)P + 1), 0);
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x140004838  test    rcx, rcx
0x14000483b  jz      short locret_1400048AF
0x14000483d  mov     [rsp+arg_0], rbx
0x140004842  mov     [rsp+arg_8], rsi
0x140004847  push    rdi
0x140004848  sub     rsp, 20h
0x14000484c  xor     esi, esi
0x14000484e  mov     rbx, rcx
0x140004851  cmp     [rcx+4], esi
0x140004854  jbe     short loc_14000487D
0x140004856  mov     rax, [rbx+8]
0x14000485a  lea     rcx, [rsi+rsi*4]
0x14000485e  mov     rcx, [rax+rcx*8+20h]; P
0x140004863  test    rcx, rcx
0x140004866  jz      short loc_140004876
0x140004868  xor     edx, edx; Tag
0x14000486a  call    cs:__imp_ExFreePoolWithTag
0x140004871  nop     dword ptr [rax+rax+00h]
0x140004876  inc     esi
0x140004878  cmp     esi, [rbx+4]
0x14000487b  jb      short loc_140004856
0x14000487d  mov     rcx, [rbx+8]; P
0x140004881  xor     edx, edx; Tag
0x140004883  call    cs:__imp_ExFreePoolWithTag
0x14000488a  nop     dword ptr [rax+rax+00h]
0x14000488f  xor     edx, edx; Tag
0x140004891  mov     rcx, rbx; P
0x140004894  call    cs:__imp_ExFreePoolWithTag
0x14000489b  nop     dword ptr [rax+rax+00h]
0x1400048a0  mov     rbx, [rsp+28h+arg_0]
0x1400048a5  mov     rsi, [rsp+28h+arg_8]
0x1400048aa  add     rsp, 20h
0x1400048ae  pop     rdi
0x1400048af  retn
```
