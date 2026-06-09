# PackageRepository::RepositoryPropertyBag::Add(void *,__int64,ushort const *,ushort const *,ushort const *)

- ea: `0x180014920`
- end: `0x180014fcd`
- name: `?Add@RepositoryPropertyBag@PackageRepository@@QEAAJPEAX_JPEBG22@Z`
- size: `1709`
- prototype: `int(PackageRepository::RepositoryPropertyBag *__hidden this, void *, __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d6c90`
- `0x1800d6d20`
- `0x1800d6db0`
- `0x1800d6e40`
- `0x1800d6ed0`

## callees

- `0x180012fc8`
- `0x180014920`
- `0x180015590`
- `0x1800198d4`
- `0x180019940`
- `0x18001adb4`
- `0x1800207a0`
- `0x180040230`
- `0x18005145c`
- `0x180068f18`
- `0x18007cdc0`
- `0x1800807b4`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800af1fc`
- `0x1800af918`
- `0x1800ba45d`

## import_xrefs

- `AppxDeploymentServer!PackageRepositoryAllocate` at `0x180014ac4`
- `AppxDeploymentServer!PackageRepositoryAllocate` at `0x180014ac4`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180014e51`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180014e51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e8c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014a9d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014d13`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014a9d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014d13`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800149b1`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800149b1`
- `ntdll!RtlFreeUnicodeString` at `0x180014a19`
- `ntdll!RtlFreeUnicodeString` at `0x180014a19`

## string_xrefs

- `0x180014ecb`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x180014c73`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180014caf`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180014cc5`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180014f49`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180014f8a`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180014fa5`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall PackageRepository::RepositoryPropertyBag::Add(
        PackageRepository::RepositoryPropertyBag *this,
        void *a2,
        int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  unsigned int v9; // edi
  NTSTATUS v10; // eax
  __int64 v11; // r15
  PWSTR Buffer; // rdx
  _WORD *v13; // rbx
  unsigned int v14; // ecx
  unsigned int v15; // edi
  int v16; // eax
  const struct std::nothrow_t *v17; // rdx
  __int64 v18; // rcx
  unsigned __int64 i; // rbx
  LPCWCH *v20; // rdi
  int v21; // eax
  const unsigned __int16 **v22; // rax
  const unsigned __int16 **v23; // rbx
  unsigned int v24; // ebx
  const struct std::nothrow_t *v26; // rdx
  unsigned int v27; // eax
  unsigned __int64 v28; // rcx
  _WORD *v29; // xmm6_8
  unsigned __int64 v30; // rax
  _WORD *v31; // rax
  _WORD *v32; // rdi
  __int64 v33; // rdx
  __int64 v34; // rdi
  __int64 v35; // rcx
  const unsigned __int16 *v36; // r15
  int v37; // eax
  __int64 v38; // rcx
  int v39; // eax
  int v40; // eax
  __int64 v41; // rdx
  int v42; // eax
  signed int LastError; // eax
  signed int v44; // ecx
  _WORD *v45; // xmm6_8
  const struct std::nothrow_t *v46; // rdx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasec; // [rsp+20h] [rbp-E0h]
  int bIgnoreCased; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasee; // [rsp+20h] [rbp-E0h]
  char *v53; // [rsp+28h] [rbp-D8h]
  unsigned int v54; // [rsp+40h] [rbp-C0h]
  unsigned int v55; // [rsp+40h] [rbp-C0h]
  void *v56[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v57; // [rsp+58h] [rbp-A8h]
  char *v58; // [rsp+60h] [rbp-A0h]
  unsigned int v59; // [rsp+68h] [rbp-98h]
  PWSTR v60; // [rsp+70h] [rbp-90h]
  LPCWCH lpString2; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING UnicodeString; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v63; // [rsp+90h] [rbp-70h]
  WCHAR String2[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v63 = a5;
  lpString2 = a6;
  memset_0(String2, 0, 0x208u);
  v9 = 0;
  v57 = 0;
  *(_OWORD *)v56 = 0;
  if ( !a2 )
  {
    v13 = v56[1];
    v15 = -2147024809;
    goto LABEL_29;
  }
  UnicodeString = 0;
  v10 = RtlConvertSidToUnicodeString(&UnicodeString, a2, 1u);
  if ( v10 >= 0 )
  {
    v11 = UnicodeString.Length >> 1;
    Buffer = UnicodeString.Buffer;
    v60 = UnicodeString.Buffer;
    if ( !(UnicodeString.Length >> 1) )
    {
      v13 = v56[1];
LABEL_5:
      v14 = 0;
      if ( v9 )
        v14 = v9 - 1;
      if ( (unsigned int)v11 <= v14 )
        goto LABEL_8;
      v42 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)v56, v11);
      v15 = v42;
      if ( v42 >= 0 )
      {
        v13 = v56[1];
        Buffer = v60;
LABEL_8:
        if ( (_DWORD)v11 )
          v13[v11] = 0;
        memcpy_0(v13, Buffer, (unsigned int)(2 * v11));
        v15 = 0;
        goto LABEL_11;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x20C,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v42,
        bIgnoreCase);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x235,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)v15,
        bIgnoreCasee);
      v13 = v56[1];
LABEL_11:
      RtlFreeUnicodeString(&UnicodeString);
      goto LABEL_12;
    }
    if ( (unsigned int)v11 > 0x20 )
    {
      v27 = UnicodeString.Length >> 1;
    }
    else
    {
      v27 = 8;
      v54 = 8;
      if ( (unsigned int)v11 <= 8 )
        goto LABEL_39;
      do
        v27 *= 2;
      while ( v27 < (unsigned int)v11 );
    }
    v54 = v27;
