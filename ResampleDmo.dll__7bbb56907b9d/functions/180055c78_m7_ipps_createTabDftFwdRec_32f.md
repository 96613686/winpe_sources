# m7_ipps_createTabDftFwdRec_32f

- ea: `0x180055c78`
- end: `0x180055d05`
- name: `m7_ipps_createTabDftFwdRec_32f`
- size: `141`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180048f80`
- `0x180049d10`

## callees

- `0x180011040`
- `0x180055c78`

## pseudocode

```c
__int64 __fastcall m7_ipps_createTabDftFwdRec_32f(int a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 result; // rax
  __int64 v5; // r8
  __int64 v6; // rcx
  float *v7; // rax
  __int64 v8; // rdx
  float v9; // xmm0_4
  float v10; // xmm0_4

  v3 = (a1 + 3) / 4;
  result = px_ippsMalloc_8u((unsigned int)(8 * ((a1 + 3) / 4)));
  v5 = result;
  if ( result )
  {
    v6 = v3;
    if ( (int)v3 > 0 )
    {
      v7 = (float *)(a2 + 8);
      v8 = v5 - a2;
      do
      {
        v9 = *v7;
        v7 += 2;
        v10 = v9 * 0.5;
        *(float *)((char *)v7 + v8 - 16) = v10;
        *(float *)((char *)v7 + v8 - 12) = *(v7 - 1) * 0.5 + 0.5;
        --v6;
      }
      while ( v6 );
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180055c78  mov     [rsp+arg_0], rbx
0x180055c7d  push    rdi
0x180055c7e  sub     rsp, 20h
0x180055c82  lea     eax, [rcx+3]
0x180055c85  mov     rdi, rdx
0x180055c88  cdq
0x180055c89  and     edx, 3
0x180055c8c  add     eax, edx
0x180055c8e  sar     eax, 2
0x180055c91  movsxd  rbx, eax
0x180055c94  mov     ecx, ebx
0x180055c96  shl     ecx, 3
0x180055c99  call    px_ippsMalloc_8u
0x180055c9e  mov     r8, rax
0x180055ca1  test    rax, rax
0x180055ca4  jz      short loc_180055CFA
0x180055ca6  mov     rcx, rbx
0x180055ca9  test    ebx, ebx
0x180055cab  jle     short loc_180055CF7
0x180055cad  movsd   xmm2, cs:__real@3fe0000000000000
0x180055cb5  mov     rdx, r8
0x180055cb8  lea     rax, [rdi+8]
0x180055cbc  sub     rdx, rdi
0x180055cbf  movss   xmm0, dword ptr [rax]
0x180055cc3  add     rax, 8
0x180055cc7  cvtps2pd xmm0, xmm0
0x180055cca  mulsd   xmm0, xmm2
0x180055cce  cvtpd2ps xmm0, xmm0
0x180055cd2  movss   dword ptr [rdx+rax-10h], xmm0
0x180055cd8  movss   xmm1, dword ptr [rax-4]
0x180055cdd  cvtps2pd xmm1, xmm1
0x180055ce0  mulsd   xmm1, xmm2
0x180055ce4  addsd   xmm1, xmm2
0x180055ce8  cvtpd2ps xmm0, xmm1
0x180055cec  movss   dword ptr [rdx+rax-0Ch], xmm0
0x180055cf2  dec     rcx
0x180055cf5  jnz     short loc_180055CBF
0x180055cf7  mov     rax, r8
0x180055cfa  mov     rbx, [rsp+28h+arg_0]
0x180055cff  add     rsp, 20h
0x180055d03  pop     rdi
0x180055d04  retn
```
