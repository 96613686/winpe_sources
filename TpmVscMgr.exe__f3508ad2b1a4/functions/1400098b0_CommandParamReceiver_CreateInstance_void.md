# CommandParamReceiver::CreateInstance(void)

- ea: `0x1400098b0`
- end: `0x140009dcf`
- name: `?CreateInstance@CommandParamReceiver@@AEAA?AV?$com_ptr_t@UITpmVirtualSmartCardManager@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `1311`
- prototype: `struct _GUID *__fastcall(HWND, struct _GUID *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008784`
- `0x140009434`

## callees

- `0x140007200`
- `0x14000764c`
- `0x1400076b4`
- `0x140008454`
- `0x1400097c0`
- `0x1400098b0`
- `0x140009f58`
- `0x14000b16c`
- `0x14000bbb8`
- `0x14000cf20`
- `0x14000cf5c`
- `0x140013010`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000994c`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000994c`
- `ADVAPI32!MakeAbsoluteSD` at `0x140009a65`
- `ADVAPI32!MakeAbsoluteSD` at `0x140009bad`
- `ADVAPI32!MakeAbsoluteSD` at `0x140009a65`
- `ADVAPI32!MakeAbsoluteSD` at `0x140009bad`
- `KERNEL32!GetLastError` at `0x14000995c`
- `KERNEL32!GetLastError` at `0x140009a6f`
- `KERNEL32!GetLastError` at `0x140009bb7`
- `KERNEL32!GetLastError` at `0x14000995c`
- `KERNEL32!GetLastError` at `0x140009a6f`
- `KERNEL32!GetLastError` at `0x140009bb7`
- `KERNEL32!LocalFree` at `0x1400099c5`
- `KERNEL32!LocalFree` at `0x140009da9`
- `KERNEL32!LocalFree` at `0x1400099c5`
- `KERNEL32!LocalFree` at `0x140009da9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x140009cd6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x140009cd6`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140009c3d`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140009c3d`

## pseudocode

```c
struct _GUID *__fastcall CommandParamReceiver::CreateInstance(HWND a1, struct _GUID *a2, const struct _GUID *a3)
{
  __int64 v5; // rax
  DWORD LastError; // eax
  unsigned int v7; // eax
  unsigned int v8; // edx
  PSECURITY_DESCRIPTOR v9; // rcx
  DWORD v10; // eax
  int v11; // edi
  unsigned int v12; // eax
  unsigned int v13; // edx
  __int64 v14; // rax
  void *pPrimaryGroup; // r10
  void *pOwner; // r8
  struct _ACL *pSacl; // rcx
  struct _ACL *v18; // r9
  void *v19; // rdx
  DWORD v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // edx
  void *v23; // rcx
  __int64 v24; // rax
  unsigned int v25; // edx
  __int64 v26; // rdi
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  PSECURITY_DESCRIPTOR v31; // rcx
  HRESULT v33; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+64h] [rbp-9Ch]
  int v35; // [rsp+68h] [rbp-98h] BYREF
  int v36; // [rsp+6Ch] [rbp-94h]
  DWORD dwDaclSize; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+74h] [rbp-8Ch] BYREF
  _DWORD v39[2]; // [rsp+78h] [rbp-88h] BYREF
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor; // [rsp+80h] [rbp-80h] BYREF
  int v41; // [rsp+88h] [rbp-78h]
  __int128 v42; // [rsp+90h] [rbp-70h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-60h]
  PSECURITY_DESCRIPTOR *p_pSelfRelativeSecurityDescriptor; // [rsp+A8h] [rbp-58h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+B0h] [rbp-50h] BYREF
  char v46; // [rsp+B8h] [rbp-48h]
  __int128 v47; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v48; // [rsp+D0h] [rbp-30h]
  __int128 v49; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v50; // [rsp+E8h] [rbp-18h]
  __int128 v51; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v52; // [rsp+100h] [rbp+0h]
  __int128 v53; // [rsp+108h] [rbp+8h] BYREF
  __int64 v54; // [rsp+118h] [rbp+18h]
  MULTI_QI pResults; // [rsp+120h] [rbp+20h] BYREF
  GUID *v56; // [rsp+138h] [rbp+38h]
  __int64 v57; // [rsp+140h] [rbp+40h]
  int v58; // [rsp+148h] [rbp+48h] BYREF
  COSERVERINFO pServerInfo; // [rsp+150h] [rbp+50h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _GUID *v61; // [rsp+1B8h] [rbp+B8h]
  DWORD dwOwnerSize; // [rsp+1C0h] [rbp+C0h] BYREF
  DWORD dwSaclSize; // [rsp+1C8h] [rbp+C8h] BYREF

  v61 = a2;
  v35 = 0;
  v36 = 1;
  *(_QWORD *)&a2->Data1 = 0;
  v41 = 1;
  if ( *(_BYTE *)(*(_QWORD *)a1 + 40LL) )
  {
    pSelfRelativeSecurityDescriptor = 0;
    p_pSelfRelativeSecurityDescriptor = &pSelfRelativeSecurityDescriptor;
    SecurityDescriptor = 0;
    v46 = 1;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:BAG:BAD:(A;;CCDCLC;;;WD)", 1u, &SecurityDescriptor, 0) )
    {
      v33 = 0;
      v34 = 1;
    }
    else
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      v33 = LastError;
      v34 = 2;
      v7 = errorlib::error_received<errorlib::scoped_error<winerror_error::tag>>();
      if ( v7 == 87 || v7 == 6 )
        TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)v7, v8);
    }
    errorlib::scoped_error<winerror_error::tag>::throwfailed(&v33);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v33);
    if ( v46 )
    {
      v9 = *p_pSelfRelativeSecurityDescriptor;
      *p_pSelfRelativeSecurityDescriptor = SecurityDescriptor;
      if ( v9 )
        LocalFree(v9);
    }
    v42 = 0;
    v43 = 0;
    v53 = 0;
    v54 = 0;
    v51 = 0;
    v52 = 0;
    v49 = 0;
    v50 = 0;
    v47 = 0;
    v48 = 0;
    dwAbsoluteSecurityDescriptorSize = 0;
    dwDaclSize = 0;
    dwSaclSize = 0;
    dwOwnerSize = 0;
    dwPrimaryGroupSize = 0;
    if ( MakeAbsoluteSD(
           pSelfRelativeSecurityDescriptor,
           0,
           &dwAbsoluteSecurityDescriptorSize,
           0,
           &dwDaclSize,
           0,
           &dwSaclSize,
           0,
           &dwOwnerSize,
           0,
           &dwPrimaryGroupSize) )
    {
      v11 = 0;
      v39[0] = 0;
    }
    else
    {
      v10 = GetLastError();
      if ( v10 )
      {
        v11 = v10;
        v39[0] = v10;
      }
      else
      {
        v11 = 1287;
        v39[0] = 1287;
      }
      v12 = errorlib::error_received<errorlib::scoped_error<winerror_error::tag>>();
      if ( v12 == 87 || v12 == 6 )
        TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)v12, v13);
    }
    v39[1] = 3;
    if ( v11 == 122 )
    {
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::resize(&v42, dwAbsoluteSecurityDescriptorSize);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::resize(&v53, dwDaclSize);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::resize(&v51, dwSaclSize);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::resize(&v49, dwOwnerSize);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::resize(&v47, dwPrimaryGroupSize);
    }
    else
    {
      errorlib::scoped_error<winerror_error::tag>::throwfailed(v39);
      v33 = -2147418113;
      v14 = errorlib::scoped_error<hresult_error::tag>::receive<long>(&v35, &v33);
      errorlib::scoped_error<hresult_error::tag>::throwfailed(v14);
    }
    pPrimaryGroup = (void *)v47;
    if ( (_QWORD)v47 == *((_QWORD *)&v47 + 1) )
      pPrimaryGroup = 0;
    pOwner = (void *)v49;
    if ( (_QWORD)v49 == *((_QWORD *)&v49 + 1) )
      pOwner = 0;
    pSacl = (struct _ACL *)v51;
    if ( (_QWORD)v51 == *((_QWORD *)&v51 + 1) )
      pSacl = 0;
    v18 = (struct _ACL *)v53;
    if ( (_QWORD)v53 == *((_QWORD *)&v53 + 1) )
      v18 = 0;
    v19 = (void *)v42;
    if ( (_QWORD)v42 == *((_QWORD *)&v42 + 1) )
      v19 = 0;
    if ( MakeAbsoluteSD(
           pSelfRelativeSecurityDescriptor,
           v19,
           &dwAbsoluteSecurityDescriptorSize,
           v18,
           &dwDaclSize,
           pSacl,
           &dwSaclSize,
           pOwner,
           &dwOwnerSize,
           pPrimaryGroup,
           &dwPrimaryGroupSize) )
    {
      v33 = 0;
      v34 = 1;
    }
    else
    {
      v20 = GetLastError();
      if ( !v20 )
        v20 = 1287;
      v33 = v20;
      v34 = 2;
      v21 = errorlib::error_received<errorlib::scoped_error<winerror_error::tag>>();
      if ( v21 == 87 || v21 == 6 )
        TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)v21, v22);
    }
    errorlib::scoped_error<winerror_error::tag>::throwfailed(&v33);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v33);
    v23 = (void *)v42;
    if ( (_QWORD)v42 == *((_QWORD *)&v42 + 1) )
      v23 = 0;
    v33 = CoInitializeSecurity(v23, -1, 0, 0, 6u, 3u, 0, 0, 0);
    v24 = errorlib::scoped_error<hresult_error::tag>::receive<long>(&v35, &v33);
    errorlib::scoped_error<hresult_error::tag>::throwfailed(v24);
    memset(&pServerInfo, 0, sizeof(pServerInfo));
    v26 = *(_QWORD *)a1 + 8LL;
    if ( !*(_BYTE *)(*(_QWORD *)a1 + 40LL) )
      TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, v25);
    if ( *(_QWORD *)(v26 + 24) > 7u )
      v26 = *(_QWORD *)v26;
    pServerInfo.pwszName = (LPWSTR)v26;
    pResults.pIID = &IID_ITpmVirtualSmartCardManager;
    pResults.pItf = 0;
    pResults.hr = 0;
    v56 = &IID_ITpmVirtualSmartCardManager2;
    v57 = 0;
    v58 = 0;
    v33 = CoCreateInstanceEx(&CLSID_RemoteTpmVirtualSmartCardManager, 0, 0x10u, &pServerInfo, 2u, &pResults);
    v27 = errorlib::scoped_error<hresult_error::tag>::receive<long>(&v35, &v33);
    errorlib::scoped_error<hresult_error::tag>::throwfailed(v27);
    v28 = errorlib::scoped_error<hresult_error::tag>::receive<long &>(&v35, &pResults.hr);
    errorlib::scoped_error<hresult_error::tag>::throwfailed(v28);
    v29 = *(_QWORD *)&a2->Data1;
    *(_QWORD *)&a2->Data1 = pResults.pItf;
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    errorlib::scoped_error<hresult_error::tag>::receive<long &>(&v35, &v58);
    v36 = 3;
    if ( v35 >= 0 )
    {
      v30 = *(_QWORD *)&a2->Data1;
      *(_QWORD *)&a2->Data1 = v57;
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v39);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v47);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v49);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v51);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v53);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v42);
    v31 = pSelfRelativeSecurityDescriptor;
    pSelfRelativeSecurityDescriptor = 0;
    if ( v31 )
      LocalFree(v31);
  }
  else
  {
    *(_QWORD *)&a2->Data1 = 0;
    dwPrimaryGroupSize = CoCreateInstanceAsAdmin(a1, a2, a3, (void **)a2);
    v5 = errorlib::scoped_error<hresult_error::tag>::receive<long>(&v35, &dwPrimaryGroupSize);
    errorlib::scoped_error<hresult_error::tag>::throwfailed(v5);
  }
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v35);
  return a2;
}

