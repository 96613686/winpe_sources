# CCbsInprocIStream::UnmarshalObject(_GUID const &,void * *)

- ea: `0x140020ae8`
- end: `0x140020c7b`
- name: `?UnmarshalObject@CCbsInprocIStream@@QEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `403`
- prototype: `int(CCbsInprocIStream *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000ca98`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x140020ae8`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x140020c02`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x140020c02`

## string_xrefs

- `0x140020b63`: `onecore\base\cbs\util\cbscom.cpp`

## pseudocode

```c
__int64 __fastcall CCbsInprocIStream::UnmarshalObject(CCbsInprocIStream *this, const struct _GUID *a2, void **a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  struct CCbsInprocIStream *v8; // rsi
  int v9; // eax
  __int64 v10; // rdx
  HRESULT v11; // eax
  __int64 v12; // rdx
  int v13; // [rsp+20h] [rbp-38h]
  int v14[2]; // [rsp+30h] [rbp-28h] BYREF
  int v15; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]

  if ( !a3 )
  {
    v4 = -2147467261;
    v15 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No object result specified");
      *(_QWORD *)v14 = &v15;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v14);
    }
    v6 = 106;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\util\\cbscom.cpp",
      (const char *)v4,
      v13);
    return v4;
  }
  v8 = vpCbsWorkerStream;
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)vpCbsWorkerStream + 3) + 40LL))(
         *((_QWORD *)vpCbsWorkerStream + 3),
         0,
         0,
         0);
  v4 = v9;
  if ( v9 < 0 )
  {
    v15 = v9;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to seek stream.");
      *(_QWORD *)v14 = &v15;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v10,
        3,
        (__int64)": {}",
        (__int64)v14);
    }
    v6 = 109;
    goto LABEL_5;
  }
  v11 = CoUnmarshalInterface(*((LPSTREAM *)v8 + 3), &GUID_a70dbecc_3734_4b22_b2d1_648c0e43e177, a3);
  v4 = v11;
  if ( v11 < 0 )
  {
    v15 = v11;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to unmarshall worker stream");
      *(_QWORD *)v14 = &v15;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v12,
        3,
        (__int64)": {}",
        (__int64)v14);
    }
    v6 = 111;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x140020ae8  push    rbp
0x140020aea  push    rbx
0x140020aeb  push    rsi
0x140020aec  push    rdi
0x140020aed  mov     rbp, rsp
0x140020af0  sub     rsp, 58h
0x140020af4  mov     rax, cs:__security_cookie
0x140020afb  xor     rax, rsp
0x140020afe  mov     [rbp+var_18], rax
0x140020b02  mov     rdi, r8
0x140020b05  test    r8, r8
0x140020b08  jnz     short loc_140020B79
0x140020b0a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020b11  mov     ebx, 80004003h
0x140020b16  mov     [rbp+var_20], ebx
0x140020b19  test    rcx, rcx
0x140020b1c  jz      short loc_140020B5A
0x140020b1e  lea     edi, [r8+3]
0x140020b22  xor     edx, edx
0x140020b24  mov     r8d, edi
0x140020b27  lea     r9, aNoObjectResult; "No object result specified"
0x140020b2e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140020b33  lea     rcx, [rbp+var_28]
0x140020b37  mov     r8d, edi
0x140020b3a  mov     qword ptr [rsp+58h+var_38], rcx; int
0x140020b3f  lea     rax, [rbp+var_20]
0x140020b43  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020b4a  lea     r9, asc_1400353E8; ": {}"
0x140020b51  mov     qword ptr [rbp+var_28], rax
0x140020b55  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020b5a  mov     edx, 6Ah ; 'j'; void *
0x140020b5f  mov     rcx, [rbp+20h]; this
0x140020b63  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\util\\cbscom.cpp"
0x140020b6a  mov     r9d, ebx; char *
0x140020b6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140020b72  mov     eax, ebx
0x140020b74  jmp     loc_140020C66
0x140020b79  mov     rsi, cs:?vpCbsWorkerStream@@3PEAVCCbsInprocIStream@@EA; CCbsInprocIStream * vpCbsWorkerStream
0x140020b80  xor     edx, edx
0x140020b82  xor     r9d, r9d
0x140020b85  xor     r8d, r8d
0x140020b88  mov     rcx, [rsi+18h]
0x140020b8c  mov     rax, [rcx]
0x140020b8f  mov     rax, [rax+28h]
0x140020b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020b98  mov     ebx, eax
0x140020b9a  test    eax, eax
0x140020b9c  jns     short loc_140020BF4
0x140020b9e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020ba5  mov     [rbp+var_20], eax
0x140020ba8  test    rcx, rcx
0x140020bab  jz      short loc_140020BEA
0x140020bad  mov     edi, 3
0x140020bb2  lea     r9, aFailedToSeekSt; "Failed to seek stream."
0x140020bb9  mov     r8d, edi
0x140020bbc  xor     edx, edx
0x140020bbe  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140020bc3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020bca  lea     rax, [rbp+var_20]
0x140020bce  mov     qword ptr [rbp+var_28], rax
0x140020bd2  lea     r9, asc_1400353E8; ": {}"
0x140020bd9  lea     rax, [rbp+var_28]
0x140020bdd  mov     r8d, edi
0x140020be0  mov     qword ptr [rsp+58h+var_38], rax
0x140020be5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020bea  mov     edx, 6Dh ; 'm'
0x140020bef  jmp     loc_140020B5F
0x140020bf4  mov     rcx, [rsi+18h]; pStm
0x140020bf8  lea     rdx, _GUID_a70dbecc_3734_4b22_b2d1_648c0e43e177; riid
0x140020bff  mov     r8, rdi; ppv
0x140020c02  call    cs:__imp_CoUnmarshalInterface
0x140020c08  mov     ebx, eax
0x140020c0a  test    eax, eax
0x140020c0c  jns     short loc_140020C64
0x140020c0e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020c15  mov     [rbp+var_20], eax
0x140020c18  test    rcx, rcx
0x140020c1b  jz      short loc_140020C5A
0x140020c1d  mov     edi, 3
0x140020c22  lea     r9, aFailedToUnmars; "Failed to unmarshall worker stream"
0x140020c29  mov     r8d, edi
0x140020c2c  xor     edx, edx
0x140020c2e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140020c33  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020c3a  lea     rax, [rbp+var_20]
0x140020c3e  mov     qword ptr [rbp+var_28], rax
0x140020c42  lea     r9, asc_1400353E8; ": {}"
0x140020c49  lea     rax, [rbp+var_28]
0x140020c4d  mov     r8d, edi
0x140020c50  mov     qword ptr [rsp+58h+var_38], rax
0x140020c55  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020c5a  mov     edx, 6Fh ; 'o'
0x140020c5f  jmp     loc_140020B5F
0x140020c64  xor     eax, eax
0x140020c66  mov     rcx, [rbp+var_18]
0x140020c6a  xor     rcx, rsp; StackCookie
0x140020c6d  call    __security_check_cookie
0x140020c72  add     rsp, 58h
0x140020c76  pop     rdi
0x140020c77  pop     rsi
0x140020c78  pop     rbx
0x140020c79  pop     rbp
0x140020c7a  retn
```
