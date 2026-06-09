# Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(uchar,uchar,uchar,uchar,void *,ulong)

- ea: `0x1800031fc`
- end: `0x1800034fe`
- name: `??$Initialize@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z`
- size: `770`
- prototype: `__int64 __fastcall(Windows::Internal::ServiceModuleBase *this, char, char, __int64, char, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180004610`

## callees

- `0x1800031fc`
- `0x180003504`
- `0x180006214`
- `0x180006444`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800032ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000345f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800032ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000345f`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180003226`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180003226`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800033f0`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800033f0`

## string_xrefs

- `0x18000323c`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180003279`: `onecore\internal\com\inc\comservicehelper.h`
- `0x1800032cd`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180003331`: `onecore\internal\com\inc\comservicehelper.h`
- `0x1800033a9`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180003403`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180003472`: `onecore\internal\com\inc\comservicehelper.h`
- `0x1800034cf`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(
        Windows::Internal::ServiceModuleBase *this,
        char a2,
        char a3,
        __int64 a4,
        char a5,
        __int64 a6)
{
  int v9; // eax
  unsigned int v10; // edi
  int v12; // eax
  HRESULT v13; // eax
  LPVOID v14; // rcx
  int v15; // eax
  LPVOID v16; // rcx
  LPVOID v17; // rcx
  int v18; // eax
  int v19; // eax
  _QWORD *v20; // rdi
  __int64 v21; // rcx
  HRESULT Instance; // eax
  unsigned int v23; // esi
  int v24; // eax
  int ppv; // [rsp+20h] [rbp-38h]
  int ppva; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  LPVOID v28; // [rsp+90h] [rbp+38h] BYREF

  v9 = RoInitialize(1);
  v10 = v9;
  *((_DWORD *)this + 4) = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v9,
      ppv);
    Windows::Internal::ServiceModuleBase::Uninitialize(this);
    return v10;
  }
  if ( a2 )
  {
    v12 = Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>();
    v10 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v12,
        ppv);
      Windows::Internal::ServiceModuleBase::Uninitialize(this);
      return v10;
    }
    v28 = 0;
    v13 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v28);
    v10 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v13,
        ppv);
      v14 = v28;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
      }
LABEL_10:
      Windows::Internal::ServiceModuleBase::Uninitialize(this);
      return v10;
    }
    v15 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v28 + 24LL))(v28, 1, 2);
    v10 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v15,
        ppv);
      v16 = v28;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
      }
      goto LABEL_10;
    }
    v17 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  v18 = (*(__int64 (__fastcall **)(Windows::Internal::ServiceModuleBase *))(*(_QWORD *)this + 32LL))(this);
  v10 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v18,
      ppv);
    Windows::Internal::ServiceModuleBase::Uninitialize(this);
    return v10;
  }
  if ( a3 )
  {
    (*(void (__fastcall **)(Windows::Internal::ServiceModuleBase *))(*(_QWORD *)this + 16LL))(this);
    *((_BYTE *)this + 20) = 1;
  }
  if ( a5 )
  {
    v19 = CoRegisterServerShutdownDelay(a6, 30000);
    v10 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v19,
        ppv);
      Windows::Internal::ServiceModuleBase::Uninitialize(this);
      return v10;
    }
    *((_BYTE *)this + 21) = 1;
  }
  v20 = (_QWORD *)((char *)this + 24);
  v21 = *((_QWORD *)this + 3);
  if ( v21 )
  {
    *v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  Instance = CoCreateInstance(
               &CLSID_ContextSwitcher,
               0,
               1u,
               &GUID_000001da_0000_0000_c000_000000000046,
               (LPVOID *)this + 3);
  v23 = Instance;
  if ( Instance >= 0 )
  {
    v24 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(struct tagComCallData *), Windows::Internal::ServiceModuleBase *, GUID *))(*(_QWORD *)*v20 + 24LL))(
            *v20,
            Windows::Internal::ServiceModuleBase::ConnectCallbackThunk,
            this,
            &IID_IContextCallback);
    v10 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v24,
        5);
      Windows::Internal::ServiceModuleBase::Uninitialize(this);
      return v10;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)Instance,
      ppva);
    Windows::Internal::ServiceModuleBase::Uninitialize(this);
    return v23;
  }
}

```

## disassembly

