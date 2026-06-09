# OSIntegration::DEH::Internal::ProtocolHelper::WriteExtensionRegistration(void)

- ea: `0x180019380`
- end: `0x180019795`
- name: `?WriteExtensionRegistration@ProtocolHelper@Internal@DEH@OSIntegration@@UEAAJXZ`
- size: `1045`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::ProtocolHelper *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180012fc8`
- `0x180015590`
- `0x180015cf4`
- `0x180017ba0`
- `0x180019380`
- `0x180019940`
- `0x18001adb4`
- `0x18005145c`
- `0x180068f18`
- `0x18007cdc0`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800af918`
- `0x1801ac010`

## import_xrefs

- `AppxDeploymentServer!PackageRepositoryAllocate` at `0x180019514`
- `AppxDeploymentServer!PackageRepositoryAllocate` at `0x180019514`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019735`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800194ed`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001965c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800194ed`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001965c`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180019429`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180019429`
- `ntdll!RtlFreeUnicodeString` at `0x18001945c`
- `ntdll!RtlFreeUnicodeString` at `0x18001945c`

## string_xrefs

- `0x18001976c`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x18001956d`: `onecore\admin\appmodel\osim\src\deh\appx\protocol\protocolhelper.cpp`
- `0x180019475`: `windows.protocol`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::ProtocolHelper::WriteExtensionRegistration(
        OSIntegration::DEH::Internal::ProtocolHelper *this)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  _QWORD *v4; // r14
  void *v5; // r15
  __int64 v6; // r13
  NTSTATUS v7; // eax
  unsigned int v8; // ebx
  void *v9; // rdi
  int v10; // eax
  const struct std::nothrow_t *v11; // rdx
  __int64 v12; // rcx
  unsigned __int64 i; // rbx
  LPCWCH *v14; // rdi
  int v15; // eax
  const unsigned __int16 **v16; // rax
  const unsigned __int16 **v17; // rdi
  const unsigned __int16 **v18; // rcx
  __int64 v19; // rdx
  const struct std::nothrow_t *v21; // rdx
  const struct std::nothrow_t *v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdx
  signed int LastError; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasec; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *lpString2; // [rsp+40h] [rbp-C0h]
  struct _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-B8h] BYREF
  void *v36[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v37; // [rsp+68h] [rbp-98h]
  WCHAR String2[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 48LL) + 152LL))(*(_QWORD *)(*((_QWORD *)this + 3) + 48LL));
  v3 = *((_QWORD *)this + 3);
  v4 = (_QWORD *)v2;
  lpString2 = (const unsigned __int16 *)*((_QWORD *)this + 15);
  v5 = *(void **)(v3 + 784);
  memset_0(String2, 0, 0x208u);
  v37 = 0;
  *(_OWORD *)v36 = 0;
  if ( !v5 )
  {
    v8 = -2147024809;
    goto LABEL_21;
  }
  v6 = *(_QWORD *)(v3 + 64);
  UnicodeString = 0;
  v7 = RtlConvertSidToUnicodeString(&UnicodeString, v5, 1u);
  if ( v7 < 0 )
  {
    v8 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x1E,
           (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
           (const char *)(unsigned int)v7,
           bIgnoreCase);
  }
  else
  {
    v8 = Common::StringBuffer::SetValue((Common::StringBuffer *)v36, UnicodeString.Buffer, UnicodeString.Length >> 1);
    RtlFreeUnicodeString(&UnicodeString);
  }
  if ( (v8 & 0x80000000) != 0 )
  {
LABEL_21:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
      (const char *)v8,
      bIgnoreCase);
    if ( v36[1] )
      operator delete(v36[1], v21);
LABEL_26:
    v19 = 166;
LABEL_19:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
      (const char *)v8,
      bIgnoreCaseb);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21A,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\protocol\\protocolhelper.cpp",
      (const char *)v8,
      bIgnoreCasec);
    return v8;
  }
  v9 = v36[1];
  bIgnoreCasea = v6;
  v10 = StringCchPrintfW(String2, 0x104u, L"%s %I64d %s %s", v36[1]);
  v8 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
      (const char *)(unsigned int)v10,
      v6);
    if ( v9 )
      operator delete(v9, v22);
    goto LABEL_26;
  }
  if ( v9 )
    operator delete(v9, v11);
  for ( i = 0; ; ++i )
  {
    if ( i >= v4[2] )
      goto LABEL_15;
    v14 = *(LPCWCH **)(*v4 + 8 * i);
    if ( !v14 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v12);
    v15 = CompareStringOrdinal(*v14, -1, String2, -1, 0);
    if ( v15 )
      break;
    MicrosoftTelemetryAssertTriggeredNoArgs(v12);
LABEL_14:
    ;
  }
  if ( v15 != 2 )
    goto LABEL_14;
  if ( i == 0x40000000 )
  {
LABEL_15:
    v16 = (const unsigned __int16 **)PackageRepositoryAllocate(0x10u);
    v17 = v16;
    if ( v16 )
    {
      *v16 = 0;
      v16[1] = 0;
      v27 = PackageRepository::PropertyBagKeyValuePair::Set(v16, String2);
      v8 = v27;
      if ( v27 < 0 )
      {
        v28 = 139;
      }
      else
      {
        v27 = PackageRepository::PropertyBagKeyValuePair::Set(v17 + 1, lpString2);
        v8 = v27;
        if ( v27 < 0 )
        {
          v28 = 140;
        }
        else
        {
          v27 = Common::Array<PackageRepository::PropertyBagKeyValuePair,Common::ContainerOperations<PackageRepository::PropertyBagKeyValuePair,PackageRepository::PropertyBagKeyValuePair>,unsigned short,Common::ContainerOperations<unsigned short,PackageRepository::PropertyBagKeyValuePair>,Common::ArrayOperations<PackageRepository::PropertyBagKeyValuePair,PackageRepository::PropertyBagKeyValuePair>>::Add(
                  v4,
                  v17);
          v8 = v27;
          if ( v27 >= 0 )
          {
            Common::AutoPtrDeallocate<PackageRepository::PropertyBagKeyValuePair>(0);
            return 0;
          }
          v28 = 142;
        }
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
        (const char *)(unsigned int)v27,
        bIgnoreCasea);
      v18 = v17;
    }
    else
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
        (const char *)0x8007000ELL,
        bIgnoreCasea);
      v18 = 0;
    }
    Common::AutoPtrDeallocate<PackageRepository::PropertyBagKeyValuePair>(v18);
LABEL_18:
    v19 = 168;
    goto LABEL_19;
  }
  if ( i < v4[2] )
  {
    _mm_lfence();
    v23 = *(_QWORD *)(*v4 + 8 * i);
  }
  else
  {
    v23 = 0;
  }
  v24 = CompareStringOrdinal(*(LPCWCH *)(v23 + 8), -1, lpString2, -1, 0);
  if ( v24 )
  {
    if ( v24 != 2 )
    {
      v25 = i < v4[2] ? *(_QWORD *)(*v4 + 8 * i) : 0LL;
      v26 = PackageRepository::PropertyBagKeyValuePair::Set((const unsigned __int16 **)(v25 + 8), lpString2);
      v8 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x9A,
          (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\staterepository\\repositorypropertybag.cpp",
          (const char *)(unsigned int)v26,
          bIgnoreCaseb);
        goto LABEL_18;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (v8 & 0x80000000) != 0 )
      goto LABEL_18;
  }
  return 0;
}

```

