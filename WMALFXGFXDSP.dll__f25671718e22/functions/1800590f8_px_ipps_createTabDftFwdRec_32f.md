# px_ipps_createTabDftFwdRec_32f

- ea: `0x1800590f8`
- end: `0x180059181`
- name: `px_ipps_createTabDftFwdRec_32f`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001cbe0`

## callees

- `0x18001f910`
- `0x1800590f8`

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
0x1800590f8  mov     [rsp+arg_0], rbx
0x1800590fd  push    rdi
0x1800590fe  sub     rsp, 20h
0x180059102  lea     eax, [rcx+3]
0x180059105  mov     rbx, rdx
0x180059108  cdq
0x180059109  and     edx, 3
0x18005910c  add     eax, edx
0x18005910e  sar     eax, 2
0x180059111  movsxd  rdi, eax
0x180059114  mov     ecx, edi
0x180059116  shl     ecx, 3
0x180059119  call    px_ippsMalloc_8u
0x18005911e  mov     rcx, rax
0x180059121  test    rax, rax
0x180059124  jz      short loc_180059176
0x180059126  mov     rdx, rdi
0x180059129  test    edi, edi
0x18005912b  jle     short loc_180059173
0x18005912d  movsd   xmm2, cs:__real@3fe0000000000000
0x180059135  add     rax, 4
0x180059139  sub     rbx, rcx
0x18005913c  movss   xmm0, dword ptr [rbx+rax-4]
0x180059142  cvtps2pd xmm0, xmm0
0x180059145  mulsd   xmm0, xmm2
0x180059149  cvtpd2ps xmm0, xmm0
0x18005914d  movss   dword ptr [rax-4], xmm0
0x180059152  movss   xmm1, dword ptr [rbx+rax]
0x180059157  cvtps2pd xmm1, xmm1
0x18005915a  mulsd   xmm1, xmm2
0x18005915e  addsd   xmm1, xmm2
0x180059162  cvtpd2ps xmm0, xmm1
0x180059166  movss   dword ptr [rax], xmm0
0x18005916a  add     rax, 8
0x18005916e  dec     rdx
0x180059171  jnz     short loc_18005913C
0x180059173  mov     rax, rcx
0x180059176  mov     rbx, [rsp+28h+arg_0]
0x18005917b  add     rsp, 20h
0x18005917f  pop     rdi
0x180059180  retn
```
