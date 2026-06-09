# NgcKspServer::NgcUserIdKey::Open(void * const,ushort const *)

- ea: `0x18003dad0`
- end: `0x18003e125`
- name: `?Open@NgcUserIdKey@NgcKspServer@@EEAAJQEAXPEBG@Z`
- size: `1621`
- prototype: `__int64 __fastcall(NgcKspServer::NgcUserIdKey *__hidden this, void *const, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000e570`
- `0x18000e960`
- `0x180010990`
- `0x180012050`
- `0x1800126d0`
- `0x1800128e4`
- `0x180016350`
- `0x180016400`
- `0x18002c918`
- `0x18002d740`
- `0x18002dc90`
- `0x18003d8c0`
- `0x18003dad0`
- `0x1800459e0`
- `0x180046d90`
- `0x180047228`
- `0x1800512bc`
- `0x18005cee0`
- `0x18005d2b0`
- `0x18005dd80`
- `0x18007612c`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003dcaa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003dcaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003deab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003deab`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003de6a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003dfd9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003e076`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003de6a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003dfd9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003e076`

## string_xrefs

- `0x18003df01`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall NgcKspServer::NgcUserIdKey::Open(
        NgcKspServer::NgcUserIdKey *this,
        void *const a2,
        unsigned __int16 *a3)
{
  signed int RpcCallerInfo; // eax
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rdx
  void *v9; // rcx
  int v10; // esi
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rdi
  ULONGLONG Ptr; // rax
  __int64 v15; // rcx
  volatile signed __int32 *v16; // rsi
  struct NgcTransport *v17; // rbx
  bool *v18; // r9
  int ShouldAddBioProtector; // eax
  __int64 v20; // rax
  char IsEnabled; // al
  __int64 v22; // rcx
  char *v23; // r9
  char *v24; // r8
  char *v25; // rdx
  bool v26; // zf
  __int64 (__fastcall *v27)(__int64, char *, char *, char *, char *); // rax
  int v28; // eax
  int v29; // eax
  __int64 v30; // rcx
  char *UserDataCount; // [rsp+20h] [rbp-E0h]
  unsigned int v32; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v33; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v34; // [rsp+38h] [rbp-C8h] BYREF
  struct NgcTransport *v35; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h]
  __int64 v38; // [rsp+68h] [rbp-98h]
  __int128 v39; // [rsp+70h] [rbp-90h]
  void *v40; // [rsp+80h] [rbp-80h]
  __int64 v41; // [rsp+88h] [rbp-78h]
  char *v42; // [rsp+90h] [rbp-70h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+98h] [rbp-68h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v45; // [rsp+B0h] [rbp-50h]
  _BYTE v46[24]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v47; // [rsp+D8h] [rbp-28h]
  _BYTE v48[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v49[32]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v50[32]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v51[32]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v52[40]; // [rsp+168h] [rbp+68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+190h] [rbp+90h] BYREF
  __int16 *v54; // [rsp+1A0h] [rbp+A0h]
  int v55; // [rsp+1A8h] [rbp+A8h]
  int v56; // [rsp+1ACh] [rbp+ACh]
  unsigned int *v57; // [rsp+1B0h] [rbp+B0h]
  __int64 v58; // [rsp+1B8h] [rbp+B8h]
  struct _EVENT_DATA_DESCRIPTOR v59; // [rsp+1C0h] [rbp+C0h] BYREF
  char *v60; // [rsp+1D0h] [rbp+D0h]
  int v61; // [rsp+1D8h] [rbp+D8h]
  int v62; // [rsp+1DCh] [rbp+DCh]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = a2;
  v41 = 0;
  RpcCallerInfo = NgcUtils::RpcCallerInfo::GetRpcCallerInfo((NgcUtils::RpcCallerInfo *)&v36);
  if ( RpcCallerInfo < 0 )
  {
    win32_exception::win32_exception((win32_exception *)&EventDescriptor, RpcCallerInfo);
    throw (hresult_exception *)&EventDescriptor;
  }
  std::wstring::wstring((char **)&EventDescriptor, a3);
  NgcUtils::NgcKeyName::NgcKeyName(v46, &EventDescriptor);
  v7 = v45;
  if ( v45 > 7 )
  {
    v8 = 2 * v45 + 2;
    if ( v8 < 0x1000 )
    {
      v9 = *(void **)&EventDescriptor.Id;
    }
    else
    {
      v9 = *(void **)(*(_QWORD *)&EventDescriptor.Id - 8LL);
      if ( (unsigned __int64)(*(_QWORD *)&EventDescriptor.Id - (_QWORD)v9 - 8LL) > 0x1F )
        __fastfail(5u);
      v8 = 2 * v45 + 41;
    }
    operator delete(v9, v8);
  }
  v44 = 0;
  v45 = 7;
  EventDescriptor.Id = 0;
  v59 = 0;
  v35 = 0;
  v34 = 0;
  LOBYTE(v7) = 1;
  v10 = NgcKspServer::NgcKspKey::AddSidAndCheckAccessAndFindKey(a2, v7, v46, &v59, &v35, &v34);
  if ( v10 >= 0 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 34);
    v42 = (char *)this + 272;
    Ptr = v59.Ptr;
    v15 = *(_QWORD *)&v59.Size;
    v59 = 0;
    *((_QWORD *)this + 44) = Ptr;
    v16 = (volatile signed __int32 *)*((_QWORD *)this + 45);
    *((_QWORD *)this + 45) = v15;
    if ( v16 )
    {
      if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    std::vector<unsigned char>::operator=((char *)this + 32, v46);
    *(_OWORD *)((char *)this + 56) = v47;
    std::wstring::operator=((char *)this + 72, v48);
    std::wstring::operator=((char *)this + 104, v49);
    std::wstring::operator=((char *)this + 136, v50);
    std::wstring::operator=((char *)this + 168, v51);
    std::wstring::operator=((char *)this + 200, v52);
    v17 = v35;
    *((_DWORD *)this + 6) = *((_DWORD *)v35 + 10);
    ShouldAddBioProtector = NgcUtils::ShouldAddBioProtector(
                              *((NgcUtils **)this + 44),
                              v17,
                              (NgcKspServer::NgcUserIdKey *)((char *)this + 370),
                              v18);
    if ( ShouldAddBioProtector < 0 && (unsigned int)dword_180122070 > 3 )
    {
      v33 = ShouldAddBioProtector;
      v57 = &v33;
      v58 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 3;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_180122078;
      UserData.Size = *(unsigned __int16 *)off_180122078;
      UserData.Reserved = 2;
      v54 = word_1801020F2;
      v55 = 41;
      v56 = 1;
      v32 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    v20 = v34;
    *((_DWORD *)this + 58) = *(_DWORD *)(v34 + 96);
    *((_DWORD *)this + 129) = *(_DWORD *)(v20 + 100);
    *((_WORD *)this + 148) = 257;
    if ( NgcKspServer::NgcUserIdKey::IsFidoKey(this) )
      *((_BYTE *)this + 584) = 0;
    if ( this != (NgcKspServer::NgcUserIdKey *)-272LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 34);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
    v22 = *((_QWORD *)this + 44);
    v23 = (char *)this + 72;
    v24 = (char *)this + 136;
    v25 = (char *)this + 56;
    UserDataCount = (char *)this + 104;
    v26 = IsEnabled == 0;
    v27 = *(__int64 (__fastcall **)(__int64, char *, char *, char *, char *))(*(_QWORD *)v22 + 168LL);
    if ( v26 )
    {
      v29 = v27(v22, v25, v24, v23, UserDataCount);
      if ( v29 < 0 && (unsigned int)dword_180122070 > 2 )
      {
        v32 = v29;
        v57 = &v32;
        v58 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 2;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_180122078;
        UserData.Size = *(unsigned __int16 *)off_180122078;
        UserData.Reserved = 2;
        v54 = (__int16 *)byte_1801020C5;
        v55 = 33;
        v56 = 1;
        v33 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      }
    }
    else
    {
      v28 = ((__int64 (__fastcall *)(__int64, char *, char *, char *))v27)(v22, v25, v24, v23);
      if ( v28 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1721,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
          (const char *)(unsigned int)v28,
          (int)UserDataCount);
    }
    if ( (unsigned int)dword_180122070 > 4 )
    {
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 4;
      EventDescriptor.Keyword = 0;
      v59.Ptr = (ULONGLONG)off_180122078;
      v59.Size = *(unsigned __int16 *)off_180122078;
      v59.Reserved = 2;
      v60 = byte_1801020A3;
      v61 = 22;
      v62 = 1;
      v32 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &v59);
    }
    NgcUtils::NgcKeyName::LogState((NgcKspServer::NgcUserIdKey *)((char *)this + 32), 0);
    std::unique_ptr<NgcTransportKeyInfo>::~unique_ptr<NgcTransportKeyInfo>(&v34);
    std::default_delete<NgcTransportContainerInfo>::operator()(v30, v17);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v52);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v51);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v50);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v49);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v48);
    std::vector<unsigned char>::_Tidy(v46);
    NgcUtils::RpcCallerInfo::~RpcCallerInfo((NgcUtils::RpcCallerInfo *)&v36);
    return 0;
  }
  else
  {
    std::unique_ptr<NgcTransportKeyInfo>::~unique_ptr<NgcTransportKeyInfo>(&v34);
    if ( v35 )
      std::default_delete<NgcTransportContainerInfo>::operator()(v11, v35);
    v12 = *(volatile signed __int32 **)&v59.Size;
    if ( *(_QWORD *)&v59.Size
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v59.Size + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v52);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v51);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v50);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v49);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v48);
    std::vector<unsigned char>::_Tidy(v46);
    NgcUtils::RpcCallerInfo::~RpcCallerInfo((NgcUtils::RpcCallerInfo *)&v36);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x18003dad0  mov     [rsp-8+arg_18], rbx
0x18003dad5  push    rbp
0x18003dad6  push    rsi
0x18003dad7  push    rdi
0x18003dad8  push    r12
0x18003dada  push    r13
0x18003dadc  push    r14
0x18003dade  push    r15
0x18003dae0  lea     rbp, [rsp-0F0h]
0x18003dae8  sub     rsp, 1F0h
0x18003daef  mov     rax, cs:__security_cookie
0x18003daf6  xor     rax, rsp
0x18003daf9  mov     [rbp+120h+var_40], rax
0x18003db00  mov     rsi, r8
0x18003db03  mov     rbx, rdx
0x18003db06  mov     rdi, rcx
0x18003db09  xorps   xmm0, xmm0
0x18003db0c  movdqa  [rsp+220h+var_1D0], xmm0
0x18003db12  xor     r12d, r12d
0x18003db15  mov     [rsp+220h+var_1C0], r12
0x18003db1a  mov     [rsp+220h+var_1B8], r12
0x18003db1f  movdqa  [rsp+220h+var_1B0], xmm0
0x18003db25  mov     [rbp+120h+var_1A0], rdx
0x18003db29  mov     [rbp+120h+var_198], r12
0x18003db2d  lea     rcx, [rsp+220h+var_1D0]; this
0x18003db32  call    ?GetRpcCallerInfo@RpcCallerInfo@NgcUtils@@AEAAJXZ; NgcUtils::RpcCallerInfo::GetRpcCallerInfo(void)
0x18003db37  test    eax, eax
0x18003db39  js      loc_18003E109
0x18003db3f  mov     rdx, rsi
0x18003db42  lea     rcx, [rbp+120h+EventDescriptor]
0x18003db46  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003db4b  nop
0x18003db4c  lea     rdx, [rbp+120h+EventDescriptor]
0x18003db50  lea     rcx, [rbp+120h+var_160]
0x18003db54  call    ??0NgcKeyName@NgcUtils@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::NgcKeyName::NgcKeyName(std::wstring const &)
0x18003db59  nop
0x18003db5a  mov     rdx, [rbp+120h+var_170]
0x18003db5e  cmp     rdx, 7
0x18003db62  jbe     short loc_18003DB9F
0x18003db64  mov     rax, qword ptr [rbp+120h+EventDescriptor.Id]
0x18003db68  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18003db70  cmp     rdx, 1000h
0x18003db77  jb      short loc_18003DB97
0x18003db79  mov     rcx, [rax-8]
0x18003db7d  sub     rax, rcx
0x18003db80  sub     rax, 8
0x18003db84  cmp     rax, 1Fh
0x18003db88  ja      short loc_18003DB90
0x18003db8a  add     rdx, 27h ; '''
0x18003db8e  jmp     short loc_18003DB9A
0x18003db90  mov     ecx, 5
0x18003db95  int     29h; Win8: RtlFailFast(ecx)
0x18003db97  mov     rcx, rax; void *
0x18003db9a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003db9f  mov     [rbp+120h+var_178], r12
0x18003dba3  mov     [rbp+120h+var_170], 7
0x18003dbab  mov     [rbp+120h+EventDescriptor.Id], r12w
0x18003dbb0  xorps   xmm0, xmm0
0x18003dbb3  movdqu  xmmword ptr [rbp+120h+var_60.Ptr], xmm0
0x18003dbbb  mov     [rsp+220h+var_1E0], r12
0x18003dbc0  mov     [rsp+220h+var_1E8], r12
0x18003dbc5  lea     rax, [rsp+220h+var_1E8]
0x18003dbca  mov     [rsp+220h+UserData], rax
0x18003dbcf  lea     rax, [rsp+220h+var_1E0]
0x18003dbd4  mov     qword ptr [rsp+220h+UserDataCount], rax
0x18003dbd9  lea     r9, [rbp+120h+var_60]
0x18003dbe0  lea     r8, [rbp+120h+var_160]
0x18003dbe4  mov     dl, 1
0x18003dbe6  mov     rcx, rbx
0x18003dbe9  call    ?AddSidAndCheckAccessAndFindKey@NgcKspKey@NgcKspServer@@KAJQEAX_NAEAVNgcKeyName@NgcUtils@@PEAV?$shared_ptr@VNgcTransport@@@std@@PEAV?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@6@PEAV?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@6@@Z; NgcKspServer::NgcKspKey::AddSidAndCheckAccessAndFindKey(void * const,bool,NgcUtils::NgcKeyName &,std::shared_ptr<NgcTransport> *,std::unique_ptr<NgcTransportContainerInfo> *,std::unique_ptr<NgcTransportKeyInfo> *)
0x18003dbee  mov     esi, eax
0x18003dbf0  test    eax, eax
0x18003dbf2  jns     loc_18003DCA0
0x18003dbf8  lea     rcx, [rsp+220h+var_1E8]
0x18003dbfd  call    ??1?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@QEAA@XZ; std::unique_ptr<NgcTransportKeyInfo>::~unique_ptr<NgcTransportKeyInfo>(void)
0x18003dc02  nop
0x18003dc03  mov     rdx, [rsp+220h+var_1E0]
0x18003dc08  test    rdx, rdx
0x18003dc0b  jz      short loc_18003DC13
0x18003dc0d  call    ??R?$default_delete@UNgcTransportContainerInfo@@@std@@QEBAXPEAUNgcTransportContainerInfo@@@Z; std::default_delete<NgcTransportContainerInfo>::operator()(NgcTransportContainerInfo *)
0x18003dc12  nop
0x18003dc13  mov     rdi, qword ptr [rbp+120h+var_60.Size]
0x18003dc1a  test    rdi, rdi
0x18003dc1d  jz      short loc_18003DC58
0x18003dc1f  mov     ebx, 0FFFFFFFFh
0x18003dc24  mov     eax, ebx
0x18003dc26  lock xadd [rdi+8], eax
0x18003dc2b  cmp     eax, 1
0x18003dc2e  jnz     short loc_18003DC58
0x18003dc30  mov     rax, [rdi]
0x18003dc33  mov     rcx, rdi
0x18003dc36  mov     rax, [rax]
0x18003dc39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc3e  lock xadd [rdi+0Ch], ebx
0x18003dc43  cmp     ebx, 1
0x18003dc46  jnz     short loc_18003DC58
0x18003dc48  mov     rax, [rdi]
0x18003dc4b  mov     rcx, rdi
0x18003dc4e  mov     rax, [rax+8]
0x18003dc52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc57  nop
0x18003dc58  lea     rcx, [rbp+120h+var_B8]
0x18003dc5c  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18003dc61  lea     rcx, [rbp+120h+var_D8]
0x18003dc65  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18003dc6a  lea     rcx, [rbp+120h+var_F8]
0x18003dc6e  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18003dc73  lea     rcx, [rbp+120h+var_118]
0x18003dc77  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18003dc7c  lea     rcx, [rbp+120h+var_138]
0x18003dc80  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18003dc85  lea     rcx, [rbp+120h+var_160]
0x18003dc89  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003dc8e  nop
0x18003dc8f  lea     rcx, [rsp+220h+var_1D0]; this
0x18003dc94  call    ??1RpcCallerInfo@NgcUtils@@QEAA@XZ; NgcUtils::RpcCallerInfo::~RpcCallerInfo(void)
0x18003dc99  mov     eax, esi
0x18003dc9b  jmp     loc_18003E0DF
0x18003dca0  lea     r14, [rdi+110h]
0x18003dca7  mov     rcx, r14; SRWLock
0x18003dcaa  call    cs:__imp_AcquireSRWLockExclusive
0x18003dcb0  mov     [rbp+120h+var_190], r14
0x18003dcb4  mov     rax, [rbp+120h+var_60.Ptr]
0x18003dcbb  mov     rcx, qword ptr [rbp+120h+var_60.Size]
0x18003dcc2  xorps   xmm0, xmm0
0x18003dcc5  movdqu  xmmword ptr [rbp+120h+var_60.Ptr], xmm0
0x18003dccd  mov     [rdi+160h], rax
0x18003dcd4  mov     rsi, [rdi+168h]
0x18003dcdb  mov     [rdi+168h], rcx
0x18003dce2  test    rsi, rsi
0x18003dce5  jz      short loc_18003DD1F
0x18003dce7  mov     ebx, 0FFFFFFFFh
0x18003dcec  mov     eax, ebx
0x18003dcee  lock xadd [rsi+8], eax
0x18003dcf3  cmp     eax, 1
0x18003dcf6  jnz     short loc_18003DD1F
0x18003dcf8  mov     rax, [rsi]
0x18003dcfb  mov     rcx, rsi
0x18003dcfe  mov     rax, [rax]
0x18003dd01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd06  lock xadd [rsi+0Ch], ebx
0x18003dd0b  cmp     ebx, 1
0x18003dd0e  jnz     short loc_18003DD1F
0x18003dd10  mov     rax, [rsi]
0x18003dd13  mov     rcx, rsi
0x18003dd16  mov     rax, [rax+8]
0x18003dd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd1f  lea     rdx, [rbp+120h+var_160]
0x18003dd23  lea     rcx, [rdi+20h]
0x18003dd27  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x18003dd2c  movups  xmm0, [rbp+120h+var_148]
0x18003dd30  movups  xmmword ptr [rdi+38h], xmm0
0x18003dd34  lea     rcx, [rdi+48h]
0x18003dd38  lea     rdx, [rbp+120h+var_138]
0x18003dd3c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003dd41  lea     rcx, [rdi+68h]
0x18003dd45  lea     rdx, [rbp+120h+var_118]
0x18003dd49  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003dd4e  lea     rcx, [rdi+88h]
0x18003dd55  lea     rdx, [rbp+120h+var_F8]
0x18003dd59  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003dd5e  lea     rcx, [rdi+0A8h]
0x18003dd65  lea     rdx, [rbp+120h+var_D8]
0x18003dd69  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003dd6e  lea     rcx, [rdi+0C8h]
0x18003dd75  lea     rdx, [rbp+120h+var_B8]
0x18003dd79  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003dd7e  mov     rbx, [rsp+220h+var_1E0]
0x18003dd83  mov     eax, [rbx+28h]
0x18003dd86  mov     [rdi+18h], eax
0x18003dd89  lea     r8, [rdi+172h]; struct NgcTransportContainerInfo *
0x18003dd90  mov     rdx, rbx; struct NgcTransport *
0x18003dd93  mov     rcx, [rdi+160h]; this
0x18003dd9a  call    ?ShouldAddBioProtector@NgcUtils@@YAJPEAVNgcTransport@@PEBUNgcTransportContainerInfo@@PEA_N@Z; NgcUtils::ShouldAddBioProtector(NgcTransport *,NgcTransportContainerInfo const *,bool *)
0x18003dd9f  lea     rsi, _TraceLoggingMetadataEnd
0x18003dda6  lea     r13, _TraceLoggingMetadata
0x18003ddad  test    eax, eax
0x18003ddaf  jns     loc_18003DE70
0x18003ddb5  mov     ecx, cs:dword_180122070
0x18003ddbb  cmp     ecx, 3
0x18003ddbe  jbe     loc_18003DE70
0x18003ddc4  mov     [rsp+220h+var_1EC], eax
0x18003ddc8  lea     rax, [rsp+220h+var_1EC]
0x18003ddcd  mov     [rbp+120h+var_70], rax
0x18003ddd4  mov     [rbp+120h+var_68], 4
0x18003dddf  mov     dword ptr [rbp+120h+EventDescriptor.Id], 0B000000h
0x18003dde6  movzx   eax, cs:word_1801020E8
0x18003dded  mov     dword ptr [rbp+120h+EventDescriptor.Level], eax
0x18003ddf0  mov     [rbp+120h+EventDescriptor.Keyword], r12
0x18003ddf4  mov     rax, cs:off_180122078
0x18003ddfb  mov     [rbp+120h+var_90.Ptr], rax
0x18003de02  movzx   eax, word ptr [rax]
0x18003de05  mov     [rbp+120h+var_90.Size], eax
0x18003de0b  mov     dword ptr [rbp+120h+var_90.0Ch], 2
0x18003de15  lea     rax, word_1801020F2
0x18003de1c  mov     [rbp+120h+var_80], rax
0x18003de23  mov     [rbp+120h+var_78], 29h ; ')'
0x18003de2d  mov     [rbp+120h+var_74], 1
0x18003de37  mov     rax, rsi
0x18003de3a  sub     eax, r13d
0x18003de3d  mov     [rsp+220h+var_1F0], eax
0x18003de41  mov     eax, [rsp+220h+var_1F0]
0x18003de45  lea     rax, [rbp+120h+var_90]
0x18003de4c  mov     [rsp+220h+UserData], rax; UserData
0x18003de51  mov     [rsp+220h+UserDataCount], 3; UserDataCount
0x18003de59  xor     r9d, r9d; RelatedActivityId
0x18003de5c  xor     r8d, r8d; ActivityId
0x18003de5f  lea     rdx, [rbp+120h+EventDescriptor]; EventDescriptor
0x18003de63  mov     rcx, cs:RegHandle; RegHandle
0x18003de6a  call    cs:__imp_EventWriteTransfer
0x18003de70  mov     rax, [rsp+220h+var_1E8]
0x18003de75  mov     ecx, [rax+60h]
0x18003de78  mov     [rdi+0E8h], ecx
0x18003de7e  mov     ecx, [rax+64h]
0x18003de81  mov     [rdi+204h], ecx
0x18003de87  mov     word ptr [rdi+128h], 101h
0x18003de90  mov     rcx, rdi; this
0x18003de93  call    ?IsFidoKey@NgcUserIdKey@NgcKspServer@@AEAA_NXZ; NgcKspServer::NgcUserIdKey::IsFidoKey(void)
0x18003de98  test    al, al
0x18003de9a  jz      short loc_18003DEA3
0x18003de9c  mov     byte ptr [rdi+248h], 0
0x18003dea3  test    r14, r14
0x18003dea6  jz      short loc_18003DEB1
0x18003dea8  mov     rcx, r14; SRWLock
0x18003deab  call    cs:__imp_ReleaseSRWLockExclusive
0x18003deb1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18003deb8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18003debd  mov     rcx, [rdi+160h]
0x18003dec4  lea     r10, [rdi+68h]
0x18003dec8  lea     r9, [rdi+48h]
0x18003decc  lea     r8, [rdi+88h]
0x18003ded3  lea     rdx, [rdi+38h]
0x18003ded7  mov     qword ptr [rsp+220h+UserDataCount], r10; int
0x18003dedc  test    al, al
0x18003dede  mov     rax, [rcx]
0x18003dee1  mov     rax, [rax+0A8h]
0x18003dee8  jz      short loc_18003DF17
0x18003deea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003deef  mov     rcx, [rbp+128h]; this
0x18003def6  test    eax, eax
0x18003def8  jns     loc_18003DFDF
0x18003defe  mov     r9d, eax; char *
0x18003df01  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18003df08  mov     edx, 1721h; void *
0x18003df0d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003df12  jmp     loc_18003DFDF
0x18003df17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df1c  test    eax, eax
0x18003df1e  jns     loc_18003DFDF
0x18003df24  mov     ecx, cs:dword_180122070
0x18003df2a  cmp     ecx, 2
0x18003df2d  jbe     loc_18003DFDF
0x18003df33  mov     [rsp+220h+var_1F0], eax
0x18003df37  lea     rax, [rsp+220h+var_1F0]
0x18003df3c  mov     [rbp+120h+var_70], rax
0x18003df43  mov     [rbp+120h+var_68], 4
0x18003df4e  mov     dword ptr [rbp+120h+EventDescriptor.Id], 0B000000h
0x18003df55  movzx   eax, cs:word_1801020BB
0x18003df5c  mov     dword ptr [rbp+120h+EventDescriptor.Level], eax
0x18003df5f  mov     [rbp+120h+EventDescriptor.Keyword], r12
0x18003df63  mov     rax, cs:off_180122078
0x18003df6a  mov     [rbp+120h+var_90.Ptr], rax
0x18003df71  movzx   eax, word ptr [rax]
0x18003df74  mov     [rbp+120h+var_90.Size], eax
0x18003df7a  mov     dword ptr [rbp+120h+var_90.0Ch], 2
0x18003df84  lea     rax, byte_1801020C5
0x18003df8b  mov     [rbp+120h+var_80], rax
0x18003df92  mov     [rbp+120h+var_78], 21h ; '!'
0x18003df9c  mov     [rbp+120h+var_74], 1
0x18003dfa6  mov     rax, rsi
0x18003dfa9  sub     eax, r13d
0x18003dfac  mov     [rsp+220h+var_1EC], eax
0x18003dfb0  mov     eax, [rsp+220h+var_1EC]
0x18003dfb4  lea     rax, [rbp+120h+var_90]
0x18003dfbb  mov     [rsp+220h+UserData], rax; UserData
0x18003dfc0  mov     [rsp+220h+UserDataCount], 3; UserDataCount
0x18003dfc8  xor     r9d, r9d; RelatedActivityId
0x18003dfcb  xor     r8d, r8d; ActivityId
0x18003dfce  lea     rdx, [rbp+120h+EventDescriptor]; EventDescriptor
0x18003dfd2  mov     rcx, cs:RegHandle; RegHandle
0x18003dfd9  call    cs:__imp_EventWriteTransfer
0x18003dfdf  mov     eax, cs:dword_180122070
0x18003dfe5  cmp     eax, 4
0x18003dfe8  jbe     loc_18003E07C
0x18003dfee  mov     dword ptr [rbp+120h+EventDescriptor.Id], 0B000000h
0x18003dff5  movzx   eax, cs:word_180102099
0x18003dffc  mov     dword ptr [rbp+120h+EventDescriptor.Level], eax
0x18003dfff  mov     [rbp+120h+EventDescriptor.Keyword], r12
0x18003e003  mov     rax, cs:off_180122078
0x18003e00a  mov     [rbp+120h+var_60.Ptr], rax
0x18003e011  movzx   eax, word ptr [rax]
0x18003e014  mov     [rbp+120h+var_60.Size], eax
0x18003e01a  mov     dword ptr [rbp+120h+var_60.0Ch], 2
0x18003e024  lea     rax, byte_1801020A3
0x18003e02b  mov     [rbp+120h+var_50], rax
0x18003e032  mov     [rbp+120h+var_48], 16h
0x18003e03c  mov     [rbp+120h+var_44], 1
0x18003e046  sub     esi, r13d
0x18003e049  mov     [rsp+220h+var_1F0], esi
0x18003e04d  mov     eax, [rsp+220h+var_1F0]
  ... truncated ...
```
