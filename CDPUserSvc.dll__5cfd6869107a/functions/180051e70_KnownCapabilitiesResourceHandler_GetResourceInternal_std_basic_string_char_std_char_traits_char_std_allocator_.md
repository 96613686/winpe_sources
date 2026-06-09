# KnownCapabilitiesResourceHandler::GetResourceInternal(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,CDPUserTrustLevel,ICDPResourceHandlerCallback *)

- ea: `0x180051e70`
- end: `0x180052349`
- name: `?GetResourceInternal@KnownCapabilitiesResourceHandler@@AEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4CDPUserTrustLevel@@PEAVICDPResourceHandlerCallback@@@Z`
- size: `1241`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180051c70`

## callees

- `0x180002a4c`
- `0x1800041b0`
- `0x180004a58`
- `0x180025ce4`
- `0x18002c570`
- `0x18002d204`
- `0x180042ce0`
- `0x180043988`
- `0x180043d60`
- `0x18004f708`
- `0x180051030`
- `0x180051e70`
- `0x18005c800`
- `0x180064010`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180052102`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180052102`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180051ed6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052028`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052155`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052272`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180051ed6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052028`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052155`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052272`

## string_xrefs

- `0x180051f01`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180052053`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180052180`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18005229d`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180051f83`: `CDP/LaunchUri`
- `0x180051f59`: `CDP/AppService`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall KnownCapabilitiesResourceHandler::GetResourceInternal(__int64 a1, __int64 a2, int a3, __int64 *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  DWORD CurrentThreadId; // ecx
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rsi
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // eax
  unsigned int v20; // ebx
  DWORD v21; // eax
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rax
  bool v26; // bl
  bool v27; // zf
  __int64 v28; // rax
  int v29; // eax
  unsigned int v30; // ebx
  DWORD v31; // eax
  __int64 v32; // r9
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rax
  unsigned int v36; // esi
  __int64 v37; // rdi
  __int64 v38; // rbx
  __int64 v39; // rax
  int v40; // eax
  unsigned int v41; // ebx
  DWORD v42; // eax
  __int64 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rax
  __int64 v47; // rcx
  int v49; // [rsp+30h] [rbp-168h] BYREF
  __int64 v50; // [rsp+38h] [rbp-160h] BYREF
  __int64 v51; // [rsp+40h] [rbp-158h] BYREF
  const char *v52; // [rsp+48h] [rbp-150h] BYREF
  int v53[4]; // [rsp+50h] [rbp-148h] BYREF
  const char *v54; // [rsp+60h] [rbp-138h] BYREF
  _DWORD v55[4]; // [rsp+68h] [rbp-130h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-120h] BYREF
  _BYTE v57[56]; // [rsp+B0h] [rbp-E8h] BYREF
  _BYTE v58[56]; // [rsp+E8h] [rbp-B0h] BYREF
  _BYTE v59[56]; // [rsp+120h] [rbp-78h] BYREF
  _BYTE v60[32]; // [rsp+158h] [rbp-40h] BYREF

  v51 = 0;
  v7 = Microsoft::WRL::Details::MakeAndInitialize<CDPComUserSettingsProvider,ICDPComUserSettingsProvider,>(&v51);
  v8 = v7;
  if ( v7 < 0 )
  {
    v52 = "..\\knowncapabilitiesresourcehandler.cpp";
    v53[0] = 179;
    v49 = v7;
    CurrentThreadId = GetCurrentThreadId();
    v50 = CurrentThreadId;
    Log<long &,char const * &,int &,unsigned __int64>(
      CurrentThreadId,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v49,
      (unsigned int)&v52,
      (__int64)v53,
      (__int64)&v50);
    v10 = cdp::ExceptionStackFromSourceLocationInfo(&v54, &v52);
    v13 = cdp::ErrorCodeToString(v8, v11, v12, v10);
    ConnectedDevices::Exception::Exception(pExceptionObject, v8, v13);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v14 = *(_QWORD *)(a2 + 16);
  v15 = std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v15, v14, "CDP/AppService", 14)
    || (v16 = std::_String_val<std::_Simple_types<char>>::_Myptr(a2),
        (unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v16, v14, "CDP/LaunchUri", 13))
    || (v17 = std::_String_val<std::_Simple_types<char>>::_Myptr(a2),
        (unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v17, v14, "CDP/RemoteSession", 17)) )
  {
    v49 = 0;
    v29 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v51 + 24LL))(v51, &v49);
    v30 = v29;
    if ( v29 < 0 )
    {
      v54 = "..\\knowncapabilitiesresourcehandler.cpp";
      v55[0] = 185;
      LODWORD(v50) = v29;
      v31 = GetCurrentThreadId();
      v52 = (const char *)v31;
      Log<long &,char const * &,int &,unsigned __int64>(
        v31,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v50,
        (unsigned int)&v54,
        (__int64)v55,
        (__int64)&v52);
      v32 = cdp::ExceptionStackFromSourceLocationInfo(&v52, &v54);
      v35 = cdp::ErrorCodeToString(v30, v33, v34, v32);
      ConnectedDevices::Exception::Exception(v58, v30, v35);
      throw (ConnectedDevices::Exception *)v58;
    }
    v26 = (_BYTE)v49 != 0;
  }
  else
  {
    v18 = std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v18, v14, "CDP/NearShare", 13) )
    {
      v49 = 0;
      v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v51 + 32LL))(v51, &v49);
      v20 = v19;
      if ( v19 < 0 )
      {
        v54 = "..\\knowncapabilitiesresourcehandler.cpp";
        v55[0] = 192;
        LODWORD(v50) = v19;
        v21 = GetCurrentThreadId();
        v52 = (const char *)v21;
        Log<long &,char const * &,int &,unsigned __int64>(
          v21,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v50,
          (unsigned int)&v54,
          (__int64)v55,
          (__int64)&v52);
        v22 = cdp::ExceptionStackFromSourceLocationInfo(&v52, &v54);
        v25 = cdp::ErrorCodeToString(v20, v23, v24, v22);
        ConnectedDevices::Exception::Exception(v57, v20, v25);
        throw (ConnectedDevices::Exception *)v57;
      }
      if ( !(_BYTE)v49 )
      {
LABEL_14:
        v26 = 0;
        goto LABEL_21;
      }
      if ( (unsigned __int8)v49 != 1 )
      {
        if ( (unsigned __int8)v49 == 2 )
        {
          v26 = 1;
          goto LABEL_21;
        }
        goto LABEL_14;
      }
      v27 = a3 == 1;
    }
    else
    {
      v26 = 0;
      v28 = std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
      if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v28, v14, "Perception/SpatialEntity", 24) )
        goto LABEL_21;
      v49 = 0;
      RtlGetDeviceFamilyInfoEnum(0, &v49, 0);
      v27 = v49 == 10;
    }
    v26 = v27;
  }
LABEL_21:
  std::string::string(v60);
  if ( v26 )
  {
    v36 = 0;
    std::string::_Assign<char>(v60, "enabled", 7);
  }
  else
  {
    std::string::_Assign<char>(v60, "disabled", 8);
    v36 = -2147217151;
  }
  v37 = std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
  v38 = *a4;
  v39 = std::_String_val<std::_Simple_types<char>>::_Myptr(v60);
  v40 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, __int64, __int64))(v38 + 24))(a4, v36, 1, v37, v39);
  v41 = v40;
  if ( v40 < 0 )
  {
    v54 = "..\\knowncapabilitiesresourcehandler.cpp";
    v55[0] = 225;
    LODWORD(v50) = v40;
    v42 = GetCurrentThreadId();
    v52 = (const char *)v42;
    Log<long &,char const * &,int &,unsigned __int64>(
      v42,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v50,
      (unsigned int)&v54,
      (__int64)v55,
      (__int64)&v52);
    v43 = cdp::ExceptionStackFromSourceLocationInfo(&v52, &v54);
    v46 = cdp::ErrorCodeToString(v41, v44, v45, v43);
    ConnectedDevices::Exception::Exception(v59, v41, v46);
    throw (ConnectedDevices::Exception *)v59;
  }
  std::string::_Tidy_deallocate(v60);
  v47 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  return 0;
}

```

