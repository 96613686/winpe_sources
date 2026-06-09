# HnsWfpDriverHelper::StopProxyTrafficLocked(_GUID)

- ea: `0x1800856bc`
- end: `0x180085b70`
- name: `?StopProxyTrafficLocked@HnsWfpDriverHelper@@AEAAJU_GUID@@@Z`
- size: `1204`
- prototype: `__int64 __fastcall(HnsWfpDriverHelper *__hidden this, struct _GUID *Buf1)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1801f8d04`

## callees

- `0x18005f0c0`
- `0x18005f560`
- `0x18005ffa0`
- `0x18006c530`
- `0x1800759d8`
- `0x180075aac`
- `0x180076f1c`
- `0x18007de54`
- `0x18007f21c`
- `0x180085608`
- `0x1800856bc`
- `0x180085ba0`

## import_xrefs

- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x1800857ba`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x1800857ba`
- `fwpuclnt!FwpmTransactionBegin0` at `0x180085791`
- `fwpuclnt!FwpmTransactionBegin0` at `0x180085791`
- `fwpuclnt!FwpmTransactionCommit0` at `0x1800858ac`
- `fwpuclnt!FwpmTransactionCommit0` at `0x1800858ac`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18008583d`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18008583d`
- `fwpuclnt!FwpmTransactionAbort0` at `0x1800858cd`
- `fwpuclnt!FwpmTransactionAbort0` at `0x1800858cd`

## string_xrefs

