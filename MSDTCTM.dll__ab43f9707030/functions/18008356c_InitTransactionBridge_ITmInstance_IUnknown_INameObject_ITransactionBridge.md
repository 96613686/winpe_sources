# InitTransactionBridge(ITmInstance *,IUnknown *,INameObject *,ITransactionBridge * *)

- ea: `0x18008356c`
- end: `0x180083919`
- name: `?InitTransactionBridge@@YAJPEAUITmInstance@@PEAUIUnknown@@PEAUINameObject@@PEAPEAUITransactionBridge@@@Z`
- size: `941`
- prototype: `__int64 __fastcall(struct ITmInstance *, struct IUnknown *, struct INameObject *, struct ITransactionBridge **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007668`

## callees

- `0x180001008`
- `0x180001058`
- `0x1800063b0`
- `0x180019b44`
- `0x18001a210`
- `0x18001fdb8`
- `0x1800240b0`
- `0x18008356c`
- `0x180083920`
- `0x1800b83e2`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800836aa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800836aa`

## string_xrefs

- `0x1800835cf`: `GetBridgeCLSID`
- `0x1800835fb`: `com\complus\dtc\dtc\msdtc\src\initbridge.cpp`
- `0x18008378e`: `com\complus\dtc\dtc\msdtc\src\initbridge.cpp`
- `0x18008387c`: `com\complus\dtc\dtc\msdtc\src\initbridge.cpp`
- `0x180083656`: `InitializeClrForCLSID`
- `0x180083626`: `No bridge was configured.`
- `0x180083735`: `OOM creating bridge config`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InitTransactionBridge(
        struct ITmInstance *a1,
        struct IUnknown *a2,
        struct INameObject *a3,
        struct ITransactionBridge **a4)
{
  _DWORD *v8; // rbx
  int BridgeCLSID; // eax
  const wchar_t *v10; // rcx
  __int64 v11; // r9
  HRESULT v12; // eax
  const wchar_t *v13; // rcx
  __int64 v14; // r9
  _QWORD *v15; // rax
  int v16; // eax
  const wchar_t *v17; // rcx
  __int64 v18; // r9
  unsigned int v19; // edx
  struct ITransactionBridge *v20; // rcx
  __int64 v21; // rcx
  char *ppv; // [rsp+20h] [rbp-39h]
  __int64 v24; // [rsp+28h] [rbp-31h]
  const wchar_t *v25; // [rsp+30h] [rbp-29h]
  unsigned int v26; // [rsp+40h] [rbp-19h] BYREF
  struct ITransactionBridge *v27; // [rsp+48h] [rbp-11h] BYREF
  struct ITransactionBridge *v28; // [rsp+50h] [rbp-9h] BYREF
  LPVOID v29[2]; // [rsp+58h] [rbp-1h] BYREF
  struct _GUID Buf1; // [rsp+68h] [rbp+Fh] BYREF

  Buf1 = 0;
  v29[0] = 0;
  v27 = 0;
  v28 = 0;
  v8 = 0;
  *a4 = 0;
  BridgeCLSID = GetBridgeCLSID(a1, &Buf1);
  v26 = BridgeCLSID;
  if ( BridgeCLSID < 0 )
  {
    v10 = (const wchar_t *)L"GetBridgeCLSID";
    v11 = 376;
LABEL_3:
    v25 = v10;
    LODWORD(v24) = BridgeCLSID;
LABEL_4:
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\initbridge.cpp",
      v11,
      L"InitTransactionBridge",
      v24,
      v25);
    goto LABEL_38;
  }
  if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
  {
    TraceStringInline(
      3,
      3,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\initbridge.cpp",
      381,
      L"InitTransactionBridge",
      0,
      L"No bridge was configured.");
    goto LABEL_38;
  }
  BridgeCLSID = InitializeClrForCLSID(&Buf1);
  v26 = BridgeCLSID;
  if ( BridgeCLSID < 0 )
  {
    v10 = L"InitializeClrForCLSID";
    v11 = 388;
    goto LABEL_3;
  }
  BridgeCLSID = InitializeGatewayForBridge(a2, a3);
  v26 = BridgeCLSID;
  if ( BridgeCLSID < 0 )
  {
    v10 = L"InitializeGatewayForBridge";
    v11 = 396;
    goto LABEL_3;
  }
  v12 = CoCreateInstance(&Buf1, 0, 1u, &IID_IUnknown, v29);
  v26 = v12;
  if ( v12 < 0 )
  {
    v13 = L"CoCI(bridge)";
    v14 = 407;
LABEL_36:
    LODWORD(v24) = v12;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\initbridge.cpp",
      v14,
      L"InitTransactionBridge",
      v24,
      v13);
    v19 = -1073737685;
    goto LABEL_37;
  }
  v12 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct ITransactionBridge **))v29[0])(
          v29[0],
          &IID_ITransactionBridge,
          &v27);
  v26 = v12;
  if ( v12 < 0 )
  {
    if ( v12 != -2147467262 )
    {
      v13 = L"Unknown failure doing QI";
      v14 = 486;
      goto LABEL_36;
    }
    v12 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct ITransactionBridge **))v29[0])(
            v29[0],
            &IID_ITransactionBridgeOld,
            &v28);
    v26 = v12;
    if ( v12 < 0 )
    {
      v13 = L"QI for old interface";
      v14 = 449;
      goto LABEL_36;
    }
    v16 = (*(__int64 (__fastcall **)(struct ITransactionBridge *))(*(_QWORD *)v28 + 24LL))(v28);
    v26 = v16;
    if ( v16 < 0 )
    {
      v17 = L"BridgeOld->Init";
      v18 = 461;
      goto LABEL_22;
    }
    v20 = v28;
  }
  else
  {
    v15 = operator new(0x18u);
    v8 = v15;
    v29[1] = v15;
    if ( v15 )
    {
      *v15 = &CTransactionBridgeConfiguration::`vftable';
      v15[2] = a1;
      (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)a1 + 8LL))(a1);
      v8[2] = 1;
    }
    else
    {
      v8 = 0;
    }
    if ( !v8 )
    {
      v26 = -2147024882;
      v25 = L"OOM creating bridge config";
      LODWORD(v24) = -2147024882;
      v11 = 424;
      goto LABEL_4;
    }
    v16 = (*(__int64 (__fastcall **)(struct ITransactionBridge *, _DWORD *))(*(_QWORD *)v27 + 24LL))(v27, v8);
    v26 = v16;
    if ( v16 < 0 )
    {
      v17 = L"Bridge->Init";
      v18 = 431;
LABEL_22:
      LODWORD(v24) = v16;
      TraceStringInline(
        3,
        1,
        L"com\\complus\\dtc\\dtc\\msdtc\\src\\initbridge.cpp",
        v18,
        L"InitTransactionBridge",
        v24,
        v17);
      v19 = -1073737684;
LABEL_37:
      locprint(2u, v19, 4u, &v26, ppv);
      goto LABEL_38;
    }
    v20 = v27;
  }
  *a4 = v20;
  (*(void (__fastcall **)(struct ITransactionBridge *))(*(_QWORD *)v20 + 8LL))(v20);
  if ( !byte_180165DA8 )
  {
    if ( (unsigned int)dword_180152CE0 > 5 && (unsigned __int8)tlgKeywordOn() )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v21,
        (__int64)byte_180147DA9);
    byte_180165DA8 = 1;
  }
