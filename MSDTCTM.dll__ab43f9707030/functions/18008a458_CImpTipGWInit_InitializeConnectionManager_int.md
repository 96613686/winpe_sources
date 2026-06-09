# CImpTipGWInit::InitializeConnectionManager(int)

- ea: `0x18008a458`
- end: `0x18008a69f`
- name: `?InitializeConnectionManager@CImpTipGWInit@@AEAAJH@Z`
- size: `583`
- prototype: `__int64 __fastcall(CImpTipGWInit *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008a240`

## callees

- `0x1800063b0`
- `0x180009370`
- `0x1800240b0`
- `0x18008a0bc`
- `0x18008a458`
- `0x1800bd010`

## import_xrefs

- `MSDTCPRX!__imp_DllGetDTCConnectionManager` at `0x18008a48d`
- `MSDTCPRX!__imp_DllGetDTCConnectionManager` at `0x18008a48d`

## string_xrefs

- `0x18008a606`: `com\complus\dtc\dtc\tipgw\gwinit\gwinit.cpp`
- `0x18008a653`: `com\complus\dtc\dtc\tipgw\gwinit\gwinit.cpp`
- `0x18008a499`: `failed DllGetDTCConnectionManager`
- `0x18008a4d0`: `failed m_pIConnMgr->QueryInterface(IID_IConnectionManagerConfig)`
- `0x18008a53e`: `failed pIConnMgrConfig->SetProtocols`
- `0x18008a5f4`: `failed pIConnMgrConfig->SetPhaseToPostInit`

## pseudocode

```c
__int64 __fastcall CImpTipGWInit::InitializeConnectionManager(CImpTipGWInit *this, int a2)
{
  _QWORD *v2; // r14
  unsigned int DTCConnectionManager; // ebx
  const wchar_t *v6; // rax
  __int64 v7; // r9
  const unsigned __int16 *v8; // rcx
  CImpInitIConnectionNotify *v9; // rax
  CImpInitIConnectionNotify *inited; // rax
  CImpInitIConnectionNotify *v11; // rdi
  const wchar_t *v12; // rax
  __int64 v13; // r9
  __int64 v15; // [rsp+28h] [rbp-30h]
  CImpInitIConnectionNotify *v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+70h] [rbp+18h] BYREF

  v2 = (_QWORD *)((char *)this + 8);
  v17 = 0;
  DTCConnectionManager = DllGetDTCConnectionManager(&CLSID_DTCCM, &IID_IConnectionManager, (char *)this + 8);
  if ( !DTCConnectionManager )
  {
    DTCConnectionManager = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v2)(
                             *v2,
                             &IID_IConnectionManagerConfig,
                             &v17);
    if ( DTCConnectionManager )
    {
      v6 = L"failed m_pIConnMgr->QueryInterface(IID_IConnectionManagerConfig)";
      v7 = 326;
      goto LABEL_20;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 40LL))(v17, 1);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 72LL))(v17, 1);
    LOBYTE(v16) = 0;
    MtxCluIsClusterPresentNonAdmin(v8, (bool *)&v16);
    if ( !(_BYTE)v16 && !a2 )
    {
      DTCConnectionManager = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 120LL))(v17, 32);
      if ( DTCConnectionManager )
      {
        v6 = L"failed pIConnMgrConfig->SetProtocols";
        v7 = 337;
        goto LABEL_20;
      }
    }
    v9 = (CImpInitIConnectionNotify *)operator new(0x10u);
    v16 = v9;
    if ( !v9 || (inited = CImpInitIConnectionNotify::CImpInitIConnectionNotify(v9), (v11 = inited) == 0) )
    {
      DTCConnectionManager = -2147024882;
      v6 = L"failed new CImpInitIConnectionNotify";
      v7 = 346;
      goto LABEL_20;
    }
    (*(void (__fastcall **)(CImpInitIConnectionNotify *))(*(_QWORD *)inited + 8LL))(inited);
    DTCConnectionManager = (*(__int64 (__fastcall **)(_QWORD, _QWORD, CImpInitIConnectionNotify *, _QWORD))(*(_QWORD *)*v2 + 24LL))(
                             *v2,
                             *((_QWORD *)this + 2),
                             v11,
                             0);
    if ( DTCConnectionManager )
    {
      v12 = L"failed m_pIConnMgr->Init";
      v13 = 356;
    }
    else
    {
      DTCConnectionManager = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 32LL))(*v2);
      if ( DTCConnectionManager )
      {
        v12 = L"failed m_pIConnMgr->StartListening";
        v13 = 364;
      }
      else
      {
        DTCConnectionManager = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17);
        if ( !DTCConnectionManager )
        {
LABEL_18:
          (*(void (__fastcall **)(CImpInitIConnectionNotify *))(*(_QWORD *)v11 + 16LL))(v11);
          goto LABEL_21;
        }
        v12 = L"failed pIConnMgrConfig->SetPhaseToPostInit";
        v13 = 372;
      }
    }
    LODWORD(v15) = DTCConnectionManager;
    TraceStringInline(
      10,
      1,
      L"com\\complus\\dtc\\dtc\\tipgw\\gwinit\\gwinit.cpp",
      v13,
      L"CImpTipGWInit::InitializeConnectionManager",
      v15,
      v12);
    goto LABEL_18;
  }
  v6 = L"failed DllGetDTCConnectionManager";
  v7 = 318;
LABEL_20:
  LODWORD(v15) = DTCConnectionManager;
  TraceStringInline(
    10,
    1,
    L"com\\complus\\dtc\\dtc\\tipgw\\gwinit\\gwinit.cpp",
    v7,
    L"CImpTipGWInit::InitializeConnectionManager",
    v15,
    v6);
LABEL_21:
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return DTCConnectionManager;
}

```

