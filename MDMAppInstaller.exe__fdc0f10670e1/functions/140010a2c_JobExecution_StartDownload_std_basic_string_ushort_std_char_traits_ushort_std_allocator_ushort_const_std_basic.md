# JobExecution::StartDownload(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140010a2c`
- end: `0x140010e22`
- name: `?StartDownload@JobExecution@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00AEAV23@@Z`
- size: `1014`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000d898`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x140006604`
- `0x1400068c8`
- `0x14000740c`
- `0x1400074d4`
- `0x14000904c`
- `0x140009f78`
- `0x14001050c`
- `0x1400105bc`
- `0x140010698`
- `0x140010a2c`
- `0x14001584c`
- `0x140015b7c`
- `0x1400162cc`
- `0x140017610`
- `0x140018878`
- `0x140018a68`
- `0x1400196dc`
- `0x14001a8d0`
- `0x14001c010`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x140010dc3`
- `ADVAPI32!RevertToSelf` at `0x140010dc3`
- `KERNEL32!LocalFree` at `0x140010de0`
- `KERNEL32!LocalFree` at `0x140010de0`
- `KERNEL32!HeapFree` at `0x140010db3`
- `KERNEL32!HeapFree` at `0x140010db3`
- `KERNEL32!GetProcessHeap` at `0x140010da5`
- `KERNEL32!GetProcessHeap` at `0x140010da5`
- `RPCRT4!RpcStringFreeW` at `0x140010dd5`
- `RPCRT4!RpcStringFreeW` at `0x140010dd5`
- `RPCRT4!UuidToStringW` at `0x140010d14`
- `RPCRT4!UuidToStringW` at `0x140010d14`

## string_xrefs

- `0x140010be7`: `Set Helper Tokens for Proxy result= 0x%1!x!`
- `0x140010c07`: `Set Security Option for CertThumbprint=%1`
- `0x140010c6d`: `Certificate thumbprint empty. Skipping the security configuration`

## pseudocode

```c
__int64 __fastcall JobExecution::StartDownload(_QWORD *a1, _QWORD *a2, _QWORD *a3, _QWORD *a4)
{
  _QWORD *v5; // rsi
  _QWORD *v6; // rdi
  int JobConfig; // ebx
  const unsigned __int16 *v9; // rcx
  wchar_t *v10; // rax
  wchar_t *v11; // rax
  int v12; // edx
  unsigned int v13; // eax
  unsigned __int16 **v14; // rdx
  const unsigned __int16 *v15; // r8
  const unsigned __int16 *v16; // r9
  _QWORD *v17; // r8
  _QWORD *v18; // rdx
  struct IBackgroundCopyJob *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  void *v22; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v24; // rdx
  _BYTE v26[7]; // [rsp+31h] [rbp-CFh] BYREF
  struct IBackgroundCopyJob *v27; // [rsp+38h] [rbp-C8h] BYREF
  ULONG SessionId; // [rsp+40h] [rbp-C0h]
  BG_CERT_STORE_LOCATION v29; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  RPC_WSTR StringUuid; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v33[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+68h] [rbp-98h]
  bool v35; // [rsp+6Ch] [rbp-94h]
  __int64 v36; // [rsp+70h] [rbp-90h]
  struct _GUID v37; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v38[32]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v39[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v40; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v41; // [rsp+D8h] [rbp-28h]
  GUID v42; // [rsp+E0h] [rbp-20h] BYREF
  UUID Uuid; // [rsp+F0h] [rbp-10h] BYREF

  v5 = a3;
  v6 = a2;
  *(_QWORD *)v33 = 0;
  v34 = 600;
  v35 = 1;
  v36 = 30;
  v27 = 0;
  Uuid = 0;
  StringUuid = 0;
  v26[0] = 0;
  lpMem = 0;
  v29 = BG_CERT_STORE_LOCATION_CURRENT_USER;
  v41 = 7;
  v40 = 0;
  LOWORD(v39[0]) = 0;
  SessionId = 0;
  v42 = GUID_NULL;
  hMem = 0;
  if ( !a2[2] || !a3[2] )
  {
    JobConfig = -2147024809;
    goto LABEL_44;
  }
  JobConfig = JobHelper::GetJobConfig((struct _JobConfig *)v33);
  if ( JobConfig < 0 )
    goto LABEL_44;
  JobConfig = GetMDMClientCert(&v29, v39, v26, &v42, &lpMem);
  if ( JobConfig < 0 )
    goto LABEL_44;
  v37 = v42;
  JobConfig = FetchUserAadToken(&v37, (unsigned __int16 **)&hMem);
  if ( JobConfig < 0 )
    goto LABEL_44;
  if ( v26[0] )
  {
    v10 = (wchar_t *)std::wstring::wstring(&v37, lpMem);
    JobConfig = FindSessionIDFromUserSid(v10);
    if ( JobConfig < 0 )
      goto LABEL_44;
    v11 = (wchar_t *)std::wstring::wstring(v38, lpMem);
    JobConfig = ImpersonateUser(v11, SessionId);
    if ( JobConfig < 0 )
      goto LABEL_44;
  }
  JobConfig = JobHelper::CreateDOJob(v9, &JobExecution::copyManager, &v27, &Uuid);
  if ( JobConfig < 0 )
    goto LABEL_44;
  JobConfig = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, _QWORD))v27->lpVtbl->SetPriority)(v27, v33[0]);
  if ( JobConfig < 0 )
    goto LABEL_44;
  v13 = SetDOHelperTokens(v27, v12);
  LogInfo(L"Set Helper Tokens for Proxy result= 0x%1!x!", v13);
  if ( v40 )
  {
    v14 = v39;
    if ( v41 >= 8 )
      v14 = (unsigned __int16 **)v39[0];
    LogInfo(L"Set Security Option for CertThumbprint=%1", v14);
    v16 = (const unsigned __int16 *)v39;
    if ( v41 >= 8 )
      v16 = v39[0];
    JobConfig = SetSecurityOptions2(v27, v29, v15, v16, v35, 0);
    if ( JobConfig < 0 )
      goto LABEL_44;
    LogInfo(L"Successfully done");
    JobConfig = AttachUserAadToken(v27, (const unsigned __int16 *)hMem);
    if ( JobConfig < 0 )
      goto LABEL_44;
  }
  else
  {
    LogError(L"Certificate thumbprint empty. Skipping the security configuration");
  }
  if ( v33[1] )
  {
    JobConfig = SetCostFlag(v27, v33[1]);
    if ( JobConfig < 0 )
      goto LABEL_44;
  }
  if ( a1[3] >= 8u )
    a1 = (_QWORD *)*a1;
  v17 = v6[3] < 8u ? v6 : (_QWORD *)*v6;
  v18 = v5[3] < 8u ? v5 : (_QWORD *)*v5;
  JobConfig = JobHelper::AddFile(&v27, v18, v17, a1);
  if ( JobConfig < 0
    || (JobConfig = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *))v27->lpVtbl->Resume)(v27), JobConfig < 0) )
  {
LABEL_44:
    LogError(L" StartDownload Failed with error = 0x%1!x!.", (unsigned int)JobConfig);
    if ( v27 )
      ((void (__fastcall *)(struct IBackgroundCopyJob *))v27->lpVtbl->Cancel)(v27);
    goto LABEL_46;
  }
  v19 = v27;
  if ( v27 )
  {
    v27 = 0;
    ((void (__fastcall *)(struct IBackgroundCopyJob *))v19->lpVtbl->Release)(v19);
  }
  if ( UuidToStringW(&Uuid, &StringUuid) )
  {
    JobConfig = -2147467259;
    goto LABEL_44;
  }
  v20 = std::char_traits<unsigned short>::length(StringUuid);
  std::wstring::assign(a4, v21, v20);
  if ( v5[3] >= 8u )
    v5 = (_QWORD *)*v5;
  if ( v6[3] >= 8u )
    v6 = (_QWORD *)*v6;
  if ( a4[3] >= 8u )
    a4 = (_QWORD *)*a4;
  LogInfo(L"Started BITS download job %1 with remote URL '%2' and download location '%3'.", a4, v6, v5);
