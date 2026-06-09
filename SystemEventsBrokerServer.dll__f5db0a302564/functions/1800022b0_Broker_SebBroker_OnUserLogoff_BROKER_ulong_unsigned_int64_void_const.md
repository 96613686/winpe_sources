# Broker::SebBroker::OnUserLogoff(_BROKER *,ulong,unsigned __int64,void * const)

- ea: `0x1800022b0`
- end: `0x18000266b`
- name: `?OnUserLogoff@SebBroker@Broker@@CAKPEAU_BROKER@@K_KQEAX@Z`
- size: `955`
- prototype: `static unsigned int(struct _BROKER *, unsigned int, unsigned __int64, void *const)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800022b0`
- `0x180002680`
- `0x180005b0c`
- `0x180006c50`
- `0x1800076a0`
- `0x18000b168`
- `0x18000f370`
- `0x180013920`
- `0x180016150`
- `0x180018ba8`
- `0x180018ce4`
- `0x1800194e4`
- `0x180019798`
- `0x18001ab34`
- `0x18001cf50`
- `0x18001d9ac`
- `0x18001f4d8`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800023a0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800023a0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800025a1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800025a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800023a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800023a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Broker::SebBroker::OnUserLogoff(struct _BROKER *a1, unsigned int a2, unsigned __int64 a3, char *a4)
{
  char *v4; // rsi
  int v5; // r12d
  int v6; // r15d
  __int64 v8; // r8
  char *pSid; // r9
  __int64 v10; // r8
  __int64 *v11; // r14
  unsigned int v12; // r13d
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 *v15; // rax
  __int64 *SessionInfo; // rax
  __int64 v17; // r8
  __int64 v18; // rcx
  std::_Ref_count_base *v19; // rdi
  int SessionID; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  std::_Ref_count_base *v23; // rcx
  __int64 v25; // [rsp+20h] [rbp-178h]
  __int64 v26; // [rsp+20h] [rbp-178h]
  unsigned int v27; // [rsp+30h] [rbp-168h] BYREF
  unsigned __int64 v28; // [rsp+38h] [rbp-160h] BYREF
  __int64 v29; // [rsp+40h] [rbp-158h]
  __int128 v30; // [rsp+48h] [rbp-150h]
  std::_Ref_count_base *v31[2]; // [rsp+58h] [rbp-140h] BYREF
  char *v32; // [rsp+68h] [rbp-130h]
  char *v33; // [rsp+70h] [rbp-128h] BYREF
  char v34; // [rsp+78h] [rbp-120h]
  DWORD CurrentThreadId; // [rsp+7Ch] [rbp-11Ch]
  __int64 v36; // [rsp+80h] [rbp-118h] BYREF
  std::_Ref_count_base *v37; // [rsp+88h] [rbp-110h]
  Broker::SebBroker *v38; // [rsp+90h] [rbp-108h] BYREF
  std::_Ref_count_base *v39; // [rsp+98h] [rbp-100h]
  void **pExceptionObject; // [rsp+A0h] [rbp-F8h] BYREF
  __int128 v41; // [rsp+A8h] [rbp-F0h]
  int v42; // [rsp+B8h] [rbp-E0h]
  int v43; // [rsp+C0h] [rbp-D8h]
  void **v44; // [rsp+C8h] [rbp-D0h] BYREF
  __int128 v45; // [rsp+D0h] [rbp-C8h]
  int v46; // [rsp+E0h] [rbp-B8h]
  int v47; // [rsp+E8h] [rbp-B0h]
  _QWORD v48[3]; // [rsp+F0h] [rbp-A8h] BYREF
  _BYTE v49[32]; // [rsp+108h] [rbp-90h] BYREF
  _BYTE v50[40]; // [rsp+128h] [rbp-70h] BYREF

  v4 = a4;
  v5 = a3;
  v6 = a2;
  v27 = a2;
  v28 = a3;
  v32 = a4;
  std::vector<_GUID>::vector<_GUID>(v48);
  std::wstring::wstring(v49);
  std::wstring::wstring(v50);
  v30 = 0;
  *(_OWORD *)v31 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_dd_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x43u, v8, v5, v6, pSid);
  Broker::SebBroker::GetInstance(&v38);
  v11 = (__int64 *)v38;
  if ( !v38 )
  {
    v12 = 21;
LABEL_33:
    v19 = (std::_Ref_count_base *)*((_QWORD *)&v30 + 1);
    goto LABEL_34;
  }
  v12 = 0;
  if ( *((struct _BROKER **)v38 + 17) != a1 )
  {
    v12 = 5;
    goto LABEL_33;
  }
  v33 = (char *)v38 + 8;
  RtlAcquireSRWLockExclusive((char *)v38 + 8);
  CurrentThreadId = GetCurrentThreadId();
  v34 = 1;
  v13 = std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::count(
          v11 + 2,
          &v28);
  try
  {
    if ( v13 != 1 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_dd_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x44u, v14, v5, v6, v4);
      v41 = 0;
      v42 = 6;
      pExceptionObject = &Broker::BILayer::Failure::`vftable';
      v43 = -1073741275;
      throw (Broker::BILayer::Failure *)&pExceptionObject;
    }
    v15 = std::map<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>::at(
            v11 + 2,
            &v28);
    std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>::operator=(v31, v15);
    LOBYTE(v25) = 0;
    SessionInfo = Broker::SebBroker::GetSessionInfo((__int64)v11, &v36, v6, v4, v25);
    v29 = *SessionInfo;
    v18 = v29;
    v19 = (std::_Ref_count_base *)SessionInfo[1];
    *SessionInfo = 0;
    SessionInfo[1] = 0;
    *(_QWORD *)&v30 = v18;
    *((_QWORD *)&v30 + 1) = v19;
    if ( v37 )
    {
      std::_Ref_count_base::_Decref(v37);
      v18 = v29;
    }
    if ( !v18 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_dd_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x45u, v17, v5, v6, v4);
      v45 = 0;
      v46 = 6;
      v44 = &Broker::BILayer::Failure::`vftable';
      v47 = -1073741275;
      throw (Broker::BILayer::Failure *)&v44;
    }
    std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<Broker::_SessionInfo>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>,0>>::erase(
      (__int64 *)v31[0],
      &v27);
    SessionID = Broker::SebBroker::GetSessionID((Broker::SebBroker *)v11, v4);
    if ( SessionID == -1 )
    {
      if ( !*((_QWORD *)v31[0] + 1) )
      {
        std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::erase(
          v11 + 2,
          &v28);
        if ( v31[1] )
          std::_Ref_count_base::_Decref(v31[1]);
        v31[1] = 0;
      }
      RtlReleaseSRWLockExclusive(v11 + 1);
      v23 = v19;
      v19 = 0;
      *((_QWORD *)&v30 + 1) = 0;
      if ( v23 )
        std::_Ref_count_base::_Decref(v23);
    }
    else
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        LODWORD(v26) = SessionID;
        WPP_SF__sid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, v4, v26);
      }
      Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)&v33);
    }
  }
  catch ( ... )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
    LODWORD(v29) = 1359;
    v12 = 1359;
    LOBYTE(v6) = v27;
    v4 = v32;
    v5 = v28;
    goto LABEL_33;
  }
