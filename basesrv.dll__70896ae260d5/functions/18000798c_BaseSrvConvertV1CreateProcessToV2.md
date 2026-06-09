# BaseSrvConvertV1CreateProcessToV2

- ea: `0x18000798c`
- end: `0x180007a6e`
- name: `BaseSrvConvertV1CreateProcessToV2`
- size: `226`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007cf0`

## callees

- `0x18000d713`

## pseudocode

```c
void *__fastcall BaseSrvConvertV1CreateProcessToV2(__int64 a1, __int64 a2)
{
  void *result; // rax

  *(_OWORD *)a2 = *(_OWORD *)a1;
  *(_OWORD *)(a2 + 16) = *(_OWORD *)(a1 + 16);
  *(_OWORD *)(a2 + 32) = *(_OWORD *)(a1 + 32);
  *(_QWORD *)(a2 + 48) = *(_QWORD *)(a1 + 48);
  *(_OWORD *)(a2 + 56) = *(_OWORD *)(a1 + 56);
  *(_OWORD *)(a2 + 72) = *(_OWORD *)(a1 + 72);
  *(_OWORD *)(a2 + 88) = *(_OWORD *)(a1 + 88);
  *(_OWORD *)(a2 + 104) = *(_OWORD *)(a1 + 104);
  *(_OWORD *)(a2 + 120) = *(_OWORD *)(a1 + 120);
  *(_OWORD *)(a2 + 136) = *(_OWORD *)(a1 + 136);
  *(_OWORD *)(a2 + 152) = *(_OWORD *)(a1 + 152);
  *(_OWORD *)(a2 + 168) = *(_OWORD *)(a1 + 168);
  *(_OWORD *)(a2 + 184) = *(_OWORD *)(a1 + 184);
  *(_OWORD *)(a2 + 200) = *(_OWORD *)(a1 + 200);
  *(_OWORD *)(a2 + 216) = *(_OWORD *)(a1 + 216);
  *(_QWORD *)(a2 + 232) = *(_QWORD *)(a1 + 232);
  result = memset_0((void *)(a2 + 240), 0, 0x110u);
  *(_OWORD *)(a2 + 512) = *(_OWORD *)(a1 + 240);
  *(_QWORD *)(a2 + 528) = *(_QWORD *)(a1 + 256);
  return result;
}

```

## disassembly

```asm
0x18000798c  mov     [rsp+arg_0], rbx
0x180007991  push    rdi
0x180007992  sub     rsp, 20h
0x180007996  movups  xmm0, xmmword ptr [rcx]
0x180007999  mov     rbx, rcx
0x18000799c  mov     rdi, rdx
0x18000799f  movups  xmmword ptr [rdx], xmm0
0x1800079a2  movups  xmm1, xmmword ptr [rcx+10h]
0x1800079a6  lea     rax, [rbx+38h]
0x1800079aa  movups  xmmword ptr [rdx+10h], xmm1
0x1800079ae  movups  xmm0, xmmword ptr [rcx+20h]
0x1800079b2  movups  xmmword ptr [rdx+20h], xmm0
0x1800079b6  movsd   xmm1, qword ptr [rcx+30h]
0x1800079bb  lea     rcx, [rdx+38h]
0x1800079bf  movsd   qword ptr [rdx+30h], xmm1
0x1800079c4  mov     edx, 80h
0x1800079c9  movups  xmm0, xmmword ptr [rax]
0x1800079cc  movups  xmmword ptr [rcx], xmm0
0x1800079cf  lea     r8, [rdx+rcx]
0x1800079d3  movups  xmm1, xmmword ptr [rax+10h]
0x1800079d7  movups  xmmword ptr [rcx+10h], xmm1
0x1800079db  movups  xmm0, xmmword ptr [rax+20h]
0x1800079df  movups  xmmword ptr [rcx+20h], xmm0
0x1800079e3  movups  xmm1, xmmword ptr [rax+30h]
0x1800079e7  movups  xmmword ptr [rcx+30h], xmm1
0x1800079eb  movups  xmm0, xmmword ptr [rax+40h]
0x1800079ef  movups  xmmword ptr [rcx+40h], xmm0
0x1800079f3  movups  xmm1, xmmword ptr [rax+50h]
0x1800079f7  movups  xmmword ptr [rcx+50h], xmm1
0x1800079fb  movups  xmm0, xmmword ptr [rax+60h]
0x1800079ff  movups  xmmword ptr [rcx+60h], xmm0
0x180007a03  add     rcx, 0B8h; void *
0x180007a0a  movups  xmm0, xmmword ptr [rax+70h]
0x180007a0e  add     rax, rdx
0x180007a11  xor     edx, edx; Val
0x180007a13  movups  xmmword ptr [r8-10h], xmm0
0x180007a18  movups  xmm1, xmmword ptr [rax]
0x180007a1b  movups  xmmword ptr [r8], xmm1
0x180007a1f  movups  xmm0, xmmword ptr [rax+10h]
0x180007a23  movups  xmmword ptr [r8+10h], xmm0
0x180007a28  movups  xmm1, xmmword ptr [rax+20h]
0x180007a2c  movups  xmmword ptr [r8+20h], xmm1
0x180007a31  mov     rax, [rax+30h]
0x180007a35  mov     [r8+30h], rax
0x180007a39  mov     r8d, 110h; Size
0x180007a3f  call    memset_0
0x180007a44  movups  xmm0, xmmword ptr [rbx+0F0h]
0x180007a4b  movups  xmmword ptr [rdi+200h], xmm0
0x180007a52  movsd   xmm1, qword ptr [rbx+100h]
0x180007a5a  mov     rbx, [rsp+28h+arg_0]
0x180007a5f  movsd   qword ptr [rdi+210h], xmm1
0x180007a67  add     rsp, 20h
0x180007a6b  pop     rdi
0x180007a6c  retn
```
