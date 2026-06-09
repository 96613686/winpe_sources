# UaspGetStringDescriptors

- ea: `0x140005be0`
- end: `0x140005d5e`
- name: `UaspGetStringDescriptors`
- size: `382`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005aac`

## callees

- `0x140005944`
- `0x140005be0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005c36`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005cba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005c36`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005cba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d00`

## pseudocode

```c
__int64 __fastcall UaspGetStringDescriptors(__int64 a1, __int64 a2, __int64 a3)
{
  int Descriptor; // ecx
  __int64 v6; // rbx
  unsigned __int64 v7; // rcx
  unsigned int v8; // edx
  __int16 v9; // di
  __int64 v10; // rdx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  int v14; // [rsp+28h] [rbp-40h]
  int v15; // [rsp+28h] [rbp-40h]
  int v16; // [rsp+28h] [rbp-40h]
  int v17; // [rsp+28h] [rbp-40h]
  PVOID P; // [rsp+78h] [rbp+10h] BYREF

  P = 0;
  Descriptor = UaspGetDescriptor(a3, a2, 3, 0, 0, v14, 2u, &P);
  if ( Descriptor < 0 )
    return (unsigned int)Descriptor;
  v6 = *(unsigned __int8 *)P;
  ExFreePoolWithTag(P, 0);
  if ( (unsigned __int8)v6 < 4u || (v6 & 1) != 0 )
    return (unsigned int)-1073741668;
  Descriptor = UaspGetDescriptor(a3, (__int64)&P, 3, 0, 0, v15, v6, &P);
  if ( Descriptor >= 0 )
  {
    v7 = (unsigned __int64)(v6 - 2) >> 1;
    v8 = 2;
    v9 = *((_WORD *)P + 1);
    if ( (unsigned int)v7 >= 2 )
    {
      while ( *((_WORD *)P + v8) != 1033 )
      {
        if ( ++v8 > (unsigned int)v7 )
          goto LABEL_10;
      }
      v9 = 1033;
    }
LABEL_10:
    ExFreePoolWithTag(P, 0);
    Descriptor = UaspGetDescriptor(a3, v10, 3, *(_BYTE *)(*(_QWORD *)(a1 + 32) + 16LL), v9, v16, 2u, &P);
    if ( Descriptor >= 0 )
    {
      v11 = *(unsigned __int8 *)P;
      ExFreePoolWithTag(P, 0);
      if ( v11 >= 4 && (v11 & 1) == 0 )
      {
        Descriptor = UaspGetDescriptor(a3, v12, 3, *(_BYTE *)(*(_QWORD *)(a1 + 32) + 16LL), v9, v17, v11, &P);
        if ( Descriptor >= 0 )
          *(_QWORD *)(a1 + 56) = P;
        return (unsigned int)Descriptor;
      }
      return (unsigned int)-1073741668;
    }
  }
  return (unsigned int)Descriptor;
}

