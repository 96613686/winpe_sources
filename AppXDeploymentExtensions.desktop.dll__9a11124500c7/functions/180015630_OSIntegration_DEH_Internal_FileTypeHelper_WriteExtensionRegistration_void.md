# OSIntegration::DEH::Internal::FileTypeHelper::WriteExtensionRegistration(void)

- ea: `0x180015630`
- end: `0x180015cee`
- name: `?WriteExtensionRegistration@FileTypeHelper@Internal@DEH@OSIntegration@@UEAAJXZ`
- size: `1726`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::FileTypeHelper *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180012fc8`
- `0x180015590`
- `0x180015630`
- `0x180015cf4`
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
- `0x1801ac010`

## import_xrefs

- `AppxDeploymentServer!PackageRepositoryAllocate` at `0x180015838`
- `AppxDeploymentServer!PackageRepositoryAllocate` at `0x180015838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b9b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015811`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015aa3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015811`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015aa3`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180015719`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180015719`
- `ntdll!RtlFreeUnicodeString` at `0x18001577b`
- `ntdll!RtlFreeUnicodeString` at `0x18001577b`

## string_xrefs

- `0x180015bd2`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x1800159b7`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800159e0`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180015a00`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180015c5d`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180015c75`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180015c9a`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180015cb5`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OSIntegration::DEH::Internal::FileTypeHelper::WriteExtensionRegistration(
        OSIntegration::DEH::Internal::FileTypeHelper *this)
{
  bool v1; // zf
  OSIntegration::DEH::Internal::FileTypeHelper *v2; // r13
  _QWORD *v3; // rsi
  unsigned __int64 i; // r12
  __int64 v5; // rbx
  void *v6; // rdi
  unsigned int v7; // r14d
  __int64 v8; // rax
  __int64 v9; // rcx
  NTSTATUS v10; // eax
  const struct std::nothrow_t *v11; // rdx
  __int64 v12; // rsi
  PWSTR Buffer; // r12
  _WORD *v14; // rdi
  unsigned int v15; // ebx
  int v16; // eax
  const struct std::nothrow_t *v17; // rdx
  unsigned __int64 k; // rbx
  LPCWCH *v19; // rdi
  int v20; // eax
  const unsigned __int16 **v21; // rax
  const unsigned __int16 **v22; // rdi
  const unsigned __int16 **v23; // rcx
  __int64 v24; // rdx
  const struct std::nothrow_t *v26; // rdx
  const struct std::nothrow_t *v27; // rdx
  unsigned int j; // ebx
  __int64 v29; // r12
  unsigned __int64 v30; // rax
  void *v31; // rax
  void *v32; // r14
  __int64 v33; // rcx
  const unsigned __int16 *v34; // r14
  int v35; // eax
  __int64 v36; // rcx
  int v37; // eax
  int v38; // eax
  __int64 v39; // rdx
  int v40; // eax
  signed int LastError; // eax
  unsigned int v42; // eax
  const struct std::nothrow_t *v43; // rdx
  errno_t v44; // r13d
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasec; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  int bIgnoreCased; // [rsp+20h] [rbp-E0h]
  char *v50; // [rsp+28h] [rbp-D8h]
  void *Source[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v52; // [rsp+50h] [rbp-B0h]
  PWSTR v53; // [rsp+58h] [rbp-A8h]
  OSIntegration::DEH::Internal::FileTypeHelper *v54; // [rsp+60h] [rbp-A0h]
  LPCWCH lpString2; // [rsp+68h] [rbp-98h]
  unsigned __int64 v56; // [rsp+70h] [rbp-90h]
  struct _UNICODE_STRING UnicodeString; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v58; // [rsp+88h] [rbp-78h]
  __int64 v59; // [rsp+90h] [rbp-70h]
  int v60[2]; // [rsp+98h] [rbp-68h]
  WCHAR String2[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v1 = *((_QWORD *)this + 42) == 0;
  v2 = this;
  v54 = this;
  if ( !v1 )
  {
    v3 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 48LL) + 152LL))(*(_QWORD *)(*((_QWORD *)this + 3) + 48LL));
    v58 = v3;
    for ( i = 0; ; i = v56 + 1 )
    {
      v56 = i;
      if ( i >= *((_QWORD *)v2 + 42) )
        return 0;
      v5 = *((_QWORD *)v2 + 3);
      lpString2 = (LPCWCH)*((_QWORD *)v2 + 18);
      v6 = *(void **)(v5 + 784);
      memset_0(String2, 0, 0x208u);
      v7 = 0;
      v52 = 0;
      *(_OWORD *)Source = 0;
      if ( !v6 )
      {
        v14 = Source[1];
        v15 = -2147024809;
LABEL_30:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xD0,
          (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
          (const char *)v15,
          bIgnoreCase);
        if ( v14 )
          operator delete(v14, v26);
LABEL_35:
        v24 = 166;
LABEL_28:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
          (const char *)v15,
          bIgnoreCase);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4E4,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
          (const char *)v15,
          bIgnoreCasec);
        return v15;
      }
      v8 = *((_QWORD *)v2 + 40);
      UnicodeString = 0;
      v9 = *(_QWORD *)(v8 + 8 * i);
      *(_QWORD *)v60 = *(_QWORD *)(v5 + 64);
      v59 = *(_QWORD *)(v9 + 8);
      v10 = RtlConvertSidToUnicodeString(&UnicodeString, v6, 1u);
      if ( v10 < 0 )
      {
        v42 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x1E,
                (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
                (const char *)(unsigned int)v10,
                bIgnoreCase);
        v14 = Source[1];
        v15 = v42;
        goto LABEL_13;
      }
      v12 = UnicodeString.Length >> 1;
      Buffer = UnicodeString.Buffer;
      v53 = UnicodeString.Buffer;
      if ( UnicodeString.Length >> 1 )
      {
        if ( (unsigned int)v12 > 0x20 )
        {
          j = UnicodeString.Length >> 1;
        }
        else
        {
          for ( j = 8; j < (unsigned int)v12; j *= 2 )
            ;
        }
        v14 = Source[1];
        if ( j > 0x3FFFFFFF )
        {
          v15 = -2147023613;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A9,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)0x80070503LL,
            bIgnoreCase);
