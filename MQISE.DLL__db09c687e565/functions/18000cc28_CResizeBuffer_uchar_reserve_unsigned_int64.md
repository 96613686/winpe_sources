# CResizeBuffer<uchar>::reserve(unsigned __int64)

- ea: `0x18000cc28`
- end: `0x18000ccae`
- name: `?reserve@?$CResizeBuffer@E@@QEAAX_K@Z`
- size: `134`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c7c`
- `0x18000bce4`
- `0x18000be1c`

## callees

- `0x18000b98c`
- `0x18000cc28`

## pseudocode

```c
void __fastcall CResizeBuffer<unsigned char>::reserve(__int64 a1, unsigned __int64 a2)
{
  __int64 v2; // r8
  unsigned __int64 v3; // rax
  __int64 v4; // r10
  _BYTE **v5; // rcx
  _BYTE *v6; // rax
  _BYTE *v7; // rax
  char v8; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  if ( v2 )
    v3 = *(_QWORD *)(a1 + 24) - v2;
  else
    v3 = 0;
  if ( v3 < a2 )
  {
    v8 = 0;
    v4 = a1 + 8;
    v5 = (_BYTE **)(a1 + 24);
    if ( v2 )
      v6 = &(*v5)[-v2];
    else
      v6 = 0;
    if ( (unsigned __int64)v6 >= a2 )
    {
      if ( v2 && a2 < (unsigned __int64)&(*v5)[-v2] && (_BYTE *)(v2 + a2) != *v5 )
        *v5 = (_BYTE *)(v2 + a2);
    }
    else
    {
      if ( v2 )
        v7 = &(*v5)[-v2];
      else
        v7 = 0;
      std::vector<unsigned char>::_Insert_n(v4, *v5, a2 - (_QWORD)v7, &v8);
    }
  }
}

```

## disassembly

```asm
0x18000cc28  sub     rsp, 28h
0x18000cc2c  mov     r8, [rcx+10h]
0x18000cc30  test    r8, r8
0x18000cc33  jnz     short loc_18000CC39
0x18000cc35  xor     eax, eax
0x18000cc37  jmp     short loc_18000CC40
0x18000cc39  mov     rax, [rcx+18h]
0x18000cc3d  sub     rax, r8
0x18000cc40  cmp     rax, rdx
0x18000cc43  jnb     short loc_18000CCA9
0x18000cc45  mov     [rsp+28h+arg_0], 0
0x18000cc4a  lea     r10, [rcx+8]
0x18000cc4e  lea     rcx, [r10+10h]
0x18000cc52  test    r8, r8
0x18000cc55  jnz     short loc_18000CC5B
0x18000cc57  xor     eax, eax
0x18000cc59  jmp     short loc_18000CC61
0x18000cc5b  mov     rax, [rcx]
0x18000cc5e  sub     rax, r8
0x18000cc61  cmp     rax, rdx
0x18000cc64  jnb     short loc_18000CC8D
0x18000cc66  test    r8, r8
0x18000cc69  jnz     short loc_18000CC6F
0x18000cc6b  xor     eax, eax
0x18000cc6d  jmp     short loc_18000CC75
0x18000cc6f  mov     rax, [rcx]
0x18000cc72  sub     rax, r8
0x18000cc75  sub     rdx, rax
0x18000cc78  lea     r9, [rsp+28h+arg_0]
0x18000cc7d  mov     r8, rdx
0x18000cc80  mov     rdx, [rcx]
0x18000cc83  mov     rcx, r10
0x18000cc86  call    ?_Insert_n@?$vector@EV?$allocator@E@std@@@std@@IEAAXV?$_Vector_iterator@EV?$allocator@E@std@@@2@_KAEBE@Z; std::vector<uchar>::_Insert_n(std::_Vector_iterator<uchar>,unsigned __int64,uchar const &)
0x18000cc8b  jmp     short loc_18000CCA9
0x18000cc8d  test    r8, r8
0x18000cc90  jz      short loc_18000CCA9
0x18000cc92  mov     rax, [rcx]
0x18000cc95  sub     rax, r8
0x18000cc98  cmp     rdx, rax
0x18000cc9b  jnb     short loc_18000CCA9
0x18000cc9d  lea     rax, [r8+rdx]
0x18000cca1  cmp     rax, [rcx]
0x18000cca4  jz      short loc_18000CCA9
0x18000cca6  mov     [rcx], rax
0x18000cca9  add     rsp, 28h
0x18000ccad  retn
```
