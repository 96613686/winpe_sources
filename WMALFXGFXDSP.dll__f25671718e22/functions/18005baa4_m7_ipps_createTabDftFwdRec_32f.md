# m7_ipps_createTabDftFwdRec_32f

- ea: `0x18005baa4`
- end: `0x18005bb31`
- name: `m7_ipps_createTabDftFwdRec_32f`
- size: `141`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001da40`
- `0x18001e7d0`

## callees

- `0x18001f910`
- `0x18005baa4`

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
0x18005baa4  mov     [rsp+arg_0], rbx
0x18005baa9  push    rdi
0x18005baaa  sub     rsp, 20h
0x18005baae  lea     eax, [rcx+3]
0x18005bab1  mov     rdi, rdx
0x18005bab4  cdq
0x18005bab5  and     edx, 3
0x18005bab8  add     eax, edx
0x18005baba  sar     eax, 2
0x18005babd  movsxd  rbx, eax
0x18005bac0  mov     ecx, ebx
0x18005bac2  shl     ecx, 3
0x18005bac5  call    px_ippsMalloc_8u
0x18005baca  mov     r8, rax
0x18005bacd  test    rax, rax
0x18005bad0  jz      short loc_18005BB26
0x18005bad2  mov     rcx, rbx
0x18005bad5  test    ebx, ebx
0x18005bad7  jle     short loc_18005BB23
0x18005bad9  movsd   xmm2, cs:__real@3fe0000000000000
0x18005bae1  mov     rdx, r8
0x18005bae4  lea     rax, [rdi+8]
0x18005bae8  sub     rdx, rdi
0x18005baeb  movss   xmm0, dword ptr [rax]
0x18005baef  add     rax, 8
0x18005baf3  cvtps2pd xmm0, xmm0
0x18005baf6  mulsd   xmm0, xmm2
0x18005bafa  cvtpd2ps xmm0, xmm0
0x18005bafe  movss   dword ptr [rdx+rax-10h], xmm0
0x18005bb04  movss   xmm1, dword ptr [rax-4]
0x18005bb09  cvtps2pd xmm1, xmm1
0x18005bb0c  mulsd   xmm1, xmm2
0x18005bb10  addsd   xmm1, xmm2
0x18005bb14  cvtpd2ps xmm0, xmm1
0x18005bb18  movss   dword ptr [rdx+rax-0Ch], xmm0
0x18005bb1e  dec     rcx
0x18005bb21  jnz     short loc_18005BAEB
0x18005bb23  mov     rax, r8
0x18005bb26  mov     rbx, [rsp+28h+arg_0]
0x18005bb2b  add     rsp, 20h
0x18005bb2f  pop     rdi
0x18005bb30  retn
```
