# win_musl::consumption::ZipEndOfCentralDirectoryZip64LocatorConsumer::Close(win_musl::ByteReceiverUnique<win_musl::consumption::ZipEndOfCentralDirectoryZip64LocatorConsumer,0,IUnknown> &)

- ea: `0x180085130`
- end: `0x18008539a`
- name: `?Close@ZipEndOfCentralDirectoryZip64LocatorConsumer@consumption@win_musl@@QEAAXAEAV?$ByteReceiverUnique@VZipEndOfCentralDirectoryZip64LocatorConsumer@consumption@win_musl@@$0A@UIUnknown@@@3@@Z`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180084f8c`

## callees

- `0x1800019b0`
- `0x180007b44`
- `0x18000a030`
- `0x1800517a0`
- `0x180085130`
- `0x1800cd38c`
- `0x1801108cc`
- `0x180117740`
- `0x18012a010`

## string_xrefs

- `0x180085190`: `diskNumberDirectoryStart`
- `0x1800851a6`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryzip64locatorconsumer.cpp`
- `0x180085242`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryzip64locatorconsumer.cpp`
- `0x18008517e`: `win_musl::consumption::ZipEndOfCentralDirectoryZip64LocatorConsumer::Close`
- `0x180085261`: `_context->end_of_central_directory.offsetZip64EndOfCentralDirectory`
- `0x1800851d3`: `Number of the disk with the start of the zip64 end of central directory must be 0 - only support single disk archives.`

## pseudocode

```c
__int64 __fastcall win_musl::consumption::ZipEndOfCentralDirectoryZip64LocatorConsumer::Close(_QWORD *a1)
{
  __int64 v2; // rcx
  __int128 v3; // xmm6
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 result; // rax
  __int64 v7; // rcx
  _BYTE v8[8]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v9; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v10; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF

  v2 = a1[7];
  if ( !v2 || a1[8] - v2 != 16 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x87u,
      0x80511001,
      (struct win_musl::TStringEllipseBase *)L"Wrong number of bytes sent");
    throw (SplException::THResultException *)pExceptionObject;
  }
  *(_QWORD *)&v9 = 16;
  *((_QWORD *)&v9 + 1) = v2;
  v10 = v9;
  if ( (unsigned int)win_musl::detail::readThenLog<unsigned int>(
                       (__int64)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofc"
                                "entraldirectoryzip64locatorconsumer.cpp",
                       146,
                       (__int64)"win_musl::consumption::ZipEndOfCentralDirectoryZip64LocatorConsumer::Close",
                       (__int64)"diskNumberDirectoryStart",
                       (unsigned int *)&v10,
                       (__int64)&v9) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x99u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Number of the disk with the start of the zip64 end of central directory mus"
                                              "t be 0 - only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v3 = v9;
  v10 = v9;
  v8[0] = 0;
  v4 = win_musl::detail::vector_read<unsigned __int64>(&v10, &v9, v8);
  if ( v8[0] )
  {
    v10 = v3;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirectoryzip64locatorconsumer.cpp",
      164,
      "win_musl::consumption::ZipEndOfCentralDirectoryZip64LocatorConsumer::Close",
      "_context->end_of_central_directory.offsetZip64EndOfCentralDirectory",
      8,
      &v10);
  }
  v5 = a1[3];
  v10 = v9;
  *(_QWORD *)(v5 + 160) = v4;
  result = win_musl::detail::readThenLog<unsigned int>(
             (__int64)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldire"
                      "ctoryzip64locatorconsumer.cpp",
             168,
             (__int64)"win_musl::consumption::ZipEndOfCentralDirectoryZip64LocatorConsumer::Close",
             (__int64)"diskNumberTotal",
             (unsigned int *)&v10,
             (__int64)&v9);
  if ( (_DWORD)result != 1 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xAEu,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Total number of disks must be 1 - only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v7 = a1[4];
  if ( v7 )
  {
    if ( dword_1801C4FE0 != -1 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 40LL))(v7, a1[5]);
      return win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(
               a1 + 4,
               0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180085130  mov     rax, rsp
0x180085133  mov     [rax+10h], rbx
0x180085137  mov     [rax+18h], rdi
0x18008513b  push    rbp
0x18008513c  lea     rbp, [rax-38h]
0x180085140  sub     rsp, 130h
0x180085147  movaps  xmmword ptr [rax-18h], xmm6
0x18008514b  mov     rax, cs:__security_cookie
0x180085152  xor     rax, rsp
0x180085155  mov     [rbp+30h+var_20], rax
0x180085159  mov     rbx, rcx
0x18008515c  mov     rcx, [rcx+38h]
0x180085160  test    rcx, rcx
0x180085163  jz      loc_180085354
0x180085169  mov     rax, [rbx+40h]
0x18008516d  sub     rax, rcx
0x180085170  cmp     rax, 10h
0x180085174  jnz     loc_180085354
0x18008517a  mov     dword ptr [rsp+130h+var_E8+8], eax
0x18008517e  lea     rdi, aWinMuslConsump_5; "win_musl::consumption::ZipEndOfCentralD"...
0x180085185  xor     eax, eax
0x180085187  mov     qword ptr [rsp+130h+var_D8], rcx
0x18008518c  mov     dword ptr [rsp+130h+var_E8+0Ch], eax
0x180085190  lea     r9, aDisknumberdire; "diskNumberDirectoryStart"
0x180085197  movaps  xmm0, [rsp+130h+var_E8+8]
0x18008519c  lea     rax, [rsp+130h+var_E8+8]
0x1800851a1  mov     qword ptr [rsp+130h+var_108], rax
0x1800851a6  lea     rcx, aOnecorePrintsc_9; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x1800851ad  lea     rax, [rsp+130h+var_D8+8]
0x1800851b2  movaps  [rsp+130h+var_E8+8], xmm0
0x1800851b7  mov     r8, rdi
0x1800851ba  mov     qword ptr [rsp+130h+var_110], rax
0x1800851bf  mov     edx, 92h
0x1800851c4  movdqa  xmmword ptr [rsp+130h+var_D8+8], xmm0
0x1800851ca  call    ??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x1800851cf  test    eax, eax
0x1800851d1  jz      short loc_180085219
0x1800851d3  lea     rax, aNumberOfTheDis; "Number of the disk with the start of th"...
0x1800851da  mov     [rsp+130h+var_100], rax; struct win_musl::TStringEllipseBase *
0x1800851df  lea     r9, word_18013A0B6
0x1800851e6  mov     [rsp+130h+var_108], 80511008h; unsigned int
0x1800851ee  lea     r8, aNoFilename; "(no filename)"
0x1800851f5  lea     rcx, [rsp+130h+pExceptionObject]; this
0x1800851fa  mov     [rsp+130h+var_110], 99h; unsigned int
0x180085202  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180085207  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18008520e  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180085213  call    _CxxThrowException_0
0x180085219  movaps  xmm6, [rsp+130h+var_E8+8]
0x18008521e  lea     r8, [rsp+130h+var_F0]
0x180085223  lea     rdx, [rsp+130h+var_E8+8]
0x180085228  movdqa  xmmword ptr [rsp+130h+var_D8+8], xmm6
0x18008522e  lea     rcx, [rsp+130h+var_D8+8]
0x180085233  mov     [rsp+130h+var_F0], 0
0x180085238  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x18008523d  cmp     [rsp+130h+var_F0], 0
0x180085242  lea     rcx, aOnecorePrintsc_9; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x180085249  mov     rdx, rax
0x18008524c  mov     r8, rdi
0x18008524f  jz      short loc_18008527B
0x180085251  lea     rax, [rsp+130h+var_D8+8]
0x180085256  movdqa  xmmword ptr [rsp+130h+var_D8+8], xmm6
0x18008525c  mov     qword ptr [rsp+130h+var_108], rax
0x180085261  lea     r9, aContextEndOfCe; "_context->end_of_central_directory.offs"...
0x180085268  mov     edx, 0A4h
0x18008526d  mov     [rsp+130h+var_110], 8
0x180085275  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x18008527b  mov     rax, [rbx+18h]
0x18008527f  lea     r9, aDisknumbertota; "diskNumberTotal"
0x180085286  movaps  xmm0, [rsp+130h+var_E8+8]
0x18008528b  movdqa  xmmword ptr [rsp+130h+var_D8+8], xmm0
0x180085291  mov     [rax+0A0h], rdx
0x180085298  lea     rax, [rsp+130h+var_E8+8]
0x18008529d  mov     qword ptr [rsp+130h+var_108], rax
0x1800852a2  mov     edx, 0A8h
0x1800852a7  lea     rax, [rsp+130h+var_D8+8]
0x1800852ac  mov     qword ptr [rsp+130h+var_110], rax
0x1800852b1  call    ??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x1800852b6  cmp     eax, 1
0x1800852b9  jz      short loc_180085301
0x1800852bb  lea     rax, aTotalNumberOfD; "Total number of disks must be 1 - only "...
0x1800852c2  mov     [rsp+130h+var_100], rax; struct win_musl::TStringEllipseBase *
0x1800852c7  lea     r9, word_18013A0B6
0x1800852ce  mov     [rsp+130h+var_108], 80511008h; unsigned int
0x1800852d6  lea     r8, aNoFilename; "(no filename)"
0x1800852dd  lea     rcx, [rsp+130h+pExceptionObject]; this
0x1800852e2  mov     [rsp+130h+var_110], 0AEh; unsigned int
0x1800852ea  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800852ef  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800852f6  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x1800852fb  call    _CxxThrowException_0
0x180085301  mov     rcx, [rbx+20h]
0x180085305  test    rcx, rcx
0x180085308  jz      short loc_18008532E
0x18008530a  cmp     cs:dword_1801C4FE0, 0FFFFFFFFh
0x180085311  jz      short loc_18008532E
0x180085313  mov     rax, [rcx]
0x180085316  mov     rdx, [rbx+28h]
0x18008531a  mov     rax, [rax+28h]
0x18008531e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085323  xor     edx, edx
0x180085325  lea     rcx, [rbx+20h]
0x180085329  call    ?reset@?$scope_helper@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@3@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@@Z; win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(win_scope::scope<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> &,win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *)
0x18008532e  mov     rcx, [rbp+30h+var_20]
0x180085332  xor     rcx, rsp; StackCookie
0x180085335  call    __security_check_cookie
0x18008533a  lea     r11, [rsp+130h+var_s0]
0x180085342  mov     rbx, [r11+18h]
0x180085346  mov     rdi, [r11+20h]
0x18008534a  movaps  xmm6, xmmword ptr [r11-10h]
0x18008534f  mov     rsp, r11
0x180085352  pop     rbp
0x180085353  retn
0x180085354  lea     rax, aWrongNumberOfB; "Wrong number of bytes sent"
0x18008535b  mov     [rsp+130h+var_100], rax; struct win_musl::TStringEllipseBase *
0x180085360  lea     r9, word_18013A0B6
0x180085367  mov     [rsp+130h+var_108], 80511001h; unsigned int
0x18008536f  lea     r8, aNoFilename; "(no filename)"
0x180085376  lea     rcx, [rsp+130h+pExceptionObject]; this
0x18008537b  mov     [rsp+130h+var_110], 87h; unsigned int
0x180085383  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180085388  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18008538f  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180085394  call    _CxxThrowException_0
```
