# u8_ipps_createTabDftDir_32f

- ea: `0x180053c34`
- end: `0x180053cc2`
- name: `u8_ipps_createTabDftDir_32f`
- size: `142`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180048d70`
- `0x180048f80`
- `0x180049b00`
- `0x180049d10`
- `0x180055260`

## callees

- `0x180011040`
- `0x180053c34`

## pseudocode

```c
__int64 __fastcall u8_ipps_createTabDftDir_32f(unsigned int a1, __int64 *a2, int a3)
{
  __int64 v3; // rbx
  __int64 result; // rax
  int v7; // r9d
  __int64 v8; // r10
  __int64 v9; // rdi
  _DWORD *v10; // r8
  __int64 v11; // rax
  __int64 v12; // rax

  v3 = a1;
  result = px_ippsMalloc_8u(16 * a1);
  v7 = 0;
  v8 = result;
  if ( result )
  {
    v9 = 0;
    v10 = (_DWORD *)(result + 8LL * (int)v3);
    if ( (int)v3 > 0 )
    {
      do
      {
        v11 = *a2;
        a2 += a3 / (int)v3;
        *(_QWORD *)(v8 + 8 * v9++) = v11;
      }
      while ( v9 < (int)v3 );
      v12 = v3;
      do
      {
        *v10 = v7;
        v10[(int)v3] = v7;
        v7 += 2;
        ++v10;
        --v12;
      }
      while ( v12 );
    }
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180053c34  mov     [rsp+arg_0], rbx
0x180053c39  mov     [rsp+arg_8], rbp
0x180053c3e  mov     [rsp+arg_10], rsi
0x180053c43  push    rdi
0x180053c44  sub     rsp, 20h
0x180053c48  mov     ebx, ecx
0x180053c4a  shl     ecx, 4
0x180053c4d  mov     ebp, r8d
0x180053c50  mov     rsi, rdx
0x180053c53  call    px_ippsMalloc_8u
0x180053c58  xor     r9d, r9d
0x180053c5b  mov     r10, rax
0x180053c5e  test    rax, rax
0x180053c61  jz      short loc_180053CAD
0x180053c63  movsxd  r11, ebx
0x180053c66  mov     rdi, r9
0x180053c69  lea     r8, [rax+r11*8]
0x180053c6d  test    ebx, ebx
0x180053c6f  jle     short loc_180053CAA
0x180053c71  mov     eax, ebp
0x180053c73  cdq
0x180053c74  idiv    ebx
0x180053c76  movsxd  rcx, eax
0x180053c79  shl     rcx, 3
0x180053c7d  mov     rax, [rsi]
0x180053c80  add     rsi, rcx
0x180053c83  mov     [r10+rdi*8], rax
0x180053c87  inc     rdi
0x180053c8a  cmp     rdi, r11
0x180053c8d  jl      short loc_180053C7D
0x180053c8f  test    ebx, ebx
0x180053c91  jle     short loc_180053CAA
0x180053c93  mov     rax, rbx
0x180053c96  mov     [r8], r9d
0x180053c99  mov     [r8+r11*4], r9d
0x180053c9d  add     r9d, 2
0x180053ca1  lea     r8, [r8+4]
0x180053ca5  dec     rax
0x180053ca8  jnz     short loc_180053C96
0x180053caa  mov     rax, r10
0x180053cad  mov     rbx, [rsp+28h+arg_0]
0x180053cb2  mov     rbp, [rsp+28h+arg_8]
0x180053cb7  mov     rsi, [rsp+28h+arg_10]
0x180053cbc  add     rsp, 20h
0x180053cc0  pop     rdi
0x180053cc1  retn
```
