# UaspGetDescriptors

- ea: `0x140005aac`
- end: `0x140005bda`
- name: `UaspGetDescriptors`
- size: `302`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400015cc`

## callees

- `0x140005944`
- `0x140005aac`
- `0x140005be0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005b46`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005b9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005b46`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005b9d`

## pseudocode

```c
__int64 __fastcall UaspGetDescriptors(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  int Descriptor; // ebx
  unsigned int v7; // esi
  __int64 v8; // rdx
  int v10; // [rsp+28h] [rbp-30h]
  int v11; // [rsp+28h] [rbp-30h]
  int v12; // [rsp+28h] [rbp-30h]
  PVOID P; // [rsp+68h] [rbp+10h] BYREF

  P = 0;
  Descriptor = UaspGetDescriptor(a3, a2, 1, 0, 0, v10, 0x12u, &P);
  if ( Descriptor >= 0 )
  {
    *(_QWORD *)(a1 + 32) = P;
    Descriptor = UaspGetDescriptor(a3, v5, 2, 0, 0, v11, 9u, &P);
    if ( Descriptor >= 0 )
    {
      v7 = *((unsigned __int16 *)P + 1);
      ExFreePoolWithTag(P, 0);
      if ( (unsigned __int16)v7 >= 9u )
      {
        Descriptor = UaspGetDescriptor(a3, (__int64)&P, 2, 0, 0, v12, v7, &P);
        if ( Descriptor >= 0 )
        {
          if ( *((_WORD *)P + 1) <= (unsigned __int16)v7 )
          {
            *(_QWORD *)(a1 + 40) = P;
            if ( *(_BYTE *)(*(_QWORD *)(a1 + 32) + 16LL) )
              UaspGetStringDescriptors(a1, v8, a3);
          }
          else
          {
            Descriptor = -1073741668;
            ExFreePoolWithTag(P, 0);
          }
        }
      }
      else
      {
        return (unsigned int)-1073741668;
      }
    }
  }
  return (unsigned int)Descriptor;
}

```

## disassembly

```asm
0x140005aac  mov     r11, rsp
0x140005aaf  mov     [r11+8], rbx
0x140005ab3  mov     [r11+18h], rbp
0x140005ab7  mov     [r11+10h], rdx
0x140005abb  push    rsi
0x140005abc  push    rdi
0x140005abd  push    r14
0x140005abf  sub     rsp, 40h
0x140005ac3  mov     rdi, rcx
0x140005ac6  mov     qword ptr [r11+10h], 0
0x140005ace  lea     rcx, [r11+10h]
0x140005ad2  mov     rbp, r8
0x140005ad5  mov     [r11-20h], rcx
0x140005ad9  xor     eax, eax
0x140005adb  mov     [rsp+58h+var_28], 12h
0x140005ae3  mov     rcx, rbp
0x140005ae6  xor     r9d, r9d
0x140005ae9  mov     [rsp+58h+var_38], ax
0x140005aee  mov     r8b, 1
0x140005af1  call    UaspGetDescriptor
0x140005af6  mov     ebx, eax
0x140005af8  test    eax, eax
0x140005afa  js      loc_140005BC4
0x140005b00  mov     rax, [rsp+58h+P]
0x140005b05  lea     rcx, [rsp+58h+P]
0x140005b0a  mov     [rsp+58h+var_20], rcx
0x140005b0f  xor     r9d, r9d
0x140005b12  mov     [rdi+20h], rax
0x140005b16  mov     r8b, 2
0x140005b19  xor     eax, eax
0x140005b1b  mov     rcx, rbp
0x140005b1e  lea     r14d, [rax+9]
0x140005b22  mov     [rsp+58h+var_28], r14d
0x140005b27  mov     [rsp+58h+var_38], ax
0x140005b2c  call    UaspGetDescriptor
0x140005b31  mov     ebx, eax
0x140005b33  test    eax, eax
0x140005b35  js      loc_140005BC4
0x140005b3b  mov     rcx, [rsp+58h+P]; P
0x140005b40  xor     edx, edx; Tag
0x140005b42  movzx   esi, word ptr [rcx+2]
0x140005b46  call    cs:__imp_ExFreePoolWithTag
0x140005b4d  nop     dword ptr [rax+rax+00h]
0x140005b52  cmp     si, r14w
0x140005b56  jnb     short loc_140005B5F
0x140005b58  mov     ebx, 0C000009Ch
0x140005b5d  jmp     short loc_140005BC4
0x140005b5f  xor     ecx, ecx
0x140005b61  lea     rdx, [rsp+58h+P]
0x140005b66  mov     [rsp+58h+var_20], rdx
0x140005b6b  xor     r9d, r9d
0x140005b6e  mov     [rsp+58h+var_28], esi
0x140005b72  mov     r8b, 2
0x140005b75  mov     [rsp+58h+var_38], cx
0x140005b7a  mov     rcx, rbp
0x140005b7d  call    UaspGetDescriptor
0x140005b82  mov     ebx, eax
0x140005b84  test    eax, eax
0x140005b86  js      short loc_140005BC4
0x140005b88  mov     rax, [rsp+58h+P]
0x140005b8d  cmp     [rax+2], si
0x140005b91  jbe     short loc_140005BAB
0x140005b93  xor     edx, edx; Tag
0x140005b95  mov     rcx, rax; P
0x140005b98  mov     ebx, 0C000009Ch
0x140005b9d  call    cs:__imp_ExFreePoolWithTag
0x140005ba4  nop     dword ptr [rax+rax+00h]
0x140005ba9  jmp     short loc_140005BC4
0x140005bab  mov     [rdi+28h], rax
0x140005baf  mov     rax, [rdi+20h]
0x140005bb3  cmp     byte ptr [rax+10h], 0
0x140005bb7  jz      short loc_140005BC4
0x140005bb9  mov     r8, rbp
0x140005bbc  mov     rcx, rdi
0x140005bbf  call    UaspGetStringDescriptors
0x140005bc4  mov     rbp, [rsp+58h+arg_10]
0x140005bc9  mov     eax, ebx
0x140005bcb  mov     rbx, [rsp+58h+arg_0]
0x140005bd0  add     rsp, 40h
0x140005bd4  pop     r14
0x140005bd6  pop     rdi
0x140005bd7  pop     rsi
0x140005bd8  retn
```
