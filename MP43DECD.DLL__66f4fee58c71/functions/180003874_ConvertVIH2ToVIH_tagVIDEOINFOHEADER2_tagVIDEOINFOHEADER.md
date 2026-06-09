# ConvertVIH2ToVIH(tagVIDEOINFOHEADER2 *,tagVIDEOINFOHEADER *)

- ea: `0x180003874`
- end: `0x1800038fa`
- name: `?ConvertVIH2ToVIH@@YAJPEAUtagVIDEOINFOHEADER2@@PEAUtagVIDEOINFOHEADER@@@Z`
- size: `134`
- prototype: `int(struct tagVIDEOINFOHEADER2 *, struct tagVIDEOINFOHEADER *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004750`
- `0x180004ffc`
- `0x180007800`

## callees

- `0x180002144`
- `0x180003874`

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
0x180003874  mov     [rsp+arg_0], rbx
0x180003879  mov     [rsp+arg_8], rsi
0x18000387e  push    rdi
0x18000387f  sub     rsp, 20h
0x180003883  mov     rbx, rdx
0x180003886  mov     rdi, rcx
0x180003889  test    rcx, rcx
0x18000388c  jz      short loc_1800038E3
0x18000388e  test    rdx, rdx
0x180003891  jz      short loc_1800038E3
0x180003893  xor     esi, esi
0x180003895  xor     edx, edx; Val
0x180003897  mov     rcx, rbx; void *
0x18000389a  lea     r8d, [rsi+58h]; Size
0x18000389e  call    memset_0
0x1800038a3  movups  xmm0, xmmword ptr [rdi]
0x1800038a6  movdqu  xmmword ptr [rbx], xmm0
0x1800038aa  movups  xmm1, xmmword ptr [rdi+10h]
0x1800038ae  movdqu  xmmword ptr [rbx+10h], xmm1
0x1800038b3  mov     eax, [rdi+20h]
0x1800038b6  mov     [rbx+20h], eax
0x1800038b9  mov     eax, [rdi+24h]
0x1800038bc  mov     [rbx+24h], eax
0x1800038bf  mov     rax, [rdi+28h]
0x1800038c3  mov     [rbx+28h], rax
0x1800038c7  movups  xmm0, xmmword ptr [rdi+48h]
0x1800038cb  movups  xmmword ptr [rbx+30h], xmm0
0x1800038cf  movups  xmm1, xmmword ptr [rdi+58h]
0x1800038d3  movups  xmmword ptr [rbx+40h], xmm1
0x1800038d7  movsd   xmm0, qword ptr [rdi+68h]
0x1800038dc  movsd   qword ptr [rbx+50h], xmm0
0x1800038e1  jmp     short loc_1800038E8
0x1800038e3  mov     esi, 80004003h
0x1800038e8  mov     rbx, [rsp+28h+arg_0]
0x1800038ed  mov     eax, esi
0x1800038ef  mov     rsi, [rsp+28h+arg_8]
0x1800038f4  add     rsp, 20h
0x1800038f8  pop     rdi
0x1800038f9  retn
```