LABEL_48:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x232,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)v15,
            bIgnoreCaseb);
          goto LABEL_12;
        }
        if ( j )
        {
          v29 = j + 1;
          v30 = 2LL * (unsigned int)v29;
          if ( !is_mul_ok((unsigned int)v29, 2u) )
            v30 = -1;
          v31 = operator new[](v30, (const struct std::nothrow_t *)&std::nothrow);
          v32 = v31;
          if ( !v31 )
          {
            v15 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x193,
              (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
              (const char *)0x8007000ELL,
              bIgnoreCase);
LABEL_84:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1C4,
              (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
              (const char *)v15,
              bIgnoreCasea);
            v2 = v54;
            goto LABEL_48;
          }
          v44 = memcpy_s(v31, 2 * v29, v14, 0);
          if ( v44 )
          {
            operator delete(v32, v43);
            v15 = -2147024809;
            LODWORD(v50) = v44;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x198,
              (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
              (const char *)0x80070057LL,
              (int)"0x%08lx",
              v50);
            goto LABEL_84;
          }
          operator delete(v14, v43);
          v14 = v32;
          v2 = v54;
          v7 = j + 1;
          v52 = j + 1;
          Source[1] = v14;
          if ( LODWORD(Source[0]) > j )
          {
            LODWORD(Source[0]) = j;
            v14[j] = 0;
          }
          else if ( LODWORD(Source[0]) < j && !LODWORD(Source[0]) )
          {
            *v14 = 0;
          }
          Buffer = v53;
        }
        else
        {
          if ( Source[1] )
          {
            operator delete(Source[1], v11);
            v14 = 0;
            Source[1] = 0;
            LODWORD(Source[0]) = 0;
          }
          v52 = 0;
        }
      }
      else
      {
        v14 = Source[1];
      }
      if ( (unsigned int)v12 <= (v7 != 0 ? v7 - 1 : 0) )
        goto LABEL_9;
      v40 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)Source, v12);
      v15 = v40;
      if ( v40 >= 0 )
      {
        v14 = Source[1];
LABEL_9:
        if ( (_DWORD)v12 )
          v14[v12] = 0;
        memcpy_0(v14, Buffer, (unsigned int)(2 * v12));
        v15 = 0;
        goto LABEL_12;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x20C,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v40,
        bIgnoreCase);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x235,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)v15,
        bIgnoreCased);
      v14 = Source[1];
