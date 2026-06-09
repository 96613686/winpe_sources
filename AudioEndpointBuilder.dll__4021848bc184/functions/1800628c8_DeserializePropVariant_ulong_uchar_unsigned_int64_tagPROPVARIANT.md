# DeserializePropVariant(ulong,uchar *,unsigned __int64,tagPROPVARIANT *)

- ea: `0x1800628c8`
- end: `0x180062d1b`
- name: `?DeserializePropVariant@@YAJKPEAE_KPEAUtagPROPVARIANT@@@Z`
- size: `1107`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800322a0`

## callees

- `0x18000ceb0`
- `0x180010da8`
- `0x18003f78c`
- `0x18005ea84`
- `0x1800627ec`
- `0x18006286c`
- `0x1800628c8`
- `0x1800638e4`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180062a5a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180062b31`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180062a5a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180062b31`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180062a4d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180062b20`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180062b43`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180062a4d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180062b20`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180062b43`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180062bc6`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180062bc6`

## string_xrefs

- `0x1800628fb`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x18006291d`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180062a34`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180062afc`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180062cb1`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`

## pseudocode

```c
__int64 __fastcall DeserializePropVariant(__int64 a1, unsigned __int8 *a2, __int64 a3, struct tagPROPVARIANT *a4)
{
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v9; // rdx
  unsigned int v10; // edi
  unsigned __int64 v11; // rbx
  __int64 v12; // rcx
  unsigned __int64 v13; // r15
  int v14; // r14d
  __int64 v15; // rdx
  SAFEARRAY *v16; // rbx
  unsigned __int8 *v17; // r10
  unsigned int i; // ebx
  unsigned __int8 *v19; // r12
  _DWORD *v20; // r10
  __int64 v21; // rdx
  SAFEARRAY *v22; // rbx
  SAFEARRAY *v23; // rbx
  BSTR v24; // rax
  unsigned __int8 *v25; // rcx
  __int64 v26; // rdx
  int v27; // esi
  __int64 v28; // rdx
  size_t v29; // r8
  SAFEARRAY *psa; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int64 v31; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+40h]
  unsigned __int64 v33; // [rsp+88h] [rbp+50h] BYREF

  if ( !a2 )
  {
    v6 = -2147467261;
    v7 = 803;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
      (const char *)(unsigned int)v6,
      (int)psa);
    return (unsigned int)v6;
  }
  if ( !a3 )
  {
    v9 = 804;
LABEL_6:
    v10 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
      (const char *)0x80070057LL,
      (int)psa);
    return v10;
  }
  *(_OWORD *)&a4->vt = 0;
  a4->bstrblobVal.pData = 0;
  if ( (_DWORD)a1 == 4 )
  {
    a4->vt = 19;
    a4->lVal = *(_DWORD *)a2;
    return 0;
  }
  if ( (_DWORD)a1 == 1 )
  {
    v6 = _AllocString<CTCoAllocPolicy>(a1, a2, a2, &a4->decVal.Lo32);
    if ( v6 < 0 )
    {
      v7 = 817;
      goto LABEL_3;
    }
    a4->vt = 31;
    return 0;
  }
  v11 = *(unsigned __int16 *)a2;
  if ( (v11 & 0x1000) != 0 )
  {
    LOWORD(v11) = (v11 & 0xEFFF) - 8;
    if ( (unsigned __int16)v11 <= 0x39u )
    {
      v12 = 0x200000000C00001LL;
      if ( _bittest64(&v12, v11) )
      {
        v9 = 832;
        goto LABEL_6;
      }
    }
    a4->lVal = *((_DWORD *)a2 + 1);
    v6 = AllocCoMemCopy(a2 + 8, a3 - 8, &a4->bstrblobVal.pData);
    if ( v6 < 0 )
    {
      v7 = 839;
      goto LABEL_3;
    }
    a4->vt = *(_WORD *)a2;
    return 0;
  }
  if ( (v11 & 0x2004) != 0x2004 )
  {
    if ( (unsigned int)v11 > 0x1E )
    {
      switch ( (_DWORD)v11 )
      {
        case '@':
LABEL_77:
          v29 = a3 - 8;
          if ( v29 > 0x10 )
          {
            v9 = 891;
            goto LABEL_6;
          }
          memcpy_0(&a4->decVal.8, a2 + 8, v29);
          break;
        case 'A':
          a4->lVal = a3 - 8;
          v27 = AllocCoMemCopy(a2 + 8, (unsigned int)(a3 - 8), &a4->bstrblobVal.pData);
          if ( v27 < 0 )
          {
            v28 = 926;
            goto LABEL_74;
          }
          break;
        case 'H':
          v27 = AllocCoMemCopy(a2 + 8, 0x10u, &a4->pbVal);
          if ( v27 < 0 )
          {
            v28 = 901;
            goto LABEL_74;
          }
          break;
        default:
          goto LABEL_64;
      }
    }
    else
    {
      if ( (_DWORD)v11 != 30 )
      {
        if ( (unsigned int)v11 > 9 )
        {
          if ( (_DWORD)v11 != 10
            && (_DWORD)v11 != 11
            && ((_DWORD)v11 == 13 || (_DWORD)v11 != 17 && (_DWORD)v11 != 18 && (unsigned int)(v11 - 20) >= 2) )
          {
            goto LABEL_64;
          }
        }
        else
        {
          if ( (_DWORD)v11 == 9 )
            goto LABEL_64;
          if ( (_DWORD)v11 != 2
            && (_DWORD)v11 != 3
            && (_DWORD)v11 != 4
            && (_DWORD)v11 != 5
            && (_DWORD)v11 != 6
            && (_DWORD)v11 != 7 )
          {
            if ( (_DWORD)v11 == 8 )
            {
              if ( a2 == (unsigned __int8 *)-8LL )
              {
                v9 = 907;
                goto LABEL_6;
              }
              v24 = SysAllocStringByteLen((LPCSTR)a2 + 8, (int)a3 - 10);
              a4->hVal.QuadPart = (LONGLONG)v24;
              if ( !v24 )
              {
                v6 = -2147024882;
                v7 = 912;
                goto LABEL_3;
              }
              goto LABEL_80;
            }
LABEL_64:
            v6 = -2147023266;
            v7 = 941;
            goto LABEL_3;
          }
        }
        goto LABEL_77;
      }
      v25 = a2 + 8;
      v26 = -1;
      do
        ++v26;
      while ( v25[v26] );
      v27 = AllocCoMemCopy(v25, v26 + 1, &a4->pbVal);
      if ( v27 < 0 )
      {
        v28 = 919;
LABEL_74:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v28,
          (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
          (const char *)(unsigned int)v27,
          (int)psa);
        return (unsigned int)v27;
      }
    }
LABEL_80:
    a4->vt = v11;
    return 0;
  }
  v31 = a3 - 24;
  v13 = (unsigned __int64)(a3 - 24) >> 2;
  psa = 0;
  v14 = ATL::CComSafeArray<float,4>::Create(&psa, (unsigned int)v13, a3, a3);
  if ( v14 >= 0 )
  {
    v17 = a2 + 24;
    for ( i = 0; ; ++i )
    {
      if ( i >= v13 )
      {
        v23 = psa;
        SafeArrayUnlock(psa);
        a4->hVal.QuadPart = (LONGLONG)v23;
        a4->vt = *(_WORD *)a2;
        return 0;
      }
      v33 = 0;
      v19 = v17 + 4;
      if ( v17 + 4 < v17 )
        break;
      v14 = ULongLongSub((unsigned __int64)(v17 + 4), (unsigned __int64)(a2 + 24), &v33);
      if ( v14 < 0 )
      {
        v15 = 857;
        goto LABEL_24;
      }
      if ( v33 > v31 )
      {
        v10 = -2147024809;
        v21 = 859;
        goto LABEL_39;
      }
      LODWORD(v33) = *v20;
      v14 = ATL::CComSafeArray<float,4>::SetAt(&psa, i, &v33);
      if ( v14 < 0 )
      {
        v15 = 862;
        goto LABEL_24;
      }
      v17 = v19;
    }
    v10 = -2147024362;
    v21 = 855;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
      (const char *)v10,
      (int)psa);
    v22 = psa;
    if ( psa && SafeArrayUnlock(psa) >= 0 )
      SafeArrayDestroy(v22);
    return v10;
  }
  v15 = 850;
LABEL_24:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
    (const char *)(unsigned int)v14,
    (int)psa);
  v16 = psa;
  if ( psa && SafeArrayUnlock(psa) >= 0 )
    SafeArrayDestroy(v16);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800628c8  push    rbp
0x1800628ca  push    rbx
0x1800628cb  push    rsi
0x1800628cc  push    rdi
0x1800628cd  push    r12
0x1800628cf  push    r13
0x1800628d1  push    r14
0x1800628d3  push    r15
0x1800628d5  mov     rbp, rsp
0x1800628d8  sub     rsp, 38h
0x1800628dc  mov     rdi, r9
0x1800628df  mov     r9, r8
0x1800628e2  mov     rsi, rdx
0x1800628e5  test    rdx, rdx
0x1800628e8  jnz     short loc_18006290E
0x1800628ea  mov     ebx, 80004003h
0x1800628ef  mov     edx, 323h; void *
0x1800628f4  mov     rcx, [rbp+40h]; this
0x1800628f8  mov     r9d, ebx; char *
0x1800628fb  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180062902  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062907  mov     eax, ebx
0x180062909  jmp     loc_180062D0A
0x18006290e  test    r9, r9
0x180062911  jnz     short loc_180062937
0x180062913  mov     edx, 324h; void *
0x180062918  mov     edi, 80070057h
0x18006291d  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180062924  mov     r9d, edi; char *
0x180062927  mov     rcx, [rbp+40h]; this
0x18006292b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062930  mov     eax, edi
0x180062932  jmp     loc_180062D0A
0x180062937  xorps   xmm0, xmm0
0x18006293a  xor     eax, eax
0x18006293c  movups  xmmword ptr [rdi], xmm0
0x18006293f  mov     [rdi+10h], rax
0x180062943  cmp     ecx, 4
0x180062946  jnz     short loc_180062957
0x180062948  mov     word ptr [rdi], 13h
0x18006294d  mov     eax, [rdx]
0x18006294f  mov     [rdi+8], eax
0x180062952  jmp     loc_180062D08
0x180062957  cmp     ecx, 1
0x18006295a  jnz     short loc_180062982
0x18006295c  lea     r9, [rdi+8]
0x180062960  mov     r8, rsi
0x180062963  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180062968  mov     ebx, eax
0x18006296a  test    eax, eax
0x18006296c  jns     short loc_180062978
0x18006296e  mov     edx, 331h
0x180062973  jmp     loc_1800628F4
0x180062978  mov     word ptr [rdi], 1Fh
0x18006297d  jmp     loc_180062D08
0x180062982  movzx   ebx, word ptr [rdx]
0x180062985  bt      bx, 0Ch
0x18006298a  jnb     short loc_1800629EA
0x18006298c  mov     eax, 0EFFFh
0x180062991  and     bx, ax
0x180062994  sub     bx, 8
0x180062998  cmp     bx, 39h ; '9'
0x18006299c  ja      short loc_1800629B8
0x18006299e  mov     rcx, 200000000C00001h
0x1800629a8  bt      rcx, rbx
0x1800629ac  jnb     short loc_1800629B8
0x1800629ae  mov     edx, 340h
0x1800629b3  jmp     loc_180062918
0x1800629b8  mov     eax, [rdx+4]
0x1800629bb  mov     [rdi+8], eax
0x1800629be  lea     r8, [rdi+10h]; unsigned __int8 **
0x1800629c2  lea     rdx, [r9-8]; Size
0x1800629c6  lea     rcx, [rsi+8]; Src
0x1800629ca  call    ?AllocCoMemCopy@@YAJPEAE_KPEAPEAE@Z; AllocCoMemCopy(uchar *,unsigned __int64,uchar * *)
0x1800629cf  mov     ebx, eax
0x1800629d1  test    eax, eax
0x1800629d3  jns     short loc_1800629DF
0x1800629d5  mov     edx, 347h
0x1800629da  jmp     loc_1800628F4
0x1800629df  movzx   eax, word ptr [rsi]
0x1800629e2  mov     [rdi], ax
0x1800629e5  jmp     loc_180062D08
0x1800629ea  movzx   eax, bx
0x1800629ed  mov     ecx, 2004h
0x1800629f2  and     ax, cx
0x1800629f5  cmp     ax, cx
0x1800629f8  jnz     loc_180062B58
0x1800629fe  lea     rax, [r8-18h]
0x180062a02  mov     [rbp+var_10], rax
0x180062a06  mov     r15, rax
0x180062a09  shr     r15, 2
0x180062a0d  mov     [rbp+psa], 0
0x180062a15  mov     edx, r15d
0x180062a18  lea     rcx, [rbp+psa]
0x180062a1c  call    ?Create@?$CComSafeArray@M$03@ATL@@QEAAJKJ@Z; ATL::CComSafeArray<float,4>::Create(ulong,long)
0x180062a21  mov     r14d, eax
0x180062a24  test    eax, eax
0x180062a26  jns     short loc_180062A68
0x180062a28  mov     edx, 352h; void *
0x180062a2d  mov     rcx, [rbp+40h]; this
0x180062a31  mov     r9d, r14d; char *
0x180062a34  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180062a3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062a40  nop
0x180062a41  mov     rbx, [rbp+psa]
0x180062a45  test    rbx, rbx
0x180062a48  jz      short loc_180062A60
0x180062a4a  mov     rcx, rbx; psa
0x180062a4d  call    cs:__imp_SafeArrayUnlock
0x180062a53  test    eax, eax
0x180062a55  js      short loc_180062A60
0x180062a57  mov     rcx, rbx; psa
0x180062a5a  call    cs:__imp_SafeArrayDestroy
0x180062a60  mov     eax, r14d
0x180062a63  jmp     loc_180062D0A
0x180062a68  lea     r10, [rsi+18h]
0x180062a6c  xor     ebx, ebx
0x180062a6e  mov     eax, ebx
0x180062a70  cmp     rax, r15
0x180062a73  jnb     loc_180062B3C
0x180062a79  mov     [rbp+arg_8], 0
0x180062a81  lea     r12, [r10+4]
0x180062a85  cmp     r12, r10
0x180062a88  jb      short loc_180062AF2
0x180062a8a  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x180062a8e  lea     rdx, [rsi+18h]; unsigned __int64
0x180062a92  mov     rcx, r12; unsigned __int64
0x180062a95  call    ?ULongLongSub@@YAJ_K0PEA_K@Z; ULongLongSub(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180062a9a  mov     r14d, eax
0x180062a9d  test    eax, eax
0x180062a9f  js      short loc_180062AE8
0x180062aa1  mov     rax, [rbp+var_10]
0x180062aa5  cmp     [rbp+arg_8], rax
0x180062aa9  ja      short loc_180062ADC
0x180062aab  movss   xmm0, dword ptr [r10]
0x180062ab0  movss   dword ptr [rbp+arg_8], xmm0
0x180062ab5  lea     r8, [rbp+arg_8]
0x180062ab9  mov     edx, ebx
0x180062abb  lea     rcx, [rbp+psa]
0x180062abf  call    ?SetAt@?$CComSafeArray@M$03@ATL@@QEAAJJAEBMH@Z; ATL::CComSafeArray<float,4>::SetAt(long,float const &,int)
0x180062ac4  mov     r14d, eax
0x180062ac7  test    eax, eax
0x180062ac9  js      short loc_180062AD2
0x180062acb  mov     r10, r12
0x180062ace  inc     ebx
0x180062ad0  jmp     short loc_180062A6E
0x180062ad2  mov     edx, 35Eh
0x180062ad7  jmp     loc_180062A2D
0x180062adc  mov     edi, 80070057h
0x180062ae1  mov     edx, 35Bh
0x180062ae6  jmp     short loc_180062AFC
0x180062ae8  mov     edx, 359h
0x180062aed  jmp     loc_180062A2D
0x180062af2  mov     edi, 80070216h
0x180062af7  mov     edx, 357h; void *
0x180062afc  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180062b03  mov     r9d, edi; char *
0x180062b06  mov     rcx, [rbp+40h]; this
0x180062b0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062b0f  nop
0x180062b10  mov     rbx, [rbp+psa]
0x180062b14  test    rbx, rbx
0x180062b17  jz      loc_180062930
0x180062b1d  mov     rcx, rbx; psa
0x180062b20  call    cs:__imp_SafeArrayUnlock
0x180062b26  test    eax, eax
0x180062b28  js      loc_180062930
0x180062b2e  mov     rcx, rbx; psa
0x180062b31  call    cs:__imp_SafeArrayDestroy
0x180062b37  jmp     loc_180062930
0x180062b3c  mov     rbx, [rbp+psa]
0x180062b40  mov     rcx, rbx; psa
0x180062b43  call    cs:__imp_SafeArrayUnlock
0x180062b49  mov     [rdi+8], rbx
0x180062b4d  movzx   eax, word ptr [rsi]
0x180062b50  mov     [rdi], ax
0x180062b53  jmp     loc_180062D08
0x180062b58  mov     ecx, ebx
0x180062b5a  cmp     ebx, 1Eh
0x180062b5d  ja      loc_180062C60
0x180062b63  jz      loc_180062C32
0x180062b69  cmp     ebx, 9
0x180062b6c  ja      short loc_180062BE8
0x180062b6e  jz      loc_180062C23
0x180062b74  sub     ecx, 2
0x180062b77  jz      loc_180062CE4
0x180062b7d  sub     ecx, 1
0x180062b80  jz      loc_180062CE4
0x180062b86  sub     ecx, 1
0x180062b89  jz      loc_180062CE4
0x180062b8f  sub     ecx, 1
0x180062b92  jz      loc_180062CE4
0x180062b98  sub     ecx, 1
0x180062b9b  jz      loc_180062CE4
0x180062ba1  sub     ecx, 1
0x180062ba4  jz      loc_180062CE4
0x180062baa  cmp     ecx, 1
0x180062bad  jnz     short loc_180062C23
0x180062baf  lea     rcx, [rdx+8]; psz
0x180062bb3  test    rcx, rcx
0x180062bb6  jnz     short loc_180062BC2
0x180062bb8  mov     edx, 38Bh
0x180062bbd  jmp     loc_180062918
0x180062bc2  lea     edx, [r8-0Ah]; len
0x180062bc6  call    cs:__imp_SysAllocStringByteLen
0x180062bcc  mov     [rdi+8], rax
0x180062bd0  test    rax, rax
0x180062bd3  jnz     loc_180062D05
0x180062bd9  mov     ebx, 8007000Eh
0x180062bde  mov     edx, 390h
0x180062be3  jmp     loc_1800628F4
0x180062be8  sub     ecx, 0Ah
0x180062beb  jz      loc_180062CE4
0x180062bf1  sub     ecx, 1
0x180062bf4  jz      loc_180062CE4
0x180062bfa  sub     ecx, 2
0x180062bfd  jz      short loc_180062C23
0x180062bff  sub     ecx, 4
0x180062c02  jz      loc_180062CE4
0x180062c08  sub     ecx, 1
0x180062c0b  jz      loc_180062CE4
0x180062c11  sub     ecx, 2
0x180062c14  jz      loc_180062CE4
0x180062c1a  cmp     ecx, 1
0x180062c1d  jz      loc_180062CE4
0x180062c23  mov     ebx, 8007065Eh
0x180062c28  mov     edx, 3ADh
0x180062c2d  jmp     loc_1800628F4
0x180062c32  lea     rcx, [rdx+8]; Src
0x180062c36  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180062c3a  inc     rdx
0x180062c3d  cmp     byte ptr [rcx+rdx], 0
0x180062c41  jnz     short loc_180062C3A
0x180062c43  lea     r8, [rdi+8]; unsigned __int8 **
0x180062c47  inc     rdx; Size
0x180062c4a  call    ?AllocCoMemCopy@@YAJPEAE_KPEAPEAE@Z; AllocCoMemCopy(uchar *,unsigned __int64,uchar * *)
0x180062c4f  mov     esi, eax
0x180062c51  test    eax, eax
0x180062c53  jns     loc_180062D05
0x180062c59  mov     edx, 397h
0x180062c5e  jmp     short loc_180062CAA
0x180062c60  sub     ecx, 40h ; '@'
0x180062c63  jz      short loc_180062CE4
0x180062c65  sub     ecx, 1
0x180062c68  jz      short loc_180062CC1
0x180062c6a  sub     ecx, 1
0x180062c6d  jz      short loc_180062C23
0x180062c6f  sub     ecx, 1
0x180062c72  jz      short loc_180062C23
0x180062c74  sub     ecx, 1
0x180062c77  jz      short loc_180062C23
0x180062c79  sub     ecx, 1
0x180062c7c  jz      short loc_180062C23
0x180062c7e  sub     ecx, 1
0x180062c81  jz      short loc_180062C23
0x180062c83  sub     ecx, 1
0x180062c86  jz      short loc_180062C23
0x180062c88  cmp     ecx, 1
0x180062c8b  jnz     short loc_180062C23
0x180062c8d  lea     r8, [rdi+8]; unsigned __int8 **
0x180062c91  lea     rcx, [rdx+8]; Src
0x180062c95  mov     edx, 10h; Size
0x180062c9a  call    ?AllocCoMemCopy@@YAJPEAE_KPEAPEAE@Z; AllocCoMemCopy(uchar *,unsigned __int64,uchar * *)
0x180062c9f  mov     esi, eax
0x180062ca1  test    eax, eax
0x180062ca3  jns     short loc_180062D05
0x180062ca5  mov     edx, 385h; void *
0x180062caa  mov     rcx, [rbp+40h]; this
0x180062cae  mov     r9d, esi; char *
0x180062cb1  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180062cb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062cbd  mov     eax, esi
0x180062cbf  jmp     short loc_180062D0A
0x180062cc1  lea     eax, [r8-8]
0x180062cc5  mov     [rdi+8], eax
0x180062cc8  lea     r8, [rdi+10h]; unsigned __int8 **
0x180062ccc  mov     edx, eax; Size
0x180062cce  lea     rcx, [rsi+8]; Src
0x180062cd2  call    ?AllocCoMemCopy@@YAJPEAE_KPEAPEAE@Z; AllocCoMemCopy(uchar *,unsigned __int64,uchar * *)
0x180062cd7  mov     esi, eax
0x180062cd9  test    eax, eax
0x180062cdb  jns     short loc_180062D05
0x180062cdd  mov     edx, 39Eh
0x180062ce2  jmp     short loc_180062CAA
0x180062ce4  add     r8, 0FFFFFFFFFFFFFFF8h; Size
0x180062ce8  cmp     r8, 10h
0x180062cec  jbe     short loc_180062CF8
0x180062cee  mov     edx, 37Bh
0x180062cf3  jmp     loc_180062918
0x180062cf8  add     rdx, 8; Src
0x180062cfc  lea     rcx, [rdi+8]; void *
0x180062d00  call    memcpy_0
0x180062d05  mov     [rdi], bx
0x180062d08  xor     eax, eax
0x180062d0a  add     rsp, 38h
0x180062d0e  pop     r15
0x180062d10  pop     r14
0x180062d12  pop     r13
0x180062d14  pop     r12
0x180062d16  pop     rdi
  ... truncated ...
```
