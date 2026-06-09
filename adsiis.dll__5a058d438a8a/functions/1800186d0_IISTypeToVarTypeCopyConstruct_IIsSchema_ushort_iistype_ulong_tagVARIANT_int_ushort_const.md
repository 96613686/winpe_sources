# IISTypeToVarTypeCopyConstruct(IIsSchema *,ushort *,_iistype *,ulong,tagVARIANT *,int,ushort const *)

- ea: `0x1800186d0`
- end: `0x180018835`
- name: `?IISTypeToVarTypeCopyConstruct@@YAJPEAVIIsSchema@@PEAGPEAU_iistype@@KPEAUtagVARIANT@@HPEBG@Z`
- size: `357`
- prototype: `__int64 __usercall@<rax>(struct IIsSchema *@<rcx>, unsigned __int16 *@<rdx>, struct _iistype *@<r8>, unsigned int@<r9d>, VARIANTARG *pvarg, int, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ed0`
- `0x180003050`
- `0x180005a90`
- `0x180005e40`
- `0x180006b00`
- `0x180006d90`
- `0x180010104`

## callees

- `0x180018518`
- `0x1800186d0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180018733`
- `OLEAUT32!__imp_VariantInit` at `0x1800187a9`
- `OLEAUT32!__imp_VariantInit` at `0x180018733`
- `OLEAUT32!__imp_VariantInit` at `0x1800187a9`
- `OLEAUT32!__imp_VariantClear` at `0x1800187f7`
- `OLEAUT32!__imp_VariantClear` at `0x1800187f7`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001876f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001876f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001880e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001880e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800187eb`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800187eb`

## pseudocode

```c
int __fastcall IISTypeToVarTypeCopyConstruct(
        struct IIsSchema *a1,
        unsigned __int16 *a2,
        struct _iistype *a3,
        signed int a4,
        VARIANTARG *pvarg,
        int a6,
        unsigned __int16 *a7)
{
  int v8; // r8d
  int result; // eax
  VARIANTARG *v13; // r15
  SAFEARRAY *v14; // rsi
  HRESULT v15; // ebx
  LONG i; // eax
  SAFEARRAYBOUND rgsabound; // [rsp+30h] [rbp-28h] BYREF
  VARIANTARG pv; // [rsp+38h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+B0h] [rbp+58h] BYREF

  rgIndices = 0;
  v8 = *(_DWORD *)a3;
  if ( ((v8 - 5) & 0xFFFFFFFA) == 0 && v8 != 6 )
    return IISTypeToVarTypeCopy(a1, a2, a3, pvarg, a6, a7);
  v13 = pvarg;
  VariantInit(pvarg);
  if ( a4 == 1 && ((*(_DWORD *)a3 - 4) & 0xFFFFFFFB) == 0 )
    a4 = **((_WORD **)a3 + 1) != 0;
  rgsabound.lLbound = 0;
  rgsabound.cElements = a4;
  v14 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  if ( v14 )
  {
    rgIndices = 0;
    for ( i = 0; i < a4; i = ++rgIndices )
    {
      memset(&pv, 0, sizeof(pv));
      VariantInit(&pv);
      v15 = IISTypeToVarTypeCopy(a1, a2, (struct _iistype *)((char *)a3 + 24 * rgIndices), &pv, a6, 0);
      if ( v15 >= 0 )
      {
        v15 = SafeArrayPutElement(v14, &rgIndices, &pv);
        VariantClear(&pv);
        if ( v15 >= 0 )
          continue;
      }
      SafeArrayDestroy(v14);
      return v15;
    }
    v13->vt = 8204;
    result = 0;
    v13->llVal = (LONGLONG)v14;
  }
  else
  {
    return -2147024882;
  }
  return result;
}

```

## disassembly

