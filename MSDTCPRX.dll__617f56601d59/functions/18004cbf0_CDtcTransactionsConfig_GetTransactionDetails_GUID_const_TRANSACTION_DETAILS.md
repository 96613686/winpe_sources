# CDtcTransactionsConfig::GetTransactionDetails(_GUID const &,_TRANSACTION_DETAILS *)

- ea: `0x18004cbf0`
- end: `0x18004d2f1`
- name: `?GetTransactionDetails@CDtcTransactionsConfig@@QEAAJAEBU_GUID@@PEAU_TRANSACTION_DETAILS@@@Z`
- size: `1793`
- prototype: `int(CDtcTransactionsConfig *__hidden this, const struct _GUID *, struct _TRANSACTION_DETAILS *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004b240`

## callees

- `0x180003cf0`
- `0x18000d5f4`
- `0x180012130`
- `0x180021e78`
- `0x180048d50`
- `0x180049010`
- `0x18004cb30`
- `0x18004cbf0`
- `0x18007f82c`
- `0x18007f8a0`
- `0x180081d9e`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004cf71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004cfba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004d099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004d0fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004cf71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004cfba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004d099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004d0fb`

## string_xrefs

- `0x18004cc6e`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004cce9`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004cd4a`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004cdd3`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004ce74`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004cf38`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004d1a2`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004d2a7`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004cc49`: `CDtcTransactionsConfig::GetTransactionDetails`
- `0x18004ccd9`: `CDtcTransactionsConfig::GetTransactionDetails`
- `0x18004cd3f`: `CDtcTransactionsConfig::GetTransactionDetails`
- `0x18004cde0`: `CDtcTransactionsConfig::GetTransactionDetails`
- `0x18004ce43`: `CDtcTransactionsConfig::GetTransactionDetails`
- `0x18004ce67`: `CDtcTransactionsConfig::GetTransactionDetails`
- `0x18004d1db`: `CDtcTransactionsConfig::GetTransactionDetails`
- `0x18004d204`: `CDtcTransactionsConfig::GetTransactionDetails`
- `0x18004cc8f`: `CDtcTransactionsConfig::GetTransactionDetails (com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp@422): pTransactionDetails shouldn't be NULL`
- `0x18004d1e7`: `Failed to create a CSendReceive.`
- `0x18004cf85`: `CoTaskMemAlloc failed.`
- `0x18004cfce`: `CoTaskMemAlloc failed.`
- `0x18004d13b`: `CoTaskMemAlloc failed.`
- `0x18004d16f`: `CoTaskMemAlloc failed.`

## pseudocode

