# SharingPlatform::SessionHost::CreateAndStartSessionStream(bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,SharingPlatform::CDPBinaryHostContainer *)

- ea: `0x18005c1f8`
- end: `0x18005c4be`
- name: `?CreateAndStartSessionStream@SessionHost@SharingPlatform@@AEAAJ_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDPBinaryHostContainer@2@@Z`
- size: `710`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800112e0`
- `0x18005bdd0`
- `0x18005c0d8`

## callees

- `0x180004928`
- `0x180006668`
- `0x18000a580`
- `0x180010d04`
- `0x1800130ec`
- `0x180018490`
- `0x180019bcc`
- `0x1800225a0`
- `0x18004a640`
- `0x1800571d8`
- `0x18005ac14`
- `0x18005ad50`
- `0x18005c1f8`
- `0x18006a010`

## import_xrefs

- `cdp!CDPCreateBinaryHostInternal` at `0x18005c364`
- `cdp!CDPCreateBinaryHostInternal` at `0x18005c364`

## string_xrefs

- `0x18005c269`: `SessionHost::CreateAndStartSessionStream isSystem=%d name=%ls setttings=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SharingPlatform::SessionHost::CreateAndStartSessionStream(
        __int64 a1,
        unsigned __int64 a2,
        _QWORD *a3,
        __int64 *a4)
{
  _QWORD *v5; // rdi
  unsigned int v6; // r15d
  unsigned int v8; // r12d
  _QWORD *v9; // rbx
  __int64 v10; // rcx
  RemoteSessionTraceProvider *v11; // rax
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  char *v17; // r8
  _QWORD *v18; // r8
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rbx
  __int64 v23; // rbx
  int v25; // [rsp+20h] [rbp-60h]
  int v26; // [rsp+20h] [rbp-60h]
  __int64 v27; // [rsp+30h] [rbp-50h] BYREF
  int v28[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v29; // [rsp+40h] [rbp-40h] BYREF
  __int64 v30; // [rsp+48h] [rbp-38h] BYREF
  __int64 v31; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v32[4]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v5 = a3;
  v6 = (unsigned __int8)a2;
  v8 = (*((_BYTE *)a4 + 16) != 0) | 0x30000000;
  if ( a3[3] <= 7u )
    v9 = a3;
  else
    v9 = (_QWORD *)*a3;
  if ( RemoteSessionTraceProvider::IsEnabled(a1, a2) )
  {
    v11 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                          v10,
                                          _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
    v25 = v8;
    RemoteSessionTraceProvider::LogVerbose_(
      v11,
      L"SessionHost::CreateAndStartSessionStream isSystem=%d name=%ls setttings=%d",
      v6,
      v9);
  }
  v30 = 0;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v30);
  v27 = a1;
  if ( (_BYTE)v6 )
  {
    v12 = Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPBinaryHostCallback,ICDPBinaryHostCallback,SharingPlatform::SessionHost *>(
            &v30,
            &v27);
    v13 = v12;
    if ( v12 < 0 )
    {
      v14 = 133;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)".\\sessionhost.cpp",
        (const char *)(unsigned int)v12,
        v25);
      goto LABEL_34;
    }
  }
  else
  {
    v12 = Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPBinaryHostChannelCallback,ICDPBinaryHostCallback,SharingPlatform::SessionHost *>(
            &v30,
            &v27);
    v13 = v12;
    if ( v12 < 0 )
    {
      v14 = 137;
      goto LABEL_11;
    }
  }
  *(_QWORD *)v28 = 0;
  v31 = 0;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v31);
  v15 = *(_QWORD *)&SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId;
  if ( *(_QWORD *)&SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId + 8LL))(*(_QWORD *)&SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId);
    v15 = *(_QWORD *)&SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId;
  }
  v31 = v15;
  if ( v5[3] <= 7u )
    v16 = v5;
  else
    v16 = (_QWORD *)*v5;
  v17 = (char *)v16 + 2 * v5[2];
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  std::string::string(v32, v5, v17);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v28);
  v18 = v32;
  if ( v32[3] > 0xFu )
    v18 = (_QWORD *)v32[0];
  v19 = CDPCreateBinaryHostInternal(v31, v30, v18, v8, v28);
  v13 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x94,
      (unsigned int)".\\sessionhost.cpp",
      (const char *)(unsigned int)v19,
      v26);
    std::string::~string(v32);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v31);
