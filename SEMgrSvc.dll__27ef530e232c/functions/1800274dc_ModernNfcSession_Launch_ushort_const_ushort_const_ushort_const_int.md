# ModernNfcSession::Launch(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800274dc`
- end: `0x180027aa5`
- name: `?Launch@ModernNfcSession@@SAJPEBG00H@Z`
- size: `1481`
- prototype: `__int64 __fastcall(PCNZWCH sourceString, PCNZWCH, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001cd70`

## callees

- `0x1800049a0`
- `0x180005834`
- `0x180005858`
- `0x180005ee8`
- `0x18000c964`
- `0x18000e4e4`
- `0x18001bd64`
- `0x18001c8a0`
- `0x18001e61c`
- `0x180020d1c`
- `0x180021080`
- `0x1800274dc`
- `0x18002a598`
- `0x18002ad54`
- `0x18002d380`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800275e2`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800275e2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180027604`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180027604`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027744`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027744`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180027667`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180027667`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800275fe`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800275fe`

## string_xrefs

- `0x180027a8b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800276d5`: `onecoreuap\ds\nfc\product\semanagement\common\seeventmgr\src\modernnfcsession.cpp`
- `0x180027773`: `onecoreuap\ds\nfc\product\semanagement\common\seeventmgr\src\modernnfcsession.cpp`
- `0x18002799c`: `onecoreuap\ds\nfc\product\semanagement\common\seeventmgr\src\modernnfcsession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall ModernNfcSession::Launch(PCNZWCH sourceString, PCNZWCH a2, const unsigned __int16 *a3, int a4)
{
  bool v7; // bl
  HRESULT v8; // eax
  wil::details::in1diag3 *v9; // rcx
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  int v13; // ebx
  __int64 v14; // rcx
  HRESULT v15; // eax
  int v16; // edx
  __int64 v17; // r8
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rbx
  __int64 (__fastcall *v26)(__int64, __int64 *); // rdi
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v35; // rcx
  int v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+20h] [rbp-E0h]
  __int64 v38; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43[14]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+D8h] [rbp-28h]
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING string; // [rsp+F8h] [rbp-8h] BYREF
  void **v47; // [rsp+100h] [rbp+0h] BYREF
  int v48; // [rsp+108h] [rbp+8h] BYREF
  char v49; // [rsp+10Ch] [rbp+Ch]
  int v50; // [rsp+130h] [rbp+30h] BYREF
  const char *v51; // [rsp+138h] [rbp+38h]
  __int64 v52; // [rsp+140h] [rbp+40h]
  char v53; // [rsp+148h] [rbp+48h]
  int v54; // [rsp+150h] [rbp+50h]
  _BYTE v55[152]; // [rsp+158h] [rbp+58h] BYREF
  __int128 v56; // [rsp+1F0h] [rbp+F0h]
  int v57; // [rsp+200h] [rbp+100h]
  __int64 v58; // [rsp+208h] [rbp+108h]
  int *v59; // [rsp+210h] [rbp+110h]
  __int64 v60; // [rsp+218h] [rbp+118h]
  __int64 v61; // [rsp+220h] [rbp+120h]
  void ***v62; // [rsp+228h] [rbp+128h]
  __int64 v63; // [rsp+230h] [rbp+130h]
  int v64; // [rsp+238h] [rbp+138h]
  int *v65; // [rsp+240h] [rbp+140h]
  char v66; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v7 = a4 != 0;
  v48 = 0;
  v49 = 0;
  v53 = 0;
  v50 = 0;
  v51 = "LaunchModernNfcSession";
  v52 = 0;
  v54 = 0;
  v56 = 0;
  memset_0(v55, 0, sizeof(v55));
  v57 = 1;
  v58 = 0;
  v59 = &v48;
  v60 = 0;
  v61 = 0;
  v62 = &v47;
  v63 = 0;
  v64 = 0;
  v65 = &v50;
  v66 = 0;
  v47 = &SEManagementTelemetry::LaunchModernNfcSession::`vftable';
  SEManagementTelemetry::LaunchModernNfcSession::StartActivity(
    (SEManagementTelemetry::LaunchModernNfcSession *)&v47,
    sourceString,
    a2,
    v7);
  v42 = 0;
  if ( (unsigned __int8)IsUMgrQueryUserContextPresent() )
  {
    v8 = CoImpersonateClient();
    v9 = retaddr;
    if ( v8 < 0 )
      goto LABEL_59;
    UMgrQueryUserContext(0, &v42);
    CoRevertToSelf();
  }
  v38 = 0;
  string = 0;
  v10 = WindowsCreateStringReference(L"Windows.Foundation.Collections.ValueSet", 0x27u, &hstringHeader, &string);
  if ( v10 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
    JUMPOUT(0x180027AA4LL);
  }
  v38 = 0;
  v39 = 0;
  v13 = RoActivateInstance(string, &v39);
  if ( v13 >= 0 )
  {
    if ( !memcmp_0(&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v38 = v39;
    }
    else
    {
      v13 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v39)(
              v39,
              &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
              &v38);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
  }
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seeventmgr\\src\\modernnfcsession.cpp",
      (const char *)(unsigned int)v13,
      v36);
    v14 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
LABEL_52:
    v47 = &SEManagementTelemetry::LaunchModernNfcSession::`vftable';
    wil::ActivityBase<SEManagementTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v47);
    wil::ActivityBase<SEManagementTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SEManagementTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(&v47);
    return (unsigned int)v13;
  }
  v41 = v38;
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
  string = 0;
  v15 = WindowsCreateStringReference(L"SmartCardTriggerLaunch", 0x16u, &hstringHeader, &string);
  if ( v15 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
LABEL_59:
    wil::details::in1diag3::_FailFast_Hr(
      v9,
      (void *)0x14AA,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v8,
      v36);
  }
  v18 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(&v41, string, v17, a4 != 0);
  v13 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seeventmgr\\src\\modernnfcsession.cpp",
      (const char *)(unsigned int)v18,
      v36);
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v19 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    goto LABEL_52;
  }
  v44 = 0;
  v40 = 0;
  v20 = Windows::Internal::Shell::TryShellActivateApplicationAsync(
          sourceString,
          a2,
          v38,
          v42,
          0,
          v42,
          &v40,
          (__int64)v43);
  v13 = v20;
  if ( v20 >= 0 )
  {
    v39 = 0;
    v22 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> *>(v40);
    v13 = v22;
    if ( v22 >= 0 )
    {
      v25 = v40;
      v26 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 64LL);
      v27 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      v28 = v26(v25, &v39);
      v13 = v28;
      if ( v28 >= 0 )
      {
        v31 = v39;
        if ( v39 )
        {
          v39 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        }
        v32 = v40;
        if ( v40 )
        {
          v40 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        }
        v13 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21D,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\shellactivationhelpers.h",
          (const char *)(unsigned int)v28,
          v37);
        v29 = v39;
        if ( v39 )
        {
          v39 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        v30 = v40;
        if ( v40 )
        {
          v40 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21C,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\shellactivationhelpers.h",
        (const char *)(unsigned int)v22,
        v37);
      v23 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      v24 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x219,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\shellactivationhelpers.h",
      (const char *)(unsigned int)v20,
      v37);
    v21 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
  }
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 24LL))(v44);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seeventmgr\\src\\modernnfcsession.cpp",
      (const char *)(unsigned int)v13,
      v37);
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v33 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    goto LABEL_52;
  }
  SEManagementTelemetry::LaunchModernNfcSession::Stop((SEManagementTelemetry::LaunchModernNfcSession *)&v47, v42);
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  v35 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v47 = &SEManagementTelemetry::LaunchModernNfcSession::`vftable';
  wil::ActivityBase<SEManagementTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v47);
  wil::ActivityBase<SEManagementTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SEManagementTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(&v47);
  return 0;
}

```

