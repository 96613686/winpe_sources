# EnterpriseWorkerThread::ProcessNewRequest(void)

- ea: `0x180017368`
- end: `0x180017739`
- name: `?ProcessNewRequest@EnterpriseWorkerThread@@AEAAJXZ`
- size: `977`
- prototype: `__int64 __fastcall(EnterpriseWorkerThread *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800167f8`

## callees

- `0x180002514`
- `0x180012d54`
- `0x180012d84`
- `0x180013ddc`
- `0x180014cdc`
- `0x180017368`
- `0x18001845c`
- `0x180018518`
- `0x180018d9c`
- `0x18001a374`
- `0x18001b210`
- `0x18001b2bc`
- `0x18001b4bc`
- `0x180027cbc`
- `0x180027d1c`
- `0x180027dc0`
- `0x1800280e8`
- `0x180066df0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180017704`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180017704`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180017534`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180017534`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017562`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017562`
- `OLEAUT32!__imp_SysFreeString` at `0x180017681`
- `OLEAUT32!__imp_SysFreeString` at `0x1800176eb`
- `OLEAUT32!__imp_SysFreeString` at `0x180017681`
- `OLEAUT32!__imp_SysFreeString` at `0x1800176eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800176f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800176f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800173b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800173b6`

## pseudocode

```c
__int64 __fastcall EnterpriseWorkerThread::ProcessNewRequest(EnterpriseWorkerThread *this)
{
  void **v2; // rax
  __int64 v3; // rcx
  int updated; // edi
  unsigned int v5; // esi
  IID v6; // xmm6
  unsigned __int16 *v7; // rbx
  void **v8; // rax
  int v9; // eax
  __int64 v10; // rcx
  OLECHAR *v11; // rcx
  LPVOID pv; // [rsp+38h] [rbp-99h] BYREF
  __int64 v14; // [rsp+40h] [rbp-91h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-89h]
  _WORD *v16; // [rsp+50h] [rbp-81h]
  _WORD v17[8]; // [rsp+58h] [rbp-79h] BYREF
  int v18; // [rsp+68h] [rbp-69h] BYREF
  unsigned __int16 *v19[2]; // [rsp+70h] [rbp-61h] BYREF
  _WORD v20[8]; // [rsp+80h] [rbp-51h] BYREF
  _OWORD *v21; // [rsp+90h] [rbp-41h] BYREF
  struct HBTSREQUEST__ *v22; // [rsp+98h] [rbp-39h] BYREF
  _BYTE v23[24]; // [rsp+A0h] [rbp-31h] BYREF
  IID rclsid; // [rsp+B8h] [rbp-19h] BYREF
  struct HBTSREQUEST__ *v25; // [rsp+C8h] [rbp-9h]
  GUID v26; // [rsp+D8h] [rbp+7h] BYREF

  v21 = 0;
  LODWORD(v14) = 0;
  v18 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v2 = tlx::replace<_GUID,&void tlx::_delete_array<_GUID>(_GUID *)>((void **)&v21);
  updated = EnrollmentManager::EnumeratePrimaryKeys(v3, (GUID **)v2, (DWORD *)&v14);
  if ( updated < 0 )
    goto LABEL_40;
  v5 = 0;
  if ( !(_DWORD)v14 )
    goto LABEL_40;
  while ( 1 )
  {
    v6 = (IID)v21[v5];
    v7 = 0;
    pv = 0;
    v26 = v6;
    updated = EnrollmentManager::RetrieveByte(2LL * v5, &v26, 7, &v18);
    if ( updated < 0 )
    {
      v11 = 0;
      goto LABEL_39;
    }
    if ( v18 != 1 )
      goto LABEL_27;
    lpFileName = v17;
    v16 = v17;
    v17[0] = 0;
    v26 = v6;
    updated = EnrollmentManager::RetrieveBSTR(1, &v26, 5, &pv);
    if ( updated < 0 )
      break;
    v7 = (unsigned __int16 *)pv;
    if ( (unsigned int)RemoteUrl((LPCWSTR)pv) )
    {
      v22 = 0;
      v19[0] = v20;
      v19[1] = v20;
      v20[0] = 0;
      v26 = GUID_NULL;
      LODWORD(pv) = 0;
      updated = DetermineInstallFileType(v7, (enum EnterpriseFileType *)&pv);
      if ( updated < 0 )
        goto LABEL_29;
      rclsid = v6;
      updated = GenerateDestinationFileName(&rclsid);
      if ( updated < 0 )
        goto LABEL_29;
      DeleteLocalFile(lpFileName);
      rclsid = v6;
      updated = EnrollmentManager::RetrieveGUID(1u, (__int64)&rclsid, 3, &v26);
      if ( updated < 0 )
        goto LABEL_29;
      rclsid = v6;
      pv = 0;
      v8 = tlx::replace<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>(&pv);
      updated = StringFromCLSID(&rclsid, (LPOLESTR *)v8);
      if ( updated >= 0
        && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               v19,
                               pv) )
      {
        updated = -2147024882;
      }
      if ( pv )
        CoTaskMemFree(pv);
      if ( updated < 0 )
        goto LABEL_29;
      rclsid = v26;
      v9 = EnterpriseWorkerThread::DownloadXap(this, &rclsid, v7, lpFileName, v19[0], &v22);
      rclsid = v6;
      if ( v9 >= 0 )
      {
        updated = EnterpriseWorkerThread::UpdateLocalUriField(v10, &rclsid, lpFileName);
        if ( updated < 0 )
          goto LABEL_29;
        if ( v22 )
        {
          rclsid = v6;
          v25 = v22;
          if ( !*(_QWORD *)utl::_Tree<_GUID,utl::pair<_GUID const,HBTSREQUEST__ *>,memory_compare_less<_GUID>,utl::allocator<utl::pair<_GUID const,HBTSREQUEST__ *>>,0>::insert<utl::pair<_GUID,HBTSREQUEST__ *>,0>(
                             (__int64)this + 136,
                             (__int64)v23,
                             &rclsid) )
          {
            updated = -2147024882;
LABEL_29:
            if ( v19[0] != v20 )
              operator delete(v19[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_31:
            if ( lpFileName != v17 )
              operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
            v11 = v7;
            goto LABEL_39;
          }
        }
      }
      else
      {
        updated = EnterpriseWorkerThread::UpdateXAPRequestStatus(this, &rclsid, 7);
        if ( updated < 0 )
          goto LABEL_29;
        updated = 0;
      }
      if ( v19[0] != v20 )
        operator delete(v19[0], (const struct std::nothrow_t *)&std::nothrow);
    }
    else
    {
      rclsid = v6;
      updated = EnterpriseWorkerThread::UpdateXAPRequestStatus(this, &rclsid, 3);
      if ( updated < 0 )
        goto LABEL_31;
    }
    if ( lpFileName != v17 )
      operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
LABEL_27:
    SysFreeString(v7);
    if ( ++v5 >= (unsigned int)v14 )
      goto LABEL_40;
  }
  if ( lpFileName != v17 )
    operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  v11 = (OLECHAR *)pv;
LABEL_39:
  SysFreeString(v11);
LABEL_40:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( v21 )
    operator delete[](v21);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180017368  mov     rax, rsp
0x18001736b  mov     [rax+10h], rbx
0x18001736f  mov     [rax+18h], rsi
0x180017373  push    rbp
0x180017374  push    rdi
0x180017375  push    r12
0x180017377  push    r13
0x180017379  push    r14
0x18001737b  lea     rbp, [rax-5Fh]
0x18001737f  sub     rsp, 100h
0x180017386  movaps  xmmword ptr [rax-38h], xmm6
0x18001738a  mov     rax, cs:__security_cookie
0x180017391  xor     rax, rsp
0x180017394  mov     [rbp+57h+var_40], rax
0x180017398  mov     r14, rcx
0x18001739b  mov     [rbp+57h+var_98], 0
0x1800173a3  mov     dword ptr [rsp+120h+var_E8], 0
0x1800173ab  mov     [rbp+57h+var_C0], 1
0x1800173b2  add     rcx, 58h ; 'X'; lpCriticalSection
0x1800173b6  call    cs:__imp_EnterCriticalSection
0x1800173bc  lea     rcx, [rbp+57h+var_98]
0x1800173c0  call    ??$replace@U_GUID@@$1??$_delete_array@U_GUID@@@tlx@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_GUID@@AEAV?$auto_array_ptr@U_GUID@@$1??$_delete_array@U_GUID@@@tlx@@YAXPEAU1@@Z@0@@Z; tlx::replace<_GUID,&tlx::_delete_array<_GUID>(_GUID *)>(tlx::auto_array_ptr<_GUID,&tlx::_delete_array<_GUID>(_GUID *)> &)
0x1800173c5  mov     rdx, rax
0x1800173c8  lea     r8, [rsp+120h+var_E8]
0x1800173cd  call    ?EnumeratePrimaryKeys@EnrollmentManager@@SAJW4TABLEID@@PEAPEAU_GUID@@AEAK@Z; EnrollmentManager::EnumeratePrimaryKeys(TABLEID,_GUID * *,ulong &)
0x1800173d2  mov     edi, eax
0x1800173d4  test    eax, eax
0x1800173d6  js      loc_1800176F1
0x1800173dc  xor     esi, esi
0x1800173de  cmp     dword ptr [rsp+120h+var_E8], esi
0x1800173e2  jbe     loc_1800176F1
0x1800173e8  lea     r13, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800173ef  mov     ecx, esi
0x1800173f1  add     rcx, rcx
0x1800173f4  mov     rax, [rbp+57h+var_98]
0x1800173f8  movups  xmm6, xmmword ptr [rax+rcx*8]
0x1800173fc  xor     ebx, ebx
0x1800173fe  mov     [rsp+120h+pv], rbx
0x180017403  movdqu  [rbp+57h+var_50], xmm6
0x180017408  lea     r8d, [rbx+7]
0x18001740c  lea     r9, [rbp+57h+var_C0]
0x180017410  lea     rdx, [rbp+57h+var_50]
0x180017414  call    ?RetrieveByte@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAE@Z; EnrollmentManager::RetrieveByte(TABLEID,_GUID,ushort,uchar *)
0x180017419  mov     edi, eax
0x18001741b  test    eax, eax
0x18001741d  js      loc_1800176E9
0x180017423  cmp     [rbp+57h+var_C0], 1
0x180017427  jnz     loc_18001767E
0x18001742d  lea     rax, [rbp+57h+var_D0]
0x180017431  mov     [rsp+120h+lpFileName], rax
0x180017436  lea     rax, [rbp+57h+var_D0]
0x18001743a  mov     [rsp+120h+var_D8], rax
0x18001743f  xor     eax, eax
0x180017441  mov     [rbp+57h+var_D0], ax
0x180017445  movdqa  [rbp+57h+var_50], xmm6
0x18001744a  lea     r8d, [rbx+5]
0x18001744e  lea     r9, [rsp+120h+pv]
0x180017453  lea     rdx, [rbp+57h+var_50]
0x180017457  lea     ecx, [rbx+1]
0x18001745a  call    ?RetrieveBSTR@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAPEAG@Z; EnrollmentManager::RetrieveBSTR(TABLEID,_GUID,ushort,ushort * *)
0x18001745f  mov     edi, eax
0x180017461  test    eax, eax
0x180017463  js      loc_1800176CC
0x180017469  mov     rbx, [rsp+120h+pv]
0x18001746e  mov     rcx, rbx; pwszUrl
0x180017471  call    ?RemoteUrl@@YAHPEBG@Z; RemoteUrl(ushort const *)
0x180017476  test    eax, eax
0x180017478  jz      loc_180017637
0x18001747e  mov     [rbp+57h+var_90], 0
0x180017486  lea     rax, [rbp+57h+var_A8]
0x18001748a  mov     [rbp+57h+var_B8], rax
0x18001748e  lea     rax, [rbp+57h+var_A8]
0x180017492  mov     [rbp+57h+var_B0], rax
0x180017496  xor     eax, eax
0x180017498  mov     [rbp+57h+var_A8], ax
0x18001749c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800174a3  movdqu  [rbp+57h+var_50], xmm0
0x1800174a8  mov     dword ptr [rsp+120h+pv], eax
0x1800174ac  lea     rdx, [rsp+120h+pv]; enum EnterpriseFileType *
0x1800174b1  mov     rcx, rbx; unsigned __int16 *
0x1800174b4  call    ?DetermineInstallFileType@@YAJPEBGPEAW4EnterpriseFileType@@@Z; DetermineInstallFileType(ushort const *,EnterpriseFileType *)
0x1800174b9  mov     edi, eax
0x1800174bb  test    eax, eax
0x1800174bd  js      loc_180017695
0x1800174c3  movdqa  xmmword ptr [rbp+57h+rclsid.Data1], xmm6
0x1800174c8  mov     r8d, dword ptr [rsp+120h+pv]
0x1800174cd  lea     rdx, [rsp+120h+lpFileName]
0x1800174d2  lea     rcx, [rbp+57h+rclsid]; rclsid
0x1800174d6  call    ?GenerateDestinationFileName@@YAJU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4EnterpriseFileType@@@Z; GenerateDestinationFileName(_GUID,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,EnterpriseFileType)
0x1800174db  mov     edi, eax
0x1800174dd  test    eax, eax
0x1800174df  js      loc_180017695
0x1800174e5  mov     rcx, [rsp+120h+lpFileName]; lpFileName
0x1800174ea  call    ?DeleteLocalFile@@YAJPEBG@Z; DeleteLocalFile(ushort const *)
0x1800174ef  movdqa  xmmword ptr [rbp+57h+rclsid.Data1], xmm6
0x1800174f4  mov     r8d, 3
0x1800174fa  lea     r9, [rbp+57h+var_50]
0x1800174fe  lea     rdx, [rbp+57h+rclsid]
0x180017502  lea     ecx, [r8-2]
0x180017506  call    ?RetrieveGUID@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAU3@@Z; EnrollmentManager::RetrieveGUID(TABLEID,_GUID,ushort,_GUID *)
0x18001750b  mov     edi, eax
0x18001750d  test    eax, eax
0x18001750f  js      loc_180017695
0x180017515  movdqa  xmmword ptr [rbp+57h+rclsid.Data1], xmm6
0x18001751a  mov     [rsp+120h+pv], 0
0x180017523  lea     rcx, [rsp+120h+pv]
0x180017528  call    ??$replace@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>(tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0> &)
0x18001752d  mov     rdx, rax; lplpsz
0x180017530  lea     rcx, [rbp+57h+rclsid]; rclsid
0x180017534  call    cs:__imp_StringFromCLSID
0x18001753a  mov     edi, eax
0x18001753c  test    eax, eax
0x18001753e  js      short loc_180017558
0x180017540  mov     rdx, [rsp+120h+pv]
0x180017545  lea     rcx, [rbp+57h+var_B8]
0x180017549  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18001754e  test    al, al
0x180017550  mov     eax, 8007000Eh
0x180017555  cmovz   edi, eax
0x180017558  mov     rcx, [rsp+120h+pv]; pv
0x18001755d  test    rcx, rcx
0x180017560  jz      short loc_180017568
0x180017562  call    cs:__imp_CoTaskMemFree
0x180017568  test    edi, edi
0x18001756a  js      loc_180017695
0x180017570  mov     rax, [rbp+57h+var_B8]
0x180017574  movaps  xmm0, [rbp+57h+var_50]
0x180017578  movdqa  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x18001757d  lea     rcx, [rbp+57h+var_90]
0x180017581  mov     [rsp+120h+var_F8], rcx; struct HBTSREQUEST__ **
0x180017586  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x18001758b  mov     r9, [rsp+120h+lpFileName]; unsigned __int16 *
0x180017590  mov     r8, rbx; unsigned __int16 *
0x180017593  lea     rdx, [rbp+57h+rclsid]; struct _GUID
0x180017597  mov     rcx, r14; this
0x18001759a  call    ?DownloadXap@EnterpriseWorkerThread@@AEAAJU_GUID@@PEBG11PEAPEAUHBTSREQUEST__@@@Z; EnterpriseWorkerThread::DownloadXap(_GUID,ushort const *,ushort const *,ushort const *,HBTSREQUEST__ * *)
0x18001759f  movdqa  xmmword ptr [rbp+57h+rclsid.Data1], xmm6
0x1800175a4  lea     rdx, [rbp+57h+rclsid]
0x1800175a8  test    eax, eax
0x1800175aa  jns     short loc_1800175DC
0x1800175ac  mov     byte ptr [rsp+120h+var_F8], 64h ; 'd'
0x1800175b1  lea     rcx, aUnableToInitia; "Unable to initiate download"
0x1800175b8  mov     [rsp+120h+var_100], rcx
0x1800175bd  mov     r9d, eax
0x1800175c0  mov     r8d, 7
0x1800175c6  mov     rcx, r14
0x1800175c9  call    ?UpdateXAPRequestStatus@EnterpriseWorkerThread@@AEAAJU_GUID@@W4_ENTERPRISE_APP_INSTALL_STATE@@JPEBGE@Z; EnterpriseWorkerThread::UpdateXAPRequestStatus(_GUID,_ENTERPRISE_APP_INSTALL_STATE,long,ushort const *,uchar)
0x1800175ce  mov     edi, eax
0x1800175d0  test    eax, eax
0x1800175d2  js      loc_180017695
0x1800175d8  xor     edi, edi
0x1800175da  jmp     short loc_180017620
0x1800175dc  mov     r8, [rsp+120h+lpFileName]
0x1800175e1  call    ?UpdateLocalUriField@EnterpriseWorkerThread@@AEAAJU_GUID@@PEBGW4_ENTERPRISE_APP_INSTALL_STATE@@E@Z; EnterpriseWorkerThread::UpdateLocalUriField(_GUID,ushort const *,_ENTERPRISE_APP_INSTALL_STATE,uchar)
0x1800175e6  mov     edi, eax
0x1800175e8  test    eax, eax
0x1800175ea  js      loc_180017695
0x1800175f0  mov     rax, [rbp+57h+var_90]
0x1800175f4  test    rax, rax
0x1800175f7  jz      short loc_180017620
0x1800175f9  movdqu  xmmword ptr [rbp+57h+rclsid.Data1], xmm6
0x1800175fe  mov     [rbp+57h+var_60], rax
0x180017602  lea     rcx, [r14+88h]
0x180017609  lea     r8, [rbp+57h+rclsid]
0x18001760d  lea     rdx, [rbp+57h+var_88]
0x180017611  call    ??$insert@U?$pair@U_GUID@@PEAUHBTSREQUEST__@@@utl@@$0A@@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@PEAUHBTSREQUEST__@@@utl@@U?$memory_compare_less@U_GUID@@@@V?$allocator@U?$pair@$$CBU_GUID@@PEAUHBTSREQUEST__@@@utl@@@3@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBU_GUID@@PEAUHBTSREQUEST__@@@utl@@@utl@@_N@1@$$QEAU?$pair@U_GUID@@PEAUHBTSREQUEST__@@@1@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,HBTSREQUEST__ *>,memory_compare_less<_GUID>,utl::allocator<utl::pair<_GUID const,HBTSREQUEST__ *>>,0>::insert<utl::pair<_GUID,HBTSREQUEST__ *>,0>(utl::pair<_GUID,HBTSREQUEST__ *> &&)
0x180017616  cmp     qword ptr [rax], 0
0x18001761a  jz      loc_1800176C5
0x180017620  lea     rax, [rbp+57h+var_A8]
0x180017624  mov     rcx, [rbp+57h+var_B8]; void *
0x180017628  cmp     rcx, rax
0x18001762b  jz      short loc_180017668
0x18001762d  mov     rdx, r13; struct std::nothrow_t *
0x180017630  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017635  jmp     short loc_180017668
0x180017637  movdqa  xmmword ptr [rbp+57h+rclsid.Data1], xmm6
0x18001763c  mov     byte ptr [rsp+120h+var_F8], 32h ; '2'
0x180017641  lea     rax, aDownloaded; "Downloaded!"
0x180017648  mov     [rsp+120h+var_100], rax
0x18001764d  mov     r9d, edi
0x180017650  mov     r8d, 3
0x180017656  lea     rdx, [rbp+57h+rclsid]
0x18001765a  mov     rcx, r14
0x18001765d  call    ?UpdateXAPRequestStatus@EnterpriseWorkerThread@@AEAAJU_GUID@@W4_ENTERPRISE_APP_INSTALL_STATE@@JPEBGE@Z; EnterpriseWorkerThread::UpdateXAPRequestStatus(_GUID,_ENTERPRISE_APP_INSTALL_STATE,long,ushort const *,uchar)
0x180017662  mov     edi, eax
0x180017664  test    eax, eax
0x180017666  js      short loc_1800176AA
0x180017668  lea     rax, [rbp+57h+var_D0]
0x18001766c  mov     rcx, [rsp+120h+lpFileName]; void *
0x180017671  cmp     rcx, rax
0x180017674  jz      short loc_18001767E
0x180017676  mov     rdx, r13; struct std::nothrow_t *
0x180017679  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001767e  mov     rcx, rbx; bstrString
0x180017681  call    cs:__imp_SysFreeString
0x180017687  inc     esi
0x180017689  cmp     esi, dword ptr [rsp+120h+var_E8]
0x18001768d  jb      loc_1800173EF
0x180017693  jmp     short loc_1800176F1
0x180017695  lea     rax, [rbp+57h+var_A8]
0x180017699  mov     rcx, [rbp+57h+var_B8]; void *
0x18001769d  cmp     rcx, rax
0x1800176a0  jz      short loc_1800176AA
0x1800176a2  mov     rdx, r13; struct std::nothrow_t *
0x1800176a5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800176aa  lea     rax, [rbp+57h+var_D0]
0x1800176ae  mov     rcx, [rsp+120h+lpFileName]; void *
0x1800176b3  cmp     rcx, rax
0x1800176b6  jz      short loc_1800176C0
0x1800176b8  mov     rdx, r13; struct std::nothrow_t *
0x1800176bb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800176c0  mov     rcx, rbx
0x1800176c3  jmp     short loc_1800176EB
0x1800176c5  mov     edi, 8007000Eh
0x1800176ca  jmp     short loc_180017695
0x1800176cc  lea     rax, [rbp+57h+var_D0]
0x1800176d0  mov     rcx, [rsp+120h+lpFileName]; void *
0x1800176d5  cmp     rcx, rax
0x1800176d8  jz      short loc_1800176E2
0x1800176da  mov     rdx, r13; struct std::nothrow_t *
0x1800176dd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800176e2  mov     rcx, [rsp+120h+pv]
0x1800176e7  jmp     short loc_1800176EB
0x1800176e9  xor     ecx, ecx; bstrString
0x1800176eb  call    cs:__imp_SysFreeString
0x1800176f1  lea     rcx, [r14+58h]; lpCriticalSection
0x1800176f5  call    cs:__imp_LeaveCriticalSection
0x1800176fb  mov     rcx, [rbp+57h+var_98]
0x1800176ff  test    rcx, rcx
0x180017702  jz      short loc_18001770A
0x180017704  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001770a  mov     eax, edi
0x18001770c  mov     rcx, [rbp+57h+var_40]
0x180017710  xor     rcx, rsp; StackCookie
0x180017713  call    __security_check_cookie
0x180017718  lea     r11, [rsp+120h+var_20]
0x180017720  mov     rbx, [r11+38h]
0x180017724  mov     rsi, [r11+40h]
0x180017728  movaps  xmm6, xmmword ptr [r11-10h]
0x18001772d  mov     rsp, r11
0x180017730  pop     r14
0x180017732  pop     r13
0x180017734  pop     r12
0x180017736  pop     rdi
0x180017737  pop     rbp
0x180017738  retn
```
