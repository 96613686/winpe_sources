# BaseSrvConvertV1CreateProcessToV2

- ea: `0x180007c84`
- end: `0x180007d7c`
- name: `BaseSrvConvertV1CreateProcessToV2`
- size: `248`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008000`

## callees

- `0x18000db1d`

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
0x180007c84  mov     [rsp+arg_0], rbx
0x180007c89  push    rdi
0x180007c8a  sub     rsp, 20h
0x180007c8e  movups  xmm0, xmmword ptr [rcx]
0x180007c91  mov     rbx, rcx
0x180007c94  mov     rdi, rdx
0x180007c97  mov     r8d, 110h; Size
0x180007c9d  movups  xmmword ptr [rdx], xmm0
0x180007ca0  movups  xmm1, xmmword ptr [rcx+10h]
0x180007ca4  movups  xmmword ptr [rdx+10h], xmm1
0x180007ca8  movups  xmm0, xmmword ptr [rcx+20h]
0x180007cac  movups  xmmword ptr [rdx+20h], xmm0
0x180007cb0  movsd   xmm1, qword ptr [rcx+30h]
0x180007cb5  movsd   qword ptr [rdx+30h], xmm1
0x180007cba  movups  xmm0, xmmword ptr [rcx+38h]
0x180007cbe  movups  xmmword ptr [rdx+38h], xmm0
0x180007cc2  movups  xmm1, xmmword ptr [rcx+48h]
0x180007cc6  movups  xmmword ptr [rdx+48h], xmm1
0x180007cca  movups  xmm0, xmmword ptr [rcx+58h]
0x180007cce  movups  xmmword ptr [rdx+58h], xmm0
0x180007cd2  movups  xmm1, xmmword ptr [rcx+68h]
0x180007cd6  movups  xmmword ptr [rdx+68h], xmm1
0x180007cda  movups  xmm0, xmmword ptr [rcx+78h]
0x180007cde  movups  xmmword ptr [rdx+78h], xmm0
0x180007ce2  movups  xmm1, xmmword ptr [rcx+88h]
0x180007ce9  movups  xmmword ptr [rdx+88h], xmm1
0x180007cf0  movups  xmm0, xmmword ptr [rcx+98h]
0x180007cf7  movups  xmmword ptr [rdx+98h], xmm0
0x180007cfe  movups  xmm1, xmmword ptr [rcx+0A8h]
0x180007d05  movups  xmmword ptr [rdx+0A8h], xmm1
0x180007d0c  movups  xmm0, xmmword ptr [rcx+0B8h]
0x180007d13  movups  xmmword ptr [rdx+0B8h], xmm0
0x180007d1a  movups  xmm1, xmmword ptr [rcx+0C8h]
0x180007d21  movups  xmmword ptr [rdx+0C8h], xmm1
0x180007d28  movups  xmm0, xmmword ptr [rcx+0D8h]
0x180007d2f  movups  xmmword ptr [rdx+0D8h], xmm0
0x180007d36  mov     rax, [rcx+0E8h]
0x180007d3d  lea     rcx, [rdx+0F0h]; void *
0x180007d44  mov     [rdx+0E8h], rax
0x180007d4b  xor     edx, edx; Val
0x180007d4d  call    memset_0
0x180007d52  movups  xmm0, xmmword ptr [rbx+0F0h]
0x180007d59  movups  xmmword ptr [rdi+200h], xmm0
0x180007d60  movsd   xmm1, qword ptr [rbx+100h]
0x180007d68  mov     rbx, [rsp+28h+arg_0]
0x180007d6d  movsd   qword ptr [rdi+210h], xmm1
0x180007d75  add     rsp, 20h
0x180007d79  pop     rdi
0x180007d7a  retn
```