```

## disassembly

```asm
0x1400098b0  mov     [rsp-8+arg_8], rdx
0x1400098b5  push    rbp
0x1400098b6  push    rbx
0x1400098b7  push    rsi
0x1400098b8  push    rdi
0x1400098b9  push    r12
0x1400098bb  push    r14
0x1400098bd  push    r15
0x1400098bf  lea     rbp, [rsp-70h]
0x1400098c4  sub     rsp, 170h
0x1400098cb  mov     rbx, rdx
0x1400098ce  mov     rsi, rcx
0x1400098d1  mov     r15d, 1
0x1400098d7  mov     [rbp+0A0h+var_118], r15d
0x1400098db  xor     r14d, r14d
0x1400098de  mov     [rsp+1A0h+var_138], r14d
0x1400098e3  mov     [rsp+1A0h+var_134], r15d
0x1400098e8  mov     [rdx], r14
0x1400098eb  mov     [rbp+0A0h+var_118], r15d
0x1400098ef  mov     rax, [rcx]
0x1400098f2  cmp     [rax+28h], r14b
0x1400098f6  jnz     short loc_140009927
0x1400098f8  mov     [rdx], r14
0x1400098fb  mov     r9, rdx; void **
0x1400098fe  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x140009903  mov     [rbp+0A0h+dwPrimaryGroupSize], eax
0x140009909  lea     rdx, [rbp+0A0h+dwPrimaryGroupSize]
0x140009910  lea     rcx, [rsp+1A0h+var_138]
0x140009915  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x14000991a  mov     rcx, rax
0x14000991d  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x140009922  jmp     loc_140009DB0
0x140009927  mov     [rbp+0A0h+pSelfRelativeSecurityDescriptor], r14
0x14000992b  lea     rax, [rbp+0A0h+pSelfRelativeSecurityDescriptor]
0x14000992f  mov     [rbp+0A0h+var_F8], rax
0x140009933  mov     [rbp+0A0h+SecurityDescriptor], r14
0x140009937  mov     [rbp+0A0h+var_E8], r15b
0x14000993b  xor     r9d, r9d; SecurityDescriptorSize
0x14000993e  lea     r8, [rbp+0A0h+SecurityDescriptor]; SecurityDescriptor
0x140009942  mov     edx, r15d; StringSDRevision
0x140009945  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;CCDCLC;;;WD)"
0x14000994c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140009952  mov     r12d, 507h
0x140009958  test    eax, eax
0x14000995a  jnz     short loc_14000998C
0x14000995c  call    cs:__imp_GetLastError
0x140009962  test    eax, eax
0x140009964  cmovz   eax, r12d
0x140009968  mov     [rsp+1A0h+var_140], eax
0x14000996c  mov     [rsp+1A0h+var_13C], 2
0x140009974  call    ??$error_received@V?$scoped_error@Utag@winerror_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@winerror_error@@@0@AEBUtag@winerror_error@@@Z; errorlib::error_received<errorlib::scoped_error<winerror_error::tag>>(errorlib::scoped_error<winerror_error::tag> const &,winerror_error::tag const &)
0x140009979  cmp     eax, 57h ; 'W'
0x14000997c  jz      short loc_140009983
0x14000997e  cmp     eax, 6
0x140009981  jnz     short loc_140009996
0x140009983  mov     ecx, eax; this
0x140009985  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x14000998a  jmp     short loc_140009996
0x14000998c  mov     [rsp+1A0h+var_140], r14d
0x140009991  mov     [rsp+1A0h+var_13C], r15d
0x140009996  lea     rcx, [rsp+1A0h+var_140]
0x14000999b  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x1400099a0  nop
0x1400099a1  lea     rcx, [rsp+1A0h+var_140]
0x1400099a6  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1400099ab  nop
0x1400099ac  cmp     [rbp+0A0h+var_E8], r14b
0x1400099b0  jz      short loc_1400099CB
0x1400099b2  mov     rdx, [rbp+0A0h+var_F8]
0x1400099b6  mov     rcx, [rdx]; hMem
0x1400099b9  mov     rax, [rbp+0A0h+SecurityDescriptor]
0x1400099bd  mov     [rdx], rax
0x1400099c0  test    rcx, rcx
0x1400099c3  jz      short loc_1400099CB
0x1400099c5  call    cs:__imp_LocalFree
0x1400099cb  xorps   xmm0, xmm0
0x1400099ce  movdqu  [rbp+0A0h+var_110], xmm0
0x1400099d3  mov     [rbp+0A0h+var_100], r14
0x1400099d7  movdqu  [rbp+0A0h+var_98], xmm0
0x1400099dc  mov     [rbp+0A0h+var_88], r14
0x1400099e0  movdqu  [rbp+0A0h+var_B0], xmm0
0x1400099e5  mov     [rbp+0A0h+var_A0], r14
0x1400099e9  movdqu  [rbp+0A0h+var_C8], xmm0
0x1400099ee  mov     [rbp+0A0h+var_B8], r14
0x1400099f2  movdqu  [rbp+0A0h+var_E0], xmm0
0x1400099f7  mov     [rbp+0A0h+var_D0], r14
0x1400099fb  mov     [rsp+1A0h+dwAbsoluteSecurityDescriptorSize], r14d
0x140009a00  mov     [rsp+1A0h+dwDaclSize], r14d
0x140009a05  mov     [rbp+0A0h+dwSaclSize], r14d
0x140009a0c  mov     [rbp+0A0h+dwOwnerSize], r14d
0x140009a13  mov     [rbp+0A0h+dwPrimaryGroupSize], r14d
0x140009a1a  lea     rax, [rbp+0A0h+dwPrimaryGroupSize]
0x140009a21  mov     [rsp+1A0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140009a26  mov     [rsp+1A0h+pPrimaryGroup], r14; pPrimaryGroup
0x140009a2b  lea     rax, [rbp+0A0h+dwOwnerSize]
0x140009a32  mov     [rsp+1A0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140009a37  mov     [rsp+1A0h+pOwner], r14; pOwner
0x140009a3c  lea     rax, [rbp+0A0h+dwSaclSize]
0x140009a43  mov     [rsp+1A0h+lpdwSaclSize], rax; lpdwSaclSize
0x140009a48  mov     [rsp+1A0h+pSacl], r14; pSacl
0x140009a4d  lea     rax, [rsp+1A0h+dwDaclSize]
0x140009a52  mov     [rsp+1A0h+lpdwDaclSize], rax; lpdwDaclSize
0x140009a57  xor     r9d, r9d; pDacl
0x140009a5a  lea     r8, [rsp+1A0h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140009a5f  xor     edx, edx; pAbsoluteSecurityDescriptor
0x140009a61  mov     rcx, [rbp+0A0h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x140009a65  call    cs:__imp_MakeAbsoluteSD
0x140009a6b  test    eax, eax
0x140009a6d  jnz     short loc_140009AA4
0x140009a6f  call    cs:__imp_GetLastError
0x140009a75  test    eax, eax
0x140009a77  jnz     short loc_140009A86
0x140009a79  mov     eax, r12d
0x140009a7c  mov     edi, r12d
0x140009a7f  mov     [rsp+1A0h+var_128], r12d
0x140009a84  jmp     short loc_140009A8C
0x140009a86  mov     edi, eax
0x140009a88  mov     [rsp+1A0h+var_128], eax
0x140009a8c  call    ??$error_received@V?$scoped_error@Utag@winerror_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@winerror_error@@@0@AEBUtag@winerror_error@@@Z; errorlib::error_received<errorlib::scoped_error<winerror_error::tag>>(errorlib::scoped_error<winerror_error::tag> const &,winerror_error::tag const &)
0x140009a91  cmp     eax, 57h ; 'W'
0x140009a94  jz      short loc_140009A9B
0x140009a96  cmp     eax, 6
0x140009a99  jnz     short loc_140009AAC
0x140009a9b  mov     ecx, eax; this
0x140009a9d  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x140009aa2  jmp     short loc_140009AAC
0x140009aa4  mov     edi, r14d
0x140009aa7  mov     [rsp+1A0h+var_128], r14d
0x140009aac  mov     [rsp+1A0h+var_124], 3
0x140009ab4  cmp     edi, 7Ah ; 'z'
0x140009ab7  jnz     short loc_140009B02
0x140009ab9  mov     edx, [rsp+1A0h+dwAbsoluteSecurityDescriptorSize]
0x140009abd  lea     rcx, [rbp+0A0h+var_110]
0x140009ac1  call    ?resize@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAX_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::resize(unsigned __int64)
0x140009ac6  mov     edx, [rsp+1A0h+dwDaclSize]
0x140009aca  lea     rcx, [rbp+0A0h+var_98]
0x140009ace  call    ?resize@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAX_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::resize(unsigned __int64)
0x140009ad3  mov     edx, [rbp+0A0h+dwSaclSize]
0x140009ad9  lea     rcx, [rbp+0A0h+var_B0]
0x140009add  call    ?resize@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAX_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::resize(unsigned __int64)
0x140009ae2  mov     edx, [rbp+0A0h+dwOwnerSize]
0x140009ae8  lea     rcx, [rbp+0A0h+var_C8]
0x140009aec  call    ?resize@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAX_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::resize(unsigned __int64)
0x140009af1  mov     edx, [rbp+0A0h+dwPrimaryGroupSize]
0x140009af7  lea     rcx, [rbp+0A0h+var_E0]
0x140009afb  call    ?resize@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAX_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::resize(unsigned __int64)
0x140009b00  jmp     short loc_140009B2B
0x140009b02  lea     rcx, [rsp+1A0h+var_128]
0x140009b07  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x140009b0c  mov     [rsp+1A0h+var_140], 8000FFFFh
0x140009b14  lea     rdx, [rsp+1A0h+var_140]
0x140009b19  lea     rcx, [rsp+1A0h+var_138]
0x140009b1e  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x140009b23  mov     rcx, rax
0x140009b26  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x140009b2b  mov     r10, qword ptr [rbp+0A0h+var_E0]
0x140009b2f  cmp     r10, qword ptr [rbp+0A0h+var_E0+8]
0x140009b33  cmovz   r10, r14
0x140009b37  mov     r8, qword ptr [rbp+0A0h+var_C8]
0x140009b3b  cmp     r8, qword ptr [rbp+0A0h+var_C8+8]
0x140009b3f  cmovz   r8, r14
0x140009b43  mov     rcx, qword ptr [rbp+0A0h+var_B0]
0x140009b47  cmp     rcx, qword ptr [rbp+0A0h+var_B0+8]
0x140009b4b  cmovz   rcx, r14
0x140009b4f  mov     r9, qword ptr [rbp+0A0h+var_98]
0x140009b53  cmp     r9, qword ptr [rbp+0A0h+var_98+8]
0x140009b57  cmovz   r9, r14; pDacl
0x140009b5b  mov     rdx, qword ptr [rbp+0A0h+var_110]
0x140009b5f  cmp     rdx, qword ptr [rbp+0A0h+var_110+8]
0x140009b63  cmovz   rdx, r14; pAbsoluteSecurityDescriptor
0x140009b67  lea     rax, [rbp+0A0h+dwPrimaryGroupSize]
0x140009b6e  mov     [rsp+1A0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140009b73  mov     [rsp+1A0h+pPrimaryGroup], r10; pPrimaryGroup
0x140009b78  lea     rax, [rbp+0A0h+dwOwnerSize]
0x140009b7f  mov     [rsp+1A0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140009b84  mov     [rsp+1A0h+pOwner], r8; pOwner
0x140009b89  lea     rax, [rbp+0A0h+dwSaclSize]
0x140009b90  mov     [rsp+1A0h+lpdwSaclSize], rax; lpdwSaclSize
0x140009b95  mov     [rsp+1A0h+pSacl], rcx; pSacl
0x140009b9a  lea     rax, [rsp+1A0h+dwDaclSize]
0x140009b9f  mov     [rsp+1A0h+lpdwDaclSize], rax; lpdwDaclSize
0x140009ba4  lea     r8, [rsp+1A0h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140009ba9  mov     rcx, [rbp+0A0h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x140009bad  call    cs:__imp_MakeAbsoluteSD
0x140009bb3  test    eax, eax
0x140009bb5  jnz     short loc_140009BE7
0x140009bb7  call    cs:__imp_GetLastError
0x140009bbd  test    eax, eax
0x140009bbf  cmovz   eax, r12d
0x140009bc3  mov     [rsp+1A0h+var_140], eax
0x140009bc7  mov     [rsp+1A0h+var_13C], 2
0x140009bcf  call    ??$error_received@V?$scoped_error@Utag@winerror_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@winerror_error@@@0@AEBUtag@winerror_error@@@Z; errorlib::error_received<errorlib::scoped_error<winerror_error::tag>>(errorlib::scoped_error<winerror_error::tag> const &,winerror_error::tag const &)
0x140009bd4  cmp     eax, 57h ; 'W'
0x140009bd7  jz      short loc_140009BDE
0x140009bd9  cmp     eax, 6
0x140009bdc  jnz     short loc_140009BF1
0x140009bde  mov     ecx, eax; this
0x140009be0  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x140009be5  jmp     short loc_140009BF1
0x140009be7  mov     [rsp+1A0h+var_140], r14d
0x140009bec  mov     [rsp+1A0h+var_13C], r15d
0x140009bf1  lea     rcx, [rsp+1A0h+var_140]
0x140009bf6  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x140009bfb  nop
0x140009bfc  lea     rcx, [rsp+1A0h+var_140]
0x140009c01  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x140009c06  mov     rcx, qword ptr [rbp+0A0h+var_110]
0x140009c0a  cmp     rcx, qword ptr [rbp+0A0h+var_110+8]
0x140009c0e  cmovz   rcx, r14; pSecDesc
0x140009c12  mov     [rsp+1A0h+lpdwOwnerSize], r14; pReserved3
0x140009c17  mov     dword ptr [rsp+1A0h+pOwner], r14d; dwCapabilities
0x140009c1c  mov     [rsp+1A0h+lpdwSaclSize], r14; pAuthList
0x140009c21  mov     r15d, 3
0x140009c27  mov     dword ptr [rsp+1A0h+pSacl], r15d; dwImpLevel
0x140009c2c  mov     dword ptr [rsp+1A0h+lpdwDaclSize], 6; dwAuthnLevel
0x140009c34  xor     r9d, r9d; pReserved1
0x140009c37  xor     r8d, r8d; asAuthSvc
0x140009c3a  or      edx, 0FFFFFFFFh; cAuthSvc
0x140009c3d  call    cs:__imp_CoInitializeSecurity
0x140009c43  mov     [rsp+1A0h+var_140], eax
0x140009c47  lea     rdx, [rsp+1A0h+var_140]
0x140009c4c  lea     rcx, [rsp+1A0h+var_138]
0x140009c51  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x140009c56  mov     rcx, rax
0x140009c59  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x140009c5e  xorps   xmm0, xmm0
0x140009c61  movups  xmmword ptr [rbp+0A0h+pServerInfo.dwReserved1], xmm0
0x140009c65  movups  xmmword ptr [rbp+0A0h+pServerInfo.pAuthInfo], xmm0
0x140009c69  mov     rdi, [rsi]
0x140009c6c  add     rdi, 8
0x140009c70  cmp     [rdi+20h], r14b
0x140009c74  jnz     short loc_140009C80
0x140009c76  mov     ecx, 80004004h; this
0x140009c7b  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x140009c80  cmp     qword ptr [rdi+18h], 7
0x140009c85  jbe     short loc_140009C8A
0x140009c87  mov     rdi, [rdi]
0x140009c8a  mov     [rbp+0A0h+pServerInfo.pwszName], rdi
0x140009c8e  lea     rax, IID_ITpmVirtualSmartCardManager
0x140009c95  mov     [rbp+0A0h+pResults.pIID], rax
0x140009c99  mov     [rbp+0A0h+pResults.pItf], r14
0x140009c9d  mov     [rbp+0A0h+pResults.hr], r14d
0x140009ca1  lea     rax, IID_ITpmVirtualSmartCardManager2
0x140009ca8  mov     [rbp+0A0h+var_68], rax
0x140009cac  mov     [rbp+0A0h+var_60], r14
0x140009cb0  mov     [rbp+0A0h+var_58], r14d
0x140009cb4  lea     rax, [rbp+0A0h+pResults]
0x140009cb8  mov     [rsp+1A0h+pSacl], rax; pResults
0x140009cbd  mov     dword ptr [rsp+1A0h+lpdwDaclSize], 2; dwCount
0x140009cc5  lea     r9, [rbp+0A0h+pServerInfo]; pServerInfo
0x140009cc9  xor     edx, edx; punkOuter
0x140009ccb  lea     r8d, [rdx+10h]; dwClsCtx
0x140009ccf  lea     rcx, CLSID_RemoteTpmVirtualSmartCardManager; Clsid
0x140009cd6  call    cs:__imp_CoCreateInstanceEx
0x140009cdc  mov     [rsp+1A0h+var_140], eax
0x140009ce0  lea     rdx, [rsp+1A0h+var_140]
0x140009ce5  lea     rcx, [rsp+1A0h+var_138]
0x140009cea  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x140009cef  mov     rcx, rax
0x140009cf2  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x140009cf7  lea     rdx, [rbp+0A0h+pResults.hr]
0x140009cfb  lea     rcx, [rsp+1A0h+var_138]
0x140009d00  call    ??$receive@AEAJ@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@AEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long &>(long &)
0x140009d05  mov     rcx, rax
0x140009d08  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x140009d0d  mov     rax, [rbp+0A0h+pResults.pItf]
0x140009d11  mov     rcx, [rbx]
0x140009d14  mov     [rbx], rax
0x140009d17  test    rcx, rcx
0x140009d1a  jz      short loc_140009D29
0x140009d1c  mov     rax, [rcx]
0x140009d1f  mov     rax, [rax+10h]
0x140009d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d28  nop
0x140009d29  lea     rdx, [rbp+0A0h+var_58]
0x140009d2d  lea     rcx, [rsp+1A0h+var_138]
0x140009d32  call    ??$receive@AEAJ@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@AEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long &>(long &)
0x140009d37  mov     [rsp+1A0h+var_134], r15d
0x140009d3c  cmp     [rsp+1A0h+var_138], r14d
0x140009d41  jl      short loc_140009D5F
0x140009d43  mov     rax, [rbp+0A0h+var_60]
0x140009d47  mov     rcx, [rbx]
0x140009d4a  mov     [rbx], rax
0x140009d4d  test    rcx, rcx
0x140009d50  jz      short loc_140009D5F
0x140009d52  mov     rax, [rcx]
0x140009d55  mov     rax, [rax+10h]
0x140009d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d5e  nop
0x140009d5f  lea     rcx, [rsp+1A0h+var_128]
0x140009d64  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x140009d69  nop
0x140009d6a  lea     rcx, [rbp+0A0h+var_E0]
0x140009d6e  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x140009d73  nop
0x140009d74  lea     rcx, [rbp+0A0h+var_C8]
0x140009d78  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x140009d7d  nop
0x140009d7e  lea     rcx, [rbp+0A0h+var_B0]
0x140009d82  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
  ... truncated ...
```