- `0x1800858b8`: `FwpmTransactionCommit failed with %d\n`
- `0x180085773`: `Policy already removed.\n`
- `0x180085912`: `Policy already removed.\n`
- `0x180085820`: `FwpmFilterDeleteByKey failed with %d\n`
- `0x1800857c9`: `FwpmFilterDeleteByKey failed due to Filter not found. Ignoring error.\n`
- `0x1800858a3`: `FwpmProviderContextDeleteByKey failed with %d\n`
- `0x18008584c`: `FwpmProviderContextDeleteByKey failed due to provider context not found. Ignoring error.\n`
- `0x1800859c3`: `RemovePolicyFilters Policy: %ws Filter: %ws\n`
- `0x180085a8a`: `RemovePolicyProviderContexts Policy: %ws Provider Context: %ws\n`
- `0x180085964`: `Policy %ws already removed.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HnsWfpDriverHelper::StopProxyTrafficLocked(HnsWfpDriverHelper *this, struct _GUID *Buf1)
{
  __int64 *v5; // rdi
  __int64 *v6; // rbx
  DWORD v7; // esi
  HANDLE *v8; // rcx
  DWORD v9; // eax
  __int64 **v10; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  void *v13; // rcx
  DWORD v14; // eax
  __int64 **v15; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  DWORD v18; // eax
  __int64 **v19; // rdi
  __int64 **v20; // rdi
  _QWORD *v21; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rbx
  _QWORD *v24; // rax
  __int64 *n; // rbx
  __int64 *v26; // rax
  __int64 *v27; // rcx
  void *v28; // rax
  _QWORD *v29; // rax
  _QWORD *v30; // rbx
  _QWORD *v31; // rax
  __int64 *ii; // rbx
  __int64 *v33; // rax
  __int64 *v34; // rcx
  void *v35; // rax
  unsigned __int64 v36; // [rsp+20h] [rbp-49h] BYREF
  _BYTE v37[24]; // [rsp+28h] [rbp-41h] BYREF
  _BYTE v38[32]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v39[32]; // [rsp+60h] [rbp-9h] BYREF

  HNSTraceProvider::TraceEnter("HnsWfpDriverHelper::StopProxyTrafficLocked", 0x39Eu);
  if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
  {
    LogMessage(L"Policy Id was null.\n");
    HNSTraceProvider::TraceSuccess("HnsWfpDriverHelper::StopProxyTrafficLocked", 0x3A5u);
    return 87;
  }
  std::_Tree<std::_Tmap_traits<_GUID,_GUID,HNS::Service::Common::GuidLessThan,std::allocator<std::pair<_GUID const,_GUID>>,1>>::equal_range(
    (char *)this + 32,
    &v37[8],
    Buf1);
  std::_Tree<std::_Tmap_traits<_GUID,_GUID,HNS::Service::Common::GuidLessThan,std::allocator<std::pair<_GUID const,_GUID>>,1>>::equal_range(
    (char *)this + 56,
    &v36,
    Buf1);
  v5 = (__int64 *)v36;
  v6 = *(__int64 **)&v37[8];
  if ( *(_OWORD *)v37 == __PAIR128__(*(unsigned __int64 *)&v37[16], v36) )
  {
    v7 = 0;
    LogMessage(L"Policy already removed.\n");
  }
  else
  {
    v8 = (HANDLE *)*((_QWORD *)this + 15);
    if ( v8 )
    {
      v7 = FwpmTransactionBegin0(*v8, 0);
      if ( v7 )
      {
        LogMessage(L"FwpmTransactionBegin failed with %d\n", v7);
      }
      else
      {
        while ( v6 != *(__int64 **)&v37[16] )
        {
          v9 = FwpmFilterDeleteByKey0(**((HANDLE **)this + 15), (const GUID *)((char *)v6 + 44));
          v7 = v9;
          if ( v9 == -2144206845 )
          {
            LogMessage(L"FwpmFilterDeleteByKey failed due to Filter not found. Ignoring error.\n");
          }
          else if ( v9 )
          {
            LogMessage(L"FwpmFilterDeleteByKey failed with %d\n", v9);
            goto LABEL_38;
          }
          v10 = (__int64 **)v6[2];
          if ( *((_BYTE *)v10 + 25) )
          {
            for ( i = (__int64 *)v6[1]; !*((_BYTE *)i + 25) && v6 == (__int64 *)i[2]; i = (__int64 *)i[1] )
              v6 = i;
            v6 = i;
          }
          else
          {
            v6 = (__int64 *)v6[2];
            for ( j = *v10; !*((_BYTE *)j + 25); j = (__int64 *)*j )
              v6 = j;
          }
        }
        while ( 1 )
        {
          v13 = (void *)**((_QWORD **)this + 15);
          if ( v5 == *(__int64 **)v37 )
            break;
          v14 = FwpmProviderContextDeleteByKey0(v13, (const GUID *)((char *)v5 + 44));
          v7 = v14;
          if ( v14 == -2144206842 )
          {
            LogMessage(L"FwpmProviderContextDeleteByKey failed due to provider context not found. Ignoring error.\n");
          }
          else if ( v14 )
          {
            LogMessage(L"FwpmProviderContextDeleteByKey failed with %d\n", v14);
            goto LABEL_38;
          }
          v15 = (__int64 **)v5[2];
          if ( *((_BYTE *)v15 + 25) )
          {
            for ( k = (__int64 *)v5[1]; !*((_BYTE *)k + 25) && v5 == (__int64 *)k[2]; k = (__int64 *)k[1] )
              v5 = k;
            v5 = k;
          }
          else
          {
            v5 = (__int64 *)v5[2];
            for ( m = *v15; !*((_BYTE *)m + 25); m = (__int64 *)*m )
              v5 = m;
          }
        }
        v7 = FwpmTransactionCommit0(v13);
        if ( !v7 )
        {
          *(struct _GUID *)&v37[8] = *Buf1;
          std::_Tree<std::_Tmap_traits<_GUID,_GUID,HNS::Service::Common::GuidLessThan,std::allocator<std::pair<_GUID const,_GUID>>,1>>::equal_range(
            (char *)this + 32,
            &v36,
            &v37[8]);
          v19 = (__int64 **)v36;
          if ( v36 == *(_QWORD *)v37 )
          {
            LogMessage(L"Policy already removed.\n");
          }
          else
          {
            do
            {
              v22 = (_QWORD *)GuidToString(v38, (char *)v19 + 44, 0);
              v23 = v22;
              if ( v22[3] > 7u )
                v23 = (_QWORD *)*v22;
              v24 = (_QWORD *)GuidToString(v39, &v37[8], 0);
              if ( v24[3] > 7u )
                v24 = (_QWORD *)*v24;
              LogMessage(L"RemovePolicyFilters Policy: %ws Filter: %ws\n", v24, v23);
              std::wstring::~wstring(v39);
              std::wstring::~wstring(v38);
              n = v19[2];
              if ( *((_BYTE *)n + 25) )
              {
                v26 = (__int64 *)v19;
                for ( n = v19[1]; !*((_BYTE *)n + 25) && v26 == (__int64 *)n[2]; n = (__int64 *)n[1] )
                  v26 = n;
              }
              else
              {
                v27 = (__int64 *)*n;
                if ( !*(_BYTE *)(*n + 25) )
                {
                  do
                  {
                    n = v27;
                    v27 = (__int64 *)*v27;
                  }
                  while ( !*((_BYTE *)v27 + 25) );
                }
              }
              v28 = (void *)std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HNSObjectProperty>>>::_Extract(
                              (char *)this + 40,
                              v19);
              operator delete(v28, (const struct std::nothrow_t *)0x40);
              v19 = (__int64 **)n;
            }
            while ( n != *(__int64 **)v37 );
          }
          *(struct _GUID *)&v37[8] = *Buf1;
          std::_Tree<std::_Tmap_traits<_GUID,_GUID,HNS::Service::Common::GuidLessThan,std::allocator<std::pair<_GUID const,_GUID>>,1>>::equal_range(
            (char *)this + 56,
            &v36,
            &v37[8]);
          v20 = (__int64 **)v36;
          if ( v36 == *(_QWORD *)v37 )
          {
            v21 = (_QWORD *)GuidToString(v38, &v37[8], 0);
            if ( v21[3] > 7u )
              v21 = (_QWORD *)*v21;
            LogMessage(L"Policy %ws already removed.\n", v21);
            std::wstring::~wstring(v38);
          }
          else
          {
            do
            {
              v29 = (_QWORD *)GuidToString(v39, (char *)v20 + 44, 0);
              v30 = v29;
              if ( v29[3] > 7u )
                v30 = (_QWORD *)*v29;
              v31 = (_QWORD *)GuidToString(v38, &v37[8], 0);
              if ( v31[3] > 7u )
                v31 = (_QWORD *)*v31;
              LogMessage(L"RemovePolicyProviderContexts Policy: %ws Provider Context: %ws\n", v31, v30);
              std::wstring::~wstring(v38);
              std::wstring::~wstring(v39);
              ii = v20[2];
              if ( *((_BYTE *)ii + 25) )
              {
                v33 = (__int64 *)v20;
                for ( ii = v20[1]; !*((_BYTE *)ii + 25) && v33 == (__int64 *)ii[2]; ii = (__int64 *)ii[1] )
                  v33 = ii;
              }
              else
              {
                v34 = (__int64 *)*ii;
                if ( !*(_BYTE *)(*ii + 25) )
                {
                  do
                  {
                    ii = v34;
                    v34 = (__int64 *)*v34;
                  }
                  while ( !*((_BYTE *)v34 + 25) );
                }
              }
              v35 = (void *)std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HNSObjectProperty>>>::_Extract(
                              (char *)this + 64,
                              v20);
              operator delete(v35, (const struct std::nothrow_t *)0x40);
              v20 = (__int64 **)ii;
            }
            while ( ii != *(__int64 **)v37 );
          }
          goto LABEL_75;
        }
        LogMessage(L"FwpmTransactionCommit failed with %d\n", v7);
      }
LABEL_38:
      v18 = FwpmTransactionAbort0(**((HANDLE **)this + 15));
      if ( v18 )
        LogMessage(L"FwpmTransactionAbort failed with %d\n", v18);
    }
    else
    {
      v7 = 6;
      LogMessage(L"Engine handle is null.\n");
    }
  }
LABEL_75:
  if ( !*((_QWORD *)this + 6) )
    HnsWfpDriverHelper::StopHnsL4WfpProxyDriverLocked(this);
  HNSTraceProvider::TraceSuccess("HnsWfpDriverHelper::StopProxyTrafficLocked", 0x3F0u);
  if ( (int)v7 > 0 )
    return (unsigned __int16)v7 | 0x80070000;
  return v7;
}

```