```

## disassembly

```asm
0x140005be0  mov     r11, rsp
0x140005be3  mov     [r11+10h], rdx
0x140005be7  push    rbx
0x140005be8  push    rbp
0x140005be9  push    rsi
0x140005bea  push    rdi
0x140005beb  sub     rsp, 48h
0x140005bef  mov     rsi, rcx
0x140005bf2  mov     qword ptr [r11+10h], 0
0x140005bfa  lea     rcx, [r11+10h]
0x140005bfe  mov     rbp, r8
0x140005c01  mov     [r11-30h], rcx
0x140005c05  xor     eax, eax
0x140005c07  mov     [rsp+68h+var_38], 2
0x140005c0f  mov     rcx, rbp
0x140005c12  xor     r9d, r9d
0x140005c15  mov     [rsp+68h+var_48], ax
0x140005c1a  mov     r8b, 3
0x140005c1d  call    UaspGetDescriptor
0x140005c22  mov     ecx, eax
0x140005c24  test    eax, eax
0x140005c26  js      loc_140005D52
0x140005c2c  mov     rcx, [rsp+68h+P]; P
0x140005c31  xor     edx, edx; Tag
0x140005c33  movzx   ebx, byte ptr [rcx]
0x140005c36  call    cs:__imp_ExFreePoolWithTag
0x140005c3d  nop     dword ptr [rax+rax+00h]
0x140005c42  cmp     bl, 4
0x140005c45  jb      loc_140005D4D
0x140005c4b  test    bl, 1
0x140005c4e  jnz     loc_140005D4D
0x140005c54  xor     ecx, ecx
0x140005c56  lea     rdx, [rsp+68h+P]
0x140005c5b  mov     [rsp+68h+var_30], rdx
0x140005c60  xor     r9d, r9d
0x140005c63  mov     [rsp+68h+var_38], ebx
0x140005c67  mov     r8b, 3
0x140005c6a  mov     [rsp+68h+var_48], cx
0x140005c6f  mov     rcx, rbp
0x140005c72  call    UaspGetDescriptor
0x140005c77  mov     ecx, eax
0x140005c79  test    eax, eax
0x140005c7b  js      loc_140005D52
0x140005c81  mov     r8, [rsp+68h+P]
0x140005c86  lea     rcx, [rbx-2]
0x140005c8a  shr     rcx, 1
0x140005c8d  mov     edx, 2
0x140005c92  movzx   edi, word ptr [r8+2]
0x140005c97  cmp     ecx, edx
0x140005c99  jb      short loc_140005CB5
0x140005c9b  mov     r9d, 409h
0x140005ca1  mov     eax, edx
0x140005ca3  cmp     [r8+rax*2], r9w
0x140005ca8  jz      short loc_140005CB2
0x140005caa  inc     edx
0x140005cac  cmp     edx, ecx
0x140005cae  jbe     short loc_140005CA1
0x140005cb0  jmp     short loc_140005CB5
0x140005cb2  mov     edi, r9d
0x140005cb5  xor     edx, edx; Tag
0x140005cb7  mov     rcx, r8; P
0x140005cba  call    cs:__imp_ExFreePoolWithTag
0x140005cc1  nop     dword ptr [rax+rax+00h]
0x140005cc6  mov     r9, [rsi+20h]
0x140005cca  lea     rax, [rsp+68h+P]
0x140005ccf  mov     [rsp+68h+var_30], rax
0x140005cd4  mov     r8b, 3
0x140005cd7  mov     [rsp+68h+var_38], 2
0x140005cdf  mov     rcx, rbp
0x140005ce2  mov     [rsp+68h+var_48], di
0x140005ce7  mov     r9b, [r9+10h]
0x140005ceb  call    UaspGetDescriptor
0x140005cf0  mov     ecx, eax
0x140005cf2  test    eax, eax
0x140005cf4  js      short loc_140005D52
0x140005cf6  mov     rcx, [rsp+68h+P]; P
0x140005cfb  xor     edx, edx; Tag
0x140005cfd  movzx   ebx, byte ptr [rcx]
0x140005d00  call    cs:__imp_ExFreePoolWithTag
0x140005d07  nop     dword ptr [rax+rax+00h]
0x140005d0c  cmp     ebx, 4
0x140005d0f  jb      short loc_140005D4D
0x140005d11  test    bl, 1
0x140005d14  jnz     short loc_140005D4D
0x140005d16  mov     r9, [rsi+20h]
0x140005d1a  lea     rax, [rsp+68h+P]
0x140005d1f  mov     [rsp+68h+var_30], rax
0x140005d24  mov     r8b, 3
0x140005d27  mov     [rsp+68h+var_38], ebx
0x140005d2b  mov     rcx, rbp
0x140005d2e  mov     [rsp+68h+var_48], di
0x140005d33  mov     r9b, [r9+10h]
0x140005d37  call    UaspGetDescriptor
0x140005d3c  mov     ecx, eax
0x140005d3e  test    eax, eax
0x140005d40  js      short loc_140005D52
0x140005d42  mov     rax, [rsp+68h+P]
0x140005d47  mov     [rsi+38h], rax
0x140005d4b  jmp     short loc_140005D52
0x140005d4d  mov     ecx, 0C000009Ch
0x140005d52  mov     eax, ecx
0x140005d54  add     rsp, 48h
0x140005d58  pop     rdi
0x140005d59  pop     rsi
0x140005d5a  pop     rbp
0x140005d5b  pop     rbx
0x140005d5c  retn
```
