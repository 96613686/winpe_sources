# ConvertXMPArrayToNumberArrayOnRead(tagPROPVARIANT const *,ushort,tagPROPVARIANT *)

- ea: `0x18001f724`
- end: `0x18001f9cd`
- name: `?ConvertXMPArrayToNumberArrayOnRead@@YAJPEBUtagPROPVARIANT@@GPEAU1@@Z`
- size: `681`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, unsigned __int16, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e644`

## callees

- `0x1800076b0`
- `0x180007804`
- `0x180007d90`
- `0x18000cf60`
- `0x18000e364`
- `0x18000f1c0`
- `0x18000fc64`
- `0x180013e34`
- `0x180016020`
- `0x1800169b8`
- `0x18001f724`
- `0x18001ff7c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f75b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f886`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f904`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f75b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f886`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f904`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f88f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f8b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f90e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f88f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f8b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f90e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConvertXMPArrayToNumberArrayOnRead(
        const struct tagPROPVARIANT *a1,
        unsigned __int16 a2,
        struct tagPROPVARIANT *a3)
{
  int v4; // r12d
  ULONGLONG v6; // rsi
  __int64 v7; // r9
  HRESULT v8; // ebx
  unsigned int i; // r15d
  unsigned __int64 v10; // rdi
  PROPVARIANT *v11; // r14
  __int64 v12; // r14
  unsigned __int64 k; // rsi
  void *v14; // rcx
  __int64 j; // rsi
  PROPVARIANT *pvar; // [rsp+20h] [rbp-A9h] BYREF
  __int64 v18; // [rsp+28h] [rbp-A1h] BYREF
  __int64 v19; // [rsp+30h] [rbp-99h] BYREF
  ULONGLONG ullMultiplicand; // [rsp+38h] [rbp-91h]
  __int64 v21; // [rsp+40h] [rbp-89h]
  int v22; // [rsp+48h] [rbp-81h]
  void *v23; // [rsp+50h] [rbp-79h] BYREF
  unsigned __int16 v24[64]; // [rsp+60h] [rbp-69h] BYREF

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
      ullMultiplicand = 0;
      v21 = 0;
      v22 = 0;
      memset_0(v24, 0, sizeof(v24));
      for ( i = 0; ; ++i )
      {
        v8 = StringCchPrintfW(v24, 0x40u, L"/{uint=%d}", i);
        v10 = ullMultiplicand;
        if ( v8 < 0 )
          goto LABEL_16;
        pvar = 0;
        v8 = CoTaskMemAllocWithInit(0x18u, (void **)&pvar);
        if ( v8 < 0 )
          goto LABEL_16;
        v11 = pvar;
        v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, PROPVARIANT *))(*(_QWORD *)v18 + 40LL))(
               v18,
               v24,
               pvar);
        if ( v8 < 0 )
          break;
        if ( (int)ConvertPropvarFromStringToValue(v11, v4) < 0 )
        {
          PropVariantClear(v11);
          CoTaskMemFree(v11);
          v8 = -2147418113;
LABEL_16:
          v12 = v19;
          goto LABEL_17;
        }
        ATL::CAtlArray<tagPROPVARIANT *,ATL::CElementTraits<tagPROPVARIANT *>>::Add(&v19, &pvar);
      }
      PropVariantClear(v11);
      CoTaskMemFree(v11);
      if ( v8 != -2003292352 )
        goto LABEL_16;
      pvar = 0;
      if ( v10 > 0xFFFFFFFF )
      {
        v8 = -2147024362;
        goto LABEL_21;
      }
      v8 = ULongLongMult(v10, v6, (ULONGLONG *)&pvar);
      if ( v8 < 0 )
        goto LABEL_16;
      v23 = 0;
      v8 = CoTaskMemAllocWithInit((size_t)pvar, &v23);
      v12 = v19;
      if ( v8 >= 0 )
      {
        a3->vt = v4 | 0x1000;
        a3->lVal = v10;
        a3->bstrblobVal.pData = (BYTE *)v23;
        for ( j = 0; (unsigned int)j < (unsigned int)v10; j = (unsigned int)(j + 1) )
        {
          if ( (unsigned int)j >= v10 )
            ATL::AtlThrowImpl(-2147024809);
          SetPropVariantElement(a3, j, *(const struct tagPROPVARIANT **)(v12 + 8 * j));
        }
      }