## disassembly

```asm
0x1800274dc  mov     [rsp-8+arg_10], rbx
0x1800274e1  mov     [rsp-8+arg_18], rsi
0x1800274e6  push    rbp
0x1800274e7  push    rdi
0x1800274e8  push    r12
0x1800274ea  push    r14
0x1800274ec  push    r15
0x1800274ee  lea     rbp, [rsp-160h]
0x1800274f6  sub     rsp, 260h
0x1800274fd  mov     rax, cs:__security_cookie
0x180027504  xor     rax, rsp
0x180027507  mov     [rbp+180h+var_30], rax
0x18002750e  mov     edi, r9d
0x180027511  mov     r14, rdx
0x180027514  mov     rsi, rcx
0x180027517  xor     r15d, r15d
0x18002751a  test    r9d, r9d
0x18002751d  setnz   bl
0x180027520  mov     [rbp+180h+var_178], r15d
0x180027524  mov     [rbp+180h+var_174], r15b
0x180027528  mov     [rbp+180h+var_138], r15b
0x18002752c  mov     [rbp+180h+var_150], r15d
0x180027530  lea     rax, aLaunchmodernnf_0; "LaunchModernNfcSession"
0x180027537  mov     [rbp+180h+var_148], rax
0x18002753b  mov     [rbp+180h+var_140], r15
0x18002753f  mov     [rbp+180h+var_130], r15d
0x180027543  xorps   xmm0, xmm0
0x180027546  movdqa  [rbp+180h+var_90], xmm0
0x18002754e  xor     edx, edx; Val
0x180027550  mov     r8d, 98h; Size
0x180027556  lea     rcx, [rbp+180h+var_128]; void *
0x18002755a  call    memset_0
0x18002755f  mov     [rbp+180h+var_80], 1
0x180027569  xor     eax, eax
0x18002756b  mov     [rbp+180h+var_78], rax
0x180027572  lea     rax, [rbp+180h+var_178]
0x180027576  mov     [rbp+180h+var_70], rax
0x18002757d  mov     [rbp+180h+var_68], r15
0x180027584  mov     [rbp+180h+var_60], r15
0x18002758b  lea     rax, [rbp+180h+var_180]
0x18002758f  mov     [rbp+180h+var_58], rax
0x180027596  mov     [rbp+180h+var_50], r15
0x18002759d  mov     [rbp+180h+var_48], r15d
0x1800275a4  lea     rax, [rbp+180h+var_150]
0x1800275a8  mov     [rbp+180h+var_40], rax
0x1800275af  mov     [rbp+180h+var_38], r15b
0x1800275b6  lea     r12, ??_7LaunchModernNfcSession@SEManagementTelemetry@@6B@; const SEManagementTelemetry::LaunchModernNfcSession::`vftable'
0x1800275bd  mov     [rbp+180h+var_180], r12
0x1800275c1  mov     r9b, bl; bool
0x1800275c4  mov     r8, r14; unsigned __int16 *
0x1800275c7  mov     rdx, rsi; unsigned __int16 *
0x1800275ca  lea     rcx, [rbp+180h+var_180]; this
0x1800275ce  call    ?StartActivity@LaunchModernNfcSession@SEManagementTelemetry@@QEAAXPEBG0_N@Z; SEManagementTelemetry::LaunchModernNfcSession::StartActivity(ushort const *,ushort const *,bool)
0x1800275d3  nop
0x1800275d4  mov     [rsp+280h+var_220], r15
0x1800275d9  call    IsUMgrQueryUserContextPresent
0x1800275de  test    al, al
0x1800275e0  jz      short loc_18002760A
0x1800275e2  call    cs:__imp_CoImpersonateClient
0x1800275e8  mov     rcx, [rbp+188h]
0x1800275ef  test    eax, eax
0x1800275f1  js      loc_180027A88
0x1800275f7  lea     rdx, [rsp+280h+var_220]
0x1800275fc  xor     ecx, ecx
0x1800275fe  call    cs:__imp_UMgrQueryUserContext
0x180027604  call    cs:__imp_CoRevertToSelf
0x18002760a  mov     [rsp+280h+var_240], r15
0x18002760f  mov     [rbp+180h+string], r15
0x180027613  lea     r9, [rbp+180h+string]; string
0x180027617  lea     r8, [rbp+180h+hstringHeader]; hstringHeader
0x18002761b  mov     edx, 27h ; '''; length
0x180027620  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x180027627  call    cs:__imp_WindowsCreateStringReference
0x18002762d  test    eax, eax
0x18002762f  js      loc_180027A9D
0x180027635  mov     rbx, [rbp+180h+string]
0x180027639  mov     rcx, [rsp+280h+var_240]
0x18002763e  test    rcx, rcx
0x180027641  jz      short loc_180027655
0x180027643  mov     [rsp+280h+var_240], r15
0x180027648  mov     rax, [rcx]
0x18002764b  mov     rax, [rax+10h]
0x18002764f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027654  nop
0x180027655  mov     [rsp+280h+var_240], r15
0x18002765a  mov     [rsp+280h+var_238], r15
0x18002765f  lea     rdx, [rsp+280h+var_238]
0x180027664  mov     rcx, rbx
0x180027667  call    cs:__imp_RoActivateInstance
0x18002766d  mov     ebx, eax
0x18002766f  test    eax, eax
0x180027671  js      short loc_1800276C7
0x180027673  mov     r8d, 10h; Size
0x180027679  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180027680  lea     rcx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; Buf1
0x180027687  call    memcmp_0
0x18002768c  mov     rcx, [rsp+280h+var_238]
0x180027691  test    eax, eax
0x180027693  jnz     short loc_18002769C
0x180027695  mov     [rsp+280h+var_240], rcx
0x18002769a  jmp     short loc_1800276C7
0x18002769c  mov     rax, [rcx]
0x18002769f  lea     r8, [rsp+280h+var_240]
0x1800276a4  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x1800276ab  mov     rax, [rax]
0x1800276ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276b3  mov     ebx, eax
0x1800276b5  mov     rcx, [rsp+280h+var_238]
0x1800276ba  mov     rax, [rcx]
0x1800276bd  mov     rax, [rax+10h]
0x1800276c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276c6  nop
0x1800276c7  test    ebx, ebx
0x1800276c9  jns     short loc_180027708
0x1800276cb  mov     rcx, [rbp+188h]; this
0x1800276d2  mov     r9d, ebx; char *
0x1800276d5  lea     r8, aOnecoreuapDsNf_53; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x1800276dc  mov     edx, 24h ; '$'; void *
0x1800276e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800276e6  nop
0x1800276e7  mov     rcx, [rsp+280h+var_240]
0x1800276ec  test    rcx, rcx
0x1800276ef  jz      short loc_180027703
0x1800276f1  mov     [rsp+280h+var_240], r15
0x1800276f6  mov     rax, [rcx]
0x1800276f9  mov     rax, [rax+10h]
0x1800276fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027702  nop
0x180027703  jmp     loc_1800279E1
0x180027708  mov     rcx, [rsp+280h+var_240]
0x18002770d  mov     [rsp+280h+var_228], rcx
0x180027712  test    rcx, rcx
0x180027715  jz      short loc_180027724
0x180027717  mov     rax, [rcx]
0x18002771a  mov     rax, [rax+8]
0x18002771e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027723  nop
0x180027724  mov     ebx, r15d
0x180027727  test    edi, edi
0x180027729  setnz   bl
0x18002772c  mov     [rbp+180h+string], r15
0x180027730  lea     r9, [rbp+180h+string]; string
0x180027734  lea     r8, [rbp+180h+hstringHeader]; hstringHeader
0x180027738  mov     edx, 16h; length
0x18002773d  lea     rcx, aSmartcardtrigg; "SmartCardTriggerLaunch"
0x180027744  call    cs:__imp_WindowsCreateStringReference
0x18002774a  test    eax, eax
0x18002774c  js      loc_180027A80
0x180027752  mov     r9d, ebx
0x180027755  mov     rdx, [rbp+180h+string]
0x180027759  lea     rcx, [rsp+280h+var_228]
0x18002775e  call    ??$SetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJIPEAPEAUIInspectable@@@ZI@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uint,IInspectable * *),uint)
0x180027763  mov     ebx, eax
0x180027765  test    eax, eax
0x180027767  jns     short loc_1800277BD
0x180027769  mov     rcx, [rbp+188h]; this
0x180027770  mov     r9d, eax; char *
0x180027773  lea     r8, aOnecoreuapDsNf_53; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18002777a  mov     edx, 2Bh ; '+'; void *
0x18002777f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027784  nop
0x180027785  mov     rcx, [rsp+280h+var_228]
0x18002778a  test    rcx, rcx
0x18002778d  jz      short loc_18002779C
0x18002778f  mov     rax, [rcx]
0x180027792  mov     rax, [rax+10h]
0x180027796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002779b  nop
0x18002779c  mov     rcx, [rsp+280h+var_240]
0x1800277a1  test    rcx, rcx
0x1800277a4  jz      short loc_1800277B8
0x1800277a6  mov     [rsp+280h+var_240], r15
0x1800277ab  mov     rax, [rcx]
0x1800277ae  mov     rax, [rax+10h]
0x1800277b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277b7  nop
0x1800277b8  jmp     loc_1800279E1
0x1800277bd  mov     [rbp+180h+var_1A8], r15
0x1800277c1  mov     r9, [rsp+280h+var_220]
0x1800277c6  mov     [rsp+280h+var_230], r15
0x1800277cb  lea     rcx, [rsp+280h+var_218]
0x1800277d0  mov     [rsp+280h+var_248], rcx; __int64
0x1800277d5  lea     rcx, [rsp+280h+var_230]
0x1800277da  mov     [rsp+280h+var_250], rcx; __int64
0x1800277df  mov     [rsp+280h+var_258], r9; __int64
0x1800277e4  mov     [rsp+280h+var_260], r15d; int
0x1800277e9  mov     r8, [rsp+280h+var_240]
0x1800277ee  mov     rdx, r14; PCNZWCH
0x1800277f1  mov     rcx, rsi; sourceString
0x1800277f4  call    ?TryShellActivateApplicationAsync@Shell@Internal@Windows@@YAJPEBG0PEAUIPropertySet@Collections@Foundation@3@0UWindowId@WindowManagement@ApplicationModel@23@_KPEAPEAU?$IAsyncOperation@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@63@$$QEAV?$function@$$A6AJUActivationArguments@Shell@Internal@Windows@@PEAUIPropertySet@Collections@Foundation@4@UWindowId@WindowManagement@ApplicationModel@34@_KPEAK@Z@wistd@@@Z; Windows::Internal::Shell::TryShellActivateApplicationAsync(ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet *,ushort const *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> * *,wistd::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,ulong *)> &&)
0x1800277f9  mov     ebx, eax
0x1800277fb  test    eax, eax
0x1800277fd  jns     short loc_18002783C
0x1800277ff  mov     rcx, [rbp+188h]; this
0x180027806  mov     r9d, eax; char *
0x180027809  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\shell"...
0x180027810  mov     edx, 219h; void *
0x180027815  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002781a  nop
0x18002781b  mov     rcx, [rsp+280h+var_230]
0x180027820  test    rcx, rcx
0x180027823  jz      short loc_180027837
0x180027825  mov     [rsp+280h+var_230], r15
0x18002782a  mov     rax, [rcx]
0x18002782d  mov     rax, [rax+10h]
0x180027831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027836  nop
0x180027837  jmp     loc_180027979
0x18002783c  mov     [rsp+280h+var_238], r15
0x180027841  mov     rcx, [rsp+280h+var_230]
0x180027846  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18002784b  mov     ebx, eax
0x18002784d  test    eax, eax
0x18002784f  jns     short loc_1800278AA
0x180027851  mov     rcx, [rbp+188h]; this
0x180027858  mov     r9d, eax; char *
0x18002785b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\shell"...
0x180027862  mov     edx, 21Ch; void *
0x180027867  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002786c  nop
0x18002786d  mov     rcx, [rsp+280h+var_238]
0x180027872  test    rcx, rcx
0x180027875  jz      short loc_180027889
0x180027877  mov     [rsp+280h+var_238], r15
0x18002787c  mov     rax, [rcx]
0x18002787f  mov     rax, [rax+10h]
0x180027883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027888  nop
0x180027889  mov     rcx, [rsp+280h+var_230]
0x18002788e  test    rcx, rcx
0x180027891  jz      short loc_1800278A5
0x180027893  mov     [rsp+280h+var_230], r15
0x180027898  mov     rax, [rcx]
0x18002789b  mov     rax, [rax+10h]
0x18002789f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278a4  nop
0x1800278a5  jmp     loc_180027979
0x1800278aa  mov     rbx, [rsp+280h+var_230]
0x1800278af  mov     rax, [rbx]
0x1800278b2  mov     rdi, [rax+40h]
0x1800278b6  mov     rcx, [rsp+280h+var_238]
0x1800278bb  test    rcx, rcx
0x1800278be  jz      short loc_1800278D2
0x1800278c0  mov     [rsp+280h+var_238], r15
0x1800278c5  mov     rdx, [rcx]
0x1800278c8  mov     rax, [rdx+10h]
0x1800278cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278d1  nop
0x1800278d2  lea     rdx, [rsp+280h+var_238]
0x1800278d7  mov     rcx, rbx
0x1800278da  mov     rax, rdi
0x1800278dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278e2  mov     ebx, eax
0x1800278e4  test    eax, eax
0x1800278e6  jns     short loc_18002793E
0x1800278e8  mov     rcx, [rbp+188h]; this
0x1800278ef  mov     r9d, eax; char *
0x1800278f2  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\shell"...
0x1800278f9  mov     edx, 21Dh; void *
0x1800278fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027903  nop
0x180027904  mov     rcx, [rsp+280h+var_238]
0x180027909  test    rcx, rcx
0x18002790c  jz      short loc_180027920
0x18002790e  mov     [rsp+280h+var_238], r15
0x180027913  mov     rax, [rcx]
0x180027916  mov     rax, [rax+10h]
0x18002791a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002791f  nop
0x180027920  mov     rcx, [rsp+280h+var_230]
0x180027925  test    rcx, rcx
0x180027928  jz      short loc_18002793C
0x18002792a  mov     [rsp+280h+var_230], r15
0x18002792f  mov     rax, [rcx]
0x180027932  mov     rax, [rax+10h]
0x180027936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002793b  nop
0x18002793c  jmp     short loc_180027979
0x18002793e  mov     rcx, [rsp+280h+var_238]
0x180027943  test    rcx, rcx
0x180027946  jz      short loc_18002795A
0x180027948  mov     [rsp+280h+var_238], r15
0x18002794d  mov     rax, [rcx]
0x180027950  mov     rax, [rax+10h]
0x180027954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027959  nop
0x18002795a  mov     rcx, [rsp+280h+var_230]
0x18002795f  test    rcx, rcx
0x180027962  jz      short loc_180027976
0x180027964  mov     [rsp+280h+var_230], r15
0x180027969  mov     rax, [rcx]
0x18002796c  mov     rax, [rax+10h]
0x180027970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027975  nop
0x180027976  mov     ebx, r15d
0x180027979  mov     rcx, [rbp+180h+var_1A8]
0x18002797d  test    rcx, rcx
0x180027980  jz      short loc_18002798E
0x180027982  mov     rax, [rcx]
0x180027985  mov     rax, [rax+18h]
  ... truncated ...
```
