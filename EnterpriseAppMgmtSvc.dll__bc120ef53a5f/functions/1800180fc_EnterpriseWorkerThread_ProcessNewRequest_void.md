# EnterpriseWorkerThread::ProcessNewRequest(void)

- ea: `0x1800180fc`
- end: `0x1800184f8`
- name: `?ProcessNewRequest@EnterpriseWorkerThread@@AEAAJXZ`
- size: `1020`
- prototype: `__int64 __fastcall(EnterpriseWorkerThread *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800175bc`

## callees

- `0x180002544`
- `0x180013794`
- `0x1800137c8`
- `0x1800148e8`
- `0x18001596c`
- `0x1800180fc`
- `0x1800192ac`
- `0x180019384`
- `0x18001a07c`
- `0x18001b63c`
- `0x18001c550`
- `0x18001c5fc`
- `0x18001c818`
- `0x180029e60`
- `0x180029ed0`
- `0x180029f90`
- `0x18002a2e0`
- `0x18006c910`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800184bc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800184bc`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800182ce`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800182ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018302`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018302`
- `OLEAUT32!__imp_SysFreeString` at `0x180018427`
- `OLEAUT32!__imp_SysFreeString` at `0x180018497`
- `OLEAUT32!__imp_SysFreeString` at `0x180018427`
- `OLEAUT32!__imp_SysFreeString` at `0x180018497`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800184a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800184a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001814a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001814a`

## pseudocode

```c
__int64 __fastcall EnterpriseWorkerThread::ProcessNewRequest(EnterpriseWorkerThread *this)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  HRESULT updated; // edi
  unsigned int v5; // esi
  IID v6; // xmm6
  unsigned __int16 *v7; // rbx
  LPOLESTR *v8; // rax
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
  v2 = tlx::replace<_GUID,&void tlx::_delete_array<_GUID>(_GUID *)>(&v21);
  updated = EnrollmentManager::EnumeratePrimaryKeys(v3, v2, &v14);
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
      updated = EnrollmentManager::RetrieveGUID(1, &rclsid, 3, &v26);
      if ( updated < 0 )
        goto LABEL_29;
      rclsid = v6;
      pv = 0;
      v8 = (LPOLESTR *)tlx::replace<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>(&pv);
      updated = StringFromCLSID(&rclsid, v8);
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
                             (char *)this + 136,
                             v23,
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
0x1800180fc  mov     rax, rsp
0x1800180ff  mov     [rax+10h], rbx
0x180018103  mov     [rax+18h], rsi
0x180018107  push    rbp
0x180018108  push    rdi
0x180018109  push    r12
0x18001810b  push    r13
0x18001810d  push    r14
0x18001810f  lea     rbp, [rax-5Fh]
0x180018113  sub     rsp, 100h
0x18001811a  movaps  xmmword ptr [rax-38h], xmm6
0x18001811e  mov     rax, cs:__security_cookie
0x180018125  xor     rax, rsp
0x180018128  mov     [rbp+57h+var_40], rax
0x18001812c  mov     r14, rcx
0x18001812f  mov     [rbp+57h+var_98], 0
0x180018137  mov     dword ptr [rsp+120h+var_E8], 0
0x18001813f  mov     [rbp+57h+var_C0], 1
0x180018146  add     rcx, 58h ; 'X'; lpCriticalSection
0x18001814a  call    cs:__imp_EnterCriticalSection
0x180018151  nop     dword ptr [rax+rax+00h]
0x180018156  lea     rcx, [rbp+57h+var_98]
0x18001815a  call    ??$replace@U_GUID@@$1??$_delete_array@U_GUID@@@tlx@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_GUID@@AEAV?$auto_array_ptr@U_GUID@@$1??$_delete_array@U_GUID@@@tlx@@YAXPEAU1@@Z@0@@Z; tlx::replace<_GUID,&tlx::_delete_array<_GUID>(_GUID *)>(tlx::auto_array_ptr<_GUID,&tlx::_delete_array<_GUID>(_GUID *)> &)
0x18001815f  mov     rdx, rax
0x180018162  lea     r8, [rsp+120h+var_E8]
0x180018167  call    ?EnumeratePrimaryKeys@EnrollmentManager@@SAJW4TABLEID@@PEAPEAU_GUID@@AEAK@Z; EnrollmentManager::EnumeratePrimaryKeys(TABLEID,_GUID * *,ulong &)
0x18001816c  mov     edi, eax
0x18001816e  test    eax, eax
0x180018170  js      loc_1800184A3
0x180018176  xor     esi, esi
0x180018178  cmp     dword ptr [rsp+120h+var_E8], esi
0x18001817c  jbe     loc_1800184A3
0x180018182  lea     r13, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180018189  mov     ecx, esi
0x18001818b  add     rcx, rcx
0x18001818e  mov     rax, [rbp+57h+var_98]
0x180018192  movups  xmm6, xmmword ptr [rax+rcx*8]
0x180018196  xor     ebx, ebx
0x180018198  mov     [rsp+120h+pv], rbx
0x18001819d  movdqu  [rbp+57h+var_50], xmm6
0x1800181a2  lea     r8d, [rbx+7]
0x1800181a6  lea     r9, [rbp+57h+var_C0]
0x1800181aa  lea     rdx, [rbp+57h+var_50]
0x1800181ae  call    ?RetrieveByte@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAE@Z; EnrollmentManager::RetrieveByte(TABLEID,_GUID,ushort,uchar *)
0x1800181b3  mov     edi, eax
0x1800181b5  test    eax, eax
0x1800181b7  js      loc_180018495
0x1800181bd  cmp     [rbp+57h+var_C0], 1
0x1800181c1  jnz     loc_180018424
0x1800181c7  lea     rax, [rbp+57h+var_D0]
0x1800181cb  mov     [rsp+120h+lpFileName], rax
0x1800181d0  lea     rax, [rbp+57h+var_D0]
0x1800181d4  mov     [rsp+120h+var_D8], rax
0x1800181d9  xor     eax, eax
0x1800181db  mov     [rbp+57h+var_D0], ax
0x1800181df  movdqa  [rbp+57h+var_50], xmm6
0x1800181e4  lea     r8d, [rbx+5]
0x1800181e8  lea     r9, [rsp+120h+pv]
0x1800181ed  lea     rdx, [rbp+57h+var_50]
0x1800181f1  lea     ecx, [rbx+1]
0x1800181f4  call    ?RetrieveBSTR@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAPEAG@Z; EnrollmentManager::RetrieveBSTR(TABLEID,_GUID,ushort,ushort * *)
0x1800181f9  mov     edi, eax
0x1800181fb  test    eax, eax
0x1800181fd  js      loc_180018478
0x180018203  mov     rbx, [rsp+120h+pv]
0x180018208  mov     rcx, rbx; pwszUrl
0x18001820b  call    ?RemoteUrl@@YAHPEBG@Z; RemoteUrl(ushort const *)
0x180018210  test    eax, eax
0x180018212  jz      loc_1800183DD
0x180018218  mov     [rbp+57h+var_90], 0
0x180018220  lea     rax, [rbp+57h+var_A8]
0x180018224  mov     [rbp+57h+var_B8], rax
0x180018228  lea     rax, [rbp+57h+var_A8]
0x18001822c  mov     [rbp+57h+var_B0], rax
0x180018230  xor     eax, eax
0x180018232  mov     [rbp+57h+var_A8], ax
0x180018236  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001823d  movdqu  [rbp+57h+var_50], xmm0
0x180018242  mov     dword ptr [rsp+120h+pv], eax
0x180018246  lea     rdx, [rsp+120h+pv]; enum EnterpriseFileType *
0x18001824b  mov     rcx, rbx; unsigned __int16 *
0x18001824e  call    ?DetermineInstallFileType@@YAJPEBGPEAW4EnterpriseFileType@@@Z; DetermineInstallFileType(ushort const *,EnterpriseFileType *)
0x180018253  mov     edi, eax
0x180018255  test    eax, eax
0x180018257  js      loc_180018441
0x18001825d  movdqa  xmmword ptr [rbp+57h+rclsid.Data1], xmm6
0x180018262  mov     r8d, dword ptr [rsp+120h+pv]
0x180018267  lea     rdx, [rsp+120h+lpFileName]
0x18001826c  lea     rcx, [rbp+57h+rclsid]; rclsid
0x180018270  call    ?GenerateDestinationFileName@@YAJU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4EnterpriseFileType@@@Z; GenerateDestinationFileName(_GUID,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,EnterpriseFileType)
0x180018275  mov     edi, eax
0x180018277  test    eax, eax
0x180018279  js      loc_180018441
0x18001827f  mov     rcx, [rsp+120h+lpFileName]; lpFileName
0x180018284  call    ?DeleteLocalFile@@YAJPEBG@Z; DeleteLocalFile(ushort const *)
0x180018289  movdqa  xmmword ptr [rbp+57h+rclsid.Data1], xmm6
0x18001828e  mov     r8d, 3
0x180018294  lea     r9, [rbp+57h+var_50]
0x180018298  lea     rdx, [rbp+57h+rclsid]
0x18001829c  lea     ecx, [r8-2]
0x1800182a0  call    ?RetrieveGUID@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAU3@@Z; EnrollmentManager::RetrieveGUID(TABLEID,_GUID,ushort,_GUID *)
0x1800182a5  mov     edi, eax
0x1800182a7  test    eax, eax
0x1800182a9  js      loc_180018441
0x1800182af  movdqa  xmmword ptr [rbp+57h+rclsid.Data1], xmm6
0x1800182b4  mov     [rsp+120h+pv], 0
0x1800182bd  lea     rcx, [rsp+120h+pv]
0x1800182c2  call    ??$replace@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>(tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0> &)
0x1800182c7  mov     rdx, rax; lplpsz
0x1800182ca  lea     rcx, [rbp+57h+rclsid]; rclsid
0x1800182ce  call    cs:__imp_StringFromCLSID
0x1800182d5  nop     dword ptr [rax+rax+00h]
0x1800182da  mov     edi, eax
0x1800182dc  test    eax, eax
0x1800182de  js      short loc_1800182F8
0x1800182e0  mov     rdx, [rsp+120h+pv]
0x1800182e5  lea     rcx, [rbp+57h+var_B8]
0x1800182e9  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800182ee  test    al, al
0x1800182f0  mov     eax, 8007000Eh
0x1800182f5  cmovz   edi, eax
0x1800182f8  mov     rcx, [rsp+120h+pv]; pv
0x1800182fd  test    rcx, rcx
0x180018300  jz      short loc_18001830E
0x180018302  call    cs:__imp_CoTaskMemFree
0x180018309  nop     dword ptr [rax+rax+00h]
0x18001830e  test    edi, edi
0x180018310  js      loc_180018441
0x180018316  mov     rax, [rbp+57h+var_B8]
0x18001831a  movaps  xmm0, [rbp+57h+var_50]
0x18001831e  movdqa  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x180018323  lea     rcx, [rbp+57h+var_90]
0x180018327  mov     [rsp+120h+var_F8], rcx; struct HBTSREQUEST__ **
0x18001832c  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x180018331  mov     r9, [rsp+120h+lpFileName]; unsigned __int16 *
0x180018336  mov     r8, rbx; unsigned __int16 *
0x180018339  lea     rdx, [rbp+57h+rclsid]; struct _GUID
0x18001833d  mov     rcx, r14; this
0x180018340  call    ?DownloadXap@EnterpriseWorkerThread@@AEAAJU_GUID@@PEBG11PEAPEAUHBTSREQUEST__@@@Z; EnterpriseWorkerThread::DownloadXap(_GUID,ushort const *,ushort const *,ushort const *,HBTSREQUEST__ * *)
0x180018345  movdqa  xmmword ptr [rbp+57h+rclsid.Data1], xmm6
0x18001834a  lea     rdx, [rbp+57h+rclsid]
0x18001834e  test    eax, eax
0x180018350  jns     short loc_180018382
0x180018352  mov     byte ptr [rsp+120h+var_F8], 64h ; 'd'
0x180018357  lea     rcx, aUnableToInitia; "Unable to initiate download"
0x18001835e  mov     [rsp+120h+var_100], rcx
0x180018363  mov     r9d, eax
0x180018366  mov     r8d, 7
0x18001836c  mov     rcx, r14
0x18001836f  call    ?UpdateXAPRequestStatus@EnterpriseWorkerThread@@AEAAJU_GUID@@W4_ENTERPRISE_APP_INSTALL_STATE@@JPEBGE@Z; EnterpriseWorkerThread::UpdateXAPRequestStatus(_GUID,_ENTERPRISE_APP_INSTALL_STATE,long,ushort const *,uchar)
0x180018374  mov     edi, eax
0x180018376  test    eax, eax
0x180018378  js      loc_180018441
0x18001837e  xor     edi, edi
0x180018380  jmp     short loc_1800183C6
0x180018382  mov     r8, [rsp+120h+lpFileName]
0x180018387  call    ?UpdateLocalUriField@EnterpriseWorkerThread@@AEAAJU_GUID@@PEBGW4_ENTERPRISE_APP_INSTALL_STATE@@E@Z; EnterpriseWorkerThread::UpdateLocalUriField(_GUID,ushort const *,_ENTERPRISE_APP_INSTALL_STATE,uchar)
0x18001838c  mov     edi, eax
0x18001838e  test    eax, eax
0x180018390  js      loc_180018441
0x180018396  mov     rax, [rbp+57h+var_90]
0x18001839a  test    rax, rax
0x18001839d  jz      short loc_1800183C6
0x18001839f  movdqu  xmmword ptr [rbp+57h+rclsid.Data1], xmm6
0x1800183a4  mov     [rbp+57h+var_60], rax
0x1800183a8  lea     rcx, [r14+88h]
0x1800183af  lea     r8, [rbp+57h+rclsid]
0x1800183b3  lea     rdx, [rbp+57h+var_88]
0x1800183b7  call    ??$insert@U?$pair@U_GUID@@PEAUHBTSREQUEST__@@@utl@@$0A@@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@PEAUHBTSREQUEST__@@@utl@@U?$memory_compare_less@U_GUID@@@@V?$allocator@U?$pair@$$CBU_GUID@@PEAUHBTSREQUEST__@@@utl@@@3@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBU_GUID@@PEAUHBTSREQUEST__@@@utl@@@utl@@_N@1@$$QEAU?$pair@U_GUID@@PEAUHBTSREQUEST__@@@1@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,HBTSREQUEST__ *>,memory_compare_less<_GUID>,utl::allocator<utl::pair<_GUID const,HBTSREQUEST__ *>>,0>::insert<utl::pair<_GUID,HBTSREQUEST__ *>,0>(utl::pair<_GUID,HBTSREQUEST__ *> &&)
0x1800183bc  cmp     qword ptr [rax], 0
0x1800183c0  jz      loc_180018471
0x1800183c6  lea     rax, [rbp+57h+var_A8]
0x1800183ca  mov     rcx, [rbp+57h+var_B8]; void *
0x1800183ce  cmp     rcx, rax
0x1800183d1  jz      short loc_18001840E
0x1800183d3  mov     rdx, r13; struct std::nothrow_t *
0x1800183d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800183db  jmp     short loc_18001840E
0x1800183dd  movdqa  xmmword ptr [rbp+57h+rclsid.Data1], xmm6
0x1800183e2  mov     byte ptr [rsp+120h+var_F8], 32h ; '2'
0x1800183e7  lea     rax, aDownloaded; "Downloaded!"
0x1800183ee  mov     [rsp+120h+var_100], rax
0x1800183f3  mov     r9d, edi
0x1800183f6  mov     r8d, 3
0x1800183fc  lea     rdx, [rbp+57h+rclsid]
0x180018400  mov     rcx, r14
0x180018403  call    ?UpdateXAPRequestStatus@EnterpriseWorkerThread@@AEAAJU_GUID@@W4_ENTERPRISE_APP_INSTALL_STATE@@JPEBGE@Z; EnterpriseWorkerThread::UpdateXAPRequestStatus(_GUID,_ENTERPRISE_APP_INSTALL_STATE,long,ushort const *,uchar)
0x180018408  mov     edi, eax
0x18001840a  test    eax, eax
0x18001840c  js      short loc_180018456
0x18001840e  lea     rax, [rbp+57h+var_D0]
0x180018412  mov     rcx, [rsp+120h+lpFileName]; void *
0x180018417  cmp     rcx, rax
0x18001841a  jz      short loc_180018424
0x18001841c  mov     rdx, r13; struct std::nothrow_t *
0x18001841f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180018424  mov     rcx, rbx; bstrString
0x180018427  call    cs:__imp_SysFreeString
0x18001842e  nop     dword ptr [rax+rax+00h]
0x180018433  inc     esi
0x180018435  cmp     esi, dword ptr [rsp+120h+var_E8]
0x180018439  jb      loc_180018189
0x18001843f  jmp     short loc_1800184A3
0x180018441  lea     rax, [rbp+57h+var_A8]
0x180018445  mov     rcx, [rbp+57h+var_B8]; void *
0x180018449  cmp     rcx, rax
0x18001844c  jz      short loc_180018456
0x18001844e  mov     rdx, r13; struct std::nothrow_t *
0x180018451  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180018456  lea     rax, [rbp+57h+var_D0]
0x18001845a  mov     rcx, [rsp+120h+lpFileName]; void *
0x18001845f  cmp     rcx, rax
0x180018462  jz      short loc_18001846C
0x180018464  mov     rdx, r13; struct std::nothrow_t *
0x180018467  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001846c  mov     rcx, rbx
0x18001846f  jmp     short loc_180018497
0x180018471  mov     edi, 8007000Eh
0x180018476  jmp     short loc_180018441
0x180018478  lea     rax, [rbp+57h+var_D0]
0x18001847c  mov     rcx, [rsp+120h+lpFileName]; void *
0x180018481  cmp     rcx, rax
0x180018484  jz      short loc_18001848E
0x180018486  mov     rdx, r13; struct std::nothrow_t *
0x180018489  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001848e  mov     rcx, [rsp+120h+pv]
0x180018493  jmp     short loc_180018497
0x180018495  xor     ecx, ecx; bstrString
0x180018497  call    cs:__imp_SysFreeString
0x18001849e  nop     dword ptr [rax+rax+00h]
0x1800184a3  lea     rcx, [r14+58h]; lpCriticalSection
0x1800184a7  call    cs:__imp_LeaveCriticalSection
0x1800184ae  nop     dword ptr [rax+rax+00h]
0x1800184b3  mov     rcx, [rbp+57h+var_98]
0x1800184b7  test    rcx, rcx
0x1800184ba  jz      short loc_1800184C8
0x1800184bc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800184c3  nop     dword ptr [rax+rax+00h]
0x1800184c8  mov     eax, edi
0x1800184ca  mov     rcx, [rbp+57h+var_40]
0x1800184ce  xor     rcx, rsp; StackCookie
0x1800184d1  call    __security_check_cookie
0x1800184d6  lea     r11, [rsp+120h+var_20]
0x1800184de  mov     rbx, [r11+38h]
0x1800184e2  mov     rsi, [r11+40h]
0x1800184e6  movaps  xmm6, xmmword ptr [r11-10h]
0x1800184eb  mov     rsp, r11
0x1800184ee  pop     r14
0x1800184f0  pop     r13
0x1800184f2  pop     r12
0x1800184f4  pop     rdi
0x1800184f5  pop     rbp
0x1800184f6  retn
```
