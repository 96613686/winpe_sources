# PackageRepository::RepositoryPropertyBag::Get(void *,__int64,ushort const *,ushort const *,Common::StringBuffer &)

- ea: `0x180014fe0`
- end: `0x18001557c`
- name: `?Get@RepositoryPropertyBag@PackageRepository@@QEAAJPEAX_JPEBG2AEAVStringBuffer@Common@@@Z`
- size: `1436`
- prototype: `int(PackageRepository::RepositoryPropertyBag *__hidden this, void *, __int64, const unsigned __int16 *, const unsigned __int16 *, struct Common::StringBuffer *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007c960`

## callees

- `0x180012fc8`
- `0x180014fe0`
- `0x180015590`
- `0x180017ba0`
- `0x18001adb4`
- `0x18001f69c`
- `0x1800207a0`
- `0x180040230`
- `0x180068f18`
- `0x18007cdc0`
- `0x1800807b4`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800af1fc`
- `0x1800af918`
- `0x1800ba45d`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001515d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001515d`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180015071`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180015071`
- `ntdll!RtlFreeUnicodeString` at `0x1800150d9`
- `ntdll!RtlFreeUnicodeString` at `0x1800150d9`

## string_xrefs

- `0x180015447`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x1800152d2`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18001530e`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180015324`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800154c5`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180015506`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180015521`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180015546`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall PackageRepository::RepositoryPropertyBag::Get(
        PackageRepository::RepositoryPropertyBag *this,
        void *a2,
        int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        struct Common::StringBuffer *a6)
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
  const struct std::nothrow_t *v23; // rdx
  unsigned int v24; // eax
  unsigned __int64 v25; // rcx
  _WORD *v26; // xmm6_8
  unsigned __int64 v27; // rax
  _WORD *v28; // rax
  _WORD *v29; // rdi
  __int64 v30; // rdx
  __int64 v31; // rax
  const unsigned __int16 *v32; // rdx
  _WORD *v33; // rax
  __int64 v34; // rcx
  int v35; // ebx
  int v36; // eax
  _WORD *v37; // xmm6_8
  const struct std::nothrow_t *v38; // rdx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasec; // [rsp+20h] [rbp-E0h]
  int bIgnoreCased; // [rsp+20h] [rbp-E0h]
  char *v44; // [rsp+28h] [rbp-D8h]
  unsigned int v45; // [rsp+40h] [rbp-C0h]
  void *v46[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v47; // [rsp+58h] [rbp-A8h]
  char *v48; // [rsp+60h] [rbp-A0h]
  unsigned int v49; // [rsp+68h] [rbp-98h]
  PWSTR v50; // [rsp+70h] [rbp-90h]
  Common::StringBuffer *v51; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING UnicodeString; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v53; // [rsp+90h] [rbp-70h]
  WCHAR String2[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v53 = a5;
  v51 = a6;
  memset_0(String2, 0, 0x208u);
  v9 = 0;
  v47 = 0;
  *(_OWORD *)v46 = 0;
  if ( !a2 )
  {
    v13 = v46[1];
    v15 = -2147024809;
LABEL_25:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
      (const char *)v15,
      bIgnoreCase);
    if ( !v13 )
    {
LABEL_27:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB2,
        (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
        (const char *)v15,
        bIgnoreCaseb);
      return v15;
    }
LABEL_26:
    operator delete(v13, v23);
    goto LABEL_27;
  }
  UnicodeString = 0;
  v10 = RtlConvertSidToUnicodeString(&UnicodeString, a2, 1u);
  if ( v10 >= 0 )
  {
    v11 = UnicodeString.Length >> 1;
    Buffer = UnicodeString.Buffer;
    v50 = UnicodeString.Buffer;
    if ( !(UnicodeString.Length >> 1) )
    {
      v13 = v46[1];
LABEL_5:
      v14 = 0;
      if ( v9 )
        v14 = v9 - 1;
      if ( (unsigned int)v11 <= v14 )
        goto LABEL_8;
      v36 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)v46, v11);
      v15 = v36;
      if ( v36 >= 0 )
      {
        v13 = v46[1];
        Buffer = v50;
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
        (const char *)(unsigned int)v36,
        bIgnoreCase);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x235,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)v15,
        bIgnoreCased);
      v13 = v46[1];
LABEL_11:
      RtlFreeUnicodeString(&UnicodeString);
      goto LABEL_12;
    }
    if ( (unsigned int)v11 > 0x20 )
    {
      v24 = UnicodeString.Length >> 1;
    }
    else
    {
      v24 = 8;
      v45 = 8;
      if ( (unsigned int)v11 <= 8 )
        goto LABEL_35;
      do
        v24 *= 2;
      while ( v24 < (unsigned int)v11 );
    }
    v45 = v24;
LABEL_35:
    if ( v24 > 0x3FFFFFFF )
    {
      v13 = v46[1];
      v15 = -2147023613;
      v30 = 425;
    }
    else
    {
      if ( !v24 )
      {
        v37 = (_WORD *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        v13 = v37;
        if ( v37 )
        {
          operator delete(v37, (const struct std::nothrow_t *)UnicodeString.Buffer);
          Buffer = v50;
          v13 = 0;
          v46[1] = 0;
          LODWORD(v46[0]) = 0;
        }
        v47 = 0;
        goto LABEL_5;
      }
      v25 = v24 + 1;
      v49 = v24 + 1;
      v26 = (_WORD *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      v27 = 2 * v25;
      v13 = v26;
      v48 = (char *)v25;
      if ( !is_mul_ok(v25, 2u) )
        v27 = -1;
      v28 = operator new[](v27, (const struct std::nothrow_t *)&std::nothrow);
      v29 = v28;
      if ( v28 )
      {
        LODWORD(v48) = memcpy_s(v28, 2LL * (_QWORD)v48, v26, 0);
        if ( !(_DWORD)v48 )
        {
          operator delete(v26, v38);
          v13 = v29;
          v9 = v49;
          Buffer = v50;
          v47 = v49;
          v46[1] = v13;
          if ( LODWORD(v46[0]) > v45 )
          {
            LODWORD(v46[0]) = v45;
            v13[v45] = 0;
          }
          else if ( LODWORD(v46[0]) < v45 && !LODWORD(v46[0]) )
          {
            *v13 = 0;
          }
          goto LABEL_5;
        }
        operator delete(v29, v38);
        v15 = -2147024809;
        LODWORD(v44) = (_DWORD)v48;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x198,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)0x80070057LL,
          (int)"0x%08lx",
          v44);
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
      v30 = 452;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)v15,
      bIgnoreCase);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)v15,
      bIgnoreCasec);
    goto LABEL_11;
  }
  v13 = v46[1];
  v15 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x1E,
          (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
          (const char *)(unsigned int)v10,
          bIgnoreCase);
LABEL_12:
  if ( (v15 & 0x80000000) != 0 )
    goto LABEL_25;
  v16 = StringCchPrintfW(String2, 0x104u, L"%s %I64d %s %s", v13);
  v15 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
      (const char *)(unsigned int)v16,
      a3);
    if ( !v13 )
      goto LABEL_27;
    goto LABEL_26;
  }
  if ( v13 )
    operator delete(v13, v17);
  for ( i = 0; ; ++i )
  {
    while ( 1 )
    {
      if ( i >= *((_QWORD *)this + 2) )
        return 2147943568LL;
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
  if ( i == 0x40000000 )
    return 2147943568LL;
  if ( i >= *((_QWORD *)this + 2) )
  {
    v31 = 0;
  }
  else
  {
    _mm_lfence();
    v31 = *(_QWORD *)(*(_QWORD *)this + 8 * i);
  }
  v32 = *(const unsigned __int16 **)(v31 + 8);
  if ( v32 )
  {
    v33 = *(_WORD **)(v31 + 8);
    v34 = 1073741822;
    do
    {
      if ( !*v33 )
        break;
      ++v33;
      --v34;
    }
    while ( v34 );
    v35 = -2147024809;
    if ( v34 )
    {
      v35 = Common::StringBuffer::SetValue(v51, v32, 1073741822 - v34);
      if ( v35 >= 0 )
        return 0;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x249,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x80070057LL,
        bIgnoreCasea);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
      (const char *)(unsigned int)v35,
      bIgnoreCasea);
    return (unsigned int)v35;
  }
  else
  {
    Common::StringBuffer::Clear(v51);
    return 0;
  }
}

```