LABEL_38:
  if ( v27 )
    (*(void (__fastcall **)(struct ITransactionBridge *))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v28 )
    (*(void (__fastcall **)(struct ITransactionBridge *))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v29[0] )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29[0] + 16LL))(v29[0]);
  if ( v8 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  return v26;
}

```

## disassembly

```asm
0x18008356c  push    rbp
0x18008356e  push    rbx
0x18008356f  push    rsi
0x180083570  push    rdi
0x180083571  push    r14
0x180083573  push    r15
0x180083575  lea     rbp, [rsp-2Fh]
0x18008357a  sub     rsp, 88h
0x180083581  mov     rax, cs:__security_cookie
0x180083588  xor     rax, rsp
0x18008358b  mov     [rbp+57h+var_38], rax
0x18008358f  mov     r14, r9
0x180083592  mov     r15, r8
0x180083595  mov     rdi, rdx
0x180083598  mov     rsi, rcx
0x18008359b  xorps   xmm0, xmm0
0x18008359e  movups  [rbp+57h+Buf1], xmm0
0x1800835a2  mov     [rbp+57h+var_58], 0
0x1800835aa  mov     [rbp+57h+var_68], 0
0x1800835b2  mov     [rbp+57h+var_60], 0
0x1800835ba  xor     ebx, ebx
0x1800835bc  mov     [r9], rbx
0x1800835bf  lea     rdx, [rbp+57h+Buf1]; struct _GUID *
0x1800835c3  call    ?GetBridgeCLSID@@YAJPEAUITmInstance@@PEAU_GUID@@@Z; GetBridgeCLSID(ITmInstance *,_GUID *)
0x1800835c8  mov     [rbp+57h+var_70], eax
0x1800835cb  test    eax, eax
0x1800835cd  jns     short loc_18008360C
0x1800835cf  lea     rcx, aGetbridgeclsid; "GetBridgeCLSID"
0x1800835d6  mov     r9d, 178h
0x1800835dc  mov     [rsp+0B0h+var_80], rcx
0x1800835e1  mov     dword ptr [rsp+0B0h+var_88], eax
0x1800835e5  mov     edx, 1
0x1800835ea  mov     ecx, 3
0x1800835ef  lea     rax, aInittransactio; "InitTransactionBridge"
0x1800835f6  mov     [rsp+0B0h+ppv], rax
0x1800835fb  lea     r8, aComComplusDtcD_31; "com\\complus\\dtc\\dtc\\msdtc\\src\\ini"...
0x180083602  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180083607  jmp     loc_1800838A7
0x18008360c  mov     r8d, 10h; Size
0x180083612  lea     rdx, GUID_NULL; Buf2
0x180083619  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18008361d  call    memcmp_0
0x180083622  test    eax, eax
0x180083624  jnz     short loc_180083646
0x180083626  lea     rax, aNoBridgeWasCon; "No bridge was configured."
0x18008362d  mov     [rsp+0B0h+var_80], rax
0x180083632  mov     [rsp+0B0h+var_88], rbx
0x180083637  mov     r9d, 17Dh
0x18008363d  mov     edx, 3
0x180083642  mov     ecx, edx
0x180083644  jmp     short loc_1800835EF
0x180083646  lea     rcx, [rbp+57h+Buf1]; struct _GUID *
0x18008364a  call    ?InitializeClrForCLSID@@YAJAEBU_GUID@@@Z; InitializeClrForCLSID(_GUID const &)
0x18008364f  mov     [rbp+57h+var_70], eax
0x180083652  test    eax, eax
0x180083654  jns     short loc_180083668
0x180083656  lea     rcx, aInitializeclrf; "InitializeClrForCLSID"
0x18008365d  mov     r9d, 184h
0x180083663  jmp     loc_1800835DC
0x180083668  mov     rdx, r15; struct INameObject *
0x18008366b  mov     rcx, rdi; struct IUnknown *
0x18008366e  call    ?InitializeGatewayForBridge@@YAJPEAUIUnknown@@PEAUINameObject@@@Z; InitializeGatewayForBridge(IUnknown *,INameObject *)
0x180083673  mov     [rbp+57h+var_70], eax
0x180083676  test    eax, eax
0x180083678  jns     short loc_18008368C
0x18008367a  lea     rcx, aInitializegate; "InitializeGatewayForBridge"
0x180083681  mov     r9d, 18Ch
0x180083687  jmp     loc_1800835DC
0x18008368c  lea     rax, [rbp+57h+var_58]
0x180083690  mov     [rsp+0B0h+ppv], rax; ppv
0x180083695  lea     r9, IID_IUnknown; riid
0x18008369c  mov     edi, 1
0x1800836a1  mov     r8d, edi; dwClsContext
0x1800836a4  xor     edx, edx; pUnkOuter
0x1800836a6  lea     rcx, [rbp+57h+Buf1]; rclsid
0x1800836aa  call    cs:__imp_CoCreateInstance
0x1800836b0  mov     [rbp+57h+var_70], eax
0x1800836b3  test    eax, eax
0x1800836b5  jns     short loc_1800836C9
0x1800836b7  lea     rcx, aCociBridge; "CoCI(bridge)"
0x1800836be  mov     r9d, 197h
0x1800836c4  jmp     loc_180083867
0x1800836c9  mov     rcx, [rbp+57h+var_58]
0x1800836cd  mov     rax, [rcx]
0x1800836d0  lea     r8, [rbp+57h+var_68]
0x1800836d4  lea     rdx, IID_ITransactionBridge
0x1800836db  mov     rax, [rax]
0x1800836de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800836e3  mov     [rbp+57h+var_70], eax
0x1800836e6  test    eax, eax
0x1800836e8  js      loc_1800837B1
0x1800836ee  mov     ecx, 18h; Size
0x1800836f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800836f8  mov     rbx, rax
0x1800836fb  mov     [rbp+57h+var_50], rax
0x1800836ff  test    rax, rax
0x180083702  jz      short loc_180083726
0x180083704  lea     rax, ??_7CTransactionBridgeConfiguration@@6B@; const CTransactionBridgeConfiguration::`vftable'
0x18008370b  mov     [rbx], rax
0x18008370e  mov     [rbx+10h], rsi
0x180083712  mov     rax, [rsi]
0x180083715  mov     rcx, rsi
0x180083718  mov     rax, [rax+8]
0x18008371c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083721  mov     [rbx+8], edi
0x180083724  jmp     short loc_180083728
0x180083726  xor     ebx, ebx
0x180083728  test    rbx, rbx
0x18008372b  jnz     short loc_180083752
0x18008372d  mov     ecx, 8007000Eh
0x180083732  mov     [rbp+57h+var_70], ecx
0x180083735  lea     rax, aOomCreatingBri; "OOM creating bridge config"
0x18008373c  mov     [rsp+0B0h+var_80], rax
0x180083741  mov     dword ptr [rsp+0B0h+var_88], ecx
0x180083745  mov     r9d, 1A8h
0x18008374b  mov     edx, edi
0x18008374d  jmp     loc_1800835EA
0x180083752  mov     rcx, [rbp+57h+var_68]
0x180083756  mov     rax, [rcx]
0x180083759  mov     rdx, rbx
0x18008375c  mov     rax, [rax+18h]
0x180083760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083765  mov     [rbp+57h+var_70], eax
0x180083768  test    eax, eax
0x18008376a  jns     short loc_1800837AB
0x18008376c  lea     rcx, aBridgeInit; "Bridge->Init"
0x180083773  mov     r9d, 1AFh
0x180083779  mov     [rsp+0B0h+var_80], rcx
0x18008377e  mov     dword ptr [rsp+0B0h+var_88], eax
0x180083782  lea     rax, aInittransactio; "InitTransactionBridge"
0x180083789  mov     [rsp+0B0h+ppv], rax
0x18008378e  lea     r8, aComComplusDtcD_31; "com\\complus\\dtc\\dtc\\msdtc\\src\\ini"...
0x180083795  mov     edx, edi
0x180083797  mov     ecx, 3
0x18008379c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800837a1  mov     edx, 0C000102Ch
0x1800837a6  jmp     loc_180083894
0x1800837ab  mov     rcx, [rbp+57h+var_68]
0x1800837af  jmp     short loc_180083819
0x1800837b1  cmp     eax, 80004002h
0x1800837b6  jnz     loc_18008385A
0x1800837bc  mov     rcx, [rbp+57h+var_58]
0x1800837c0  mov     rax, [rcx]
0x1800837c3  lea     r8, [rbp+57h+var_60]
0x1800837c7  lea     rdx, IID_ITransactionBridgeOld
0x1800837ce  mov     rax, [rax]
0x1800837d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800837d6  mov     [rbp+57h+var_70], eax
0x1800837d9  test    eax, eax
0x1800837db  jns     short loc_1800837EC
0x1800837dd  lea     rcx, aQiForOldInterf; "QI for old interface"
0x1800837e4  mov     r9d, 1C1h
0x1800837ea  jmp     short loc_180083867
0x1800837ec  mov     rcx, [rbp+57h+var_60]
0x1800837f0  mov     rax, [rcx]
0x1800837f3  mov     rax, [rax+18h]
0x1800837f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800837fc  mov     [rbp+57h+var_70], eax
0x1800837ff  test    eax, eax
0x180083801  jns     short loc_180083815
0x180083803  lea     rcx, aBridgeoldInit; "BridgeOld->Init"
0x18008380a  mov     r9d, 1CDh
0x180083810  jmp     loc_180083779
0x180083815  mov     rcx, [rbp+57h+var_60]
0x180083819  mov     [r14], rcx
0x18008381c  mov     rax, [rcx]
0x18008381f  mov     rax, [rax+8]
0x180083823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083828  cmp     cs:byte_180165DA8, 0
0x18008382f  jnz     short loc_1800838A7
0x180083831  mov     eax, cs:dword_180152CE0
0x180083837  cmp     eax, 5
0x18008383a  jbe     short loc_180083851
0x18008383c  call    _tlgKeywordOn
0x180083841  test    al, al
0x180083843  jz      short loc_180083851
0x180083845  lea     rdx, byte_180147DA9
0x18008384c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180083851  mov     cs:byte_180165DA8, dil
0x180083858  jmp     short loc_1800838A7
0x18008385a  lea     rcx, aUnknownFailure; "Unknown failure doing QI"
0x180083861  mov     r9d, 1E6h
0x180083867  mov     [rsp+0B0h+var_80], rcx
0x18008386c  mov     dword ptr [rsp+0B0h+var_88], eax
0x180083870  lea     rax, aInittransactio; "InitTransactionBridge"
0x180083877  mov     [rsp+0B0h+ppv], rax; char *
0x18008387c  lea     r8, aComComplusDtcD_31; "com\\complus\\dtc\\dtc\\msdtc\\src\\ini"...
0x180083883  mov     edx, edi
0x180083885  mov     ecx, 3
0x18008388a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18008388f  mov     edx, 0C000102Bh; unsigned int
0x180083894  lea     r9, [rbp+57h+var_70]; void *
0x180083898  mov     r8d, 4; unsigned int
0x18008389e  lea     ecx, [r8-2]; unsigned int
0x1800838a2  call    ?locprint@@YAXKKKPEAXPEAD@Z; locprint(ulong,ulong,ulong,void *,char *)
0x1800838a7  mov     rcx, [rbp+57h+var_68]
0x1800838ab  test    rcx, rcx
0x1800838ae  jz      short loc_1800838BC
0x1800838b0  mov     rax, [rcx]
0x1800838b3  mov     rax, [rax+10h]
0x1800838b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800838bc  mov     rcx, [rbp+57h+var_60]
0x1800838c0  test    rcx, rcx
0x1800838c3  jz      short loc_1800838D1
0x1800838c5  mov     rax, [rcx]
0x1800838c8  mov     rax, [rax+10h]
0x1800838cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800838d1  mov     rcx, [rbp+57h+var_58]
0x1800838d5  test    rcx, rcx
0x1800838d8  jz      short loc_1800838E6
0x1800838da  mov     rax, [rcx]
0x1800838dd  mov     rax, [rax+10h]
0x1800838e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800838e6  test    rbx, rbx
0x1800838e9  jz      short loc_1800838FA
0x1800838eb  mov     rax, [rbx]
0x1800838ee  mov     rcx, rbx
0x1800838f1  mov     rax, [rax+10h]
0x1800838f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800838fa  mov     eax, [rbp+57h+var_70]
0x1800838fd  mov     rcx, [rbp+57h+var_38]
0x180083901  xor     rcx, rsp; StackCookie
0x180083904  call    __security_check_cookie
0x180083909  add     rsp, 88h
0x180083910  pop     r15
0x180083912  pop     r14
0x180083914  pop     rdi
0x180083915  pop     rsi
0x180083916  pop     rbx
0x180083917  pop     rbp
0x180083918  retn
```