LABEL_17:
      for ( k = 0; k < v10; ++k )
      {
        v14 = *(void **)(v12 + 8 * k);
        if ( v14 )
          CoTaskMemFree(v14);
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
0x18001f724  mov     [rsp-8+arg_8], rbx
0x18001f729  push    rbp
0x18001f72a  push    rsi
0x18001f72b  push    rdi
0x18001f72c  push    r12
0x18001f72e  push    r13
0x18001f730  push    r14
0x18001f732  push    r15
0x18001f734  lea     rbp, [rsp-27h]
0x18001f739  sub     rsp, 0F0h
0x18001f740  mov     rax, cs:__security_cookie
0x18001f747  xor     rax, rsp
0x18001f74a  mov     [rbp+57h+var_40], rax
0x18001f74e  mov     r13, r8
0x18001f751  movzx   r12d, dx
0x18001f755  mov     rdi, rcx
0x18001f758  mov     rcx, r8; pvar
0x18001f75b  call    cs:__imp_PropVariantClear
0x18001f761  mov     r9d, r12d
0x18001f764  mov     esi, 2
0x18001f769  sub     r9d, esi
0x18001f76c  jz      short loc_18001F78F
0x18001f76e  sub     r9d, 1
0x18001f772  jz      short loc_18001F78A
0x18001f774  sub     r9d, 0Fh
0x18001f778  jz      short loc_18001F78F
0x18001f77a  cmp     r9d, 1
0x18001f77e  jz      short loc_18001F78A
0x18001f780  mov     ebx, 80070057h
0x18001f785  jmp     loc_18001F8DB
0x18001f78a  mov     esi, 4
0x18001f78f  xor     r14d, r14d
0x18001f792  mov     ebx, r14d
0x18001f795  cmp     word ptr [rdi], 0Dh
0x18001f799  jnz     loc_18001F8DB
0x18001f79f  mov     [rsp+120h+var_F8], r14
0x18001f7a4  mov     rcx, [rdi+8]
0x18001f7a8  mov     rax, [rcx]
0x18001f7ab  lea     r8, [rsp+120h+var_F8]
0x18001f7b0  lea     rdx, _GUID_30989668_e1c9_4597_b395_458eedb808df
0x18001f7b7  mov     rax, [rax]
0x18001f7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7bf  mov     ebx, eax
0x18001f7c1  test    eax, eax
0x18001f7c3  js      loc_18001F8D1
0x18001f7c9  mov     [rsp+120h+var_F0], r14
0x18001f7ce  mov     [rsp+120h+ullMultiplicand], r14
0x18001f7d3  mov     [rsp+120h+var_E0], r14
0x18001f7d8  mov     [rsp+120h+var_D8], r14d
0x18001f7dd  xor     edx, edx; Val
0x18001f7df  mov     r8d, 80h; Size
0x18001f7e5  lea     rcx, [rbp+57h+var_C0]; void *
0x18001f7e9  call    memset_0
0x18001f7ee  mov     r15d, r14d
0x18001f7f1  mov     r9d, r15d
0x18001f7f4  lea     r8, aUintD; "/{uint=%d}"
0x18001f7fb  mov     edx, 40h ; '@'; unsigned __int64
0x18001f800  lea     rcx, [rbp+57h+var_C0]; unsigned __int16 *
0x18001f804  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f809  mov     ebx, eax
0x18001f80b  mov     rdi, [rsp+120h+ullMultiplicand]
0x18001f810  test    eax, eax
0x18001f812  js      loc_18001F89A
0x18001f818  mov     [rsp+120h+pvar], r14
0x18001f81d  lea     rdx, [rsp+120h+pvar]; void **
0x18001f822  mov     ecx, 18h; Size
0x18001f827  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18001f82c  mov     ebx, eax
0x18001f82e  test    eax, eax
0x18001f830  js      short loc_18001F89A
0x18001f832  mov     rcx, [rsp+120h+var_F8]
0x18001f837  mov     rax, [rcx]
0x18001f83a  mov     r14, [rsp+120h+pvar]
0x18001f83f  mov     r8, r14
0x18001f842  lea     rdx, [rbp+57h+var_C0]
0x18001f846  mov     rax, [rax+28h]
0x18001f84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f84f  mov     ebx, eax
0x18001f851  mov     rcx, r14; pvar
0x18001f854  test    eax, eax
0x18001f856  js      loc_18001F904
0x18001f85c  movzx   edx, r12w; unsigned __int16
0x18001f860  call    ?ConvertPropvarFromStringToValue@@YAJPEAUtagPROPVARIANT@@G@Z; ConvertPropvarFromStringToValue(tagPROPVARIANT *,ushort)
0x18001f865  test    eax, eax
0x18001f867  js      short loc_18001F883
0x18001f869  lea     rdx, [rsp+120h+pvar]
0x18001f86e  lea     rcx, [rsp+120h+var_F0]
0x18001f873  call    ?Add@?$CAtlArray@PEAUtagPROPVARIANT@@V?$CElementTraits@PEAUtagPROPVARIANT@@@ATL@@@ATL@@QEAA_KAEBQEAUtagPROPVARIANT@@@Z; ATL::CAtlArray<tagPROPVARIANT *,ATL::CElementTraits<tagPROPVARIANT *>>::Add(tagPROPVARIANT * const &)
0x18001f878  inc     r15d
0x18001f87b  xor     r14d, r14d
0x18001f87e  jmp     loc_18001F7F1
0x18001f883  mov     rcx, r14; pvar
0x18001f886  call    cs:__imp_PropVariantClear
0x18001f88c  mov     rcx, r14; pv
0x18001f88f  call    cs:__imp_CoTaskMemFree
0x18001f895  mov     ebx, 8000FFFFh
0x18001f89a  mov     r14, [rsp+120h+var_F0]
0x18001f89f  xor     esi, esi
0x18001f8a1  test    rdi, rdi
0x18001f8a4  jz      short loc_18001F8C6
0x18001f8a6  cmp     rsi, rdi
0x18001f8a9  jnb     loc_18001F9C2
0x18001f8af  mov     rcx, [r14+rsi*8]; pv
0x18001f8b3  test    rcx, rcx
0x18001f8b6  jz      short loc_18001F8BE
0x18001f8b8  call    cs:__imp_CoTaskMemFree
0x18001f8be  inc     rsi
0x18001f8c1  cmp     rsi, rdi
0x18001f8c4  jb      short loc_18001F8AF
0x18001f8c6  lea     rcx, [rsp+120h+var_F0]
0x18001f8cb  call    ??1?$CAtlArray@PEBGV?$CElementTraits@PEBG@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<ushort const *,ATL::CElementTraits<ushort const *>>::~CAtlArray<ushort const *,ATL::CElementTraits<ushort const *>>(void)
0x18001f8d0  nop
0x18001f8d1  lea     rcx, [rsp+120h+var_F8]
0x18001f8d6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001f8db  mov     eax, ebx
0x18001f8dd  mov     rcx, [rbp+57h+var_40]
0x18001f8e1  xor     rcx, rsp; StackCookie
0x18001f8e4  call    __security_check_cookie
0x18001f8e9  mov     rbx, [rsp+120h+arg_8]
0x18001f8f1  add     rsp, 0F0h
0x18001f8f8  pop     r15
0x18001f8fa  pop     r14
0x18001f8fc  pop     r13
0x18001f8fe  pop     r12
0x18001f900  pop     rdi
0x18001f901  pop     rsi
0x18001f902  pop     rbp
0x18001f903  retn
0x18001f904  call    cs:__imp_PropVariantClear
0x18001f90a  nop
0x18001f90b  mov     rcx, r14; pv
0x18001f90e  call    cs:__imp_CoTaskMemFree
0x18001f914  cmp     ebx, 88982F40h
0x18001f91a  jnz     loc_18001F89A
0x18001f920  mov     [rsp+120h+pvar], 0
0x18001f929  mov     eax, 0FFFFFFFFh
0x18001f92e  cmp     rdi, rax
0x18001f931  ja      loc_18001F9B8
0x18001f937  lea     r8, [rsp+120h+pvar]; pullResult
0x18001f93c  mov     rdx, rsi; ullMultiplier
0x18001f93f  mov     rcx, rdi; ullMultiplicand
0x18001f942  call    ULongLongMult
0x18001f947  mov     ebx, eax
0x18001f949  test    eax, eax
0x18001f94b  js      loc_18001F89A
0x18001f951  mov     [rbp+57h+var_D0], 0
0x18001f959  lea     rdx, [rbp+57h+var_D0]; void **
0x18001f95d  mov     rcx, [rsp+120h+pvar]; Size
0x18001f962  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18001f967  mov     ebx, eax
0x18001f969  mov     r14, [rsp+120h+var_F0]
0x18001f96e  test    eax, eax
0x18001f970  js      loc_18001F89F
0x18001f976  or      r12w, 1000h
0x18001f97c  mov     [r13+0], r12w
0x18001f981  mov     [r13+8], edi
0x18001f985  mov     rax, [rbp+57h+var_D0]
0x18001f989  mov     [r13+10h], rax
0x18001f98d  xor     esi, esi
0x18001f98f  test    edi, edi
0x18001f991  jz      loc_18001F89F
0x18001f997  mov     r8d, esi
0x18001f99a  cmp     r8, rdi
0x18001f99d  jnb     short loc_18001F9C2
0x18001f99f  mov     r8, [r14+rsi*8]; struct tagPROPVARIANT *
0x18001f9a3  mov     edx, esi; unsigned int
0x18001f9a5  mov     rcx, r13; struct tagPROPVARIANT *
0x18001f9a8  call    ?SetPropVariantElement@@YAJPEAUtagPROPVARIANT@@KPEBU1@@Z; SetPropVariantElement(tagPROPVARIANT *,ulong,tagPROPVARIANT const *)
0x18001f9ad  inc     esi
0x18001f9af  cmp     esi, edi
0x18001f9b1  jb      short loc_18001F997
0x18001f9b3  jmp     loc_18001F89F
0x18001f9b8  mov     ebx, 80070216h
0x18001f9bd  jmp     loc_18001F8C6
0x18001f9c2  mov     ecx, 80070057h; int
0x18001f9c7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
