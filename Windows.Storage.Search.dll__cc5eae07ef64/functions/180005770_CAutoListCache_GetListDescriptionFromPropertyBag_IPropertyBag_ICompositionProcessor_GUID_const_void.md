# CAutoListCache::GetListDescriptionFromPropertyBag(IPropertyBag *,ICompositionProcessor *,_GUID const &,void * *)

- ea: `0x180005770`
- end: `0x180005bdb`
- name: `?GetListDescriptionFromPropertyBag@CAutoListCache@@UEAAJPEAUIPropertyBag@@PEAUICompositionProcessor@@AEBU_GUID@@PEAPEAX@Z`
- size: `1131`
- prototype: `int(CAutoListCache *__hidden this, struct IPropertyBag *, struct ICompositionProcessor *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005608`
- `0x180005770`
- `0x180005fa4`
- `0x180072cd0`
- `0x18007db28`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IStream_Reset` at `0x180005acf`
- `SHCORE!IStream_Reset` at `0x180005acf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005861`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005861`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000590c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005931`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000590c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005931`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000595c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000595c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000593f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005966`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005b1b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005b25`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005b85`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000593f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005966`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005b1b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005b25`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005b85`
- `PROPSYS!PropVariantToStringAlloc` at `0x180005810`
- `PROPSYS!PropVariantToStringAlloc` at `0x180005810`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x180005bc9`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x180005bc9`
- `PROPSYS!PropVariantCompareEx` at `0x180005a02`
- `PROPSYS!PropVariantCompareEx` at `0x180005a02`
- `PROPSYS!PropVariantChangeType` at `0x180005abf`
- `PROPSYS!PropVariantChangeType` at `0x180005abf`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b8f`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b8f`
- `OLEAUT32!__imp_SysStringLen` at `0x180005b3e`
- `OLEAUT32!__imp_SysStringLen` at `0x180005b3e`

## string_xrefs

