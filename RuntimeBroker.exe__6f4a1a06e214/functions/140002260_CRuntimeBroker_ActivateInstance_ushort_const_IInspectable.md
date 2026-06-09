# CRuntimeBroker::ActivateInstance(ushort const *,IInspectable * *)

- ea: `0x140002260`
- end: `0x140002588`
- name: `?ActivateInstance@CRuntimeBroker@@UEAAJPEBGPEAPEAUIInspectable@@@Z`
- size: `808`
- prototype: `int(CRuntimeBroker *__hidden this, const unsigned __int16 *, struct IInspectable **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140002260`
- `0x1400027ac`
- `0x1400027d0`
- `0x140002d70`
- `0x1400050b0`
- `0x140006b10`
- `0x140008c80`
- `0x14000cdc8`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x14000245d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1400024b9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x14000245d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1400024b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1400022e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1400022e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400022ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002415`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002551`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400022ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002415`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002551`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000235d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000235d`
- `combase!__imp_CoGetCallContextOfObject` at `0x140002383`
- `combase!__imp_CoGetCallContextOfObject` at `0x140002383`

## string_xrefs

- `0x1400022f6`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`
- `0x140002467`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`
- `0x1400024c3`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`
- `0x1400024e8`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`
- `0x140002530`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`
- `0x140002562`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`
- `0x140002511`: `onecore\com\combase\inc\IndirectCallTarget.hpp`
- `0x14000242c`: `activatableClassId`
- `0x140002488`: `activatableClassId`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::ActivateInstance(
        CRuntimeBroker *this,
        const unsigned __int16 *a2,
        struct IInspectable **a3)
{
  unsigned __int64 v6; // rbx
  HRESULT v7; // ebx
  __int64 v8; // rdx
  int ActivationFactory; // eax
  unsigned int v11; // edi
  __int64 v12; // rdi
  int v13; // ebx
  struct IIndirectCallTarget *v14; // rbx
  int v15; // eax
  __int64 v16; // rdx
  int v17; // [rsp+20h] [rbp-60h]
  int v18; // [rsp+20h] [rbp-60h]
  struct IIndirectCallTarget *v19; // [rsp+30h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-48h] BYREF
  __int64 v21; // [rsp+40h] [rbp-40h] BYREF
  __int128 v22; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v23[22]; // [rsp+58h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  LODWORD(v19) = 0;
  *a3 = 0;
  if ( !a2 )
  {
    v22 = *(_OWORD *)L"activatableClassId";
    *(_OWORD *)v23 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v23[14] = *(_QWORD *)L"sId";
    RoOriginateErrorW(2147942487LL, 18, &v22);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x283,
      (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
      (const char *)0x80070057LL,
      v17);
    return 2147942487LL;
  }
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( v6 > 0xFFFFFFFF )
  {
    v22 = *(_OWORD *)L"activatableClassId";
    *(_OWORD *)v23 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v23[14] = *(_QWORD *)L"sId";
    RoOriginateErrorW(2147942487LL, 18, &v22);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28B,
      (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
      (const char *)0x80070057LL,
      v17);
    return 2147942487LL;
  }
  WindowsDeleteString(0);
  string = 0;
  v7 = WindowsCreateString(a2, v6, &string);
  if ( v7 < 0 )
  {
    v8 = 656;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
      (const char *)(unsigned int)v7,
      v17);
    WindowsDeleteString(string);
    return (unsigned int)v7;
  }
  v7 = CRuntimeBroker::ValidateBrokeredActivationRequest(a2, (enum Windows::Foundation::ThreadingType *)&v19);
  if ( v7 < 0 )
  {
    v8 = 657;
    goto LABEL_7;
  }
  v21 = 0;
  ActivationFactory = RoGetActivationFactory(string, &GUID_00000035_0000_0000_c000_000000000046, &v21);
  v11 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v12 = v21;
    v19 = 0;
    v13 = CoGetCallContextOfObject(this, &GUID_9937b752_3636_4546_8b25_319e71ce7cbd, &v19);
    if ( v13 < 0 )
    {
      v16 = 23;
    }
    else
    {
      v14 = 0;
      if ( !v19 )
      {
LABEL_14:
        v15 = (*(__int64 (__fastcall **)(__int64, struct IInspectable **))(*(_QWORD *)v21 + 48LL))(v21, a3);
        v11 = v15;
        if ( v15 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2A2,
            (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
            (const char *)(unsigned int)v15,
            v17);
        if ( v14 )
          ClearIndirectCallTarget(v14);
        goto LABEL_18;
      }
      v13 = (*(__int64 (__fastcall **)(struct IIndirectCallTarget *, __int64))(*(_QWORD *)v19 + 32LL))(v19, v12);
      if ( v13 >= 0 )
      {
        v14 = v19;
        v19 = 0;
        goto LABEL_14;
      }
      v16 = 28;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\com\\combase\\inc\\IndirectCallTarget.hpp",
      (const char *)(unsigned int)v13,
      v17);
    wil::com_ptr_t<IActivationFactory,wil::err_returncode_policy>::~com_ptr_t<IActivationFactory,wil::err_returncode_policy>(&v19);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A0,
      (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
      (const char *)(unsigned int)v13,
      v18);
    wil::com_ptr_t<IActivationFactory,wil::err_returncode_policy>::~com_ptr_t<IActivationFactory,wil::err_returncode_policy>(&v21);
    WindowsDeleteString(string);
    return (unsigned int)v13;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x29D,
    (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v17);
LABEL_18:
  CRuntimeBroker::LogActivation(string, &GUID_NULL, v11, 1, v17);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  WindowsDeleteString(string);
  return v11;
}

```

