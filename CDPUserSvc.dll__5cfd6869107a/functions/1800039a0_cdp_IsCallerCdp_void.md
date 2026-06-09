# cdp::IsCallerCdp(void)

- ea: `0x1800039a0`
- end: `0x180003d27`
- name: `?IsCallerCdp@cdp@@YA_NXZ`
- size: `903`
- prototype: `bool __fastcall(cdp *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003350`
- `0x1800034f0`
- `0x1800038c4`
- `0x18004d4ec`

## callees

- `0x1800039a0`
- `0x18002c570`
- `0x18002d204`
- `0x18003a4ac`
- `0x180042ce0`
- `0x180043988`
- `0x180043d60`
- `0x18005c338`
- `0x18005c800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c04`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180003ac2`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180003ac2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003cb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003cb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b2a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180003b0a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180003b0a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180003af0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180003af0`

## string_xrefs

- `0x180003bc0`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180003c5c`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180003ce3`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall cdp::IsCallerCdp(cdp *this)
{
  HRESULT v1; // eax
  unsigned int v2; // ebx
  bool v3; // bl
  signed int LastError; // eax
  unsigned int v6; // ebx
  int v7; // ecx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  signed int v12; // eax
  unsigned int v13; // ebx
  int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  int v19; // ecx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rax
  char v24[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-CCh] BYREF
  const char *v26; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+40h] [rbp-C0h] BYREF
  WINBOOL IsMember; // [rsp+48h] [rbp-B8h] BYREF
  __int64 CurrentThreadId; // [rsp+50h] [rbp-B0h] BYREF
  PSID Sid; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v33[24]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR StringSid[64]; // [rsp+C0h] [rbp-40h] BYREF

  wcscpy(StringSid, L"S-1-5-80-3433512109-503559027-1389316256-1766580070-2256751264");
  v24[0] = 0;
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v32, (__int64)v24);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v31, (__int64)&v32);
  v1 = CoImpersonateClient();
  v2 = v1;
  if ( v1 == -2147417833 )
  {
    ScopeWarden__lambda_6ddc22219f7099de82eca18a5ccc9b7c___::_ScopeWarden__lambda_6ddc22219f7099de82eca18a5ccc9b7c___(&v31);
    return 1;
  }
  else
  {
    if ( v1 < 0 )
    {
      v26 = ".\\platformutils.cpp";
      v27 = 517;
      v25 = v1;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v19,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v25,
        (unsigned int)&v26,
        (__int64)&v27,
        (__int64)&CurrentThreadId);
      v20 = cdp::ExceptionStackFromSourceLocationInfo(v33, &v26);
      v23 = cdp::ErrorCodeToString(v2, v21, v22, v20);
      ConnectedDevices::Exception::Exception(pExceptionObject, v2, v23);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    v24[0] = 1;
    Sid = 0;
    if ( !ConvertStringSidToSidW(StringSid, &Sid) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v26 = ".\\platformutils.cpp";
      v27 = 526;
      v25 = v6;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v7,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v25,
        (unsigned int)&v26,
        (__int64)&v27,
        (__int64)&CurrentThreadId);
      v8 = cdp::ExceptionStackFromSourceLocationInfo(v33, &v26);
      v11 = cdp::ErrorCodeToString(v6, v9, v10, v8);
      ConnectedDevices::Exception::Exception(pExceptionObject, v6, v11);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    IsMember = 0;
    if ( !CheckTokenMembership(0, Sid, &IsMember) )
    {
      v12 = GetLastError();
      v13 = v12;
      if ( v12 > 0 )
        v13 = (unsigned __int16)v12 | 0x80070000;
      v26 = ".\\platformutils.cpp";
      v27 = 530;
      v25 = v13;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v14,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v25,
        (unsigned int)&v26,
        (__int64)&v27,
        (__int64)&CurrentThreadId);
      v15 = cdp::ExceptionStackFromSourceLocationInfo(v33, &v26);
      v18 = cdp::ErrorCodeToString(v13, v16, v17, v15);
      ConnectedDevices::Exception::Exception(pExceptionObject, v13, v18);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    v3 = IsMember != 0;
    if ( Sid )
      LocalFree(Sid);
    ScopeWarden__lambda_6ddc22219f7099de82eca18a5ccc9b7c___::_ScopeWarden__lambda_6ddc22219f7099de82eca18a5ccc9b7c___(&v31);
    return v3;
  }
}