LABEL_12:
      RtlFreeUnicodeString(&UnicodeString);
      v3 = v58;
LABEL_13:
      if ( (v15 & 0x80000000) != 0 )
        goto LABEL_30;
      v50 = (char *)L"windows.fileTypeAssociation";
      bIgnoreCase = v60[0];
      v16 = StringCchPrintfW(String2, 0x104u, L"%s %I64d %s %s", v14);
      v15 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xD2,
          (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
          (const char *)(unsigned int)v16,
          bIgnoreCase);
        if ( v14 )
          operator delete(v14, v27);
        goto LABEL_35;
      }
      if ( v14 )
        operator delete(v14, v17);
      for ( k = 0; ; ++k )
      {
        if ( k >= v3[2] )
          goto LABEL_24;
        v19 = *(LPCWCH **)(*v3 + 8 * k);
        if ( !v19 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v20 = CompareStringOrdinal(*v19, -1, String2, -1, 0);
        if ( v20 )
          break;
        MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_23:
        ;
      }
      if ( v20 != 2 )
        goto LABEL_23;
      if ( k == 0x40000000 )
      {
LABEL_24:
        v21 = (const unsigned __int16 **)PackageRepositoryAllocate(0x10u);
        v22 = v21;
        if ( v21 )
        {
          *v21 = 0;
          v21[1] = 0;
          v38 = PackageRepository::PropertyBagKeyValuePair::Set(v21, String2);
          v15 = v38;
          if ( v38 < 0 )
          {
            v39 = 139;
          }
          else
          {
            v38 = PackageRepository::PropertyBagKeyValuePair::Set(v22 + 1, lpString2);
            v15 = v38;
            if ( v38 < 0 )
            {
              v39 = 140;
            }
            else
            {
              v38 = Common::Array<PackageRepository::PropertyBagKeyValuePair,Common::ContainerOperations<PackageRepository::PropertyBagKeyValuePair,PackageRepository::PropertyBagKeyValuePair>,unsigned short,Common::ContainerOperations<unsigned short,PackageRepository::PropertyBagKeyValuePair>,Common::ArrayOperations<PackageRepository::PropertyBagKeyValuePair,PackageRepository::PropertyBagKeyValuePair>>::Add(
                      v3,
                      v22);
              v15 = v38;
              if ( v38 >= 0 )
              {
                Common::AutoPtrDeallocate<PackageRepository::PropertyBagKeyValuePair>(0);
                continue;
              }
              v39 = 142;
            }
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v39,
            (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
            (const char *)(unsigned int)v38,
            bIgnoreCase);
          v23 = v22;
        }
        else
        {
          v15 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x89,
            (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
            (const char *)0x8007000ELL,
            bIgnoreCase);
          v23 = 0;
        }
        Common::AutoPtrDeallocate<PackageRepository::PropertyBagKeyValuePair>(v23);
LABEL_27:
        v24 = 168;
        goto LABEL_28;
      }
      if ( k < v3[2] )
      {
        _mm_lfence();
        v33 = *(_QWORD *)(*v3 + 8 * k);
      }
      else
      {
        v33 = 0;
      }
      v34 = lpString2;
      v35 = CompareStringOrdinal(*(LPCWCH *)(v33 + 8), -1, lpString2, -1, 0);
      if ( v35 )
      {
        if ( v35 != 2 )
        {
          v36 = k < v3[2] ? *(_QWORD *)(*v3 + 8 * k) : 0LL;
          v37 = PackageRepository::PropertyBagKeyValuePair::Set((const unsigned __int16 **)(v36 + 8), v34);
          v15 = v37;
          if ( v37 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x9A,
              (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
              (const char *)(unsigned int)v37,
              bIgnoreCase);
            goto LABEL_27;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v15 = LastError;
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
        if ( (v15 & 0x80000000) != 0 )
          goto LABEL_27;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180015630  push    rbp
0x180015632  push    rbx
0x180015633  push    rsi
0x180015634  push    rdi
0x180015635  push    r12
0x180015637  push    r13
0x180015639  push    r14
0x18001563b  push    r15
0x18001563d  lea     rbp, [rsp-1C8h]
0x180015645  sub     rsp, 2C8h
0x18001564c  mov     rax, cs:__security_cookie
0x180015653  xor     rax, rsp
0x180015656  mov     [rbp+200h+var_50], rax
0x18001565d  cmp     qword ptr [rcx+150h], 0
0x180015665  mov     r13, rcx
0x180015668  mov     [rsp+300h+var_2A0], rcx
0x18001566d  jz      loc_180015CE7
0x180015673  mov     rax, [rcx+18h]
0x180015677  mov     rcx, [rax+30h]
0x18001567b  mov     rax, [rcx]
0x18001567e  mov     rax, [rax+98h]
0x180015685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001568a  mov     rsi, rax
0x18001568d  mov     [rbp+200h+var_278], rax
0x180015691  xor     r12d, r12d
0x180015694  lea     r15, aOnecoreAdminAp_59; "onecore\\admin\\appmodel\\packagereposi"...
0x18001569b  mov     [rsp+300h+var_290], r12
0x1800156a0  cmp     r12, [r13+150h]
0x1800156a7  jnb     loc_180015CE7
0x1800156ad  mov     rax, [r13+90h]
0x1800156b4  lea     rcx, [rbp+200h+String2]; void *
0x1800156b8  mov     rbx, [r13+18h]
0x1800156bc  xor     edx, edx; Val
0x1800156be  mov     r8d, 208h; Size
0x1800156c4  mov     [rsp+300h+lpString2], rax
0x1800156c9  mov     rdi, [rbx+310h]
0x1800156d0  call    memset_0
0x1800156d5  xor     r14d, r14d
0x1800156d8  xorps   xmm0, xmm0
0x1800156db  mov     [rsp+300h+var_2B0], r14d
0x1800156e0  movups  xmmword ptr [rsp+300h+Source], xmm0
0x1800156e5  test    rdi, rdi
0x1800156e8  jz      loc_1800158CB
0x1800156ee  mov     rax, [r13+140h]
0x1800156f5  mov     r8b, 1; AllocateDestinationString
0x1800156f8  mov     rdx, rdi; Sid
0x1800156fb  movups  xmmword ptr [rsp+300h+UnicodeString.Length], xmm0
0x180015700  mov     rcx, [rax+r12*8]
0x180015704  mov     rax, [rbx+40h]
0x180015708  mov     qword ptr [rbp+200h+var_268], rax
0x18001570c  mov     r12, [rcx+8]
0x180015710  lea     rcx, [rsp+300h+UnicodeString]; UnicodeString
0x180015715  mov     [rbp+200h+var_270], r12
0x180015719  call    cs:__imp_RtlConvertSidToUnicodeString
0x180015720  nop     dword ptr [rax+rax+00h]
0x180015725  test    eax, eax
0x180015727  js      loc_180015BCB
0x18001572d  movzx   esi, [rsp+300h+UnicodeString.Length]
0x180015732  shr     esi, 1
0x180015734  mov     r12, [rbp+200h+UnicodeString.Buffer]
0x180015738  mov     [rsp+300h+var_2A8], r12
0x18001573d  jnz     loc_180015945
0x180015743  mov     rdi, [rsp+300h+Source+8]
0x180015748  lea     ecx, [r14-1]
0x18001574c  neg     r14d
0x18001574f  sbb     eax, eax
0x180015751  and     eax, ecx
0x180015753  cmp     esi, eax
0x180015755  ja      loc_180015B7B
0x18001575b  test    esi, esi
0x18001575d  jz      short loc_180015765
0x18001575f  xor     eax, eax
0x180015761  mov     [rdi+rsi*2], ax
0x180015765  lea     r8d, [rsi+rsi]; Size
0x180015769  mov     rdx, r12; Src
0x18001576c  mov     rcx, rdi; void *
0x18001576f  call    memcpy_0
0x180015774  xor     ebx, ebx
0x180015776  lea     rcx, [rsp+300h+UnicodeString]; UnicodeString
0x18001577b  call    cs:__imp_RtlFreeUnicodeString
0x180015782  nop     dword ptr [rax+rax+00h]
0x180015787  mov     rsi, [rbp+200h+var_278]
0x18001578b  mov     r12, [rbp+200h+var_270]
0x18001578f  test    ebx, ebx
0x180015791  js      loc_1800158D5
0x180015797  lea     rax, aWindowsFiletyp; "windows.fileTypeAssociation"
0x18001579e  mov     [rsp+300h+var_2D0], r12
0x1800157a3  mov     [rsp+300h+var_2D8], rax
0x1800157a8  lea     r8, aSI64dSS; "%s %I64d %s %s"
0x1800157af  mov     rax, qword ptr [rbp+200h+var_268]
0x1800157b3  lea     rcx, [rbp+200h+String2]; unsigned __int16 *
0x1800157b7  mov     r9, rdi
0x1800157ba  mov     qword ptr [rsp+300h+bIgnoreCase], rax; int
0x1800157bf  mov     edx, 104h; unsigned __int64
0x1800157c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800157c9  mov     ebx, eax
0x1800157cb  test    eax, eax
0x1800157cd  js      loc_180015903
0x1800157d3  test    rdi, rdi
0x1800157d6  jz      short loc_1800157E0
0x1800157d8  mov     rcx, rdi; void *
0x1800157db  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800157e0  xor     ebx, ebx
0x1800157e2  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800157e6  cmp     rbx, [rsi+10h]
0x1800157ea  jnb     short loc_180015833
0x1800157ec  mov     rax, [rsi]
0x1800157ef  mov     rdi, [rax+rbx*8]
0x1800157f3  test    rdi, rdi
0x1800157f6  jz      loc_180015931
0x1800157fc  mov     rcx, [rdi]; lpString1
0x1800157ff  lea     r8, [rbp+200h+String2]; lpString2
0x180015803  mov     r9d, r12d; cchCount2
0x180015806  mov     [rsp+300h+bIgnoreCase], 0; bIgnoreCase
0x18001580e  mov     edx, r12d; cchCount1
0x180015811  call    cs:__imp_CompareStringOrdinal
0x180015818  nop     dword ptr [rax+rax+00h]
0x18001581d  test    eax, eax
0x18001581f  jz      loc_18001593B
0x180015825  cmp     eax, 2
0x180015828  jz      loc_180015A74
0x18001582e  inc     rbx
0x180015831  jmp     short loc_1800157E6
0x180015833  mov     ecx, 10h
0x180015838  call    cs:__imp_?PackageRepositoryAllocate@@YAPEAX_K@Z; PackageRepositoryAllocate(unsigned __int64)
0x18001583f  nop     dword ptr [rax+rax+00h]
0x180015844  mov     rdi, rax
0x180015847  test    rax, rax
0x18001584a  jnz     loc_180015B02
0x180015850  mov     rcx, [rbp+208h]; this
0x180015857  mov     ebx, 8007000Eh
0x18001585c  mov     r9d, ebx; char *
0x18001585f  mov     r8, r15; unsigned int
0x180015862  mov     edx, 89h; void *
0x180015867  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001586c  xor     ecx, ecx
0x18001586e  call    ??$AutoPtrDeallocate@VPropertyBagKeyValuePair@PackageRepository@@@Common@@YAXPEAVPropertyBagKeyValuePair@PackageRepository@@@Z; Common::AutoPtrDeallocate<PackageRepository::PropertyBagKeyValuePair>(PackageRepository::PropertyBagKeyValuePair *)
0x180015873  mov     edx, 0A8h; void *
0x180015878  mov     rcx, [rbp+208h]; this
0x18001587f  mov     r9d, ebx; char *
0x180015882  mov     r8, r15; unsigned int
0x180015885  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001588a  mov     rcx, [rbp+208h]; this
0x180015891  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180015898  mov     r9d, ebx; char *
0x18001589b  mov     edx, 4E4h; void *
0x1800158a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800158a5  mov     eax, ebx
0x1800158a7  mov     rcx, [rbp+200h+var_50]
0x1800158ae  xor     rcx, rsp; StackCookie
0x1800158b1  call    __security_check_cookie
0x1800158b6  add     rsp, 2C8h
0x1800158bd  pop     r15
0x1800158bf  pop     r14
0x1800158c1  pop     r13
0x1800158c3  pop     r12
0x1800158c5  pop     rdi
0x1800158c6  pop     rsi
0x1800158c7  pop     rbx
0x1800158c8  pop     rbp
0x1800158c9  retn
0x1800158cb  mov     rdi, [rsp+300h+Source+8]
0x1800158d0  mov     ebx, 80070057h
0x1800158d5  mov     rcx, [rbp+208h]; this
0x1800158dc  mov     r9d, ebx; char *
0x1800158df  mov     r8, r15; unsigned int
0x1800158e2  mov     edx, 0D0h; void *
0x1800158e7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800158ec  test    rdi, rdi
0x1800158ef  jz      short loc_1800158F9
0x1800158f1  mov     rcx, rdi; void *
0x1800158f4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800158f9  test    ebx, ebx
0x1800158fb  jns     loc_1800157E0
0x180015901  jmp     short loc_180015927
0x180015903  mov     rcx, [rbp+208h]; this
0x18001590a  mov     r9d, eax; char *
0x18001590d  mov     r8, r15; unsigned int
0x180015910  mov     edx, 0D2h; void *
0x180015915  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001591a  test    rdi, rdi
0x18001591d  jz      short loc_180015927
0x18001591f  mov     rcx, rdi; void *
0x180015922  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015927  mov     edx, 0A6h
0x18001592c  jmp     loc_180015878
0x180015931  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pair != nullptr")
0x180015936  jmp     loc_1800157FC
0x18001593b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "compareResult != 0")
0x180015940  jmp     loc_18001582E
0x180015945  cmp     esi, 20h ; ' '
0x180015948  ja      loc_1800159D5
0x18001594e  mov     ebx, 8
0x180015953  cmp     esi, ebx
0x180015955  jbe     short loc_18001595D
0x180015957  add     ebx, ebx
0x180015959  cmp     ebx, esi
0x18001595b  jb      short loc_180015957
0x18001595d  mov     rdi, [rsp+300h+Source+8]
0x180015962  cmp     ebx, 3FFFFFFFh
0x180015968  ja      short loc_1800159D9
0x18001596a  test    ebx, ebx
0x18001596c  jz      loc_180015BF2
0x180015972  lea     r12d, [rbx+1]
0x180015976  test    r12d, r12d
0x180015979  jz      loc_180015A47
0x18001597f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180015986  mov     r13d, r12d
0x180015989  mov     eax, 2
0x18001598e  mul     r13
0x180015991  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015998  cmovb   rax, rcx
0x18001599c  mov     rcx, rax; unsigned __int64
0x18001599f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800159a4  mov     r14, rax
0x1800159a7  test    rax, rax
0x1800159aa  jnz     loc_180015C14
0x1800159b0  mov     rcx, [rbp+208h]; this
0x1800159b7  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x1800159be  mov     ebx, 8007000Eh
0x1800159c3  mov     edx, 193h; void *
0x1800159c8  mov     r9d, ebx; char *
0x1800159cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800159d0  jmp     loc_180015C6E
0x1800159d5  mov     ebx, esi
0x1800159d7  jmp     short loc_18001595D
0x1800159d9  mov     rcx, [rbp+208h]; this
0x1800159e0  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x1800159e7  mov     ebx, 80070503h
0x1800159ec  mov     edx, 1A9h; void *
0x1800159f1  mov     r9d, ebx; char *
0x1800159f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800159f9  mov     rcx, [rbp+208h]; this
0x180015a00  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x180015a07  mov     r9d, ebx; char *
0x180015a0a  mov     edx, 232h; void *
0x180015a0f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015a14  jmp     loc_180015776
0x180015a19  mov     rcx, rdi; void *
0x180015a1c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015a21  mov     eax, dword ptr [rsp+300h+Source]
0x180015a25  mov     rdi, r14
0x180015a28  mov     r13, [rsp+300h+var_2A0]
0x180015a2d  mov     r14d, r12d
0x180015a30  mov     [rsp+300h+var_2B0], r12d
0x180015a35  mov     [rsp+300h+Source+8], rdi
0x180015a3a  cmp     eax, ebx
0x180015a3c  ja      short loc_180015A51
0x180015a3e  jnb     short loc_180015A47
0x180015a40  test    eax, eax
0x180015a42  jnz     short loc_180015A47
0x180015a44  mov     [rdi], ax
0x180015a47  mov     r12, [rsp+300h+var_2A8]
0x180015a4c  jmp     loc_180015748
0x180015a51  mov     ecx, ebx
0x180015a53  xor     eax, eax
0x180015a55  mov     dword ptr [rsp+300h+Source], ebx
0x180015a59  mov     [rdi+rcx*2], ax
0x180015a5d  jmp     short loc_180015A47
0x180015a5f  test    ebx, ebx
0x180015a61  js      loc_180015873
0x180015a67  mov     r12, [rsp+300h+var_290]
0x180015a6c  inc     r12
0x180015a6f  jmp     loc_18001569B
0x180015a74  cmp     rbx, 40000000h
0x180015a7b  jz      loc_180015833
0x180015a81  cmp     rbx, [rsi+10h]
0x180015a85  jb      short loc_180015AF6
0x180015a87  xor     ecx, ecx
0x180015a89  mov     r14, [rsp+300h+lpString2]
0x180015a8e  mov     r9d, r12d; cchCount2
0x180015a91  mov     rcx, [rcx+8]; lpString1
0x180015a95  mov     r8, r14; lpString2
0x180015a98  mov     edx, r12d; cchCount1
0x180015a9b  mov     [rsp+300h+bIgnoreCase], 0; int
0x180015aa3  call    cs:__imp_CompareStringOrdinal
0x180015aaa  nop     dword ptr [rax+rax+00h]
0x180015aaf  test    eax, eax
0x180015ab1  jz      loc_180015B9B
0x180015ab7  cmp     eax, 2
0x180015aba  jz      short loc_180015A67
0x180015abc  cmp     rbx, [rsi+10h]
0x180015ac0  jb      loc_180015BBF
0x180015ac6  xor     ecx, ecx
0x180015ac8  add     rcx, 8; unsigned __int16 **
0x180015acc  mov     rdx, r14; unsigned __int16 *
0x180015acf  call    ?Set@PropertyBagKeyValuePair@PackageRepository@@CAJAEAPEBGPEBG@Z; PackageRepository::PropertyBagKeyValuePair::Set(ushort const * &,ushort const *)
0x180015ad4  mov     ebx, eax
0x180015ad6  test    eax, eax
0x180015ad8  jns     short loc_180015A67
0x180015ada  mov     rcx, [rbp+208h]; this
0x180015ae1  mov     r9d, eax; char *
0x180015ae4  mov     r8, r15; unsigned int
0x180015ae7  mov     edx, 9Ah; void *
0x180015aec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015af1  jmp     loc_180015873
0x180015af6  lfence
0x180015af9  mov     rax, [rsi]
0x180015afc  mov     rcx, [rax+rbx*8]
0x180015b00  jmp     short loc_180015A89
  ... truncated ...
```
