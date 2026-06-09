# av_murmur3_update

- ea: `0x180045360`
- end: `0x180045497`
- name: `av_murmur3_update`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18003ccd0`

## callees

- `0x180045360`
- `0x18007a960`

## pseudocode

```c
void __fastcall av_murmur3_update(__m128i *a1, const __m128i *a2, __int64 a3)
{
  __int64 v3; // r9
  __int64 v5; // r8
  int v7; // eax
  __int64 v8; // rcx
  __int8 v9; // al
  unsigned __int64 v10; // rax
  __int64 v11; // rax
  const __m128i *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int32 v15; // edi

  v3 = a1->m128i_i64[1];
  v5 = a1->m128i_i64[0];
  if ( a3 )
  {
    a1[2].m128i_i64[1] += a3;
    v7 = a1[2].m128i_i32[0];
    if ( v7 > 0 )
    {
      while ( v7 < 16 )
      {
        v8 = v7;
        v9 = a2->m128i_i8[0];
        a2 = (const __m128i *)((char *)a2 + 1);
        a1[1].m128i_i8[v8] = v9;
        v7 = a1[2].m128i_i32[0] + 1;
        a1[2].m128i_i32[0] = v7;
        if ( !--a3 )
          return;
      }
      v10 = 0x87C37B91114253D5uLL * a1[1].m128i_i64[0];
      a1[2].m128i_i32[0] = 0;
      v11 = __ROR8__(v5 ^ (0x4CF5AD432745937FLL * __ROR8__(v10, 33)), 37);
      v5 = v3 + v11 + 4 * (v3 + v11) + 1390208809;
      v3 = 5
         * (v5
          + __ROR8__(v3 ^ (0x87C37B91114253D5uLL * __ROR8__(0x4CF5AD432745937FLL * a1[1].m128i_i64[1], 31)), 33)
          + 188866289LL);
    }
    v12 = (const __m128i *)((char *)a2 + (a3 & 0xFFFFFFFFFFFFFFF0uLL));
    while ( a2 < v12 )
    {
      v13 = __ROR8__(v5 ^ (0x4CF5AD432745937FLL * __ROR8__(0x87C37B91114253D5uLL * a2->m128i_i64[0], 33)), 37);
      v5 = v3 + v13 + 4 * (v3 + v13) + 1390208809;
      v14 = v5
          + __ROR8__(v3 ^ (0x87C37B91114253D5uLL * __ROR8__(0x4CF5AD432745937FLL * a2->m128i_i64[1], 31)), 33)
          + 188866289LL;
      ++a2;
      v3 = 5 * v14;
    }
    a1->m128i_i64[0] = v5;
    a1->m128i_i64[1] = v3;
    v15 = a3 & 0xF;
    if ( v15 )
    {
      sub_18007A960(a1 + 1, a2, v15);
      a1[2].m128i_i32[0] = v15;
    }
  }
}

```

## disassembly

```asm
0x180045360  mov     [rsp+arg_8], rbx
0x180045365  push    rdi
0x180045366  sub     rsp, 20h
0x18004536a  mov     r9, [rcx+8]
0x18004536e  mov     rdi, r8
0x180045371  mov     r8, [rcx]
0x180045374  mov     rbx, rcx
0x180045377  test    rdi, rdi
0x18004537a  jz      loc_18004548C
0x180045380  add     [rcx+28h], rdi
0x180045384  mov     r11, 87C37B91114253D5h
0x18004538e  mov     eax, [rcx+20h]
0x180045391  mov     r10, 4CF5AD432745937Fh
0x18004539b  test    eax, eax
0x18004539d  jle     short loc_180045414
0x18004539f  jmp     short loc_1800453BF
0x1800453a1  movsxd  rcx, eax
0x1800453a4  mov     al, [rdx]
0x1800453a6  inc     rdx
0x1800453a9  mov     [rcx+rbx+10h], al
0x1800453ad  mov     eax, [rbx+20h]
0x1800453b0  inc     eax
0x1800453b2  mov     [rbx+20h], eax
0x1800453b5  sub     rdi, 1
0x1800453b9  jz      loc_18004548C
0x1800453bf  cmp     eax, 10h
0x1800453c2  jl      short loc_1800453A1
0x1800453c4  mov     rax, [rbx+10h]
0x1800453c8  imul    rax, r11
0x1800453cc  mov     dword ptr [rbx+20h], 0
0x1800453d3  ror     rax, 21h
0x1800453d7  imul    rax, r10
0x1800453db  xor     rax, r8
0x1800453de  ror     rax, 25h
0x1800453e2  add     rax, r9
0x1800453e5  lea     r8, ds:52DCE729h[rax*4]
0x1800453ed  add     r8, rax
0x1800453f0  mov     rax, [rbx+18h]
0x1800453f4  imul    rax, r10
0x1800453f8  ror     rax, 1Fh
0x1800453fc  imul    rax, r11
0x180045400  xor     rax, r9
0x180045403  ror     rax, 21h
0x180045407  add     rax, 0B41DEF1h
0x18004540d  add     rax, r8
0x180045410  lea     r9, [rax+rax*4]
0x180045414  mov     rcx, rdi
0x180045417  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18004541b  add     rcx, rdx
0x18004541e  jmp     short loc_18004546C
0x180045420  mov     rax, [rdx]
0x180045423  imul    rax, r11
0x180045427  ror     rax, 21h
0x18004542b  imul    rax, r10
0x18004542f  xor     rax, r8
0x180045432  ror     rax, 25h
0x180045436  add     rax, r9
0x180045439  lea     r8, ds:52DCE729h[rax*4]
0x180045441  add     r8, rax
0x180045444  mov     rax, [rdx+8]
0x180045448  imul    rax, r10
0x18004544c  ror     rax, 1Fh
0x180045450  imul    rax, r11
0x180045454  xor     rax, r9
0x180045457  ror     rax, 21h
0x18004545b  add     rax, 0B41DEF1h
0x180045461  add     rax, r8
0x180045464  add     rdx, 10h
0x180045468  lea     r9, [rax+rax*4]
0x18004546c  cmp     rdx, rcx
0x18004546f  jb      short loc_180045420
0x180045471  mov     [rbx], r8
0x180045474  mov     [rbx+8], r9
0x180045478  and     edi, 0Fh
0x18004547b  jbe     short loc_18004548C
0x18004547d  lea     rcx, [rbx+10h]
0x180045481  mov     r8d, edi
0x180045484  call    sub_18007A960
0x180045489  mov     [rbx+20h], edi
0x18004548c  mov     rbx, [rsp+28h+arg_8]
0x180045491  add     rsp, 20h
0x180045495  pop     rdi
0x180045496  retn
```
