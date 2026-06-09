# FwProduct::put_RuleCategories(tagVARIANT)

- ea: `0x18001b210`
- end: `0x18001b419`
- name: `?put_RuleCategories@FwProduct@@UEAAJUtagVARIANT@@@Z`
- size: `521`
- prototype: `int(FwProduct *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001b210`
- `0x1800277b0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001b384`
- `OLEAUT32!__imp_VariantClear` at `0x18001b384`
- `OLEAUT32!__imp_VariantCopy` at `0x18001b374`
- `OLEAUT32!__imp_VariantCopy` at `0x18001b374`
- `fwbase!FwBaseFree` at `0x18001b337`
- `fwbase!FwBaseFree` at `0x18001b3d6`
- `fwbase!FwBaseFree` at `0x18001b337`
- `fwbase!FwBaseFree` at `0x18001b3d6`
- `fwbase!FwAllocArray` at `0x18001b2ac`
- `fwbase!FwAllocArray` at `0x18001b2ac`
- `fwbase!FwReportReturnError` at `0x18001b32e`
- `fwbase!FwReportReturnError` at `0x18001b3cd`
- `fwbase!FwReportReturnError` at `0x18001b3e5`
- `fwbase!FwReportReturnError` at `0x18001b40c`
- `fwbase!FwReportReturnError` at `0x18001b32e`
- `fwbase!FwReportReturnError` at `0x18001b3cd`
- `fwbase!FwReportReturnError` at `0x18001b3e5`
- `fwbase!FwReportReturnError` at `0x18001b40c`

## pseudocode

