# win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close(win_musl::ByteReceiverUnique<win_musl::consumption::ZipEndOfCentralDirectoryConsumer,0,IUnknown> &)

- ea: `0x180007428`
- end: `0x1800079d2`
- name: `?Close@ZipEndOfCentralDirectoryConsumer@consumption@win_musl@@QEAAXAEAV?$ByteReceiverUnique@VZipEndOfCentralDirectoryConsumer@consumption@win_musl@@$0A@UIUnknown@@@3@@Z`
- size: `1450`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180085634`

## callees

- `0x180007428`
- `0x1800079d8`
- `0x180007b44`
- `0x180007cac`
- `0x18000b7e4`
- `0x180015af4`
- `0x1800517a0`
- `0x1800cb784`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x1801148a8`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180007735`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180007735`

## string_xrefs

- `0x1800074c5`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryconsumer.cpp`
- `0x1800075d5`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryconsumer.cpp`
- `0x180007611`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryconsumer.cpp`
- `0x180007652`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryconsumer.cpp`
- `0x1800074b6`: `win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close`
- `0x180007646`: `win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close`
- `0x1800075c6`: `sizeCentralDirectory`
- `0x18000763f`: `_bytesNeededComment`
- `0x180007506`: `diskNumberDirectoryStart`
- `0x180007549`: `directoryEntriesCountThisDisk`
- `0x180007602`: `offsetCentralDirectory`
- `0x180007945`: `invalid end_of_central_directory source value!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close(
        win_musl::consumption::ZipEndOfCentralDirectoryConsumer *this)
{
  __int64 v2; // rcx
  unsigned __int16 Then; // ax
  int v4; // r14d
  unsigned __int16 v5; // ax
  int v6; // esi
  __int16 v7; // bx
  unsigned __int16 v8; // ax
  __int64 v9; // r15
  __int64 v10; // rbx
  __int64 v11; // r12
  __int64 v12; // rdx
  int v13; // ecx
  __int128 v14; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h]
  _QWORD pExceptionObject[3]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v18[2]; // [rsp+88h] [rbp-78h] BYREF
  const char *v19; // [rsp+90h] [rbp-70h]
  _BYTE v20[56]; // [rsp+98h] [rbp-68h] BYREF
  GUID v21; // [rsp+D0h] [rbp-30h]
  int v22; // [rsp+F8h] [rbp-8h]

  v16 = -2;
  v2 = *((_QWORD *)this + 8);
  if ( !v2 || *((_QWORD *)this + 9) - v2 != 18 )
  {
    win_musl::DebugLogHelper("(no filename)", &word_18013A0B6, 158, 1024, -2142171135, L"Wrong number of bytes sent");
    *(_QWORD *)&v14 = "Unexpected HRESULT returned by API";
    exception::exception((exception *)pExceptionObject, (const char *const *)&v14);
    memset_0(v20, 0, 0x68u);
    v19 = "(no filename)";
    v18[1] = 158;
    v22 = -1;
    pExceptionObject[0] = &SplException::THResultException::`vftable';
    v18[0] = -2142171135;
    v21 = GUID_NULL;
    if ( SplException::Functions )
      v22 = SplException::Functions(v18);
    throw (SplException::THResultException *)pExceptionObject;
  }
  *(_QWORD *)&v14 = 18;
  *((_QWORD *)&v14 + 1) = v2;
  v15 = v14;
  Then = win_musl::detail::readThenLog<unsigned short>(
           (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentrald"
                         "irectoryconsumer.cpp",
           168,
           (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close",
           (unsigned int)"diskNumberThis",
           (__int64)&v15,
           (__int64)&v14);
  v4 = Then;
  if ( Then && Then != 0xFFFF )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xACu,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Archive feature not supported: only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v15 = v14;
  v5 = win_musl::detail::readThenLog<unsigned short>(
         (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldir"
                       "ectoryconsumer.cpp",
         178,
         (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close",
         (unsigned int)"diskNumberDirectoryStart",
         (__int64)&v15,
         (__int64)&v14);
  v6 = v5;
  if ( v5 && v5 != 0xFFFF )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xB6u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Archive feature not supported: only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v15 = v14;
  v7 = win_musl::detail::readThenLog<unsigned short>(
         (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldir"
                       "ectoryconsumer.cpp",
         188,
         (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close",
         (unsigned int)"directoryEntriesCountThisDisk",
         (__int64)&v15,
         (__int64)&v14);
  v15 = v14;
  v8 = win_musl::detail::readThenLog<unsigned short>(
         (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldir"
                       "ectoryconsumer.cpp",
         193,
         (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close",
         (unsigned int)"countEntries",
         (__int64)&v15,
         (__int64)&v14);
  v9 = v8;
  if ( v7 != v8 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xC5u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Archive feature not supported: only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v15 = v14;
  v10 = (unsigned int)win_musl::detail::readThenLog<unsigned int>(
                        (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zip"
                                      "endofcentraldirectoryconsumer.cpp",
                        202,
                        (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close",
                        (unsigned int)"sizeCentralDirectory",
                        (__int64)&v15,
                        (__int64)&v14);
  v15 = v14;
  v11 = (unsigned int)win_musl::detail::readThenLog<unsigned int>(
                        (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zip"
                                      "endofcentraldirectoryconsumer.cpp",
                        208,
                        (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close",
                        (unsigned int)"offsetCentralDirectory",
                        (__int64)&v15,
                        (__int64)&v14);
  v15 = v14;
  *((_WORD *)this + 44) = win_musl::detail::readThenLog<unsigned short>(
                            (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\"
                                          "zipendofcentraldirectoryconsumer.cpp",
                            211,
                            (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close",
                            (unsigned int)"_bytesNeededComment",
                            (__int64)&v15,
                            (__int64)&v14);
  v12 = *((_QWORD *)this + 4);
  v13 = *(_DWORD *)(v12 + 128);
  if ( !v13 )
  {
    *(_DWORD *)(v12 + 128) = 1;
    *(_QWORD *)(*((_QWORD *)this + 4) + 152LL) = v11;
    *(_QWORD *)(*((_QWORD *)this + 4) + 144LL) = v10;
    *(_QWORD *)(*((_QWORD *)this + 4) + 136LL) = v9;
    *(_DWORD *)(*((_QWORD *)this + 4) + 168LL) = v4;
LABEL_8:
    *(_DWORD *)(*((_QWORD *)this + 4) + 172LL) = v6;
    goto LABEL_9;
  }
  if ( v13 != 2 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x110u,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"invalid end_of_central_directory source value!");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( (_DWORD)v11 != -1 )
    *(_QWORD *)(v12 + 152) = v11;
  if ( (_DWORD)v10 != -1 )
    *(_QWORD *)(*((_QWORD *)this + 4) + 144LL) = v10;
  if ( (_WORD)v9 != 0xFFFF )
    *(_QWORD *)(*((_QWORD *)this + 4) + 136LL) = v9;
  if ( (_WORD)v4 != 0xFFFF )
    *(_DWORD *)(*((_QWORD *)this + 4) + 168LL) = v4;
  if ( (_WORD)v6 != 0xFFFF )
    goto LABEL_8;
LABEL_9:
  if ( *((_WORD *)this + 44) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
      WPP_SF_ID(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        12,
        WPP_37a605dc7fd83120dddcbd48d857a9dd_Traceguids,
        *((_QWORD *)this + 6),
        *((unsigned __int16 *)this + 44));
    *(_QWORD *)&v15 = *((_QWORD *)this + 6);
    *((_QWORD *)&v15 + 1) = v15 + *((unsigned __int16 *)this + 44);
    win_dox::ByteCollection::CreateSenderOfRange(*((_QWORD *)this + 4) + 104LL, &v14, &v15);
    win_musl::consumption::ZipEndOfCentralDirectoryConsumer::ProcessCommentByteSender(
      this,
      (struct win_dox::ByteSender *)&v14);
    *(_QWORD *)&v14 = &win_dox::OpcRelationshipSender::`vftable';
    if ( *((_QWORD *)&v14 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v14 + 1) + 16LL))(*((_QWORD *)&v14 + 1));
  }
  else
  {
    win_musl::consumption::ZipEndOfCentralDirectoryConsumer::ReportComment(this);
  }
}

```

## disassembly

```asm
0x180007428  push    rbp
0x18000742a  push    rbx
0x18000742b  push    rsi
0x18000742c  push    rdi
0x18000742d  push    r12
0x18000742f  push    r13
0x180007431  push    r14
0x180007433  push    r15
0x180007435  lea     rbp, [rsp-28h]
0x18000743a  sub     rsp, 128h
0x180007441  mov     [rsp+160h+var_100], 0FFFFFFFFFFFFFFFEh
0x18000744a  mov     rax, cs:__security_cookie
0x180007451  xor     rax, rsp
0x180007454  mov     [rbp+60h+var_50], rax
0x180007458  mov     rdi, rcx
0x18000745b  xor     r13d, r13d
0x18000745e  mov     rcx, [rcx+40h]
0x180007462  test    rcx, rcx
0x180007465  jz      loc_1800076E7
0x18000746b  mov     rax, [rdi+48h]
0x18000746f  sub     rax, rcx
0x180007472  cmp     rax, 12h
0x180007476  jnz     loc_1800076E7
0x18000747c  mov     dword ptr [rsp+160h+var_120], eax
0x180007480  xor     eax, eax
0x180007482  mov     dword ptr [rsp+160h+var_120+4], eax
0x180007486  mov     qword ptr [rsp+160h+var_120+8], rcx
0x18000748b  movaps  xmm0, [rsp+160h+var_120]
0x180007490  movaps  [rsp+160h+var_120], xmm0
0x180007495  movdqa  [rsp+160h+var_110], xmm0
0x18000749b  lea     rax, [rsp+160h+var_120]
0x1800074a0  mov     qword ptr [rsp+160h+var_138], rax
0x1800074a5  lea     rax, [rsp+160h+var_110]
0x1800074aa  mov     qword ptr [rsp+160h+var_140], rax
0x1800074af  lea     r9, aDisknumberthis; "diskNumberThis"
0x1800074b6  lea     r12, aWinMuslConsump_9; "win_musl::consumption::ZipEndOfCentralD"...
0x1800074bd  mov     r8, r12
0x1800074c0  mov     edx, 0A8h
0x1800074c5  lea     r15, aOnecorePrintsc_5; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x1800074cc  mov     rcx, r15
0x1800074cf  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x1800074d4  movzx   r14d, ax
0x1800074d8  mov     ebx, 0FFFFh
0x1800074dd  cmp     r13w, r14w
0x1800074e1  jnz     loc_180007803
0x1800074e7  movaps  xmm0, [rsp+160h+var_120]
0x1800074ec  movdqa  [rsp+160h+var_110], xmm0
0x1800074f2  lea     rax, [rsp+160h+var_120]
0x1800074f7  mov     qword ptr [rsp+160h+var_138], rax
0x1800074fc  lea     rax, [rsp+160h+var_110]
0x180007501  mov     qword ptr [rsp+160h+var_140], rax
0x180007506  lea     r9, aDisknumberdire; "diskNumberDirectoryStart"
0x18000750d  mov     r8, r12
0x180007510  mov     edx, 0B2h
0x180007515  mov     rcx, r15
0x180007518  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18000751d  movzx   esi, ax
0x180007520  cmp     r13w, si
0x180007524  jnz     loc_180007853
0x18000752a  movaps  xmm0, [rsp+160h+var_120]
0x18000752f  movdqa  [rsp+160h+var_110], xmm0
0x180007535  lea     rax, [rsp+160h+var_120]
0x18000753a  mov     qword ptr [rsp+160h+var_138], rax
0x18000753f  lea     rax, [rsp+160h+var_110]
0x180007544  mov     qword ptr [rsp+160h+var_140], rax
0x180007549  lea     r9, aDirectoryentri; "directoryEntriesCountThisDisk"
0x180007550  mov     r8, r12
0x180007553  mov     edx, 0BCh
0x180007558  mov     rcx, r15
0x18000755b  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180007560  movzx   ebx, ax
0x180007563  movaps  xmm0, [rsp+160h+var_120]
0x180007568  movdqa  [rsp+160h+var_110], xmm0
0x18000756e  lea     rax, [rsp+160h+var_120]
0x180007573  mov     qword ptr [rsp+160h+var_138], rax
0x180007578  lea     rax, [rsp+160h+var_110]
0x18000757d  mov     qword ptr [rsp+160h+var_140], rax
0x180007582  lea     r9, aCountentries; "countEntries"
0x180007589  mov     r8, r12
0x18000758c  mov     edx, 0C1h
0x180007591  mov     rcx, r15
0x180007594  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180007599  movzx   r15d, ax
0x18000759d  cmp     bx, r15w
0x1800075a1  jnz     loc_1800078A2
0x1800075a7  movaps  xmm0, [rsp+160h+var_120]
0x1800075ac  movdqa  [rsp+160h+var_110], xmm0
0x1800075b2  lea     rax, [rsp+160h+var_120]
0x1800075b7  mov     qword ptr [rsp+160h+var_138], rax
0x1800075bc  lea     rax, [rsp+160h+var_110]
0x1800075c1  mov     qword ptr [rsp+160h+var_140], rax
0x1800075c6  lea     r9, aSizecentraldir; "sizeCentralDirectory"
0x1800075cd  mov     r8, r12
0x1800075d0  mov     edx, 0CAh
0x1800075d5  lea     rcx, aOnecorePrintsc_5; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x1800075dc  call    ??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x1800075e1  mov     ebx, eax
0x1800075e3  movaps  xmm0, [rsp+160h+var_120]
0x1800075e8  movdqa  [rsp+160h+var_110], xmm0
0x1800075ee  lea     rax, [rsp+160h+var_120]
0x1800075f3  mov     qword ptr [rsp+160h+var_138], rax
0x1800075f8  lea     rax, [rsp+160h+var_110]
0x1800075fd  mov     qword ptr [rsp+160h+var_140], rax
0x180007602  lea     r9, aOffsetcentrald; "offsetCentralDirectory"
0x180007609  mov     r8, r12
0x18000760c  mov     edx, 0D0h
0x180007611  lea     rcx, aOnecorePrintsc_5; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x180007618  call    ??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18000761d  mov     r12d, eax
0x180007620  movaps  xmm0, [rsp+160h+var_120]
0x180007625  movdqa  [rsp+160h+var_110], xmm0
0x18000762b  lea     rax, [rsp+160h+var_120]
0x180007630  mov     qword ptr [rsp+160h+var_138], rax
0x180007635  lea     rax, [rsp+160h+var_110]
0x18000763a  mov     qword ptr [rsp+160h+var_140], rax
0x18000763f  lea     r9, aBytesneededcom; "_bytesNeededComment"
0x180007646  lea     r8, aWinMuslConsump_9; "win_musl::consumption::ZipEndOfCentralD"...
0x18000764d  mov     edx, 0D3h
0x180007652  lea     rcx, aOnecorePrintsc_5; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x180007659  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18000765e  mov     [rdi+58h], ax
0x180007662  mov     rdx, [rdi+20h]
0x180007666  mov     ecx, [rdx+80h]
0x18000766c  test    ecx, ecx
0x18000766e  jnz     loc_1800078E8
0x180007674  mov     dword ptr [rdx+80h], 1
0x18000767e  mov     rax, [rdi+20h]
0x180007682  mov     [rax+98h], r12
0x180007689  mov     rax, [rdi+20h]
0x18000768d  mov     [rax+90h], rbx
0x180007694  mov     rax, [rdi+20h]
0x180007698  mov     [rax+88h], r15
0x18000769f  mov     rax, [rdi+20h]
0x1800076a3  mov     [rax+0A8h], r14d
0x1800076aa  mov     rax, [rdi+20h]
0x1800076ae  mov     [rax+0ACh], esi
0x1800076b4  cmp     [rdi+58h], r13w
0x1800076b9  jnz     loc_18000798B
0x1800076bf  mov     rcx, rdi; this
0x1800076c2  call    ?ReportComment@ZipEndOfCentralDirectoryConsumer@consumption@win_musl@@AEAAXXZ; win_musl::consumption::ZipEndOfCentralDirectoryConsumer::ReportComment(void)
0x1800076c7  mov     rcx, [rbp+60h+var_50]
0x1800076cb  xor     rcx, rsp; StackCookie
0x1800076ce  call    __security_check_cookie
0x1800076d3  add     rsp, 128h
0x1800076da  pop     r15
0x1800076dc  pop     r14
0x1800076de  pop     r13
0x1800076e0  pop     r12
0x1800076e2  pop     rdi
0x1800076e3  pop     rsi
0x1800076e4  pop     rbx
0x1800076e5  pop     rbp
0x1800076e6  retn
0x1800076e7  lea     rax, aWrongNumberOfB; "Wrong number of bytes sent"
0x1800076ee  mov     qword ptr [rsp+160h+var_138], rax
0x1800076f3  mov     [rsp+160h+var_140], 80511001h
0x1800076fb  mov     edi, 9Eh
0x180007700  mov     r9d, 400h
0x180007706  mov     r8d, edi
0x180007709  lea     rdx, word_18013A0B6
0x180007710  lea     rbx, aNoFilename; "(no filename)"
0x180007717  mov     rcx, rbx
0x18000771a  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x18000771f  lea     rax, aUnexpectedHres; "Unexpected HRESULT returned by API"
0x180007726  mov     qword ptr [rsp+160h+var_120], rax
0x18000772b  lea     rdx, [rsp+160h+var_120]
0x180007730  lea     rcx, [rsp+160h+pExceptionObject]
0x180007735  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18000773b  xor     edx, edx; Val
0x18000773d  lea     r8d, [rdi-36h]; Size
0x180007741  lea     rcx, [rbp+60h+var_C8]; void *
0x180007745  call    memset_0
0x18000774a  mov     [rbp+60h+var_D0], rbx
0x18000774e  mov     [rbp+60h+var_D4], edi
0x180007751  or      ecx, 0FFFFFFFFh
0x180007754  mov     [rbp+60h+var_68], ecx
0x180007757  lea     rax, ??_7THResultException@SplException@@6B@; const SplException::THResultException::`vftable'
0x18000775e  mov     [rsp+160h+pExceptionObject], rax
0x180007763  mov     [rbp+60h+var_D8], 80511001h
0x18000776a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180007771  movdqu  [rbp+60h+var_90], xmm0
0x180007776  mov     rax, cs:?Functions@SplException@@3UExceptionTableFunctions@1@A; SplException::ExceptionTableFunctions SplException::Functions
0x18000777d  test    rax, rax
0x180007780  jz      short loc_18000778E
0x180007782  lea     rcx, [rbp+60h+var_D8]
0x180007786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000778b  mov     [rbp+60h+var_68], eax
0x18000778e  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180007795  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18000779a  call    _CxxThrowException_0
0x1800077a0  mov     rdx, [rdi+30h]
0x1800077a4  mov     qword ptr [rsp+160h+var_110], rdx
0x1800077a9  movzx   eax, word ptr [rdi+58h]
0x1800077ad  add     rax, rdx
0x1800077b0  mov     qword ptr [rsp+160h+var_110+8], rax
0x1800077b5  mov     rcx, [rdi+20h]
0x1800077b9  add     rcx, 68h ; 'h'
0x1800077bd  lea     r8, [rsp+160h+var_110]
0x1800077c2  lea     rdx, [rsp+160h+var_120]
0x1800077c7  call    ?CreateSenderOfRange@ByteCollection@win_dox@@QEBA?AVByteSender@2@AEBU?$range@_K@2@@Z; win_dox::ByteCollection::CreateSenderOfRange(win_dox::range<unsigned __int64> const &)
0x1800077cc  nop
0x1800077cd  lea     rdx, [rsp+160h+var_120]; struct win_dox::ByteSender *
0x1800077d2  mov     rcx, rdi; this
0x1800077d5  call    ?ProcessCommentByteSender@ZipEndOfCentralDirectoryConsumer@consumption@win_musl@@AEAAXAEAVByteSender@win_dox@@@Z; win_musl::consumption::ZipEndOfCentralDirectoryConsumer::ProcessCommentByteSender(win_dox::ByteSender &)
0x1800077da  nop
0x1800077db  lea     rax, ??_7OpcRelationshipSender@win_dox@@6B@; const win_dox::OpcRelationshipSender::`vftable'
0x1800077e2  mov     qword ptr [rsp+160h+var_120], rax
0x1800077e7  mov     rcx, qword ptr [rsp+160h+var_120+8]
0x1800077ec  test    rcx, rcx
0x1800077ef  jz      short loc_1800077FE
0x1800077f1  mov     rax, [rcx]
0x1800077f4  mov     rax, [rax+10h]
0x1800077f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077fd  nop
0x1800077fe  jmp     loc_1800076C7
0x180007803  cmp     bx, r14w
0x180007807  jz      loc_1800074E7
0x18000780d  lea     rax, aArchiveFeature; "Archive feature not supported: only sup"...
0x180007814  mov     [rsp+160h+var_130], rax; struct win_musl::TStringEllipseBase *
0x180007819  mov     [rsp+160h+var_138], 80511008h; unsigned int
0x180007821  mov     [rsp+160h+var_140], 0ACh; unsigned int
0x180007829  lea     r9, word_18013A0B6
0x180007830  lea     r8, aNoFilename; "(no filename)"
0x180007837  lea     rcx, [rsp+160h+pExceptionObject]; this
0x18000783c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180007841  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180007848  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18000784d  call    _CxxThrowException_0
0x180007853  cmp     bx, si
0x180007856  jz      loc_18000752A
0x18000785c  lea     rax, aArchiveFeature; "Archive feature not supported: only sup"...
0x180007863  mov     [rsp+160h+var_130], rax; struct win_musl::TStringEllipseBase *
0x180007868  mov     [rsp+160h+var_138], 80511008h; unsigned int
0x180007870  mov     [rsp+160h+var_140], 0B6h; unsigned int
0x180007878  lea     r9, word_18013A0B6
0x18000787f  lea     r8, aNoFilename; "(no filename)"
0x180007886  lea     rcx, [rsp+160h+pExceptionObject]; this
0x18000788b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180007890  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180007897  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18000789c  call    _CxxThrowException_0
0x1800078a2  lea     rax, aArchiveFeature; "Archive feature not supported: only sup"...
0x1800078a9  mov     [rsp+160h+var_130], rax; struct win_musl::TStringEllipseBase *
0x1800078ae  mov     [rsp+160h+var_138], 80511008h; unsigned int
0x1800078b6  mov     [rsp+160h+var_140], 0C5h; unsigned int
0x1800078be  lea     r9, word_18013A0B6
0x1800078c5  lea     r8, aNoFilename; "(no filename)"
0x1800078cc  lea     rcx, [rsp+160h+pExceptionObject]; this
0x1800078d1  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800078d6  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800078dd  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x1800078e2  call    _CxxThrowException_0
0x1800078e8  sub     ecx, 1
0x1800078eb  jz      short loc_180007945
0x1800078ed  cmp     ecx, 1
0x1800078f0  jnz     short loc_180007945
0x1800078f2  or      ecx, 0FFFFFFFFh
0x1800078f5  cmp     r12d, ecx
0x1800078f8  jz      short loc_180007901
0x1800078fa  mov     [rdx+98h], r12
0x180007901  cmp     ebx, ecx
0x180007903  jz      short loc_180007910
0x180007905  mov     rax, [rdi+20h]
0x180007909  mov     [rax+90h], rbx
0x180007910  mov     edx, 0FFFFh
0x180007915  cmp     r15w, dx
0x180007919  jz      short loc_180007926
0x18000791b  mov     rax, [rdi+20h]
0x18000791f  mov     [rax+88h], r15
0x180007926  cmp     r14w, dx
0x18000792a  jz      short loc_180007937
0x18000792c  mov     rax, [rdi+20h]
0x180007930  mov     [rax+0A8h], r14d
0x180007937  cmp     si, dx
0x18000793a  jz      loc_1800076B4
0x180007940  jmp     loc_1800076AA
0x180007945  lea     rax, aInvalidEndOfCe; "invalid end_of_central_directory source"...
0x18000794c  mov     [rsp+160h+var_130], rax; struct win_musl::TStringEllipseBase *
0x180007951  mov     [rsp+160h+var_138], 8000FFFFh; unsigned int
0x180007959  mov     [rsp+160h+var_140], 110h; unsigned int
0x180007961  lea     r9, word_18013A0B6
0x180007968  lea     r8, aNoFilename; "(no filename)"
0x18000796f  lea     rcx, [rsp+160h+pExceptionObject]; this
0x180007974  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180007979  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180007980  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x180007985  call    _CxxThrowException_0
0x18000798b  lea     rax, WPP_GLOBAL_Control
0x180007992  mov     rcx, cs:WPP_GLOBAL_Control
0x180007999  cmp     rcx, rax
0x18000799c  jz      loc_1800077A0
0x1800079a2  test    byte ptr [rcx+44h], 10h
0x1800079a6  jz      loc_1800077A0
0x1800079ac  movzx   eax, word ptr [rdi+58h]
0x1800079b0  mov     edx, 0Ch
0x1800079b5  mov     [rsp+160h+var_140], eax
0x1800079b9  mov     r9, [rdi+30h]
0x1800079bd  lea     r8, WPP_37a605dc7fd83120dddcbd48d857a9dd_Traceguids
0x1800079c4  mov     rcx, [rcx+38h]
0x1800079c8  call    WPP_SF_ID
  ... truncated ...
```