LABEL_34:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_dd_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x48u, v10, v5, v6, v4);
  if ( v39 )
    std::_Ref_count_base::_Decref(v39);
  if ( v31[1] )
    std::_Ref_count_base::_Decref(v31[1]);
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v48);
  return v12;
}

```

## disassembly

```asm
0x1800022b0  push    rbx
0x1800022b2  push    rsi
0x1800022b3  push    rdi
0x1800022b4  push    r12
0x1800022b6  push    r13
0x1800022b8  push    r14
0x1800022ba  push    r15
0x1800022bc  sub     rsp, 160h
0x1800022c3  mov     rax, cs:__security_cookie
0x1800022ca  xor     rax, rsp
0x1800022cd  mov     [rsp+198h+var_48], rax
0x1800022d5  mov     rsi, r9
0x1800022d8  mov     r12, r8
0x1800022db  mov     r15d, edx
0x1800022de  mov     rdi, rcx
0x1800022e1  mov     [rsp+198h+var_168], edx
0x1800022e5  mov     [rsp+198h+var_160], r8
0x1800022ea  mov     [rsp+198h+var_130], r9
0x1800022ef  lea     rcx, [rsp+198h+var_A8]
0x1800022f7  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x1800022fc  lea     rcx, [rsp+198h+var_90]
0x180002304  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180002309  lea     rcx, [rsp+198h+var_70]
0x180002311  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180002316  nop
0x180002317  xorps   xmm1, xmm1
0x18000231a  movdqu  [rsp+198h+var_150], xmm1
0x180002320  xorps   xmm0, xmm0
0x180002323  movdqu  xmmword ptr [rsp+198h+var_140], xmm0
0x180002329  mov     rcx, cs:WPP_GLOBAL_Control
0x180002330  test    byte ptr [rcx+1Ch], 1
0x180002334  jz      short loc_180002357
0x180002336  cmp     byte ptr [rcx+19h], 4
0x18000233a  jb      short loc_180002357
0x18000233c  mov     edx, 43h ; 'C'
0x180002341  mov     [rsp+198h+pSid], r9; pSid
0x180002346  mov     dword ptr [rsp+198h+var_178], r15d; char
0x18000234b  mov     r9d, r12d
0x18000234e  mov     rcx, [rcx+10h]; LoggerHandle
0x180002352  call    WPP_SF_dd_sid_
0x180002357  lea     rcx, [rsp+198h+var_108]
0x18000235f  call    ?GetInstance@SebBroker@Broker@@SA?AV?$shared_ptr@VSebBroker@Broker@@@std@@XZ; Broker::SebBroker::GetInstance(void)
0x180002364  nop
0x180002365  mov     r14, [rsp+198h+var_108]
0x18000236d  xor     ebx, ebx
0x18000236f  test    r14, r14
0x180002372  jnz     short loc_18000237D
0x180002374  lea     r13d, [r14+15h]
0x180002378  jmp     loc_1800025D3
0x18000237d  mov     r13d, ebx
0x180002380  cmp     [r14+88h], rdi
0x180002387  jz      short loc_180002394
0x180002389  mov     r13d, 5
0x18000238f  jmp     loc_1800025D3
0x180002394  lea     rax, [r14+8]
0x180002398  mov     [rsp+198h+var_128], rax
0x18000239d  mov     rcx, rax
0x1800023a0  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800023a6  call    cs:__imp_GetCurrentThreadId
0x1800023ac  mov     [rsp+198h+var_11C], eax
0x1800023b0  mov     [rsp+198h+var_120], 1
0x1800023b5  lea     rdx, [rsp+198h+var_160]
0x1800023ba  lea     rcx, [r14+10h]
0x1800023be  call    ?count@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEBA_KAEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::count(unsigned __int64 const &)
0x1800023c3  cmp     rax, 1
0x1800023c7  jz      short loc_18000243B
0x1800023c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023d0  test    byte ptr [rcx+1Ch], 1
0x1800023d4  jz      short loc_1800023F7
0x1800023d6  cmp     byte ptr [rcx+19h], 2
0x1800023da  jb      short loc_1800023F7
0x1800023dc  mov     edx, 44h ; 'D'
0x1800023e1  mov     [rsp+198h+pSid], rsi; pSid
0x1800023e6  mov     dword ptr [rsp+198h+var_178], r15d; char
0x1800023eb  mov     r9d, r12d
0x1800023ee  mov     rcx, [rcx+10h]; LoggerHandle
0x1800023f2  call    WPP_SF_dd_sid_
0x1800023f7  xorps   xmm0, xmm0
0x1800023fa  movups  [rsp+198h+var_F0], xmm0
0x180002402  mov     [rsp+198h+var_E0], 6
0x18000240d  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x180002414  mov     [rsp+198h+pExceptionObject], rax
0x18000241c  mov     [rsp+198h+var_D8], 0C0000225h
0x180002427  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x18000242e  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x180002436  call    _CxxThrowException_0
0x18000243b  lea     rdx, [rsp+198h+var_160]
0x180002440  lea     rcx, [r14+10h]
0x180002444  call    ?at@?$map@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@2@AEB_K@Z; std::map<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>::at(unsigned __int64 const &)
0x180002449  mov     rdx, rax
0x18000244c  lea     rcx, [rsp+198h+var_140]
0x180002451  call    ??4?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>::operator=(std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>> const &)
0x180002456  mov     [rsp+198h+var_178], bl
0x18000245a  mov     r9, rsi
0x18000245d  mov     r8d, r15d
0x180002460  lea     rdx, [rsp+198h+var_118]
0x180002468  mov     rcx, r14
0x18000246b  call    ?GetSessionInfo@SebBroker@Broker@@QEAA?AV?$shared_ptr@U_SessionInfo@Broker@@@std@@KQEAX_N@Z; Broker::SebBroker::GetSessionInfo(ulong,void * const,bool)
0x180002470  mov     rcx, [rax]
0x180002473  mov     [rsp+198h+var_158], rcx
0x180002478  mov     rdi, [rax+8]
0x18000247c  mov     [rax], rbx
0x18000247f  mov     [rax+8], rbx
0x180002483  mov     qword ptr [rsp+198h+var_150], rcx
0x180002488  mov     qword ptr [rsp+198h+var_150+8], rdi
0x18000248d  cmp     [rsp+198h+var_110], rbx
0x180002495  jz      short loc_1800024A9
0x180002497  mov     rcx, [rsp+198h+var_110]; this
0x18000249f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800024a4  mov     rcx, [rsp+198h+var_158]
0x1800024a9  test    rcx, rcx
0x1800024ac  jnz     short loc_180002520
0x1800024ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024b5  test    byte ptr [rcx+1Ch], 1
0x1800024b9  jz      short loc_1800024DC
0x1800024bb  cmp     byte ptr [rcx+19h], 2
0x1800024bf  jb      short loc_1800024DC
0x1800024c1  mov     edx, 45h ; 'E'
0x1800024c6  mov     [rsp+198h+pSid], rsi; pSid
0x1800024cb  mov     dword ptr [rsp+198h+var_178], r15d; char
0x1800024d0  mov     r9d, r12d
0x1800024d3  mov     rcx, [rcx+10h]; LoggerHandle
0x1800024d7  call    WPP_SF_dd_sid_
0x1800024dc  xorps   xmm0, xmm0
0x1800024df  movups  [rsp+198h+var_C8], xmm0
0x1800024e7  mov     [rsp+198h+var_B8], 6
0x1800024f2  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x1800024f9  mov     [rsp+198h+var_D0], rax
0x180002501  mov     [rsp+198h+var_B0], 0C0000225h
0x18000250c  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x180002513  lea     rcx, [rsp+198h+var_D0]; pExceptionObject
0x18000251b  call    _CxxThrowException_0
0x180002520  lea     rdx, [rsp+198h+var_168]
0x180002525  mov     rcx, [rsp+198h+var_140]
0x18000252a  call    ?erase@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>,0>>::erase(ulong const &)
0x18000252f  mov     rdx, rsi; void *
0x180002532  mov     rcx, r14; this
0x180002535  call    ?GetSessionID@SebBroker@Broker@@AEAAKQEAX@Z; Broker::SebBroker::GetSessionID(void * const)
0x18000253a  cmp     eax, 0FFFFFFFFh
0x18000253d  jz      short loc_180002570
0x18000253f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002546  test    byte ptr [rcx+1Ch], 1
0x18000254a  jz      short loc_180002563
0x18000254c  cmp     byte ptr [rcx+19h], 4
0x180002550  jb      short loc_180002563
0x180002552  mov     dword ptr [rsp+198h+var_178], eax; char
0x180002556  mov     r9, rsi
0x180002559  mov     rcx, [rcx+10h]; LoggerHandle
0x18000255d  call    WPP_SF__sid_d
0x180002562  nop
0x180002563  lea     rcx, [rsp+198h+var_128]; this
0x180002568  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x18000256d  nop
0x18000256e  jmp     short loc_1800025D8
0x180002570  mov     rax, [rsp+198h+var_140]
0x180002575  cmp     [rax+8], rbx
0x180002579  jnz     short loc_18000259D
0x18000257b  lea     rdx, [rsp+198h+var_160]
0x180002580  lea     rcx, [r14+10h]
0x180002584  call    ?erase@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::erase(unsigned __int64 const &)
0x180002589  mov     rcx, [rsp+198h+var_140+8]; this
0x18000258e  test    rcx, rcx
0x180002591  jz      short loc_180002598
0x180002593  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180002598  mov     [rsp+198h+var_140+8], rbx
0x18000259d  lea     rcx, [r14+8]
0x1800025a1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800025a7  mov     rcx, rdi; this
0x1800025aa  mov     rdi, rbx
0x1800025ad  mov     qword ptr [rsp+198h+var_150+8], rbx
0x1800025b2  test    rcx, rcx
0x1800025b5  jz      short loc_1800025BD
0x1800025b7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800025bc  nop
0x1800025bd  jmp     short loc_1800025D8
0x1800025bf  mov     r13d, dword ptr [rsp+198h+var_158]
0x1800025c4  mov     r15d, [rsp+198h+var_168]
0x1800025c9  mov     rsi, [rsp+198h+var_130]
0x1800025ce  mov     r12, [rsp+198h+var_160]
0x1800025d3  mov     rdi, qword ptr [rsp+198h+var_150+8]
0x1800025d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025df  test    byte ptr [rcx+1Ch], 1
0x1800025e3  jz      short loc_180002607
0x1800025e5  cmp     byte ptr [rcx+19h], 4
0x1800025e9  jb      short loc_180002607
0x1800025eb  mov     edx, 48h ; 'H'
0x1800025f0  mov     [rsp+198h+pSid], rsi; pSid
0x1800025f5  mov     dword ptr [rsp+198h+var_178], r15d; char
0x1800025fa  mov     r9d, r12d
0x1800025fd  mov     rcx, [rcx+10h]; LoggerHandle
0x180002601  call    WPP_SF_dd_sid_
0x180002606  nop
0x180002607  mov     rcx, [rsp+198h+var_100]; this
0x18000260f  test    rcx, rcx
0x180002612  jz      short loc_18000261A
0x180002614  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180002619  nop
0x18000261a  mov     rcx, [rsp+198h+var_140+8]; this
0x18000261f  test    rcx, rcx
0x180002622  jz      short loc_18000262A
0x180002624  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180002629  nop
0x18000262a  test    rdi, rdi
0x18000262d  jz      short loc_180002638
0x18000262f  mov     rcx, rdi; this
0x180002632  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180002637  nop
0x180002638  lea     rcx, [rsp+198h+var_A8]; this
0x180002640  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180002645  mov     eax, r13d
0x180002648  mov     rcx, [rsp+198h+var_48]
0x180002650  xor     rcx, rsp; StackCookie
0x180002653  call    __security_check_cookie
0x180002658  add     rsp, 160h
0x18000265f  pop     r15
0x180002661  pop     r14
0x180002663  pop     r13
0x180002665  pop     r12
0x180002667  pop     rdi
0x180002668  pop     rsi
0x180002669  pop     rbx
0x18000266a  retn
```