## disassembly

```asm
0x180051e70  mov     [rsp+arg_0], rbx
0x180051e75  mov     [rsp+arg_10], rsi
0x180051e7a  push    rdi
0x180051e7b  push    r14
0x180051e7d  push    r15
0x180051e7f  sub     rsp, 180h
0x180051e86  mov     rax, cs:__security_cookie
0x180051e8d  xor     rax, rsp
0x180051e90  mov     [rsp+198h+var_20], rax
0x180051e98  mov     r15, r9
0x180051e9b  mov     r14d, r8d
0x180051e9e  mov     rdi, rdx
0x180051ea1  mov     [rsp+198h+var_158], 0
0x180051eaa  lea     rcx, [rsp+198h+var_158]
0x180051eaf  call    ??$MakeAndInitialize@VCDPComUserSettingsProvider@@UICDPComUserSettingsProvider@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUICDPComUserSettingsProvider@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CDPComUserSettingsProvider,ICDPComUserSettingsProvider,>(ICDPComUserSettingsProvider * *)
0x180051eb4  mov     ebx, eax
0x180051eb6  test    eax, eax
0x180051eb8  jns     loc_180051F47
0x180051ebe  lea     rcx, aKnowncapabilit_0; "..\\knowncapabilitiesresourcehandler.cp"...
0x180051ec5  mov     [rsp+198h+var_150], rcx
0x180051eca  mov     [rsp+198h+var_148], 0B3h
0x180051ed2  mov     [rsp+198h+var_168], eax
0x180051ed6  call    cs:__imp_GetCurrentThreadId
0x180051edc  mov     ecx, eax
0x180051ede  mov     [rsp+198h+var_160], rcx
0x180051ee3  lea     rax, [rsp+198h+var_160]
0x180051ee8  mov     [rsp+198h+var_170], rax
0x180051eed  lea     rax, [rsp+198h+var_148]
0x180051ef2  mov     [rsp+198h+var_178], rax
0x180051ef7  lea     r9, [rsp+198h+var_150]
0x180051efc  lea     r8, [rsp+198h+var_168]
0x180051f01  lea     rdx, aHr0x08xFileSLi_3; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180051f08  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180051f0d  lea     rdx, [rsp+198h+var_150]
0x180051f12  lea     rcx, [rsp+198h+var_138]
0x180051f17  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180051f1c  mov     r9, rax
0x180051f1f  mov     ecx, ebx
0x180051f21  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180051f26  mov     r8, rax
0x180051f29  mov     edx, ebx
0x180051f2b  lea     rcx, [rsp+198h+pExceptionObject]
0x180051f30  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180051f35  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180051f3c  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x180051f41  call    _CxxThrowException_0
0x180051f47  mov     rsi, [rdi+10h]
0x180051f4b  mov     rcx, rdi
0x180051f4e  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180051f53  mov     r9d, 0Eh
0x180051f59  lea     r8, aCdpAppservice; "CDP/AppService"
0x180051f60  mov     rdx, rsi
0x180051f63  mov     rcx, rax
0x180051f66  call    ??$_Traits_equal@U?$char_traits@D@std@@@std@@YA_NQEBD_K01@Z; std::_Traits_equal<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x180051f6b  test    al, al
0x180051f6d  jnz     loc_180052115
0x180051f73  mov     rcx, rdi
0x180051f76  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180051f7b  mov     ebx, 0Dh
0x180051f80  mov     r9d, ebx
0x180051f83  lea     r8, aCdpLaunchuri; "CDP/LaunchUri"
0x180051f8a  mov     rdx, rsi
0x180051f8d  mov     rcx, rax
0x180051f90  call    ??$_Traits_equal@U?$char_traits@D@std@@@std@@YA_NQEBD_K01@Z; std::_Traits_equal<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x180051f95  test    al, al
0x180051f97  jnz     loc_180052115
0x180051f9d  mov     rcx, rdi
0x180051fa0  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180051fa5  lea     r9d, [rbx+4]
0x180051fa9  lea     r8, aCdpRemotesessi; "CDP/RemoteSession"
0x180051fb0  mov     rdx, rsi
0x180051fb3  mov     rcx, rax
0x180051fb6  call    ??$_Traits_equal@U?$char_traits@D@std@@@std@@YA_NQEBD_K01@Z; std::_Traits_equal<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x180051fbb  test    al, al
0x180051fbd  jnz     loc_180052115
0x180051fc3  mov     rcx, rdi
0x180051fc6  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180051fcb  mov     r9d, ebx
0x180051fce  lea     r8, aCdpNearshare; "CDP/NearShare"
0x180051fd5  mov     rdx, rsi
0x180051fd8  mov     rcx, rax
0x180051fdb  call    ??$_Traits_equal@U?$char_traits@D@std@@@std@@YA_NQEBD_K01@Z; std::_Traits_equal<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x180051fe0  test    al, al
0x180051fe2  jz      loc_1800520C6
0x180051fe8  mov     [rsp+198h+var_168], 0
0x180051ff0  mov     rcx, [rsp+198h+var_158]
0x180051ff5  mov     rax, [rcx]
0x180051ff8  lea     rdx, [rsp+198h+var_168]
0x180051ffd  mov     rax, [rax+20h]
0x180052001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052006  mov     ebx, eax
0x180052008  test    eax, eax
0x18005200a  jns     loc_18005209F
0x180052010  lea     rcx, aKnowncapabilit_0; "..\\knowncapabilitiesresourcehandler.cp"...
0x180052017  mov     [rsp+198h+var_138], rcx
0x18005201c  mov     [rsp+198h+var_130], 0C0h
0x180052024  mov     dword ptr [rsp+198h+var_160], eax
0x180052028  call    cs:__imp_GetCurrentThreadId
0x18005202e  mov     ecx, eax
0x180052030  mov     [rsp+198h+var_150], rcx
0x180052035  lea     rax, [rsp+198h+var_150]
0x18005203a  mov     [rsp+198h+var_170], rax
0x18005203f  lea     rax, [rsp+198h+var_130]
0x180052044  mov     [rsp+198h+var_178], rax
0x180052049  lea     r9, [rsp+198h+var_138]
0x18005204e  lea     r8, [rsp+198h+var_160]
0x180052053  lea     rdx, aHr0x08xFileSLi_3; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18005205a  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18005205f  lea     rdx, [rsp+198h+var_138]
0x180052064  lea     rcx, [rsp+198h+var_150]
0x180052069  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18005206e  mov     r9, rax
0x180052071  mov     ecx, ebx
0x180052073  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180052078  mov     r8, rax
0x18005207b  mov     edx, ebx
0x18005207d  lea     rcx, [rsp+198h+var_E8]
0x180052085  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18005208a  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180052091  lea     rcx, [rsp+198h+var_E8]; pExceptionObject
0x180052099  call    _CxxThrowException_0
0x18005209f  movzx   ecx, byte ptr [rsp+198h+var_168]
0x1800520a4  test    ecx, ecx
0x1800520a6  jz      short loc_1800520BF
0x1800520a8  sub     ecx, 1
0x1800520ab  jz      short loc_1800520B9
0x1800520ad  cmp     ecx, 1
0x1800520b0  jnz     short loc_1800520BF
0x1800520b2  mov     bl, cl
0x1800520b4  jmp     loc_1800521D4
0x1800520b9  cmp     r14d, 1
0x1800520bd  jmp     short loc_18005210D
0x1800520bf  xor     bl, bl
0x1800520c1  jmp     loc_1800521D4
0x1800520c6  xor     bl, bl
0x1800520c8  mov     rcx, rdi
0x1800520cb  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800520d0  mov     r9d, 18h
0x1800520d6  lea     r8, aPerceptionSpat; "Perception/SpatialEntity"
0x1800520dd  mov     rdx, rsi
0x1800520e0  mov     rcx, rax
0x1800520e3  call    ??$_Traits_equal@U?$char_traits@D@std@@@std@@YA_NQEBD_K01@Z; std::_Traits_equal<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1800520e8  test    al, al
0x1800520ea  jz      loc_1800521D4
0x1800520f0  mov     [rsp+198h+var_168], 0
0x1800520f8  xor     r8d, r8d
0x1800520fb  lea     rdx, [rsp+198h+var_168]
0x180052100  xor     ecx, ecx
0x180052102  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180052108  cmp     [rsp+198h+var_168], 0Ah
0x18005210d  setz    bl
0x180052110  jmp     loc_1800521D4
0x180052115  mov     [rsp+198h+var_168], 0
0x18005211d  mov     rcx, [rsp+198h+var_158]
0x180052122  mov     rax, [rcx]
0x180052125  lea     rdx, [rsp+198h+var_168]
0x18005212a  mov     rax, [rax+18h]
0x18005212e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052133  mov     ebx, eax
0x180052135  test    eax, eax
0x180052137  jns     loc_1800521CC
0x18005213d  lea     rcx, aKnowncapabilit_0; "..\\knowncapabilitiesresourcehandler.cp"...
0x180052144  mov     [rsp+198h+var_138], rcx
0x180052149  mov     [rsp+198h+var_130], 0B9h
0x180052151  mov     dword ptr [rsp+198h+var_160], eax
0x180052155  call    cs:__imp_GetCurrentThreadId
0x18005215b  mov     ecx, eax
0x18005215d  mov     [rsp+198h+var_150], rcx
0x180052162  lea     rax, [rsp+198h+var_150]
0x180052167  mov     [rsp+198h+var_170], rax
0x18005216c  lea     rax, [rsp+198h+var_130]
0x180052171  mov     [rsp+198h+var_178], rax
0x180052176  lea     r9, [rsp+198h+var_138]
0x18005217b  lea     r8, [rsp+198h+var_160]
0x180052180  lea     rdx, aHr0x08xFileSLi_3; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180052187  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18005218c  lea     rdx, [rsp+198h+var_138]
0x180052191  lea     rcx, [rsp+198h+var_150]
0x180052196  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18005219b  mov     r9, rax
0x18005219e  mov     ecx, ebx
0x1800521a0  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800521a5  mov     r8, rax
0x1800521a8  mov     edx, ebx
0x1800521aa  lea     rcx, [rsp+198h+var_B0]
0x1800521b2  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800521b7  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800521be  lea     rcx, [rsp+198h+var_B0]; pExceptionObject
0x1800521c6  call    _CxxThrowException_0
0x1800521cc  cmp     byte ptr [rsp+198h+var_168], 0
0x1800521d1  setnz   bl
0x1800521d4  lea     rcx, [rsp+198h+var_40]
0x1800521dc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800521e1  nop
0x1800521e2  lea     rcx, [rsp+198h+var_40]
0x1800521ea  test    bl, bl
0x1800521ec  jz      short loc_180052202
0x1800521ee  xor     esi, esi
0x1800521f0  lea     r8d, [rsi+7]
0x1800521f4  lea     rdx, aEnabled_0; "enabled"
0x1800521fb  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x180052200  jmp     short loc_180052219
0x180052202  mov     r8d, 8
0x180052208  lea     rdx, aDisabled; "disabled"
0x18005220f  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x180052214  mov     esi, 80041101h
0x180052219  mov     rcx, rdi
0x18005221c  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180052221  mov     rdi, rax
0x180052224  mov     rbx, [r15]
0x180052227  lea     rcx, [rsp+198h+var_40]
0x18005222f  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180052234  mov     [rsp+198h+var_178], rax
0x180052239  mov     r9, rdi
0x18005223c  mov     r8d, 1
0x180052242  mov     edx, esi
0x180052244  mov     rcx, r15
0x180052247  mov     rax, [rbx+18h]
0x18005224b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052250  mov     ebx, eax
0x180052252  test    eax, eax
0x180052254  jns     loc_1800522E9
0x18005225a  lea     rcx, aKnowncapabilit_0; "..\\knowncapabilitiesresourcehandler.cp"...
0x180052261  mov     [rsp+198h+var_138], rcx
0x180052266  mov     [rsp+198h+var_130], 0E1h
0x18005226e  mov     dword ptr [rsp+198h+var_160], eax
0x180052272  call    cs:__imp_GetCurrentThreadId
0x180052278  mov     ecx, eax
0x18005227a  mov     [rsp+198h+var_150], rcx
0x18005227f  lea     rax, [rsp+198h+var_150]
0x180052284  mov     [rsp+198h+var_170], rax
0x180052289  lea     rax, [rsp+198h+var_130]
0x18005228e  mov     [rsp+198h+var_178], rax
0x180052293  lea     r9, [rsp+198h+var_138]
0x180052298  lea     r8, [rsp+198h+var_160]
0x18005229d  lea     rdx, aHr0x08xFileSLi_3; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800522a4  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800522a9  lea     rdx, [rsp+198h+var_138]
0x1800522ae  lea     rcx, [rsp+198h+var_150]
0x1800522b3  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800522b8  mov     r9, rax
0x1800522bb  mov     ecx, ebx
0x1800522bd  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800522c2  mov     r8, rax
0x1800522c5  mov     edx, ebx
0x1800522c7  lea     rcx, [rsp+198h+var_78]
0x1800522cf  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800522d4  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800522db  lea     rcx, [rsp+198h+var_78]; pExceptionObject
0x1800522e3  call    _CxxThrowException_0
0x1800522e9  lea     rcx, [rsp+198h+var_40]
0x1800522f1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800522f6  nop
0x1800522f7  mov     rcx, [rsp+198h+var_158]
0x1800522fc  test    rcx, rcx
0x1800522ff  jz      short loc_180052317
0x180052301  mov     [rsp+198h+var_158], 0
0x18005230a  mov     rax, [rcx]
0x18005230d  mov     rax, [rax+10h]
0x180052311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052316  nop
0x180052317  xor     eax, eax
0x180052319  jmp     short loc_18005231F
0x18005231b  mov     eax, dword ptr [rsp+198h+var_160]
0x18005231f  mov     rcx, [rsp+198h+var_20]
0x180052327  xor     rcx, rsp; StackCookie
0x18005232a  call    __security_check_cookie
0x18005232f  lea     r11, [rsp+198h+var_18]
0x180052337  mov     rbx, [r11+20h]
0x18005233b  mov     rsi, [r11+30h]
0x18005233f  mov     rsp, r11
0x180052342  pop     r15
0x180052344  pop     r14
0x180052346  pop     rdi
0x180052347  retn
```
