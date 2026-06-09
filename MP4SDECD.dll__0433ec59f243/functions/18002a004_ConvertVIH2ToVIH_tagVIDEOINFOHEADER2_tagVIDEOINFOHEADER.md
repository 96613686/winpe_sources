# ConvertVIH2ToVIH(tagVIDEOINFOHEADER2 *,tagVIDEOINFOHEADER *)

- ea: `0x18002a004`
- end: `0x18002a08a`
- name: `?ConvertVIH2ToVIH@@YAJPEAUtagVIDEOINFOHEADER2@@PEAUtagVIDEOINFOHEADER@@@Z`
- size: `134`
- prototype: `int(struct tagVIDEOINFOHEADER2 *, struct tagVIDEOINFOHEADER *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800149ac`
- `0x180029020`
- `0x18002d778`

## callees

- `0x18002a004`
- `0x18002b394`

## pseudocode

```c
__int64 __fastcall ConvertVIH2ToVIH(struct tagVIDEOINFOHEADER2 *a1, struct tagVIDEOINFOHEADER *a2)
{
  unsigned int v4; // esi

  if ( a1 && a2 )
  {
    v4 = 0;
    memset_0(a2, 0, sizeof(struct tagVIDEOINFOHEADER));
    a2->rcSource = a1->rcSource;
    a2->rcTarget = a1->rcTarget;
    a2->dwBitRate = a1->dwBitRate;
    a2->dwBitErrorRate = a1->dwBitErrorRate;
    a2->AvgTimePerFrame = a1->AvgTimePerFrame;
    *(_OWORD *)&a2->bmiHeader.biSize = *(_OWORD *)&a1->bmiHeader.biSize;
    *(_OWORD *)&a2->bmiHeader.biCompression = *(_OWORD *)&a1->bmiHeader.biCompression;
    *(_QWORD *)&a2->bmiHeader.biClrUsed = *(_QWORD *)&a1->bmiHeader.biClrUsed;
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v4;
}

```

## disassembly

```asm
0x18002a004  mov     [rsp+arg_0], rbx
0x18002a009  mov     [rsp+arg_8], rsi
0x18002a00e  push    rdi
0x18002a00f  sub     rsp, 20h
0x18002a013  mov     rbx, rdx
0x18002a016  mov     rdi, rcx
0x18002a019  test    rcx, rcx
0x18002a01c  jz      short loc_18002A073
0x18002a01e  test    rdx, rdx
0x18002a021  jz      short loc_18002A073
0x18002a023  xor     esi, esi
0x18002a025  xor     edx, edx; Val
0x18002a027  mov     rcx, rbx; void *
0x18002a02a  lea     r8d, [rsi+58h]; Size
0x18002a02e  call    memset_0
0x18002a033  movups  xmm0, xmmword ptr [rdi]
0x18002a036  movdqu  xmmword ptr [rbx], xmm0
0x18002a03a  movups  xmm1, xmmword ptr [rdi+10h]
0x18002a03e  movdqu  xmmword ptr [rbx+10h], xmm1
0x18002a043  mov     eax, [rdi+20h]
0x18002a046  mov     [rbx+20h], eax
0x18002a049  mov     eax, [rdi+24h]
0x18002a04c  mov     [rbx+24h], eax
0x18002a04f  mov     rax, [rdi+28h]
0x18002a053  mov     [rbx+28h], rax
0x18002a057  movups  xmm0, xmmword ptr [rdi+48h]
0x18002a05b  movups  xmmword ptr [rbx+30h], xmm0
0x18002a05f  movups  xmm1, xmmword ptr [rdi+58h]
0x18002a063  movups  xmmword ptr [rbx+40h], xmm1
0x18002a067  movsd   xmm0, qword ptr [rdi+68h]
0x18002a06c  movsd   qword ptr [rbx+50h], xmm0
0x18002a071  jmp     short loc_18002A078
0x18002a073  mov     esi, 80004003h
0x18002a078  mov     rbx, [rsp+28h+arg_0]
0x18002a07d  mov     eax, esi
0x18002a07f  mov     rsi, [rsp+28h+arg_8]
0x18002a084  add     rsp, 20h
0x18002a088  pop     rdi
0x18002a089  retn
```