## disassembly

```asm
0x1800856bc  mov     [rsp-8+arg_10], rbx
0x1800856c1  push    rbp
0x1800856c2  push    rsi
0x1800856c3  push    rdi
0x1800856c4  push    r12
0x1800856c6  push    r13
0x1800856c8  push    r14
0x1800856ca  push    r15
0x1800856cc  lea     rbp, [rsp-27h]
0x1800856d1  sub     rsp, 90h
0x1800856d8  mov     rax, cs:__security_cookie
0x1800856df  xor     rax, rsp
0x1800856e2  mov     [rbp+57h+var_40], rax
0x1800856e6  mov     r15, rdx
0x1800856e9  mov     r14, rcx
0x1800856ec  mov     edx, 39Eh; unsigned int
0x1800856f1  lea     rcx, aHnswfpdriverhe_0; "HnsWfpDriverHelper::StopProxyTrafficLoc"...
0x1800856f8  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1800856fd  mov     r8d, 10h; Size
0x180085703  lea     rdx, GUID_NULL; Buf2
0x18008570a  mov     rcx, r15; Buf1
0x18008570d  call    memcmp_0
0x180085712  test    eax, eax
0x180085714  jnz     short loc_18008573D
0x180085716  lea     rcx, aPolicyIdWasNul; "Policy Id was null.\n"
0x18008571d  call    ?LogMessage@@YAXPEBGZZ; LogMessage(ushort const *,...)
0x180085722  mov     edx, 3A5h; unsigned int
0x180085727  lea     rcx, aHnswfpdriverhe_0; "HnsWfpDriverHelper::StopProxyTrafficLoc"...
0x18008572e  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x180085733  mov     eax, 57h ; 'W'
0x180085738  jmp     loc_180085B49
0x18008573d  mov     r8, r15
0x180085740  lea     rdx, [rbp+57h+var_90]
0x180085744  lea     rcx, [r14+20h]
0x180085748  call    ?equal_range@?$_Tree@V?$_Tmap_traits@U_GUID@@U1@UGuidLessThan@Common@Service@HNS@@V?$allocator@U?$pair@$$CBU_GUID@@U1@@std@@@std@@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@U1@@std@@@std@@@std@@@std@@V12@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,_GUID,HNS::Service::Common::GuidLessThan,std::allocator<std::pair<_GUID const,_GUID>>,1>>::equal_range(_GUID const &)
0x18008574d  mov     r8, r15
0x180085750  lea     rdx, [rbp+57h+var_A0]
0x180085754  lea     rcx, [r14+38h]
0x180085758  call    ?equal_range@?$_Tree@V?$_Tmap_traits@U_GUID@@U1@UGuidLessThan@Common@Service@HNS@@V?$allocator@U?$pair@$$CBU_GUID@@U1@@std@@@std@@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@U1@@std@@@std@@@std@@@std@@V12@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,_GUID,HNS::Service::Common::GuidLessThan,std::allocator<std::pair<_GUID const,_GUID>>,1>>::equal_range(_GUID const &)
0x18008575d  mov     rdi, [rbp+57h+var_A0]
0x180085761  mov     rbx, qword ptr [rbp+57h+var_90]
0x180085765  cmp     rbx, qword ptr [rbp+57h+var_90+8]
0x180085769  jnz     short loc_18008577F
0x18008576b  cmp     rdi, [rbp+57h+var_98]
0x18008576f  jnz     short loc_18008577F
0x180085771  xor     esi, esi
0x180085773  lea     rcx, aPolicyAlreadyR; "Policy already removed.\n"
0x18008577a  jmp     loc_180085B15
0x18008577f  mov     rcx, [r14+78h]
0x180085783  test    rcx, rcx
0x180085786  jz      loc_180085B09
0x18008578c  xor     edx, edx; flags
0x18008578e  mov     rcx, [rcx]; engineHandle
0x180085791  call    cs:__imp_FwpmTransactionBegin0
0x180085797  mov     esi, eax
0x180085799  test    eax, eax
0x18008579b  jz      short loc_1800857A9
0x18008579d  lea     rcx, aFwpmtransactio; "FwpmTransactionBegin failed with %d\n"
0x1800857a4  jmp     loc_1800858BF
0x1800857a9  cmp     rbx, qword ptr [rbp+57h+var_90+8]
0x1800857ad  jz      short loc_18008582C
0x1800857af  lea     rdx, [rbx+2Ch]; key
0x1800857b3  mov     rcx, [r14+78h]
0x1800857b7  mov     rcx, [rcx]; engineHandle
0x1800857ba  call    cs:__imp_FwpmFilterDeleteByKey0
0x1800857c0  mov     esi, eax
0x1800857c2  cmp     eax, 80320003h
0x1800857c7  jnz     short loc_1800857D7
0x1800857c9  lea     rcx, aFwpmfilterdele_0; "FwpmFilterDeleteByKey failed due to Fil"...
0x1800857d0  call    ?LogMessage@@YAXPEBGZZ; LogMessage(ushort const *,...)
0x1800857d5  jmp     short loc_1800857DB
0x1800857d7  test    eax, eax
0x1800857d9  jnz     short loc_180085820
0x1800857db  mov     rcx, [rbx+10h]
0x1800857df  cmp     byte ptr [rcx+19h], 0
0x1800857e3  jz      short loc_180085803
0x1800857e5  mov     rax, [rbx+8]
0x1800857e9  jmp     short loc_1800857F8
0x1800857eb  cmp     rbx, [rax+10h]
0x1800857ef  jnz     short loc_1800857FE
0x1800857f1  mov     rbx, rax
0x1800857f4  mov     rax, [rax+8]
0x1800857f8  cmp     byte ptr [rax+19h], 0
0x1800857fc  jz      short loc_1800857EB
0x1800857fe  mov     rbx, rax
0x180085801  jmp     short loc_1800857A9
0x180085803  mov     rbx, rcx
0x180085806  mov     rcx, [rcx]
0x180085809  cmp     byte ptr [rcx+19h], 0
0x18008580d  jnz     short loc_1800857A9
0x18008580f  mov     rbx, rcx
0x180085812  mov     rax, [rcx]
0x180085815  mov     rcx, rax
0x180085818  cmp     byte ptr [rax+19h], 0
0x18008581c  jz      short loc_18008580F
0x18008581e  jmp     short loc_1800857A9
0x180085820  lea     rcx, aFwpmfilterdele; "FwpmFilterDeleteByKey failed with %d\n"
0x180085827  jmp     loc_1800858BF
0x18008582c  mov     rcx, [r14+78h]
0x180085830  mov     rcx, [rcx]; engineHandle
0x180085833  cmp     rdi, [rbp+57h+var_98]
0x180085837  jz      short loc_1800858AC
0x180085839  lea     rdx, [rdi+2Ch]; key
0x18008583d  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x180085843  mov     esi, eax
0x180085845  cmp     eax, 80320006h
0x18008584a  jnz     short loc_18008585A
0x18008584c  lea     rcx, aFwpmproviderco_1; "FwpmProviderContextDeleteByKey failed d"...
0x180085853  call    ?LogMessage@@YAXPEBGZZ; LogMessage(ushort const *,...)
0x180085858  jmp     short loc_18008585E
0x18008585a  test    eax, eax
0x18008585c  jnz     short loc_1800858A3
0x18008585e  mov     rcx, [rdi+10h]
0x180085862  cmp     byte ptr [rcx+19h], 0
0x180085866  jz      short loc_180085886
0x180085868  mov     rax, [rdi+8]
0x18008586c  jmp     short loc_18008587B
0x18008586e  cmp     rdi, [rax+10h]
0x180085872  jnz     short loc_180085881
0x180085874  mov     rdi, rax
0x180085877  mov     rax, [rax+8]
0x18008587b  cmp     byte ptr [rax+19h], 0
0x18008587f  jz      short loc_18008586E
0x180085881  mov     rdi, rax
0x180085884  jmp     short loc_18008582C
0x180085886  mov     rdi, rcx
0x180085889  mov     rcx, [rcx]
0x18008588c  cmp     byte ptr [rcx+19h], 0
0x180085890  jnz     short loc_18008582C
0x180085892  mov     rdi, rcx
0x180085895  mov     rax, [rcx]
0x180085898  mov     rcx, rax
0x18008589b  cmp     byte ptr [rax+19h], 0
0x18008589f  jz      short loc_180085892
0x1800858a1  jmp     short loc_18008582C
0x1800858a3  lea     rcx, aFwpmproviderco_0; "FwpmProviderContextDeleteByKey failed w"...
0x1800858aa  jmp     short loc_1800858BF
0x1800858ac  call    cs:__imp_FwpmTransactionCommit0
0x1800858b2  mov     esi, eax
0x1800858b4  test    eax, eax
0x1800858b6  jz      short loc_1800858EE
0x1800858b8  lea     rcx, aFwpmtransactio_1; "FwpmTransactionCommit failed with %d\n"
0x1800858bf  mov     edx, esi
0x1800858c1  call    ?LogMessage@@YAXPEBGZZ; LogMessage(ushort const *,...)
0x1800858c6  mov     rcx, [r14+78h]
0x1800858ca  mov     rcx, [rcx]; engineHandle
0x1800858cd  call    cs:__imp_FwpmTransactionAbort0
0x1800858d3  test    eax, eax
0x1800858d5  jz      loc_180085B1A
0x1800858db  mov     edx, eax
0x1800858dd  lea     rcx, aFwpmtransactio_0; "FwpmTransactionAbort failed with %d\n"
0x1800858e4  call    ?LogMessage@@YAXPEBGZZ; LogMessage(ushort const *,...)
0x1800858e9  jmp     loc_180085B1A
0x1800858ee  movaps  xmm0, xmmword ptr [r15]
0x1800858f2  movdqa  [rbp+57h+var_90], xmm0
0x1800858f7  lea     r8, [rbp+57h+var_90]
0x1800858fb  lea     rdx, [rbp+57h+var_A0]
0x1800858ff  lea     rcx, [r14+20h]
0x180085903  call    ?equal_range@?$_Tree@V?$_Tmap_traits@U_GUID@@U1@UGuidLessThan@Common@Service@HNS@@V?$allocator@U?$pair@$$CBU_GUID@@U1@@std@@@std@@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@U1@@std@@@std@@@std@@@std@@V12@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,_GUID,HNS::Service::Common::GuidLessThan,std::allocator<std::pair<_GUID const,_GUID>>,1>>::equal_range(_GUID const &)
0x180085908  mov     rdi, [rbp+57h+var_A0]
0x18008590c  cmp     rdi, [rbp+57h+var_98]
0x180085910  jnz     short loc_180085985
0x180085912  lea     rcx, aPolicyAlreadyR; "Policy already removed.\n"
0x180085919  call    ?LogMessage@@YAXPEBGZZ; LogMessage(ushort const *,...)
0x18008591e  movaps  xmm0, xmmword ptr [r15]
0x180085922  movdqa  [rbp+57h+var_90], xmm0
0x180085927  lea     r8, [rbp+57h+var_90]
0x18008592b  lea     rdx, [rbp+57h+var_A0]
0x18008592f  lea     rcx, [r14+38h]
0x180085933  call    ?equal_range@?$_Tree@V?$_Tmap_traits@U_GUID@@U1@UGuidLessThan@Common@Service@HNS@@V?$allocator@U?$pair@$$CBU_GUID@@U1@@std@@@std@@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@U1@@std@@@std@@@std@@@std@@V12@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,_GUID,HNS::Service::Common::GuidLessThan,std::allocator<std::pair<_GUID const,_GUID>>,1>>::equal_range(_GUID const &)
0x180085938  mov     rdi, [rbp+57h+var_A0]
0x18008593c  cmp     rdi, [rbp+57h+var_98]
0x180085940  jnz     loc_180085A4C
0x180085946  xor     r8d, r8d
0x180085949  lea     rdx, [rbp+57h+var_90]
0x18008594d  lea     rcx, [rbp+57h+var_80]
0x180085951  call    ?GuidToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; GuidToString(_GUID const &,bool)
0x180085956  nop
0x180085957  cmp     qword ptr [rax+18h], 7
0x18008595c  jbe     short loc_180085961
0x18008595e  mov     rax, [rax]
0x180085961  mov     rdx, rax
0x180085964  lea     rcx, aPolicyWsAlread; "Policy %ws already removed.\n"
0x18008596b  call    ?LogMessage@@YAXPEBGZZ; LogMessage(ushort const *,...)
0x180085970  nop
0x180085971  lea     rcx, [rbp+57h+var_80]; void *
0x180085975  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008597a  jmp     loc_180085B1A
0x18008597f  cmp     rdi, [rbp+57h+var_98]
0x180085983  jz      short loc_18008591E
0x180085985  lea     rdx, [rdi+2Ch]
0x180085989  xor     r8d, r8d
0x18008598c  lea     rcx, [rbp+57h+var_80]
0x180085990  call    ?GuidToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; GuidToString(_GUID const &,bool)
0x180085995  mov     rbx, rax
0x180085998  cmp     qword ptr [rax+18h], 7
0x18008599d  jbe     short loc_1800859A2
0x18008599f  mov     rbx, [rax]
0x1800859a2  xor     r8d, r8d
0x1800859a5  lea     rdx, [rbp+57h+var_90]
0x1800859a9  lea     rcx, [rbp+57h+var_60]
0x1800859ad  call    ?GuidToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; GuidToString(_GUID const &,bool)
0x1800859b2  nop
0x1800859b3  cmp     qword ptr [rax+18h], 7
0x1800859b8  jbe     short loc_1800859BD
0x1800859ba  mov     rax, [rax]
0x1800859bd  mov     r8, rbx
0x1800859c0  mov     rdx, rax
0x1800859c3  lea     rcx, aRemovepolicyfi; "RemovePolicyFilters Policy: %ws Filter:"...
0x1800859ca  call    ?LogMessage@@YAXPEBGZZ; LogMessage(ushort const *,...)
0x1800859cf  nop
0x1800859d0  lea     rcx, [rbp+57h+var_60]; void *
0x1800859d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800859d9  nop
0x1800859da  lea     rcx, [rbp+57h+var_80]; void *
0x1800859de  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800859e3  mov     rbx, [rdi+10h]
0x1800859e7  xor     edx, edx
0x1800859e9  cmp     [rbx+19h], dl
0x1800859ec  jz      short loc_180085A0B
0x1800859ee  mov     rax, rdi
0x1800859f1  mov     rbx, [rdi+8]
0x1800859f5  jmp     short loc_180085A04
0x1800859f7  cmp     rax, [rbx+10h]
0x1800859fb  jnz     short loc_180085A21
0x1800859fd  mov     rax, rbx
0x180085a00  mov     rbx, [rbx+8]
0x180085a04  cmp     [rbx+19h], dl
0x180085a07  jz      short loc_1800859F7
0x180085a09  jmp     short loc_180085A21
0x180085a0b  mov     rcx, [rbx]
0x180085a0e  cmp     [rcx+19h], dl
0x180085a11  jnz     short loc_180085A21
0x180085a13  mov     rbx, rcx
0x180085a16  mov     rax, [rcx]
0x180085a19  mov     rcx, rax
0x180085a1c  cmp     [rax+19h], dl
0x180085a1f  jz      short loc_180085A13
0x180085a21  mov     rdx, rdi
0x180085a24  lea     rcx, [r14+28h]
0x180085a28  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHNSObjectProperty@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHNSObjectProperty@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHNSObjectProperty@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HNSObjectProperty>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HNSObjectProperty>>>,std::_Iterator_base0>)
0x180085a2d  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x180085a32  mov     rcx, rax; void *
0x180085a35  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180085a3a  mov     rdi, rbx
0x180085a3d  jmp     loc_18008597F
0x180085a42  cmp     rdi, [rbp+57h+var_98]
0x180085a46  jz      loc_180085B1A
0x180085a4c  lea     rdx, [rdi+2Ch]
0x180085a50  xor     r8d, r8d
0x180085a53  lea     rcx, [rbp+57h+var_60]
0x180085a57  call    ?GuidToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; GuidToString(_GUID const &,bool)
0x180085a5c  mov     rbx, rax
0x180085a5f  cmp     qword ptr [rax+18h], 7
0x180085a64  jbe     short loc_180085A69
0x180085a66  mov     rbx, [rax]
0x180085a69  xor     r8d, r8d
0x180085a6c  lea     rdx, [rbp+57h+var_90]
0x180085a70  lea     rcx, [rbp+57h+var_80]
0x180085a74  call    ?GuidToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; GuidToString(_GUID const &,bool)
0x180085a79  nop
0x180085a7a  cmp     qword ptr [rax+18h], 7
0x180085a7f  jbe     short loc_180085A84
0x180085a81  mov     rax, [rax]
0x180085a84  mov     r8, rbx
0x180085a87  mov     rdx, rax
0x180085a8a  lea     rcx, aRemovepolicypr; "RemovePolicyProviderContexts Policy: %w"...
0x180085a91  call    ?LogMessage@@YAXPEBGZZ; LogMessage(ushort const *,...)
0x180085a96  nop
0x180085a97  lea     rcx, [rbp+57h+var_80]; void *
0x180085a9b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180085aa0  nop
0x180085aa1  lea     rcx, [rbp+57h+var_60]; void *
0x180085aa5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180085aaa  mov     rbx, [rdi+10h]
0x180085aae  xor     edx, edx
0x180085ab0  cmp     [rbx+19h], dl
0x180085ab3  jz      short loc_180085AD2
0x180085ab5  mov     rax, rdi
0x180085ab8  mov     rbx, [rdi+8]
0x180085abc  jmp     short loc_180085ACB
0x180085abe  cmp     rax, [rbx+10h]
0x180085ac2  jnz     short loc_180085AE8
0x180085ac4  mov     rax, rbx
0x180085ac7  mov     rbx, [rbx+8]
0x180085acb  cmp     [rbx+19h], dl
0x180085ace  jz      short loc_180085ABE
0x180085ad0  jmp     short loc_180085AE8
0x180085ad2  mov     rcx, [rbx]
0x180085ad5  cmp     [rcx+19h], dl
0x180085ad8  jnz     short loc_180085AE8
0x180085ada  mov     rbx, rcx
0x180085add  mov     rax, [rcx]
0x180085ae0  mov     rcx, rax
0x180085ae3  cmp     [rax+19h], dl
0x180085ae6  jz      short loc_180085ADA
0x180085ae8  mov     rdx, rdi
0x180085aeb  lea     rcx, [r14+40h]
0x180085aef  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHNSObjectProperty@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHNSObjectProperty@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHNSObjectProperty@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HNSObjectProperty>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HNSObjectProperty>>>,std::_Iterator_base0>)
0x180085af4  mov     edx, 40h ; '@'; struct std::nothrow_t *
  ... truncated ...
```
