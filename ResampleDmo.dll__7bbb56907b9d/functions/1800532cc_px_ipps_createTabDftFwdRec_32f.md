# px_ipps_createTabDftFwdRec_32f

- ea: `0x1800532cc`
- end: `0x180053355`
- name: `px_ipps_createTabDftFwdRec_32f`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180048120`

## callees

- `0x180011040`
- `0x1800532cc`

## pseudocode

```c
__int64 __fastcall px_ipps_createTabDftFwdRec_32f(int a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 result; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  float *v7; // rax
  __int64 v8; // rbx
  float v9; // xmm0_4

  v3 = (a1 + 3) / 4;
  result = px_ippsMalloc_8u((unsigned int)(8 * ((a1 + 3) / 4)));
  v5 = result;
  if ( result )
  {
    v6 = v3;
    if ( (int)v3 > 0 )
    {
      v7 = (float *)(result + 4);
      v8 = a2 - v5;
      do
      {
        v9 = *(float *)((char *)v7 + v8 - 4) * 0.5;
        *(v7 - 1) = v9;
        *v7 = *(float *)((char *)v7 + v8) * 0.5 + 0.5;
        v7 += 2;
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
0x1800532cc  mov     [rsp+arg_0], rbx
0x1800532d1  push    rdi
0x1800532d2  sub     rsp, 20h
0x1800532d6  lea     eax, [rcx+3]
0x1800532d9  mov     rbx, rdx
0x1800532dc  cdq
0x1800532dd  and     edx, 3
0x1800532e0  add     eax, edx
0x1800532e2  sar     eax, 2
0x1800532e5  movsxd  rdi, eax
0x1800532e8  mov     ecx, edi
0x1800532ea  shl     ecx, 3
0x1800532ed  call    px_ippsMalloc_8u
0x1800532f2  mov     rcx, rax
0x1800532f5  test    rax, rax
0x1800532f8  jz      short loc_18005334A
0x1800532fa  mov     rdx, rdi
0x1800532fd  test    edi, edi
0x1800532ff  jle     short loc_180053347
0x180053301  movsd   xmm2, cs:__real@3fe0000000000000
0x180053309  add     rax, 4
0x18005330d  sub     rbx, rcx
0x180053310  movss   xmm0, dword ptr [rbx+rax-4]
0x180053316  cvtps2pd xmm0, xmm0
0x180053319  mulsd   xmm0, xmm2
0x18005331d  cvtpd2ps xmm0, xmm0
0x180053321  movss   dword ptr [rax-4], xmm0
0x180053326  movss   xmm1, dword ptr [rbx+rax]
0x18005332b  cvtps2pd xmm1, xmm1
0x18005332e  mulsd   xmm1, xmm2
0x180053332  addsd   xmm1, xmm2
0x180053336  cvtpd2ps xmm0, xmm1
0x18005333a  movss   dword ptr [rax], xmm0
0x18005333e  add     rax, 8
0x180053342  dec     rdx
0x180053345  jnz     short loc_180053310
0x180053347  mov     rax, rcx
0x18005334a  mov     rbx, [rsp+28h+arg_0]
0x18005334f  add     rsp, 20h
0x180053353  pop     rdi
0x180053354  retn
```
