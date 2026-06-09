# Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(uchar,uchar,uchar,uchar,void *,ulong)

- ea: `0x1800023c8`
- end: `0x180002675`
- name: `??$Initialize@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z`
- size: `685`
- prototype: `__int64 __fastcall(Windows::Internal::ServiceModuleBase *this, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180004140`

## callees

- `0x1800023c8`
- `0x18000267c`
- `0x180006804`
- `0x1800077c4`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002487`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800025ce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002487`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800025ce`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800023f4`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800023f4`

## string_xrefs

- `0x18000240a`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180002446`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18000249a`: `onecore\internal\com\inc\comservicehelper.h`
- `0x1800024fe`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180002576`: `onecore\internal\com\inc\comservicehelper.h`
- `0x1800025e1`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18000263e`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(
        Windows::Internal::ServiceModuleBase *this,
        char a2)
{
  int v4; // eax
  unsigned int v5; // edi
  int v7; // eax
  HRESULT v8; // eax
  LPVOID v9; // rcx
  int v10; // eax
  LPVOID v11; // rcx
  LPVOID v12; // rcx
  int v13; // eax
  _QWORD *v14; // rdi
  __int64 v15; // rcx
  HRESULT Instance; // eax
  unsigned int v17; // esi
  int v18; // eax
  int ppv; // [rsp+20h] [rbp-30h]
  int ppva; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  LPVOID v22; // [rsp+70h] [rbp+20h] BYREF

  v4 = RoInitialize(1);
  v5 = v4;
  *((_DWORD *)this + 4) = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v4,
      ppv);
    Windows::Internal::ServiceModuleBase::Uninitialize(this);
    return v5;
  }
  if ( a2 )
  {
    v7 = Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>();
    v5 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v7,
        ppv);
      Windows::Internal::ServiceModuleBase::Uninitialize(this);
      return v5;
    }
    v22 = 0;
    v8 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v22);
    v5 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v8,
        ppv);
      v9 = v22;
      if ( v22 )
      {
        v22 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
      }
LABEL_10:
      Windows::Internal::ServiceModuleBase::Uninitialize(this);
      return v5;
    }
    v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v22 + 24LL))(v22, 1, 2);
    v5 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v10,
        ppv);
      v11 = v22;
      if ( v22 )
      {
        v22 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
      }
      goto LABEL_10;
    }
    v12 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  v13 = (*(__int64 (__fastcall **)(Windows::Internal::ServiceModuleBase *))(*(_QWORD *)this + 32LL))(this);
  v5 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v13,
      ppv);
    Windows::Internal::ServiceModuleBase::Uninitialize(this);
    return v5;
  }
  v14 = (_QWORD *)((char *)this + 24);
  v15 = *((_QWORD *)this + 3);
  if ( v15 )
  {
    *v14 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  Instance = CoCreateInstance(
               &CLSID_ContextSwitcher,
               0,
               1u,
               &GUID_000001da_0000_0000_c000_000000000046,
               (LPVOID *)this + 3);
  v17 = Instance;
  if ( Instance >= 0 )
  {
    v18 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(struct tagComCallData *), Windows::Internal::ServiceModuleBase *, GUID *))(*(_QWORD *)*v14 + 24LL))(
            *v14,
            Windows::Internal::ServiceModuleBase::ConnectCallbackThunk,
            this,
            &IID_IContextCallback);
    v5 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v18,
        5);
      Windows::Internal::ServiceModuleBase::Uninitialize(this);
      return v5;
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
    return v17;
  }
}

```

## disassembly