LABEL_39:
    if ( v27 > 0x3FFFFFFF )
    {
      v13 = v56[1];
      v15 = -2147023613;
      v33 = 425;
    }
    else
    {
      if ( !v27 )
      {
        v45 = (_WORD *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        v13 = v45;
        if ( v45 )
        {
          operator delete(v45, (const struct std::nothrow_t *)UnicodeString.Buffer);
          Buffer = v60;
          v13 = 0;
          v56[1] = 0;
          LODWORD(v56[0]) = 0;
        }
        v57 = 0;
        goto LABEL_5;
      }
      v28 = v27 + 1;
      v59 = v27 + 1;
      v29 = (_WORD *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      v30 = 2 * v28;
      v13 = v29;
      v58 = (char *)v28;
      if ( !is_mul_ok(v28, 2u) )
        v30 = -1;
      v31 = operator new[](v30, (const struct std::nothrow_t *)&std::nothrow);
      v32 = v31;
      if ( v31 )
      {
        LODWORD(v58) = memcpy_s(v31, 2LL * (_QWORD)v58, v29, 0);
        if ( !(_DWORD)v58 )
        {
          operator delete(v29, v46);
          v13 = v32;
          v9 = v59;
          Buffer = v60;
          v57 = v59;
          v56[1] = v13;
          if ( LODWORD(v56[0]) > v54 )
          {
            LODWORD(v56[0]) = v54;
            v13[v54] = 0;
          }
          else if ( LODWORD(v56[0]) < v54 && !LODWORD(v56[0]) )
          {
            *v13 = 0;
          }
          goto LABEL_5;
        }
        operator delete(v32, v46);
        v15 = -2147024809;
        LODWORD(v53) = (_DWORD)v58;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x198,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)0x80070057LL,
          (int)"0x%08lx",
          v53);
      }
      else
      {
        v15 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x193,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)0x8007000ELL,
          bIgnoreCase);
      }
      v33 = 452;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)v15,
      bIgnoreCase);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)v15,
      bIgnoreCased);
    goto LABEL_11;
  }
  v13 = v56[1];
  v15 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x1E,
          (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
          (const char *)(unsigned int)v10,
          bIgnoreCase);