LABEL_23:
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v28);
    goto LABEL_34;
  }
  std::string::~string(v32);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v31);
  v29 = 0;
  v27 = a1;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v29);
  v20 = Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPHostAuthorizationProvider,ICDPHostAuthorizationProvider,SharingPlatform::SessionHost *>(
          &v29,
          &v27);
  v13 = v20;
  if ( v20 < 0 )
  {
    v21 = 153;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)".\\sessionhost.cpp",
      (const char *)(unsigned int)v20,
      v26);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v29);
    goto LABEL_23;
  }
  v20 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v28 + 56LL))(*(_QWORD *)v28, v29);
  v13 = v20;
  if ( v20 < 0 )
  {
    v21 = 154;
    goto LABEL_26;
  }
  v22 = *(_QWORD *)v28;
  if ( *a4 != *(_QWORD *)v28 )
  {
    v27 = *(_QWORD *)v28;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(&v27);
    v27 = *a4;
    *a4 = v22;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v27);
  }
  v23 = v30;
  if ( a4[1] != v30 )
  {
    v27 = v30;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(&v27);
    v27 = a4[1];
    a4[1] = v23;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v27);
  }
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v28);
  v13 = 0;
LABEL_34:
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v30);
  return v13;
}

```

## disassembly

```asm
0x18005c1f8  push    rbp
0x18005c1fa  push    rbx
0x18005c1fb  push    rsi
0x18005c1fc  push    rdi
0x18005c1fd  push    r12
0x18005c1ff  push    r14
0x18005c201  push    r15
0x18005c203  mov     rbp, rsp
0x18005c206  sub     rsp, 80h
0x18005c20d  mov     rax, cs:__security_cookie
0x18005c214  xor     rax, rsp
0x18005c217  mov     [rbp+var_8], rax
0x18005c21b  mov     rsi, r9
0x18005c21e  mov     rdi, r8
0x18005c221  movzx   r15d, dl
0x18005c225  mov     r14, rcx
0x18005c228  xor     r12d, r12d
0x18005c22b  cmp     [r9+10h], r12b
0x18005c22f  setnz   r12b
0x18005c233  or      r12d, 30000000h
0x18005c23a  cmp     qword ptr [r8+18h], 7
0x18005c23f  jbe     short loc_18005C246
0x18005c241  mov     rbx, [r8]
0x18005c244  jmp     short loc_18005C249
0x18005c246  mov     rbx, rdi
0x18005c249  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x18005c24e  test    al, al
0x18005c250  jz      short loc_18005C278
0x18005c252  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x18005c259  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x18005c25e  mov     r8d, r15d
0x18005c261  mov     [rsp+80h+var_60], r12d; int
0x18005c266  mov     r9, rbx
0x18005c269  lea     rdx, aSessionhostCre; "SessionHost::CreateAndStartSessionStrea"...
0x18005c270  mov     rcx, rax; this
0x18005c273  call    ?LogVerbose_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogVerbose_(ushort const *,...)
0x18005c278  mov     [rbp+var_38], 0
0x18005c280  lea     rcx, [rbp+var_38]
0x18005c284  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005c289  mov     [rbp+var_50], r14
0x18005c28d  lea     rdx, [rbp+var_50]
0x18005c291  lea     rcx, [rbp+var_38]
0x18005c295  test    r15b, r15b
0x18005c298  jz      short loc_18005C2AC
0x18005c29a  call    ??$MakeAndInitialize@VCDPBinaryHostCallback@Internal@SharingPlatform@@VICDPBinaryHostCallback@@PEAVSessionHost@3@@Details@WRL@Microsoft@@YAJPEAPEAVICDPBinaryHostCallback@@$$QEAPEAVSessionHost@SharingPlatform@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPBinaryHostCallback,ICDPBinaryHostCallback,SharingPlatform::SessionHost *>(ICDPBinaryHostCallback * *,SharingPlatform::SessionHost * &&)
0x18005c29f  mov     ebx, eax
0x18005c2a1  test    eax, eax
0x18005c2a3  jns     short loc_18005C2D4
0x18005c2a5  mov     edx, 85h
0x18005c2aa  jmp     short loc_18005C2BC
0x18005c2ac  call    ??$MakeAndInitialize@VCDPBinaryHostChannelCallback@Internal@SharingPlatform@@VICDPBinaryHostCallback@@PEAVSessionHost@3@@Details@WRL@Microsoft@@YAJPEAPEAVICDPBinaryHostCallback@@$$QEAPEAVSessionHost@SharingPlatform@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPBinaryHostChannelCallback,ICDPBinaryHostCallback,SharingPlatform::SessionHost *>(ICDPBinaryHostCallback * *,SharingPlatform::SessionHost * &&)
0x18005c2b1  mov     ebx, eax
0x18005c2b3  test    eax, eax
0x18005c2b5  jns     short loc_18005C2D4
0x18005c2b7  mov     edx, 89h; void *
0x18005c2bc  lea     r8, aSessionhostCpp; ".\\sessionhost.cpp"
0x18005c2c3  mov     r9d, eax; char *
0x18005c2c6  mov     rcx, [rbp+38h]; this
0x18005c2ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c2cf  jmp     loc_18005C495
0x18005c2d4  mov     qword ptr [rbp+var_48], 0
0x18005c2dc  mov     [rbp+var_30], 0
0x18005c2e4  lea     rcx, [rbp+var_30]
0x18005c2e8  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005c2ed  nop
0x18005c2ee  mov     rcx, cs:?sm_spSessionsAppId@SharingPlatformStatics@SharingPlatform@@0V?$ComPtr@VICDPAppId@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ICDPAppId> SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId
0x18005c2f5  test    rcx, rcx
0x18005c2f8  jz      short loc_18005C30D
0x18005c2fa  mov     rax, [rcx]
0x18005c2fd  mov     rax, [rax+8]
0x18005c301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c306  mov     rcx, cs:?sm_spSessionsAppId@SharingPlatformStatics@SharingPlatform@@0V?$ComPtr@VICDPAppId@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ICDPAppId> SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId
0x18005c30d  mov     [rbp+var_30], rcx
0x18005c311  cmp     qword ptr [rdi+18h], 7
0x18005c316  jbe     short loc_18005C31D
0x18005c318  mov     rcx, [rdi]
0x18005c31b  jmp     short loc_18005C320
0x18005c31d  mov     rcx, rdi
0x18005c320  mov     rax, [rdi+10h]
0x18005c324  lea     r8, [rcx+rax*2]
0x18005c328  jbe     short loc_18005C32D
0x18005c32a  mov     rdi, [rdi]
0x18005c32d  mov     rdx, rdi
0x18005c330  lea     rcx, [rbp+var_28]
0x18005c334  call    ??$?0V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0AEBV?$allocator@D@1@@Z; std::string::string(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::allocator<char> const &)
0x18005c339  lea     rcx, [rbp+var_48]
0x18005c33d  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005c342  lea     r8, [rbp+var_28]
0x18005c346  cmp     [rbp+var_10], 0Fh
0x18005c34b  cmova   r8, [rbp+var_28]
0x18005c350  lea     rax, [rbp+var_48]
0x18005c354  mov     qword ptr [rsp+80h+var_60], rax; int
0x18005c359  mov     r9d, r12d
0x18005c35c  mov     rdx, [rbp+var_38]
0x18005c360  mov     rcx, [rbp+var_30]
0x18005c364  call    cs:__imp_CDPCreateBinaryHostInternal
0x18005c36a  mov     ebx, eax
0x18005c36c  test    eax, eax
0x18005c36e  jns     short loc_18005C3AA
0x18005c370  mov     rcx, [rbp+38h]; this
0x18005c374  mov     r9d, eax; char *
0x18005c377  lea     r8, aSessionhostCpp; ".\\sessionhost.cpp"
0x18005c37e  mov     edx, 94h; void *
0x18005c383  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c388  lea     rcx, [rbp+var_28]
0x18005c38c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18005c391  nop
0x18005c392  lea     rcx, [rbp+var_30]
0x18005c396  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005c39b  nop
0x18005c39c  lea     rcx, [rbp+var_48]
0x18005c3a0  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005c3a5  jmp     loc_18005C495
0x18005c3aa  lea     rcx, [rbp+var_28]
0x18005c3ae  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18005c3b3  nop
0x18005c3b4  lea     rcx, [rbp+var_30]
0x18005c3b8  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005c3bd  mov     [rbp+var_40], 0
0x18005c3c5  mov     [rbp+var_50], r14
0x18005c3c9  lea     rcx, [rbp+var_40]
0x18005c3cd  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005c3d2  lea     rdx, [rbp+var_50]
0x18005c3d6  lea     rcx, [rbp+var_40]
0x18005c3da  call    ??$MakeAndInitialize@VCDPHostAuthorizationProvider@Internal@SharingPlatform@@VICDPHostAuthorizationProvider@@PEAVSessionHost@3@@Details@WRL@Microsoft@@YAJPEAPEAVICDPHostAuthorizationProvider@@$$QEAPEAVSessionHost@SharingPlatform@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPHostAuthorizationProvider,ICDPHostAuthorizationProvider,SharingPlatform::SessionHost *>(ICDPHostAuthorizationProvider * *,SharingPlatform::SessionHost * &&)
0x18005c3df  mov     ebx, eax
0x18005c3e1  test    eax, eax
0x18005c3e3  jns     short loc_18005C409
0x18005c3e5  mov     edx, 99h; void *
0x18005c3ea  lea     r8, aSessionhostCpp; ".\\sessionhost.cpp"
0x18005c3f1  mov     r9d, eax; char *
0x18005c3f4  mov     rcx, [rbp+38h]; this
0x18005c3f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c3fd  nop
0x18005c3fe  lea     rcx, [rbp+var_40]
0x18005c402  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005c407  jmp     short loc_18005C39C
0x18005c409  mov     rcx, qword ptr [rbp+var_48]
0x18005c40d  mov     rax, [rcx]
0x18005c410  mov     rdx, [rbp+var_40]
0x18005c414  mov     rax, [rax+38h]
0x18005c418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c41d  mov     ebx, eax
0x18005c41f  test    eax, eax
0x18005c421  jns     short loc_18005C42A
0x18005c423  mov     edx, 9Ah
0x18005c428  jmp     short loc_18005C3EA
0x18005c42a  mov     rbx, qword ptr [rbp+var_48]
0x18005c42e  cmp     [rsi], rbx
0x18005c431  jz      short loc_18005C453
0x18005c433  mov     [rbp+var_50], rbx
0x18005c437  lea     rcx, [rbp+var_50]
0x18005c43b  call    ?InternalAddRef@?$ComPtr@UISessionIdentifier@SharingPlatform@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(void)
0x18005c440  mov     rax, [rsi]
0x18005c443  mov     [rbp+var_50], rax
0x18005c447  mov     [rsi], rbx
0x18005c44a  lea     rcx, [rbp+var_50]
0x18005c44e  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005c453  mov     rbx, [rbp+var_38]
0x18005c457  cmp     [rsi+8], rbx
0x18005c45b  jz      short loc_18005C480
0x18005c45d  mov     [rbp+var_50], rbx
0x18005c461  lea     rcx, [rbp+var_50]
0x18005c465  call    ?InternalAddRef@?$ComPtr@UISessionIdentifier@SharingPlatform@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(void)
0x18005c46a  mov     rax, [rsi+8]
0x18005c46e  mov     [rbp+var_50], rax
0x18005c472  mov     [rsi+8], rbx
0x18005c476  lea     rcx, [rbp+var_50]
0x18005c47a  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005c47f  nop
0x18005c480  lea     rcx, [rbp+var_40]
0x18005c484  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005c489  nop
0x18005c48a  lea     rcx, [rbp+var_48]
0x18005c48e  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005c493  xor     ebx, ebx
0x18005c495  lea     rcx, [rbp+var_38]
0x18005c499  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005c49e  mov     eax, ebx
0x18005c4a0  mov     rcx, [rbp+var_8]
0x18005c4a4  xor     rcx, rsp; StackCookie
0x18005c4a7  call    __security_check_cookie
0x18005c4ac  add     rsp, 80h
0x18005c4b3  pop     r15
0x18005c4b5  pop     r14
0x18005c4b7  pop     r12
0x18005c4b9  pop     rdi
0x18005c4ba  pop     rsi
0x18005c4bb  pop     rbx
0x18005c4bc  pop     rbp
0x18005c4bd  retn
```