## disassembly

```asm
0x18008a458  mov     [rsp+arg_8], rbx
0x18008a45d  mov     [rsp+arg_18], rbp
0x18008a462  push    rsi
0x18008a463  push    rdi
0x18008a464  push    r14
0x18008a466  sub     rsp, 40h
0x18008a46a  lea     r14, [rcx+8]
0x18008a46e  mov     [rsp+58h+arg_10], 0
0x18008a477  mov     edi, edx
0x18008a479  mov     rbp, rcx
0x18008a47c  mov     r8, r14
0x18008a47f  lea     rdx, IID_IConnectionManager
0x18008a486  lea     rcx, CLSID_DTCCM
0x18008a48d  call    cs:__imp_DllGetDTCConnectionManager
0x18008a493  mov     ebx, eax
0x18008a495  test    eax, eax
0x18008a497  jz      short loc_18008A4B0
0x18008a499  lea     rax, aFailedDllgetdt; "failed DllGetDTCConnectionManager"
0x18008a4a0  mov     r9d, 13Eh
0x18008a4a6  mov     edx, 1
0x18008a4ab  jmp     loc_18008A64E
0x18008a4b0  mov     rcx, [r14]
0x18008a4b3  lea     r8, [rsp+58h+arg_10]
0x18008a4b8  lea     rdx, IID_IConnectionManagerConfig
0x18008a4bf  mov     rax, [rcx]
0x18008a4c2  mov     rax, [rax]
0x18008a4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a4ca  mov     ebx, eax
0x18008a4cc  test    eax, eax
0x18008a4ce  jz      short loc_18008A4DF
0x18008a4d0  lea     rax, aFailedMPiconnm; "failed m_pIConnMgr->QueryInterface(IID_"...
0x18008a4d7  mov     r9d, 146h
0x18008a4dd  jmp     short loc_18008A4A6
0x18008a4df  mov     rcx, [rsp+58h+arg_10]
0x18008a4e4  mov     esi, 1
0x18008a4e9  mov     edx, esi
0x18008a4eb  mov     rax, [rcx]
0x18008a4ee  mov     rax, [rax+28h]
0x18008a4f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a4f7  mov     rcx, [rsp+58h+arg_10]
0x18008a4fc  mov     edx, esi
0x18008a4fe  mov     rax, [rcx]
0x18008a501  mov     rax, [rax+48h]
0x18008a505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a50a  lea     rdx, [rsp+58h+arg_0]; bool *
0x18008a50f  mov     byte ptr [rsp+58h+arg_0], 0
0x18008a514  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x18008a519  cmp     byte ptr [rsp+58h+arg_0], 0
0x18008a51e  jnz     short loc_18008A550
0x18008a520  test    edi, edi
0x18008a522  jnz     short loc_18008A550
0x18008a524  mov     rcx, [rsp+58h+arg_10]
0x18008a529  lea     edx, [rsi+1Fh]
0x18008a52c  mov     rax, [rcx]
0x18008a52f  mov     rax, [rax+78h]
0x18008a533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a538  mov     ebx, eax
0x18008a53a  test    eax, eax
0x18008a53c  jz      short loc_18008A550
0x18008a53e  lea     rax, aFailedPiconnmg; "failed pIConnMgrConfig->SetProtocols"
0x18008a545  mov     r9d, 151h
0x18008a54b  jmp     loc_18008A64C
0x18008a550  mov     ecx, 10h; Size
0x18008a555  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008a55a  mov     [rsp+58h+arg_0], rax
0x18008a55f  test    rax, rax
0x18008a562  jz      loc_18008A63A
0x18008a568  mov     rcx, rax; this
0x18008a56b  call    ??0CImpInitIConnectionNotify@@QEAA@XZ; CImpInitIConnectionNotify::CImpInitIConnectionNotify(void)
0x18008a570  mov     rdi, rax
0x18008a573  test    rax, rax
0x18008a576  jz      loc_18008A63A
0x18008a57c  mov     rax, [rax]
0x18008a57f  mov     rcx, rdi
0x18008a582  mov     rax, [rax+8]
0x18008a586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a58b  mov     rcx, [r14]
0x18008a58e  xor     r9d, r9d
0x18008a591  mov     rdx, [rbp+10h]
0x18008a595  mov     r8, rdi
0x18008a598  mov     rax, [rcx]
0x18008a59b  mov     rax, [rax+18h]
0x18008a59f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a5a4  mov     ebx, eax
0x18008a5a6  test    eax, eax
0x18008a5a8  jz      short loc_18008A5B9
0x18008a5aa  lea     rax, aFailedMPiconnm_1; "failed m_pIConnMgr->Init"
0x18008a5b1  mov     r9d, 164h
0x18008a5b7  jmp     short loc_18008A601
0x18008a5b9  mov     rcx, [r14]
0x18008a5bc  mov     rax, [rcx]
0x18008a5bf  mov     rax, [rax+20h]
0x18008a5c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a5c8  mov     ebx, eax
0x18008a5ca  test    eax, eax
0x18008a5cc  jz      short loc_18008A5DD
0x18008a5ce  lea     rax, aFailedMPiconnm_0; "failed m_pIConnMgr->StartListening"
0x18008a5d5  mov     r9d, 16Ch
0x18008a5db  jmp     short loc_18008A601
0x18008a5dd  mov     rcx, [rsp+58h+arg_10]
0x18008a5e2  mov     rax, [rcx]
0x18008a5e5  mov     rax, [rax+18h]
0x18008a5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a5ee  mov     ebx, eax
0x18008a5f0  test    eax, eax
0x18008a5f2  jz      short loc_18008A629
0x18008a5f4  lea     rax, aFailedPiconnmg_0; "failed pIConnMgrConfig->SetPhaseToPostI"...
0x18008a5fb  mov     r9d, 174h
0x18008a601  mov     [rsp+58h+var_28], rax
0x18008a606  lea     r8, aComComplusDtcD_95; "com\\complus\\dtc\\dtc\\tipgw\\gwinit\\"...
0x18008a60d  lea     rax, aCimptipgwinitI_1; "CImpTipGWInit::InitializeConnectionMana"...
0x18008a614  mov     dword ptr [rsp+58h+var_30], ebx
0x18008a618  mov     edx, esi
0x18008a61a  mov     [rsp+58h+var_38], rax
0x18008a61f  mov     ecx, 0Ah
0x18008a624  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18008a629  mov     rax, [rdi]
0x18008a62c  mov     rcx, rdi
0x18008a62f  mov     rax, [rax+10h]
0x18008a633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a638  jmp     short loc_18008A674
0x18008a63a  mov     ebx, 8007000Eh
0x18008a63f  lea     rax, aFailedNewCimpi; "failed new CImpInitIConnectionNotify"
0x18008a646  mov     r9d, 15Ah
0x18008a64c  mov     edx, esi
0x18008a64e  mov     [rsp+58h+var_28], rax
0x18008a653  lea     r8, aComComplusDtcD_95; "com\\complus\\dtc\\dtc\\tipgw\\gwinit\\"...
0x18008a65a  lea     rax, aCimptipgwinitI_1; "CImpTipGWInit::InitializeConnectionMana"...
0x18008a661  mov     dword ptr [rsp+58h+var_30], ebx
0x18008a665  mov     ecx, 0Ah
0x18008a66a  mov     [rsp+58h+var_38], rax
0x18008a66f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18008a674  mov     rcx, [rsp+58h+arg_10]
0x18008a679  test    rcx, rcx
0x18008a67c  jz      short loc_18008A68A
0x18008a67e  mov     rax, [rcx]
0x18008a681  mov     rax, [rax+10h]
0x18008a685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a68a  mov     rbp, [rsp+58h+arg_18]
0x18008a68f  mov     eax, ebx
0x18008a691  mov     rbx, [rsp+58h+arg_8]
0x18008a696  add     rsp, 40h
0x18008a69a  pop     r14
0x18008a69c  pop     rdi
0x18008a69d  pop     rsi
0x18008a69e  retn
```