## disassembly

```asm
0x180014fe0  push    rbp
0x180014fe2  push    rbx
0x180014fe3  push    rsi
0x180014fe4  push    rdi
0x180014fe5  push    r12
0x180014fe7  push    r13
0x180014fe9  push    r14
0x180014feb  push    r15
0x180014fed  lea     rbp, [rsp-1D8h]
0x180014ff5  sub     rsp, 2D8h
0x180014ffc  movaps  [rsp+310h+var_50], xmm6
0x180015004  mov     rax, cs:__security_cookie
0x18001500b  xor     rax, rsp
0x18001500e  mov     [rbp+210h+var_60], rax
0x180015015  mov     rax, [rbp+210h+arg_28]
0x18001501c  mov     r12, r8
0x18001501f  mov     r15, [rbp+210h+arg_20]
0x180015026  mov     rbx, rdx
0x180015029  mov     rsi, rcx
0x18001502c  mov     [rbp+210h+var_280], r15
0x180015030  xor     edx, edx; Val
0x180015032  mov     [rsp+310h+var_298], rax
0x180015037  mov     r8d, 208h; Size
0x18001503d  lea     rcx, [rbp+210h+String2]; void *
0x180015041  mov     r13, r9
0x180015044  call    memset_0
0x180015049  xor     edi, edi
0x18001504b  xorps   xmm6, xmm6
0x18001504e  mov     [rsp+310h+var_2B8], edi
0x180015052  movups  xmmword ptr [rsp+310h+var_2C8], xmm6
0x180015057  test    rbx, rbx
0x18001505a  jz      loc_1800151B0
0x180015060  xorps   xmm0, xmm0
0x180015063  lea     rcx, [rbp+210h+UnicodeString]; UnicodeString
0x180015067  mov     r8b, 1; AllocateDestinationString
0x18001506a  mov     rdx, rbx; Sid
0x18001506d  movups  xmmword ptr [rbp+210h+UnicodeString.Length], xmm0
0x180015071  call    cs:__imp_RtlConvertSidToUnicodeString
0x180015078  nop     dword ptr [rax+rax+00h]
0x18001507d  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180015084  test    eax, eax
0x180015086  js      loc_180015440
0x18001508c  movzx   r15d, [rbp+210h+UnicodeString.Length]
0x180015091  shr     r15d, 1
0x180015094  mov     rdx, [rbp+210h+UnicodeString.Buffer]; struct std::nothrow_t *
0x180015098  mov     [rsp+310h+var_2A0], rdx
0x18001509d  jnz     loc_180015254
0x1800150a3  mov     rbx, [rsp+310h+var_2C8+8]
0x1800150a8  xor     ecx, ecx
0x1800150aa  lea     eax, [rdi-1]
0x1800150ad  test    edi, edi
0x1800150af  cmovnz  ecx, eax
0x1800150b2  cmp     r15d, ecx
0x1800150b5  ja      loc_18001541A
0x1800150bb  test    r15d, r15d
0x1800150be  jz      short loc_1800150C7
0x1800150c0  xor     eax, eax
0x1800150c2  mov     [rbx+r15*2], ax
0x1800150c7  lea     r8d, [r15+r15]; Size
0x1800150cb  mov     rcx, rbx; void *
0x1800150ce  call    memcpy_0
0x1800150d3  xor     edi, edi
0x1800150d5  lea     rcx, [rbp+210h+UnicodeString]; UnicodeString
0x1800150d9  call    cs:__imp_RtlFreeUnicodeString
0x1800150e0  nop     dword ptr [rax+rax+00h]
0x1800150e5  mov     r15, [rbp+210h+var_280]
0x1800150e9  test    edi, edi
0x1800150eb  js      loc_1800151C1
0x1800150f1  mov     [rsp+310h+var_2E0], r15
0x1800150f6  lea     r8, aSI64dSS; "%s %I64d %s %s"
0x1800150fd  mov     [rsp+310h+var_2E8], r13
0x180015102  lea     rcx, [rbp+210h+String2]; unsigned __int16 *
0x180015106  mov     r9, rbx
0x180015109  mov     qword ptr [rsp+310h+bIgnoreCase], r12; int
0x18001510e  mov     edx, 104h; unsigned __int64
0x180015113  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015118  mov     edi, eax
0x18001511a  test    eax, eax
0x18001511c  js      loc_180015213
0x180015122  test    rbx, rbx
0x180015125  jz      short loc_18001512F
0x180015127  mov     rcx, rbx; void *
0x18001512a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001512f  xor     r15d, r15d
0x180015132  mov     ebx, r15d
0x180015135  cmp     rbx, [rsi+10h]
0x180015139  jnb     short loc_18001517F
0x18001513b  mov     rax, [rsi]
0x18001513e  mov     rdi, [rax+rbx*8]
0x180015142  test    rdi, rdi
0x180015145  jz      loc_18001524A
0x18001514b  mov     rcx, [rdi]; lpString1
0x18001514e  lea     r8, [rbp+210h+String2]; lpString2
0x180015152  mov     r9d, r14d; cchCount2
0x180015155  mov     [rsp+310h+bIgnoreCase], r15d; int
0x18001515a  mov     edx, r14d; cchCount1
0x18001515d  call    cs:__imp_CompareStringOrdinal
0x180015164  nop     dword ptr [rax+rax+00h]
0x180015169  test    eax, eax
0x18001516b  jz      loc_18001523D
0x180015171  cmp     eax, 2
0x180015174  jz      loc_18001533D
0x18001517a  inc     rbx
0x18001517d  jmp     short loc_180015135
0x18001517f  mov     eax, 80070490h
0x180015184  mov     rcx, [rbp+210h+var_60]
0x18001518b  xor     rcx, rsp; StackCookie
0x18001518e  call    __security_check_cookie
0x180015193  movaps  xmm6, [rsp+310h+var_50]
0x18001519b  add     rsp, 2D8h
0x1800151a2  pop     r15
0x1800151a4  pop     r14
0x1800151a6  pop     r13
0x1800151a8  pop     r12
0x1800151aa  pop     rdi
0x1800151ab  pop     rsi
0x1800151ac  pop     rbx
0x1800151ad  pop     rbp
0x1800151ae  retn
0x1800151b0  mov     rbx, [rsp+310h+var_2C8+8]
0x1800151b5  mov     edi, 80070057h
0x1800151ba  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800151c1  mov     rcx, [rbp+218h]; this
0x1800151c8  lea     r8, aOnecoreAdminAp_59; "onecore\\admin\\appmodel\\packagereposi"...
0x1800151cf  mov     r9d, edi; char *
0x1800151d2  mov     edx, 0D0h; void *
0x1800151d7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800151dc  test    rbx, rbx
0x1800151df  jz      short loc_1800151E9
0x1800151e1  mov     rcx, rbx; void *
0x1800151e4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800151e9  test    edi, edi
0x1800151eb  jns     loc_18001512F
0x1800151f1  mov     rcx, [rbp+218h]; this
0x1800151f8  lea     r8, aOnecoreAdminAp_59; "onecore\\admin\\appmodel\\packagereposi"...
0x1800151ff  mov     r9d, edi; char *
0x180015202  mov     edx, 0B2h; void *
0x180015207  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001520c  mov     eax, edi
0x18001520e  jmp     loc_180015184
0x180015213  mov     rcx, [rbp+218h]; this
0x18001521a  lea     r8, aOnecoreAdminAp_59; "onecore\\admin\\appmodel\\packagereposi"...
0x180015221  mov     r9d, eax; char *
0x180015224  mov     edx, 0D2h; void *
0x180015229  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001522e  test    rbx, rbx
0x180015231  jz      short loc_1800151F1
0x180015233  mov     rcx, rbx; void *
0x180015236  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001523b  jmp     short loc_1800151F1
0x18001523d  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "compareResult != 0")
0x180015242  inc     rbx
0x180015245  jmp     loc_180015135
0x18001524a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pair != nullptr")
0x18001524f  jmp     loc_18001514B
0x180015254  cmp     r15d, 20h ; ' '
0x180015258  ja      loc_1800152F0
0x18001525e  mov     eax, 8
0x180015263  mov     [rsp+310h+var_2D0], eax
0x180015267  cmp     r15d, eax
0x18001526a  jbe     short loc_180015277
0x18001526c  add     eax, eax
0x18001526e  cmp     eax, r15d
0x180015271  jb      short loc_18001526C
0x180015273  mov     [rsp+310h+var_2D0], eax
0x180015277  cmp     eax, 3FFFFFFFh
0x18001527c  ja      short loc_1800152F8
0x18001527e  test    eax, eax
0x180015280  jz      loc_180015467
0x180015286  lea     ecx, [rax+1]
0x180015289  mov     [rsp+310h+var_2A8], ecx
0x18001528d  test    ecx, ecx
0x18001528f  jz      loc_1800150A3
0x180015295  psrldq  xmm6, 8
0x18001529a  mov     eax, 2
0x18001529f  mul     rcx
0x1800152a2  movq    rbx, xmm6
0x1800152a7  mov     [rsp+310h+var_2B0], rcx
0x1800152ac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800152b3  cmovb   rax, r14
0x1800152b7  mov     rcx, rax; unsigned __int64
0x1800152ba  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800152bf  mov     rdi, rax
0x1800152c2  test    rax, rax
0x1800152c5  jnz     loc_180015497
0x1800152cb  mov     rcx, [rbp+218h]; this
0x1800152d2  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x1800152d9  mov     edi, 8007000Eh
0x1800152de  mov     edx, 193h; void *
0x1800152e3  mov     r9d, edi; char *
0x1800152e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800152eb  jmp     loc_1800154F5
0x1800152f0  mov     eax, r15d
0x1800152f3  jmp     loc_180015273
0x1800152f8  mov     rbx, [rsp+310h+var_2C8+8]
0x1800152fd  mov     edi, 80070503h
0x180015302  mov     edx, 1A9h; void *
0x180015307  mov     rcx, [rbp+218h]; this
0x18001530e  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x180015315  mov     r9d, edi; char *
0x180015318  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001531d  mov     rcx, [rbp+218h]; this
0x180015324  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x18001532b  mov     r9d, edi; char *
0x18001532e  mov     edx, 232h; void *
0x180015333  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015338  jmp     loc_1800150D5
0x18001533d  cmp     rbx, 40000000h
0x180015344  jz      loc_18001517F
0x18001534a  cmp     rbx, [rsi+10h]
0x18001534e  jnb     short loc_1800153B0
0x180015350  lfence
0x180015353  mov     rax, [rsi]
0x180015356  mov     rax, [rax+rbx*8]
0x18001535a  mov     rdx, [rax+8]; unsigned __int16 *
0x18001535e  test    rdx, rdx
0x180015361  jz      short loc_1800153B5
0x180015363  mov     r8d, 3FFFFFFEh
0x180015369  mov     rax, rdx
0x18001536c  mov     ecx, r8d
0x18001536f  nop
0x180015370  cmp     [rax], r15w
0x180015374  jz      short loc_180015380
0x180015376  add     rax, 2
0x18001537a  sub     rcx, 1
0x18001537e  jnz     short loc_180015370
0x180015380  test    rcx, rcx
0x180015383  mov     ebx, 80070057h
0x180015388  cmovnz  ebx, r15d
0x18001538c  jz      loc_18001553F
0x180015392  sub     r8d, ecx; unsigned int
0x180015395  mov     rcx, [rsp+310h+var_298]; this
0x18001539a  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x18001539f  mov     ebx, eax
0x1800153a1  test    eax, eax
0x1800153a3  js      loc_18001555A
0x1800153a9  xor     eax, eax
0x1800153ab  jmp     loc_180015184
0x1800153b0  mov     rax, r15
0x1800153b3  jmp     short loc_18001535A
0x1800153b5  mov     rcx, [rsp+310h+var_298]; this
0x1800153ba  call    ?Clear@StringBuffer@Common@@QEAAXXZ; Common::StringBuffer::Clear(void)
0x1800153bf  xor     eax, eax
0x1800153c1  jmp     loc_180015184
0x1800153c6  mov     rcx, rbx; void *
0x1800153c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800153ce  mov     ecx, [rsp+310h+var_2A8]
0x1800153d2  mov     rbx, rdi
0x1800153d5  mov     eax, [rsp+310h+var_2D0]
0x1800153d9  mov     edi, ecx
0x1800153db  mov     rdx, [rsp+310h+var_2A0]
0x1800153e0  mov     [rsp+310h+var_2B8], ecx
0x1800153e4  mov     ecx, dword ptr [rsp+310h+var_2C8]
0x1800153e8  mov     [rsp+310h+var_2C8+8], rbx
0x1800153ed  cmp     ecx, eax
0x1800153ef  ja      short loc_180015409
0x1800153f1  jnb     loc_1800150A8
0x1800153f7  test    ecx, ecx
0x1800153f9  jnz     loc_1800150A8
0x1800153ff  xor     eax, eax
0x180015401  mov     [rbx], ax
0x180015404  jmp     loc_1800150A8
0x180015409  mov     ecx, eax
0x18001540b  mov     dword ptr [rsp+310h+var_2C8], eax
0x18001540f  xor     eax, eax
0x180015411  mov     [rbx+rcx*2], ax
0x180015415  jmp     loc_1800150A8
0x18001541a  mov     edx, r15d; unsigned int
0x18001541d  lea     rcx, [rsp+310h+var_2C8]; this
0x180015422  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x180015427  mov     edi, eax
0x180015429  test    eax, eax
0x18001542b  js      loc_1800154FF
0x180015431  mov     rbx, [rsp+310h+var_2C8+8]
0x180015436  mov     rdx, [rsp+310h+var_2A0]
0x18001543b  jmp     loc_1800150BB
0x180015440  mov     rcx, [rbp+218h]; this
0x180015447  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\common\\sidhel"...
0x18001544e  mov     r9d, eax; char *
0x180015451  mov     edx, 1Eh; void *
0x180015456  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001545b  mov     rbx, [rsp+310h+var_2C8+8]
0x180015460  mov     edi, eax
0x180015462  jmp     loc_1800150E9
0x180015467  psrldq  xmm6, 8
0x18001546c  movq    rbx, xmm6
0x180015471  test    rbx, rbx
0x180015474  jz      short loc_18001548E
0x180015476  mov     rcx, rbx; void *
0x180015479  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001547e  mov     rdx, [rsp+310h+var_2A0]
0x180015483  xor     ebx, ebx
0x180015485  mov     [rsp+310h+var_2C8+8], rbx
0x18001548a  mov     dword ptr [rsp+310h+var_2C8], ebx
0x18001548e  mov     [rsp+310h+var_2B8], edi
0x180015492  jmp     loc_1800150A8
0x180015497  mov     rdx, [rsp+310h+var_2B0]
0x18001549c  xor     r9d, r9d; SourceSize
0x18001549f  add     rdx, rdx; DestinationSize
0x1800154a2  mov     r8, rbx; Source
  ... truncated ...
```