```asm
0x1800023c8  mov     [rsp-18h+arg_8], rbx
0x1800023cd  mov     [rsp-18h+arg_10], rsi
0x1800023d2  push    rbp
0x1800023d3  push    rdi
0x1800023d4  push    r15
0x1800023d6  mov     rbp, rsp
0x1800023d9  sub     rsp, 50h
0x1800023dd  mov     sil, dl
0x1800023e0  mov     rbx, rcx
0x1800023e3  mov     [rbp+var_10], rcx
0x1800023e7  mov     r15d, 1
0x1800023ed  mov     [rbp+var_8], r15b
0x1800023f1  mov     ecx, r15d
0x1800023f4  call    cs:__imp_RoInitialize
0x1800023fa  mov     edi, eax
0x1800023fc  mov     [rbx+10h], eax
0x1800023ff  test    eax, eax
0x180002401  jns     short loc_18000242B
0x180002403  mov     rcx, [rbp+18h]; this
0x180002407  mov     r9d, eax; char *
0x18000240a  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180002411  lea     edx, [r15+62h]; void *
0x180002415  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000241a  nop
0x18000241b  mov     rcx, rbx; this
0x18000241e  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180002423  nop
0x180002424  mov     eax, edi
0x180002426  jmp     loc_180002660
0x18000242b  test    sil, sil
0x18000242e  jz      loc_18000255A
0x180002434  call    ??$InitializeSecurity@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@@ServiceModuleBase@Internal@Windows@@IEAAJXZ; Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>(void)
0x180002439  mov     edi, eax
0x18000243b  test    eax, eax
0x18000243d  jns     short loc_180002463
0x18000243f  mov     rcx, [rbp+18h]; this
0x180002443  mov     r9d, eax; char *
0x180002446  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x18000244d  mov     edx, 6Ch ; 'l'; void *
0x180002452  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002457  nop
0x180002458  mov     rcx, rbx; this
0x18000245b  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180002460  nop
0x180002461  jmp     short loc_180002424
0x180002463  mov     [rbp+arg_0], 0
0x18000246b  lea     rax, [rbp+arg_0]
0x18000246f  mov     [rsp+50h+ppv], rax; int
0x180002474  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18000247b  mov     r8d, r15d; dwClsContext
0x18000247e  xor     edx, edx; pUnkOuter
0x180002480  lea     rcx, CLSID_GlobalOptions; rclsid
0x180002487  call    cs:__imp_CoCreateInstance
0x18000248d  mov     edi, eax
0x18000248f  test    eax, eax
0x180002491  jns     short loc_1800024D8
0x180002493  mov     rcx, [rbp+18h]; this
0x180002497  mov     r9d, eax; char *
0x18000249a  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x1800024a1  mov     edx, 73h ; 's'; void *
0x1800024a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800024ab  nop
0x1800024ac  mov     rcx, [rbp+arg_0]
0x1800024b0  test    rcx, rcx
0x1800024b3  jz      short loc_1800024CA
0x1800024b5  mov     [rbp+arg_0], 0
0x1800024bd  mov     rax, [rcx]
0x1800024c0  mov     rax, [rax+10h]
0x1800024c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024c9  nop
0x1800024ca  mov     rcx, rbx; this
0x1800024cd  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x1800024d2  nop
0x1800024d3  jmp     loc_180002424
0x1800024d8  mov     rcx, [rbp+arg_0]
0x1800024dc  mov     rax, [rcx]
0x1800024df  mov     r8d, 2
0x1800024e5  mov     edx, r15d
0x1800024e8  mov     rax, [rax+18h]
0x1800024ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024f1  mov     edi, eax
0x1800024f3  test    eax, eax
0x1800024f5  jns     short loc_18000253C
0x1800024f7  mov     rcx, [rbp+18h]; this
0x1800024fb  mov     r9d, eax; char *
0x1800024fe  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180002505  mov     edx, 74h ; 't'; void *
0x18000250a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000250f  nop
0x180002510  mov     rcx, [rbp+arg_0]
0x180002514  test    rcx, rcx
0x180002517  jz      short loc_18000252E
0x180002519  mov     [rbp+arg_0], 0
0x180002521  mov     rax, [rcx]
0x180002524  mov     rax, [rax+10h]
0x180002528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000252d  nop
0x18000252e  mov     rcx, rbx; this
0x180002531  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180002536  nop
0x180002537  jmp     loc_180002424
0x18000253c  mov     rcx, [rbp+arg_0]
0x180002540  test    rcx, rcx
0x180002543  jz      short loc_18000255A
0x180002545  mov     [rbp+arg_0], 0
0x18000254d  mov     rax, [rcx]
0x180002550  mov     rax, [rax+10h]
0x180002554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002559  nop
0x18000255a  mov     rax, [rbx]
0x18000255d  mov     rcx, rbx
0x180002560  mov     rax, [rax+20h]
0x180002564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002569  mov     edi, eax
0x18000256b  test    eax, eax
0x18000256d  jns     short loc_180002596
0x18000256f  mov     rcx, [rbp+18h]; this
0x180002573  mov     r9d, eax; char *
0x180002576  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x18000257d  mov     edx, 7Bh ; '{'; void *
0x180002582  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002587  nop
0x180002588  mov     rcx, rbx; this
0x18000258b  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180002590  nop
0x180002591  jmp     loc_180002424
0x180002596  lea     rdi, [rbx+18h]
0x18000259a  mov     rcx, [rdi]
0x18000259d  test    rcx, rcx
0x1800025a0  jz      short loc_1800025B6
0x1800025a2  mov     qword ptr [rdi], 0
0x1800025a9  mov     rax, [rcx]
0x1800025ac  mov     rax, [rax+10h]
0x1800025b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025b5  nop
0x1800025b6  mov     [rsp+50h+ppv], rdi; int
0x1800025bb  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x1800025c2  mov     r8d, r15d; dwClsContext
0x1800025c5  xor     edx, edx; pUnkOuter
0x1800025c7  lea     rcx, CLSID_ContextSwitcher; rclsid
0x1800025ce  call    cs:__imp_CoCreateInstance
0x1800025d4  mov     esi, eax
0x1800025d6  test    eax, eax
0x1800025d8  jns     short loc_180002600
0x1800025da  mov     rcx, [rbp+18h]; this
0x1800025de  mov     r9d, eax; char *
0x1800025e1  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x1800025e8  mov     edx, 8Dh; void *
0x1800025ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800025f2  nop
0x1800025f3  mov     rcx, rbx; this
0x1800025f6  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x1800025fb  nop
0x1800025fc  mov     eax, esi
0x1800025fe  jmp     short loc_180002660
0x180002600  mov     rcx, [rdi]
0x180002603  mov     rax, [rcx]
0x180002606  mov     [rsp+50h+var_28], 0
0x18000260f  mov     dword ptr [rsp+50h+ppv], 5; int
0x180002617  lea     r9, IID_IContextCallback
0x18000261e  mov     r8, rbx
0x180002621  lea     rdx, ?ConnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::ConnectCallbackThunk(tagComCallData *)
0x180002628  mov     rax, [rax+18h]
0x18000262c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002631  mov     edi, eax
0x180002633  test    eax, eax
0x180002635  jns     short loc_18000265E
0x180002637  mov     rcx, [rbp+18h]; this
0x18000263b  mov     r9d, eax; char *
0x18000263e  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180002645  mov     edx, 90h; void *
0x18000264a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000264f  nop
0x180002650  mov     rcx, rbx; this
0x180002653  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180002658  nop
0x180002659  jmp     loc_180002424
0x18000265e  xor     eax, eax
0x180002660  lea     r11, [rsp+50h+var_s0]
0x180002665  mov     rbx, [r11+28h]
0x180002669  mov     rsi, [r11+30h]
0x18000266d  mov     rsp, r11
0x180002670  pop     r15
0x180002672  pop     rdi
0x180002673  pop     rbp
0x180002674  retn
```
