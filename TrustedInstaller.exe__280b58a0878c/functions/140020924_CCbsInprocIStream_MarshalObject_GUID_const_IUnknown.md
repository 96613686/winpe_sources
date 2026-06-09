# CCbsInprocIStream::MarshalObject(_GUID const &,IUnknown *)

- ea: `0x140020924`
- end: `0x140020ae1`
- name: `?MarshalObject@CCbsInprocIStream@@QEAAJAEBU_GUID@@PEAUIUnknown@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(CCbsInprocIStream *this, const struct _GUID *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000ca98`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x140020924`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1400209ca`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1400209ca`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x140020a50`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x140020a50`

## string_xrefs

- `0x1400209a9`: `onecore\base\cbs\util\cbscom.cpp`
- `0x140020966`: `Object already has a defined stream`
- `0x1400209e7`: `Failed to create stream.`
- `0x140020a85`: `Failed to marshall update session.`

## pseudocode

```c
__int64 __fastcall CCbsInprocIStream::MarshalObject(
        CCbsInprocIStream *this,
        const struct _GUID *a2,
        struct IUnknown *a3)
{
  struct CCbsInprocIStream *v3; // rdi
  HRESULT v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdx
  HRESULT StreamOnHGlobal; // eax
  __int64 v10; // rdx
  struct LogAdapter::Logger *v11; // rcx
  __int64 v12; // rdx
  int pvDestContext; // [rsp+20h] [rbp-38h]
  int v14[2]; // [rsp+30h] [rbp-28h] BYREF
  int v15; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]

  v3 = vpCbsWorkerStream;
  if ( *((_QWORD *)vpCbsWorkerStream + 3) )
  {
    v5 = -2146498560;
    v15 = -2146498560;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Object already has a defined stream");
      *(_QWORD *)v14 = &v15;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v6,
        3,
        (__int64)": {}",
        (__int64)v14);
    }
    v7 = 89;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\cbs\\util\\cbscom.cpp",
      (const char *)(unsigned int)v5,
      pvDestContext);
    return (unsigned int)v5;
  }
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, (LPSTREAM *)vpCbsWorkerStream + 3);
  v5 = StreamOnHGlobal;
  if ( StreamOnHGlobal < 0 )
  {
    v15 = StreamOnHGlobal;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create stream.");
      *(_QWORD *)v14 = &v15;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v10,
        3,
        (__int64)": {}",
        (__int64)v14);
    }
    v7 = 91;
    goto LABEL_5;
  }
  v5 = CoMarshalInterface(*((LPSTREAM *)v3 + 3), &GUID_a70dbecc_3734_4b22_b2d1_648c0e43e177, a3, 3u, 0, 1u);
  if ( v5 < 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 3) + 16LL))(*((_QWORD *)v3 + 3));
    v11 = LogAdapter::g_Logger;
    *((_QWORD *)v3 + 3) = 0;
    v15 = v5;
    if ( v11 )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)v11,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to marshall update session.");
      *(_QWORD *)v14 = &v15;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v12,
        3,
        (__int64)": {}",
        (__int64)v14);
    }
    v7 = 98;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x140020924  push    rbp