- `0x1800057ec`: `AutolistCacheKey`
- `0x180005838`: `AutolistCacheTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAutoListCache::GetListDescriptionFromPropertyBag(
        CAutoListCache *this,
        struct IPropertyBag *a2,
        struct ICompositionProcessor *a3,
        const struct _GUID *a4,
        void **pbstr)
{
  const struct _GUID *v5; // r15
  struct ICompositionProcessor *v6; // r12
  IPropertyBag *v7; // rsi
  void **v9; // rdi
  HRESULT BSTR; // ebx
  PWSTR v11; // rbx
  __int64 v12; // rax
  __int64 v13; // r15
  unsigned int v14; // r13d
  unsigned int v15; // r9d
  __int64 (__fastcall *v16)(PWSTR, _QWORD, _QWORD); // rax
  unsigned int v17; // eax
  unsigned __int64 i; // r8
  unsigned int v19; // eax
  __int64 *v20; // rsi
  const struct _GUID *v22; // r8
  OLECHAR *v23; // rcx
  __int64 v24; // [rsp+20h] [rbp-60h] BYREF
  __int64 v25; // [rsp+28h] [rbp-58h] BYREF
  PWSTR ppszOut; // [rsp+30h] [rbp-50h] BYREF
  PROPVARIANT pvar[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v28; // [rsp+48h] [rbp-38h]
  struct tagPROPVARIANT propvarSrc; // [rsp+50h] [rbp-30h] BYREF
  PROPVARIANT propvar[2]; // [rsp+68h] [rbp-18h] BYREF
  __int64 v31; // [rsp+78h] [rbp-8h]

  v5 = a4;
  v6 = a3;
  v7 = a2;
  v9 = pbstr;
  *pbstr = 0;
  v25 = 0;
  if ( ((__int64 (__fastcall *)(struct IPropertyBag *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
         &v25) < 0 )
  {
LABEL_49:
    pbstr = 0;
    BSTR = PSPropertyBag_ReadBSTR(v7, L"AutoList", (BSTR *)&pbstr);
    if ( BSTR >= 0 )
    {
      BSTR = -2147467259;
      v23 = (OLECHAR *)pbstr;
      if ( !pbstr )
      {
LABEL_46:
        SysFreeString(v23);
        return (unsigned int)BSTR;
      }
      if ( SysStringLen((BSTR)pbstr) )
      {
        memset(&propvarSrc, 0, sizeof(propvarSrc));
        BSTR = InitPropVariantFromStringEx((unsigned __int16 *)pbstr);
        if ( BSTR >= 0 )
        {
          BSTR = LoadBinaryAutoListFromStreamPropVariant(&propvarSrc, v6, v5, v9);
          PropVariantClear((PROPVARIANT *)&propvarSrc);
        }
      }
    }
    v23 = (OLECHAR *)pbstr;
    goto LABEL_46;
  }
  *(_OWORD *)propvar = 0;
  v31 = 0;
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, PROPVARIANT *))(*(_QWORD *)v25 + 24LL))(
         v25,
         L"AutolistCacheKey",
         propvar) >= 0 )
  {
    ppszOut = 0;
    BSTR = PropVariantToStringAlloc(propvar, &ppszOut);
    if ( BSTR < 0 )
      goto LABEL_21;
    *(_OWORD *)pvar = 0;
    v28 = 0;
    BSTR = (*(__int64 (__fastcall **)(__int64, const wchar_t *, PROPVARIANT *))(*(_QWORD *)v25 + 24LL))(
             v25,
             L"AutolistCacheTime",
             pvar);
    if ( BSTR < 0 )
    {
LABEL_20:
      CoTaskMemFree(ppszOut);
LABEL_21:
      PropVariantClear(propvar);
      if ( BSTR >= 0 )
        goto LABEL_22;
      goto LABEL_35;
    }
    v11 = ppszOut;
    *v9 = 0;
    v24 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    if ( *((_QWORD *)this + 10) )
    {
      v12 = -1;
      do
        ++v12;
      while ( v11[v12] );
      v13 = 0;
      v14 = 2 * v12 + 2;
      v15 = *((_DWORD *)this + 19);
      v16 = (__int64 (__fastcall *)(PWSTR, _QWORD, _QWORD))*((_QWORD *)this + 8);
      if ( v16 )
      {
        v19 = v16(v11, v14, v15);
      }
      else
      {
        v17 = 314159269;
        for ( i = 0; i < v14; v17 ^= (v17 >> 2) + 2080 * v17 + *((unsigned __int8 *)v11 + i++) )
          ;
        v19 = (v17 & 0x7FFFFFFF) % v15;
      }
      v20 = *(__int64 **)(*((_QWORD *)this + 10) + 8LL * v19);
      if ( !v20 )
        goto LABEL_13;
      while ( v14 != *((_DWORD *)v20 + 2) || memcmp_0(v11, (char *)v20 + *((unsigned int *)this + 24), v14) )
      {
        v20 = (__int64 *)*v20;
        if ( !v20 )
          goto LABEL_13;
      }
      if ( *((_DWORD *)this + 22) == 8 )
      {
        BSTR = 0;
        v13 = *(__int64 *)((char *)v20 + *((unsigned int *)this + 23));
      }
      else
      {
LABEL_13:
        BSTR = -2147319765;
      }
      if ( BSTR < 0 )
        goto LABEL_18;
      if ( !LOWORD(pvar[0]) || !PropVariantCompareEx(pvar, (const PROPVARIANT *const)(v13 + 8), PVCU_DEFAULT, 0) )
      {
        v24 = 0;
        if ( *(_QWORD *)v13 )
          BSTR = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v13)(
                   *(_QWORD *)v13,
                   &GUID_cd17328b_e4ef_4215_a92d_62a914658f82,
                   &v24);
        else
          BSTR = -2147467259;
LABEL_18:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
        if ( BSTR >= 0 )
        {
          BSTR = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 24LL))(v24);
          if ( BSTR >= 0 )
            BSTR = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v24)(v24, a4, pbstr);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        goto LABEL_19;
      }
    }
    BSTR = -2147467259;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
LABEL_19:
    PropVariantClear(pvar);
    v9 = pbstr;
    v7 = a2;
    v5 = a4;
    v6 = a3;
    goto LABEL_20;
  }
LABEL_35:
  memset(&propvarSrc, 0, sizeof(propvarSrc));
  BSTR = (*(__int64 (__fastcall **)(__int64, const WCHAR *, struct tagPROPVARIANT *))(*(_QWORD *)v25 + 24LL))(
           v25,
           L"AutoList",
           &propvarSrc);
  if ( BSTR >= 0 )
  {
    *(_OWORD *)pvar = 0;
    v28 = 0;
    BSTR = PropVariantChangeType(pvar, (const PROPVARIANT *const)&propvarSrc, 0, 0x42u);
    if ( BSTR >= 0 )
    {
      IStream_Reset((IStream *)pvar[1]);
      pbstr = 0;
      BSTR = LoadBinaryAutoListFromStream((struct IStream *)pvar[1], v6, v22, (void **)&pbstr);
      if ( BSTR >= 0 )
      {
        BSTR = (*((__int64 (__fastcall **)(void **, const struct _GUID *, void **))*pbstr + 3))(pbstr, v5, v9);
        (*((void (__fastcall **)(void **))*pbstr + 2))(pbstr);
      }
      PropVariantClear(pvar);
    }
    PropVariantClear((PROPVARIANT *)&propvarSrc);
  }
LABEL_22:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( BSTR < 0 )
    goto LABEL_49;
  return (unsigned int)BSTR;
}

```

