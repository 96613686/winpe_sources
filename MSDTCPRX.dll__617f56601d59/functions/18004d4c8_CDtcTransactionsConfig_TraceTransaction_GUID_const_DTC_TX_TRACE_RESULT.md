# CDtcTransactionsConfig::TraceTransaction(_GUID const &,_DTC_TX_TRACE_RESULT *)

- ea: `0x18004d4c8`
- end: `0x18004d8f3`
- name: `?TraceTransaction@CDtcTransactionsConfig@@QEAAJAEBU_GUID@@PEAW4_DTC_TX_TRACE_RESULT@@@Z`
- size: `1067`
- prototype: `__int64 __fastcall(CDtcTransactionsConfig *__hidden this, const struct _GUID *, enum _DTC_TX_TRACE_RESULT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004bc54`

## callees

- `0x180003cf0`
- `0x180048d50`
- `0x180049010`
- `0x18004d4c8`
- `0x18007ee20`
- `0x18007f82c`
- `0x18007f8a0`
- `0x180081dd0`
- `0x180085010`

## string_xrefs

- `0x18004d53b`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004d589`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004d61e`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004d6b0`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004d7bd`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004d7ee`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004d8ac`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004d50f`: `CDtcTransactionsConfig::TraceTransaction`
- `0x18004d57e`: `CDtcTransactionsConfig::TraceTransaction`
- `0x18004d5c7`: `CDtcTransactionsConfig::TraceTransaction`
- `0x18004d613`: `CDtcTransactionsConfig::TraceTransaction`
- `0x18004d6a5`: `CDtcTransactionsConfig::TraceTransaction`
- `0x18004d79d`: `CDtcTransactionsConfig::TraceTransaction`
- `0x18004d7ce`: `CDtcTransactionsConfig::TraceTransaction`
- `0x18004d7da`: `Failed to create CSendReceive.`

## pseudocode

```c
__int64 __fastcall CDtcTransactionsConfig::TraceTransaction(
        CDtcConfig **this,
        const struct _GUID *a2,
        enum _DTC_TX_TRACE_RESULT *a3)
{
  struct IConnectionDispenser *v6; // r14
  CIConnSink *v7; // rdi
  struct INameObject *v8; // r12
  int v9; // r15d
  int ConnectionDispenser; // ebx
  const wchar_t *v11; // rax
  __int64 v12; // r9
  const wchar_t *v13; // rax
  __int64 v14; // r9
  struct CSendReceive *Instance; // rax
  int PartnerNamedObject; // eax
  __int64 v18; // [rsp+28h] [rbp-41h]
  __int64 v19; // [rsp+28h] [rbp-41h]
  __int64 v20; // [rsp+38h] [rbp-31h]
  int v21; // [rsp+50h] [rbp-19h] BYREF
  struct IConnectionDispenser *v22; // [rsp+58h] [rbp-11h] BYREF
  struct INameObject *v23; // [rsp+60h] [rbp-9h] BYREF
  __int64 v24; // [rsp+68h] [rbp-1h] BYREF
  enum _DTC_TX_TRACE_RESULT *v25; // [rsp+70h] [rbp+7h]
  __int128 v26; // [rsp+78h] [rbp+Fh] BYREF