0x140020926  push    rbx
0x140020927  push    rdi
0x140020928  push    r14
0x14002092a  mov     rbp, rsp
0x14002092d  sub     rsp, 58h
0x140020931  mov     rax, cs:__security_cookie
0x140020938  xor     rax, rsp
0x14002093b  mov     [rbp+var_18], rax
0x14002093f  mov     rdi, cs:?vpCbsWorkerStream@@3PEAVCCbsInprocIStream@@EA; CCbsInprocIStream * vpCbsWorkerStream
0x140020946  mov     r14, r8
0x140020949  cmp     qword ptr [rdi+18h], 0
0x14002094e  jz      short loc_1400209BF
0x140020950  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020957  mov     ebx, 800F0800h
0x14002095c  mov     [rbp+var_20], ebx
0x14002095f  test    rcx, rcx
0x140020962  jz      short loc_1400209A0
0x140020964  xor     edx, edx
0x140020966  lea     r9, aObjectAlreadyH; "Object already has a defined stream"
0x14002096d  lea     r8d, [rdx+3]
0x140020971  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140020976  lea     rcx, [rbp+var_28]
0x14002097a  mov     r8d, 3
0x140020980  mov     [rsp+58h+pvDestContext], rcx; int
0x140020985  lea     rax, [rbp+var_20]
0x140020989  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020990  lea     r9, asc_1400353E8; ": {}"
0x140020997  mov     qword ptr [rbp+var_28], rax
0x14002099b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400209a0  mov     edx, 59h ; 'Y'; void *
0x1400209a5  mov     rcx, [rbp+20h]; this
0x1400209a9  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\util\\cbscom.cpp"
0x1400209b0  mov     r9d, ebx; char *
0x1400209b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400209b8  mov     eax, ebx
0x1400209ba  jmp     loc_140020ACB
0x1400209bf  lea     r8, [rdi+18h]; ppstm
0x1400209c3  mov     edx, 1; fDeleteOnRelease
0x1400209c8  xor     ecx, ecx; hGlobal
0x1400209ca  call    cs:__imp_CreateStreamOnHGlobal
0x1400209d0  mov     ebx, eax
0x1400209d2  test    eax, eax
0x1400209d4  jns     short loc_140020A2B
0x1400209d6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400209dd  mov     [rbp+var_20], eax
0x1400209e0  test    rcx, rcx
0x1400209e3  jz      short loc_140020A21
0x1400209e5  xor     edx, edx
0x1400209e7  lea     r9, aFailedToCreate_11; "Failed to create stream."
0x1400209ee  lea     r8d, [rdx+3]
0x1400209f2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400209f7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400209fe  lea     rax, [rbp+var_20]
0x140020a02  mov     qword ptr [rbp+var_28], rax
0x140020a06  lea     r9, asc_1400353E8; ": {}"
0x140020a0d  lea     rax, [rbp+var_28]
0x140020a11  mov     r8d, 3
0x140020a17  mov     [rsp+58h+pvDestContext], rax
0x140020a1c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020a21  mov     edx, 5Bh ; '['
0x140020a26  jmp     loc_1400209A5
0x140020a2b  mov     rcx, [rdi+18h]; pStm
0x140020a2f  lea     rdx, _GUID_a70dbecc_3734_4b22_b2d1_648c0e43e177; riid
0x140020a36  mov     [rsp+58h+mshlflags], 1; mshlflags
0x140020a3e  mov     r9d, 3; dwDestContext
0x140020a44  mov     r8, r14; pUnk
0x140020a47  mov     [rsp+58h+pvDestContext], 0; pvDestContext
0x140020a50  call    cs:__imp_CoMarshalInterface
0x140020a56  mov     ebx, eax
0x140020a58  test    eax, eax
0x140020a5a  jns     short loc_140020AC9
0x140020a5c  mov     rcx, [rdi+18h]
0x140020a60  mov     rdx, [rcx]
0x140020a63  mov     rax, [rdx+10h]
0x140020a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020a6c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020a73  mov     qword ptr [rdi+18h], 0
0x140020a7b  mov     [rbp+var_20], ebx
0x140020a7e  test    rcx, rcx
0x140020a81  jz      short loc_140020ABF
0x140020a83  xor     edx, edx
0x140020a85  lea     r9, aFailedToMarsha_1; "Failed to marshall update session."
0x140020a8c  lea     r8d, [rdx+3]
0x140020a90  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140020a95  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020a9c  lea     rax, [rbp+var_20]
0x140020aa0  mov     qword ptr [rbp+var_28], rax
0x140020aa4  lea     r9, asc_1400353E8; ": {}"
0x140020aab  lea     rax, [rbp+var_28]
0x140020aaf  mov     r8d, 3
0x140020ab5  mov     [rsp+58h+pvDestContext], rax
0x140020aba  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020abf  mov     edx, 62h ; 'b'
0x140020ac4  jmp     loc_1400209A5
0x140020ac9  xor     eax, eax
0x140020acb  mov     rcx, [rbp+var_18]
0x140020acf  xor     rcx, rsp; StackCookie
0x140020ad2  call    __security_check_cookie
0x140020ad7  add     rsp, 58h
0x140020adb  pop     r14
0x140020add  pop     rdi
0x140020ade  pop     rbx
0x140020adf  pop     rbp
0x140020ae0  retn
```
