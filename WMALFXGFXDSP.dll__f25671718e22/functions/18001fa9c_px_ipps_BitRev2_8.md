# px_ipps_BitRev2_8

- ea: `0x18001fa9c`
- end: `0x18001fb8a`
- name: `px_ipps_BitRev2_8`
- size: `238`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180018990`
- `0x180018af0`
- `0x180018ccc`
- `0x1800196c0`
- `0x1800243d8`
- `0x18002447c`

## callees

- `0x18001fa9c`

## pseudocode

```c
__int64 __fastcall px_ipps_BitRev2_8(_QWORD *a1, _QWORD *a2, int a3, int *a4)
{
  __int64 result; // rax
  __int64 v6; // rax
  _QWORD *v7; // r8
  _QWORD *i; // rbx
  int v9; // ecx

  if ( a3 >= 8 )
  {
    v6 = (__int64)a3 >> 1;
    v7 = &a2[v6];
    for ( i = &a1[v6]; ; v7[(int)result + 1] = i[v9 + 1] )
    {
      LODWORD(result) = *a4 >> 1;
      v9 = a4[1] >> 1;
      if ( (int)result <= 0 )
        break;
      a4 += 2;
      a2[v9] = a1[(int)result];
      a2[v9 + 1] = i[(int)result];
      a2[(int)result] = a1[v9];
      a2[(int)result + 1] = i[v9];
      v7[v9] = a1[(int)result + 1];
      v7[v9 + 1] = i[(int)result + 1];
      v7[(int)result] = a1[v9 + 1];
    }
    do
    {
      ++a4;
      a2[(int)result] = a1[(int)result];
      a2[(int)result + 1] = i[(int)result];
      v7[(int)result] = a1[(int)result + 1];
      v7[(int)result + 1] = i[(int)result + 1];
      result = (unsigned int)(*a4 >> 1);
    }
    while ( (int)result > 0 );
  }
  else
  {
    *a2 = *a1;
    result = a1[a3 - 1];
    a2[a3 - 1] = result;
    if ( a3 > 2 )
    {
      a2[2] = a1[1];
      result = a1[2];
      a2[1] = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001fa9c  mov     [rsp+arg_0], rbx
0x18001faa1  mov     r10, rdx
0x18001faa4  mov     r11, rcx
0x18001faa7  cmp     r8d, 8
0x18001faab  jge     short loc_18001FADF
0x18001faad  mov     rax, [rcx]
0x18001fab0  movsxd  r9, r8d
0x18001fab3  mov     [rdx], rax
0x18001fab6  mov     rax, [rcx+r9*8-8]
0x18001fabb  mov     [rdx+r9*8-8], rax
0x18001fac0  cmp     r8d, 2
0x18001fac4  jle     loc_18001FB84
0x18001faca  mov     rax, [rcx+8]
0x18001face  mov     [rdx+10h], rax
0x18001fad2  mov     rax, [rcx+10h]
0x18001fad6  mov     [rdx+8], rax
0x18001fada  jmp     loc_18001FB84
0x18001fadf  movsxd  rax, r8d
0x18001fae2  sar     rax, 1
0x18001fae5  lea     r8, [rdx+rax*8]
0x18001fae9  lea     rbx, [rcx+rax*8]
0x18001faed  jmp     short loc_18001FB41
0x18001faef  movsxd  rdx, eax
0x18001faf2  movsxd  rcx, ecx
0x18001faf5  add     r9, 8
0x18001faf9  mov     rax, [r11+rdx*8]
0x18001fafd  mov     [r10+rcx*8], rax
0x18001fb01  mov     rax, [rbx+rdx*8]
0x18001fb05  mov     [r10+rcx*8+8], rax
0x18001fb0a  mov     rax, [r11+rcx*8]
0x18001fb0e  mov     [r10+rdx*8], rax
0x18001fb12  mov     rax, [rbx+rcx*8]
0x18001fb16  mov     [r10+rdx*8+8], rax
0x18001fb1b  mov     rax, [r11+rdx*8+8]
0x18001fb20  mov     [r8+rcx*8], rax
0x18001fb24  mov     rax, [rbx+rdx*8+8]
0x18001fb29  mov     [r8+rcx*8+8], rax
0x18001fb2e  mov     rax, [r11+rcx*8+8]
0x18001fb33  mov     [r8+rdx*8], rax
0x18001fb37  mov     rax, [rbx+rcx*8+8]
0x18001fb3c  mov     [r8+rdx*8+8], rax
0x18001fb41  mov     eax, [r9]
0x18001fb44  mov     ecx, [r9+4]
0x18001fb48  sar     eax, 1
0x18001fb4a  sar     ecx, 1
0x18001fb4c  test    eax, eax
0x18001fb4e  jg      short loc_18001FAEF
0x18001fb50  movsxd  rcx, eax
0x18001fb53  lea     r9, [r9+4]
0x18001fb57  mov     rax, [r11+rcx*8]
0x18001fb5b  mov     [r10+rcx*8], rax
0x18001fb5f  mov     rax, [rbx+rcx*8]
0x18001fb63  mov     [r10+rcx*8+8], rax
0x18001fb68  mov     rax, [r11+rcx*8+8]
0x18001fb6d  mov     [r8+rcx*8], rax
0x18001fb71  mov     rax, [rbx+rcx*8+8]
0x18001fb76  mov     [r8+rcx*8+8], rax
0x18001fb7b  mov     eax, [r9]
0x18001fb7e  sar     eax, 1
0x18001fb80  test    eax, eax
0x18001fb82  jg      short loc_18001FB50
0x18001fb84  mov     rbx, [rsp+arg_0]
0x18001fb89  retn
```
