# WriteVariantToStreamEx(tagVARIANT const *,ISequentialStream *,ulong)

- ea: `0x180003390`
- end: `0x18000356b`
- name: `?WriteVariantToStreamEx@@YAJPEBUtagVARIANT@@PEAUISequentialStream@@K@Z`
- size: `475`
- prototype: `__int64 __fastcall(VARIANTARG *pvarSrc, struct ISequentialStream *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003380`

## callees

- `0x180002f60`
- `0x180003028`
- `0x180003390`
- `0x180004010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800033ca`
- `OLEAUT32!__imp_VariantInit` at `0x1800033ca`
- `OLEAUT32!__imp_VariantClear` at `0x1800034dd`
- `OLEAUT32!__imp_VariantClear` at `0x1800034dd`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000353e`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000353e`

## pseudocode

```c
__int64 __fastcall WriteVariantToStreamEx(VARIANTARG *pvarSrc, struct ISequentialStream *a2, unsigned int a3)
{
  HRESULT v6; // ebx
  unsigned int vt; // ecx
  unsigned int v8; // edi
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ebp
  VARTYPE v23; // ax
  unsigned __int16 *bstrVal; // rcx
  HRESULT v25; // eax
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF
  int v27; // [rsp+80h] [rbp+8h] BYREF

  v27 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !pvarSrc || !a2 )
  {
    v6 = -2147467261;
    goto LABEL_33;
  }
  vt = pvarSrc->vt;
  v8 = 0;
  if ( vt > 0xB )
  {
    v16 = vt - 13;
    if ( !v16 )
      goto LABEL_32;
    v17 = v16 - 3;
    if ( !v17 || (v18 = v17 - 1) == 0 )
    {
      v8 = 1;
      goto LABEL_25;
    }
    v19 = v18 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( !v20 )
        goto LABEL_22;
      v15 = v20 - 3;
      if ( !v15 )
        goto LABEL_22;
      goto LABEL_13;
    }
LABEL_23:
    v8 = 2;
    goto LABEL_25;
  }
  if ( vt == 11 )
    goto LABEL_23;
  v9 = vt - 2;
  if ( !v9 )
    goto LABEL_23;
  v10 = v9 - 1;
  if ( !v10 )
    goto LABEL_22;
  v11 = v10 - 1;
  if ( !v11 )
    goto LABEL_22;
  v12 = v11 - 1;
  if ( !v12 || (v13 = v12 - 1) == 0 || (v14 = v13 - 1) == 0 )
  {
    v8 = 8;
    goto LABEL_25;
  }
  v15 = v14 - 2;
  if ( !v15 )
    goto LABEL_32;
LABEL_13:
  if ( v15 == 1 )
LABEL_22:
    v8 = 4;
LABEL_25:
  if ( a3 < 2 )
  {
LABEL_43:
    v6 = -2147024362;
    goto LABEL_33;
  }
  v6 = ((__int64 (__fastcall *)(struct ISequentialStream *, VARIANTARG *, __int64, int *))a2->lpVtbl->Write)(
         a2,
         pvarSrc,
         2,
         &v27);
  if ( v6 < 0 )
    goto LABEL_33;
  if ( v27 != 2 )
  {
LABEL_32:
    v6 = -2147467259;
    goto LABEL_33;
  }
  v21 = a3 - 2;
  if ( !v8 )
  {
    v23 = pvarSrc->vt;
    if ( pvarSrc->vt == 8 )
    {
      bstrVal = pvarSrc->bstrVal;
    }
    else
    {
      if ( (v23 & 0x2000) != 0 )
      {
        v25 = WriteSafeArrayToStream(pvarSrc->parray, v23 & 0xDFFF, a2);
LABEL_42:
        v6 = v25;
        goto LABEL_33;
      }
      if ( v23 == 1 )
        goto LABEL_33;
      v6 = VariantChangeType(&pvarg, pvarSrc, 1u, 8u);
      if ( v6 < 0 )
        goto LABEL_33;
      bstrVal = pvarg.bstrVal;
    }
    v25 = WriteBSTRToStreamEx(bstrVal, a2, v21);
    goto LABEL_42;
  }
  if ( v21 < v8 )
    goto LABEL_43;
  v6 = ((__int64 (__fastcall *)(struct ISequentialStream *, ULONG *, _QWORD, int *))a2->lpVtbl->Write)(
         a2,
         &pvarSrc->decVal.Lo32,
         v8,
         &v27);
  if ( v6 >= 0 && v8 != v27 )
    goto LABEL_32;
LABEL_33:
  VariantClear(&pvarg);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003390  mov     r11, rsp
0x180003393  mov     [r11+10h], rbx
0x180003397  mov     [r11+18h], rbp
0x18000339b  push    rsi
0x18000339c  push    rdi
0x18000339d  push    r12
0x18000339f  push    r13
0x1800033a1  push    r14
0x1800033a3  sub     rsp, 50h
0x1800033a7  xorps   xmm0, xmm0
0x1800033aa  mov     dword ptr [r11+8], 0
0x1800033b2  mov     rsi, rcx
0x1800033b5  xor     eax, eax
0x1800033b7  movups  xmmword ptr [rsp+78h+pvarg], xmm0
0x1800033bc  lea     rcx, [r11-48h]; pvarg
0x1800033c0  mov     [r11-38h], rax
0x1800033c4  mov     ebp, r8d
0x1800033c7  mov     r14, rdx
0x1800033ca  call    cs:__imp_VariantInit
0x1800033d0  test    rsi, rsi
0x1800033d3  jnz     short loc_1800033DF
0x1800033d5  mov     ebx, 80004003h
0x1800033da  jmp     loc_1800034D8
0x1800033df  test    r14, r14
0x1800033e2  jz      short loc_1800033D5
0x1800033e4  movzx   ecx, word ptr [rsi]
0x1800033e7  xor     edi, edi
0x1800033e9  lea     r12d, [rdi+8]
0x1800033ed  lea     r13d, [rdi+1]
0x1800033f1  cmp     ecx, 0Bh
0x1800033f4  ja      short loc_18000342B
0x1800033f6  jz      short loc_180003454
0x1800033f8  sub     ecx, 2
0x1800033fb  jz      short loc_180003454
0x1800033fd  sub     ecx, r13d
0x180003400  jz      short loc_18000344D
0x180003402  sub     ecx, r13d
0x180003405  jz      short loc_18000344D
0x180003407  sub     ecx, r13d
0x18000340a  jz      short loc_180003426
0x18000340c  sub     ecx, r13d
0x18000340f  jz      short loc_180003426
0x180003411  sub     ecx, r13d
0x180003414  jz      short loc_180003426
0x180003416  sub     ecx, 2
0x180003419  jz      loc_1800034D3
0x18000341f  cmp     ecx, r13d
0x180003422  jz      short loc_18000344D
0x180003424  jmp     short loc_18000345E
0x180003426  mov     edi, r12d
0x180003429  jmp     short loc_18000345E
0x18000342b  sub     ecx, 0Dh
0x18000342e  jz      loc_1800034D3
0x180003434  sub     ecx, 3
0x180003437  jz      short loc_18000345B
0x180003439  sub     ecx, r13d
0x18000343c  jz      short loc_18000345B
0x18000343e  sub     ecx, r13d
0x180003441  jz      short loc_180003454
0x180003443  sub     ecx, r13d
0x180003446  jz      short loc_18000344D
0x180003448  sub     ecx, 3
0x18000344b  jnz     short loc_18000341F
0x18000344d  mov     edi, 4
0x180003452  jmp     short loc_18000345E
0x180003454  mov     edi, 2
0x180003459  jmp     short loc_18000345E
0x18000345b  mov     edi, r13d
0x18000345e  cmp     ebp, 2
0x180003461  jb      loc_180003561
0x180003467  mov     rax, [r14]
0x18000346a  lea     r9, [rsp+78h+arg_0]
0x180003472  mov     r8d, 2
0x180003478  mov     rdx, rsi
0x18000347b  mov     rcx, r14
0x18000347e  mov     rax, [rax+20h]
0x180003482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003487  mov     ebx, eax
0x180003489  test    eax, eax
0x18000348b  js      short loc_1800034D8
0x18000348d  cmp     [rsp+78h+arg_0], 2
0x180003495  jnz     short loc_1800034D3
0x180003497  add     ebp, 0FFFFFFFEh
0x18000349a  test    edi, edi
0x18000349c  jz      short loc_1800034FE
0x18000349e  cmp     ebp, edi
0x1800034a0  jb      loc_180003561
0x1800034a6  mov     rax, [r14]
0x1800034a9  lea     rdx, [rsi+8]
0x1800034ad  lea     r9, [rsp+78h+arg_0]
0x1800034b5  mov     r8d, edi
0x1800034b8  mov     rcx, r14
0x1800034bb  mov     rax, [rax+20h]
0x1800034bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034c4  mov     ebx, eax
0x1800034c6  test    eax, eax
0x1800034c8  js      short loc_1800034D8
0x1800034ca  cmp     edi, [rsp+78h+arg_0]
0x1800034d1  jz      short loc_1800034D8
0x1800034d3  mov     ebx, 80004005h
0x1800034d8  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1800034dd  call    cs:__imp_VariantClear
0x1800034e3  lea     r11, [rsp+78h+var_28]
0x1800034e8  mov     eax, ebx
0x1800034ea  mov     rbx, [r11+38h]
0x1800034ee  mov     rbp, [r11+40h]
0x1800034f2  mov     rsp, r11
0x1800034f5  pop     r14
0x1800034f7  pop     r13
0x1800034f9  pop     r12
0x1800034fb  pop     rdi
0x1800034fc  pop     rsi
0x1800034fd  retn
0x1800034fe  movzx   eax, word ptr [rsi]
0x180003501  cmp     ax, r12w
0x180003505  jnz     short loc_18000350D
0x180003507  mov     rcx, [rsi+8]
0x18000350b  jmp     short loc_18000354F
0x18000350d  bt      ax, 0Dh
0x180003512  jnb     short loc_18000352A
0x180003514  mov     rcx, [rsi+8]; psa
0x180003518  mov     edx, 0DFFFh
0x18000351d  and     dx, ax; unsigned __int16
0x180003520  mov     r8, r14; struct ISequentialStream *
0x180003523  call    ?WriteSafeArrayToStream@@YAJPEAUtagSAFEARRAY@@GPEAUISequentialStream@@@Z; WriteSafeArrayToStream(tagSAFEARRAY *,ushort,ISequentialStream *)
0x180003528  jmp     short loc_18000355A
0x18000352a  cmp     ax, r13w
0x18000352e  jz      short loc_1800034D8
0x180003530  mov     r9d, r12d; vt
0x180003533  lea     rcx, [rsp+78h+pvarg]; pvargDest
0x180003538  mov     r8d, r13d; wFlags
0x18000353b  mov     rdx, rsi; pvarSrc
0x18000353e  call    cs:__imp_VariantChangeType
0x180003544  mov     ebx, eax
0x180003546  test    eax, eax
0x180003548  js      short loc_1800034D8
0x18000354a  mov     rcx, qword ptr [rsp+78h+pvarg+8]; unsigned __int16 *
0x18000354f  mov     rdx, r14; struct ISequentialStream *
0x180003552  mov     r8d, ebp; unsigned int
0x180003555  call    ?WriteBSTRToStreamEx@@YAJPEAGPEAUISequentialStream@@K@Z; WriteBSTRToStreamEx(ushort *,ISequentialStream *,ulong)
0x18000355a  mov     ebx, eax
0x18000355c  jmp     loc_1800034D8
0x180003561  mov     ebx, 80070216h
0x180003566  jmp     loc_1800034D8
```