```c
__int64 __fastcall CDtcTransactionsConfig::GetTransactionDetails(
        CDtcTransactionsConfig *this,
        const struct _GUID *a2,
        struct _TRANSACTION_DETAILS *a3)
{
  CIConnSink *v3; // rdi
  struct INameObject *v7; // r13
  __int128 v8; // xmm0
  CDtcConfig *v9; // rcx
  int ConnectionDispenser; // ebx
  __int64 v11; // r9
  struct CSendReceive *Instance; // rax
  int PartnerNamedObject; // eax
  const wchar_t *v15; // rax
  __int64 v16; // rax
  __int64 v17; // xmm1_8
  _DWORD *v18; // r15
  SIZE_T v19; // rcx
  void *v20; // rax
  void *v21; // rax
  __int64 i; // r12
  __int64 v23; // rbx
  char *v24; // r15
  char *v25; // rcx
  unsigned int v26; // r15d
  char *v27; // rcx
  CDtcTransactionsConfig *v28; // rcx
  __int64 v29; // [rsp+28h] [rbp-D8h]
  __int64 v30; // [rsp+28h] [rbp-D8h]
  const wchar_t *v31; // [rsp+30h] [rbp-D0h]
  __int64 v32; // [rsp+38h] [rbp-C8h]
  unsigned int v33; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v34; // [rsp+54h] [rbp-ACh] BYREF
  char *v35; // [rsp+58h] [rbp-A8h] BYREF
  int v36; // [rsp+60h] [rbp-A0h] BYREF
  struct INameObject *v37; // [rsp+68h] [rbp-98h] BYREF
  struct IConnectionDispenser *v38; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v39; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v40; // [rsp+80h] [rbp-80h]
  __int128 v41; // [rsp+90h] [rbp-70h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-60h]
  __int128 v43; // [rsp+B0h] [rbp-50h] BYREF
  char v44[256]; // [rsp+C0h] [rbp-40h] BYREF

  v3 = 0;
  v38 = 0;
  v37 = 0;
  v36 = 0;
  v39 = 0;
  v33 = 0;
  v35 = 0;
  v34 = 0;
  v7 = 0;
  v43 = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    420,
    L"CDtcTransactionsConfig::GetTransactionDetails",
    0,
    L"In");
  if ( !a3 )
    DtcInternalErrorW(
      L"CDtcTransactionsConfig::GetTransactionDetails (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp@422): pTrans"
       "actionDetails shouldn't be NULL");
  v8 = (__int128)*a2;
  *(_DWORD *)a3 = 0;
  *((_QWORD *)a3 + 1) = 0;
  *((_QWORD *)a3 + 2) = 0;
  v9 = (CDtcConfig *)*((_QWORD *)this + 3);
  v43 = v8;
  ConnectionDispenser = CDtcConfig::GetConnectionDispenser(v9, &v38);
  if ( ConnectionDispenser < 0 )
  {
    v11 = 437;
    v31 = L"GetConnectionDispenser failed.";
    LODWORD(v29) = ConnectionDispenser;
    goto LABEL_5;
  }
  Instance = CSendReceive::CreateInstance();
  v3 = Instance;
  if ( !Instance )
  {
LABEL_47:
    v31 = L"Failed to create a CSendReceive.";
    ConnectionDispenser = -2147024882;
    LODWORD(v29) = -2147024882;
    v11 = 454;
    goto LABEL_5;
  }
  if ( !(*(unsigned int (__fastcall **)(struct CSendReceive *))(*(_QWORD *)Instance + 32LL))(Instance) )
  {
    LODWORD(v29) = ConnectionDispenser;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
      446,
      L"CDtcTransactionsConfig::GetTransactionDetails",
      v29,
      L"pCSendReceive->Init() failed.");
    CIConnSink::DeleteObject(v3);
    v3 = 0;
    goto LABEL_47;
  }
  (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v3 + 160LL))(v3);
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
  (*(void (__fastcall **)(CIConnSink *, unsigned __int64))(*(_QWORD *)v3 + 136LL))(
    v3,
    ((unsigned __int64)this + 8) & -(__int64)(this != 0));
  PartnerNamedObject = CDtcConfig::GetPartnerNamedObject(*((CDtcConfig **)this + 3), &v37);
  if ( PartnerNamedObject < 0 )
  {
    LODWORD(v29) = PartnerNamedObject;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
      464,
      L"CDtcTransactionsConfig::GetTransactionDetails",
      v29,
      L"GetPartnerNamedObject failed.");
    return 0;
  }
  v7 = v37;
  ConnectionDispenser = (*(__int64 (__fastcall **)(CIConnSink *, struct IConnectionDispenser *, struct INameObject *, __int64, int))(*(_QWORD *)v3 + 248LL))(
                          v3,
                          v38,
                          v37,
                          1,
                          34);
  if ( ConnectionDispenser >= 0 )
  {
    v16 = (*(__int64 (__fastcall **)(struct INameObject *))(*(_QWORD *)v7 + 24LL))(v7);
    v17 = *(_QWORD *)(v16 + 16);
    v41 = *(_OWORD *)v16;
    v42 = v17;
    TraceStringInline(
      15,
      3,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
      478,
      L"CDtcTransactionsConfig::GetTransactionDetails",
      0,
      L"Connection established to %s",
      &v41);
    ConnectionDispenser = (*(__int64 (__fastcall **)(CIConnSink *, __int64, __int64, __int128 *, int *, _DWORD **, _DWORD, unsigned int *))(*(_QWORD *)v3 + 96LL))(
                            v3,
                            18177,
                            16,
                            &v43,
                            &v36,
                            &v39,
                            0,
                            &v33);
    if ( ConnectionDispenser || v36 != 18178 || v33 <= 0xC )
    {
      LODWORD(v32) = v36;
      LODWORD(v30) = ConnectionDispenser;
      TraceStringInline(
        15,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
        491,
        L"CDtcTransactionsConfig::GetTransactionDetails",
        v30,
        L"pCSendReceive->SendReceive failed or invalid message received Mtag = %d, cbRef = %d",
        v32,
        v33);
      ConnectionDispenser = -2147467259;
      goto LABEL_48;
    }
    LODWORD(v32) = 18178;
    TraceStringInline(
      15,
      3,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
      496,
      L"CDtcTransactionsConfig::GetTransactionDetails",
      0,
      L"Response received %d",
      v32);
    v18 = v39;
    v19 = 8LL * (unsigned int)(*v39 + 1);
    *(_DWORD *)a3 = *v39 + 1;
    v20 = CoTaskMemAlloc(v19);
    *((_QWORD *)a3 + 1) = v20;
    if ( v20 )
    {
      memset_0(v20, 0, 8LL * *(unsigned int *)a3);
      v21 = CoTaskMemAlloc(8LL * *(unsigned int *)a3);
      *((_QWORD *)a3 + 2) = v21;
      if ( v21 )
      {
        memset_0(v21, 0, 8LL * *(unsigned int *)a3);
        v33 -= 8;
        v37 = (struct INameObject *)(v18 + 2);
        for ( i = 0; (unsigned int)i < *(_DWORD *)a3; i = (unsigned int)(i + 1) )
        {
          ConnectionDispenser = CTxStatusInfo::GetNextVarItemWithinBounds((void **)&v37, (void **)&v35, &v34, &v33);
          if ( ConnectionDispenser < 0 )
          {
            v15 = L"CTxStatusInfo::GetNextVarItemWithinBounds failed.";
            v11 = 543;
            goto LABEL_13;
          }
          LODWORD(v23) = v34;
          if ( (_DWORD)i )
          {
            v24 = v35;
          }
          else if ( !v34 || (v24 = v35) == 0 || !*v35 )
          {
            StringCbCopyA(v44, 0xFFu, Class);
            v23 = -1;
            do
              ++v23;
            while ( v44[v23] );
            v24 = v44;
            v34 = v23;
            v35 = v44;
          }
          v40 = (unsigned int)(v23 + 1);
          *(_QWORD *)(*((_QWORD *)a3 + 1) + 8 * i) = CoTaskMemAlloc(v40);
          v25 = *(char **)(*((_QWORD *)a3 + 1) + 8 * i);
          if ( !v25 )
          {
            v31 = L"CoTaskMemAlloc failed.";
            ConnectionDispenser = -2147024882;
            LODWORD(v29) = -2147024882;
            v11 = 568;
            goto LABEL_5;
          }
          if ( (_DWORD)v23 )
            StringCbCopyA(v25, v40, v24);
          else
            *v25 = 0;
          ConnectionDispenser = CTxStatusInfo::GetNextVarItemWithinBounds((void **)&v37, (void **)&v35, &v34, &v33);
          if ( ConnectionDispenser < 0 )
          {
            v15 = L"CTxStatusInfo::GetNextVarItemWithinBounds failed.";
            v11 = 593;
            goto LABEL_13;
          }
          v26 = v34;
          v40 = v34 + 1;
          *(_QWORD *)(*((_QWORD *)a3 + 2) + 8 * i) = CoTaskMemAlloc(v40);
          v27 = *(char **)(*((_QWORD *)a3 + 2) + 8 * i);
          if ( !v27 )
          {
            v31 = L"CoTaskMemAlloc failed.";
            ConnectionDispenser = -2147024882;
            LODWORD(v29) = -2147024882;
            v11 = 601;
            goto LABEL_5;
          }
          if ( v26 )
            StringCbCopyA(v27, v40, v35);
          else
            *v27 = 0;
        }
        goto LABEL_48;
      }
      v31 = L"CoTaskMemAlloc failed.";
      ConnectionDispenser = -2147024882;
      LODWORD(v29) = -2147024882;
      v11 = 519;
    }
    else
    {
      v31 = L"CoTaskMemAlloc failed.";
      ConnectionDispenser = -2147024882;
      LODWORD(v29) = -2147024882;
      v11 = 509;
    }
  }
  else
  {
    v15 = L"Failed to Connect";
    v11 = 474;
LABEL_13:
    v31 = v15;
    LODWORD(v29) = ConnectionDispenser;
  }
LABEL_5:
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    v11,
    L"CDtcTransactionsConfig::GetTransactionDetails",
    v29,
    v31);
LABEL_48:
  v28 = v38;
  if ( v38 )
    (*(void (__fastcall **)(struct IConnectionDispenser *))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v7 )
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v3 )
  {
    if ( v39 )
      (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v3 + 120LL))(v3);
    (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v3 + 144LL))(v3);
    (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v3 + 272LL))(v3);
    (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v3 + 168LL))(v3);
  }
  if ( ConnectionDispenser < 0 )
    CDtcTransactionsConfig::FreeTransactionDetails(v28, a3);
  LODWORD(v29) = ConnectionDispenser;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    639,
    L"CDtcTransactionsConfig::GetTransactionDetails",
    v29,
    L"Out");
  return (unsigned int)ConnectionDispenser;
}

```