```c
__int64 __fastcall FwProduct::put_RuleCategories(FwProduct *this, struct tagVARIANT *a2)
{
  __int64 v4; // r14
  unsigned int v5; // r15d
  __int64 v6; // rsi
  LONGLONG llVal; // rbx
  unsigned int v8; // edi
  __int64 v9; // r8
  unsigned int i; // ecx
  __int64 v11; // rdx
  int v12; // eax
  int v13; // r8d
  unsigned int j; // edx
  int v15; // ecx
  int v16; // edi
  __int64 v17; // rdx
  HRESULT v19; // eax
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned int v21; // ebx
  __int64 v22; // rdx
  VARIANTARG pvargDest; // [rsp+20h] [rbp-58h] BYREF

  memset(&pvargDest, 0, sizeof(pvargDest));
  v4 = 0;
  if ( *((_QWORD *)this + 12) )
  {
    v16 = -2147024891;
    v17 = 2147942405LL;
LABEL_19:
    FwReportReturnError("FwProduct::put_RuleCategories", v17);
    goto LABEL_20;
  }
  v5 = 0;
  if ( a2->vt )
  {
    v6 = 0;
    if ( a2->vt == 8204 && (llVal = a2->llVal) != 0 && *(_WORD *)llVal == 1 )
    {
      v8 = *(_DWORD *)(llVal + 24);
      if ( !v8 )
        goto LABEL_13;
      v6 = FwAllocArray(v8, 4);
      if ( v6 )
      {
        v9 = *(_QWORD *)(llVal + 16);
        for ( i = 0; ; ++i )
        {
          if ( i >= v8 )
          {
            v5 = v8;
            v4 = v6;
            goto LABEL_13;
          }
          v11 = i;
          if ( *(_WORD *)(v9 + 24LL * i) != 3 )
            break;
          v12 = *(_DWORD *)(v9 + 24LL * i + 8);
          *(_DWORD *)(v6 + 4 * v11) = v12;
        }
        v22 = 2147942487LL;
        v21 = -2147024809;
      }
      else
      {
        v21 = -2147024882;
        v22 = 2147942414LL;
      }
    }
    else
    {
      v21 = -2147024809;
      v22 = 2147942487LL;
    }
    FwReportReturnError("FwVariantToArrayOfLongs", v22);
    FwBaseFree(v6);
    v19 = FwReportReturnError("FwVariantToArrayOfLongs", v21);
    v16 = v19;
    if ( v19 < 0 )
    {
LABEL_30:
      v17 = (unsigned int)v19;
      goto LABEL_19;
    }
  }
LABEL_13:
  v13 = 0;
  for ( j = 0; j < v5; ++j )
  {
    v15 = *(_DWORD *)(v4 + 4LL * j);
    if ( v15 >= 4 || ((1 << v15) & v13) != 0 )
    {
      v16 = -2147024809;
      v17 = 2147942487LL;
      goto LABEL_19;
    }
    v13 |= 1 << v15;
  }
  v19 = VariantCopy(&pvargDest, a2);
  v16 = v19;
  if ( v19 < 0 )
    goto LABEL_30;
  VariantClear((VARIANTARG *)((char *)this + 64));
  pRecInfo = pvargDest.pRecInfo;
  *((_OWORD *)this + 4) = *(_OWORD *)&pvargDest.vt;
  *((_QWORD *)this + 10) = pRecInfo;
LABEL_20:
  FwBaseFree(v4);
  if ( v16 < 0 )
    return (unsigned int)FwReportReturnError("FwProduct::put_RuleCategories", (unsigned int)v16);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18001b210  mov     [rsp+arg_10], rbx
0x18001b215  push    rbp
0x18001b216  push    rsi
0x18001b217  push    rdi
0x18001b218  push    r12
0x18001b21a  push    r13
0x18001b21c  push    r14
0x18001b21e  push    r15
0x18001b220  sub     rsp, 40h
0x18001b224  mov     rax, cs:__security_cookie
0x18001b22b  xor     rax, rsp
0x18001b22e  mov     [rsp+78h+var_40], rax
0x18001b233  xor     r12d, r12d
0x18001b236  xor     eax, eax
0x18001b238  xorps   xmm0, xmm0
0x18001b23b  mov     rbp, rdx
0x18001b23e  mov     r13, rcx
0x18001b241  mov     word ptr [rsp+78h+pvargDest], r12w
0x18001b247  mov     r14d, r12d
0x18001b24a  movups  xmmword ptr [rsp+78h+pvargDest+2], xmm0
0x18001b24f  mov     qword ptr [rsp+78h+pvargDest+10h], rax
0x18001b254  cmp     [rcx+60h], r12
0x18001b258  jnz     loc_18001B3A2
0x18001b25e  lea     r10d, [r12+1]
0x18001b263  mov     r15d, r12d
0x18001b266  mov     r9d, 80070057h
0x18001b26c  cmp     [rdx], r12w
0x18001b270  jz      loc_18001B2F9
0x18001b276  mov     eax, 200Ch
0x18001b27b  mov     esi, r12d
0x18001b27e  cmp     [rdx], ax
0x18001b281  jnz     loc_18001B3C0
0x18001b287  mov     rbx, [rdx+8]
0x18001b28b  test    rbx, rbx
0x18001b28e  jz      loc_18001B3C0
0x18001b294  cmp     [rbx], r10w
0x18001b298  jnz     loc_18001B3C0
0x18001b29e  mov     edi, [rbx+18h]
0x18001b2a1  test    edi, edi
0x18001b2a3  jz      short loc_18001B2F9
0x18001b2a5  mov     ecx, edi
0x18001b2a7  lea     edx, [r12+4]
0x18001b2ac  call    cs:__imp_FwAllocArray
0x18001b2b2  mov     rsi, rax
0x18001b2b5  test    rax, rax
0x18001b2b8  jz      loc_18001B3AE
0x18001b2be  mov     r8, [rbx+10h]
0x18001b2c2  lea     r10d, [r12+1]
0x18001b2c7  mov     ecx, r12d
0x18001b2ca  cmp     ecx, edi
0x18001b2cc  jnb     short loc_18001B2ED
0x18001b2ce  mov     edx, ecx
0x18001b2d0  lea     rax, [rdx+rdx*2]
0x18001b2d4  cmp     word ptr [r8+rax*8], 3
0x18001b2da  jnz     loc_18001B3B7
0x18001b2e0  mov     eax, [r8+rax*8+8]
0x18001b2e5  add     ecx, r10d
0x18001b2e8  mov     [rsi+rdx*4], eax
0x18001b2eb  jmp     short loc_18001B2CA
0x18001b2ed  mov     r15d, edi
0x18001b2f0  mov     r14, rsi
0x18001b2f3  mov     r9d, 80070057h
0x18001b2f9  mov     r8d, r12d
0x18001b2fc  mov     edx, r12d
0x18001b2ff  cmp     edx, r15d
0x18001b302  jnb     short loc_18001B36C
0x18001b304  mov     eax, edx
0x18001b306  mov     ecx, [r14+rax*4]
0x18001b30a  cmp     ecx, 4
0x18001b30d  jge     short loc_18001B321
0x18001b30f  mov     eax, r10d
0x18001b312  shl     eax, cl
0x18001b314  test    r8d, eax
0x18001b317  jnz     short loc_18001B321
0x18001b319  or      r8d, eax
0x18001b31c  add     edx, r10d
0x18001b31f  jmp     short loc_18001B2FF
0x18001b321  mov     edi, r9d
0x18001b324  mov     edx, r9d
0x18001b327  lea     rcx, aFwproductPutRu; "FwProduct::put_RuleCategories"
0x18001b32e  call    cs:__imp_FwReportReturnError
0x18001b334  mov     rcx, r14
0x18001b337  call    cs:__imp_FwBaseFree
0x18001b33d  test    edi, edi
0x18001b33f  js      loc_18001B403
0x18001b345  mov     eax, edi
0x18001b347  mov     rcx, [rsp+78h+var_40]
0x18001b34c  xor     rcx, rsp; StackCookie
0x18001b34f  call    __security_check_cookie
0x18001b354  mov     rbx, [rsp+78h+arg_10]
0x18001b35c  add     rsp, 40h
0x18001b360  pop     r15
0x18001b362  pop     r14
0x18001b364  pop     r13
0x18001b366  pop     r12
0x18001b368  pop     rdi
0x18001b369  pop     rsi
0x18001b36a  pop     rbp
0x18001b36b  retn
0x18001b36c  mov     rdx, rbp; pvargSrc
0x18001b36f  lea     rcx, [rsp+78h+pvargDest]; pvargDest
0x18001b374  call    cs:__imp_VariantCopy
0x18001b37a  mov     edi, eax
0x18001b37c  test    eax, eax
0x18001b37e  js      short loc_18001B3FC
0x18001b380  lea     rcx, [r13+40h]; pvarg
0x18001b384  call    cs:__imp_VariantClear
0x18001b38a  movups  xmm0, xmmword ptr [rsp+78h+pvargDest]
0x18001b38f  movsd   xmm1, qword ptr [rsp+78h+pvargDest+10h]
0x18001b395  movups  xmmword ptr [r13+40h], xmm0
0x18001b39a  movsd   qword ptr [r13+50h], xmm1
0x18001b3a0  jmp     short loc_18001B334
0x18001b3a2  mov     edi, 80070005h
0x18001b3a7  mov     edx, edi
0x18001b3a9  jmp     loc_18001B327
0x18001b3ae  mov     ebx, 8007000Eh
0x18001b3b3  mov     edx, ebx
0x18001b3b5  jmp     short loc_18001B3C6
0x18001b3b7  mov     edx, 80070057h
0x18001b3bc  mov     ebx, edx
0x18001b3be  jmp     short loc_18001B3C6
0x18001b3c0  mov     ebx, r9d
0x18001b3c3  mov     edx, r9d
0x18001b3c6  lea     rcx, aFwvarianttoarr; "FwVariantToArrayOfLongs"
0x18001b3cd  call    cs:__imp_FwReportReturnError
0x18001b3d3  mov     rcx, rsi
0x18001b3d6  call    cs:__imp_FwBaseFree
0x18001b3dc  mov     edx, ebx
0x18001b3de  lea     rcx, aFwvarianttoarr; "FwVariantToArrayOfLongs"
0x18001b3e5  call    cs:__imp_FwReportReturnError
0x18001b3eb  mov     edi, eax
0x18001b3ed  test    eax, eax
0x18001b3ef  js      short loc_18001B3FC
0x18001b3f1  mov     r10d, 1
0x18001b3f7  jmp     loc_18001B2F3
0x18001b3fc  mov     edx, eax
0x18001b3fe  jmp     loc_18001B327
0x18001b403  mov     edx, edi
0x18001b405  lea     rcx, aFwproductPutRu; "FwProduct::put_RuleCategories"
0x18001b40c  call    cs:__imp_FwReportReturnError
0x18001b412  mov     edi, eax
0x18001b414  jmp     loc_18001B345
```