  v25 = a3;
  v22 = 0;
  v23 = 0;
  v6 = 0;
  v21 = 0;
  v7 = 0;
  v24 = 0;
  v8 = 0;
  v9 = 0;
  v26 = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    940,
    L"CDtcTransactionsConfig::TraceTransaction",
    0,
    L"In");
  v26 = (__int128)*a2;
  if ( a3 )
  {
    ConnectionDispenser = CDtcConfig::GetConnectionDispenser(this[3], &v22);
    if ( ConnectionDispenser >= 0 )
    {
      Instance = CSendReceive::CreateInstance();
      v7 = Instance;
      if ( Instance )
      {
        if ( (*(unsigned int (__fastcall **)(struct CSendReceive *))(*(_QWORD *)Instance + 32LL))(Instance) )
        {
          (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v7 + 160LL))(v7);
          (*((void (__fastcall **)(char *))this[1] + 1))((char *)this + 8);
          (*(void (__fastcall **)(CIConnSink *, unsigned __int64))(*(_QWORD *)v7 + 136LL))(
            v7,
            (unsigned __int64)(this + 1) & -(__int64)(this != 0));
          PartnerNamedObject = CDtcConfig::GetPartnerNamedObject(this[3], &v23);
          if ( PartnerNamedObject < 0 )
          {
            LODWORD(v18) = PartnerNamedObject;
            TraceStringInline(
              15,
              1,
              L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
              981,
              L"CDtcTransactionsConfig::TraceTransaction",
              v18,
              L"GetPartnerNamedObject failed.");
            return 0;
          }
          v8 = v23;
          v6 = v22;
          ConnectionDispenser = (*(__int64 (__fastcall **)(CIConnSink *, struct IConnectionDispenser *, struct INameObject *, __int64, int))(*(_QWORD *)v7 + 248LL))(
                                  v7,
                                  v22,
                                  v23,
                                  1,
                                  54);
          if ( ConnectionDispenser >= 0 )
          {
            ConnectionDispenser = (*(__int64 (__fastcall **)(CIConnSink *, __int64, __int64, __int128 *, int *, __int64 *, _DWORD, _QWORD))(*(_QWORD *)v7 + 96LL))(
                                    v7,
                                    8448,
                                    16,
                                    &v26,
                                    &v21,
                                    &v24,
                                    0,
                                    0);
            if ( !ConnectionDispenser )
            {
              if ( v21 == 8449 )
              {
                ConnectionDispenser = 0;
              }
              else
              {
                ConnectionDispenser = -2147467259;
                if ( v21 == 8450 )
                  v9 = 1;
                else
                  v9 = 6;
              }
              LODWORD(v20) = v21;
              TraceStringInline(
                15,
                3,
                L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
                1029,
                L"CDtcTransactionsConfig::TraceTransaction",
                0,
                L"Received MTAG: %d",
                v20);
              goto LABEL_23;
            }
            v9 = 6;
            v11 = L"SendReceive failed.";
            v12 = 1004;
          }
          else
          {
            v11 = L"Failed Connect.";
            v12 = 991;
          }
          goto LABEL_3;
        }
        LODWORD(v18) = ConnectionDispenser;
        TraceStringInline(
          15,
          1,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
          963,
          L"CDtcTransactionsConfig::TraceTransaction",
          v18,
          L"CSendReceive initialization failed.");
        CIConnSink::DeleteObject(v7);
        v7 = 0;
      }
      ConnectionDispenser = -2147024882;
      v13 = L"Failed to create CSendReceive.";
      v14 = 971;
    }
    else
    {
      v13 = L"GetConnectionDispenser failed.";
      v14 = 954;
    }
    LODWORD(v18) = ConnectionDispenser;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
      v14,
      L"CDtcTransactionsConfig::TraceTransaction",
      v18,
      v13);
    v6 = v22;
    goto LABEL_23;
  }
  ConnectionDispenser = -2147024809;
  v11 = L"Invalid argument pTraceResult.";
  v12 = 947;
LABEL_3:
  LODWORD(v18) = ConnectionDispenser;
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    v12,
    L"CDtcTransactionsConfig::TraceTransaction",
    v18,
    v11);
LABEL_23:
  if ( v24 )
    (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v7 + 120LL))(v7);
  if ( ConnectionDispenser < 0 )
    *(_DWORD *)v25 = v9;
  if ( v6 )
    (*(void (__fastcall **)(struct IConnectionDispenser *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v8 )
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v7 )
  {
    CSendReceive::Cancel(v7);
    (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v7 + 144LL))(v7);
    (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v7 + 272LL))(v7);
    (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v7 + 168LL))(v7);
  }
  LODWORD(v19) = ConnectionDispenser;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    1053,
    L"CDtcTransactionsConfig::TraceTransaction",
    v19,
    L"Out");
  return (unsigned int)ConnectionDispenser;
}

