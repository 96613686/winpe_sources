# ImpersonationHelper::GetActiveUserTokenFromUserManager(void * *,bool &)

- ea: `0x18001d2c8`
- end: `0x18001d5d1`
- name: `?GetActiveUserTokenFromUserManager@ImpersonationHelper@@CAJPEAPEAXAEA_N@Z`
- size: `777`
- prototype: `__int64 __fastcall(void **, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d048`

## callees

- `0x18000a6e0`
- `0x18001055c`
- `0x18001208c`
- `0x180018688`
- `0x18001b6a0`
- `0x18001d2c8`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d33a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d3a8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d33a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d3a8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18001d4fb`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18001d4fb`

## string_xrefs

- `0x18001d34d`: `onecore\base\diagnosis\mitigation\client\inc\ImpersonationHelper.h`
- `0x18001d3bb`: `onecore\base\diagnosis\mitigation\client\inc\ImpersonationHelper.h`
- `0x18001d409`: `onecore\base\diagnosis\mitigation\client\inc\ImpersonationHelper.h`
- `0x18001d574`: `onecore\base\diagnosis\mitigation\client\inc\ImpersonationHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ImpersonationHelper::GetActiveUserTokenFromUserManager(void **a1, bool *a2)
{
  __int64 v4; // rbx
  int ActivationFactory; // eax
  int v6; // ebx
  __int64 v7; // rbx
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v11; // eax
  int (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rdi
  HRESULT v13; // edx
  __int64 v14; // r8
  int v15; // eax
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  unsigned int i; // esi
  __int64 v19; // rdi
  int (__fastcall *v20)(__int64, _QWORD, __int64 *); // rbx
  __int64 v22; // [rsp+20h] [rbp-60h] BYREF
  __int64 v23; // [rsp+28h] [rbp-58h] BYREF
  int (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-50h] BYREF
  __int64 v25; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v26; // [rsp+40h] [rbp-40h] BYREF
  __int64 v27; // [rsp+48h] [rbp-38h] BYREF
  __int64 v28; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v30; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *a2 = 0;
  v25 = 0;
  v30 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Internal.UserManager",
    0x24u,
    0x23u);
  v4 = v30;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v25);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\ImpersonationHelper.h",
      (const char *)(unsigned int)ActivationFactory,
      v22);
LABEL_23:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
    return (unsigned int)v6;
  }
  v22 = 0;
  v30 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.System.User", 0x14u, 0x13u);
  v7 = v30;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
  v8 = RoGetActivationFactory(v7, &GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fdd, &v22);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\ImpersonationHelper.h",
      (const char *)(unsigned int)v8,
      v22);
LABEL_22:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
    goto LABEL_23;
  }
  v24 = 0;
  v9 = v22;
  v10 = *(__int64 (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v22 + 56LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
  v11 = v10(v9, &v24);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\ImpersonationHelper.h",
      (const char *)(unsigned int)v11,
      v22);
LABEL_21:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
    goto LABEL_22;
  }
  v23 = 0;
  v12 = v24;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
  v6 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(
         v12,
         v13,
         v14);
  if ( v6 < 0
    || (v6 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v12)[8])(v12, &v23),
        v6 < 0) )
  {
    v16 = (unsigned int)v6;
    v17 = 212;
    goto LABEL_20;
  }
  v26 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 56LL))(v23, &v26);
  v6 = v15;
  if ( v15 < 0 )
  {
    v16 = (unsigned int)v15;
    v17 = 215;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\ImpersonationHelper.h",
      (const char *)v16,
      v22);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
    goto LABEL_21;
  }
  for ( i = 0; i < v26; ++i )
  {
    v27 = 0;
    v19 = v23;
    v20 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v23 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
    if ( v20(v19, i, &v27) >= 0 )
    {
      v28 = 0;
      if ( (*(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v25 + 136LL))(v25, v27, &v28) >= 0
        && (int)UMgrQueryUserToken(v28, a1) >= 0 )
      {
        *a2 = 1;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
        v6 = 0;
        goto LABEL_23;
      }
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  return 0;
}

```

## disassembly

