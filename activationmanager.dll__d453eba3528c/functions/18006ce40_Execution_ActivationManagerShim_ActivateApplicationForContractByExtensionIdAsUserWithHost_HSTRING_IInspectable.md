# Execution::ActivationManagerShim::ActivateApplicationForContractByExtensionIdAsUserWithHost(HSTRING__ *,IInspectable *,HSTRING__ *,IInspectable *,ACTIVATEOPTIONSINTERNAL,unsigned __int64,unsigned __int64 *,ulong *)

- ea: `0x18006ce40`
- end: `0x18006d036`
- name: `?ActivateApplicationForContractByExtensionIdAsUserWithHost@ActivationManagerShim@Execution@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@01W4ACTIVATEOPTIONSINTERNAL@@_KPEA_KPEAK@Z`
- size: `502`
- prototype: `int __high(HSTRING, struct IInspectable *, HSTRING, struct IInspectable *, enum ACTIVATEOPTIONSINTERNAL, unsigned __int64, unsigned __int64 *, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006cda0`
- `0x18006cdf0`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x180011590`
- `0x180014040`
- `0x180029270`
- `0x18005a030`
- `0x18006ce40`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ced2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cee0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cf80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cfa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ced2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cee0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cf80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cfa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006cf19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006cf19`
- `combase!__imp_RoGetExtensionRegistrationByExtensionId` at `0x18006cec2`
- `combase!__imp_RoGetExtensionRegistrationByExtensionId` at `0x18006cec2`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!IsOnDemandRegistrationSupportedForExtensionCategory` at `0x18006cf29`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!IsOnDemandRegistrationSupportedForExtensionCategory` at `0x18006cf29`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Execution::ActivationManagerShim::ActivateApplicationForContractByExtensionIdAsUserWithHost(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        HSTRING a4,
        __int64 a5,
        unsigned int a6,
        unsigned __int64 a7,
        __int64 a8,
        unsigned int *a9)
{
  unsigned int *v13; // r15
  unsigned int v14; // ebx
  int ExtensionRegistrationByExtensionId; // edi
  int AppIdForContractAndExtensionId; // eax
  __int64 v17; // rdx
  PCWSTR StringRawBuffer; // rax
  int v20; // [rsp+20h] [rbp-81h]
  HSTRING v21; // [rsp+70h] [rbp-31h] BYREF
  _QWORD v22[2]; // [rsp+78h] [rbp-29h] BYREF
  HSTRING string[2]; // [rsp+88h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+47h]

  v13 = a9;
  if ( a9 )
  {
    *a9 = 0;
    v21 = 0;
    v22[0] = 0;
    *(_OWORD *)string = 0;
    v22[1] = a2;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(string);
    ExtensionRegistrationByExtensionId = RoGetExtensionRegistrationByExtensionId(a4, a2, string);
    if ( ExtensionRegistrationByExtensionId < 0 )
    {
      LODWORD(a9) = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
      AppIdForContractAndExtensionId = IsOnDemandRegistrationSupportedForExtensionCategory(StringRawBuffer, &a9);
      v14 = AppIdForContractAndExtensionId;
      if ( AppIdForContractAndExtensionId < 0 )
      {
        v17 = 789;
        goto LABEL_8;
      }
      if ( !(_DWORD)a9 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x316,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
          (const char *)(unsigned int)ExtensionRegistrationByExtensionId,
          v20);
        goto LABEL_11;
      }
      WindowsDeleteString(v21);
      ExtensionRegistrationByExtensionId = 0;
      v21 = 0;
      AppIdForContractAndExtensionId = GetAppIdForContractAndExtensionId(a4, a2, &v21);
      v14 = AppIdForContractAndExtensionId;
      if ( AppIdForContractAndExtensionId < 0 )
      {
        v17 = 792;
        goto LABEL_8;
      }
    }
    else
    {
      WindowsDeleteString(string[1]);
      string[1] = 0;
      WindowsDeleteString(v21);
      v21 = 0;
      AppIdForContractAndExtensionId = GetAppIdForExtensionRegistration(
                                         (struct Windows::Foundation::IExtensionRegistration *)string[0],
                                         &v21,
                                         &string[1]);
      v14 = AppIdForContractAndExtensionId;
      ExtensionRegistrationByExtensionId = 0;
      if ( AppIdForContractAndExtensionId < 0 )
      {
        v17 = 782;
LABEL_8:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
          (const char *)(unsigned int)AppIdForContractAndExtensionId,
          v20);
LABEL_12:
        ActivateByExtensionArgs::~ActivateByExtensionArgs((ActivateByExtensionArgs *)v22);
        WindowsDeleteString(v21);
        return v14;
      }
    }
    AppIdForContractAndExtensionId = Execution::ActivationManagerShim::ActivateApplicationForContractCore(
                                       a1 - 48,
                                       v21,
                                       a4,
                                       a7,
                                       a6,
                                       a5,
                                       0,
                                       (__int64)v22,
                                       a3,
                                       0,
                                       0,
                                       a8,
                                       v13,
                                       0);
    v14 = AppIdForContractAndExtensionId;
    if ( AppIdForContractAndExtensionId < 0 )
    {
      v17 = 808;
      goto LABEL_8;
    }
