# ConvertVIH2ToVIH(tagVIDEOINFOHEADER2 *,tagVIDEOINFOHEADER *)

- ea: `0x180003934`
- end: `0x1800039ba`
- name: `?ConvertVIH2ToVIH@@YAJPEAUtagVIDEOINFOHEADER2@@PEAUtagVIDEOINFOHEADER@@@Z`
- size: `134`
- prototype: `int(struct tagVIDEOINFOHEADER2 *, struct tagVIDEOINFOHEADER *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004810`
- `0x1800050bc`
- `0x1800078c0`

## callees

- `0x180002174`
- `0x180003934`

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
0x180003934  mov     [rsp+arg_0], rbx
0x180003939  mov     [rsp+arg_8], rsi
0x18000393e  push    rdi
0x18000393f  sub     rsp, 20h
0x180003943  mov     rbx, rdx
0x180003946  mov     rdi, rcx
0x180003949  test    rcx, rcx
0x18000394c  jz      short loc_1800039A3
0x18000394e  test    rdx, rdx
0x180003951  jz      short loc_1800039A3
0x180003953  xor     esi, esi
0x180003955  xor     edx, edx; Val
0x180003957  mov     rcx, rbx; void *
0x18000395a  lea     r8d, [rsi+58h]; Size
0x18000395e  call    memset_0
0x180003963  movups  xmm0, xmmword ptr [rdi]
0x180003966  movdqu  xmmword ptr [rbx], xmm0
0x18000396a  movups  xmm1, xmmword ptr [rdi+10h]
0x18000396e  movdqu  xmmword ptr [rbx+10h], xmm1
0x180003973  mov     eax, [rdi+20h]
0x180003976  mov     [rbx+20h], eax
0x180003979  mov     eax, [rdi+24h]
0x18000397c  mov     [rbx+24h], eax
0x18000397f  mov     rax, [rdi+28h]
0x180003983  mov     [rbx+28h], rax
0x180003987  movups  xmm0, xmmword ptr [rdi+48h]
0x18000398b  movups  xmmword ptr [rbx+30h], xmm0
0x18000398f  movups  xmm1, xmmword ptr [rdi+58h]
0x180003993  movups  xmmword ptr [rbx+40h], xmm1
0x180003997  movsd   xmm0, qword ptr [rdi+68h]
0x18000399c  movsd   qword ptr [rbx+50h], xmm0
0x1800039a1  jmp     short loc_1800039A8
0x1800039a3  mov     esi, 80004003h
0x1800039a8  mov     rbx, [rsp+28h+arg_0]
0x1800039ad  mov     eax, esi
0x1800039af  mov     rsi, [rsp+28h+arg_8]
0x1800039b4  add     rsp, 20h
0x1800039b8  pop     rdi
0x1800039b9  retn
```