```asm
0x18001d2c8  mov     [rsp-28h+arg_10], rbx
0x18001d2cd  push    rbp
0x18001d2ce  push    rsi
0x18001d2cf  push    rdi
0x18001d2d0  push    r14
0x18001d2d2  push    r15
0x18001d2d4  mov     rbp, rsp
0x18001d2d7  sub     rsp, 80h
0x18001d2de  mov     rax, cs:__security_cookie
0x18001d2e5  xor     rax, rsp
0x18001d2e8  mov     [rbp+var_8], rax
0x18001d2ec  mov     r14, rdx
0x18001d2ef  mov     r15, rcx
0x18001d2f2  mov     byte ptr [rdx], 0
0x18001d2f5  mov     [rbp+var_48], 0
0x18001d2fd  mov     [rbp+var_10], 0
0x18001d305  mov     r9d, 23h ; '#'; unsigned int
0x18001d30b  lea     r8d, [r9+1]; unsigned int
0x18001d30f  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18001d316  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18001d31a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001d31f  mov     rbx, [rbp+var_10]
0x18001d323  lea     rcx, [rbp+var_48]
0x18001d327  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d32c  lea     r8, [rbp+var_48]
0x18001d330  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x18001d337  mov     rcx, rbx
0x18001d33a  call    cs:__imp_RoGetActivationFactory
0x18001d340  mov     ebx, eax
0x18001d342  test    eax, eax
0x18001d344  jns     short loc_18001D363
0x18001d346  mov     rcx, [rbp+28h]; this
0x18001d34a  mov     r9d, eax; char *
0x18001d34d  lea     r8, aOnecoreBaseDia_28; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001d354  mov     edx, 0CBh; void *
0x18001d359  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d35e  jmp     loc_18001D5A3
0x18001d363  mov     [rbp+var_60], 0
0x18001d36b  mov     [rbp+var_10], 0
0x18001d373  mov     r9d, 13h; unsigned int
0x18001d379  lea     r8d, [r9+1]; unsigned int
0x18001d37d  lea     rdx, ?RuntimeClass_Windows_System_User@@3QBGB; "Windows.System.User"
0x18001d384  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18001d388  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001d38d  mov     rbx, [rbp+var_10]
0x18001d391  lea     rcx, [rbp+var_60]
0x18001d395  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d39a  lea     r8, [rbp+var_60]
0x18001d39e  lea     rdx, _GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fdd
0x18001d3a5  mov     rcx, rbx
0x18001d3a8  call    cs:__imp_RoGetActivationFactory
0x18001d3ae  mov     ebx, eax
0x18001d3b0  test    eax, eax
0x18001d3b2  jns     short loc_18001D3D1
0x18001d3b4  mov     rcx, [rbp+28h]; this
0x18001d3b8  mov     r9d, eax; char *
0x18001d3bb  lea     r8, aOnecoreBaseDia_28; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001d3c2  mov     edx, 0CEh; void *
0x18001d3c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d3cc  jmp     loc_18001D599
0x18001d3d1  mov     [rbp+var_50], 0
0x18001d3d9  mov     rdi, [rbp+var_60]
0x18001d3dd  mov     rax, [rdi]
0x18001d3e0  mov     rbx, [rax+38h]
0x18001d3e4  lea     rcx, [rbp+var_50]
0x18001d3e8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d3ed  lea     rdx, [rbp+var_50]
0x18001d3f1  mov     rcx, rdi
0x18001d3f4  mov     rax, rbx
0x18001d3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3fc  mov     ebx, eax
0x18001d3fe  test    eax, eax
0x18001d400  jns     short loc_18001D41F
0x18001d402  mov     rcx, [rbp+28h]; this
0x18001d406  mov     r9d, eax; char *
0x18001d409  lea     r8, aOnecoreBaseDia_28; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001d410  mov     edx, 0D1h; void *
0x18001d415  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d41a  jmp     loc_18001D58F
0x18001d41f  mov     [rbp+var_58], 0
0x18001d427  mov     rdi, [rbp+var_50]
0x18001d42b  lea     rcx, [rbp+var_58]
0x18001d42f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d434  mov     rcx, rdi
0x18001d437  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)
0x18001d43c  mov     ebx, eax
0x18001d43e  test    eax, eax
0x18001d440  js      loc_18001D56C
0x18001d446  mov     rax, [rdi]
0x18001d449  lea     rdx, [rbp+var_58]
0x18001d44d  mov     rcx, rdi
0x18001d450  mov     rax, [rax+40h]
0x18001d454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d459  mov     ebx, eax
0x18001d45b  test    eax, eax
0x18001d45d  js      loc_18001D56C
0x18001d463  mov     [rbp+var_40], 0
0x18001d46a  mov     rcx, [rbp+var_58]
0x18001d46e  mov     rax, [rcx]
0x18001d471  lea     rdx, [rbp+var_40]
0x18001d475  mov     rax, [rax+38h]
0x18001d479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d47e  mov     ebx, eax
0x18001d480  test    eax, eax
0x18001d482  jns     short loc_18001D491
0x18001d484  mov     r9d, eax
0x18001d487  mov     edx, 0D7h
0x18001d48c  jmp     loc_18001D574
0x18001d491  xor     esi, esi
0x18001d493  cmp     esi, [rbp+var_40]
0x18001d496  jnb     loc_18001D541
0x18001d49c  mov     [rbp+var_38], 0
0x18001d4a4  mov     rdi, [rbp+var_58]
0x18001d4a8  mov     rax, [rdi]
0x18001d4ab  mov     rbx, [rax+30h]
0x18001d4af  lea     rcx, [rbp+var_38]
0x18001d4b3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d4b8  lea     r8, [rbp+var_38]
0x18001d4bc  mov     edx, esi
0x18001d4be  mov     rcx, rdi
0x18001d4c1  mov     rax, rbx
0x18001d4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4c9  test    eax, eax
0x18001d4cb  js      short loc_18001D505
0x18001d4cd  mov     [rbp+var_30], 0
0x18001d4d5  mov     rcx, [rbp+var_48]
0x18001d4d9  mov     rax, [rcx]
0x18001d4dc  lea     r8, [rbp+var_30]
0x18001d4e0  mov     rdx, [rbp+var_38]
0x18001d4e4  mov     rax, [rax+88h]
0x18001d4eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4f0  test    eax, eax
0x18001d4f2  js      short loc_18001D505
0x18001d4f4  mov     rdx, r15
0x18001d4f7  mov     rcx, [rbp+var_30]
0x18001d4fb  call    cs:__imp_UMgrQueryUserToken
0x18001d501  test    eax, eax
0x18001d503  jns     short loc_18001D512
0x18001d505  lea     rcx, [rbp+var_38]
0x18001d509  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d50e  inc     esi
0x18001d510  jmp     short loc_18001D493
0x18001d512  mov     byte ptr [r14], 1
0x18001d516  lea     rcx, [rbp+var_38]
0x18001d51a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d51f  nop
0x18001d520  lea     rcx, [rbp+var_58]
0x18001d524  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d529  nop
0x18001d52a  lea     rcx, [rbp+var_50]
0x18001d52e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d533  nop
0x18001d534  lea     rcx, [rbp+var_60]
0x18001d538  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d53d  xor     ebx, ebx
0x18001d53f  jmp     short loc_18001D5A3
0x18001d541  lea     rcx, [rbp+var_58]
0x18001d545  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d54a  nop
0x18001d54b  lea     rcx, [rbp+var_50]
0x18001d54f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d554  nop
0x18001d555  lea     rcx, [rbp+var_60]
0x18001d559  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d55e  nop
0x18001d55f  lea     rcx, [rbp+var_48]
0x18001d563  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d568  xor     eax, eax
0x18001d56a  jmp     short loc_18001D5AE
0x18001d56c  mov     r9d, ebx; char *
0x18001d56f  mov     edx, 0D4h; void *
0x18001d574  lea     r8, aOnecoreBaseDia_28; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001d57b  mov     rcx, [rbp+28h]; this
0x18001d57f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d584  nop
0x18001d585  lea     rcx, [rbp+var_58]
0x18001d589  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d58e  nop
0x18001d58f  lea     rcx, [rbp+var_50]
0x18001d593  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d598  nop
0x18001d599  lea     rcx, [rbp+var_60]
0x18001d59d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d5a2  nop
0x18001d5a3  lea     rcx, [rbp+var_48]
0x18001d5a7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d5ac  mov     eax, ebx
0x18001d5ae  mov     rcx, [rbp+var_8]
0x18001d5b2  xor     rcx, rsp; StackCookie
0x18001d5b5  call    __security_check_cookie
0x18001d5ba  mov     rbx, [rsp+80h+arg_10]
0x18001d5c2  add     rsp, 80h
0x18001d5c9  pop     r15
0x18001d5cb  pop     r14
0x18001d5cd  pop     rdi
0x18001d5ce  pop     rsi
0x18001d5cf  pop     rbp
0x18001d5d0  retn
```