LABEL_11:
    v14 = ExtensionRegistrationByExtensionId;
    goto LABEL_12;
  }
  v14 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x301,
    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
    (const char *)0x80004003LL,
    v20);
  return v14;
}

```

## disassembly

```asm
0x18006ce40  push    rbp
0x18006ce42  push    rbx
0x18006ce43  push    rsi
0x18006ce44  push    rdi
0x18006ce45  push    r12
0x18006ce47  push    r13
0x18006ce49  push    r14
0x18006ce4b  push    r15
0x18006ce4d  lea     rbp, [rsp-7]
0x18006ce52  sub     rsp, 0A8h
0x18006ce59  mov     rsi, r9
0x18006ce5c  mov     r12, r8
0x18006ce5f  mov     r14, rdx
0x18006ce62  mov     r13, rcx
0x18006ce65  mov     r15, [rbp+3Fh+arg_40]
0x18006ce6c  xor     ebx, ebx
0x18006ce6e  test    r15, r15
0x18006ce71  jnz     short loc_18006CE95
0x18006ce73  mov     rcx, [rbp+47h]; this
0x18006ce77  mov     ebx, 80004003h
0x18006ce7c  mov     r9d, ebx; char *
0x18006ce7f  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006ce86  mov     edx, 301h; void *
0x18006ce8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ce90  jmp     loc_18006CF86
0x18006ce95  mov     [r15], ebx
0x18006ce98  mov     [rbp+3Fh+var_70], rbx
0x18006ce9c  xorps   xmm0, xmm0
0x18006ce9f  movups  [rbp+3Fh+var_68], xmm0
0x18006cea3  xorps   xmm1, xmm1
0x18006cea6  movdqu  xmmword ptr [rbp+3Fh+string], xmm1
0x18006ceab  mov     qword ptr [rbp+3Fh+var_68+8], r14
0x18006ceaf  lea     rcx, [rbp+3Fh+string]
0x18006ceb3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006ceb8  lea     r8, [rbp+3Fh+string]
0x18006cebc  mov     rdx, r14
0x18006cebf  mov     rcx, rsi
0x18006cec2  call    cs:__imp_RoGetExtensionRegistrationByExtensionId
0x18006cec8  mov     edi, eax
0x18006ceca  test    eax, eax
0x18006cecc  js      short loc_18006CF0E
0x18006cece  mov     rcx, [rbp+3Fh+string+8]; string
0x18006ced2  call    cs:__imp_WindowsDeleteString
0x18006ced8  mov     [rbp+3Fh+string+8], rbx
0x18006cedc  mov     rcx, [rbp+3Fh+var_70]; string
0x18006cee0  call    cs:__imp_WindowsDeleteString
0x18006cee6  mov     [rbp+3Fh+var_70], rbx
0x18006ceea  lea     r8, [rbp+3Fh+string+8]; HSTRING *
0x18006ceee  lea     rdx, [rbp+3Fh+var_70]; HSTRING *
0x18006cef2  mov     rcx, [rbp+3Fh+string]; struct Windows::Foundation::IExtensionRegistration *
0x18006cef6  call    ?GetAppIdForExtensionRegistration@@YAJPEAUIExtensionRegistration@Foundation@Windows@@PEAPEAUHSTRING__@@1@Z; GetAppIdForExtensionRegistration(Windows::Foundation::IExtensionRegistration *,HSTRING__ * *,HSTRING__ * *)
0x18006cefb  mov     ebx, eax
0x18006cefd  xor     edi, edi
0x18006ceff  test    eax, eax
0x18006cf01  jns     loc_18006CFCB
0x18006cf07  mov     edx, 30Eh
0x18006cf0c  jmp     short loc_18006CF3A
0x18006cf0e  mov     dword ptr [rbp+3Fh+arg_40], ebx
0x18006cf14  xor     edx, edx; length
0x18006cf16  mov     rcx, rsi; string
0x18006cf19  call    cs:__imp_WindowsGetStringRawBuffer
0x18006cf1f  lea     rdx, [rbp+3Fh+arg_40]
0x18006cf26  mov     rcx, rax
0x18006cf29  call    cs:__imp_IsOnDemandRegistrationSupportedForExtensionCategory
0x18006cf2f  mov     ebx, eax
0x18006cf31  test    eax, eax
0x18006cf33  jns     short loc_18006CF4F
0x18006cf35  mov     edx, 315h; void *
0x18006cf3a  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006cf41  mov     r9d, eax; char *
0x18006cf44  mov     rcx, [rbp+47h]; this
0x18006cf48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cf4d  jmp     short loc_18006CF72
0x18006cf4f  cmp     dword ptr [rbp+3Fh+arg_40], 0
0x18006cf56  jnz     short loc_18006CF9C
0x18006cf58  mov     rcx, [rbp+47h]; this
0x18006cf5c  mov     r9d, edi; char *
0x18006cf5f  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006cf66  mov     edx, 316h; void *
0x18006cf6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cf70  mov     ebx, edi
0x18006cf72  lea     rcx, [rbp+3Fh+var_68]; this
0x18006cf76  call    ??1ActivateByExtensionArgs@@QEAA@XZ; ActivateByExtensionArgs::~ActivateByExtensionArgs(void)
0x18006cf7b  nop
0x18006cf7c  mov     rcx, [rbp+3Fh+var_70]; string
0x18006cf80  call    cs:__imp_WindowsDeleteString
0x18006cf86  mov     eax, ebx
0x18006cf88  add     rsp, 0A8h
0x18006cf8f  pop     r15
0x18006cf91  pop     r14
0x18006cf93  pop     r13
0x18006cf95  pop     r12
0x18006cf97  pop     rdi
0x18006cf98  pop     rsi
0x18006cf99  pop     rbx
0x18006cf9a  pop     rbp
0x18006cf9b  retn
0x18006cf9c  mov     rcx, [rbp+3Fh+var_70]; string
0x18006cfa0  call    cs:__imp_WindowsDeleteString
0x18006cfa6  xor     edi, edi
0x18006cfa8  mov     [rbp+3Fh+var_70], rdi
0x18006cfac  lea     r8, [rbp+3Fh+var_70]; HSTRING *
0x18006cfb0  mov     rdx, r14; HSTRING
0x18006cfb3  mov     rcx, rsi; string
0x18006cfb6  call    ?GetAppIdForContractAndExtensionId@@YAJPEAUHSTRING__@@0PEAPEAU1@@Z; GetAppIdForContractAndExtensionId(HSTRING__ *,HSTRING__ *,HSTRING__ * *)
0x18006cfbb  mov     ebx, eax
0x18006cfbd  test    eax, eax
0x18006cfbf  jns     short loc_18006CFCB
0x18006cfc1  mov     edx, 318h
0x18006cfc6  jmp     loc_18006CF3A
0x18006cfcb  lea     rcx, [r13-30h]
0x18006cfcf  mov     [rsp+0E0h+var_78], rdi
0x18006cfd4  mov     [rsp+0E0h+var_80], r15
0x18006cfd9  mov     rax, [rbp+3Fh+arg_38]
0x18006cfe0  mov     [rsp+0E0h+var_88], rax
0x18006cfe5  mov     [rsp+0E0h+var_90], rdi
0x18006cfea  mov     [rsp+0E0h+var_98], edi
0x18006cfee  mov     [rsp+0E0h+var_A0], r12
0x18006cff3  lea     rax, [rbp+3Fh+var_68]
0x18006cff7  mov     [rsp+0E0h+var_A8], rax
0x18006cffc  mov     [rsp+0E0h+var_B0], rdi
0x18006d001  mov     rax, [rbp+3Fh+arg_20]
0x18006d005  mov     [rsp+0E0h+var_B8], rax
0x18006d00a  mov     eax, [rbp+3Fh+arg_28]
0x18006d00d  mov     [rsp+0E0h+var_C0], eax
0x18006d011  mov     r9, [rbp+3Fh+arg_30]
0x18006d015  mov     r8, rsi
0x18006d018  mov     rdx, [rbp+3Fh+var_70]
0x18006d01c  call    ?ActivateApplicationForContractCore@ActivationManagerShim@Execution@@IEAAJPEAUHSTRING__@@0_KW4ACTIVATEOPTIONSINTERNAL@@PEAUIInspectable@@PEBU_ActivateComponentInfo@@PEAUActivateByExtensionArgs@@3W4ActivateType@@PEAXPEA_KPEAKPEAPEAU5@@Z; Execution::ActivationManagerShim::ActivateApplicationForContractCore(HSTRING__ *,HSTRING__ *,unsigned __int64,ACTIVATEOPTIONSINTERNAL,IInspectable *,_ActivateComponentInfo const *,ActivateByExtensionArgs *,IInspectable *,ActivateType,void *,unsigned __int64 *,ulong *,IInspectable * *)
0x18006d021  mov     ebx, eax
0x18006d023  test    eax, eax
0x18006d025  jns     loc_18006CF70
0x18006d02b  mov     edx, 328h
0x18006d030  jmp     loc_18006CF3A
```
