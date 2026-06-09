# CombineOptionArray

- ea: `0x18005d890`
- end: `0x18005d97f`
- name: `CombineOptionArray`
- size: `239`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800034bc`
- `0x18003440c`
- `0x180034774`

## callees

- `0x18003118c`
- `0x18005d890`

## pseudocode

```c
__int64 __fastcall CombineOptionArray(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5)
{
  unsigned int v5; // ebx
  __int64 v6; // r10
  unsigned int v7; // esi
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
  v18 = v7 + v5;
  if ( v7 + v5 < a3 )
  {
    if ( a4 )
    {
      for ( i = 0; i < v5; ++i )
        VCopyOptionSelections(a2, i, a4, i, (int *)&v18, a3);
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
          VCopyOptionSelections(a2, v5 + v16, a5, v16, (int *)&v18, a3);
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
0x18005d890  push    rbx
0x18005d892  push    rbp
0x18005d893  push    rsi
0x18005d894  push    rdi
0x18005d895  push    r14
0x18005d897  push    r15
0x18005d899  sub     rsp, 38h
0x18005d89d  mov     ebx, [rcx+14h]
0x18005d8a0  xor     r10d, r10d
0x18005d8a3  mov     esi, [rcx+18h]
0x18005d8a6  mov     r15, r9
0x18005d8a9  mov     ebp, r8d
0x18005d8ac  mov     r14, rdx
0x18005d8af  lea     eax, [rsi+rbx]
0x18005d8b2  mov     [rsp+68h+arg_10], eax
0x18005d8b9  cmp     eax, r8d
0x18005d8bc  jnb     loc_18005D96E
0x18005d8c2  test    r9, r9
0x18005d8c5  jnz     short loc_18005D8DE
0x18005d8c7  mov     ecx, r10d
0x18005d8ca  test    ebx, ebx
0x18005d8cc  jz      short loc_18005D90C
0x18005d8ce  mov     eax, ecx
0x18005d8d0  inc     ecx
0x18005d8d2  mov     word ptr [rdx+rax*2], 0FFh
0x18005d8d8  cmp     ecx, ebx
0x18005d8da  jb      short loc_18005D8CE
0x18005d8dc  jmp     short loc_18005D90C
0x18005d8de  mov     edi, r10d
0x18005d8e1  test    ebx, ebx
0x18005d8e3  jz      short loc_18005D90C
0x18005d8e5  lea     rax, [rsp+68h+arg_10]
0x18005d8ed  mov     [rsp+68h+var_40], ebp
0x18005d8f1  mov     r9d, edi
0x18005d8f4  mov     [rsp+68h+var_48], rax
0x18005d8f9  mov     r8, r15
0x18005d8fc  mov     edx, edi
0x18005d8fe  mov     rcx, r14
0x18005d901  call    VCopyOptionSelections
0x18005d906  inc     edi
0x18005d908  cmp     edi, ebx
0x18005d90a  jb      short loc_18005D8E5
0x18005d90c  cmp     [rsp+68h+arg_20], r10
0x18005d914  jnz     short loc_18005D92F
0x18005d916  mov     edx, r10d
0x18005d919  test    esi, esi
0x18005d91b  jz      short loc_18005D963
0x18005d91d  lea     eax, [rbx+rdx]
0x18005d920  inc     edx
0x18005d922  mov     word ptr [r14+rax*2], 0FFh
0x18005d929  cmp     edx, esi
0x18005d92b  jb      short loc_18005D91D
0x18005d92d  jmp     short loc_18005D963
0x18005d92f  mov     edi, r10d
0x18005d932  test    esi, esi
0x18005d934  jz      short loc_18005D963
0x18005d936  mov     r8, [rsp+68h+arg_20]
0x18005d93e  lea     rax, [rsp+68h+arg_10]
0x18005d946  lea     edx, [rbx+rdi]
0x18005d949  mov     [rsp+68h+var_40], ebp
0x18005d94d  mov     r9d, edi
0x18005d950  mov     [rsp+68h+var_48], rax
0x18005d955  mov     rcx, r14
0x18005d958  call    VCopyOptionSelections
0x18005d95d  inc     edi
0x18005d95f  cmp     edi, esi
0x18005d961  jb      short loc_18005D936
0x18005d963  cmp     [rsp+68h+arg_10], ebp
0x18005d96a  setbe   r10b
0x18005d96e  mov     eax, r10d
0x18005d971  add     rsp, 38h
0x18005d975  pop     r15
0x18005d977  pop     r14
0x18005d979  pop     rdi
0x18005d97a  pop     rsi
0x18005d97b  pop     rbp
0x18005d97c  pop     rbx
0x18005d97d  retn
```
