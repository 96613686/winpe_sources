# ConvertXMPArrayToNumberArrayOnRead(tagPROPVARIANT const *,ushort,tagPROPVARIANT *)

- ea: `0x180020674`
- end: `0x180020959`
- name: `?ConvertXMPArrayToNumberArrayOnRead@@YAJPEBUtagPROPVARIANT@@GPEAU1@@Z`
- size: `741`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, unsigned __int16, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f4b0`

## callees

- `0x1800089f0`
- `0x180008b54`
- `0x1800096a0`
- `0x18000d8a0`
- `0x18000ea14`
- `0x18000f960`
- `0x1800103fc`
- `0x1800147f8`
- `0x180016a40`
- `0x180017408`
- `0x180020674`
- `0x180020f4c`
- `0x180021580`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800206ad`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800207e9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002087d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800206ad`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800207e9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002087d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800207fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020829`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002088f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800207fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020829`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002088f`

## pseudocode

```c
__int64 __fastcall ConvertXMPArrayToNumberArrayOnRead(
        const struct tagPROPVARIANT *a1,
        unsigned __int16 a2,
        struct tagPROPVARIANT *a3)
{
  int v4; // r12d
  ULONGLONG v6; // rdi
  __int64 v7; // r9
  HRESULT v8; // ebx
  unsigned int i; // r15d
  unsigned __int64 v10; // rsi
  __int64 v11; // r15
  unsigned __int64 k; // rdi
  void *v13; // rcx
  ULONGLONG v15; // rcx
  __int64 j; // rdi
  PROPVARIANT *pvar; // [rsp+20h] [rbp-99h] BYREF
  __int64 v18; // [rsp+28h] [rbp-91h] BYREF
  __int64 v19; // [rsp+30h] [rbp-89h] BYREF
  ULONGLONG ullOperand; // [rsp+38h] [rbp-81h]
  __int64 v21; // [rsp+40h] [rbp-79h]
  int v22; // [rsp+48h] [rbp-71h]
  ULONGLONG pullResult; // [rsp+50h] [rbp-69h] BYREF
  void *v24; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int16 v25[64]; // [rsp+60h] [rbp-59h] BYREF

  v4 = a2;
  PropVariantClear(a3);
  v6 = 2;
  v7 = (unsigned int)(v4 - 2);
  if ( v4 != 2 )
  {
    v7 = (unsigned int)(v4 - 3);
    if ( v4 != 3 )
    {
      v7 = (unsigned int)(v4 - 18);
      if ( v4 == 18 )
        goto LABEL_7;
      if ( v4 != 19 )
        return (unsigned int)-2147024809;
    }
    v6 = 4;
  }
LABEL_7:
  v8 = 0;
  if ( a1->vt == 13 )
  {
    v18 = 0;
    v8 = (**(__int64 (__fastcall ***)(LARGE_INTEGER, GUID *, __int64 *, __int64))a1->hVal.QuadPart)(
           a1->hVal,
           &GUID_30989668_e1c9_4597_b395_458eedb808df,
           &v18,
           v7);
    if ( v8 >= 0 )
    {
      v19 = 0;
      ullOperand = 0;
      v21 = 0;
      v22 = 0;
      memset_0(v25, 0, sizeof(v25));
      for ( i = 0; ; ++i )
      {
        v8 = StringCchPrintfW(v25, 0x40u, L"/{uint=%d}", i);
        v10 = ullOperand;
        if ( v8 < 0 )
          goto LABEL_16;
        pvar = 0;
        v8 = CoTaskMemAllocWithInit(0x18u, (void **)&pvar);
        if ( v8 < 0 )
          goto LABEL_16;
        v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, PROPVARIANT *))(*(_QWORD *)v18 + 40LL))(
               v18,
               v25,
               pvar);
        if ( v8 < 0 )
          break;
        if ( (int)ConvertPropvarFromStringToValue(pvar, v4) < 0 )
        {
          PropVariantClear(pvar);
          CoTaskMemFree(pvar);
          v8 = -2147418113;
LABEL_16:
          v11 = v19;
          goto LABEL_17;
        }
        ATL::CAtlArray<tagPROPVARIANT *,ATL::CElementTraits<tagPROPVARIANT *>>::Add(&v19, &pvar);
      }
      PropVariantClear(pvar);
      CoTaskMemFree(pvar);
      if ( v8 != -2003292352 )
        goto LABEL_16;
      pullResult = 0;
      LODWORD(pvar) = 0;
      v8 = ULongLongToULong(v10, (ULONG *)&pvar);
      if ( v8 < 0 )
        goto LABEL_21;
      v8 = ULongLongMult(v15, v6, &pullResult);
      if ( v8 < 0 )
        goto LABEL_16;
      v24 = 0;
      v8 = CoTaskMemAllocWithInit(pullResult, &v24);
      v11 = v19;
      if ( v8 >= 0 )
      {
        a3->vt = v4 | 0x1000;
        a3->lVal = v10;
        a3->bstrblobVal.pData = (BYTE *)v24;
        for ( j = 0; (unsigned int)j < (unsigned int)pvar; j = (unsigned int)(j + 1) )
        {
          if ( (unsigned int)j >= v10 )
            ATL::AtlThrowImpl(-2147024809);
          SetPropVariantElement(a3, j, *(const struct tagPROPVARIANT **)(v11 + 8 * j));
        }
      }
LABEL_17:
      for ( k = 0; k < v10; ++k )
      {
        v13 = *(void **)(v11 + 8 * k);
        if ( v13 )
          CoTaskMemFree(v13);
      }
LABEL_21:
      ATL::CAtlArray<unsigned short const *,ATL::CElementTraits<unsigned short const *>>::~CAtlArray<unsigned short const *,ATL::CElementTraits<unsigned short const *>>(&v19);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180020674  mov     [rsp-8+arg_8], rbx
0x180020679  mov     [rsp-8+arg_18], rsi
0x18002067e  push    rbp
0x18002067f  push    rdi
0x180020680  push    r12
0x180020682  push    r13
0x180020684  push    r15
0x180020686  lea     rbp, [rsp-37h]
0x18002068b  sub     rsp, 0F0h
0x180020692  mov     rax, cs:__security_cookie
0x180020699  xor     rax, rsp
0x18002069c  mov     [rbp+57h+var_30], rax
0x1800206a0  mov     r13, r8
0x1800206a3  movzx   r12d, dx
0x1800206a7  mov     rsi, rcx
0x1800206aa  mov     rcx, r8; pvar
0x1800206ad  call    cs:__imp_PropVariantClear
0x1800206b4  nop     dword ptr [rax+rax+00h]
0x1800206b9  mov     r9d, r12d
0x1800206bc  mov     edi, 2
0x1800206c1  sub     r9d, edi
0x1800206c4  jz      short loc_1800206E7
0x1800206c6  sub     r9d, 1
0x1800206ca  jz      short loc_1800206E2
0x1800206cc  sub     r9d, 0Fh
0x1800206d0  jz      short loc_1800206E7
0x1800206d2  cmp     r9d, 1
0x1800206d6  jz      short loc_1800206E2
0x1800206d8  mov     ebx, 80070057h
0x1800206dd  jmp     loc_180020852
0x1800206e2  mov     edi, 4
0x1800206e7  xor     ebx, ebx
0x1800206e9  cmp     word ptr [rsi], 0Dh
0x1800206ed  jnz     loc_180020852
0x1800206f3  mov     [rsp+110h+var_E8], rbx
0x1800206f8  mov     rcx, [rsi+8]
0x1800206fc  mov     rax, [rcx]
0x1800206ff  lea     r8, [rsp+110h+var_E8]
0x180020704  lea     rdx, _GUID_30989668_e1c9_4597_b395_458eedb808df
0x18002070b  mov     rax, [rax]
0x18002070e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020713  mov     ebx, eax
0x180020715  test    eax, eax
0x180020717  js      loc_180020848
0x18002071d  mov     [rsp+110h+var_E0], 0
0x180020726  mov     [rsp+110h+ullOperand], 0
0x18002072f  mov     [rbp+57h+var_D0], 0
0x180020737  mov     [rbp+57h+var_C8], 0
0x18002073e  xor     edx, edx; Val
0x180020740  mov     r8d, 80h; Size
0x180020746  lea     rcx, [rbp+57h+var_B0]; void *
0x18002074a  call    memset_0
0x18002074f  xor     r15d, r15d
0x180020752  mov     r9d, r15d
0x180020755  lea     r8, aUintD; "/{uint=%d}"
0x18002075c  mov     edx, 40h ; '@'; unsigned __int64
0x180020761  lea     rcx, [rbp+57h+var_B0]; unsigned __int16 *
0x180020765  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002076a  mov     ebx, eax
0x18002076c  mov     rsi, [rsp+110h+ullOperand]
0x180020771  test    eax, eax
0x180020773  js      loc_18002080B
0x180020779  mov     [rsp+110h+pvar], 0
0x180020782  lea     rdx, [rsp+110h+pvar]; void **
0x180020787  mov     ecx, 18h; Size
0x18002078c  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180020791  mov     ebx, eax
0x180020793  test    eax, eax
0x180020795  js      short loc_18002080B
0x180020797  mov     rcx, [rsp+110h+var_E8]
0x18002079c  mov     rax, [rcx]
0x18002079f  mov     r8, [rsp+110h+pvar]
0x1800207a4  lea     rdx, [rbp+57h+var_B0]
0x1800207a8  mov     rax, [rax+28h]
0x1800207ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207b1  mov     ebx, eax
0x1800207b3  mov     rcx, [rsp+110h+pvar]; pvar
0x1800207b8  test    eax, eax
0x1800207ba  js      loc_18002087D
0x1800207c0  movzx   edx, r12w; unsigned __int16
0x1800207c4  call    ?ConvertPropvarFromStringToValue@@YAJPEAUtagPROPVARIANT@@G@Z; ConvertPropvarFromStringToValue(tagPROPVARIANT *,ushort)
0x1800207c9  test    eax, eax
0x1800207cb  js      short loc_1800207E4
0x1800207cd  lea     rdx, [rsp+110h+pvar]
0x1800207d2  lea     rcx, [rsp+110h+var_E0]
0x1800207d7  call    ?Add@?$CAtlArray@PEAUtagPROPVARIANT@@V?$CElementTraits@PEAUtagPROPVARIANT@@@ATL@@@ATL@@QEAA_KAEBQEAUtagPROPVARIANT@@@Z; ATL::CAtlArray<tagPROPVARIANT *,ATL::CElementTraits<tagPROPVARIANT *>>::Add(tagPROPVARIANT * const &)
0x1800207dc  inc     r15d
0x1800207df  jmp     loc_180020752
0x1800207e4  mov     rcx, [rsp+110h+pvar]; pvar
0x1800207e9  call    cs:__imp_PropVariantClear
0x1800207f0  nop     dword ptr [rax+rax+00h]
0x1800207f5  mov     rcx, [rsp+110h+pvar]; pv
0x1800207fa  call    cs:__imp_CoTaskMemFree
0x180020801  nop     dword ptr [rax+rax+00h]
0x180020806  mov     ebx, 8000FFFFh
0x18002080b  mov     r15, [rsp+110h+var_E0]
0x180020810  xor     edi, edi
0x180020812  test    rsi, rsi
0x180020815  jz      short loc_18002083D
0x180020817  cmp     rdi, rsi
0x18002081a  jnb     loc_18002094E
0x180020820  mov     rcx, [r15+rdi*8]; pv
0x180020824  test    rcx, rcx
0x180020827  jz      short loc_180020835
0x180020829  call    cs:__imp_CoTaskMemFree
0x180020830  nop     dword ptr [rax+rax+00h]
0x180020835  inc     rdi
0x180020838  cmp     rdi, rsi
0x18002083b  jb      short loc_180020820
0x18002083d  lea     rcx, [rsp+110h+var_E0]
0x180020842  call    ??1?$CAtlArray@PEBGV?$CElementTraits@PEBG@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<ushort const *,ATL::CElementTraits<ushort const *>>::~CAtlArray<ushort const *,ATL::CElementTraits<ushort const *>>(void)
0x180020847  nop
0x180020848  lea     rcx, [rsp+110h+var_E8]
0x18002084d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020852  mov     eax, ebx
0x180020854  mov     rcx, [rbp+57h+var_30]
0x180020858  xor     rcx, rsp; StackCookie
0x18002085b  call    __security_check_cookie
0x180020860  lea     r11, [rsp+110h+var_20]
0x180020868  mov     rbx, [r11+38h]
0x18002086c  mov     rsi, [r11+48h]
0x180020870  mov     rsp, r11
0x180020873  pop     r15
0x180020875  pop     r13
0x180020877  pop     r12
0x180020879  pop     rdi
0x18002087a  pop     rbp
0x18002087b  retn
0x18002087d  call    cs:__imp_PropVariantClear
0x180020884  nop     dword ptr [rax+rax+00h]
0x180020889  nop
0x18002088a  mov     rcx, [rsp+110h+pvar]; pv
0x18002088f  call    cs:__imp_CoTaskMemFree
0x180020896  nop     dword ptr [rax+rax+00h]
0x18002089b  cmp     ebx, 88982F40h
0x1800208a1  jnz     loc_18002080B
0x1800208a7  mov     [rbp+57h+pullResult], 0
0x1800208af  mov     dword ptr [rsp+110h+pvar], 0
0x1800208b7  lea     rdx, [rsp+110h+pvar]; pulResult
0x1800208bc  mov     rcx, rsi; ullOperand
0x1800208bf  call    ULongLongToULong
0x1800208c4  mov     ebx, eax
0x1800208c6  test    eax, eax
0x1800208c8  js      loc_18002083D
0x1800208ce  lea     r8, [rbp+57h+pullResult]; pullResult
0x1800208d2  mov     rdx, rdi; ullMultiplier
0x1800208d5  call    ULongLongMult
0x1800208da  mov     ebx, eax
0x1800208dc  test    eax, eax
0x1800208de  js      loc_18002080B
0x1800208e4  mov     [rbp+57h+var_B8], 0
0x1800208ec  lea     rdx, [rbp+57h+var_B8]; void **
0x1800208f0  mov     rcx, [rbp+57h+pullResult]; Size
0x1800208f4  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x1800208f9  mov     ebx, eax
0x1800208fb  mov     r15, [rsp+110h+var_E0]
0x180020900  test    eax, eax
0x180020902  js      loc_180020810
0x180020908  or      r12w, 1000h
0x18002090e  mov     [r13+0], r12w
0x180020913  mov     [r13+8], esi
0x180020917  mov     rax, [rbp+57h+var_B8]
0x18002091b  mov     [r13+10h], rax
0x18002091f  xor     edi, edi
0x180020921  cmp     dword ptr [rsp+110h+pvar], edi
0x180020925  jbe     loc_180020810
0x18002092b  mov     r8d, edi
0x18002092e  cmp     r8, rsi
0x180020931  jnb     short loc_18002094E
0x180020933  mov     r8, [r15+rdi*8]; struct tagPROPVARIANT *
0x180020937  mov     edx, edi; unsigned int
0x180020939  mov     rcx, r13; struct tagPROPVARIANT *
0x18002093c  call    ?SetPropVariantElement@@YAJPEAUtagPROPVARIANT@@KPEBU1@@Z; SetPropVariantElement(tagPROPVARIANT *,ulong,tagPROPVARIANT const *)
0x180020941  inc     edi
0x180020943  cmp     edi, dword ptr [rsp+110h+pvar]
0x180020947  jb      short loc_18002092B
0x180020949  jmp     loc_180020810
0x18002094e  mov     ecx, 80070057h; int
0x180020953  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
