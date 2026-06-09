# put_VARIANT_Property(IADs *,ushort *,tagVARIANT)

- ea: `0x1800146dc`
- end: `0x18001478e`
- name: `?put_VARIANT_Property@@YAJPEAUIADs@@PEAGUtagVARIANT@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(struct IADs *, unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c770`
- `0x18000ca60`

## callees

- `0x1800146dc`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180014702`
- `OLEAUT32!__imp_VariantInit` at `0x180014729`
- `OLEAUT32!__imp_VariantInit` at `0x180014702`
- `OLEAUT32!__imp_VariantInit` at `0x180014729`
- `OLEAUT32!__imp_VariantClear` at `0x18001477d`
- `OLEAUT32!__imp_VariantClear` at `0x18001477d`
- `OLEAUT32!__imp_VariantCopy` at `0x180014740`
- `OLEAUT32!__imp_VariantCopy` at `0x180014740`

## pseudocode

```c
__int64 __fastcall put_VARIANT_Property(struct IADs *a1, unsigned __int16 *a2, struct tagVARIANT *a3)
{
  HRESULT v6; // ebx
  IRecordInfo *pRecInfo; // xmm1_8
  HRESULT (__stdcall *Put)(IADs *, BSTR, VARIANT); // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF
  VARIANTARG pvargSrc; // [rsp+40h] [rbp-28h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( a2 )
  {
    pRecInfo = a3->pRecInfo;
    *(_OWORD *)&pvargSrc.vt = *(_OWORD *)&a3->vt;
    pvargSrc.pRecInfo = pRecInfo;
    VariantInit(&pvarg);
    pvarg.vt = 12;
    v6 = VariantCopy(&pvarg, &pvargSrc);
    if ( v6 >= 0 )
    {
      Put = a1->lpVtbl->Put;
      pvargSrc = pvarg;
      v6 = ((__int64 (__fastcall *)(struct IADs *, unsigned __int16 *, VARIANTARG *))Put)(a1, a2, &pvargSrc);
    }
  }
  else
  {
    v6 = -2147463160;
  }
  VariantClear(&pvarg);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800146dc  push    rbp
0x1800146de  push    rbx
0x1800146df  push    rsi
0x1800146e0  push    rdi
0x1800146e1  mov     rbp, rsp
0x1800146e4  sub     rsp, 68h
0x1800146e8  mov     rsi, rcx
0x1800146eb  xorps   xmm0, xmm0
0x1800146ee  xor     eax, eax
0x1800146f0  lea     rcx, [rbp+pvarg]; pvarg
0x1800146f4  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800146f8  mov     qword ptr [rbp+pvarg+10h], rax
0x1800146fc  mov     rbx, r8
0x1800146ff  mov     rdi, rdx
0x180014702  call    cs:__imp_VariantInit
0x180014708  test    rdi, rdi
0x18001470b  jnz     short loc_180014714
0x18001470d  mov     ebx, 80005008h
0x180014712  jmp     short loc_180014779
0x180014714  movaps  xmm0, xmmword ptr [rbx]
0x180014717  lea     rcx, [rbp+pvarg]; pvarg
0x18001471b  movsd   xmm1, qword ptr [rbx+10h]
0x180014720  movaps  xmmword ptr [rbp+pvargSrc], xmm0
0x180014724  movsd   qword ptr [rbp+pvargSrc+10h], xmm1
0x180014729  call    cs:__imp_VariantInit
0x18001472f  mov     eax, 0Ch
0x180014734  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x180014738  lea     rcx, [rbp+pvarg]; pvargDest
0x18001473c  mov     word ptr [rbp+pvarg], ax
0x180014740  call    cs:__imp_VariantCopy
0x180014746  mov     ebx, eax
0x180014748  test    eax, eax
0x18001474a  js      short loc_180014779
0x18001474c  mov     rax, [rsi]
0x18001474f  lea     r8, [rbp+pvargSrc]
0x180014753  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180014757  mov     rdx, rdi
0x18001475a  mov     rcx, rsi
0x18001475d  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180014762  mov     rax, [rax+80h]
0x180014769  movaps  xmmword ptr [rbp+pvargSrc], xmm0
0x18001476d  movsd   qword ptr [rbp+pvargSrc+10h], xmm1
0x180014772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014777  mov     ebx, eax
0x180014779  lea     rcx, [rbp+pvarg]; pvarg
0x18001477d  call    cs:__imp_VariantClear
0x180014783  mov     eax, ebx
0x180014785  add     rsp, 68h
0x180014789  pop     rdi
0x18001478a  pop     rsi
0x18001478b  pop     rbx
0x18001478c  pop     rbp
0x18001478d  retn
```