```asm
0x1800186d0  push    rbp
0x1800186d2  push    rbx
0x1800186d3  push    rsi
0x1800186d4  push    rdi
0x1800186d5  push    r12
0x1800186d7  push    r13
0x1800186d9  push    r14
0x1800186db  push    r15
0x1800186dd  mov     rbp, rsp
0x1800186e0  sub     rsp, 58h
0x1800186e4  mov     r14, r8
0x1800186e7  mov     [rbp+rgIndices], 0
0x1800186ee  mov     r8d, [r8]
0x1800186f1  mov     edi, r9d
0x1800186f4  mov     r12, rdx
0x1800186f7  mov     r13, rcx
0x1800186fa  lea     eax, [r8-5]
0x1800186fe  test    eax, 0FFFFFFFAh
0x180018703  jnz     short loc_18001872C
0x180018705  cmp     r8d, 6
0x180018709  jz      short loc_18001872C
0x18001870b  mov     rax, [rbp+arg_30]
0x18001870f  mov     r8, r14; struct _iistype *
0x180018712  mov     r9, [rbp+pvarg]; struct tagVARIANT *
0x180018716  mov     [rsp+58h+var_30], rax; unsigned __int16 *
0x18001871b  mov     eax, [rbp+arg_28]
0x18001871e  mov     [rsp+58h+var_38], eax; int
0x180018722  call    ?IISTypeToVarTypeCopy@@YAJPEAVIIsSchema@@PEAGPEAU_iistype@@PEAUtagVARIANT@@HPEBG@Z; IISTypeToVarTypeCopy(IIsSchema *,ushort *,_iistype *,tagVARIANT *,int,ushort const *)
0x180018727  jmp     loc_180018824
0x18001872c  mov     r15, [rbp+pvarg]
0x180018730  mov     rcx, r15; pvarg
0x180018733  call    cs:__imp_VariantInit
0x180018739  cmp     edi, 1
0x18001873c  jnz     short loc_180018759
0x18001873e  mov     eax, [r14]
0x180018741  sub     eax, 4
0x180018744  test    eax, 0FFFFFFFBh
0x180018749  jnz     short loc_180018759
0x18001874b  mov     rax, [r14+8]
0x18001874f  movzx   ecx, word ptr [rax]
0x180018752  neg     cx
0x180018755  sbb     eax, eax
0x180018757  and     edi, eax
0x180018759  mov     ecx, 0Ch; vt
0x18001875e  mov     [rbp+rgsabound.lLbound], 0
0x180018765  lea     r8, [rbp+rgsabound]; rgsabound
0x180018769  mov     [rbp+rgsabound.cElements], edi
0x18001876c  lea     edx, [rcx-0Bh]; cDims
0x18001876f  call    cs:__imp_SafeArrayCreate
0x180018775  mov     rsi, rax
0x180018778  test    rax, rax
0x18001877b  jnz     short loc_180018787
0x18001877d  mov     ebx, 8007000Eh
0x180018782  jmp     loc_180018814
0x180018787  mov     [rbp+rgIndices], 0
0x18001878e  xor     eax, eax
0x180018790  cmp     eax, edi
0x180018792  jge     loc_180018818
0x180018798  xorps   xmm0, xmm0
0x18001879b  lea     rcx, [rbp+pv]; pvarg
0x18001879f  xor     eax, eax
0x1800187a1  movups  xmmword ptr [rbp+pv], xmm0
0x1800187a5  mov     qword ptr [rbp+pv+10h], rax
0x1800187a9  call    cs:__imp_VariantInit
0x1800187af  movsxd  rax, [rbp+rgIndices]
0x1800187b3  lea     r9, [rbp+pv]; struct tagVARIANT *
0x1800187b7  mov     [rsp+58h+var_30], 0; unsigned __int16 *
0x1800187c0  mov     rdx, r12; unsigned __int16 *
0x1800187c3  lea     rcx, [rax+rax*2]
0x1800187c7  mov     eax, [rbp+arg_28]
0x1800187ca  lea     r8, [r14+rcx*8]; struct _iistype *
0x1800187ce  mov     [rsp+58h+var_38], eax; int
0x1800187d2  mov     rcx, r13; struct IIsSchema *
0x1800187d5  call    ?IISTypeToVarTypeCopy@@YAJPEAVIIsSchema@@PEAGPEAU_iistype@@PEAUtagVARIANT@@HPEBG@Z; IISTypeToVarTypeCopy(IIsSchema *,ushort *,_iistype *,tagVARIANT *,int,ushort const *)
0x1800187da  mov     ebx, eax
0x1800187dc  test    eax, eax
0x1800187de  js      short loc_18001880B
0x1800187e0  lea     r8, [rbp+pv]; pv
0x1800187e4  mov     rcx, rsi; psa
0x1800187e7  lea     rdx, [rbp+rgIndices]; rgIndices
0x1800187eb  call    cs:__imp_SafeArrayPutElement
0x1800187f1  lea     rcx, [rbp+pv]; pvarg
0x1800187f5  mov     ebx, eax
0x1800187f7  call    cs:__imp_VariantClear
0x1800187fd  test    ebx, ebx
0x1800187ff  js      short loc_18001880B
0x180018801  mov     eax, [rbp+rgIndices]
0x180018804  inc     eax
0x180018806  mov     [rbp+rgIndices], eax
0x180018809  jmp     short loc_180018790
0x18001880b  mov     rcx, rsi; psa
0x18001880e  call    cs:__imp_SafeArrayDestroy
0x180018814  mov     eax, ebx
0x180018816  jmp     short loc_180018824
0x180018818  mov     word ptr [r15], 200Ch
0x18001881e  xor     eax, eax
0x180018820  mov     [r15+8], rsi
0x180018824  add     rsp, 58h
0x180018828  pop     r15
0x18001882a  pop     r14
0x18001882c  pop     r13
0x18001882e  pop     r12
0x180018830  pop     rdi
0x180018831  pop     rsi
0x180018832  pop     rbx
0x180018833  pop     rbp
0x180018834  retn
```
