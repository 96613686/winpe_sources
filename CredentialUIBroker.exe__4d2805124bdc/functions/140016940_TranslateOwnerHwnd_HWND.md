# TranslateOwnerHwnd(HWND__ * &)

- ea: `0x140016940`
- end: `0x140016a4e`
- name: `?TranslateOwnerHwnd@@YAJAEAPEAUHWND__@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(HWND *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140010a88`

## callees

- `0x140003620`
- `0x14000b47c`
- `0x14000e920`
- `0x1400136fc`
- `0x140016940`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400169b6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400169b6`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-2!IsEnhancedWindowingEnabled` at `0x140016963`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-2!IsEnhancedWindowingEnabled` at `0x140016963`

## string_xrefs

- `0x1400169c6`: `shellcommon\internal\shell\inc\CredUIApiCommon.h`

## pseudocode

```c
__int64 __fastcall TranslateOwnerHwnd(HWND *a1)
{
  __int64 v2; // rbx
  int ActivationFactory; // eax
  unsigned int v4; // ebx
  __int64 v5; // r8
  __int64 v6; // rax
  int v7; // eax
  int v9; // [rsp+20h] [rbp-50h]
  __int64 *v10; // [rsp+30h] [rbp-40h] BYREF
  HWND v11; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v13; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  if ( (unsigned int)IsEnhancedWindowingEnabled() )
  {
    v10 = 0;
    v13 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.UI.WindowManagement.Preview.WindowManagementPreview",
      0x3Cu,
      0x3Bu);
    v2 = v13;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
    ActivationFactory = RoGetActivationFactory(v2, &GUID_024838b0_2bbc_575f_8d01_fcf966d69516, &v10);
    v4 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\CredUIApiCommon.h",
        (const char *)(unsigned int)ActivationFactory,
        v9);
LABEL_6:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
      return v4;
    }
    v5 = (__int64)*a1;
    v11 = 0;
    v6 = *v10;
    *(GUID *)&hstringHeader.Reserved.Reserved1 = GUID_NULL;
    v7 = (*(__int64 (__fastcall **)(__int64 *, HSTRING_HEADER *, __int64, HWND *))(v6 + 48))(
           v10,
           &hstringHeader,
           v5,
           &v11);
    if ( v7 < 0 )
    {
      v4 = v7;
      goto LABEL_6;
    }
    *a1 = v11;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  }
  return 0;
}

```

## disassembly

```asm
0x140016940  mov     [rsp-8+arg_8], rbx
0x140016945  mov     [rsp-8+arg_10], rdi
0x14001694a  push    rbp
0x14001694b  mov     rbp, rsp
0x14001694e  sub     rsp, 70h
0x140016952  mov     rax, cs:__security_cookie
0x140016959  xor     rax, rsp
0x14001695c  mov     [rbp+var_10], rax
0x140016960  mov     rdi, rcx
0x140016963  call    cs:__imp_IsEnhancedWindowingEnabled
0x140016969  test    eax, eax
0x14001696b  jz      loc_140016A2E
0x140016971  mov     r9d, 3Bh ; ';'; unsigned int
0x140016977  mov     [rbp+var_40], 0
0x14001697f  lea     rdx, ?RuntimeClass_Windows_UI_WindowManagement_Preview_WindowManagementPreview@@3QBGB; "Windows.UI.WindowManagement.Preview.Win"...
0x140016986  mov     [rbp+var_18], 0
0x14001698e  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x140016992  lea     r8d, [r9+1]; unsigned int
0x140016996  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14001699b  mov     rbx, [rbp+var_18]
0x14001699f  lea     rcx, [rbp+var_40]
0x1400169a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400169a8  lea     r8, [rbp+var_40]
0x1400169ac  mov     rcx, rbx
0x1400169af  lea     rdx, _GUID_024838b0_2bbc_575f_8d01_fcf966d69516
0x1400169b6  call    cs:__imp_RoGetActivationFactory
0x1400169bc  mov     ebx, eax
0x1400169be  test    eax, eax
0x1400169c0  jns     short loc_1400169DC
0x1400169c2  mov     rcx, [rbp+8]; this
0x1400169c6  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Cred"...
0x1400169cd  mov     r9d, eax; char *
0x1400169d0  mov     edx, 0A3h; void *
0x1400169d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400169da  jmp     short loc_140016A11
0x1400169dc  mov     rcx, [rbp+var_40]
0x1400169e0  lea     r9, [rbp+var_38]
0x1400169e4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400169eb  mov     r8, [rdi]
0x1400169ee  lea     rdx, [rbp+hstringHeader]
0x1400169f2  mov     [rbp+var_38], 0
0x1400169fa  mov     rax, [rcx]
0x1400169fd  movdqu  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x140016a02  mov     rax, [rax+30h]
0x140016a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016a0b  test    eax, eax
0x140016a0d  jns     short loc_140016A1E
0x140016a0f  mov     ebx, eax
0x140016a11  lea     rcx, [rbp+var_40]
0x140016a15  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140016a1a  mov     eax, ebx
0x140016a1c  jmp     short loc_140016A30
0x140016a1e  mov     rax, [rbp+var_38]
0x140016a22  lea     rcx, [rbp+var_40]
0x140016a26  mov     [rdi], rax
0x140016a29  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140016a2e  xor     eax, eax
0x140016a30  mov     rcx, [rbp+var_10]
0x140016a34  xor     rcx, rsp; StackCookie
0x140016a37  call    __security_check_cookie
0x140016a3c  lea     r11, [rsp+70h+var_s0]
0x140016a41  mov     rbx, [r11+18h]
0x140016a45  mov     rdi, [r11+20h]
0x140016a49  mov     rsp, r11
0x140016a4c  pop     rbp
0x140016a4d  retn
```
