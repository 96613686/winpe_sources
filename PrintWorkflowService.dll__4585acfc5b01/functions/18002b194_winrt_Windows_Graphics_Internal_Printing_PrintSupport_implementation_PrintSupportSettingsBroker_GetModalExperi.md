# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::GetModalExperienceManager(void)

- ea: `0x18002b194`
- end: `0x18002b303`
- name: `?GetModalExperienceManager@PrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA?AU?$com_ptr@UIModalWindowExperienceManager@ModalExperience@Shell@Internal@Windows@@@8@XZ`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b7c0`

## callees

- `0x180003ca0`
- `0x18000b360`
- `0x1800127a4`
- `0x1800147fc`
- `0x18001da30`
- `0x18002b194`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b2d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b2d8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b229`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b229`

## string_xrefs

- `0x18002b23a`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsettingsbroker.cpp`
- `0x18002b281`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsettingsbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
RTL_SRWLOCK *__fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::GetModalExperienceManager(
        __int64 a1,
        RTL_SRWLOCK *a2)
{
  int ActivationFactory; // eax
  __int64 v5; // rsi
  __int64 (__fastcall *v6)(__int64, __int64); // r14
  int v7; // eax
  __int64 v8; // rcx
  __int64 v10; // [rsp+20h] [rbp-50h] BYREF
  int v11; // [rsp+28h] [rbp-48h]
  PSRWLOCK SRWLock[2]; // [rsp+30h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v14; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  SRWLock[1] = a2;
  a2->Ptr = 0;
  v11 = 1;
  wil::AcquireSRWLockExclusive(SRWLock, a1 + 40);
  if ( !*(_QWORD *)(a1 + 24) )
  {
    v10 = 0;
    v14 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.Shell.ModalExperience.ModalExperienceManager",
      0x3Eu,
      0x3Du);
    ActivationFactory = RoGetActivationFactory(v14, &GUID_9bee8350_74a1_45c1_a90b_f263581b945b, &v10);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x162,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsettingsbroker.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v10);
    v5 = v10;
    v6 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 48LL);
    if ( *(_QWORD *)(a1 + 24) )
      winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(a1 + 24);
    v7 = v6(v5, a1 + 24);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x163,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsettingsbroker.cpp",
        (const char *)(unsigned int)v7,
        v10);
    if ( v10 )
      winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v10);
  }
  if ( a2->Ptr )
    winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(a2);
  v8 = *(_QWORD *)(a1 + 24);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  a2->Ptr = *(PVOID *)(a1 + 24);
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  return a2;
}

```

## disassembly

```asm
0x18002b194  mov     [rsp-18h+arg_10], rbx
0x18002b199  mov     [rsp-18h+arg_18], rsi
0x18002b19e  push    rbp
0x18002b19f  push    rdi
0x18002b1a0  push    r14
0x18002b1a2  mov     rbp, rsp
0x18002b1a5  sub     rsp, 70h
0x18002b1a9  mov     rax, cs:__security_cookie
0x18002b1b0  xor     rax, rsp
0x18002b1b3  mov     [rbp+var_10], rax
0x18002b1b7  mov     rdi, rdx
0x18002b1ba  mov     rbx, rcx
0x18002b1bd  mov     [rbp+var_38], rdx
0x18002b1c1  mov     [rbp+var_48], 0
0x18002b1c8  mov     qword ptr [rdx], 0
0x18002b1cf  mov     [rbp+var_48], 1
0x18002b1d6  lea     rdx, [rcx+28h]
0x18002b1da  lea     rcx, [rbp+SRWLock]
0x18002b1de  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18002b1e3  nop
0x18002b1e4  cmp     qword ptr [rbx+18h], 0
0x18002b1e9  jnz     loc_18002B2A3
0x18002b1ef  mov     [rbp+var_50], 0
0x18002b1f7  mov     [rbp+var_18], 0
0x18002b1ff  mov     r9d, 3Dh ; '='; unsigned int
0x18002b205  lea     r8d, [r9+1]; unsigned int
0x18002b209  lea     rdx, ?RuntimeClass_Windows_Internal_Shell_ModalExperience_ModalExperienceManager@@3QBGB; "Windows.Internal.Shell.ModalExperience."...
0x18002b210  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18002b214  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002b219  nop
0x18002b21a  lea     r8, [rbp+var_50]
0x18002b21e  lea     rdx, _GUID_9bee8350_74a1_45c1_a90b_f263581b945b
0x18002b225  mov     rcx, [rbp+var_18]
0x18002b229  call    cs:__imp_RoGetActivationFactory
0x18002b22f  mov     rcx, [rbp+18h]; this
0x18002b233  test    eax, eax
0x18002b235  jns     short loc_18002B24C
0x18002b237  mov     r9d, eax; char *
0x18002b23a  lea     r8, aOnecoreuapPrin_25; "onecoreuap\\printscan\\print\\workflow"...
0x18002b241  mov     edx, 162h; void *
0x18002b246  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b24c  mov     rsi, [rbp+var_50]
0x18002b250  mov     rax, [rsi]
0x18002b253  mov     r14, [rax+30h]
0x18002b257  cmp     qword ptr [rbx+18h], 0
0x18002b25c  jz      short loc_18002B267
0x18002b25e  lea     rcx, [rbx+18h]
0x18002b262  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18002b267  lea     rdx, [rbx+18h]
0x18002b26b  mov     rcx, rsi
0x18002b26e  mov     rax, r14
0x18002b271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b276  mov     rcx, [rbp+18h]; this
0x18002b27a  test    eax, eax
0x18002b27c  jns     short loc_18002B293
0x18002b27e  mov     r9d, eax; char *
0x18002b281  lea     r8, aOnecoreuapPrin_25; "onecoreuap\\printscan\\print\\workflow"...
0x18002b288  mov     edx, 163h; void *
0x18002b28d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b293  cmp     [rbp+var_50], 0
0x18002b298  jz      short loc_18002B2A3
0x18002b29a  lea     rcx, [rbp+var_50]
0x18002b29e  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18002b2a3  cmp     qword ptr [rdi], 0
0x18002b2a7  jz      short loc_18002B2B2
0x18002b2a9  mov     rcx, rdi
0x18002b2ac  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18002b2b1  nop
0x18002b2b2  mov     rcx, [rbx+18h]
0x18002b2b6  test    rcx, rcx
0x18002b2b9  jz      short loc_18002B2C8
0x18002b2bb  mov     rax, [rcx]
0x18002b2be  mov     rax, [rax+8]
0x18002b2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2c7  nop
0x18002b2c8  mov     rcx, [rbx+18h]
0x18002b2cc  mov     [rdi], rcx
0x18002b2cf  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002b2d3  test    rcx, rcx
0x18002b2d6  jz      short loc_18002B2DE
0x18002b2d8  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b2de  mov     rax, rdi
0x18002b2e1  mov     rcx, [rbp+var_10]
0x18002b2e5  xor     rcx, rsp; StackCookie
0x18002b2e8  call    __security_check_cookie
0x18002b2ed  lea     r11, [rsp+70h+var_s0]
0x18002b2f2  mov     rbx, [r11+30h]
0x18002b2f6  mov     rsi, [r11+38h]
0x18002b2fa  mov     rsp, r11
0x18002b2fd  pop     r14
0x18002b2ff  pop     rdi
0x18002b300  pop     rbp
0x18002b301  retn
```