```

## disassembly

```asm
0x1800039a0  push    rbp
0x1800039a2  push    rbx
0x1800039a3  push    rsi
0x1800039a4  push    rdi
0x1800039a5  lea     rbp, [rsp-58h]
0x1800039aa  sub     rsp, 158h
0x1800039b1  mov     rax, cs:__security_cookie
0x1800039b8  xor     rax, rsp
0x1800039bb  mov     [rbp+70h+var_30], rax
0x1800039bf  mov     dword ptr [rbp+70h+StringSid], 2D0053h
0x1800039c6  mov     [rbp+70h+var_AC], 2D0031h
0x1800039cd  mov     [rbp+70h+var_A8], 2D0035h
0x1800039d4  mov     [rbp+70h+var_A4], 300038h
0x1800039db  mov     [rbp+70h+var_A0], 33002Dh
0x1800039e2  mov     [rbp+70h+var_9C], 330034h
0x1800039e9  mov     [rbp+70h+var_98], 350033h
0x1800039f0  mov     [rbp+70h+var_94], 320031h
0x1800039f7  mov     [rbp+70h+var_90], 300031h
0x1800039fe  mov     [rbp+70h+var_8C], 2D0039h
0x180003a05  mov     [rbp+70h+var_88], 300035h
0x180003a0c  mov     [rbp+70h+var_84], 350033h
0x180003a13  mov     [rbp+70h+var_80], 390035h
0x180003a1a  mov     [rbp+70h+var_7C], 320030h
0x180003a21  mov     [rbp+70h+var_78], 2D0037h
0x180003a28  mov     [rbp+70h+var_74], 330031h
0x180003a2f  mov     [rbp+70h+var_70], 390038h
0x180003a36  mov     [rbp+70h+var_6C], 310033h
0x180003a3d  mov     [rbp+70h+var_68], 320036h
0x180003a44  mov     [rbp+70h+var_64], 360035h
0x180003a4b  mov     [rbp+70h+var_60], 31002Dh
0x180003a52  mov     [rbp+70h+var_5C], 360037h
0x180003a59  mov     [rbp+70h+var_58], 350036h
0x180003a60  mov     [rbp+70h+var_54], 300038h
0x180003a67  mov     [rbp+70h+var_50], 370030h
0x180003a6e  mov     [rbp+70h+var_4C], 2D0030h
0x180003a75  mov     [rbp+70h+var_48], 320032h
0x180003a7c  mov     [rbp+70h+var_44], 360035h
0x180003a83  mov     [rbp+70h+var_40], 350037h
0x180003a8a  mov     [rbp+70h+var_3C], 320031h
0x180003a91  mov     [rbp+70h+var_38], 340036h
0x180003a98  xor     edi, edi
0x180003a9a  mov     [rbp+70h+var_34], di
0x180003a9e  mov     [rsp+170h+var_140], dil
0x180003aa3  lea     rdx, [rsp+170h+var_140]
0x180003aa8  lea     rcx, [rsp+170h+var_108]
0x180003aad  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180003ab2  lea     rdx, [rsp+170h+var_108]
0x180003ab7  lea     rcx, [rsp+170h+var_110]
0x180003abc  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180003ac1  nop
0x180003ac2  call    cs:__imp_CoImpersonateClient
0x180003ac8  mov     ebx, eax
0x180003aca  cmp     eax, 80010117h
0x180003acf  jz      loc_180003B5A
0x180003ad5  test    eax, eax
0x180003ad7  js      loc_180003CA0
0x180003add  mov     [rsp+170h+var_140], 1
0x180003ae2  mov     [rsp+170h+Sid], rdi
0x180003ae7  lea     rdx, [rsp+170h+Sid]; Sid
0x180003aec  lea     rcx, [rbp+70h+StringSid]; StringSid
0x180003af0  call    cs:__imp_ConvertStringSidToSidW
0x180003af6  test    eax, eax
0x180003af8  jz      short loc_180003B68
0x180003afa  mov     [rsp+170h+IsMember], edi
0x180003afe  lea     r8, [rsp+170h+IsMember]; IsMember
0x180003b03  mov     rdx, [rsp+170h+Sid]; SidToCheck
0x180003b08  xor     ecx, ecx; TokenHandle
0x180003b0a  call    cs:__imp_CheckTokenMembership
0x180003b10  test    eax, eax
0x180003b12  jz      loc_180003C04
0x180003b18  cmp     [rsp+170h+IsMember], edi
0x180003b1c  jz      short loc_180003B56
0x180003b1e  mov     bl, 1
0x180003b20  mov     rcx, [rsp+170h+Sid]; hMem
0x180003b25  test    rcx, rcx
0x180003b28  jz      short loc_180003B31
0x180003b2a  call    cs:__imp_LocalFree
0x180003b30  nop
0x180003b31  lea     rcx, [rsp+170h+var_110]
0x180003b36  call    ScopeWarden__lambda_6ddc22219f7099de82eca18a5ccc9b7c______ScopeWarden__lambda_6ddc22219f7099de82eca18a5ccc9b7c___
0x180003b3b  movzx   eax, bl
0x180003b3e  mov     rcx, [rbp+70h+var_30]
0x180003b42  xor     rcx, rsp; StackCookie
0x180003b45  call    __security_check_cookie
0x180003b4a  add     rsp, 158h
0x180003b51  pop     rdi
0x180003b52  pop     rsi
0x180003b53  pop     rbx
0x180003b54  pop     rbp
0x180003b55  retn
0x180003b56  xor     bl, bl
0x180003b58  jmp     short loc_180003B20
0x180003b5a  lea     rcx, [rsp+170h+var_110]
0x180003b5f  call    ScopeWarden__lambda_6ddc22219f7099de82eca18a5ccc9b7c______ScopeWarden__lambda_6ddc22219f7099de82eca18a5ccc9b7c___
0x180003b64  mov     al, 1
0x180003b66  jmp     short loc_180003B3E
0x180003b68  call    cs:__imp_GetLastError
0x180003b6e  mov     ebx, eax
0x180003b70  test    eax, eax
0x180003b72  jle     short loc_180003B7D
0x180003b74  movzx   ebx, ax
0x180003b77  or      ebx, 80070000h
0x180003b7d  lea     rax, aPlatformutilsC; ".\\platformutils.cpp"
0x180003b84  mov     [rsp+170h+var_138], rax
0x180003b89  mov     [rsp+170h+var_130], 20Eh
0x180003b91  mov     [rsp+170h+var_13C], ebx
0x180003b95  call    cs:__imp_GetCurrentThreadId
0x180003b9b  mov     eax, eax
0x180003b9d  mov     [rsp+170h+var_120], rax
0x180003ba2  lea     rax, [rsp+170h+var_120]
0x180003ba7  mov     [rsp+170h+var_148], rax
0x180003bac  lea     rax, [rsp+170h+var_130]
0x180003bb1  mov     [rsp+170h+var_150], rax
0x180003bb6  lea     r9, [rsp+170h+var_138]
0x180003bbb  lea     r8, [rsp+170h+var_13C]
0x180003bc0  lea     rdx, aHr0x08xFileSLi_3; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180003bc7  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180003bcc  lea     rdx, [rsp+170h+var_138]
0x180003bd1  lea     rcx, [rsp+170h+var_100]
0x180003bd6  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180003bdb  mov     r9, rax
0x180003bde  mov     ecx, ebx
0x180003be0  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180003be5  mov     r8, rax
0x180003be8  mov     edx, ebx
0x180003bea  lea     rcx, [rbp+70h+pExceptionObject]
0x180003bee  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180003bf3  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180003bfa  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180003bfe  call    _CxxThrowException_0
0x180003c04  call    cs:__imp_GetLastError
0x180003c0a  mov     ebx, eax
0x180003c0c  test    eax, eax
0x180003c0e  jle     short loc_180003C19
0x180003c10  movzx   ebx, ax
0x180003c13  or      ebx, 80070000h
0x180003c19  lea     rax, aPlatformutilsC; ".\\platformutils.cpp"
0x180003c20  mov     [rsp+170h+var_138], rax
0x180003c25  mov     [rsp+170h+var_130], 212h
0x180003c2d  mov     [rsp+170h+var_13C], ebx
0x180003c31  call    cs:__imp_GetCurrentThreadId
0x180003c37  mov     eax, eax
0x180003c39  mov     [rsp+170h+var_120], rax
0x180003c3e  lea     rax, [rsp+170h+var_120]
0x180003c43  mov     [rsp+170h+var_148], rax
0x180003c48  lea     rax, [rsp+170h+var_130]
0x180003c4d  mov     [rsp+170h+var_150], rax
0x180003c52  lea     r9, [rsp+170h+var_138]
0x180003c57  lea     r8, [rsp+170h+var_13C]
0x180003c5c  lea     rdx, aHr0x08xFileSLi_3; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180003c63  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180003c68  lea     rdx, [rsp+170h+var_138]
0x180003c6d  lea     rcx, [rsp+170h+var_100]
0x180003c72  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180003c77  mov     r9, rax
0x180003c7a  mov     ecx, ebx
0x180003c7c  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180003c81  mov     r8, rax
0x180003c84  mov     edx, ebx
0x180003c86  lea     rcx, [rbp+70h+pExceptionObject]
0x180003c8a  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180003c8f  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180003c96  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180003c9a  call    _CxxThrowException_0
0x180003ca0  lea     rax, aPlatformutilsC; ".\\platformutils.cpp"
0x180003ca7  mov     [rsp+170h+var_138], rax
0x180003cac  mov     [rsp+170h+var_130], 205h
0x180003cb4  mov     [rsp+170h+var_13C], ebx
0x180003cb8  call    cs:__imp_GetCurrentThreadId
0x180003cbe  mov     eax, eax
0x180003cc0  mov     [rsp+170h+var_120], rax
0x180003cc5  lea     rax, [rsp+170h+var_120]
0x180003cca  mov     [rsp+170h+var_148], rax
0x180003ccf  lea     rax, [rsp+170h+var_130]
0x180003cd4  mov     [rsp+170h+var_150], rax
0x180003cd9  lea     r9, [rsp+170h+var_138]
0x180003cde  lea     r8, [rsp+170h+var_13C]
0x180003ce3  lea     rdx, aHr0x08xFileSLi_3; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180003cea  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180003cef  lea     rdx, [rsp+170h+var_138]
0x180003cf4  lea     rcx, [rsp+170h+var_100]
0x180003cf9  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180003cfe  mov     r9, rax
0x180003d01  mov     ecx, ebx
0x180003d03  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180003d08  mov     r8, rax
0x180003d0b  mov     edx, ebx
0x180003d0d  lea     rcx, [rbp+70h+pExceptionObject]
0x180003d11  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180003d16  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180003d1d  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180003d21  call    _CxxThrowException_0
```
