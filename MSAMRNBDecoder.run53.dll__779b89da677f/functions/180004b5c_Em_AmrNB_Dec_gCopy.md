# Em_AmrNB_Dec_gCopy

- ea: `0x180004b5c`
- end: `0x180004bab`
- name: `Em_AmrNB_Dec_gCopy`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003800`
- `0x1800051e0`
- `0x180008e48`

## callees

- `0x180004b5c`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gCopy(__int64 a1, __int64 a2, int a3)
{
  __int64 result; // rax
  int v6; // r8d
  int v7; // ecx
  int v8; // r8d
  __int64 v9; // rdx

  result = (unsigned int)(a3 / 2);
  v6 = result;
  if ( (int)result <= 0 )
  {
    v8 = -(int)result;
    v9 = 0;
    if ( (int)result < 0 )
    {
      do
      {
        result = *(unsigned __int16 *)(a1 + 2 * v9);
        *(_WORD *)(a2 + 2 * v9) = result;
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (int)v9 < v8 );
    }
  }
  else
  {
    LODWORD(result) = 1;
    do
    {
      v7 = v6 - result;
      result = (unsigned int)(result + 1);
      *(_WORD *)(a2 + 2LL * v7) = *(_WORD *)(a1 + 2LL * v7);
    }
    while ( (int)result <= v6 );
  }
  return result;
}

```

## disassembly

```asm
0x180004b5c  mov     eax, r8d
0x180004b5f  mov     r9, rdx
0x180004b62  cdq
0x180004b63  mov     r10, rcx
0x180004b66  sub     eax, edx
0x180004b68  sar     eax, 1
0x180004b6a  mov     r8d, eax
0x180004b6d  test    eax, eax
0x180004b6f  jle     short loc_180004B90
0x180004b71  mov     eax, 1
0x180004b76  mov     ecx, r8d
0x180004b79  sub     ecx, eax
0x180004b7b  inc     eax
0x180004b7d  movsxd  rdx, ecx
0x180004b80  movzx   ecx, word ptr [r10+rdx*2]
0x180004b85  mov     [r9+rdx*2], cx
0x180004b8a  cmp     eax, r8d
0x180004b8d  jle     short loc_180004B76
0x180004b8f  retn
0x180004b90  neg     r8d
0x180004b93  xor     edx, edx
0x180004b95  test    r8d, r8d
0x180004b98  jle     short locret_180004BAA
0x180004b9a  movzx   eax, word ptr [rcx+rdx*2]
0x180004b9e  mov     [r9+rdx*2], ax
0x180004ba3  inc     edx
0x180004ba5  cmp     edx, r8d
0x180004ba8  jl      short loc_180004B9A
0x180004baa  retn
```