## disassembly

```asm
0x18004cbf0  mov     [rsp-8+arg_18], rbx
0x18004cbf5  push    rbp
0x18004cbf6  push    rsi
0x18004cbf7  push    rdi
0x18004cbf8  push    r12
0x18004cbfa  push    r13
0x18004cbfc  push    r14
0x18004cbfe  push    r15
0x18004cc00  lea     rbp, [rsp-0D0h]
0x18004cc08  sub     rsp, 1D0h
0x18004cc0f  mov     rax, cs:__security_cookie
0x18004cc16  xor     rax, rsp
0x18004cc19  mov     [rbp+100h+var_40], rax
0x18004cc20  xor     edi, edi
0x18004cc22  lea     rax, aIn_0; "In"
0x18004cc29  mov     [rsp+200h+var_1D0], rax
0x18004cc2e  mov     r14, r8
0x18004cc31  mov     rbx, rdx
0x18004cc34  mov     [rsp+200h+var_1D8], rdi
0x18004cc39  mov     r15, rcx
0x18004cc3c  mov     [rsp+200h+var_190], rdi
0x18004cc41  xorps   xmm0, xmm0
0x18004cc44  mov     [rsp+200h+var_198], rdi
0x18004cc49  lea     rax, aCdtctransactio_4; "CDtcTransactionsConfig::GetTransactionD"...
0x18004cc50  mov     [rsp+200h+var_1A0], edi
0x18004cc54  lea     edx, [rdi+6]
0x18004cc57  mov     [rsp+200h+var_188], rdi
0x18004cc5c  lea     ecx, [rdi+0Fh]
0x18004cc5f  mov     [rsp+200h+var_1B0], edi
0x18004cc63  mov     r9d, 1A4h
0x18004cc69  mov     [rsp+200h+var_1A8], rdi
0x18004cc6e  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004cc75  mov     [rsp+200h+var_1AC], edi
0x18004cc79  mov     r13d, edi
0x18004cc7c  mov     [rsp+200h+var_1E0], rax
0x18004cc81  movups  [rbp+100h+var_150], xmm0
0x18004cc85  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004cc8a  test    r14, r14
0x18004cc8d  jnz     short loc_18004CC9C
0x18004cc8f  lea     rcx, aCdtctransactio_12; "CDtcTransactionsConfig::GetTransactionD"...
0x18004cc96  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18004cc9c  movups  xmm0, xmmword ptr [rbx]
0x18004cc9f  mov     [r14], edi
0x18004cca2  lea     r12, [r15+18h]
0x18004cca6  mov     [r14+8], rdi
0x18004ccaa  lea     rdx, [rsp+200h+var_190]; struct IConnectionDispenser **
0x18004ccaf  mov     [r14+10h], rdi
0x18004ccb3  mov     rcx, [r12]; this
0x18004ccb7  movdqu  [rbp+100h+var_150], xmm0
0x18004ccbc  call    ?GetConnectionDispenser@CDtcConfig@@QEAAJPEAPEAUIConnectionDispenser@@@Z; CDtcConfig::GetConnectionDispenser(IConnectionDispenser * *)
0x18004ccc1  mov     ebx, eax
0x18004ccc3  test    eax, eax
0x18004ccc5  jns     short loc_18004CD04
0x18004ccc7  lea     rax, aGetconnectiond_0; "GetConnectionDispenser failed."
0x18004ccce  mov     r9d, 1B5h
0x18004ccd4  mov     [rsp+200h+var_1D0], rax
0x18004ccd9  lea     r12, aCdtctransactio_4; "CDtcTransactionsConfig::GetTransactionD"...
0x18004cce0  mov     dword ptr [rsp+200h+var_1D8], ebx
0x18004cce4  mov     edx, 1
0x18004cce9  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004ccf0  mov     [rsp+200h+var_1E0], r12
0x18004ccf5  mov     ecx, 0Fh
0x18004ccfa  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004ccff  jmp     loc_18004D20B
0x18004cd04  call    ?CreateInstance@CSendReceive@@SAPEAV1@XZ; CSendReceive::CreateInstance(void)
0x18004cd09  mov     rdi, rax
0x18004cd0c  mov     esi, 1
0x18004cd11  test    rax, rax
0x18004cd14  jz      loc_18004D1DB
0x18004cd1a  mov     rcx, [rax]
0x18004cd1d  mov     rax, [rcx+20h]
0x18004cd21  mov     rcx, rdi
0x18004cd24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd29  test    eax, eax
0x18004cd2b  jnz     short loc_18004CD6F
0x18004cd2d  lea     rax, aPcsendreceiveI; "pCSendReceive->Init() failed."
0x18004cd34  mov     r9d, 1BEh
0x18004cd3a  mov     [rsp+200h+var_1D0], rax
0x18004cd3f  lea     r12, aCdtctransactio_4; "CDtcTransactionsConfig::GetTransactionD"...
0x18004cd46  mov     dword ptr [rsp+200h+var_1D8], ebx
0x18004cd4a  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004cd51  mov     edx, esi
0x18004cd53  mov     [rsp+200h+var_1E0], r12
0x18004cd58  lea     ecx, [rsi+0Eh]
0x18004cd5b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004cd60  mov     rcx, rdi; this
0x18004cd63  call    ?DeleteObject@CIConnSink@@UEAAXXZ; CIConnSink::DeleteObject(void)
0x18004cd68  xor     edi, edi
0x18004cd6a  jmp     loc_18004D1E2
0x18004cd6f  mov     rax, [rdi]
0x18004cd72  mov     rcx, rdi
0x18004cd75  mov     rax, [rax+0A0h]
0x18004cd7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd81  lea     rbx, [r15+8]
0x18004cd85  mov     rax, [rbx]
0x18004cd88  mov     rcx, rbx
0x18004cd8b  mov     rax, [rax+8]
0x18004cd8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd94  mov     rax, [rdi]
0x18004cd97  neg     r15
0x18004cd9a  mov     rcx, rdi
0x18004cd9d  sbb     rdx, rdx
0x18004cda0  and     rdx, rbx
0x18004cda3  mov     rax, [rax+88h]
0x18004cdaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cdaf  mov     rcx, [r12]; this
0x18004cdb3  lea     rdx, [rsp+200h+var_198]; struct INameObject **
0x18004cdb8  call    ?GetPartnerNamedObject@CDtcConfig@@QEAAJPEAPEAUINameObject@@@Z; CDtcConfig::GetPartnerNamedObject(INameObject * *)
0x18004cdbd  test    eax, eax
0x18004cdbf  jns     short loc_18004CDFD
0x18004cdc1  lea     rdx, aGetpartnername; "GetPartnerNamedObject failed."
0x18004cdc8  mov     r9d, 1D0h
0x18004cdce  mov     [rsp+200h+var_1D0], rdx
0x18004cdd3  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004cdda  mov     dword ptr [rsp+200h+var_1D8], eax
0x18004cdde  mov     edx, esi
0x18004cde0  lea     rax, aCdtctransactio_4; "CDtcTransactionsConfig::GetTransactionD"...
0x18004cde7  mov     ecx, 0Fh
0x18004cdec  mov     [rsp+200h+var_1E0], rax
0x18004cdf1  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004cdf6  xor     eax, eax
0x18004cdf8  jmp     loc_18004D2C7
0x18004cdfd  mov     rax, [rdi]
0x18004ce00  mov     r9d, esi
0x18004ce03  mov     r13, [rsp+200h+var_198]
0x18004ce08  mov     rcx, rdi
0x18004ce0b  mov     rdx, [rsp+200h+var_190]
0x18004ce10  mov     r8, r13
0x18004ce13  mov     dword ptr [rsp+200h+var_1E0], 22h ; '"'
0x18004ce1b  mov     rax, [rax+0F8h]
0x18004ce22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce27  mov     ebx, eax
0x18004ce29  test    eax, eax
0x18004ce2b  jns     short loc_18004CE51
0x18004ce2d  lea     rax, aFailedToConnec; "Failed to Connect"
0x18004ce34  mov     r9d, 1DAh
0x18004ce3a  mov     [rsp+200h+var_1D0], rax
0x18004ce3f  mov     dword ptr [rsp+200h+var_1D8], ebx
0x18004ce43  lea     r12, aCdtctransactio_4; "CDtcTransactionsConfig::GetTransactionD"...
0x18004ce4a  mov     edx, esi
0x18004ce4c  jmp     loc_18004CCE9
0x18004ce51  mov     rax, [r13+0]
0x18004ce55  mov     rcx, r13
0x18004ce58  mov     rax, [rax+18h]
0x18004ce5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce61  mov     r15d, 3
0x18004ce67  lea     r12, aCdtctransactio_4; "CDtcTransactionsConfig::GetTransactionD"...
0x18004ce6e  mov     r9d, 1DEh
0x18004ce74  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004ce7b  mov     edx, r15d
0x18004ce7e  movups  xmm0, xmmword ptr [rax]
0x18004ce81  lea     ecx, [r15+0Ch]
0x18004ce85  movsd   xmm1, qword ptr [rax+10h]
0x18004ce8a  lea     rax, [rbp+100h+var_170]
0x18004ce8e  mov     [rsp+200h+var_1C8], rax
0x18004ce93  lea     rax, aConnectionEsta; "Connection established to %s"
0x18004ce9a  mov     [rsp+200h+var_1D0], rax
0x18004ce9f  mov     [rsp+200h+var_1D8], 0
0x18004cea8  mov     [rsp+200h+var_1E0], r12
0x18004cead  movaps  [rbp+100h+var_170], xmm0
0x18004ceb1  movsd   [rbp+100h+var_160], xmm1
0x18004ceb6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004cebb  mov     rax, [rdi]
0x18004cebe  lea     rcx, [rsp+200h+var_1B0]
0x18004cec3  mov     [rsp+200h+var_1C8], rcx
0x18004cec8  lea     r9, [rbp+100h+var_150]
0x18004cecc  lea     rcx, [rsp+200h+var_188]
0x18004ced1  mov     dword ptr [rsp+200h+var_1D0], 0
0x18004ced9  mov     [rsp+200h+var_1D8], rcx
0x18004cede  lea     r8d, [r15+0Dh]
0x18004cee2  mov     rax, [rax+60h]
0x18004cee6  lea     rcx, [rsp+200h+var_1A0]
0x18004ceeb  mov     [rsp+200h+var_1E0], rcx
0x18004cef0  mov     edx, 4701h
0x18004cef5  mov     rcx, rdi
0x18004cef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cefd  mov     ecx, [rsp+200h+var_1B0]
0x18004cf01  mov     ebx, eax
0x18004cf03  mov     eax, [rsp+200h+var_1A0]
0x18004cf07  test    ebx, ebx
0x18004cf09  jnz     loc_18004D19E
0x18004cf0f  mov     r8d, 4702h
0x18004cf15  cmp     eax, r8d
0x18004cf18  jnz     loc_18004D19E
0x18004cf1e  cmp     ecx, 0Ch
0x18004cf21  jbe     loc_18004D19E
0x18004cf27  mov     dword ptr [rsp+200h+var_1C8], r8d
0x18004cf2c  lea     rax, aResponseReceiv; "Response received %d"
0x18004cf33  mov     [rsp+200h+var_1D0], rax
0x18004cf38  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004cf3f  mov     [rsp+200h+var_1D8], 0
0x18004cf48  lea     ecx, [rbx+0Fh]
0x18004cf4b  mov     r9d, 1F0h
0x18004cf51  mov     [rsp+200h+var_1E0], r12
0x18004cf56  mov     edx, r15d
0x18004cf59  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004cf5e  mov     r15, [rsp+200h+var_188]
0x18004cf63  mov     eax, [r15]
0x18004cf66  inc     eax
0x18004cf68  mov     ecx, eax
0x18004cf6a  shl     rcx, 3; cb
0x18004cf6e  mov     [r14], eax
0x18004cf71  call    cs:__imp_CoTaskMemAlloc
0x18004cf77  mov     [r14+8], rax
0x18004cf7b  test    rax, rax
0x18004cf7e  jnz     short loc_18004CFA2
0x18004cf80  mov     eax, 8007000Eh
0x18004cf85  lea     rcx, aCotaskmemalloc; "CoTaskMemAlloc failed."
0x18004cf8c  mov     [rsp+200h+var_1D0], rcx
0x18004cf91  mov     ebx, eax
0x18004cf93  mov     dword ptr [rsp+200h+var_1D8], eax
0x18004cf97  mov     r9d, 1FDh
0x18004cf9d  jmp     loc_18004CE4A
0x18004cfa2  mov     r8d, [r14]
0x18004cfa5  xor     edx, edx; Val
0x18004cfa7  shl     r8, 3; Size
0x18004cfab  mov     rcx, rax; void *
0x18004cfae  call    memset_0
0x18004cfb3  mov     ecx, [r14]
0x18004cfb6  shl     rcx, 3; cb
0x18004cfba  call    cs:__imp_CoTaskMemAlloc
0x18004cfc0  mov     [r14+10h], rax
0x18004cfc4  test    rax, rax
0x18004cfc7  jnz     short loc_18004CFEB
0x18004cfc9  mov     eax, 8007000Eh
0x18004cfce  lea     rcx, aCotaskmemalloc; "CoTaskMemAlloc failed."
0x18004cfd5  mov     [rsp+200h+var_1D0], rcx
0x18004cfda  mov     ebx, eax
0x18004cfdc  mov     dword ptr [rsp+200h+var_1D8], eax
0x18004cfe0  mov     r9d, 207h
0x18004cfe6  jmp     loc_18004CE4A
0x18004cfeb  mov     r8d, [r14]
0x18004cfee  xor     edx, edx; Val
0x18004cff0  shl     r8, 3; Size
0x18004cff4  mov     rcx, rax; void *
0x18004cff7  call    memset_0
0x18004cffc  add     [rsp+200h+var_1B0], 0FFFFFFF8h
0x18004d001  lea     rax, [r15+8]
0x18004d005  mov     [rsp+200h+var_198], rax
0x18004d00a  xor     r12d, r12d
0x18004d00d  cmp     r12d, [r14]
0x18004d010  jnb     loc_18004D204
0x18004d016  lea     r9, [rsp+200h+var_1B0]; unsigned int *
0x18004d01b  lea     r8, [rsp+200h+var_1AC]; unsigned int *
0x18004d020  lea     rdx, [rsp+200h+var_1A8]; void **
0x18004d025  lea     rcx, [rsp+200h+var_198]; void **
0x18004d02a  call    ?GetNextVarItemWithinBounds@CTxStatusInfo@@SAJPEAPEAX0PEAK1@Z; CTxStatusInfo::GetNextVarItemWithinBounds(void * *,void * *,ulong *,ulong *)
0x18004d02f  mov     ebx, eax
0x18004d031  test    eax, eax
0x18004d033  js      loc_18004D18C
0x18004d039  mov     ebx, [rsp+200h+var_1AC]
0x18004d03d  test    r12d, r12d
0x18004d040  jnz     short loc_18004D08B
0x18004d042  test    ebx, ebx
0x18004d044  jz      short loc_18004D055
0x18004d046  mov     r15, [rsp+200h+var_1A8]
0x18004d04b  test    r15, r15
0x18004d04e  jz      short loc_18004D055
0x18004d050  cmp     [r15], r12b
0x18004d053  jnz     short loc_18004D090
0x18004d055  lea     r8, Class; char *
0x18004d05c  mov     edx, 0FFh; unsigned __int64
0x18004d061  lea     rcx, [rbp+100h+var_140]; char *
0x18004d065  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x18004d06a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004d06e  lea     r10, [rbp+100h+var_140]
0x18004d072  inc     rbx
0x18004d075  cmp     byte ptr [r10+rbx], 0
0x18004d07a  jnz     short loc_18004D072
0x18004d07c  lea     r15, [rbp+100h+var_140]
0x18004d080  mov     [rsp+200h+var_1AC], ebx
0x18004d084  mov     [rsp+200h+var_1A8], r15
0x18004d089  jmp     short loc_18004D090
0x18004d08b  mov     r15, [rsp+200h+var_1A8]
0x18004d090  lea     eax, [rbx+1]
0x18004d093  mov     ecx, eax; cb
0x18004d095  mov     [rbp+100h+var_180], rax
0x18004d099  call    cs:__imp_CoTaskMemAlloc
0x18004d09f  mov     rcx, [r14+8]
0x18004d0a3  mov     [rcx+r12*8], rax
0x18004d0a7  mov     rax, [r14+8]
0x18004d0ab  mov     rcx, [rax+r12*8]; char *
0x18004d0af  test    rcx, rcx
0x18004d0b2  jz      loc_18004D16A
0x18004d0b8  test    ebx, ebx
0x18004d0ba  jz      short loc_18004D0CA
0x18004d0bc  mov     rdx, [rbp+100h+var_180]; unsigned __int64
0x18004d0c0  mov     r8, r15; char *
0x18004d0c3  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x18004d0c8  jmp     short loc_18004D0CD
0x18004d0ca  mov     byte ptr [rcx], 0
0x18004d0cd  lea     r9, [rsp+200h+var_1B0]; unsigned int *
0x18004d0d2  lea     r8, [rsp+200h+var_1AC]; unsigned int *
0x18004d0d7  lea     rdx, [rsp+200h+var_1A8]; void **
0x18004d0dc  lea     rcx, [rsp+200h+var_198]; void **
0x18004d0e1  call    ?GetNextVarItemWithinBounds@CTxStatusInfo@@SAJPEAPEAX0PEAK1@Z; CTxStatusInfo::GetNextVarItemWithinBounds(void * *,void * *,ulong *,ulong *)
0x18004d0e6  mov     ebx, eax
0x18004d0e8  test    eax, eax
0x18004d0ea  js      short loc_18004D158
0x18004d0ec  mov     r15d, [rsp+200h+var_1AC]
  ... truncated ...
```