LABEL_12:
  if ( (v15 & 0x80000000) == 0 )
  {
    bIgnoreCasea = a3;
    v16 = StringCchPrintfW(String2, 0x104u, L"%s %I64d %s %s", v13);
    v15 = v16;
    if ( v16 >= 0 )
    {
      if ( v13 )
        operator delete(v13, v17);
      for ( i = 0; ; ++i )
      {
        while ( 1 )
        {
          if ( i >= *((_QWORD *)this + 2) )
            goto LABEL_23;
          v20 = *(LPCWCH **)(*(_QWORD *)this + 8 * i);
          if ( !v20 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v18);
          v21 = CompareStringOrdinal(*v20, -1, String2, -1, 0);
          if ( v21 )
            break;
          MicrosoftTelemetryAssertTriggeredNoArgs(v18);
          ++i;
        }
        if ( v21 == 2 )
          break;
      }
      if ( i != 0x40000000 )
      {
        v34 = 8 * i;
        if ( i < *((_QWORD *)this + 2) )
        {
          _mm_lfence();
          v35 = *(_QWORD *)(v34 + *(_QWORD *)this);
        }
        else
        {
          v35 = 0;
        }
        v36 = lpString2;
        v37 = CompareStringOrdinal(*(LPCWCH *)(v35 + 8), -1, lpString2, -1, 0);
        if ( v37 )
        {
          if ( v37 != 2 )
          {
            v38 = i < *((_QWORD *)this + 2) ? *(_QWORD *)(v34 + *(_QWORD *)this) : 0LL;
            v39 = PackageRepository::PropertyBagKeyValuePair::Set((const unsigned __int16 **)(v38 + 8), v36);
            v55 = v39;
            if ( v39 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x9A,
                (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
                (const char *)(unsigned int)v39,
                bIgnoreCaseb);
LABEL_69:
              v24 = v55;
              goto LABEL_25;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v55 = LastError;
          v44 = LastError;
          if ( LastError > 0 )
          {
            v44 = (unsigned __int16)LastError | 0x80070000;
            v55 = v44;
          }
          if ( v44 < 0 )
            goto LABEL_69;
        }
        return 0;
      }
LABEL_23:
      v22 = (const unsigned __int16 **)PackageRepositoryAllocate(0x10u);
      v23 = v22;
      if ( !v22 )
      {
        v24 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x89,
          (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
          (const char *)0x8007000ELL,
          bIgnoreCasea);
LABEL_25:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xA8,
          (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
          (const char *)v24,
          bIgnoreCaseb);
        return v24;
      }
      *v22 = 0;
      v22[1] = 0;
      v40 = PackageRepository::PropertyBagKeyValuePair::Set(v22, String2);
      v55 = v40;
      if ( v40 < 0 )
      {
        v41 = 139;
      }
      else
      {
        v40 = PackageRepository::PropertyBagKeyValuePair::Set(v23 + 1, lpString2);
        v55 = v40;
        if ( v40 < 0 )
        {
          v41 = 140;
        }
        else
        {
          v40 = Common::Array<PackageRepository::PropertyBagKeyValuePair,Common::ContainerOperations<PackageRepository::PropertyBagKeyValuePair,PackageRepository::PropertyBagKeyValuePair>,unsigned short,Common::ContainerOperations<unsigned short,PackageRepository::PropertyBagKeyValuePair>,Common::ArrayOperations<PackageRepository::PropertyBagKeyValuePair,PackageRepository::PropertyBagKeyValuePair>>::Add(
                  this,
                  v23);
          v55 = v40;
          if ( v40 >= 0 )
            return 0;
          v41 = 142;
        }
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v41,
        (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
        (const char *)(unsigned int)v40,
        bIgnoreCasea);
      PackageRepository::PropertyBagKeyValuePair::~PropertyBagKeyValuePair((PackageRepository::PropertyBagKeyValuePair *)v23);
      PackageRepositoryFree(v23);
      goto LABEL_69;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
      (const char *)(unsigned int)v16,
      a3);
    if ( v13 )
      goto LABEL_30;
    goto LABEL_31;
  }
LABEL_29:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xD0,
    (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
    (const char *)v15,
    bIgnoreCase);
  if ( v13 )
LABEL_30:
    operator delete(v13, v26);
LABEL_31:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xA6,
    (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
    (const char *)v15,
    bIgnoreCasec);
  return v15;
}

```

## disassembly

```asm
0x180014920  push    rbp
0x180014922  push    rbx
0x180014923  push    rsi
0x180014924  push    rdi
0x180014925  push    r12
0x180014927  push    r13
0x180014929  push    r14
0x18001492b  push    r15
0x18001492d  lea     rbp, [rsp-1D8h]
0x180014935  sub     rsp, 2D8h
0x18001493c  movaps  [rsp+310h+var_50], xmm6
0x180014944  mov     rax, cs:__security_cookie
0x18001494b  xor     rax, rsp
0x18001494e  mov     [rbp+210h+var_60], rax
0x180014955  mov     rax, [rbp+210h+arg_28]
0x18001495c  mov     r12, r8
0x18001495f  mov     r15, [rbp+210h+arg_20]
0x180014966  mov     rbx, rdx
0x180014969  mov     rsi, rcx
0x18001496c  mov     [rbp+210h+var_280], r15
0x180014970  xor     edx, edx; Val
0x180014972  mov     [rsp+310h+lpString2], rax
0x180014977  mov     r8d, 208h; Size
0x18001497d  lea     rcx, [rbp+210h+String2]; void *
0x180014981  mov     r13, r9
0x180014984  call    memset_0
0x180014989  xor     edi, edi
0x18001498b  xorps   xmm6, xmm6
0x18001498e  mov     [rsp+310h+var_2B8], edi
0x180014992  movups  xmmword ptr [rsp+310h+var_2C8], xmm6
0x180014997  test    rbx, rbx
0x18001499a  jz      loc_180014B51
0x1800149a0  xorps   xmm0, xmm0
0x1800149a3  lea     rcx, [rbp+210h+UnicodeString]; UnicodeString
0x1800149a7  mov     r8b, 1; AllocateDestinationString
0x1800149aa  mov     rdx, rbx; Sid
0x1800149ad  movups  xmmword ptr [rbp+210h+UnicodeString.Length], xmm0
0x1800149b1  call    cs:__imp_RtlConvertSidToUnicodeString
0x1800149b8  nop     dword ptr [rax+rax+00h]
0x1800149bd  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800149c4  test    eax, eax
0x1800149c6  js      loc_180014EC4
0x1800149cc  movzx   r15d, [rbp+210h+UnicodeString.Length]
0x1800149d1  shr     r15d, 1
0x1800149d4  mov     rdx, [rbp+210h+UnicodeString.Buffer]; struct std::nothrow_t *
0x1800149d8  mov     [rsp+310h+var_2A0], rdx
0x1800149dd  jnz     loc_180014BF5
0x1800149e3  mov     rbx, [rsp+310h+var_2C8+8]
0x1800149e8  xor     ecx, ecx
0x1800149ea  lea     eax, [rdi-1]
0x1800149ed  test    edi, edi
0x1800149ef  cmovnz  ecx, eax
0x1800149f2  cmp     r15d, ecx
0x1800149f5  ja      loc_180014E66
0x1800149fb  test    r15d, r15d
0x1800149fe  jz      short loc_180014A07
0x180014a00  xor     eax, eax
0x180014a02  mov     [rbx+r15*2], ax
0x180014a07  lea     r8d, [r15+r15]; Size
0x180014a0b  mov     rcx, rbx; void *
0x180014a0e  call    memcpy_0
0x180014a13  xor     edi, edi
0x180014a15  lea     rcx, [rbp+210h+UnicodeString]; UnicodeString
0x180014a19  call    cs:__imp_RtlFreeUnicodeString
0x180014a20  nop     dword ptr [rax+rax+00h]
0x180014a25  mov     r15, [rbp+210h+var_280]
0x180014a29  test    edi, edi
0x180014a2b  js      loc_180014B62
0x180014a31  mov     [rsp+310h+var_2E0], r15
0x180014a36  lea     r8, aSI64dSS; "%s %I64d %s %s"
0x180014a3d  mov     [rsp+310h+var_2E8], r13
0x180014a42  lea     rcx, [rbp+210h+String2]; unsigned __int16 *
0x180014a46  mov     r9, rbx
0x180014a49  mov     qword ptr [rsp+310h+bIgnoreCase], r12; int
0x180014a4e  mov     edx, 104h; unsigned __int64
0x180014a53  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014a58  mov     edi, eax
0x180014a5a  test    eax, eax
0x180014a5c  js      loc_180014BB4
0x180014a62  test    rbx, rbx
0x180014a65  jz      short loc_180014A6F
0x180014a67  mov     rcx, rbx; void *
0x180014a6a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014a6f  xor     r12d, r12d
0x180014a72  mov     ebx, r12d
0x180014a75  cmp     rbx, [rsi+10h]
0x180014a79  jnb     short loc_180014ABF
0x180014a7b  mov     rax, [rsi]
0x180014a7e  mov     rdi, [rax+rbx*8]
0x180014a82  test    rdi, rdi
0x180014a85  jz      loc_180014BDE
0x180014a8b  mov     rcx, [rdi]; lpString1
0x180014a8e  lea     r8, [rbp+210h+String2]; lpString2
0x180014a92  mov     r9d, r14d; cchCount2
0x180014a95  mov     [rsp+310h+bIgnoreCase], r12d; bIgnoreCase
0x180014a9a  mov     edx, r14d; cchCount1
0x180014a9d  call    cs:__imp_CompareStringOrdinal
0x180014aa4  nop     dword ptr [rax+rax+00h]
0x180014aa9  test    eax, eax
0x180014aab  jz      loc_180014BE8
0x180014ab1  cmp     eax, 2
0x180014ab4  jz      loc_180014CDE
0x180014aba  inc     rbx
0x180014abd  jmp     short loc_180014A75
0x180014abf  mov     ecx, 10h
0x180014ac4  call    cs:__imp_?PackageRepositoryAllocate@@YAPEAX_K@Z; PackageRepositoryAllocate(unsigned __int64)
0x180014acb  nop     dword ptr [rax+rax+00h]
0x180014ad0  mov     rbx, rax
0x180014ad3  test    rax, rax
0x180014ad6  jnz     loc_180014DD8
0x180014adc  mov     rcx, [rbp+218h]; this
0x180014ae3  lea     r8, aOnecoreAdminAp_59; "onecore\\admin\\appmodel\\packagereposi"...
0x180014aea  mov     ebx, 8007000Eh
0x180014aef  mov     edx, 89h; void *
0x180014af4  mov     r9d, ebx; char *
0x180014af7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014afc  mov     rcx, [rbp+218h]; this
0x180014b03  lea     r8, aOnecoreAdminAp_59; "onecore\\admin\\appmodel\\packagereposi"...
0x180014b0a  mov     r9d, ebx; char *
0x180014b0d  mov     edx, 0A8h; void *
0x180014b12  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014b17  mov     eax, ebx
0x180014b19  jmp     short loc_180014B25
0x180014b1b  test    ecx, ecx
0x180014b1d  js      loc_180014E5D
0x180014b23  xor     eax, eax
0x180014b25  mov     rcx, [rbp+210h+var_60]
0x180014b2c  xor     rcx, rsp; StackCookie
0x180014b2f  call    __security_check_cookie
0x180014b34  movaps  xmm6, [rsp+310h+var_50]
0x180014b3c  add     rsp, 2D8h
0x180014b43  pop     r15
0x180014b45  pop     r14
0x180014b47  pop     r13
0x180014b49  pop     r12
0x180014b4b  pop     rdi
0x180014b4c  pop     rsi
0x180014b4d  pop     rbx
0x180014b4e  pop     rbp
0x180014b4f  retn
0x180014b51  mov     rbx, [rsp+310h+var_2C8+8]
0x180014b56  mov     edi, 80070057h
0x180014b5b  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180014b62  mov     rcx, [rbp+218h]; this
0x180014b69  lea     r8, aOnecoreAdminAp_59; "onecore\\admin\\appmodel\\packagereposi"...
0x180014b70  mov     r9d, edi; char *
0x180014b73  mov     edx, 0D0h; void *
0x180014b78  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014b7d  test    rbx, rbx
0x180014b80  jz      short loc_180014B8A
0x180014b82  mov     rcx, rbx; void *
0x180014b85  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014b8a  test    edi, edi
0x180014b8c  jns     loc_180014A6F
0x180014b92  mov     rcx, [rbp+218h]; this
0x180014b99  lea     r8, aOnecoreAdminAp_59; "onecore\\admin\\appmodel\\packagereposi"...
0x180014ba0  mov     r9d, edi; char *
0x180014ba3  mov     edx, 0A6h; void *
0x180014ba8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014bad  mov     eax, edi
0x180014baf  jmp     loc_180014B25
0x180014bb4  mov     rcx, [rbp+218h]; this
0x180014bbb  lea     r8, aOnecoreAdminAp_59; "onecore\\admin\\appmodel\\packagereposi"...
0x180014bc2  mov     r9d, eax; char *
0x180014bc5  mov     edx, 0D2h; void *
0x180014bca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014bcf  test    rbx, rbx
0x180014bd2  jz      short loc_180014B92
0x180014bd4  mov     rcx, rbx; void *
0x180014bd7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014bdc  jmp     short loc_180014B92
0x180014bde  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pair != nullptr")
0x180014be3  jmp     loc_180014A8B
0x180014be8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "compareResult != 0")
0x180014bed  inc     rbx
0x180014bf0  jmp     loc_180014A75
0x180014bf5  cmp     r15d, 20h ; ' '
0x180014bf9  ja      loc_180014C91
0x180014bff  mov     eax, 8
0x180014c04  mov     [rsp+310h+var_2D0], eax
0x180014c08  cmp     r15d, eax
0x180014c0b  jbe     short loc_180014C18
0x180014c0d  add     eax, eax
0x180014c0f  cmp     eax, r15d
0x180014c12  jb      short loc_180014C0D
0x180014c14  mov     [rsp+310h+var_2D0], eax
0x180014c18  cmp     eax, 3FFFFFFFh
0x180014c1d  ja      short loc_180014C99
0x180014c1f  test    eax, eax
0x180014c21  jz      loc_180014EEB
0x180014c27  lea     ecx, [rax+1]
0x180014c2a  mov     [rsp+310h+var_2A8], ecx
0x180014c2e  test    ecx, ecx
0x180014c30  jz      loc_1800149E3
0x180014c36  psrldq  xmm6, 8
0x180014c3b  mov     eax, 2
0x180014c40  mul     rcx
0x180014c43  movq    rbx, xmm6
0x180014c48  mov     [rsp+310h+var_2B0], rcx
0x180014c4d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014c54  cmovb   rax, r14
0x180014c58  mov     rcx, rax; unsigned __int64
0x180014c5b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180014c60  mov     rdi, rax
0x180014c63  test    rax, rax
0x180014c66  jnz     loc_180014F1B
0x180014c6c  mov     rcx, [rbp+218h]; this
0x180014c73  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x180014c7a  mov     edi, 8007000Eh
0x180014c7f  mov     edx, 193h; void *
0x180014c84  mov     r9d, edi; char *
0x180014c87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014c8c  jmp     loc_180014F79
0x180014c91  mov     eax, r15d
0x180014c94  jmp     loc_180014C14
0x180014c99  mov     rbx, [rsp+310h+var_2C8+8]
0x180014c9e  mov     edi, 80070503h
0x180014ca3  mov     edx, 1A9h; void *
0x180014ca8  mov     rcx, [rbp+218h]; this
0x180014caf  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x180014cb6  mov     r9d, edi; char *
0x180014cb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014cbe  mov     rcx, [rbp+218h]; this
0x180014cc5  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x180014ccc  mov     r9d, edi; char *
0x180014ccf  mov     edx, 232h; void *
0x180014cd4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014cd9  jmp     loc_180014A15
0x180014cde  cmp     rbx, 40000000h
0x180014ce5  jz      loc_180014ABF
0x180014ceb  lea     rdi, ds:0[rbx*8]
0x180014cf3  cmp     rbx, [rsi+10h]
0x180014cf7  jb      short loc_180014D75
0x180014cf9  mov     rcx, r12
0x180014cfc  mov     r15, [rsp+310h+lpString2]
0x180014d01  mov     r9d, r14d; cchCount2
0x180014d04  mov     rcx, [rcx+8]; lpString1
0x180014d08  mov     r8, r15; lpString2
0x180014d0b  mov     edx, r14d; cchCount1
0x180014d0e  mov     [rsp+310h+bIgnoreCase], r12d; int
0x180014d13  call    cs:__imp_CompareStringOrdinal
0x180014d1a  nop     dword ptr [rax+rax+00h]
0x180014d1f  test    eax, eax
0x180014d21  jz      loc_180014E8C
0x180014d27  cmp     eax, 2
0x180014d2a  jz      loc_180014B23
0x180014d30  cmp     rbx, [rsi+10h]
0x180014d34  jb      loc_180014EB8
0x180014d3a  mov     rcx, r12
0x180014d3d  add     rcx, 8; unsigned __int16 **
0x180014d41  mov     rdx, r15; unsigned __int16 *
0x180014d44  call    ?Set@PropertyBagKeyValuePair@PackageRepository@@CAJAEAPEBGPEBG@Z; PackageRepository::PropertyBagKeyValuePair::Set(ushort const * &,ushort const *)
0x180014d49  mov     [rsp+310h+var_2D0], eax
0x180014d4d  test    eax, eax
0x180014d4f  jns     loc_180014B23
0x180014d55  mov     rcx, [rbp+218h]; this
0x180014d5c  lea     r8, aOnecoreAdminAp_59; "onecore\\admin\\appmodel\\packagereposi"...
0x180014d63  mov     r9d, eax; char *
0x180014d66  mov     edx, 9Ah; void *
0x180014d6b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014d70  jmp     loc_180014E5D
0x180014d75  lfence
0x180014d78  mov     rax, [rsi]
0x180014d7b  mov     rcx, [rdi+rax]
0x180014d7f  jmp     loc_180014CFC
0x180014d84  mov     rcx, rbx; void *
0x180014d87  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014d8c  mov     ecx, [rsp+310h+var_2A8]
0x180014d90  mov     rbx, rdi
0x180014d93  mov     eax, [rsp+310h+var_2D0]
0x180014d97  mov     edi, ecx
0x180014d99  mov     rdx, [rsp+310h+var_2A0]
0x180014d9e  mov     [rsp+310h+var_2B8], ecx
0x180014da2  mov     ecx, dword ptr [rsp+310h+var_2C8]
0x180014da6  mov     [rsp+310h+var_2C8+8], rbx
0x180014dab  cmp     ecx, eax
0x180014dad  ja      short loc_180014DC7
0x180014daf  jnb     loc_1800149E8
0x180014db5  test    ecx, ecx
0x180014db7  jnz     loc_1800149E8
0x180014dbd  xor     eax, eax
0x180014dbf  mov     [rbx], ax
0x180014dc2  jmp     loc_1800149E8
0x180014dc7  mov     ecx, eax
0x180014dc9  mov     dword ptr [rsp+310h+var_2C8], eax
0x180014dcd  xor     eax, eax
0x180014dcf  mov     [rbx+rcx*2], ax
0x180014dd3  jmp     loc_1800149E8
0x180014dd8  lea     rdx, [rbp+210h+String2]; unsigned __int16 *
0x180014ddc  mov     [rax], r12
0x180014ddf  mov     rcx, rbx; unsigned __int16 **
0x180014de2  mov     [rax+8], r12
0x180014de6  call    ?Set@PropertyBagKeyValuePair@PackageRepository@@CAJAEAPEBGPEBG@Z; PackageRepository::PropertyBagKeyValuePair::Set(ushort const * &,ushort const *)
0x180014deb  mov     [rsp+310h+var_2D0], eax
0x180014def  test    eax, eax
0x180014df1  js      loc_180014FC3
0x180014df7  mov     rdx, [rsp+310h+lpString2]; unsigned __int16 *
0x180014dfc  lea     rcx, [rbx+8]; unsigned __int16 **
0x180014e00  call    ?Set@PropertyBagKeyValuePair@PackageRepository@@CAJAEAPEBGPEBG@Z; PackageRepository::PropertyBagKeyValuePair::Set(ushort const * &,ushort const *)
0x180014e05  mov     [rsp+310h+var_2D0], eax
  ... truncated ...
```
