# GetWorkflowExtensionForApplication(Windows::Internal::StateRepository::IApplication *,Windows::Internal::StateRepository::IApplicationExtension * *)

- ea: `0x180023378`
- end: `0x18002359a`
- name: `?GetWorkflowExtensionForApplication@@YAJPEAUIApplication@StateRepository@Internal@Windows@@PEAPEAUIApplicationExtension@234@@Z`
- size: `546`
- prototype: `__int64 __fastcall(struct Windows::Internal::StateRepository::IApplication *, struct Windows::Internal::StateRepository::IApplicationExtension **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002220c`

## callees

- `0x180003ca0`
- `0x1800127a4`
- `0x1800147fc`
- `0x18001da30`
- `0x180023378`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800233f0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800233f0`

## string_xrefs

- `0x1800233bd`: `Windows.Internal.StateRepository.ApplicationExtension`
- `0x18002342c`: `Windows.PrintWorkflowBackgroundTask`
- `0x180023549`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x18002355e`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180023573`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180023587`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetWorkflowExtensionForApplication(
        struct Windows::Internal::StateRepository::IApplication *a1,
        struct Windows::Internal::StateRepository::IApplicationExtension **a2)
{
  int ActivationFactory; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, struct Windows::Internal::StateRepository::IApplication *, __int64, __int64 *); // rbx
  int v7; // eax
  int v8; // eax
  const char *v9; // r9
  __int64 result; // rax
  int v11; // eax
  int v12; // [rsp+20h] [rbp-88h]
  int v13; // [rsp+30h] [rbp-78h] BYREF
  __int64 v14; // [rsp+38h] [rbp-70h] BYREF
  __int64 v15; // [rsp+40h] [rbp-68h] BYREF
  HSTRING_HEADER v16; // [rsp+48h] [rbp-60h] BYREF
  __int64 v17; // [rsp+60h] [rbp-48h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-40h] BYREF
  __int64 v19; // [rsp+80h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *a2 = 0;
  v14 = 0;
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v16,
    L"Windows.Internal.StateRepository.ApplicationExtension",
    0x36u,
    0x35u);
  ActivationFactory = RoGetActivationFactory(v17, &GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12, &v14);
  try
  {
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A1,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v12);
    v15 = 0;
    v5 = v14;
    v6 = *(__int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IApplication *, __int64, __int64 *))(*(_QWORD *)v14 + 136LL);
    v19 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.PrintWorkflowBackgroundTask",
      0x24u,
      0x23u);
    v7 = v6(v5, a1, v19, &v15);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)v7,
        v12);
    v13 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 56LL))(v15, &v13);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1AA,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)v8,
        v12);
    if ( v13 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Internal::StateRepository::IApplicationExtension **))(*(_QWORD *)v15 + 48LL))(
              v15,
              0,
              a2);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B2,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
          (const char *)(unsigned int)v11,
          v12);
      if ( v15 )
        winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v15);
      v17 = 0;
      if ( v14 )
        winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v14);
      result = 0;
    }
    else
    {
      if ( v15 )
        winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v15);
      v17 = 0;
      if ( v14 )
        winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v14);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1B6,
                           (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x180023378  mov     r11, rsp
0x18002337b  mov     [r11+18h], rbx
0x18002337f  mov     [r11+20h], rsi
0x180023383  push    rdi
0x180023384  push    r14
0x180023386  push    r15
0x180023388  sub     rsp, 90h
0x18002338f  mov     rax, cs:__security_cookie
0x180023396  xor     rax, rsp
0x180023399  mov     [rsp+0A8h+var_20], rax
0x1800233a1  mov     rsi, rdx
0x1800233a4  mov     r14, rcx
0x1800233a7  xor     r15d, r15d
0x1800233aa  mov     [rdx], r15
0x1800233ad  mov     [r11-70h], r15
0x1800233b1  mov     [r11-48h], r15
0x1800233b5  lea     r9d, [r15+35h]; unsigned int
0x1800233b9  lea     r8d, [r15+36h]; unsigned int
0x1800233bd  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationExtension@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800233c4  lea     rcx, [r11-60h]; hstringHeader
0x1800233c8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800233cd  nop
0x1800233ce  cmp     [rsp+0A8h+var_70], r15
0x1800233d3  jz      short loc_1800233DF
0x1800233d5  lea     rcx, [rsp+0A8h+var_70]
0x1800233da  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x1800233df  lea     r8, [rsp+0A8h+var_70]
0x1800233e4  lea     rdx, _GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12
0x1800233eb  mov     rcx, [rsp+0A8h+var_48]
0x1800233f0  call    cs:__imp_RoGetActivationFactory
0x1800233f6  mov     rcx, [rsp+0A8h]; this
0x1800233fe  test    eax, eax
0x180023400  js      loc_180023546
0x180023406  mov     [rsp+0A8h+var_68], r15
0x18002340b  mov     rdi, [rsp+0A8h+var_70]
0x180023410  mov     rax, [rdi]
0x180023413  mov     rbx, [rax+88h]
0x18002341a  mov     [rsp+0A8h+var_28], r15
0x180023422  mov     r9d, 23h ; '#'; unsigned int
0x180023428  lea     r8d, [r9+1]; unsigned int
0x18002342c  lea     rdx, SourceString; "Windows.PrintWorkflowBackgroundTask"
0x180023433  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x180023438  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002343d  nop
0x18002343e  lea     r9, [rsp+0A8h+var_68]
0x180023443  mov     r8, [rsp+0A8h+var_28]
0x18002344b  mov     rdx, r14
0x18002344e  mov     rcx, rdi
0x180023451  mov     rax, rbx
0x180023454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023459  mov     rcx, [rsp+0A8h]; this
0x180023461  test    eax, eax
0x180023463  js      loc_18002355B
0x180023469  mov     [rsp+0A8h+var_78], r15d
0x18002346e  mov     rcx, [rsp+0A8h+var_68]
0x180023473  mov     rax, [rcx]
0x180023476  lea     rdx, [rsp+0A8h+var_78]
0x18002347b  mov     rax, [rax+38h]
0x18002347f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023484  mov     rcx, [rsp+0A8h]; this
0x18002348c  test    eax, eax
0x18002348e  js      loc_180023570
0x180023494  cmp     [rsp+0A8h+var_78], r15d
0x180023499  jnz     short loc_1800234C7
0x18002349b  cmp     [rsp+0A8h+var_68], r15
0x1800234a0  jz      short loc_1800234AD
0x1800234a2  lea     rcx, [rsp+0A8h+var_68]
0x1800234a7  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x1800234ac  nop
0x1800234ad  mov     [rsp+0A8h+var_48], r15
0x1800234b2  cmp     [rsp+0A8h+var_70], r15
0x1800234b7  jz      short loc_1800234C3
0x1800234b9  lea     rcx, [rsp+0A8h+var_70]
0x1800234be  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x1800234c3  xor     eax, eax
0x1800234c5  jmp     short loc_18002351D
0x1800234c7  mov     rcx, [rsp+0A8h+var_68]
0x1800234cc  mov     rax, [rcx]
0x1800234cf  mov     r8, rsi
0x1800234d2  xor     edx, edx
0x1800234d4  mov     rax, [rax+30h]
0x1800234d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234dd  mov     rcx, [rsp+0A8h]; this
0x1800234e5  test    eax, eax
0x1800234e7  js      loc_180023584
0x1800234ed  cmp     [rsp+0A8h+var_68], r15
0x1800234f2  jz      short loc_1800234FF
0x1800234f4  lea     rcx, [rsp+0A8h+var_68]
0x1800234f9  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x1800234fe  nop
0x1800234ff  mov     [rsp+0A8h+var_48], r15
0x180023504  cmp     [rsp+0A8h+var_70], r15
0x180023509  jz      short loc_180023515
0x18002350b  lea     rcx, [rsp+0A8h+var_70]
0x180023510  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180023515  xor     eax, eax
0x180023517  jmp     short loc_18002351D
0x180023519  mov     eax, [rsp+0A8h+var_78]
0x18002351d  mov     rcx, [rsp+0A8h+var_20]
0x180023525  xor     rcx, rsp; StackCookie
0x180023528  call    __security_check_cookie
0x18002352d  lea     r11, [rsp+0A8h+var_18]
0x180023535  mov     rbx, [r11+30h]
0x180023539  mov     rsi, [r11+38h]
0x18002353d  mov     rsp, r11
0x180023540  pop     r15
0x180023542  pop     r14
0x180023544  pop     rdi
0x180023545  retn
0x180023546  mov     r9d, eax; char *
0x180023549  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180023550  mov     edx, 1A1h; void *
0x180023555  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002355b  mov     r9d, eax; char *
0x18002355e  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180023565  mov     edx, 1A6h; void *
0x18002356a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023570  mov     r9d, eax; char *
0x180023573  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x18002357a  mov     edx, 1AAh; void *
0x18002357f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023584  mov     r9d, eax; char *
0x180023587  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x18002358e  mov     edx, 1B2h; void *
0x180023593  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
