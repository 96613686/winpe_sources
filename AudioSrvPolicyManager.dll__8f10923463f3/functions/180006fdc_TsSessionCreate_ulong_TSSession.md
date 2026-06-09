# TsSessionCreate(ulong,TSSession * *)

- ea: `0x180006fdc`
- end: `0x18000750c`
- name: `?TsSessionCreate@@YAJKPEAPEAVTSSession@@@Z`
- size: `1328`
- prototype: `__int64 __fastcall(DWORD SessionId, struct TSSession **)`
- caller_count: `17`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001d40`
- `0x180003554`
- `0x180003694`
- `0x1800037d0`
- `0x180007f08`
- `0x180008050`
- `0x180009090`
- `0x18000cdb0`
- `0x18000d3a8`
- `0x180014710`
- `0x18001bba0`
- `0x18001d170`
- `0x18001e760`
- `0x18001ea20`
- `0x18001f740`
- `0x180020b34`
- `0x1800421f8`

## callees

- `0x180002d68`
- `0x180006fdc`
- `0x18000a384`
- `0x18000a3a8`
- `0x18001d0b0`
- `0x18002352c`
- `0x180023b20`
- `0x180026144`
- `0x180027f10`
- `0x180028a44`
- `0x18002b3f8`
- `0x18002b5c4`
- `0x18002be34`
- `0x18002beb0`
- `0x18002bf30`
- `0x18002c104`
- `0x18002c92c`
- `0x18002caa8`
- `0x180031eb0`
- `0x18003db1c`
- `0x180041c50`
- `0x180041f5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007463`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007463`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000749d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000749d`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180007037`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180007037`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TsSessionCreate(DWORD SessionId, struct TSSession **a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  const char *v8; // r9
  __int64 result; // rax
  CDriverListener *v10; // rax
  struct TSSession *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  int refreshed; // eax
  int v16; // edx
  unsigned int v17; // edi
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rbx
  int v23; // edx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rbx
  int v27; // edx
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rbx
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rbx
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rbx
  int v43; // edx
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rcx
  struct TSSession *v47; // rcx
  const struct _tlgProvider_t *v48; // rax
  __int64 v49; // rdx
  const struct _tlgProvider_t *v50; // r8
  int v51; // r9d
  int v52; // [rsp+20h] [rbp-58h]
  int v53; // [rsp+30h] [rbp-48h] BYREF
  struct TSSession *v54; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v55[8]; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v56[6]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD v58; // [rsp+80h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v59; // [rsp+88h] [rbp+10h] BYREF
  int v60; // [rsp+90h] [rbp+18h] BYREF
  int v61; // [rsp+98h] [rbp+20h] BYREF

  v58 = SessionId;
  *a2 = 0;
  v54 = 0;
  try
  {
    v4 = TSSession::Create();
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3BE,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
        (const char *)(unsigned int)v4,
        v52);
      std::unique_ptr<TSSession>::~unique_ptr<TSSession>(&v54, v6, v7);
      return v5;
    }
    if ( SessionId == (unsigned int)RtlGetCurrentServiceSessionId() )
    {
      v10 = (CDriverListener *)operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
      v59 = (struct _RTL_CRITICAL_SECTION *)v10;
      if ( v10 )
        v10 = CDriverListener::CDriverListener(v10);
      v11 = v54;
      v59 = 0;
      v12 = *((_QWORD *)v54 + 135);
      *((_QWORD *)v54 + 135) = v10;
      if ( v12 )
        std::default_delete<CDriverListener>::operator()();
      std::unique_ptr<CDriverListener>::~unique_ptr<CDriverListener>(&v59);
      if ( !*((_QWORD *)v11 + 135) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3C4,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
          (const char *)0x8007000ELL,
          v52);
        std::unique_ptr<TSSession>::~unique_ptr<TSSession>(&v54, v13, v14);
        return 2147942414LL;
      }
    }
    else
    {
      v11 = v54;
    }
    *((_DWORD *)v11 + 1) = GetTsAudioProtocol(SessionId);
    *((_DWORD *)v11 + 2) = ++dword_180064344;
    refreshed = TsSessionRefreshSessionInformation(v11);
    v17 = refreshed;
    if ( refreshed >= 0 )
    {
      LODWORD(v59) = 1;
      v60 = 400000;
      v61 = -1042284544;
      v20 = std::make_unique<DuckingDescriptorAndId,unsigned short const (&)[5],float,int,int,0>(
              (unsigned int)&v53,
              v16,
              (unsigned int)&v61,
              (unsigned int)&v60,
              (__int64)&v59);
      v22 = *(_QWORD *)std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(
                         v21,
                         v55,
                         (char *)v11 + 1064,
                         v20);
      std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(&v53);
      LODWORD(v59) = 0;
      v60 = 400000;
      v61 = -1047527424;
      v24 = std::make_unique<DuckingDescriptorAndId,unsigned short const (&)[3],float,int,int,0>(
              (unsigned int)&v53,
              v23,
              (unsigned int)&v61,
              (unsigned int)&v60,
              (__int64)&v59);
      v26 = *(_QWORD *)std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(
                         v25,
                         v55,
                         v22,
                         v24);
      std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(&v53);
      LODWORD(v59) = -8388608;
      v60 = 0;
      v61 = 400000;
      v28 = std::make_unique<DuckingDescriptorAndId,unsigned short const (&)[2],float &,int,int,0>(
              (unsigned int)&v53,
              v27,
              (unsigned int)&v59,
              (unsigned int)&v61,
              (__int64)&v60);
      v30 = *(_QWORD *)std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(
                         v29,
                         v55,
                         v26,
                         v28);
      std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(&v53);
      v60 = 0;
      v61 = 400000;
      v53 = -1042284544;
      v31 = std::make_unique<DuckingDescriptorAndId,unsigned short const (&)[2],float,int,int,0>(
              (unsigned int)v55,
              (unsigned int)L"3",
              (unsigned int)&v53,
              (unsigned int)&v61,
              (__int64)&v60);
      v33 = *(_QWORD *)std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(
                         v32,
                         v56,
                         v30,
                         v31);
      std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(v55);
      v60 = 0;
      v61 = 400000;
      v53 = -1061158912;
      v34 = std::make_unique<DuckingDescriptorAndId,unsigned short const (&)[2],float,int,int,0>(
              (unsigned int)v55,
              (unsigned int)L"1",
              (unsigned int)&v53,
              (unsigned int)&v61,
              (__int64)&v60);
      v36 = *(_QWORD *)std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(
                         v35,
                         v56,
                         v33,
                         v34);
      std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(v55);
      v60 = 0;
      v61 = 400000;
      v53 = -1047527424;
      v37 = std::make_unique<DuckingDescriptorAndId,unsigned short const (&)[2],float,int,int,0>(
              (unsigned int)v55,
              (unsigned int)L"2",
              (unsigned int)&v53,
              (unsigned int)&v61,
              (__int64)&v60);
      v39 = *(_QWORD *)std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(
                         v38,
                         v56,
                         v36,
                         v37);
      std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(v55);
      v60 = 1;
      v61 = 400000;
      v53 = -1042284544;
      v40 = std::make_unique<DuckingDescriptorAndId,unsigned short const (&)[2],float,int,int,0>(
              (unsigned int)v55,
              (unsigned int)L"5",
              (unsigned int)&v53,
              (unsigned int)&v61,
              (__int64)&v60);
      v42 = *(_QWORD *)std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(
                         v41,
                         v56,
                         v39,
                         v40);
      std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(v55);
      v60 = 1;
      v61 = 0;
      v53 = 400000;
      v44 = std::make_unique<DuckingDescriptorAndId,unsigned short const (&)[2],float &,int,int,enum EndpointApplicability,0>(
              (unsigned int)v55,
              v43,
              (unsigned int)&v59,
              (unsigned int)&v53,
              (__int64)&v61,
              (__int64)&v60);
      std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(
        v45,
        &v59,
        v42,
        v44);
      std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(v55);
      EnterCriticalSection(&stru_180064458);
      v59 = &stru_180064458;
      std::_Hash<std::_Umap_traits<unsigned long,std::unique_ptr<TSSession>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<TSSession>>>,0>>::emplace<unsigned long &,std::unique_ptr<TSSession>>(
        v46,
        v56,
        &v58,
        &v54);
      v47 = *(struct TSSession **)(v56[0] + 24LL);
      *a2 = v47;
      TsSessionConsiderForPrimaryConsoleAudioSession(v47);
      LeaveCriticalSection(&stru_180064458);
      v48 = AudioSrvPolicyManagerTelemetryProvider::Provider();
      v50 = v48;
      if ( *(_DWORD *)v48 > 4u && (unsigned __int8)tlgKeywordOn(v48, 0x20000, v48) )
      {
        LODWORD(v59) = v58;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v50,
          (unsigned int)byte_1800584C9,
          (_DWORD)v50,
          v51,
          (__int64)&v59);
      }
      std::unique_ptr<TSSession>::~unique_ptr<TSSession>(&v54, v49, v50);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3CB,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
        (const char *)(unsigned int)refreshed,
        v52);
      std::unique_ptr<TSSession>::~unique_ptr<TSSession>(&v54, v18, v19);
      result = v17;
    }
  }
  catch ( ... )
  {
    LODWORD(v59) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x3FD,
                     (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
                     v8);
    return (unsigned int)v59;
  }
  return result;
}

```