## disassembly

```asm
0x140002260  push    rbp
0x140002262  push    rsi
0x140002263  push    rdi
0x140002264  push    r14
0x140002266  push    r15
0x140002268  mov     rbp, rsp
0x14000226b  sub     rsp, 80h
0x140002272  mov     rax, cs:__security_cookie
0x140002279  xor     rax, rsp
0x14000227c  mov     [rbp+var_10], rax
0x140002280  xor     r15d, r15d
0x140002283  mov     rsi, r8
0x140002286  mov     dword ptr [rbp+var_50], r15d
0x14000228a  mov     rdi, rdx
0x14000228d  mov     [r8], r15
0x140002290  mov     r14, rcx
0x140002293  test    rdx, rdx
0x140002296  jz      loc_14000242C
0x14000229c  mov     [rsp+80h+arg_18], rbx
0x1400022a4  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1400022ab  nop     dword ptr [rax+rax+00h]
0x1400022b0  inc     rbx
0x1400022b3  cmp     [rdx+rbx*2], r15w
0x1400022b8  jnz     short loc_1400022B0
0x1400022ba  mov     eax, 0FFFFFFFFh
0x1400022bf  cmp     rbx, rax
0x1400022c2  ja      loc_140002488
0x1400022c8  xor     ecx, ecx; string
0x1400022ca  mov     [rbp+string], r15
0x1400022ce  call    cs:__imp_WindowsDeleteString
0x1400022d4  mov     edx, ebx; length
0x1400022d6  mov     [rbp+string], r15
0x1400022da  lea     r8, [rbp+string]; string
0x1400022de  mov     rcx, rdi; sourceString
0x1400022e1  call    cs:__imp_WindowsCreateString
0x1400022e7  mov     ebx, eax
0x1400022e9  test    eax, eax
0x1400022eb  jns     short loc_140002334
0x1400022ed  mov     edx, 290h; void *
0x1400022f2  mov     rcx, [rbp+28h]; this
0x1400022f6  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x1400022fd  mov     r9d, ebx; char *
0x140002300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002305  mov     rcx, [rbp+string]; string
0x140002309  call    cs:__imp_WindowsDeleteString
0x14000230f  mov     eax, ebx
0x140002311  mov     rbx, [rsp+80h+arg_18]
0x140002319  mov     rcx, [rbp+var_10]
0x14000231d  xor     rcx, rsp; StackCookie
0x140002320  call    __security_check_cookie
0x140002325  add     rsp, 80h
0x14000232c  pop     r15
0x14000232e  pop     r14
0x140002330  pop     rdi
0x140002331  pop     rsi
0x140002332  pop     rbp
0x140002333  retn
0x140002334  lea     rdx, [rbp+var_50]; enum Windows::Foundation::ThreadingType *
0x140002338  mov     rcx, rdi; sourceString
0x14000233b  call    ?ValidateBrokeredActivationRequest@CRuntimeBroker@@CAJPEBGAEAW4ThreadingType@Foundation@Windows@@@Z; CRuntimeBroker::ValidateBrokeredActivationRequest(ushort const *,Windows::Foundation::ThreadingType &)
0x140002340  mov     ebx, eax
0x140002342  test    eax, eax
0x140002344  js      loc_140002422
0x14000234a  mov     rcx, [rbp+string]
0x14000234e  lea     r8, [rbp+var_40]
0x140002352  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x140002359  mov     [rbp+var_40], r15
0x14000235d  call    cs:__imp_RoGetActivationFactory
0x140002363  mov     edi, eax
0x140002365  test    eax, eax
0x140002367  js      loc_1400024E4
0x14000236d  mov     rdi, [rbp+var_40]
0x140002371  lea     r8, [rbp+var_50]
0x140002375  lea     rdx, _GUID_9937b752_3636_4546_8b25_319e71ce7cbd
0x14000237c  mov     [rbp+var_50], r15
0x140002380  mov     rcx, r14
0x140002383  call    cs:__imp_CoGetCallContextOfObject
0x140002389  mov     ebx, eax
0x14000238b  test    eax, eax
0x14000238d  js      loc_140002501
0x140002393  mov     rcx, [rbp+var_50]
0x140002397  mov     rbx, r15
0x14000239a  test    rcx, rcx
0x14000239d  jz      short loc_1400023C0
0x14000239f  mov     rax, [rcx]
0x1400023a2  mov     rdx, rdi
0x1400023a5  mov     rax, [rax+20h]
0x1400023a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023ae  mov     ebx, eax
0x1400023b0  test    eax, eax
0x1400023b2  js      loc_140002508
0x1400023b8  mov     rbx, [rbp+var_50]
0x1400023bc  mov     [rbp+var_50], r15
0x1400023c0  mov     rcx, [rbp+var_40]
0x1400023c4  mov     rdx, rsi
0x1400023c7  mov     rax, [rcx]
0x1400023ca  mov     rax, [rax+30h]
0x1400023ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023d3  mov     edi, eax
0x1400023d5  test    eax, eax
0x1400023d7  js      loc_14000255E
0x1400023dd  test    rbx, rbx
0x1400023e0  jnz     loc_14000257B
0x1400023e6  mov     rcx, [rbp+string]; HSTRING
0x1400023ea  lea     rdx, GUID_NULL; struct _GUID *
0x1400023f1  mov     r9b, 1; bool
0x1400023f4  mov     r8d, edi; int
0x1400023f7  call    ?LogActivation@CRuntimeBroker@@SAXPEAUHSTRING__@@AEBU_GUID@@J_N2@Z; CRuntimeBroker::LogActivation(HSTRING__ *,_GUID const &,long,bool,bool)
0x1400023fc  mov     rcx, [rbp+var_40]
0x140002400  test    rcx, rcx
0x140002403  jz      short loc_140002411
0x140002405  mov     rax, [rcx]
0x140002408  mov     rax, [rax+10h]
0x14000240c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002411  mov     rcx, [rbp+string]; string
0x140002415  call    cs:__imp_WindowsDeleteString
0x14000241b  mov     eax, edi
0x14000241d  jmp     loc_140002311
0x140002422  mov     edx, 291h
0x140002427  jmp     loc_1400022F2
0x14000242c  movups  xmm0, xmmword ptr cs:aActivatablecla; "activatableClassId"
0x140002433  lea     r8, [rbp+var_38]
0x140002437  mov     edx, 12h
0x14000243c  movups  xmm1, xmmword ptr cs:aActivatablecla+10h; "bleClassId"
0x140002443  mov     ecx, 80070057h
0x140002448  movups  [rbp+var_38], xmm0
0x14000244c  movsd   xmm0, qword ptr cs:aActivatablecla+1Eh; "sId"
0x140002454  movups  xmmword ptr [rbp+var_28], xmm1
0x140002458  movsd   qword ptr [rbp+var_28+0Eh], xmm0
0x14000245d  call    cs:__imp_RoOriginateErrorW
0x140002463  mov     rcx, [rbp+28h]; this
0x140002467  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x14000246e  mov     r9d, 80070057h; char *
0x140002474  mov     edx, 283h; void *
0x140002479  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000247e  mov     eax, 80070057h
0x140002483  jmp     loc_140002319
0x140002488  movups  xmm0, xmmword ptr cs:aActivatablecla; "activatableClassId"
0x14000248f  lea     r8, [rbp+var_38]
0x140002493  mov     edx, 12h
0x140002498  movups  xmm1, xmmword ptr cs:aActivatablecla+10h; "bleClassId"
0x14000249f  mov     ecx, 80070057h
0x1400024a4  movups  [rbp+var_38], xmm0
0x1400024a8  movsd   xmm0, qword ptr cs:aActivatablecla+1Eh; "sId"
0x1400024b0  movups  xmmword ptr [rbp+var_28], xmm1
0x1400024b4  movsd   qword ptr [rbp+var_28+0Eh], xmm0
0x1400024b9  call    cs:__imp_RoOriginateErrorW
0x1400024bf  mov     rcx, [rbp+28h]; this
0x1400024c3  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x1400024ca  mov     r9d, 80070057h; char *
0x1400024d0  mov     edx, 28Bh; void *
0x1400024d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400024da  mov     eax, 80070057h
0x1400024df  jmp     loc_140002311
0x1400024e4  mov     rcx, [rbp+28h]; this
0x1400024e8  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x1400024ef  mov     r9d, eax; char *
0x1400024f2  mov     edx, 29Dh; void *
0x1400024f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400024fc  jmp     loc_1400023E6
0x140002501  mov     edx, 17h
0x140002506  jmp     short loc_14000250D
0x140002508  mov     edx, 1Ch; void *
0x14000250d  mov     rcx, [rbp+28h]; this
0x140002511  lea     r8, aOnecoreComComb; "onecore\\com\\combase\\inc\\IndirectCal"...
0x140002518  mov     r9d, ebx; char *
0x14000251b  lea     rdi, [rbp+var_50]
0x14000251f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002524  mov     rcx, rdi
0x140002527  call    ??1?$com_ptr_t@UIActivationFactory@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IActivationFactory,wil::err_returncode_policy>::~com_ptr_t<IActivationFactory,wil::err_returncode_policy>(void)
0x14000252c  mov     rcx, [rbp+28h]; this
0x140002530  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x140002537  mov     r9d, ebx; char *
0x14000253a  mov     edx, 2A0h; void *
0x14000253f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002544  lea     rcx, [rbp+var_40]
0x140002548  call    ??1?$com_ptr_t@UIActivationFactory@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IActivationFactory,wil::err_returncode_policy>::~com_ptr_t<IActivationFactory,wil::err_returncode_policy>(void)
0x14000254d  mov     rcx, [rbp+string]; string
0x140002551  call    cs:__imp_WindowsDeleteString
0x140002557  mov     eax, ebx
0x140002559  jmp     loc_140002311
0x14000255e  mov     rcx, [rbp+28h]; this
0x140002562  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x140002569  mov     r9d, eax; char *
0x14000256c  mov     edx, 2A2h; void *
0x140002571  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140002576  jmp     loc_1400023DD
0x14000257b  mov     rcx, rbx; struct IIndirectCallTarget *
0x14000257e  call    ?ClearIndirectCallTarget@@YAXPEAUIIndirectCallTarget@@@Z; ClearIndirectCallTarget(IIndirectCallTarget *)
0x140002583  jmp     loc_1400023E6
```
