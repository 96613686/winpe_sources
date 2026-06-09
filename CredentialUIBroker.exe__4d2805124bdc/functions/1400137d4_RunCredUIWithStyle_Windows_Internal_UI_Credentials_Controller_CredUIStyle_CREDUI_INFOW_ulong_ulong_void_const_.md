# RunCredUIWithStyle(Windows::Internal::UI::Credentials::Controller::CredUIStyle,_CREDUI_INFOW *,ulong,ulong *,void const *,ulong,void * *,ulong *,int *,ulong,unsigned __int64,ulong *)

- ea: `0x1400137d4`
- end: `0x140013add`
- name: `?RunCredUIWithStyle@@YAJW4CredUIStyle@Controller@Credentials@UI@Internal@Windows@@PEAU_CREDUI_INFOW@@KPEAKPEBXKPEAPEAX2PEAHK_K2@Z`
- size: `777`
- prototype: `__int64 __fastcall(unsigned int, struct _CREDUI_INFOW *, unsigned int, __int64, int, __int64, __int64, __int64, __int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000ec00`

## callees

- `0x140003620`
- `0x1400042c4`
- `0x140006f00`
- `0x140008bb8`
- `0x14000abf8`
- `0x14000ad2c`
- `0x14000b47c`
- `0x14001096c`
- `0x1400115c4`
- `0x1400136fc`
- `0x1400137d4`
- `0x140016a54`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x14001383d`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x14001383d`

## string_xrefs

- `0x140013978`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x140013850`: `shellcommon\internal\shell\inc\CredUIApiCommon.h`
- `0x1400138c8`: `shellcommon\internal\shell\inc\CredUIApiCommon.h`
- `0x14001399b`: `shellcommon\internal\shell\inc\CredUIApiCommon.h`

## pseudocode

```c
__int64 __fastcall RunCredUIWithStyle(
        unsigned int a1,
        struct _CREDUI_INFOW *a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        _DWORD *a12)
{
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  void *v18; // rcx
  __int64 v19; // rdx
  void *v20; // rcx
  void *v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  unsigned __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  int v30; // [rsp+20h] [rbp-F0h]
  __int64 v31; // [rsp+90h] [rbp-80h] BYREF
  _BYTE v32[4]; // [rsp+98h] [rbp-78h] BYREF
  int v33; // [rsp+9Ch] [rbp-74h] BYREF
  int v34; // [rsp+A0h] [rbp-70h] BYREF
  int v35; // [rsp+A4h] [rbp-6Ch] BYREF
  unsigned int v36; // [rsp+A8h] [rbp-68h]
  __int64 v37; // [rsp+B0h] [rbp-60h]
  __int64 v38; // [rsp+B8h] [rbp-58h]
  _BYTE v39[144]; // [rsp+C0h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+150h] [rbp+40h] BYREF
  __int64 v41; // [rsp+168h] [rbp+58h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+B8h]

  v38 = a8;
  v36 = a1;
  v37 = a9;
  *a12 = 31;
  v15 = RoInitialize(1);
  v16 = v15;
  if ( v15 >= 0 )
  {
    wil::ScopeExit__lambda_c1ab7529d7e92a365307d2ca98424221___(v32);
    memset_0(v39, 0, 0x88u);
    v17 = ConvertCredUiInfoToInternal(a2, v36 != 0, (struct CREDUI_INFO_INTERNAL *)v39);
    v16 = v17;
    if ( v17 < 0 )
    {
      v19 = 417;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\CredUIApiCommon.h",
        (const char *)(unsigned int)v17,
        v30);
LABEL_24:
      wil::details::ScopeExitFn__lambda_c1ab7529d7e92a365307d2ca98424221___::_ScopeExitFn__lambda_c1ab7529d7e92a365307d2ca98424221___(v32);
      return v16;
    }
    v33 = 0;
    v17 = CheckTokenMembershipSubAuthority0(v18, 0x13u, &v33);
    v16 = v17;
    if ( v17 < 0 )
    {
      v19 = 420;
      goto LABEL_7;
    }
    v34 = 0;
    v17 = CheckTokenMembershipSubAuthority0(v20, 0x12u, &v34);
    v16 = v17;
    if ( v17 < 0 )
    {
      v19 = 423;
      goto LABEL_7;
    }
    v35 = 0;
    v17 = CheckTokenMembershipSubAuthority0(v21, 0x14u, &v35);
    v16 = v17;
    if ( v17 < 0 )
    {
      v19 = 426;
      goto LABEL_7;
    }
    if ( v33 || v34 || v35 )
    {
      v30 = a5;
      v17 = PromptLocalServiceWithStyle(v22, v39, a3, a4);
      v16 = v17;
      if ( v17 < 0 )
      {
        v19 = 430;
        goto LABEL_7;
      }
    }
    else
    {
      v31 = 0;
      v41 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.Shell.CredUX",
        0x1Eu,
        0x1Du);
      v23 = Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
              v41,
              0,
              &GUID_67078ac7_61f1_4621_b0bb_8ccb832d9727,
              &v31);
      v16 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x299,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)v23,
          v30);
        v24 = v16;
        v25 = 435;
        goto LABEL_17;
      }
      v27 = PromptAndWaitForCredsWithStyle(v31, v36);
      v16 = v27;
      if ( v27 < 0 )
      {
        v24 = (unsigned int)v27;
        v25 = 437;
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"shellcommon\\internal\\shell\\inc\\CredUIApiCommon.h",
          (const char *)v24,
          v30);
        v26 = v31;
        if ( v31 )
        {
          v31 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        goto LABEL_24;
      }
      v28 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
    }
    v16 = 0;
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19A,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\CredUIApiCommon.h",
    (const char *)(unsigned int)v15,
    v30);
  return v16;
}