## disassembly

```asm
0x180005770  mov     [rsp-38h+arg_0], rbx
0x180005775  mov     [rsp-38h+arg_18], r9
0x18000577a  mov     [rsp-38h+arg_10], r8
0x18000577f  mov     [rsp-38h+arg_8], rdx
0x180005784  push    rbp
0x180005785  push    rsi
0x180005786  push    rdi
0x180005787  push    r12
0x180005789  push    r13
0x18000578b  push    r14
0x18000578d  push    r15
0x18000578f  mov     rbp, rsp
0x180005792  sub     rsp, 80h
0x180005799  mov     r15, r9
0x18000579c  mov     r12, r8
0x18000579f  mov     rsi, rdx
0x1800057a2  mov     r14, rcx
0x1800057a5  xor     r13d, r13d
0x1800057a8  mov     rdi, [rbp+pbstr]
0x1800057ac  mov     [rdi], r13
0x1800057af  mov     [rbp+var_58], r13
0x1800057b3  mov     rax, [rdx]
0x1800057b6  lea     r8, [rbp+var_58]
0x1800057ba  lea     rdx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x1800057c1  mov     rcx, rsi
0x1800057c4  mov     rax, [rax]
0x1800057c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057cc  test    eax, eax
0x1800057ce  js      loc_180005BB7
0x1800057d4  xorps   xmm0, xmm0
0x1800057d7  xor     eax, eax
0x1800057d9  movups  xmmword ptr [rbp+propvar], xmm0
0x1800057dd  mov     [rbp+var_8], rax
0x1800057e1  mov     rcx, [rbp+var_58]
0x1800057e5  mov     rax, [rcx]
0x1800057e8  lea     r8, [rbp+propvar]
0x1800057ec  lea     rdx, aAutolistcachek; "AutolistCacheKey"
0x1800057f3  mov     rax, [rax+18h]
0x1800057f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057fc  test    eax, eax
0x1800057fe  js      loc_180005A6F
0x180005804  mov     [rbp+ppszOut], r13
0x180005808  lea     rdx, [rbp+ppszOut]; ppszOut
0x18000580c  lea     rcx, [rbp+propvar]; propvar
0x180005810  call    cs:__imp_PropVariantToStringAlloc
0x180005816  mov     ebx, eax
0x180005818  test    eax, eax
0x18000581a  js      loc_180005962
0x180005820  xorps   xmm0, xmm0
0x180005823  xor     eax, eax
0x180005825  movups  xmmword ptr [rbp+pvar], xmm0
0x180005829  mov     [rbp+var_38], rax
0x18000582d  mov     rcx, [rbp+var_58]
0x180005831  mov     rax, [rcx]
0x180005834  lea     r8, [rbp+pvar]
0x180005838  lea     rdx, aAutolistcachet; "AutolistCacheTime"
0x18000583f  mov     rax, [rax+18h]
0x180005843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005848  mov     ebx, eax
0x18000584a  test    eax, eax
0x18000584c  js      loc_180005958
0x180005852  mov     rbx, [rbp+ppszOut]
0x180005856  mov     [rdi], r13
0x180005859  mov     [rbp+var_60], r13
0x18000585d  lea     rcx, [r14+18h]; lpCriticalSection
0x180005861  call    cs:__imp_EnterCriticalSection
0x180005867  cmp     [r14+50h], r13
0x18000586b  jz      loc_180005903
0x180005871  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005878  nop     dword ptr [rax+rax+00000000h]
0x180005880  lea     rax, [rax+1]
0x180005884  cmp     [rbx+rax*2], r13w
0x180005889  jnz     short loc_180005880
0x18000588b  xor     r15d, r15d
0x18000588e  lea     r13d, ds:2[rax*2]
0x180005896  mov     r9d, [r14+4Ch]
0x18000589a  mov     rax, [r14+40h]
0x18000589e  mov     edi, r13d
0x1800058a1  test    rax, rax
0x1800058a4  jnz     loc_180005B9A
0x1800058aa  mov     eax, 12B9B0A5h
0x1800058af  xor     r8d, r8d
0x1800058b2  test    r13d, r13d
0x1800058b5  jz      short loc_1800058DE
0x1800058b7  nop     word ptr [rax+rax+00000000h]
0x1800058c0  movzx   edx, byte ptr [rbx+r8]
0x1800058c5  imul    ecx, eax, 820h
0x1800058cb  add     edx, ecx
0x1800058cd  mov     ecx, eax
0x1800058cf  shr     ecx, 2
0x1800058d2  add     edx, ecx
0x1800058d4  xor     eax, edx
0x1800058d6  inc     r8
0x1800058d9  cmp     r8, rdi
0x1800058dc  jb      short loc_1800058C0
0x1800058de  btr     eax, 1Fh
0x1800058e2  xor     edx, edx
0x1800058e4  div     r9d
0x1800058e7  mov     eax, edx
0x1800058e9  mov     ecx, eax
0x1800058eb  mov     rax, [r14+50h]
0x1800058ef  mov     rsi, [rax+rcx*8]
0x1800058f3  test    rsi, rsi
0x1800058f6  jnz     loc_180005A41
0x1800058fc  mov     ebx, 8002802Bh
0x180005901  jmp     short loc_180005925
0x180005903  mov     ebx, 80004005h
0x180005908  lea     rcx, [r14+18h]; lpCriticalSection
0x18000590c  call    cs:__imp_LeaveCriticalSection
0x180005912  jmp     short loc_18000593B
0x180005914  cmp     dword ptr [r14+58h], 8
0x180005919  jnz     short loc_1800058FC
0x18000591b  xor     ebx, ebx
0x18000591d  mov     eax, [r14+5Ch]
0x180005921  mov     r15, [rax+rsi]
0x180005925  test    ebx, ebx
0x180005927  jns     loc_1800059ED
0x18000592d  lea     rcx, [r14+18h]; lpCriticalSection
0x180005931  call    cs:__imp_LeaveCriticalSection
0x180005937  test    ebx, ebx
0x180005939  jns     short loc_1800059A9
0x18000593b  lea     rcx, [rbp+pvar]; pvar
0x18000593f  call    cs:__imp_PropVariantClear
0x180005945  mov     rdi, [rbp+pbstr]
0x180005949  mov     rsi, [rbp+arg_8]
0x18000594d  mov     r15, [rbp+arg_18]
0x180005951  mov     r12, [rbp+arg_10]
0x180005955  xor     r13d, r13d
0x180005958  mov     rcx, [rbp+ppszOut]; pv
0x18000595c  call    cs:__imp_CoTaskMemFree
0x180005962  lea     rcx, [rbp+propvar]; pvar
0x180005966  call    cs:__imp_PropVariantClear
0x18000596c  test    ebx, ebx
0x18000596e  js      loc_180005A6F
0x180005974  mov     rcx, [rbp+var_58]
0x180005978  mov     rax, [rcx]
0x18000597b  mov     rax, [rax+10h]
0x18000597f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005984  test    ebx, ebx
0x180005986  js      loc_180005BB7
0x18000598c  mov     eax, ebx
0x18000598e  mov     rbx, [rsp+80h+arg_0]
0x180005996  add     rsp, 80h
0x18000599d  pop     r15
0x18000599f  pop     r14
0x1800059a1  pop     r13
0x1800059a3  pop     r12
0x1800059a5  pop     rdi
0x1800059a6  pop     rsi
0x1800059a7  pop     rbp
0x1800059a8  retn
0x1800059a9  mov     rcx, [rbp+var_60]
0x1800059ad  mov     rax, [rcx]
0x1800059b0  mov     rax, [rax+18h]
0x1800059b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b9  mov     ebx, eax
0x1800059bb  test    eax, eax
0x1800059bd  js      short loc_1800059D8
0x1800059bf  mov     rcx, [rbp+var_60]
0x1800059c3  mov     rax, [rcx]
0x1800059c6  mov     r8, [rbp+pbstr]
0x1800059ca  mov     rdx, [rbp+arg_18]
0x1800059ce  mov     rax, [rax]
0x1800059d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059d6  mov     ebx, eax
0x1800059d8  mov     rcx, [rbp+var_60]
0x1800059dc  mov     rax, [rcx]
0x1800059df  mov     rax, [rax+10h]
0x1800059e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e8  jmp     loc_18000593B
0x1800059ed  cmp     word ptr [rbp+pvar], 0
0x1800059f2  jz      short loc_180005A10
0x1800059f4  lea     rdx, [r15+8]; propvar2
0x1800059f8  xor     r9d, r9d; flags
0x1800059fb  xor     r8d, r8d; unit
0x1800059fe  lea     rcx, [rbp+pvar]; propvar1
0x180005a02  call    cs:__imp_PropVariantCompareEx
0x180005a08  test    eax, eax
0x180005a0a  jnz     loc_180005903
0x180005a10  mov     [rbp+var_60], 0
0x180005a18  mov     rcx, [r15]
0x180005a1b  test    rcx, rcx
0x180005a1e  jz      loc_180005BAD
0x180005a24  mov     rax, [rcx]
0x180005a27  lea     r8, [rbp+var_60]
0x180005a2b  lea     rdx, _GUID_cd17328b_e4ef_4215_a92d_62a914658f82
0x180005a32  mov     rax, [rax]
0x180005a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a3a  mov     ebx, eax
0x180005a3c  jmp     loc_18000592D
0x180005a41  cmp     r13d, [rsi+8]
0x180005a45  jnz     short loc_180005A61
0x180005a47  mov     edx, [r14+60h]
0x180005a4b  add     rdx, rsi; Buf2
0x180005a4e  mov     r8, rdi; Size
0x180005a51  mov     rcx, rbx; Buf1
0x180005a54  call    memcmp_0
0x180005a59  test    eax, eax
0x180005a5b  jz      loc_180005914
0x180005a61  mov     rsi, [rsi]
0x180005a64  test    rsi, rsi
0x180005a67  jz      loc_1800058FC
0x180005a6d  jmp     short loc_180005A41
0x180005a6f  xorps   xmm0, xmm0
0x180005a72  xor     eax, eax
0x180005a74  movups  xmmword ptr [rbp+propvarSrc], xmm0
0x180005a78  mov     [rbp+var_20], rax
0x180005a7c  mov     rcx, [rbp+var_58]
0x180005a80  mov     rax, [rcx]
0x180005a83  lea     r8, [rbp+propvarSrc]
0x180005a87  lea     rdx, propName; "AutoList"
0x180005a8e  mov     rax, [rax+18h]
0x180005a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a97  mov     ebx, eax
0x180005a99  test    eax, eax
0x180005a9b  js      loc_180005974
0x180005aa1  xorps   xmm0, xmm0
0x180005aa4  xor     eax, eax
0x180005aa6  movups  xmmword ptr [rbp+pvar], xmm0
0x180005aaa  mov     [rbp+var_38], rax
0x180005aae  mov     r9d, 42h ; 'B'; vt
0x180005ab4  xor     r8d, r8d; flags
0x180005ab7  lea     rdx, [rbp+propvarSrc]; propvarSrc
0x180005abb  lea     rcx, [rbp+pvar]; ppropvarDest
0x180005abf  call    cs:__imp_PropVariantChangeType
0x180005ac5  mov     ebx, eax
0x180005ac7  test    eax, eax
0x180005ac9  js      short loc_180005B21
0x180005acb  mov     rcx, [rbp+pvar+8]; pstm
0x180005acf  call    cs:__imp_IStream_Reset
0x180005ad5  mov     [rbp+pbstr], r13
0x180005ad9  lea     r9, [rbp+pbstr]; void **
0x180005add  mov     rdx, r12; struct ICompositionProcessor *
0x180005ae0  mov     rcx, [rbp+pvar+8]; struct IStream *
0x180005ae4  call    ?LoadBinaryAutoListFromStream@@YAJPEAUIStream@@PEAUICompositionProcessor@@AEBU_GUID@@PEAPEAX@Z; LoadBinaryAutoListFromStream(IStream *,ICompositionProcessor *,_GUID const &,void * *)
0x180005ae9  mov     ebx, eax
0x180005aeb  test    eax, eax
0x180005aed  js      short loc_180005B17
0x180005aef  mov     rcx, [rbp+pbstr]
0x180005af3  mov     rax, [rcx]
0x180005af6  mov     r8, rdi
0x180005af9  mov     rdx, r15
0x180005afc  mov     rax, [rax+18h]
0x180005b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b05  mov     ebx, eax
0x180005b07  mov     rcx, [rbp+pbstr]
0x180005b0b  mov     rax, [rcx]
0x180005b0e  mov     rax, [rax+10h]
0x180005b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b17  lea     rcx, [rbp+pvar]; pvar
0x180005b1b  call    cs:__imp_PropVariantClear
0x180005b21  lea     rcx, [rbp+propvarSrc]; pvar
0x180005b25  call    cs:__imp_PropVariantClear
0x180005b2b  jmp     loc_180005974
0x180005b30  mov     ebx, 80004005h
0x180005b35  mov     rcx, [rbp+pbstr]; pbstr
0x180005b39  test    rcx, rcx
0x180005b3c  jz      short loc_180005B8F
0x180005b3e  call    cs:__imp_SysStringLen
0x180005b44  test    eax, eax
0x180005b46  jz      short loc_180005B8B
0x180005b48  xorps   xmm0, xmm0
0x180005b4b  xor     eax, eax
0x180005b4d  movups  xmmword ptr [rbp+propvarSrc], xmm0
0x180005b51  mov     [rbp+var_20], rax
0x180005b55  mov     edx, 42h ; 'B'
0x180005b5a  lea     r8, [rbp+propvarSrc]
0x180005b5e  mov     rcx, [rbp+pbstr]; unsigned __int16 *
0x180005b62  call    InitPropVariantFromStringEx
0x180005b67  mov     ebx, eax
0x180005b69  test    eax, eax
0x180005b6b  js      short loc_180005B8B
0x180005b6d  mov     r9, rdi; void **
0x180005b70  mov     r8, r15; struct _GUID *
0x180005b73  mov     rdx, r12; struct ICompositionProcessor *
0x180005b76  lea     rcx, [rbp+propvarSrc]; struct tagPROPVARIANT *
0x180005b7a  call    ?LoadBinaryAutoListFromStreamPropVariant@@YAJAEBUtagPROPVARIANT@@PEAUICompositionProcessor@@AEBU_GUID@@PEAPEAX@Z; LoadBinaryAutoListFromStreamPropVariant(tagPROPVARIANT const &,ICompositionProcessor *,_GUID const &,void * *)
0x180005b7f  mov     ebx, eax
0x180005b81  lea     rcx, [rbp+propvarSrc]; pvar
0x180005b85  call    cs:__imp_PropVariantClear
0x180005b8b  mov     rcx, [rbp+pbstr]; bstrString
0x180005b8f  call    cs:__imp_SysFreeString
0x180005b95  jmp     loc_18000598C
0x180005b9a  mov     r8d, r9d
0x180005b9d  mov     edx, r13d
0x180005ba0  mov     rcx, rbx
0x180005ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ba8  jmp     loc_1800058E9
0x180005bad  mov     ebx, 80004005h
0x180005bb2  jmp     loc_18000592D
0x180005bb7  mov     [rbp+pbstr], r13
0x180005bbb  lea     r8, [rbp+pbstr]; value
0x180005bbf  lea     rdx, propName; "AutoList"
0x180005bc6  mov     rcx, rsi; propBag
0x180005bc9  call    cs:__imp_PSPropertyBag_ReadBSTR
0x180005bcf  mov     ebx, eax
0x180005bd1  test    eax, eax
0x180005bd3  js      short loc_180005B8B
0x180005bd5  jmp     loc_180005B30
```
