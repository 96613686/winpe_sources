# CombineOptionArray

- ea: `0x18005bc24`
- end: `0x18005bd12`
- name: `CombineOptionArray`
- size: `238`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800033f4`
- `0x180032d94`
- `0x1800330fc`

## callees

- `0x18002fc04`
- `0x18005bc24`

## pseudocode

```c
__int64 __fastcall CombineOptionArray(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5)
{
  unsigned int v5; // ebx
  __int64 v6; // r10
  unsigned int v7; // esi
  int v8; // r15d
  unsigned int j; // ecx
  __int64 v12; // rax
  unsigned int i; // edi
  unsigned int v14; // edx
  __int64 v15; // rax
  unsigned int v16; // edi
  unsigned int v18; // [rsp+80h] [rbp+18h] BYREF

  v5 = *(_DWORD *)(a1 + 20);
  v6 = 0;
  v7 = *(_DWORD *)(a1 + 24);
  v8 = a4;
  v18 = v7 + v5;
  if ( v7 + v5 < a3 )
  {
    if ( a4 )
    {
      for ( i = 0; i < v5; ++i )
        VCopyOptionSelections(a2, i, v8, i, (__int64)&v18, a3);
    }
    else
    {
      for ( j = 0; j < v5; *(_WORD *)(a2 + 2 * v12) = 255 )
        v12 = j++;
    }
    if ( a5 == v6 )
    {
      v14 = v6;
      if ( v7 )
      {
        do
        {
          v15 = v5 + v14++;
          *(_WORD *)(a2 + 2 * v15) = 255;
        }
        while ( v14 < v7 );
      }
    }
    else
    {
      v16 = v6;
      if ( v7 )
      {
        do
        {
          VCopyOptionSelections(a2, v5 + v16, a5, v16, (__int64)&v18, a3);
          ++v16;
        }
        while ( v16 < v7 );
      }
    }
    LOBYTE(v6) = v18 <= a3;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005bc24  push    rbx
0x18005bc26  push    rbp
0x18005bc27  push    rsi
0x18005bc28  push    rdi
0x18005bc29  push    r14
0x18005bc2b  push    r15
0x18005bc2d  sub     rsp, 38h
0x18005bc31  mov     ebx, [rcx+14h]
0x18005bc34  xor     r10d, r10d
0x18005bc37  mov     esi, [rcx+18h]
0x18005bc3a  mov     r15, r9
0x18005bc3d  mov     ebp, r8d
0x18005bc40  mov     r14, rdx
0x18005bc43  lea     eax, [rsi+rbx]
0x18005bc46  mov     [rsp+68h+arg_10], eax
0x18005bc4d  cmp     eax, r8d
0x18005bc50  jnb     loc_18005BD02
0x18005bc56  test    r9, r9
0x18005bc59  jnz     short loc_18005BC72
0x18005bc5b  mov     ecx, r10d
0x18005bc5e  test    ebx, ebx
0x18005bc60  jz      short loc_18005BCA0
0x18005bc62  mov     eax, ecx
0x18005bc64  inc     ecx
0x18005bc66  mov     word ptr [rdx+rax*2], 0FFh
0x18005bc6c  cmp     ecx, ebx
0x18005bc6e  jb      short loc_18005BC62
0x18005bc70  jmp     short loc_18005BCA0
0x18005bc72  mov     edi, r10d
0x18005bc75  test    ebx, ebx
0x18005bc77  jz      short loc_18005BCA0
0x18005bc79  lea     rax, [rsp+68h+arg_10]
0x18005bc81  mov     [rsp+68h+var_40], ebp
0x18005bc85  mov     r9d, edi
0x18005bc88  mov     [rsp+68h+var_48], rax
0x18005bc8d  mov     r8, r15
0x18005bc90  mov     edx, edi
0x18005bc92  mov     rcx, r14
0x18005bc95  call    VCopyOptionSelections
0x18005bc9a  inc     edi
0x18005bc9c  cmp     edi, ebx
0x18005bc9e  jb      short loc_18005BC79
0x18005bca0  cmp     [rsp+68h+arg_20], r10
0x18005bca8  jnz     short loc_18005BCC3
0x18005bcaa  mov     edx, r10d
0x18005bcad  test    esi, esi
0x18005bcaf  jz      short loc_18005BCF7
0x18005bcb1  lea     eax, [rbx+rdx]
0x18005bcb4  inc     edx
0x18005bcb6  mov     word ptr [r14+rax*2], 0FFh
0x18005bcbd  cmp     edx, esi
0x18005bcbf  jb      short loc_18005BCB1
0x18005bcc1  jmp     short loc_18005BCF7
0x18005bcc3  mov     edi, r10d
0x18005bcc6  test    esi, esi
0x18005bcc8  jz      short loc_18005BCF7
0x18005bcca  mov     r8, [rsp+68h+arg_20]
0x18005bcd2  lea     rax, [rsp+68h+arg_10]
0x18005bcda  lea     edx, [rbx+rdi]
0x18005bcdd  mov     [rsp+68h+var_40], ebp
0x18005bce1  mov     r9d, edi
0x18005bce4  mov     [rsp+68h+var_48], rax
0x18005bce9  mov     rcx, r14
0x18005bcec  call    VCopyOptionSelections
0x18005bcf1  inc     edi
0x18005bcf3  cmp     edi, esi
0x18005bcf5  jb      short loc_18005BCCA
0x18005bcf7  cmp     [rsp+68h+arg_10], ebp
0x18005bcfe  setbe   r10b
0x18005bd02  mov     eax, r10d
0x18005bd05  add     rsp, 38h
0x18005bd09  pop     r15
0x18005bd0b  pop     r14
0x18005bd0d  pop     rdi
0x18005bd0e  pop     rsi
0x18005bd0f  pop     rbp
0x18005bd10  pop     rbx
0x18005bd11  retn
```