LABEL_46:
  v22 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
    lpMem = 0;
  }
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  LocalFree(hMem);
  LOBYTE(v24) = 1;
  std::wstring::_Tidy(v39, v24, 0);
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v27);
  return (unsigned int)JobConfig;
}

```

## disassembly

```asm
0x140010a2c  push    rbp
0x140010a2e  push    rbx
0x140010a2f  push    rsi
0x140010a30  push    rdi
0x140010a31  push    r12
0x140010a33  push    r13
0x140010a35  push    r14
0x140010a37  push    r15
0x140010a39  lea     rbp, [rsp-18h]
0x140010a3e  sub     rsp, 118h
0x140010a45  mov     rax, cs:__security_cookie
0x140010a4c  xor     rax, rsp
0x140010a4f  mov     [rbp+50h+var_50], rax
0x140010a53  mov     r14, r9
0x140010a56  mov     rsi, r8
0x140010a59  mov     rdi, rdx
0x140010a5c  mov     r15, rcx
0x140010a5f  xor     r13d, r13d
0x140010a62  mov     qword ptr [rsp+150h+var_F0], r13
0x140010a67  mov     [rsp+150h+var_E8], 258h
0x140010a6f  mov     [rsp+150h+var_E4], 1
0x140010a74  mov     [rsp+150h+var_E0], 1Eh
0x140010a7d  mov     [rsp+150h+var_118], r13
0x140010a82  xorps   xmm0, xmm0
0x140010a85  movups  xmmword ptr [rbp+50h+Uuid.Data1], xmm0
0x140010a89  mov     [rsp+150h+StringUuid], r13
0x140010a8e  mov     [rsp+150h+var_11F], r13b
0x140010a93  mov     r12b, r13b
0x140010a96  mov     [rsp+150h+var_120], r13b
0x140010a9b  mov     [rsp+150h+lpMem], r13
0x140010aa0  mov     [rsp+150h+var_10C], r13d
0x140010aa5  mov     [rbp+50h+var_78], 7
0x140010aad  mov     [rbp+50h+var_80], r13
0x140010ab1  mov     word ptr [rbp+50h+var_90], r13w
0x140010ab6  mov     [rsp+150h+SessionId], r13d
0x140010abb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140010ac2  movdqu  [rbp+50h+var_70], xmm0
0x140010ac7  mov     [rsp+150h+hMem], r13
0x140010acc  cmp     [rdx+10h], r13
0x140010ad0  jz      loc_140010D72
0x140010ad6  cmp     [r8+10h], r13
0x140010ada  jz      loc_140010D72
0x140010ae0  lea     rcx, [rsp+150h+var_F0]; struct _JobConfig *
0x140010ae5  call    ?GetJobConfig@JobHelper@@SAJAEAU_JobConfig@@@Z; JobHelper::GetJobConfig(_JobConfig &)
0x140010aea  mov     ebx, eax
0x140010aec  test    eax, eax
0x140010aee  js      loc_140010D77
0x140010af4  lea     rax, [rsp+150h+lpMem]
0x140010af9  mov     qword ptr [rsp+150h+var_130], rax
0x140010afe  lea     r9, [rbp+50h+var_70]
0x140010b02  lea     r8, [rsp+150h+var_11F]
0x140010b07  lea     rdx, [rbp+50h+var_90]
0x140010b0b  lea     rcx, [rsp+150h+var_10C]
0x140010b10  call    ?GetMDMClientCert@@YAJAEAW4BG_CERT_STORE_LOCATION@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_NAEAU_GUID@@PEAPEAG@Z; GetMDMClientCert(BG_CERT_STORE_LOCATION &,std::wstring &,bool &,_GUID &,ushort * *)
0x140010b15  mov     ebx, eax
0x140010b17  test    eax, eax
0x140010b19  js      loc_140010D77
0x140010b1f  movaps  xmm0, [rbp+50h+var_70]
0x140010b23  movdqa  xmmword ptr [rbp+50h+var_D0.Data1], xmm0
0x140010b28  lea     rdx, [rsp+150h+hMem]; unsigned __int16 **
0x140010b2d  lea     rcx, [rbp+50h+var_D0]; struct _GUID
0x140010b31  call    ?FetchUserAadToken@@YAJU_GUID@@PEAPEAG@Z; FetchUserAadToken(_GUID,ushort * *)
0x140010b36  mov     ebx, eax
0x140010b38  test    eax, eax
0x140010b3a  js      loc_140010D77
0x140010b40  cmp     [rsp+150h+var_11F], r13b
0x140010b45  jz      short loc_140010B9A
0x140010b47  mov     rdx, [rsp+150h+lpMem]
0x140010b4c  lea     rcx, [rbp+50h+var_D0]
0x140010b50  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140010b55  lea     rdx, [rsp+150h+SessionId]
0x140010b5a  mov     rcx, rax; String2
0x140010b5d  call    ?FindSessionIDFromUserSid@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK@Z; FindSessionIDFromUserSid(std::wstring,ulong &)
0x140010b62  mov     ebx, eax
0x140010b64  test    eax, eax
0x140010b66  js      loc_140010D77
0x140010b6c  mov     rdx, [rsp+150h+lpMem]
0x140010b71  lea     rcx, [rbp+50h+var_B0]
0x140010b75  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140010b7a  lea     r8, [rsp+150h+var_120]
0x140010b7f  mov     edx, [rsp+150h+SessionId]; SessionId
0x140010b83  mov     rcx, rax; String2
0x140010b86  call    ?ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z; ImpersonateUser(std::wstring,ulong,bool &)
0x140010b8b  mov     ebx, eax
0x140010b8d  mov     r12b, [rsp+150h+var_120]
0x140010b92  test    eax, eax
0x140010b94  js      loc_140010D77
0x140010b9a  lea     r9, [rbp+50h+Uuid]; struct _GUID *
0x140010b9e  lea     r8, [rsp+150h+var_118]; struct IBackgroundCopyJob **
0x140010ba3  lea     rdx, ?copyManager@JobExecution@@0V?$CComPtr@UIBackgroundCopyManager@@@ATL@@A; struct IBackgroundCopyManager **
0x140010baa  call    ?CreateDOJob@JobHelper@@SAJPEBGPEAPEAUIBackgroundCopyManager@@PEAPEAUIBackgroundCopyJob@@PEAU_GUID@@@Z; JobHelper::CreateDOJob(ushort const *,IBackgroundCopyManager * *,IBackgroundCopyJob * *,_GUID *)
0x140010baf  mov     ebx, eax
0x140010bb1  test    eax, eax
0x140010bb3  js      loc_140010D77
0x140010bb9  mov     rcx, [rsp+150h+var_118]
0x140010bbe  mov     rax, [rcx]
0x140010bc1  mov     edx, [rsp+150h+var_F0]
0x140010bc5  mov     rax, [rax+0A8h]
0x140010bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010bd1  mov     ebx, eax
0x140010bd3  test    eax, eax
0x140010bd5  js      loc_140010D77
0x140010bdb  mov     rcx, [rsp+150h+var_118]; struct IBackgroundCopyJob *
0x140010be0  call    ?SetDOHelperTokens@@YAJPEAUIBackgroundCopyJob@@H@Z; SetDOHelperTokens(IBackgroundCopyJob *,int)
0x140010be5  mov     edx, eax
0x140010be7  lea     rcx, aSetHelperToken; "Set Helper Tokens for Proxy result= 0x%"...
0x140010bee  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140010bf3  cmp     [rbp+50h+var_80], r13
0x140010bf7  jz      short loc_140010C6D
0x140010bf9  lea     rdx, [rbp+50h+var_90]
0x140010bfd  cmp     [rbp+50h+var_78], 8
0x140010c02  cmovnb  rdx, [rbp+50h+var_90]
0x140010c07  lea     rcx, aSetSecurityOpt; "Set Security Option for CertThumbprint="...
0x140010c0e  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140010c13  lea     r9, [rbp+50h+var_90]
0x140010c17  cmp     [rbp+50h+var_78], 8
0x140010c1c  cmovnb  r9, [rbp+50h+var_90]; unsigned __int16 *
0x140010c21  mov     [rsp+150h+var_128], r12b; bool
0x140010c26  mov     al, [rsp+150h+var_E4]
0x140010c2a  mov     [rsp+150h+var_130], al; bool
0x140010c2e  mov     edx, [rsp+150h+var_10C]; enum BG_CERT_STORE_LOCATION
0x140010c32  mov     rcx, [rsp+150h+var_118]; struct IBackgroundCopyJob *
0x140010c37  call    ?SetSecurityOptions2@@YAJPEAUIBackgroundCopyJob@@W4BG_CERT_STORE_LOCATION@@PEBG2_N3@Z; SetSecurityOptions2(IBackgroundCopyJob *,BG_CERT_STORE_LOCATION,ushort const *,ushort const *,bool,bool)
0x140010c3c  mov     ebx, eax
0x140010c3e  test    eax, eax
0x140010c40  js      loc_140010D77
0x140010c46  lea     rcx, aSuccessfullyDo; "Successfully done"
0x140010c4d  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140010c52  mov     rdx, [rsp+150h+hMem]; unsigned __int16 *
0x140010c57  mov     rcx, [rsp+150h+var_118]; struct IBackgroundCopyJob *
0x140010c5c  call    ?AttachUserAadToken@@YAJPEAUIBackgroundCopyJob@@PEBG@Z; AttachUserAadToken(IBackgroundCopyJob *,ushort const *)
0x140010c61  mov     ebx, eax
0x140010c63  test    eax, eax
0x140010c65  js      loc_140010D77
0x140010c6b  jmp     short loc_140010C79
0x140010c6d  lea     rcx, aCertificateThu; "Certificate thumbprint empty. Skipping "...
0x140010c74  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140010c79  mov     edx, [rsp+150h+var_F0+4]; unsigned int
0x140010c7d  test    edx, edx
0x140010c7f  jz      short loc_140010C95
0x140010c81  mov     rcx, [rsp+150h+var_118]; struct IBackgroundCopyJob *
0x140010c86  call    ?SetCostFlag@@YAJPEAUIBackgroundCopyJob@@K@Z; SetCostFlag(IBackgroundCopyJob *,ulong)
0x140010c8b  mov     ebx, eax
0x140010c8d  test    eax, eax
0x140010c8f  js      loc_140010D77
0x140010c95  cmp     qword ptr [r15+18h], 8
0x140010c9a  jb      short loc_140010C9F
0x140010c9c  mov     r15, [r15]
0x140010c9f  cmp     qword ptr [rdi+18h], 8
0x140010ca4  jb      short loc_140010CAB
0x140010ca6  mov     r8, [rdi]
0x140010ca9  jmp     short loc_140010CAE
0x140010cab  mov     r8, rdi
0x140010cae  cmp     qword ptr [rsi+18h], 8
0x140010cb3  jb      short loc_140010CBA
0x140010cb5  mov     rdx, [rsi]
0x140010cb8  jmp     short loc_140010CBD
0x140010cba  mov     rdx, rsi
0x140010cbd  mov     r9, r15
0x140010cc0  lea     rcx, [rsp+150h+var_118]
0x140010cc5  call    ?AddFile@JobHelper@@SAJAEAV?$CComPtr@UIBackgroundCopyJob@@@ATL@@PEBG11@Z; JobHelper::AddFile(ATL::CComPtr<IBackgroundCopyJob> &,ushort const *,ushort const *,ushort const *)
0x140010cca  mov     ebx, eax
0x140010ccc  test    eax, eax
0x140010cce  js      loc_140010D77
0x140010cd4  mov     rcx, [rsp+150h+var_118]
0x140010cd9  mov     rax, [rcx]
0x140010cdc  mov     rax, [rax+38h]
0x140010ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010ce5  mov     ebx, eax
0x140010ce7  test    eax, eax
0x140010ce9  js      loc_140010D77
0x140010cef  mov     rcx, [rsp+150h+var_118]
0x140010cf4  test    rcx, rcx
0x140010cf7  jz      short loc_140010D0B
0x140010cf9  mov     [rsp+150h+var_118], r13
0x140010cfe  mov     rax, [rcx]
0x140010d01  mov     rax, [rax+10h]
0x140010d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d0a  nop
0x140010d0b  lea     rdx, [rsp+150h+StringUuid]; StringUuid
0x140010d10  lea     rcx, [rbp+50h+Uuid]; Uuid
0x140010d14  call    cs:__imp_UuidToStringW
0x140010d1a  test    eax, eax
0x140010d1c  jz      short loc_140010D25
0x140010d1e  mov     ebx, 80004005h
0x140010d23  jmp     short loc_140010D77
0x140010d25  mov     rcx, [rsp+150h+StringUuid]
0x140010d2a  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x140010d2f  mov     r8, rax
0x140010d32  mov     rdx, rcx
0x140010d35  mov     rcx, r14
0x140010d38  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x140010d3d  cmp     qword ptr [rsi+18h], 8
0x140010d42  jb      short loc_140010D47
0x140010d44  mov     rsi, [rsi]
0x140010d47  cmp     qword ptr [rdi+18h], 8
0x140010d4c  jb      short loc_140010D51
0x140010d4e  mov     rdi, [rdi]
0x140010d51  cmp     qword ptr [r14+18h], 8
0x140010d56  jb      short loc_140010D5B
0x140010d58  mov     r14, [r14]
0x140010d5b  mov     r9, rsi
0x140010d5e  mov     r8, rdi
0x140010d61  mov     rdx, r14
0x140010d64  lea     rcx, aStartedBitsDow; "Started BITS download job %1 with remot"...
0x140010d6b  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140010d70  jmp     short loc_140010D9B
0x140010d72  mov     ebx, 80070057h
0x140010d77  mov     edx, ebx
0x140010d79  lea     rcx, aStartdownloadF; " StartDownload Failed with error = 0x%1"...
0x140010d80  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140010d85  mov     rcx, [rsp+150h+var_118]
0x140010d8a  test    rcx, rcx
0x140010d8d  jz      short loc_140010D9B
0x140010d8f  mov     rax, [rcx]
0x140010d92  mov     rax, [rax+40h]
0x140010d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d9b  mov     rdi, [rsp+150h+lpMem]
0x140010da0  test    rdi, rdi
0x140010da3  jz      short loc_140010DBE
0x140010da5  call    cs:__imp_GetProcessHeap
0x140010dab  mov     r8, rdi; lpMem
0x140010dae  xor     edx, edx; dwFlags
0x140010db0  mov     rcx, rax; hHeap
0x140010db3  call    cs:__imp_HeapFree
0x140010db9  mov     [rsp+150h+lpMem], r13
0x140010dbe  test    r12b, r12b
0x140010dc1  jz      short loc_140010DC9
0x140010dc3  call    cs:__imp_RevertToSelf
0x140010dc9  cmp     [rsp+150h+StringUuid], r13
0x140010dce  jz      short loc_140010DDB
0x140010dd0  lea     rcx, [rsp+150h+StringUuid]; String
0x140010dd5  call    cs:__imp_RpcStringFreeW
0x140010ddb  mov     rcx, [rsp+150h+hMem]; hMem
0x140010de0  call    cs:__imp_LocalFree
0x140010de6  nop
0x140010de7  xor     r8d, r8d
0x140010dea  mov     dl, 1
0x140010dec  lea     rcx, [rbp+50h+var_90]
0x140010df0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140010df5  nop
0x140010df6  lea     rcx, [rsp+150h+var_118]
0x140010dfb  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x140010e00  mov     eax, ebx
0x140010e02  mov     rcx, [rbp+50h+var_50]
0x140010e06  xor     rcx, rsp; StackCookie
0x140010e09  call    __security_check_cookie
0x140010e0e  add     rsp, 118h
0x140010e15  pop     r15
0x140010e17  pop     r14
0x140010e19  pop     r13
0x140010e1b  pop     r12
0x140010e1d  pop     rdi
0x140010e1e  pop     rsi
0x140010e1f  pop     rbx
0x140010e20  pop     rbp
0x140010e21  retn
```