## disassembly

```asm
0x180006fdc  mov     [rsp+arg_0], ecx
0x180006fe0  push    rbx
0x180006fe1  push    rsi
0x180006fe2  push    rdi
0x180006fe3  sub     rsp, 60h
0x180006fe7  mov     rsi, rdx
0x180006fea  mov     edi, ecx
0x180006fec  mov     qword ptr [rdx], 0
0x180006ff3  mov     [rsp+78h+var_40], 0
0x180006ffc  lea     rdx, [rsp+78h+var_40]
0x180007001  call    ?Create@TSSession@@SAJKAEAV?$unique_ptr@VTSSession@@U?$default_delete@VTSSession@@@std@@@std@@@Z; TSSession::Create(ulong,std::unique_ptr<TSSession> &)
0x180007006  mov     ebx, eax
0x180007008  test    eax, eax
0x18000700a  jns     short loc_180007037
0x18000700c  mov     rcx, [rsp+78h]; this
0x180007011  mov     r9d, eax; char *
0x180007014  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18000701b  mov     edx, 3BEh; void *
0x180007020  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007025  nop
0x180007026  lea     rcx, [rsp+78h+var_40]
0x18000702b  call    ??1?$unique_ptr@VTSSession@@U?$default_delete@VTSSession@@@std@@@std@@QEAA@XZ; std::unique_ptr<TSSession>::~unique_ptr<TSSession>(void)
0x180007030  mov     eax, ebx
0x180007032  jmp     loc_180007503
0x180007037  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18000703d  cmp     edi, eax
0x18000703f  jnz     loc_1800070DB
0x180007045  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000704c  mov     ecx, 208h; unsigned __int64
0x180007051  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007056  mov     [rsp+78h+arg_8], rax
0x18000705e  test    rax, rax
0x180007061  jz      short loc_18000706B
0x180007063  mov     rcx, rax; this
0x180007066  call    ??0CDriverListener@@QEAA@XZ; CDriverListener::CDriverListener(void)
0x18000706b  mov     rbx, [rsp+78h+var_40]
0x180007070  mov     [rsp+78h+arg_8], 0
0x18000707c  mov     rdx, [rbx+438h]
0x180007083  mov     [rbx+438h], rax
0x18000708a  test    rdx, rdx
0x18000708d  jz      short loc_180007094
0x18000708f  call    ??R?$default_delete@VCDriverListener@@@std@@QEBAXPEAVCDriverListener@@@Z; std::default_delete<CDriverListener>::operator()(CDriverListener *)
0x180007094  lea     rcx, [rsp+78h+arg_8]
0x18000709c  call    ??1?$unique_ptr@VCDriverListener@@U?$default_delete@VCDriverListener@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDriverListener>::~unique_ptr<CDriverListener>(void)
0x1800070a1  cmp     qword ptr [rbx+438h], 0
0x1800070a9  jnz     short loc_1800070E0
0x1800070ab  mov     rcx, [rsp+78h]; this
0x1800070b0  mov     ebx, 8007000Eh
0x1800070b5  mov     r9d, ebx; char *
0x1800070b8  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x1800070bf  mov     edx, 3C4h; void *
0x1800070c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070c9  nop
0x1800070ca  lea     rcx, [rsp+78h+var_40]
0x1800070cf  call    ??1?$unique_ptr@VTSSession@@U?$default_delete@VTSSession@@@std@@@std@@QEAA@XZ; std::unique_ptr<TSSession>::~unique_ptr<TSSession>(void)
0x1800070d4  mov     eax, ebx
0x1800070d6  jmp     loc_180007503
0x1800070db  mov     rbx, [rsp+78h+var_40]
0x1800070e0  mov     ecx, edi; SessionId
0x1800070e2  call    ?GetTsAudioProtocol@@YAIK@Z; GetTsAudioProtocol(ulong)
0x1800070e7  mov     [rbx+4], eax
0x1800070ea  mov     eax, cs:dword_180064344
0x1800070f0  inc     eax
0x1800070f2  mov     cs:dword_180064344, eax
0x1800070f8  mov     [rbx+8], eax
0x1800070fb  mov     rcx, rbx; struct TSSession *
0x1800070fe  call    ?TsSessionRefreshSessionInformation@@YAJPEAVTSSession@@@Z; TsSessionRefreshSessionInformation(TSSession *)
0x180007103  mov     edi, eax
0x180007105  test    eax, eax
0x180007107  jns     short loc_180007134
0x180007109  mov     rcx, [rsp+78h]; this
0x18000710e  mov     r9d, eax; char *
0x180007111  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180007118  mov     edx, 3CBh; void *
0x18000711d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007122  nop
0x180007123  lea     rcx, [rsp+78h+var_40]
0x180007128  call    ??1?$unique_ptr@VTSSession@@U?$default_delete@VTSSession@@@std@@@std@@QEAA@XZ; std::unique_ptr<TSSession>::~unique_ptr<TSSession>(void)
0x18000712d  mov     eax, edi
0x18000712f  jmp     loc_180007503
0x180007134  mov     dword ptr [rsp+78h+arg_8], 1
0x18000713f  mov     edi, 61A80h
0x180007144  mov     [rsp+78h+arg_10], edi
0x18000714b  mov     [rsp+78h+arg_18], 0C1E00000h
0x180007156  lea     rax, [rsp+78h+arg_8]
0x18000715e  mov     [rsp+78h+var_58], rax
0x180007163  lea     r9, [rsp+78h+arg_10]
0x18000716b  lea     r8, [rsp+78h+arg_18]
0x180007173  lea     rcx, [rsp+78h+var_48]
0x180007178  call    ??$make_unique@UDuckingDescriptorAndId@@AEAY04$$CBGMHH$0A@@std@@YA?AV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@0@AEAY04$$CBG$$QEAM$$QEAH2@Z; std::make_unique<DuckingDescriptorAndId,ushort const (&)[5],float,int,int,0>(ushort const (&)[5],float &&,int &&,int &&)
0x18000717d  nop
0x18000717e  mov     r9, rax
0x180007181  lea     r8, [rbx+428h]
0x180007188  lea     rdx, [rsp+78h+var_38]
0x18000718d  call    ??$emplace_after@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@?$forward_list@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@V?$allocator@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@2@@std@@QEAA?AV?$_Flist_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@$$QEAV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@1@@Z; std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<std::unique_ptr<DuckingDescriptorAndId>>>>,std::unique_ptr<DuckingDescriptorAndId> &&)
0x180007192  mov     rbx, [rax]
0x180007195  lea     rcx, [rsp+78h+var_48]
0x18000719a  call    ??1?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@QEAA@XZ; std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(void)
0x18000719f  mov     dword ptr [rsp+78h+arg_8], 0
0x1800071aa  mov     [rsp+78h+arg_10], edi
0x1800071b1  mov     [rsp+78h+arg_18], 0C1900000h
0x1800071bc  lea     rax, [rsp+78h+arg_8]
0x1800071c4  mov     [rsp+78h+var_58], rax
0x1800071c9  lea     r9, [rsp+78h+arg_10]
0x1800071d1  lea     r8, [rsp+78h+arg_18]
0x1800071d9  lea     rcx, [rsp+78h+var_48]
0x1800071de  call    ??$make_unique@UDuckingDescriptorAndId@@AEAY02$$CBGMHH$0A@@std@@YA?AV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@0@AEAY02$$CBG$$QEAM$$QEAH2@Z; std::make_unique<DuckingDescriptorAndId,ushort const (&)[3],float,int,int,0>(ushort const (&)[3],float &&,int &&,int &&)
0x1800071e3  nop
0x1800071e4  mov     r9, rax
0x1800071e7  mov     r8, rbx
0x1800071ea  lea     rdx, [rsp+78h+var_38]
0x1800071ef  call    ??$emplace_after@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@?$forward_list@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@V?$allocator@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@2@@std@@QEAA?AV?$_Flist_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@$$QEAV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@1@@Z; std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<std::unique_ptr<DuckingDescriptorAndId>>>>,std::unique_ptr<DuckingDescriptorAndId> &&)
0x1800071f4  mov     rbx, [rax]
0x1800071f7  lea     rcx, [rsp+78h+var_48]
0x1800071fc  call    ??1?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@QEAA@XZ; std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(void)
0x180007201  mov     dword ptr [rsp+78h+arg_8], 0FF800000h
0x18000720c  mov     [rsp+78h+arg_10], 0
0x180007217  mov     [rsp+78h+arg_18], edi
0x18000721e  lea     rax, [rsp+78h+arg_10]
0x180007226  mov     [rsp+78h+var_58], rax
0x18000722b  lea     r9, [rsp+78h+arg_18]
0x180007233  lea     r8, [rsp+78h+arg_8]
0x18000723b  lea     rcx, [rsp+78h+var_48]
0x180007240  call    ??$make_unique@UDuckingDescriptorAndId@@AEAY01$$CBGAEAMHH$0A@@std@@YA?AV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@0@AEAY01$$CBGAEAM$$QEAH2@Z; std::make_unique<DuckingDescriptorAndId,ushort const (&)[2],float &,int,int,0>(ushort const (&)[2],float &,int &&,int &&)
0x180007245  nop
0x180007246  mov     r9, rax
0x180007249  mov     r8, rbx
0x18000724c  lea     rdx, [rsp+78h+var_38]
0x180007251  call    ??$emplace_after@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@?$forward_list@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@V?$allocator@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@2@@std@@QEAA?AV?$_Flist_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@$$QEAV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@1@@Z; std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<std::unique_ptr<DuckingDescriptorAndId>>>>,std::unique_ptr<DuckingDescriptorAndId> &&)
0x180007256  mov     rbx, [rax]
0x180007259  lea     rcx, [rsp+78h+var_48]
0x18000725e  call    ??1?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@QEAA@XZ; std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(void)
0x180007263  mov     [rsp+78h+arg_10], 0
0x18000726e  mov     [rsp+78h+arg_18], edi
0x180007275  mov     [rsp+78h+var_48], 0C1E00000h
0x18000727d  lea     rax, [rsp+78h+arg_10]
0x180007285  mov     [rsp+78h+var_58], rax
0x18000728a  lea     r9, [rsp+78h+arg_18]
0x180007292  lea     r8, [rsp+78h+var_48]
0x180007297  lea     rdx, a3; "3"
0x18000729e  lea     rcx, [rsp+78h+var_38]
0x1800072a3  call    ??$make_unique@UDuckingDescriptorAndId@@AEAY01$$CBGMHH$0A@@std@@YA?AV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@0@AEAY01$$CBG$$QEAM$$QEAH2@Z; std::make_unique<DuckingDescriptorAndId,ushort const (&)[2],float,int,int,0>(ushort const (&)[2],float &&,int &&,int &&)
0x1800072a8  nop
0x1800072a9  mov     r9, rax
0x1800072ac  mov     r8, rbx
0x1800072af  lea     rdx, [rsp+78h+var_30]
0x1800072b4  call    ??$emplace_after@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@?$forward_list@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@V?$allocator@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@2@@std@@QEAA?AV?$_Flist_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@$$QEAV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@1@@Z; std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<std::unique_ptr<DuckingDescriptorAndId>>>>,std::unique_ptr<DuckingDescriptorAndId> &&)
0x1800072b9  mov     rbx, [rax]
0x1800072bc  lea     rcx, [rsp+78h+var_38]
0x1800072c1  call    ??1?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@QEAA@XZ; std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(void)
0x1800072c6  mov     [rsp+78h+arg_10], 0
0x1800072d1  mov     [rsp+78h+arg_18], edi
0x1800072d8  mov     [rsp+78h+var_48], 0C0C00000h
0x1800072e0  lea     rax, [rsp+78h+arg_10]
0x1800072e8  mov     [rsp+78h+var_58], rax
0x1800072ed  lea     r9, [rsp+78h+arg_18]
0x1800072f5  lea     r8, [rsp+78h+var_48]
0x1800072fa  lea     rdx, a1; "1"
0x180007301  lea     rcx, [rsp+78h+var_38]
0x180007306  call    ??$make_unique@UDuckingDescriptorAndId@@AEAY01$$CBGMHH$0A@@std@@YA?AV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@0@AEAY01$$CBG$$QEAM$$QEAH2@Z; std::make_unique<DuckingDescriptorAndId,ushort const (&)[2],float,int,int,0>(ushort const (&)[2],float &&,int &&,int &&)
0x18000730b  nop
0x18000730c  mov     r9, rax
0x18000730f  mov     r8, rbx
0x180007312  lea     rdx, [rsp+78h+var_30]
0x180007317  call    ??$emplace_after@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@?$forward_list@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@V?$allocator@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@2@@std@@QEAA?AV?$_Flist_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@$$QEAV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@1@@Z; std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<std::unique_ptr<DuckingDescriptorAndId>>>>,std::unique_ptr<DuckingDescriptorAndId> &&)
0x18000731c  mov     rbx, [rax]
0x18000731f  lea     rcx, [rsp+78h+var_38]
0x180007324  call    ??1?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@QEAA@XZ; std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(void)
0x180007329  mov     [rsp+78h+arg_10], 0
0x180007334  mov     [rsp+78h+arg_18], edi
0x18000733b  mov     [rsp+78h+var_48], 0C1900000h
0x180007343  lea     rax, [rsp+78h+arg_10]
0x18000734b  mov     [rsp+78h+var_58], rax
0x180007350  lea     r9, [rsp+78h+arg_18]
0x180007358  lea     r8, [rsp+78h+var_48]
0x18000735d  lea     rdx, a2; "2"
0x180007364  lea     rcx, [rsp+78h+var_38]
0x180007369  call    ??$make_unique@UDuckingDescriptorAndId@@AEAY01$$CBGMHH$0A@@std@@YA?AV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@0@AEAY01$$CBG$$QEAM$$QEAH2@Z; std::make_unique<DuckingDescriptorAndId,ushort const (&)[2],float,int,int,0>(ushort const (&)[2],float &&,int &&,int &&)
0x18000736e  nop
0x18000736f  mov     r9, rax
0x180007372  mov     r8, rbx
0x180007375  lea     rdx, [rsp+78h+var_30]
0x18000737a  call    ??$emplace_after@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@?$forward_list@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@V?$allocator@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@2@@std@@QEAA?AV?$_Flist_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@$$QEAV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@1@@Z; std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<std::unique_ptr<DuckingDescriptorAndId>>>>,std::unique_ptr<DuckingDescriptorAndId> &&)
0x18000737f  mov     rbx, [rax]
0x180007382  lea     rcx, [rsp+78h+var_38]
0x180007387  call    ??1?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@QEAA@XZ; std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(void)
0x18000738c  mov     [rsp+78h+arg_10], 1
0x180007397  mov     [rsp+78h+arg_18], edi
0x18000739e  mov     [rsp+78h+var_48], 0C1E00000h
0x1800073a6  lea     rax, [rsp+78h+arg_10]
0x1800073ae  mov     [rsp+78h+var_58], rax
0x1800073b3  lea     r9, [rsp+78h+arg_18]
0x1800073bb  lea     r8, [rsp+78h+var_48]
0x1800073c0  lea     rdx, a5; "5"
0x1800073c7  lea     rcx, [rsp+78h+var_38]
0x1800073cc  call    ??$make_unique@UDuckingDescriptorAndId@@AEAY01$$CBGMHH$0A@@std@@YA?AV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@0@AEAY01$$CBG$$QEAM$$QEAH2@Z; std::make_unique<DuckingDescriptorAndId,ushort const (&)[2],float,int,int,0>(ushort const (&)[2],float &&,int &&,int &&)
0x1800073d1  nop
0x1800073d2  mov     r9, rax
0x1800073d5  mov     r8, rbx
0x1800073d8  lea     rdx, [rsp+78h+var_30]
0x1800073dd  call    ??$emplace_after@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@?$forward_list@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@V?$allocator@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@2@@std@@QEAA?AV?$_Flist_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@$$QEAV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@1@@Z; std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<std::unique_ptr<DuckingDescriptorAndId>>>>,std::unique_ptr<DuckingDescriptorAndId> &&)
0x1800073e2  mov     rbx, [rax]
0x1800073e5  lea     rcx, [rsp+78h+var_38]
0x1800073ea  call    ??1?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@QEAA@XZ; std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(void)
0x1800073ef  mov     [rsp+78h+arg_10], 1
0x1800073fa  mov     [rsp+78h+arg_18], 0
0x180007405  mov     [rsp+78h+var_48], edi
0x180007409  lea     rax, [rsp+78h+arg_10]
0x180007411  mov     [rsp+78h+var_50], rax
0x180007416  lea     rax, [rsp+78h+arg_18]
0x18000741e  mov     [rsp+78h+var_58], rax
0x180007423  lea     r9, [rsp+78h+var_48]
0x180007428  lea     r8, [rsp+78h+arg_8]
0x180007430  lea     rcx, [rsp+78h+var_38]
0x180007435  call    ??$make_unique@UDuckingDescriptorAndId@@AEAY01$$CBGAEAMHHW4EndpointApplicability@@$0A@@std@@YA?AV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@0@AEAY01$$CBGAEAM$$QEAH2$$QEAW4EndpointApplicability@@@Z; std::make_unique<DuckingDescriptorAndId,ushort const (&)[2],float &,int,int,EndpointApplicability,0>(ushort const (&)[2],float &,int &&,int &&,EndpointApplicability &&)
0x18000743a  nop
0x18000743b  mov     r9, rax
0x18000743e  mov     r8, rbx
0x180007441  lea     rdx, [rsp+78h+arg_8]
0x180007449  call    ??$emplace_after@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@?$forward_list@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@V?$allocator@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@2@@std@@QEAA?AV?$_Flist_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@V?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@@std@@@std@@@1@$$QEAV?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@1@@Z; std::forward_list<std::unique_ptr<DuckingDescriptorAndId>>::emplace_after<std::unique_ptr<DuckingDescriptorAndId>>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<std::unique_ptr<DuckingDescriptorAndId>>>>,std::unique_ptr<DuckingDescriptorAndId> &&)
0x18000744e  nop
0x18000744f  lea     rcx, [rsp+78h+var_38]
0x180007454  call    ??1?$unique_ptr@UDuckingDescriptorAndId@@U?$default_delete@UDuckingDescriptorAndId@@@std@@@std@@QEAA@XZ; std::unique_ptr<DuckingDescriptorAndId>::~unique_ptr<DuckingDescriptorAndId>(void)
0x180007459  lea     rbx, stru_180064458
0x180007460  mov     rcx, rbx; lpCriticalSection
0x180007463  call    cs:__imp_EnterCriticalSection
0x180007469  mov     [rsp+78h+arg_8], rbx
0x180007471  lea     r9, [rsp+78h+var_40]
0x180007476  lea     r8, [rsp+78h+arg_0]
0x18000747e  lea     rdx, [rsp+78h+var_30]
0x180007483  call    ??$emplace@AEAKV?$unique_ptr@VTSSession@@U?$default_delete@VTSSession@@@std@@@std@@@?$_Hash@V?$_Umap_traits@KV?$unique_ptr@VTSSession@@U?$default_delete@VTSSession@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VTSSession@@U?$default_delete@VTSSession@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$unique_ptr@VTSSession@@U?$default_delete@VTSSession@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@AEAK$$QEAV?$unique_ptr@VTSSession@@U?$default_delete@VTSSession@@@std@@@1@@Z; std::_Hash<std::_Umap_traits<ulong,std::unique_ptr<TSSession>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::unique_ptr<TSSession>>>,0>>::emplace<ulong &,std::unique_ptr<TSSession>>(ulong &,std::unique_ptr<TSSession> &&)
0x180007488  mov     rax, [rsp+78h+var_30]
0x18000748d  mov     rcx, [rax+18h]; struct TSSession *
0x180007491  mov     [rsi], rcx
0x180007494  call    ?TsSessionConsiderForPrimaryConsoleAudioSession@@YAXPEAVTSSession@@@Z; TsSessionConsiderForPrimaryConsoleAudioSession(TSSession *)
0x180007499  nop
0x18000749a  mov     rcx, rbx; lpCriticalSection
0x18000749d  call    cs:__imp_LeaveCriticalSection
0x1800074a3  call    ?Provider@AudioSrvPolicyManagerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioSrvPolicyManagerTelemetryProvider::Provider(void)
0x1800074a8  mov     r8, rax
0x1800074ab  mov     ecx, [rax]
0x1800074ad  cmp     ecx, 4
0x1800074b0  jbe     short loc_1800074EE
0x1800074b2  mov     edx, 20000h
0x1800074b7  mov     rcx, rax
0x1800074ba  call    _tlgKeywordOn
0x1800074bf  test    al, al
0x1800074c1  jz      short loc_1800074EE
0x1800074c3  mov     ecx, [rsp+78h+arg_0]
0x1800074ca  mov     dword ptr [rsp+78h+arg_8], ecx
0x1800074d1  lea     rax, [rsp+78h+arg_8]
0x1800074d9  mov     [rsp+78h+var_58], rax
0x1800074de  lea     rdx, byte_1800584C9
0x1800074e5  mov     rcx, r8
0x1800074e8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800074ed  nop
0x1800074ee  lea     rcx, [rsp+78h+var_40]
0x1800074f3  call    ??1?$unique_ptr@VTSSession@@U?$default_delete@VTSSession@@@std@@@std@@QEAA@XZ; std::unique_ptr<TSSession>::~unique_ptr<TSSession>(void)
0x1800074f8  xor     eax, eax
0x1800074fa  jmp     short loc_180007503
0x1800074fc  mov     eax, dword ptr [rsp+78h+arg_8]
0x180007503  add     rsp, 60h
0x180007507  pop     rdi
0x180007508  pop     rsi
0x180007509  pop     rbx
0x18000750a  retn
```
