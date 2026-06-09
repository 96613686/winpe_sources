# CreateMappingNames

- ea: `0x14001376c`
- end: `0x14001383b`
- name: `CreateMappingNames`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000874c`

## callees

- `0x14001360c`
- `0x14001376c`
- `0x140013844`

## pseudocode

```c
__int64 __fastcall CreateMappingNames(
        const UNICODE_STRING *a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        const UNICODE_STRING *a4,
        __int64 a5,
        struct _UNICODE_STRING **a6)
{
  __int64 v9; // rdx
  int MappingName; // ebx
  __int64 v11; // rdx

  *(_OWORD *)a6 = 0;
  *((_OWORD *)a6 + 1) = 0;
  MappingName = CreateMappingName(a1, (__int64)a2, a6);
  if ( MappingName < 0 )
    goto LABEL_12;
  if ( a2 && a2->Length )
  {
    MappingName = CreateMappingName(a2, v9, a6 + 1);
    if ( MappingName < 0 )
      goto LABEL_12;
    if ( (*a6)[1].Length != a6[1][1].Length )
    {
LABEL_11:
      MappingName = -1073741811;
      goto LABEL_12;
    }
  }
  MappingName = CreateMappingName(a3, v9, a6 + 2);
  if ( MappingName >= 0 )
  {
    if ( !a4 || !a4->Length )
      return 0;
    MappingName = CreateMappingName(a4, v11, a6 + 3);
    if ( MappingName >= 0 )
    {
      if ( a6[2][1].Length != a6[3][1].Length )
        goto LABEL_11;
      return 0;
    }
  }
LABEL_12:
  DeleteMappingNames(a6);
  return (unsigned int)MappingName;
}

```

## disassembly

```asm
0x14001376c  push    rbx
0x14001376e  push    rbp
0x14001376f  push    rsi
0x140013770  push    rdi
0x140013771  push    r12
0x140013773  push    r14
0x140013775  push    r15
0x140013777  sub     rsp, 20h
0x14001377b  mov     rdi, [rsp+58h+arg_28]
0x140013783  xorps   xmm0, xmm0
0x140013786  mov     r15, r8
0x140013789  mov     rbp, r9
0x14001378c  mov     r8, rdi
0x14001378f  mov     rsi, rdx
0x140013792  movups  xmmword ptr [rdi], xmm0
0x140013795  movups  xmmword ptr [rdi+10h], xmm0
0x140013799  call    CreateMappingName
0x14001379e  xor     r12d, r12d
0x1400137a1  mov     ebx, eax
0x1400137a3  test    eax, eax
0x1400137a5  js      short loc_14001381C
0x1400137a7  test    rsi, rsi
0x1400137aa  jz      short loc_1400137D5
0x1400137ac  cmp     [rsi], r12w
0x1400137b0  jbe     short loc_1400137D5
0x1400137b2  lea     r8, [rdi+8]
0x1400137b6  mov     rcx, rsi; SourceString
0x1400137b9  call    CreateMappingName
0x1400137be  mov     ebx, eax
0x1400137c0  test    eax, eax
0x1400137c2  js      short loc_14001381C
0x1400137c4  mov     rax, [rdi+8]
0x1400137c8  mov     rcx, [rdi]
0x1400137cb  movzx   eax, word ptr [rax+10h]
0x1400137cf  cmp     [rcx+10h], ax
0x1400137d3  jnz     short loc_140013817
0x1400137d5  lea     r8, [rdi+10h]
0x1400137d9  mov     rcx, r15; SourceString
0x1400137dc  call    CreateMappingName
0x1400137e1  mov     ebx, eax
0x1400137e3  test    eax, eax
0x1400137e5  js      short loc_14001381C
0x1400137e7  test    rbp, rbp
0x1400137ea  jz      short loc_140013826
0x1400137ec  cmp     [rbp+0], r12w
0x1400137f1  jbe     short loc_140013826
0x1400137f3  lea     r8, [rdi+18h]
0x1400137f7  mov     rcx, rbp; SourceString
0x1400137fa  call    CreateMappingName
0x1400137ff  mov     ebx, eax
0x140013801  test    eax, eax
0x140013803  js      short loc_14001381C
0x140013805  mov     rax, [rdi+18h]
0x140013809  mov     rdx, [rdi+10h]
0x14001380d  movzx   eax, word ptr [rax+10h]
0x140013811  cmp     [rdx+10h], ax
0x140013815  jz      short loc_140013826
0x140013817  mov     ebx, 0C000000Dh
0x14001381c  mov     rcx, rdi
0x14001381f  call    DeleteMappingNames
0x140013824  jmp     short loc_140013829
0x140013826  mov     ebx, r12d
0x140013829  mov     eax, ebx
0x14001382b  add     rsp, 20h
0x14001382f  pop     r15
0x140013831  pop     r14
0x140013833  pop     r12
0x140013835  pop     rdi
0x140013836  pop     rsi
0x140013837  pop     rbp
0x140013838  pop     rbx
0x140013839  retn
```