## disassembly

```asm
0x180019380  push    rbp
0x180019382  push    rbx
0x180019383  push    rsi
0x180019384  push    rdi
0x180019385  push    r12
0x180019387  push    r13
0x180019389  push    r14
0x18001938b  push    r15
0x18001938d  lea     rbp, [rsp-198h]
0x180019395  sub     rsp, 298h
0x18001939c  mov     rax, cs:__security_cookie
0x1800193a3  xor     rax, rsp
0x1800193a6  mov     [rbp+1D0h+var_50], rax
0x1800193ad  mov     rax, [rcx+18h]
0x1800193b1  mov     rbx, rcx
0x1800193b4  mov     rcx, [rax+30h]
0x1800193b8  mov     rax, [rcx]
0x1800193bb  mov     rax, [rax+98h]
0x1800193c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193c7  mov     rdi, [rbx+18h]
0x1800193cb  lea     rcx, [rsp+2D0h+String2]; void *
0x1800193d0  mov     r14, rax
0x1800193d3  xor     edx, edx; Val
0x1800193d5  mov     rax, [rbx+78h]
0x1800193d9  mov     r8d, 208h; Size
0x1800193df  mov     [rsp+2D0h+lpString2], rax
0x1800193e4  mov     r15, [rdi+310h]
0x1800193eb  call    memset_0
0x1800193f0  xor     eax, eax
0x1800193f2  lea     rsi, aOnecoreAdminAp_59; "onecore\\admin\\appmodel\\packagereposi"...
0x1800193f9  mov     [rsp+2D0h+var_268], eax
0x1800193fd  xorps   xmm0, xmm0
0x180019400  movups  xmmword ptr [rsp+2D0h+var_278], xmm0
0x180019405  test    r15, r15
0x180019408  jz      loc_1800195A7
0x18001940e  mov     r12, [rbx+90h]
0x180019415  lea     rcx, [rsp+2D0h+UnicodeString]; UnicodeString
0x18001941a  mov     r13, [rdi+40h]
0x18001941e  mov     r8b, 1; AllocateDestinationString
0x180019421  mov     rdx, r15; Sid
0x180019424  movups  xmmword ptr [rsp+2D0h+UnicodeString.Length], xmm0
0x180019429  call    cs:__imp_RtlConvertSidToUnicodeString
0x180019430  nop     dword ptr [rax+rax+00h]
0x180019435  test    eax, eax
0x180019437  js      loc_180019765
0x18001943d  movzx   r8d, [rsp+2D0h+UnicodeString.Length]
0x180019443  lea     rcx, [rsp+2D0h+var_278]; this
0x180019448  mov     rdx, [rsp+2D0h+UnicodeString.Buffer]; unsigned __int16 *
0x18001944d  shr     r8d, 1; unsigned int
0x180019450  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x180019455  lea     rcx, [rsp+2D0h+UnicodeString]; UnicodeString
0x18001945a  mov     ebx, eax
0x18001945c  call    cs:__imp_RtlFreeUnicodeString
0x180019463  nop     dword ptr [rax+rax+00h]
0x180019468  test    ebx, ebx
0x18001946a  js      loc_1800195AC
0x180019470  mov     rdi, [rsp+2D0h+var_278+8]
0x180019475  lea     rax, aWindowsProtoco_0; "windows.protocol"
0x18001947c  mov     [rsp+2D0h+var_2A0], r12
0x180019481  lea     r8, aSI64dSS; "%s %I64d %s %s"
0x180019488  mov     [rsp+2D0h+var_2A8], rax
0x18001948d  lea     rcx, [rsp+2D0h+String2]; unsigned __int16 *
0x180019492  mov     r9, rdi
0x180019495  mov     qword ptr [rsp+2D0h+bIgnoreCase], r13; int
0x18001949a  mov     edx, 104h; unsigned __int64
0x18001949f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800194a4  mov     ebx, eax
0x1800194a6  test    eax, eax
0x1800194a8  js      loc_1800195DC
0x1800194ae  test    rdi, rdi
0x1800194b1  jz      short loc_1800194BB
0x1800194b3  mov     rcx, rdi; void *
0x1800194b6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800194bb  xor     ebx, ebx
0x1800194bd  or      r12d, 0FFFFFFFFh
0x1800194c1  cmp     rbx, [r14+10h]
0x1800194c5  jnb     short loc_18001950F
0x1800194c7  mov     rax, [r14]
0x1800194ca  mov     rdi, [rax+rbx*8]
0x1800194ce  test    rdi, rdi
0x1800194d1  jz      loc_180019614
0x1800194d7  mov     rcx, [rdi]; lpString1
0x1800194da  lea     r8, [rsp+2D0h+String2]; lpString2
0x1800194df  mov     r9d, r12d; cchCount2
0x1800194e2  mov     [rsp+2D0h+bIgnoreCase], 0; bIgnoreCase
0x1800194ea  mov     edx, r12d; cchCount1
0x1800194ed  call    cs:__imp_CompareStringOrdinal
0x1800194f4  nop     dword ptr [rax+rax+00h]
0x1800194f9  test    eax, eax
0x1800194fb  jz      loc_18001960A
0x180019501  cmp     eax, 2
0x180019504  jz      loc_18001962D
0x18001950a  inc     rbx
0x18001950d  jmp     short loc_1800194C1
0x18001950f  mov     ecx, 10h
0x180019514  call    cs:__imp_?PackageRepositoryAllocate@@YAPEAX_K@Z; PackageRepositoryAllocate(unsigned __int64)
0x18001951b  nop     dword ptr [rax+rax+00h]
0x180019520  mov     rdi, rax
0x180019523  test    rax, rax
0x180019526  jnz     loc_1800196BB
0x18001952c  mov     rcx, [rbp+1D8h]; this
0x180019533  mov     ebx, 8007000Eh
0x180019538  mov     r9d, ebx; char *
0x18001953b  mov     r8, rsi; unsigned int
0x18001953e  mov     edx, 89h; void *
0x180019543  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019548  xor     ecx, ecx
0x18001954a  call    ??$AutoPtrDeallocate@VPropertyBagKeyValuePair@PackageRepository@@@Common@@YAXPEAVPropertyBagKeyValuePair@PackageRepository@@@Z; Common::AutoPtrDeallocate<PackageRepository::PropertyBagKeyValuePair>(PackageRepository::PropertyBagKeyValuePair *)
0x18001954f  mov     edx, 0A8h; void *
0x180019554  mov     rcx, [rbp+1D8h]; this
0x18001955b  mov     r9d, ebx; char *
0x18001955e  mov     r8, rsi; unsigned int
0x180019561  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180019566  mov     rcx, [rbp+1D8h]; this
0x18001956d  lea     r8, aOnecoreAdminAp_153; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180019574  mov     r9d, ebx; char *
0x180019577  mov     edx, 21Ah; void *
0x18001957c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019581  mov     eax, ebx
0x180019583  mov     rcx, [rbp+1D0h+var_50]
0x18001958a  xor     rcx, rsp; StackCookie
0x18001958d  call    __security_check_cookie
0x180019592  add     rsp, 298h
0x180019599  pop     r15
0x18001959b  pop     r14
0x18001959d  pop     r13
0x18001959f  pop     r12
0x1800195a1  pop     rdi
0x1800195a2  pop     rsi
0x1800195a3  pop     rbx
0x1800195a4  pop     rbp
0x1800195a5  retn
0x1800195a7  mov     ebx, 80070057h
0x1800195ac  mov     rcx, [rbp+1D8h]; this
0x1800195b3  mov     r9d, ebx; char *
0x1800195b6  mov     r8, rsi; unsigned int
0x1800195b9  mov     edx, 0D0h; void *
0x1800195be  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800195c3  mov     rcx, [rsp+2D0h+var_278+8]; void *
0x1800195c8  test    rcx, rcx
0x1800195cb  jz      short loc_1800195D2
0x1800195cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800195d2  test    ebx, ebx
0x1800195d4  jns     loc_1800194BB
0x1800195da  jmp     short loc_180019600
0x1800195dc  mov     rcx, [rbp+1D8h]; this
0x1800195e3  mov     r9d, eax; char *
0x1800195e6  mov     r8, rsi; unsigned int
0x1800195e9  mov     edx, 0D2h; void *
0x1800195ee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800195f3  test    rdi, rdi
0x1800195f6  jz      short loc_180019600
0x1800195f8  mov     rcx, rdi; void *
0x1800195fb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019600  mov     edx, 0A6h
0x180019605  jmp     loc_180019554
0x18001960a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "compareResult != 0")
0x18001960f  jmp     loc_18001950A
0x180019614  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pair != nullptr")
0x180019619  jmp     loc_1800194D7
0x18001961e  test    ebx, ebx
0x180019620  js      loc_18001954F
0x180019626  xor     eax, eax
0x180019628  jmp     loc_180019583
0x18001962d  cmp     rbx, 40000000h
0x180019634  jz      loc_18001950F
0x18001963a  cmp     rbx, [r14+10h]
0x18001963e  jb      short loc_1800196AF
0x180019640  xor     ecx, ecx
0x180019642  mov     r15, [rsp+2D0h+lpString2]
0x180019647  mov     r9d, r12d; cchCount2
0x18001964a  mov     rcx, [rcx+8]; lpString1
0x18001964e  mov     r8, r15; lpString2
0x180019651  mov     edx, r12d; cchCount1
0x180019654  mov     [rsp+2D0h+bIgnoreCase], 0; int
0x18001965c  call    cs:__imp_CompareStringOrdinal
0x180019663  nop     dword ptr [rax+rax+00h]
0x180019668  test    eax, eax
0x18001966a  jz      loc_180019735
0x180019670  cmp     eax, 2
0x180019673  jz      short loc_180019626
0x180019675  cmp     rbx, [r14+10h]
0x180019679  jb      loc_180019759
0x18001967f  xor     ecx, ecx
0x180019681  add     rcx, 8; unsigned __int16 **
0x180019685  mov     rdx, r15; unsigned __int16 *
0x180019688  call    ?Set@PropertyBagKeyValuePair@PackageRepository@@CAJAEAPEBGPEBG@Z; PackageRepository::PropertyBagKeyValuePair::Set(ushort const * &,ushort const *)
0x18001968d  mov     ebx, eax
0x18001968f  test    eax, eax
0x180019691  jns     short loc_180019626
0x180019693  mov     rcx, [rbp+1D8h]; this
0x18001969a  mov     r9d, eax; char *
0x18001969d  mov     r8, rsi; unsigned int
0x1800196a0  mov     edx, 9Ah; void *
0x1800196a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800196aa  jmp     loc_18001954F
0x1800196af  lfence
0x1800196b2  mov     rax, [r14]
0x1800196b5  mov     rcx, [rax+rbx*8]
0x1800196b9  jmp     short loc_180019642
0x1800196bb  lea     rdx, [rsp+2D0h+String2]; unsigned __int16 *
0x1800196c0  mov     qword ptr [rax], 0
0x1800196c7  mov     rcx, rdi; unsigned __int16 **
0x1800196ca  mov     qword ptr [rax+8], 0
0x1800196d2  call    ?Set@PropertyBagKeyValuePair@PackageRepository@@CAJAEAPEBGPEBG@Z; PackageRepository::PropertyBagKeyValuePair::Set(ushort const * &,ushort const *)
0x1800196d7  mov     ebx, eax
0x1800196d9  test    eax, eax
0x1800196db  js      loc_180019787
0x1800196e1  mov     rdx, [rsp+2D0h+lpString2]; unsigned __int16 *
0x1800196e6  lea     rcx, [rdi+8]; unsigned __int16 **
0x1800196ea  call    ?Set@PropertyBagKeyValuePair@PackageRepository@@CAJAEAPEBGPEBG@Z; PackageRepository::PropertyBagKeyValuePair::Set(ushort const * &,ushort const *)
0x1800196ef  mov     ebx, eax
0x1800196f1  test    eax, eax
0x1800196f3  js      short loc_180019716
0x1800196f5  mov     rdx, rdi
0x1800196f8  mov     rcx, r14
0x1800196fb  call    ?Add@?$Array@VPropertyBagKeyValuePair@PackageRepository@@V?$ContainerOperations@VPropertyBagKeyValuePair@PackageRepository@@V12@@Common@@GV?$ContainerOperations@GVPropertyBagKeyValuePair@PackageRepository@@@4@V?$ArrayOperations@VPropertyBagKeyValuePair@PackageRepository@@V12@@4@@Common@@QEAAJPEAVPropertyBagKeyValuePair@PackageRepository@@@Z; Common::Array<PackageRepository::PropertyBagKeyValuePair,Common::ContainerOperations<PackageRepository::PropertyBagKeyValuePair,PackageRepository::PropertyBagKeyValuePair>,ushort,Common::ContainerOperations<ushort,PackageRepository::PropertyBagKeyValuePair>,Common::ArrayOperations<PackageRepository::PropertyBagKeyValuePair,PackageRepository::PropertyBagKeyValuePair>>::Add(PackageRepository::PropertyBagKeyValuePair *)
0x180019700  mov     ebx, eax
0x180019702  test    eax, eax
0x180019704  js      loc_18001978E
0x18001970a  xor     ecx, ecx
0x18001970c  call    ??$AutoPtrDeallocate@VPropertyBagKeyValuePair@PackageRepository@@@Common@@YAXPEAVPropertyBagKeyValuePair@PackageRepository@@@Z; Common::AutoPtrDeallocate<PackageRepository::PropertyBagKeyValuePair>(PackageRepository::PropertyBagKeyValuePair *)
0x180019711  jmp     loc_180019626
0x180019716  mov     edx, 8Ch; void *
0x18001971b  mov     rcx, [rbp+1D8h]; this
0x180019722  mov     r9d, eax; char *
0x180019725  mov     r8, rsi; unsigned int
0x180019728  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001972d  mov     rcx, rdi
0x180019730  jmp     loc_18001954A
0x180019735  call    cs:__imp_GetLastError
0x18001973c  nop     dword ptr [rax+rax+00h]
0x180019741  mov     ebx, eax
0x180019743  test    eax, eax
0x180019745  jle     loc_18001961E
0x18001974b  movzx   ebx, ax
0x18001974e  or      ebx, 80070000h
0x180019754  jmp     loc_18001961E
0x180019759  mov     rax, [r14]
0x18001975c  mov     rcx, [rax+rbx*8]
0x180019760  jmp     loc_180019681
0x180019765  mov     rcx, [rbp+1D8h]; this
0x18001976c  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\common\\sidhel"...
0x180019773  mov     r9d, eax; char *
0x180019776  mov     edx, 1Eh; void *
0x18001977b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180019780  mov     ebx, eax
0x180019782  jmp     loc_180019468
0x180019787  mov     edx, 8Bh
0x18001978c  jmp     short loc_18001971B
0x18001978e  mov     edx, 8Eh
0x180019793  jmp     short loc_18001971B
```
