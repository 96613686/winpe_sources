# LzmaDec_WriteRem

- ea: `0x140017bdc`
- end: `0x140017c5c`
- name: `LzmaDec_WriteRem`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140016040`
- `0x140017e58`

## callees

- `0x140017bdc`

## pseudocode

```c
char __fastcall LzmaDec_WriteRem(__int64 a1, __int64 a2)
{
  unsigned __int64 v2; // r8
  unsigned int v3; // eax
  unsigned __int64 v4; // r9
  unsigned __int64 v5; // r11
  unsigned __int64 v6; // rdx
  __int64 v7; // r10
  __int64 v8; // rbx

  v2 = *(unsigned int *)(a1 + 92);
  LOBYTE(v3) = v2 - 1;
  if ( (unsigned int)(v2 - 1) <= 0x110 )
  {
    v4 = *(_QWORD *)(a1 + 40);
    v5 = *(unsigned int *)(a1 + 72);
    v6 = a2 - v4;
    if ( v6 >= v2 )
      LODWORD(v6) = *(_DWORD *)(a1 + 92);
    if ( !*(_DWORD *)(a1 + 68) )
    {
      v3 = *(_DWORD *)(a1 + 4) - *(_DWORD *)(a1 + 64);
      if ( v3 <= (unsigned int)v6 )
        *(_DWORD *)(a1 + 68) = *(_DWORD *)(a1 + 4);
    }
    *(_DWORD *)(a1 + 64) += v6;
    *(_DWORD *)(a1 + 92) = v2 - v6;
    if ( (_DWORD)v6 )
    {
      v7 = *(_QWORD *)(a1 + 24);
      v8 = *(_QWORD *)(a1 + 32);
      do
      {
        LOBYTE(v3) = *(_BYTE *)(v7 - v5 + (v8 & -(__int64)(v4 < v5)) + v4);
        *(_BYTE *)(v7 + v4++) = v3;
        LODWORD(v6) = v6 - 1;
      }
      while ( (_DWORD)v6 );
    }
    *(_QWORD *)(a1 + 40) = v4;
  }
  return v3;
}

```

## disassembly

```asm
0x140017bdc  mov     [rsp+arg_0], rbx
0x140017be1  mov     r8d, [rcx+5Ch]
0x140017be5  lea     eax, [r8-1]
0x140017be9  cmp     eax, 110h
0x140017bee  ja      short loc_140017C56
0x140017bf0  mov     r9, [rcx+28h]
0x140017bf4  mov     r11d, [rcx+48h]
0x140017bf8  sub     rdx, r9
0x140017bfb  cmp     rdx, r8
0x140017bfe  cmovnb  edx, r8d
0x140017c02  cmp     dword ptr [rcx+44h], 0
0x140017c06  jnz     short loc_140017C1A
0x140017c08  mov     r10d, [rcx+4]
0x140017c0c  mov     eax, r10d
0x140017c0f  sub     eax, [rcx+40h]
0x140017c12  cmp     eax, edx
0x140017c14  ja      short loc_140017C1A
0x140017c16  mov     [rcx+44h], r10d
0x140017c1a  add     [rcx+40h], edx
0x140017c1d  sub     r8d, edx
0x140017c20  mov     [rcx+5Ch], r8d
0x140017c24  test    edx, edx
0x140017c26  jz      short loc_140017C52
0x140017c28  mov     r10, [rcx+18h]
0x140017c2c  mov     rbx, [rcx+20h]
0x140017c30  mov     r8, r10
0x140017c33  sub     r8, r11
0x140017c36  cmp     r9, r11
0x140017c39  sbb     rax, rax
0x140017c3c  and     rax, rbx
0x140017c3f  add     rax, r8
0x140017c42  mov     al, [rax+r9]
0x140017c46  mov     [r10+r9], al
0x140017c4a  inc     r9
0x140017c4d  add     edx, 0FFFFFFFFh
0x140017c50  jnz     short loc_140017C36
0x140017c52  mov     [rcx+28h], r9
0x140017c56  mov     rbx, [rsp+arg_0]
0x140017c5b  retn
```
