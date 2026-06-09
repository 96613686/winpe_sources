# AcknowledgeSettingsPayload(void)

- ea: `0x1400120b0`
- end: `0x14001220c`
- name: `?AcknowledgeSettingsPayload@@YAJXZ`
- size: `348`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140007ad8`
- `0x14000b0cc`

## callees

- `0x140002f40`
- `0x140005cac`
- `0x14000a4bc`
- `0x1400120b0`
- `0x140012214`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140012119`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140012119`

## string_xrefs

- `0x14001212c`: `onecore\windows\directx\database\updater\exe\onesettingshelper.cpp`
- `0x14001219e`: `onecore\windows\directx\database\updater\exe\onesettingshelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 AcknowledgeSettingsPayload(void)
{
  int ActivationFactory; // eax
  unsigned int v2; // ebx
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64, __int64 *); // rbx
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // [rsp+20h] [rbp-40h] BYREF
  __int64 v8; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  __int64 v10; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  if ( g_bForceWeekly )
    return 0;
  v8 = 0;
  v10 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload",
    0x3Au,
    0x39u);
  ActivationFactory = RoGetActivationFactory(v10, &GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0, &v8);
  v2 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v7 = 0;
    v3 = v8;
    v4 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v8 + 48LL);
    v7 = 0;
    v10 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"DXDB", 5u, 4u);
    v5 = v4(v3, v10, &v7);
    v2 = v5;
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 112LL))(v7);
      v2 = v5;
      if ( v5 >= 0 )
      {
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v7);
        v2 = 0;
        goto LABEL_11;
      }
      v6 = 160;
    }
    else
    {
      v6 = 156;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\onesettingshelper.cpp",
      (const char *)(unsigned int)v5,
      v7);
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v7);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\onesettingshelper.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v7);
  }
LABEL_11:
  wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v8);
  return v2;
}

```

## disassembly

```asm
0x1400120b0  mov     [rsp-8+arg_0], rbx
0x1400120b5  mov     [rsp-8+arg_8], rdi
0x1400120ba  push    rbp
0x1400120bb  mov     rbp, rsp
0x1400120be  sub     rsp, 60h
0x1400120c2  mov     rax, cs:__security_cookie
0x1400120c9  xor     rax, rsp
0x1400120cc  mov     [rbp+var_10], rax
0x1400120d0  cmp     cs:?g_bForceWeekly@@3_NA, 0; bool g_bForceWeekly
0x1400120d7  jz      short loc_1400120E0
0x1400120d9  xor     eax, eax
0x1400120db  jmp     loc_1400121F0
0x1400120e0  mov     [rbp+var_38], 0
0x1400120e8  mov     [rbp+var_18], 0
0x1400120f0  mov     r9d, 39h ; '9'; unsigned int
0x1400120f6  lea     r8d, [r9+1]; unsigned int
0x1400120fa  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x140012101  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x140012105  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14001210a  lea     r8, [rbp+var_38]
0x14001210e  lea     rdx, _GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0
0x140012115  mov     rcx, [rbp+var_18]
0x140012119  call    cs:__imp_RoGetActivationFactory
0x14001211f  mov     ebx, eax
0x140012121  test    eax, eax
0x140012123  jns     short loc_140012142
0x140012125  mov     rcx, [rbp+8]; this
0x140012129  mov     r9d, eax; char *
0x14001212c  lea     r8, aOnecoreWindows_4; "onecore\\windows\\directx\\database\\up"...
0x140012133  mov     edx, 99h; void *
0x140012138  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001213d  jmp     loc_1400121E5
0x140012142  mov     [rbp+var_40], 0
0x14001214a  mov     rdi, [rbp+var_38]
0x14001214e  mov     rax, [rdi]
0x140012151  mov     rbx, [rax+30h]
0x140012155  mov     [rbp+var_40], 0
0x14001215d  mov     [rbp+var_18], 0
0x140012165  mov     r9d, 4; unsigned int
0x14001216b  lea     r8d, [r9+1]; unsigned int
0x14001216f  lea     rdx, sourceString; "DXDB"
0x140012176  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x14001217a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14001217f  nop
0x140012180  lea     r8, [rbp+var_40]
0x140012184  mov     rdx, [rbp+var_18]
0x140012188  mov     rcx, rdi
0x14001218b  mov     rax, rbx
0x14001218e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012193  mov     ebx, eax
0x140012195  test    eax, eax
0x140012197  jns     short loc_1400121BD
0x140012199  mov     edx, 9Ch; void *
0x14001219e  lea     r8, aOnecoreWindows_4; "onecore\\windows\\directx\\database\\up"...
0x1400121a5  mov     r9d, eax; char *
0x1400121a8  mov     rcx, [rbp+8]; this
0x1400121ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400121b1  nop
0x1400121b2  lea     rcx, [rbp+var_40]
0x1400121b6  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x1400121bb  jmp     short loc_1400121E5
0x1400121bd  mov     rcx, [rbp+var_40]
0x1400121c1  mov     rax, [rcx]
0x1400121c4  mov     rax, [rax+70h]
0x1400121c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400121cd  mov     ebx, eax
0x1400121cf  test    eax, eax
0x1400121d1  jns     short loc_1400121DA
0x1400121d3  mov     edx, 0A0h
0x1400121d8  jmp     short loc_14001219E
0x1400121da  lea     rcx, [rbp+var_40]
0x1400121de  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x1400121e3  xor     ebx, ebx
0x1400121e5  lea     rcx, [rbp+var_38]
0x1400121e9  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x1400121ee  mov     eax, ebx
0x1400121f0  mov     rcx, [rbp+var_10]
0x1400121f4  xor     rcx, rsp; StackCookie
0x1400121f7  call    __security_check_cookie
0x1400121fc  mov     rbx, [rsp+60h+arg_0]
0x140012201  mov     rdi, [rsp+60h+arg_8]
0x140012206  add     rsp, 60h
0x14001220a  pop     rbp
0x14001220b  retn
```
