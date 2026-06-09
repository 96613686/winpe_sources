# CGatheringService::GetFilterPool(CTransaction const *,CFilterPool * *)

- ea: `0x1800195b8`
- end: `0x180019baa`
- name: `?GetFilterPool@CGatheringService@@QEAAJPEBVCTransaction@@PEAPEAVCFilterPool@@@Z`
- size: `1522`
- prototype: `int(CGatheringService *__hidden this, const struct CTransaction *, struct CFilterPool **)`
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004b0b8`

## callees

- `0x18000a23c`
- `0x18000e628`
- `0x180018e0c`
- `0x1800195b8`
- `0x180019bb0`
- `0x180022710`
- `0x180026b58`
- `0x180027164`
- `0x18002751c`
- `0x180029db0`
- `0x180030704`
- `0x18004936c`
- `0x180049b5c`
- `0x18004b638`
- `0x180052460`
- `0x180052c14`
- `0x180056610`
- `0x18005e788`
- `0x180061f78`
- `0x1800692f4`
- `0x18008da30`
- `0x18008fde0`
- `0x1800bae10`
- `0x1800c2700`
- `0x1800cccec`
- `0x1800ccd20`
- `0x1800ccda4`
- `0x1800cf9a4`
- `0x1800f873c`
- `0x18010ff58`
- `0x1801244c0`
- `0x18017bb74`
- `0x18017d0e0`
- `0x18017f624`
- `0x18019e700`
- `0x18019e76c`
- `0x180241010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180019a9e`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180019a9e`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180019a6a`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180019acf`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180019a6a`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180019acf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019760`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019760`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800197d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800197d4`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800198b6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800198b6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800197a4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800197a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CGatheringService::GetFilterPool(
        CGatheringService *this,
        const struct CTransaction *a2,
        struct CFilterPool **a3)
{
  int v5; // r13d
  int v6; // r12d
  const WCHAR *ContainerUserSid; // rax
  const wchar_t *AppUserModelId; // rax
  __int64 v9; // rsi
  unsigned int v10; // edi
  _QWORD *v11; // rsi
  _QWORD *v12; // rdi
  LPCWSTR v14; // rsi
  void **v15; // rax
  int SessionUserForSid; // edi
  const wchar_t *v17; // r8
  CFilterPool *v18; // rsi
  void **phNewToken; // rax
  BOOL v20; // eax
  unsigned int v21; // edx
  int v22; // eax
  int v23; // eax
  LPCWSTR v24; // rdx
  const wchar_t *v25; // rax
  wchar_t *Buffer; // rax
  wchar_t *v27; // rax
  wchar_t *v28; // rax
  LPCWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  CFilterPool *v30; // [rsp+48h] [rbp-B8h] BYREF
  PSID Sid; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hExistingToken; // [rsp+58h] [rbp-A8h] BYREF
  struct CFilterPool **v33; // [rsp+60h] [rbp-A0h]
  _DWORD v34[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h]
  char *v36; // [rsp+78h] [rbp-88h]
  void **v37; // [rsp+80h] [rbp-80h] BYREF
  __int16 *v38; // [rsp+88h] [rbp-78h]
  __int64 v39; // [rsp+90h] [rbp-70h]
  __int16 v40; // [rsp+98h] [rbp-68h] BYREF
  void **v41; // [rsp+D0h] [rbp-30h] BYREF
  __int16 *v42; // [rsp+D8h] [rbp-28h]
  __int64 v43; // [rsp+E0h] [rbp-20h]
  __int16 v44; // [rsp+E8h] [rbp-18h] BYREF
  void **v45; // [rsp+120h] [rbp+20h] BYREF
  __int16 *v46; // [rsp+128h] [rbp+28h]
  __int64 v47; // [rsp+130h] [rbp+30h]
  __int16 v48; // [rsp+138h] [rbp+38h] BYREF
  void **v49; // [rsp+170h] [rbp+70h] BYREF
  void *Block; // [rsp+178h] [rbp+78h]
  int v51; // [rsp+180h] [rbp+80h]
  unsigned int v52; // [rsp+184h] [rbp+84h]
  _BYTE v53[520]; // [rsp+188h] [rbp+88h] BYREF
  void **v54; // [rsp+390h] [rbp+290h] BYREF
  wchar_t *v55; // [rsp+398h] [rbp+298h]
  __int64 v56; // [rsp+3A0h] [rbp+2A0h]
  __int16 v57; // [rsp+3A8h] [rbp+2A8h] BYREF