```asm
0x1800031fc  push    rbp
0x1800031fe  push    rbx
0x1800031ff  push    rsi
0x180003200  push    rdi
0x180003201  push    r12
0x180003203  push    r14
0x180003205  mov     rbp, rsp
0x180003208  sub     rsp, 58h
0x18000320c  mov     r14b, r8b
0x18000320f  mov     sil, dl
0x180003212  mov     rbx, rcx
0x180003215  mov     [rbp+var_18], rcx
0x180003219  mov     r12d, 1
0x18000321f  mov     [rbp+var_10], r12b
0x180003223  mov     ecx, r12d
0x180003226  call    cs:__imp_RoInitialize
0x18000322c  mov     edi, eax
0x18000322e  mov     [rbx+10h], eax
0x180003231  test    eax, eax
0x180003233  jns     short loc_18000325E
0x180003235  mov     rcx, [rbp+30h]; this
0x180003239  mov     r9d, eax; char *
0x18000323c  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180003243  lea     edx, [r12+62h]; void *
0x180003248  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000324d  nop
0x18000324e  mov     rcx, rbx; this
0x180003251  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180003256  nop
0x180003257  mov     eax, edi
0x180003259  jmp     loc_1800034F1
0x18000325e  test    sil, sil
0x180003261  jz      loc_18000338D
0x180003267  call    ??$InitializeSecurity@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@@ServiceModuleBase@Internal@Windows@@IEAAJXZ; Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>(void)
0x18000326c  mov     edi, eax
0x18000326e  test    eax, eax
0x180003270  jns     short loc_180003296
0x180003272  mov     rcx, [rbp+30h]; this
0x180003276  mov     r9d, eax; char *
0x180003279  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180003280  mov     edx, 6Ch ; 'l'; void *
0x180003285  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000328a  nop
0x18000328b  mov     rcx, rbx; this
0x18000328e  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180003293  nop
0x180003294  jmp     short loc_180003257
0x180003296  mov     [rbp+arg_0], 0
0x18000329e  lea     rax, [rbp+arg_0]
0x1800032a2  mov     [rsp+58h+ppv], rax; int
0x1800032a7  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800032ae  mov     r8d, r12d; dwClsContext
0x1800032b1  xor     edx, edx; pUnkOuter
0x1800032b3  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800032ba  call    cs:__imp_CoCreateInstance
0x1800032c0  mov     edi, eax
0x1800032c2  test    eax, eax
0x1800032c4  jns     short loc_18000330B
0x1800032c6  mov     rcx, [rbp+30h]; this
0x1800032ca  mov     r9d, eax; char *
0x1800032cd  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x1800032d4  mov     edx, 73h ; 's'; void *
0x1800032d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800032de  nop
0x1800032df  mov     rcx, [rbp+arg_0]
0x1800032e3  test    rcx, rcx
0x1800032e6  jz      short loc_1800032FD
0x1800032e8  mov     [rbp+arg_0], 0
0x1800032f0  mov     rax, [rcx]
0x1800032f3  mov     rax, [rax+10h]
0x1800032f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032fc  nop
0x1800032fd  mov     rcx, rbx; this
0x180003300  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180003305  nop
0x180003306  jmp     loc_180003257
0x18000330b  mov     rcx, [rbp+arg_0]
0x18000330f  mov     rax, [rcx]
0x180003312  mov     r8d, 2
0x180003318  mov     edx, r12d
0x18000331b  mov     rax, [rax+18h]
0x18000331f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003324  mov     edi, eax
0x180003326  test    eax, eax
0x180003328  jns     short loc_18000336F
0x18000332a  mov     rcx, [rbp+30h]; this
0x18000332e  mov     r9d, eax; char *
0x180003331  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180003338  mov     edx, 74h ; 't'; void *
0x18000333d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003342  nop
0x180003343  mov     rcx, [rbp+arg_0]
0x180003347  test    rcx, rcx
0x18000334a  jz      short loc_180003361
0x18000334c  mov     [rbp+arg_0], 0
0x180003354  mov     rax, [rcx]
0x180003357  mov     rax, [rax+10h]
0x18000335b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003360  nop
0x180003361  mov     rcx, rbx; this
0x180003364  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180003369  nop
0x18000336a  jmp     loc_180003257
0x18000336f  mov     rcx, [rbp+arg_0]
0x180003373  test    rcx, rcx
0x180003376  jz      short loc_18000338D
0x180003378  mov     [rbp+arg_0], 0
0x180003380  mov     rax, [rcx]
0x180003383  mov     rax, [rax+10h]
0x180003387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000338c  nop
0x18000338d  mov     rax, [rbx]
0x180003390  mov     rcx, rbx
0x180003393  mov     rax, [rax+20h]
0x180003397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000339c  mov     edi, eax
0x18000339e  test    eax, eax
0x1800033a0  jns     short loc_1800033C9
0x1800033a2  mov     rcx, [rbp+30h]; this
0x1800033a6  mov     r9d, eax; char *
0x1800033a9  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x1800033b0  mov     edx, 7Bh ; '{'; void *
0x1800033b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800033ba  nop
0x1800033bb  mov     rcx, rbx; this
0x1800033be  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x1800033c3  nop
0x1800033c4  jmp     loc_180003257
0x1800033c9  test    r14b, r14b
0x1800033cc  jz      short loc_1800033E1
0x1800033ce  mov     rax, [rbx]
0x1800033d1  mov     rcx, rbx
0x1800033d4  mov     rax, [rax+10h]
0x1800033d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033dd  mov     [rbx+14h], r12b
0x1800033e1  cmp     [rbp+arg_20], 0
0x1800033e5  jz      short loc_180003427
0x1800033e7  mov     edx, 7530h
0x1800033ec  mov     rcx, [rbp+arg_28]
0x1800033f0  call    cs:__imp_CoRegisterServerShutdownDelay
0x1800033f6  mov     edi, eax
0x1800033f8  test    eax, eax
0x1800033fa  jns     short loc_180003423
0x1800033fc  mov     rcx, [rbp+30h]; this
0x180003400  mov     r9d, eax; char *
0x180003403  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x18000340a  mov     edx, 89h; void *
0x18000340f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003414  nop
0x180003415  mov     rcx, rbx; this
0x180003418  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18000341d  nop
0x18000341e  jmp     loc_180003257
0x180003423  mov     [rbx+15h], r12b
0x180003427  lea     rdi, [rbx+18h]
0x18000342b  mov     rcx, [rdi]
0x18000342e  test    rcx, rcx
0x180003431  jz      short loc_180003447
0x180003433  mov     qword ptr [rdi], 0
0x18000343a  mov     rax, [rcx]
0x18000343d  mov     rax, [rax+10h]
0x180003441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003446  nop
0x180003447  mov     [rsp+58h+ppv], rdi; int
0x18000344c  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x180003453  mov     r8d, r12d; dwClsContext
0x180003456  xor     edx, edx; pUnkOuter
0x180003458  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18000345f  call    cs:__imp_CoCreateInstance
0x180003465  mov     esi, eax
0x180003467  test    eax, eax
0x180003469  jns     short loc_180003491
0x18000346b  mov     rcx, [rbp+30h]; this
0x18000346f  mov     r9d, eax; char *
0x180003472  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180003479  mov     edx, 8Dh; void *
0x18000347e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003483  nop
0x180003484  mov     rcx, rbx; this
0x180003487  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18000348c  nop
0x18000348d  mov     eax, esi
0x18000348f  jmp     short loc_1800034F1
0x180003491  mov     rcx, [rdi]
0x180003494  mov     rax, [rcx]
0x180003497  mov     [rsp+58h+var_30], 0
0x1800034a0  mov     dword ptr [rsp+58h+ppv], 5; int
0x1800034a8  lea     r9, IID_IContextCallback
0x1800034af  mov     r8, rbx
0x1800034b2  lea     rdx, ?ConnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::ConnectCallbackThunk(tagComCallData *)
0x1800034b9  mov     rax, [rax+18h]
0x1800034bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034c2  mov     edi, eax
0x1800034c4  test    eax, eax
0x1800034c6  jns     short loc_1800034EF
0x1800034c8  mov     rcx, [rbp+30h]; this
0x1800034cc  mov     r9d, eax; char *
0x1800034cf  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x1800034d6  mov     edx, 90h; void *
0x1800034db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800034e0  nop
0x1800034e1  mov     rcx, rbx; this
0x1800034e4  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x1800034e9  nop
0x1800034ea  jmp     loc_180003257
0x1800034ef  xor     eax, eax
0x1800034f1  add     rsp, 58h
0x1800034f5  pop     r14
0x1800034f7  pop     r12
0x1800034f9  pop     rdi
0x1800034fa  pop     rsi
0x1800034fb  pop     rbx
0x1800034fc  pop     rbp
0x1800034fd  retn
```