```

## disassembly

```asm
0x18004d4c8  mov     [rsp-8+arg_18], rbx
0x18004d4cd  push    rbp
0x18004d4ce  push    rsi
0x18004d4cf  push    rdi
0x18004d4d0  push    r12
0x18004d4d2  push    r13
0x18004d4d4  push    r14
0x18004d4d6  push    r15
0x18004d4d8  lea     rbp, [rsp-27h]
0x18004d4dd  sub     rsp, 90h
0x18004d4e4  mov     rax, cs:__security_cookie
0x18004d4eb  xor     rax, rsp
0x18004d4ee  mov     [rbp+57h+var_38], rax
0x18004d4f2  mov     r13, rcx
0x18004d4f5  mov     [rbp+57h+var_50], r8
0x18004d4f9  xor     ecx, ecx
0x18004d4fb  lea     rax, aIn_0; "In"
0x18004d502  mov     [rsp+0C0h+var_90], rax
0x18004d507  mov     rbx, rdx
0x18004d50a  mov     [rsp+0C0h+var_98], rcx
0x18004d50f  lea     rax, aCdtctransactio; "CDtcTransactionsConfig::TraceTransactio"...
0x18004d516  mov     rsi, r8
0x18004d519  mov     [rbp+57h+var_68], rcx
0x18004d51d  lea     edx, [rcx+6]
0x18004d520  mov     [rbp+57h+var_60], rcx
0x18004d524  mov     r14d, ecx
0x18004d527  mov     [rbp+57h+var_70], ecx
0x18004d52a  mov     edi, ecx
0x18004d52c  mov     [rbp+57h+var_58], rcx
0x18004d530  mov     r12d, ecx
0x18004d533  mov     [rsp+0C0h+var_A0], rax
0x18004d538  mov     r15d, ecx
0x18004d53b  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004d542  xorps   xmm0, xmm0
0x18004d545  lea     ecx, [rdx+9]
0x18004d548  mov     r9d, 3ACh
0x18004d54e  movups  [rbp+57h+var_48], xmm0
0x18004d552  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004d557  movups  xmm0, xmmword ptr [rbx]
0x18004d55a  movdqu  [rbp+57h+var_48], xmm0
0x18004d55f  test    rsi, rsi
0x18004d562  jnz     short loc_18004D5A4
0x18004d564  mov     ebx, 80070057h
0x18004d569  lea     rax, aInvalidArgumen_0; "Invalid argument pTraceResult."
0x18004d570  mov     r9d, 3B3h
0x18004d576  lea     edx, [rsi+1]
0x18004d579  mov     [rsp+0C0h+var_90], rax
0x18004d57e  lea     r13, aCdtctransactio; "CDtcTransactionsConfig::TraceTransactio"...
0x18004d585  mov     dword ptr [rsp+0C0h+var_98], ebx
0x18004d589  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004d590  mov     ecx, 0Fh
0x18004d595  mov     [rsp+0C0h+var_A0], r13
0x18004d59a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004d59f  jmp     loc_18004D80C
0x18004d5a4  lea     r14, [r13+18h]
0x18004d5a8  mov     rcx, [r14]; this
0x18004d5ab  lea     rdx, [rbp+57h+var_68]; struct IConnectionDispenser **
0x18004d5af  call    ?GetConnectionDispenser@CDtcConfig@@QEAAJPEAPEAUIConnectionDispenser@@@Z; CDtcConfig::GetConnectionDispenser(IConnectionDispenser * *)
0x18004d5b4  mov     ebx, eax
0x18004d5b6  test    eax, eax
0x18004d5b8  jns     short loc_18004D5D8
0x18004d5ba  lea     rax, aGetconnectiond_0; "GetConnectionDispenser failed."
0x18004d5c1  mov     r9d, 3BAh
0x18004d5c7  lea     r13, aCdtctransactio; "CDtcTransactionsConfig::TraceTransactio"...
0x18004d5ce  mov     edx, 1
0x18004d5d3  jmp     loc_18004D7E9
0x18004d5d8  call    ?CreateInstance@CSendReceive@@SAPEAV1@XZ; CSendReceive::CreateInstance(void)
0x18004d5dd  mov     rdi, rax
0x18004d5e0  mov     esi, 1
0x18004d5e5  test    rax, rax
0x18004d5e8  jz      loc_18004D7CE
0x18004d5ee  mov     rcx, [rax]
0x18004d5f1  mov     rax, [rcx+20h]
0x18004d5f5  mov     rcx, rdi
0x18004d5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d5fd  test    eax, eax
0x18004d5ff  jnz     short loc_18004D643
0x18004d601  lea     rax, aCsendreceiveIn; "CSendReceive initialization failed."
0x18004d608  mov     r9d, 3C3h
0x18004d60e  mov     [rsp+0C0h+var_90], rax
0x18004d613  lea     r13, aCdtctransactio; "CDtcTransactionsConfig::TraceTransactio"...
0x18004d61a  mov     dword ptr [rsp+0C0h+var_98], ebx
0x18004d61e  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004d625  mov     edx, esi
0x18004d627  mov     [rsp+0C0h+var_A0], r13
0x18004d62c  lea     ecx, [rsi+0Eh]
0x18004d62f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004d634  mov     rcx, rdi; this
0x18004d637  call    ?DeleteObject@CIConnSink@@UEAAXXZ; CIConnSink::DeleteObject(void)
0x18004d63c  xor     edi, edi
0x18004d63e  jmp     loc_18004D7D5
0x18004d643  mov     rax, [rdi]
0x18004d646  mov     rcx, rdi
0x18004d649  mov     rax, [rax+0A0h]
0x18004d650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d655  lea     rbx, [r13+8]
0x18004d659  mov     rax, [rbx]
0x18004d65c  mov     rcx, rbx
0x18004d65f  mov     rax, [rax+8]
0x18004d663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d668  mov     rax, [rdi]
0x18004d66b  neg     r13
0x18004d66e  mov     rcx, rdi
0x18004d671  sbb     rdx, rdx
0x18004d674  and     rdx, rbx
0x18004d677  mov     rax, [rax+88h]
0x18004d67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d683  mov     rcx, [r14]; this
0x18004d686  lea     rdx, [rbp+57h+var_60]; struct INameObject **
0x18004d68a  call    ?GetPartnerNamedObject@CDtcConfig@@QEAAJPEAPEAUINameObject@@@Z; CDtcConfig::GetPartnerNamedObject(INameObject * *)
0x18004d68f  test    eax, eax
0x18004d691  jns     short loc_18004D6CF
0x18004d693  lea     rdx, aGetpartnername; "GetPartnerNamedObject failed."
0x18004d69a  mov     r9d, 3D5h
0x18004d6a0  mov     [rsp+0C0h+var_90], rdx
0x18004d6a5  lea     r13, aCdtctransactio; "CDtcTransactionsConfig::TraceTransactio"...
0x18004d6ac  mov     dword ptr [rsp+0C0h+var_98], eax
0x18004d6b0  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004d6b7  mov     edx, esi
0x18004d6b9  mov     [rsp+0C0h+var_A0], r13
0x18004d6be  mov     ecx, 0Fh
0x18004d6c3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004d6c8  xor     eax, eax
0x18004d6ca  jmp     loc_18004D8CC
0x18004d6cf  mov     rax, [rdi]
0x18004d6d2  mov     r9d, esi
0x18004d6d5  mov     r12, [rbp+57h+var_60]
0x18004d6d9  mov     rcx, rdi
0x18004d6dc  mov     r14, [rbp+57h+var_68]
0x18004d6e0  mov     r8, r12
0x18004d6e3  mov     rdx, r14
0x18004d6e6  mov     dword ptr [rsp+0C0h+var_A0], 36h ; '6'
0x18004d6ee  mov     rax, [rax+0F8h]
0x18004d6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6fa  mov     ebx, eax
0x18004d6fc  test    eax, eax
0x18004d6fe  jns     short loc_18004D714
0x18004d700  lea     rax, aFailedConnect; "Failed Connect."
0x18004d707  mov     r9d, 3DFh
0x18004d70d  mov     edx, esi
0x18004d70f  jmp     loc_18004D579
0x18004d714  mov     rax, [rdi]
0x18004d717  lea     rcx, [rbp+57h+var_58]
0x18004d71b  mov     [rsp+0C0h+var_88], r15
0x18004d720  lea     r9, [rbp+57h+var_48]
0x18004d724  mov     dword ptr [rsp+0C0h+var_90], r15d
0x18004d729  mov     edx, 2100h
0x18004d72e  mov     [rsp+0C0h+var_98], rcx
0x18004d733  mov     r8d, 10h
0x18004d739  mov     rax, [rax+60h]
0x18004d73d  lea     rcx, [rbp+57h+var_70]
0x18004d741  mov     [rsp+0C0h+var_A0], rcx
0x18004d746  mov     rcx, rdi
0x18004d749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d74e  mov     ebx, eax
0x18004d750  test    eax, eax
0x18004d752  jz      short loc_18004D769
0x18004d754  mov     r15d, 6
0x18004d75a  lea     rax, aSendreceiveFai; "SendReceive failed."
0x18004d761  mov     r9d, 3ECh
0x18004d767  jmp     short loc_18004D70D
0x18004d769  mov     ecx, [rbp+57h+var_70]
0x18004d76c  mov     eax, ecx
0x18004d76e  sub     eax, 2101h
0x18004d773  jz      short loc_18004D78B
0x18004d775  mov     ebx, 80004005h
0x18004d77a  sub     eax, esi
0x18004d77c  jz      short loc_18004D786
0x18004d77e  mov     r15d, 6
0x18004d784  jmp     short loc_18004D78D
0x18004d786  mov     r15d, esi
0x18004d789  jmp     short loc_18004D78D
0x18004d78b  xor     ebx, ebx
0x18004d78d  mov     dword ptr [rsp+0C0h+var_88], ecx
0x18004d791  lea     rax, aReceivedMtagD; "Received MTAG: %d"
0x18004d798  mov     [rsp+0C0h+var_90], rax
0x18004d79d  lea     r13, aCdtctransactio; "CDtcTransactionsConfig::TraceTransactio"...
0x18004d7a4  mov     edx, 3
0x18004d7a9  mov     [rsp+0C0h+var_98], 0
0x18004d7b2  mov     r9d, 405h
0x18004d7b8  mov     [rsp+0C0h+var_A0], r13
0x18004d7bd  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004d7c4  lea     ecx, [rdx+0Ch]
0x18004d7c7  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004d7cc  jmp     short loc_18004D80C
0x18004d7ce  lea     r13, aCdtctransactio; "CDtcTransactionsConfig::TraceTransactio"...
0x18004d7d5  mov     ebx, 8007000Eh
0x18004d7da  lea     rax, aFailedToCreate_6; "Failed to create CSendReceive."
0x18004d7e1  mov     r9d, 3CBh
0x18004d7e7  mov     edx, esi
0x18004d7e9  mov     [rsp+0C0h+var_90], rax
0x18004d7ee  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004d7f5  mov     dword ptr [rsp+0C0h+var_98], ebx
0x18004d7f9  mov     ecx, 0Fh
0x18004d7fe  mov     [rsp+0C0h+var_A0], r13
0x18004d803  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004d808  mov     r14, [rbp+57h+var_68]
0x18004d80c  mov     rdx, [rbp+57h+var_58]
0x18004d810  test    rdx, rdx
0x18004d813  jz      short loc_18004D824
0x18004d815  mov     rax, [rdi]
0x18004d818  mov     rcx, rdi
0x18004d81b  mov     rax, [rax+78h]
0x18004d81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d824  test    ebx, ebx
0x18004d826  jns     short loc_18004D82F
0x18004d828  mov     rax, [rbp+57h+var_50]
0x18004d82c  mov     [rax], r15d
0x18004d82f  test    r14, r14
0x18004d832  jz      short loc_18004D843
0x18004d834  mov     rax, [r14]
0x18004d837  mov     rcx, r14
0x18004d83a  mov     rax, [rax+10h]
0x18004d83e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d843  test    r12, r12
0x18004d846  jz      short loc_18004D858
0x18004d848  mov     rax, [r12]
0x18004d84c  mov     rcx, r12
0x18004d84f  mov     rax, [rax+10h]
0x18004d853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d858  test    rdi, rdi
0x18004d85b  jz      short loc_18004D89B
0x18004d85d  mov     rcx, rdi; this
0x18004d860  call    ?Cancel@CSendReceive@@QEAAJXZ; CSendReceive::Cancel(void)
0x18004d865  mov     rax, [rdi]
0x18004d868  mov     rcx, rdi
0x18004d86b  mov     rax, [rax+90h]
0x18004d872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d877  mov     rax, [rdi]
0x18004d87a  mov     rcx, rdi
0x18004d87d  mov     rax, [rax+110h]
0x18004d884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d889  mov     rax, [rdi]
0x18004d88c  mov     rcx, rdi
0x18004d88f  mov     rax, [rax+0A8h]
0x18004d896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d89b  mov     edx, 6
0x18004d8a0  lea     rax, aOut; "Out"
0x18004d8a7  mov     [rsp+0C0h+var_90], rax
0x18004d8ac  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004d8b3  mov     dword ptr [rsp+0C0h+var_98], ebx
0x18004d8b7  mov     r9d, 41Dh
0x18004d8bd  mov     [rsp+0C0h+var_A0], r13
0x18004d8c2  lea     ecx, [rdx+9]
0x18004d8c5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004d8ca  mov     eax, ebx
0x18004d8cc  mov     rcx, [rbp+57h+var_38]
0x18004d8d0  xor     rcx, rsp; StackCookie
0x18004d8d3  call    __security_check_cookie
0x18004d8d8  mov     rbx, [rsp+0C0h+arg_18]
0x18004d8e0  add     rsp, 90h
0x18004d8e7  pop     r15
0x18004d8e9  pop     r14
0x18004d8eb  pop     r13
0x18004d8ed  pop     r12
0x18004d8ef  pop     rdi
0x18004d8f0  pop     rsi
0x18004d8f1  pop     rbp
0x18004d8f2  retn
```