```

## disassembly

```asm
0x1400137d4  push    rbp
0x1400137d6  push    rbx
0x1400137d7  push    rsi
0x1400137d8  push    rdi
0x1400137d9  push    r12
0x1400137db  push    r13
0x1400137dd  push    r14
0x1400137df  push    r15
0x1400137e1  lea     rbp, [rsp-78h]
0x1400137e6  sub     rsp, 188h
0x1400137ed  mov     rax, cs:__security_cookie
0x1400137f4  xor     rax, rsp
0x1400137f7  mov     [rbp+0B0h+var_50], rax
0x1400137fb  mov     rax, [rbp+0B0h+arg_38]
0x140013802  mov     r15, r9
0x140013805  mov     rdi, [rbp+0B0h+arg_58]
0x14001380c  mov     r14d, r8d
0x14001380f  mov     r12, [rbp+0B0h+arg_20]
0x140013816  mov     rsi, rdx
0x140013819  mov     r13, [rbp+0B0h+arg_30]
0x140013820  mov     [rbp+0B0h+var_108], rax
0x140013824  mov     rax, [rbp+0B0h+arg_40]
0x14001382b  mov     [rbp+0B0h+var_118], ecx
0x14001382e  mov     ecx, 1
0x140013833  mov     [rbp+0B0h+var_110], rax
0x140013837  mov     dword ptr [rdi], 1Fh
0x14001383d  call    cs:__imp_RoInitialize
0x140013843  mov     ebx, eax
0x140013845  test    eax, eax
0x140013847  jns     short loc_140013869
0x140013849  mov     rcx, [rbp+0B8h]; this
0x140013850  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Cred"...
0x140013857  mov     r9d, eax; char *
0x14001385a  mov     edx, 19Ah; void *
0x14001385f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013864  jmp     loc_140013A57
0x140013869  lea     rcx, [rbp+0B0h+var_128]
0x14001386d  call    wil__ScopeExit__lambda_c1ab7529d7e92a365307d2ca98424221___
0x140013872  xor     edx, edx; Val
0x140013874  lea     rcx, [rbp+0B0h+var_100]; void *
0x140013878  mov     r8d, 88h; Size
0x14001387e  call    memset_0
0x140013883  cmp     [rbp+0B0h+var_118], 0
0x140013887  lea     r8, [rbp+0B0h+var_100]; struct CREDUI_INFO_INTERNAL *
0x14001388b  mov     rcx, rsi; struct _CREDUI_INFOW *
0x14001388e  setnz   dl; bool
0x140013891  call    ?ConvertCredUiInfoToInternal@@YAJPEAU_CREDUI_INFOW@@_NPEAUCREDUI_INFO_INTERNAL@@@Z; ConvertCredUiInfoToInternal(_CREDUI_INFOW *,bool,CREDUI_INFO_INTERNAL *)
0x140013896  xor     esi, esi
0x140013898  mov     ebx, eax
0x14001389a  test    eax, eax
0x14001389c  jns     short loc_1400138A5
0x14001389e  mov     edx, 1A1h
0x1400138a3  jmp     short loc_1400138C1
0x1400138a5  lea     r8, [rbp+0B0h+var_124]; int *
0x1400138a9  mov     [rbp+0B0h+var_124], esi
0x1400138ac  mov     edx, 13h; unsigned int
0x1400138b1  call    ?CheckTokenMembershipSubAuthority0@@YAJPEAXKPEAH@Z; CheckTokenMembershipSubAuthority0(void *,ulong,int *)
0x1400138b6  mov     ebx, eax
0x1400138b8  test    eax, eax
0x1400138ba  jns     short loc_1400138DC
0x1400138bc  mov     edx, 1A4h; void *
0x1400138c1  mov     rcx, [rbp+0B8h]; this
0x1400138c8  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Cred"...
0x1400138cf  mov     r9d, eax; char *
0x1400138d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400138d7  jmp     loc_140013A4E
0x1400138dc  lea     r8, [rbp+0B0h+var_120]; int *
0x1400138e0  mov     [rbp+0B0h+var_120], esi
0x1400138e3  mov     edx, 12h; unsigned int
0x1400138e8  call    ?CheckTokenMembershipSubAuthority0@@YAJPEAXKPEAH@Z; CheckTokenMembershipSubAuthority0(void *,ulong,int *)
0x1400138ed  mov     ebx, eax
0x1400138ef  test    eax, eax
0x1400138f1  jns     short loc_1400138FA
0x1400138f3  mov     edx, 1A7h
0x1400138f8  jmp     short loc_1400138C1
0x1400138fa  lea     r8, [rbp+0B0h+var_11C]; int *
0x1400138fe  mov     [rbp+0B0h+var_11C], esi
0x140013901  mov     edx, 14h; unsigned int
0x140013906  call    ?CheckTokenMembershipSubAuthority0@@YAJPEAXKPEAH@Z; CheckTokenMembershipSubAuthority0(void *,ulong,int *)
0x14001390b  mov     ebx, eax
0x14001390d  test    eax, eax
0x14001390f  jns     short loc_140013918
0x140013911  mov     edx, 1AAh
0x140013916  jmp     short loc_1400138C1
0x140013918  cmp     [rbp+0B0h+var_124], esi
0x14001391b  jnz     loc_140013A79
0x140013921  cmp     [rbp+0B0h+var_120], esi
0x140013924  jnz     loc_140013A79
0x14001392a  cmp     [rbp+0B0h+var_11C], esi
0x14001392d  jnz     loc_140013A79
0x140013933  mov     r9d, 1Dh; unsigned int
0x140013939  mov     [rbp+0B0h+var_130], rsi
0x14001393d  lea     rdx, aWindowsInterna; "Windows.Internal.Shell.CredUX"
0x140013944  mov     [rbp+0B0h+var_58], rsi
0x140013948  lea     rcx, [rbp+0B0h+hstringHeader]; hstringHeader
0x14001394c  lea     r8d, [r9+1]; unsigned int
0x140013950  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140013955  mov     rcx, [rbp+0B0h+var_58]
0x140013959  lea     r9, [rbp+0B0h+var_130]
0x14001395d  lea     r8, _GUID_67078ac7_61f1_4621_b0bb_8ccb832d9727
0x140013964  mov     edx, esi
0x140013966  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x14001396b  mov     ebx, eax
0x14001396d  test    eax, eax
0x14001396f  jns     short loc_1400139C9
0x140013971  mov     rcx, [rbp+0B8h]; this
0x140013978  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x14001397f  mov     r9d, eax; char *
0x140013982  mov     edx, 299h; void *
0x140013987  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001398c  mov     r9d, ebx; char *
0x14001398f  mov     edx, 1B3h; void *
0x140013994  mov     rcx, [rbp+0B8h]; this
0x14001399b  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Cred"...
0x1400139a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400139a7  mov     rcx, [rbp+0B0h+var_130]
0x1400139ab  test    rcx, rcx
0x1400139ae  jz      loc_140013A4E
0x1400139b4  mov     [rbp+0B0h+var_130], rsi
0x1400139b8  mov     rax, [rcx]
0x1400139bb  mov     rax, [rax+10h]
0x1400139bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400139c4  jmp     loc_140013A4E
0x1400139c9  mov     eax, [rbp+0B0h+arg_48]
0x1400139cf  mov     edx, [rbp+0B0h+var_118]
0x1400139d2  mov     rcx, [rbp+0B0h+var_130]
0x1400139d6  mov     [rsp+1C0h+var_140], rdi
0x1400139de  mov     [rsp+1C0h+var_148], eax
0x1400139e2  mov     rax, [rbp+0B0h+var_110]
0x1400139e6  mov     [rsp+1C0h+var_150], rax
0x1400139eb  mov     rax, [rbp+0B0h+var_108]
0x1400139ef  mov     [rsp+1C0h+var_158], rax
0x1400139f4  mov     eax, [rbp+0B0h+arg_28]
0x1400139fa  mov     [rsp+1C0h+var_160], r13
0x1400139ff  mov     dword ptr [rsp+1C0h+var_168], eax
0x140013a03  lea     rax, [rbp+0B0h+var_100]
0x140013a07  mov     [rsp+1C0h+var_170], r12
0x140013a0c  mov     [rsp+1C0h+var_178], r15
0x140013a11  mov     dword ptr [rsp+1C0h+var_180], r14d
0x140013a16  mov     [rsp+1C0h+var_188], rax
0x140013a1b  call    ?PromptAndWaitForCredsWithStyle@@YAJPEAUICredUX@PlatformExtensions@Shell@Internal@Windows@@W4CredUIStyle@Controller@Credentials@UI@45@PEAUICredUXExtension@78945@PEAUIConsentUXContext@78945@PEAUICredUXSecurePrompt@78945@KPEBU_CREDUI_CONTEXT@@PEAUCREDUI_INFO_INTERNAL@@KPEAKPEBXKPEAPEAX7PEAHK7@Z; PromptAndWaitForCredsWithStyle(Windows::Internal::Shell::PlatformExtensions::ICredUX *,Windows::Internal::UI::Credentials::Controller::CredUIStyle,Windows::Internal::UI::Credentials::Controller::ICredUXExtension *,Windows::Internal::UI::Credentials::Controller::IConsentUXContext *,Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt *,ulong,_CREDUI_CONTEXT const *,CREDUI_INFO_INTERNAL *,ulong,ulong *,void const *,ulong,void * *,ulong *,int *,ulong,ulong *)
0x140013a20  mov     ebx, eax
0x140013a22  test    eax, eax
0x140013a24  jns     short loc_140013A33
0x140013a26  mov     r9d, eax
0x140013a29  mov     edx, 1B5h
0x140013a2e  jmp     loc_140013994
0x140013a33  mov     rcx, [rbp+0B0h+var_130]
0x140013a37  test    rcx, rcx
0x140013a3a  jz      short loc_140013A4C
0x140013a3c  mov     [rbp+0B0h+var_130], rsi
0x140013a40  mov     rax, [rcx]
0x140013a43  mov     rax, [rax+10h]
0x140013a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013a4c  mov     ebx, esi
0x140013a4e  lea     rcx, [rbp+0B0h+var_128]
0x140013a52  call    wil__details__ScopeExitFn__lambda_c1ab7529d7e92a365307d2ca98424221______ScopeExitFn__lambda_c1ab7529d7e92a365307d2ca98424221___
0x140013a57  mov     eax, ebx
0x140013a59  mov     rcx, [rbp+0B0h+var_50]
0x140013a5d  xor     rcx, rsp; StackCookie
0x140013a60  call    __security_check_cookie
0x140013a65  add     rsp, 188h
0x140013a6c  pop     r15
0x140013a6e  pop     r14
0x140013a70  pop     r13
0x140013a72  pop     r12
0x140013a74  pop     rdi
0x140013a75  pop     rsi
0x140013a76  pop     rbx
0x140013a77  pop     rbp
0x140013a78  retn
0x140013a79  mov     rax, [rbp+0B0h+arg_50]
0x140013a80  lea     rdx, [rbp+0B0h+var_100]
0x140013a84  mov     [rsp+1C0h+var_168], rdi
0x140013a89  mov     r9, r15
0x140013a8c  mov     [rsp+1C0h+var_170], rax
0x140013a91  mov     r8d, r14d
0x140013a94  mov     eax, [rbp+0B0h+arg_48]
0x140013a9a  mov     dword ptr [rsp+1C0h+var_178], eax
0x140013a9e  mov     rax, [rbp+0B0h+var_110]
0x140013aa2  mov     [rsp+1C0h+var_180], rax
0x140013aa7  mov     rax, [rbp+0B0h+var_108]
0x140013aab  mov     [rsp+1C0h+var_188], rax
0x140013ab0  mov     eax, [rbp+0B0h+arg_28]
0x140013ab6  mov     [rsp+1C0h+var_190], r13
0x140013abb  mov     [rsp+1C0h+var_198], eax
0x140013abf  mov     [rsp+1C0h+var_1A0], r12
0x140013ac4  call    ?PromptLocalServiceWithStyle@@YAJW4CREDUI_STYLE@@PEAUCREDUI_INFO_INTERNAL@@KPEAKPEBXKPEAPEAX2PEAHK_K2@Z; PromptLocalServiceWithStyle(CREDUI_STYLE,CREDUI_INFO_INTERNAL *,ulong,ulong *,void const *,ulong,void * *,ulong *,int *,ulong,unsigned __int64,ulong *)
0x140013ac9  mov     ebx, eax
0x140013acb  test    eax, eax
0x140013acd  jns     loc_140013A4C
0x140013ad3  mov     edx, 1AEh
0x140013ad8  jmp     loc_1400138C1
```