  v33 = a3;
  *a3 = 0;
  v5 = *((_DWORD *)a2 + 420) & 0x10;
  v6 = *((_DWORD *)a2 + 420) & 0x80;
  if ( v6 )
    ContainerUserSid = CTransaction::GetContainerUserSid(a2);
  else
    ContainerUserSid = (const WCHAR *)*((_QWORD *)a2 + 131);
  StringSid = ContainerUserSid;
  v49 = &CLMString::`vftable';
  Block = v53;
  v51 = 257;
  CLMString::AssignInConstructor((CLMString *)&v49, ContainerUserSid, 0xFFFFFFFF);
  v49 = &TLMString<256,512,1048576>::`vftable';
  if ( v6 )
  {
    CLMString::Assign((CLMString *)&v49, "_container", v52, 0xFFFFFFFF);
  }
  else if ( v5 )
  {
    CLMString::Assign((CLMString *)&v49, "_", v52, 0xFFFFFFFF);
    AppUserModelId = CTransaction::GetAppUserModelId(a2);
    CLMString::Append((CLMString *)&v49, AppUserModelId, 0xFFFFFFFF);
  }
  v36 = (char *)this + 4328;
  CSyncReadWrite::GetWriteAccess((CGatheringService *)((char *)this + 4328));
  v9 = *((_QWORD *)this + 497);
  v10 = *((_DWORD *)this + 988);
  v11 = (_QWORD *)(32LL * ((*((unsigned int (__fastcall **)(void ***))this + 492))(&v49) % v10) + v9);
  if ( v11 )
  {
    v12 = v11;
    while ( 1 )
    {
      v12 = (_QWORD *)*v12;
      if ( v12 == v11 + 1 || !v12 )
        break;
      if ( !(unsigned int)stringCmpI(*(PCNZWCH *)(v12[2] + 8LL), (PCNZWCH)Block) )
      {
        if ( (unsigned int)CTComObjKPtrSingleLink<TLMString<16,32,256>,CExt,CLMSubStr>::GetValue(v12, v33) )
          break;
        CSyncReadWrite::ReleaseWriteAccess((CGatheringService *)((char *)this + 4328));
        v49 = &TLMString<256,512,1048576>::`vftable';
        if ( Block )
        {
          if ( Block != v53 )
          {
            free(Block);
            wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl);
          }
        }
        return 0;
      }
    }
  }
  v34[0] = -1;
  v34[1] = 0;
  v35 = 0;
  Sid = 0;
  hExistingToken = 0;
  v14 = StringSid;
  if ( ConvertStringSidToSidW(StringSid, &Sid) )
  {
    v15 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&hExistingToken);
    SessionUserForSid = CGatheringService::GetSessionUserForSid(this, Sid, (struct SessionUser *)v34, v15);
    LocalFree(Sid);
  }
  else
  {
    SessionUserForSid = ResultFromLastError();
  }
  if ( SessionUserForSid >= 0 )
  {
    v30 = 0;
    StringSid = 0;
    SessionUserForSid = ATL::CComObject<CFilterPool>::CreateInstance(&StringSid);
    if ( SessionUserForSid < 0 )
      goto LABEL_36;
    TComNoUnkPointer<CPlugin>::operator=(&v30, StringSid);
    if ( v6 )
    {
      v17 = v14;
      v18 = v30;
      SessionUserForSid = CFilterPool::Init(
                            v30,
                            (const wchar_t *)Block,
                            v17,
                            *((unsigned int *)a2 + 438),
                            *((const wchar_t **)a2 + 131));
    }
    else
    {
      v55 = (wchar_t *)&v57;
      v56 = 257;
      v57 = 0;
      v54 = &TLMString<256,512,1048576>::`vftable';
      StringSid = 0;
      phNewToken = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&StringSid);
      v20 = DuplicateTokenEx(hExistingToken, 0xBu, 0, SecurityImpersonation, TokenPrimary, phNewToken);
      v18 = v30;
      if ( v20 || (SessionUserForSid = ResultFromKnownLastError(), SessionUserForSid >= 0) )
      {
        CLMString::operator=(&v54, L"MssGthrPipe");
        ((void (__fastcall *)(void ***, const char *, _QWORD, __int64))v54[3])(&v54, "_", HIDWORD(v56), 0xFFFFFFFFLL);
        CLMString::operator+=(&v54, &v49);
        CFilterPool::SetThreadsPerFilterDaemon(v18, *((_DWORD *)this + 972));
        if ( !*((_BYTE *)v18 + 1448) )
        {
          v22 = *((_DWORD *)this + 319);
          *((_DWORD *)v18 + 171) = v22;
          *((_DWORD *)v18 + 173) = v22;
          v23 = *((_DWORD *)this + 320);
          *((_DWORD *)v18 + 172) = v23;
          *((_DWORD *)v18 + 174) = v23;
          CFilterPoolBase::SetMaxProcesses((CFilterPool *)((char *)v18 + 24), v21);
        }
        v24 = StringSid;
        StringSid = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          (char *)v18 + 704,
          v24);
        CLMString::operator=((char *)v18 + 712, *((_QWORD *)a2 + 131));
        CLMString::operator=((char *)v18 + 904, Block);
        if ( v5 )
        {
          v25 = CTransaction::GetAppUserModelId(a2);
          std::wstring::assign((char *)v18 + 872, v25);
        }
        SessionUserForSid = CFilterPoolBase::Init((CFilterPool *)((char *)v18 + 24), v55);
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&StringSid);
      TLMString<256,512,1048576>::~TLMString<256,512,1048576>(&v54);
    }
    if ( SessionUserForSid < 0
      || (SessionUserForSid = CTComObjHMap<TLMString<256,512,1048576>,CFilterPool,CLMSubStr>::Insert(
                                (char *)this + 3928,
                                (char *)v18 + 904,
                                v18),
          SessionUserForSid < 0) )
    {
LABEL_36:
      if ( SessionUserForSid != -2147023651 )
      {
        SessionUserForSid = -2147217990;
        v46 = &v48;
        v47 = 23;
        v48 = 0;
        v45 = &TLMString<22,0,22>::`vftable';
        Buffer = CLMString::GetBuffer((CLMString *)&v45, 0);
        _o__ultow_s(v34[0], Buffer, 23);
        v42 = &v44;
        v43 = 23;
        v44 = 0;
        v41 = &TLMString<22,0,22>::`vftable';
        v27 = CLMString::GetBuffer((CLMString *)&v41, 0);
        _o__ui64tow_s(v35, v27, 23, 10);
        v38 = &v40;
        v39 = 23;
        v40 = 0;
        v37 = &TLMString<22,0,22>::`vftable';
        v28 = CLMString::GetBuffer((CLMString *)&v37, 0);
        _o__ultow_s(0, v28, 23);
        CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)&v54, *((struct CEventLog **)this + 49));
        CSearchEventEntry::SetError((CSearchEventEntry *)&v54, -2147217990);
        CSearchEventEntry::ReportError((CSearchEventEntry *)&v54, 0xC0000C21, v46, v42, v38, L"0", 0);
        CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)&v54);
        TLMString<22,0,22>::~TLMString<22,0,22>(&v37);
        TLMString<22,0,22>::~TLMString<22,0,22>(&v41);
        TLMString<22,0,22>::~TLMString<22,0,22>(&v45);
      }
    }
    else
    {
      v30 = 0;
      *v33 = v18;
    }
    TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v30);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
  CSyncReadWrite::ReleaseWriteAccess((CGatheringService *)((char *)this + 4328));
  TLMString<256,512,1048576>::~TLMString<256,512,1048576>(&v49);
  return (unsigned int)SessionUserForSid;
}

```

## disassembly

```asm
0x1800195b8  mov     [rsp-8+arg_18], rbx
0x1800195bd  push    rbp
0x1800195be  push    rsi
0x1800195bf  push    rdi
0x1800195c0  push    r12
0x1800195c2  push    r13
0x1800195c4  push    r14
0x1800195c6  push    r15
0x1800195c8  lea     rbp, [rsp-0C10h]
0x1800195d0  sub     rsp, 0D10h
0x1800195d7  mov     rax, cs:__security_cookie
0x1800195de  xor     rax, rsp
0x1800195e1  mov     [rbp+0C40h+var_40], rax
0x1800195e8  mov     [rsp+0D40h+var_CE0], r8
0x1800195ed  mov     r14, rdx
0x1800195f0  mov     r15, rcx
0x1800195f3  mov     qword ptr [r8], 0
0x1800195fa  mov     r13d, [rdx+690h]
0x180019601  mov     r12d, r13d
0x180019604  and     r13d, 10h
0x180019608  and     r12d, 80h
0x18001960f  jz      short loc_18001961B
0x180019611  mov     rcx, rdx; this
0x180019614  call    ?GetContainerUserSid@CTransaction@@QEBAPEB_WXZ; CTransaction::GetContainerUserSid(void)
0x180019619  jmp     short loc_180019622
0x18001961b  mov     rax, [rdx+418h]
0x180019622  mov     [rsp+0D40h+StringSid], rax
0x180019627  lea     rcx, ??_7CLMString@@6B@; const CLMString::`vftable'
0x18001962e  mov     [rbp+0C40h+var_BD0], rcx
0x180019632  lea     rcx, [rbp+0C40h+var_BB8]
0x180019639  mov     [rbp+0C40h+Block], rcx
0x18001963d  mov     [rbp+0C40h+var_BC0], 101h
0x180019647  or      ebx, 0FFFFFFFFh
0x18001964a  mov     r8d, ebx; unsigned int
0x18001964d  mov     rdx, rax; wchar_t *
0x180019650  lea     rcx, [rbp+0C40h+var_BD0]; this
0x180019654  call    ?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z; CLMString::AssignInConstructor(wchar_t const *,uint)
0x180019659  lea     rax, ??_7?$TLMString@$0BAA@$0CAA@$0BAAAAA@@@6B@; const TLMString<256,512,1048576>::`vftable'
0x180019660  mov     [rbp+0C40h+var_BD0], rax
0x180019664  test    r12d, r12d
0x180019667  jz      short loc_180019685
0x180019669  mov     r9d, ebx; unsigned int
0x18001966c  mov     r8d, [rbp+0C40h+var_BBC]; unsigned int
0x180019673  lea     rdx, aContainer_0; "_container"
0x18001967a  lea     rcx, [rbp+0C40h+var_BD0]; this
0x18001967e  call    ?Assign@CLMString@@UEAAHPEBDII@Z; CLMString::Assign(char const *,uint,uint)
0x180019683  jmp     short loc_1800196BB
0x180019685  test    r13d, r13d
0x180019688  jz      short loc_1800196BB
0x18001968a  mov     r9d, ebx; unsigned int
0x18001968d  mov     r8d, [rbp+0C40h+var_BBC]; unsigned int
0x180019694  lea     rdx, asc_18027B318; "_"
0x18001969b  lea     rcx, [rbp+0C40h+var_BD0]; this
0x18001969f  call    ?Assign@CLMString@@UEAAHPEBDII@Z; CLMString::Assign(char const *,uint,uint)
0x1800196a4  mov     rcx, r14; this
0x1800196a7  call    ?GetAppUserModelId@CTransaction@@QEBAPEB_WXZ; CTransaction::GetAppUserModelId(void)
0x1800196ac  mov     r8d, ebx; unsigned int
0x1800196af  mov     rdx, rax; wchar_t *
0x1800196b2  lea     rcx, [rbp+0C40h+var_BD0]; this
0x1800196b6  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800196bb  lea     rbx, [r15+10E8h]
0x1800196c2  mov     [rsp+0D40h+var_CC8], rbx
0x1800196c7  mov     rcx, rbx; this
0x1800196ca  call    ?GetWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::GetWriteAccess(void)
0x1800196cf  nop
0x1800196d0  mov     rsi, [r15+0F88h]
0x1800196d7  mov     edi, [r15+0F70h]
0x1800196de  lea     rcx, [rbp+0C40h+var_BD0]
0x1800196e2  mov     rax, [r15+0F60h]
0x1800196e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196ee  xor     edx, edx
0x1800196f0  div     edi
0x1800196f2  mov     ecx, edx
0x1800196f4  shl     rcx, 5
0x1800196f8  add     rsi, rcx
0x1800196fb  jz      short loc_18001977A
0x1800196fd  mov     rdi, rsi
0x180019700  mov     rdi, [rdi]
0x180019703  lea     rax, [rsi+8]
0x180019707  cmp     rdi, rax
0x18001970a  jz      short loc_18001977A
0x18001970c  test    rdi, rdi
0x18001970f  jz      short loc_18001977A
0x180019711  mov     rcx, [rdi+10h]
0x180019715  mov     rdx, [rbp+0C40h+Block]; lpString2
0x180019719  mov     rcx, [rcx+8]; lpString1
0x18001971d  call    ?stringCmpI@@YAHPEB_W0@Z; stringCmpI(wchar_t const *,wchar_t const *)
0x180019722  test    eax, eax
0x180019724  jnz     short loc_180019700
0x180019726  mov     rdx, [rsp+0D40h+var_CE0]
0x18001972b  mov     rcx, rdi
0x18001972e  call    ?GetValue@?$CTComObjKPtrSingleLink@V?$TLMString@$0BA@$0CA@$0BAA@@@VCExt@@VCLMSubStr@@@@QEAAJPEAPEAVCExt@@@Z; CTComObjKPtrSingleLink<TLMString<16,32,256>,CExt,CLMSubStr>::GetValue(CExt * *)
0x180019733  test    eax, eax
0x180019735  jnz     short loc_18001977A
0x180019737  mov     rcx, rbx; this
0x18001973a  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x18001973f  nop
0x180019740  lea     rax, ??_7?$TLMString@$0BAA@$0CAA@$0BAAAAA@@@6B@; const TLMString<256,512,1048576>::`vftable'
0x180019747  mov     [rbp+0C40h+var_BD0], rax
0x18001974b  mov     rcx, [rbp+0C40h+Block]; Block
0x18001974f  test    rcx, rcx
0x180019752  jz      short loc_180019773
0x180019754  lea     rax, [rbp+0C40h+var_BB8]
0x18001975b  cmp     rcx, rax
0x18001975e  jz      short loc_180019773
0x180019760  call    cs:__imp_free
0x180019766  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56494824@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824> `wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl(void)'::`2'::impl
0x18001976d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(void)
0x180019772  nop
0x180019773  xor     eax, eax
0x180019775  jmp     loc_180019B80
0x18001977a  mov     [rsp+0D40h+var_CD8], 0FFFFFFFFh
0x180019782  xor     eax, eax
0x180019784  mov     [rsp+0D40h+var_CD4], eax
0x180019788  mov     [rsp+0D40h+var_CD0], rax
0x18001978d  mov     [rsp+0D40h+Sid], rax
0x180019792  mov     [rsp+0D40h+hExistingToken], rax
0x180019797  lea     rdx, [rsp+0D40h+Sid]; Sid
0x18001979c  mov     rsi, [rsp+0D40h+StringSid]
0x1800197a1  mov     rcx, rsi; StringSid
0x1800197a4  call    cs:__imp_ConvertStringSidToSidW
0x1800197aa  test    eax, eax
0x1800197ac  jz      short loc_1800197DC
0x1800197ae  lea     rcx, [rsp+0D40h+hExistingToken]
0x1800197b3  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1800197b8  mov     r9, rax; void **
0x1800197bb  lea     r8, [rsp+0D40h+var_CD8]; struct SessionUser *
0x1800197c0  mov     rdx, [rsp+0D40h+Sid]; void *
0x1800197c5  mov     rcx, r15; this
0x1800197c8  call    ?GetSessionUserForSid@CGatheringService@@AEAAJQEAXPEAUSessionUser@@PEAPEAX@Z; CGatheringService::GetSessionUserForSid(void * const,SessionUser *,void * *)
0x1800197cd  mov     edi, eax
0x1800197cf  mov     rcx, [rsp+0D40h+Sid]; hMem
0x1800197d4  call    cs:__imp_LocalFree
0x1800197da  jmp     short loc_1800197E3
0x1800197dc  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800197e1  mov     edi, eax
0x1800197e3  test    edi, edi
0x1800197e5  js      loc_180019B61
0x1800197eb  mov     [rsp+0D40h+var_CF8], 0
0x1800197f4  mov     [rsp+0D40h+StringSid], 0
0x1800197fd  lea     rcx, [rsp+0D40h+StringSid]
0x180019802  call    ?CreateInstance@?$CComObject@VCFilterPool@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFilterPool>::CreateInstance(ATL::CComObject<CFilterPool> * *)
0x180019807  mov     edi, eax
0x180019809  test    eax, eax
0x18001980b  js      loc_180019A17
0x180019811  mov     rdx, [rsp+0D40h+StringSid]
0x180019816  lea     rcx, [rsp+0D40h+var_CF8]
0x18001981b  call    ??4?$TComNoUnkPointer@VCPlugin@@@@QEAAPEAVCPlugin@@PEAV1@@Z; TComNoUnkPointer<CPlugin>::operator=(CPlugin *)
0x180019820  test    r12d, r12d
0x180019823  jz      short loc_180019856
0x180019825  mov     r9d, [r14+6D8h]; unsigned __int64
0x18001982c  mov     rax, [r14+418h]
0x180019833  mov     qword ptr [rsp+0D40h+TokenType], rax; wchar_t *
0x180019838  mov     r8, rsi; wchar_t *
0x18001983b  mov     rdx, [rbp+0C40h+Block]; wchar_t *
0x18001983f  mov     rsi, [rsp+0D40h+var_CF8]
0x180019844  mov     rcx, rsi; this
0x180019847  call    ?Init@CFilterPool@@QEAAJPEB_W0_K0@Z; CFilterPool::Init(wchar_t const *,wchar_t const *,unsigned __int64,wchar_t const *)
0x18001984c  mov     edi, eax
0x18001984e  xor     r12d, r12d
0x180019851  jmp     loc_1800199E5
0x180019856  lea     rax, [rbp+0C40h+var_998]
0x18001985d  mov     [rbp+0C40h+var_9A8], rax
0x180019864  mov     [rbp+0C40h+var_9A0], 101h
0x18001986f  xor     r12d, r12d
0x180019872  mov     [rbp+0C40h+var_998], r12w
0x18001987a  lea     rax, ??_7?$TLMString@$0BAA@$0CAA@$0BAAAAA@@@6B@; const TLMString<256,512,1048576>::`vftable'
0x180019881  mov     [rbp+0C40h+var_9B0], rax
0x180019888  mov     [rsp+0D40h+StringSid], r12
0x18001988d  lea     rcx, [rsp+0D40h+StringSid]
0x180019892  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x180019897  mov     [rsp+0D40h+phNewToken], rax; phNewToken
0x18001989c  mov     [rsp+0D40h+TokenType], 1; TokenType
0x1800198a4  lea     r9d, [r12+2]; ImpersonationLevel
0x1800198a9  xor     r8d, r8d; lpTokenAttributes
0x1800198ac  lea     edx, [r12+0Bh]; dwDesiredAccess
0x1800198b1  mov     rcx, [rsp+0D40h+hExistingToken]; hExistingToken
0x1800198b6  call    cs:__imp_DuplicateTokenEx
0x1800198bc  mov     rsi, [rsp+0D40h+var_CF8]
0x1800198c1  test    eax, eax
0x1800198c3  jnz     short loc_1800198D4
0x1800198c5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800198ca  mov     edi, eax
0x1800198cc  test    eax, eax
0x1800198ce  js      loc_1800199CE
0x1800198d4  lea     rdx, aMssgthrpipe; "MssGthrPipe"
0x1800198db  lea     rcx, [rbp+0C40h+var_9B0]
0x1800198e2  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800198e7  mov     rax, [rbp+0C40h+var_9B0]
0x1800198ee  or      r9d, 0FFFFFFFFh
0x1800198f2  mov     r8d, dword ptr [rbp+0C40h+var_9A0+4]
0x1800198f9  lea     rdx, asc_18027B318; "_"
0x180019900  lea     rcx, [rbp+0C40h+var_9B0]
0x180019907  mov     rax, [rax+18h]
0x18001990b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019910  lea     rdx, [rbp+0C40h+var_BD0]
0x180019914  lea     rcx, [rbp+0C40h+var_9B0]
0x18001991b  call    ??YCLMString@@QEAAXAEBV0@@Z; CLMString::operator+=(CLMString const &)
0x180019920  mov     edx, [r15+0F30h]; unsigned int
0x180019927  mov     rcx, rsi; this
0x18001992a  call    ?SetThreadsPerFilterDaemon@CFilterPool@@QEAAXK@Z; CFilterPool::SetThreadsPerFilterDaemon(ulong)
0x18001992f  cmp     [rsi+5A8h], r12b
0x180019936  jnz     short loc_180019967
0x180019938  mov     eax, [r15+4FCh]
0x18001993f  mov     [rsi+2ACh], eax
0x180019945  mov     [rsi+2B4h], eax
0x18001994b  mov     eax, [r15+500h]
0x180019952  mov     [rsi+2B0h], eax
0x180019958  mov     [rsi+2B8h], eax
0x18001995e  lea     rcx, [rsi+18h]; this
0x180019962  call    ?SetMaxProcesses@CFilterPoolBase@@QEAAXK@Z; CFilterPoolBase::SetMaxProcesses(ulong)
0x180019967  mov     rdx, [rsp+0D40h+StringSid]
0x18001996c  mov     [rsp+0D40h+StringSid], r12
0x180019971  lea     rcx, [rsi+2C0h]
0x180019978  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001997d  lea     rcx, [rsi+2C8h]
0x180019984  mov     rdx, [r14+418h]
0x18001998b  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180019990  lea     rcx, [rsi+388h]
0x180019997  mov     rdx, [rbp+0C40h+Block]
0x18001999b  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800199a0  test    r13d, r13d
0x1800199a3  jz      short loc_1800199BC
0x1800199a5  mov     rcx, r14; this
0x1800199a8  call    ?GetAppUserModelId@CTransaction@@QEBAPEB_WXZ; CTransaction::GetAppUserModelId(void)
0x1800199ad  lea     rcx, [rsi+368h]
0x1800199b4  mov     rdx, rax
0x1800199b7  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800199bc  mov     rdx, [rbp+0C40h+var_9A8]; wchar_t *
0x1800199c3  lea     rcx, [rsi+18h]; this
0x1800199c7  call    ?Init@CFilterPoolBase@@QEAAJPEB_W@Z; CFilterPoolBase::Init(wchar_t const *)
0x1800199cc  mov     edi, eax
0x1800199ce  lea     rcx, [rsp+0D40h+StringSid]
0x1800199d3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800199d8  nop
0x1800199d9  lea     rcx, [rbp+0C40h+var_9B0]
0x1800199e0  call    ??1?$TLMString@$0BAA@$0CAA@$0BAAAAA@@@UEAA@XZ; TLMString<256,512,1048576>::~TLMString<256,512,1048576>(void)
0x1800199e5  test    edi, edi
0x1800199e7  js      short loc_180019A17
0x1800199e9  lea     rdx, [rsi+388h]
0x1800199f0  lea     rcx, [r15+0F58h]
0x1800199f7  mov     r8, rsi
0x1800199fa  call    ?Insert@?$CTComObjHMap@V?$TLMString@$0BAA@$0CAA@$0BAAAAA@@@VCFilterPool@@VCLMSubStr@@@@QEAAJPEBV?$TLMString@$0BAA@$0CAA@$0BAAAAA@@@PEAVCFilterPool@@@Z; CTComObjHMap<TLMString<256,512,1048576>,CFilterPool,CLMSubStr>::Insert(TLMString<256,512,1048576> const *,CFilterPool *)
0x1800199ff  mov     edi, eax
0x180019a01  test    eax, eax
0x180019a03  js      short loc_180019A17
0x180019a05  mov     [rsp+0D40h+var_CF8], r12
0x180019a0a  mov     rax, [rsp+0D40h+var_CE0]
0x180019a0f  mov     [rax], rsi
0x180019a12  jmp     loc_180019B56
0x180019a17  cmp     edi, 800704DDh
0x180019a1d  jz      loc_180019B56
0x180019a23  mov     edi, 80040DBAh
0x180019a28  lea     rax, [rbp+0C40h+var_C08]
0x180019a2c  mov     [rbp+0C40h+var_C18], rax
0x180019a30  mov     r12d, 17h
0x180019a36  mov     [rbp+0C40h+var_C10], r12
0x180019a3a  xor     r13d, r13d
0x180019a3d  mov     [rbp+0C40h+var_C08], r13w
0x180019a42  lea     r14, ??_7?$TLMString@$0BG@$0A@$0BG@@@6B@; const TLMString<22,0,22>::`vftable'
0x180019a49  mov     [rbp+0C40h+var_C20], r14
0x180019a4d  xor     edx, edx; int
0x180019a4f  lea     rcx, [rbp+0C40h+var_C20]; this
0x180019a53  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180019a58  lea     esi, [r12-0Dh]
0x180019a5d  mov     r9d, esi
0x180019a60  mov     r8d, r12d
0x180019a63  mov     rdx, rax
0x180019a66  mov     ecx, [rsp+0D40h+var_CD8]
0x180019a6a  call    cs:__imp__o__ultow_s
0x180019a70  lea     rax, [rbp+0C40h+var_C58]
0x180019a74  mov     [rbp+0C40h+var_C68], rax
0x180019a78  mov     [rbp+0C40h+var_C60], r12
0x180019a7c  mov     [rbp+0C40h+var_C58], r13w
0x180019a81  mov     [rbp+0C40h+var_C70], r14
0x180019a85  xor     edx, edx; int
0x180019a87  lea     rcx, [rbp+0C40h+var_C70]; this
0x180019a8b  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180019a90  mov     r9d, esi
0x180019a93  mov     r8d, r12d
0x180019a96  mov     rdx, rax
0x180019a99  mov     rcx, [rsp+0D40h+var_CD0]
0x180019a9e  call    cs:__imp__o__ui64tow_s
0x180019aa4  lea     rax, [rbp+0C40h+var_CA8]
0x180019aa8  mov     [rbp+0C40h+var_CB8], rax
0x180019aac  mov     [rbp+0C40h+var_CB0], r12
0x180019ab0  mov     [rbp+0C40h+var_CA8], r13w
0x180019ab5  mov     [rbp+0C40h+var_CC0], r14
0x180019ab9  xor     edx, edx; int
0x180019abb  lea     rcx, [rbp+0C40h+var_CC0]; this
0x180019abf  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180019ac4  mov     r9d, esi
0x180019ac7  mov     r8d, r12d
0x180019aca  mov     rdx, rax
0x180019acd  xor     ecx, ecx
0x180019acf  call    cs:__imp__o__ultow_s
0x180019ad5  mov     rdx, [r15+188h]; struct CEventLog *
0x180019adc  lea     rcx, [rbp+0C40h+var_9B0]; this
0x180019ae3  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x180019ae8  nop
  ... truncated ...
```
