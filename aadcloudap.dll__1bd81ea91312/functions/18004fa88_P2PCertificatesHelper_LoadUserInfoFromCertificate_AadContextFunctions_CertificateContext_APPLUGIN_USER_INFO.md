# P2PCertificatesHelper::LoadUserInfoFromCertificate(AadContextFunctions *,CertificateContext &,_APPLUGIN_USER_INFO * *)

- ea: `0x18004fa88`
- end: `0x18004ff01`
- name: `?LoadUserInfoFromCertificate@P2PCertificatesHelper@@SAJPEAVAadContextFunctions@@AEAVCertificateContext@@PEAPEAU_APPLUGIN_USER_INFO@@@Z`
- size: `1145`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, struct CertificateContext *, struct _APPLUGIN_USER_INFO **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000cf50`

## callees

- `0x180004a24`
- `0x180006530`
- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x1800090d0`
- `0x180018ac8`
- `0x180036b3c`
- `0x18004eb00`
- `0x18004fa88`
- `0x180050170`
- `0x180071e14`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fc61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fc6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fc75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fc61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fc6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fc75`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004fc57`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004fc57`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall P2PCertificatesHelper::LoadUserInfoFromCertificate(
        struct AadContextFunctions *a1,
        struct CertificateContext *a2,
        struct _APPLUGIN_USER_INFO **a3)
{
  PSID *v6; // rdi
  char v7; // r12
  int GroupsSIDsFromCert; // ecx
  unsigned int v9; // r14d
  PSID *v10; // rax
  int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rcx
  PSID *v14; // r15
  unsigned int v15; // ebx
  __int64 v16; // rax
  int v17; // ecx
  unsigned int v18; // ebx
  __int64 v20; // [rsp+20h] [rbp-A9h]
  int v21; // [rsp+30h] [rbp-99h]
  __int64 v22; // [rsp+30h] [rbp-99h]
  __int64 v23; // [rsp+80h] [rbp-49h] BYREF
  __int64 v24; // [rsp+88h] [rbp-41h] BYREF
  __int128 v25; // [rsp+90h] [rbp-39h] BYREF
  __int64 v26; // [rsp+A0h] [rbp-29h]
  __int128 v27; // [rsp+A8h] [rbp-21h]
  int v28; // [rsp+B8h] [rbp-11h]
  _BYTE v29[96]; // [rsp+C0h] [rbp-9h] BYREF
  int v30; // [rsp+130h] [rbp+67h] BYREF
  __int64 v31; // [rsp+148h] [rbp+7Fh] BYREF

  v30 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v23);
  v31 = 0;
  v6 = 0;
  v7 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 10;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    v29,
    "p2pcertificateshelper.cpp",
    "P2PCertificatesHelper::LoadUserInfoFromCertificate",
    &v30);
  if ( a1 && *(_QWORD *)a2 && a3 )
  {
    *a3 = 0;
    GroupsSIDsFromCert = P2PCertificatesHelper::ParseUserCertificateSubject(a2, &v23, &v31);
    v30 = GroupsSIDsFromCert;
    if ( GroupsSIDsFromCert < 0 )
    {
      v21 = 318;
LABEL_11:
      WPPTraceLogA(
        2,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        2,
        GroupsSIDsFromCert,
        "p2pcertificateshelper.cpp",
        v21,
        "NTSTATUS",
        &base);
      goto LABEL_35;
    }
    GroupsSIDsFromCert = P2PCertificatesHelper::GetGroupsSIDsFromCert(a2, &v25);
    v30 = GroupsSIDsFromCert;
    if ( GroupsSIDsFromCert < 0 )
    {
      v21 = 321;
      goto LABEL_11;
    }
    v9 = v26;
    if ( (_DWORD)v26 )
    {
      v10 = (PSID *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, __int64))(*(_QWORD *)a1 + 8LL))(
                      a1,
                      64,
                      8LL * (unsigned int)v26);
      v6 = v10;
      if ( !v10 )
      {
        GroupsSIDsFromCert = -1073741801;
        v30 = -1073741801;
        v21 = 332;
        goto LABEL_11;
      }
      memset_0(v10, 0, 8LL * v9);
      v7 = 1;
      v11 = 0;
      v12 = v25;
      v24 = v25;
      if ( (_QWORD)v25 )
      {
        while ( 1 )
        {
          if ( !v12 )
            ATL::AtlThrowImpl(-2147467259);
          if ( !ConvertStringSidToSidW(*(LPCWSTR *)(v12 + 16), &v6[v11]) )
          {
            v13 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
            v30 = v13;
            if ( (int)v13 < 0 )
              break;
          }
          ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(v13, &v24);
          v12 = v24;
          if ( !v24 )
            goto LABEL_22;
          ++v11;
        }
        WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v13, "p2pcertificateshelper.cpp", 348, "NTSTATUS", &base);
        v14 = v6;
        v15 = 0;
        do
        {
LABEL_31:
          if ( v14[v15] )
            (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 16LL))(a1);
          ++v15;
        }
        while ( v15 < v9 );
        goto LABEL_34;
      }
    }
LABEL_22:
    v16 = (*(__int64 (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 48LL))(a1);
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, PSID *, _QWORD, _QWORD, _QWORD, _QWORD, __int64, _QWORD, _QWORD, _QWORD, _DWORD, struct _APPLUGIN_USER_INFO **))(v16 + 48))(
            2,
            v31,
            v9,
            v6,
            0,
            0,
            0,
            0,
            v23,
            0,
            0,
            0,
            0,
            a3);
    v30 = v17;
    if ( v17 < 0 )
    {
      LODWORD(v22) = 370;
      LODWORD(v20) = v17;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v20, "p2pcertificateshelper.cpp", v22, "NTSTATUS", &base);
      goto LABEL_28;
    }
    if ( !*a3 )
    {
      LODWORD(v22) = 375;
      LODWORD(v20) = -2147187647;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v20, "p2pcertificateshelper.cpp", v22, "HRESULT", &base);
      v30 = -1073445823;
      goto LABEL_28;
    }
  }
  else
  {
    v9 = 0;
    v30 = -1073741811;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -1073741811, "p2pcertificateshelper.cpp", 312, "NTSTATUS", &base);
  }
  if ( !a1 )
    goto LABEL_37;
LABEL_28:
  v14 = v6;
  if ( !v6 )
    goto LABEL_35;
  if ( v7 )
  {
    v15 = 0;
    if ( v9 )
      goto LABEL_31;
  }
LABEL_34:
  (*(void (__fastcall **)(struct AadContextFunctions *, PSID *))(*(_QWORD *)a1 + 16LL))(a1, v6);
LABEL_35:
  if ( v31 )
    (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 16LL))(a1);
LABEL_37:
  v18 = v30;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v29);
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&v25);
  ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
  return v18;
}

```

## disassembly

```asm
0x18004fa88  mov     [rsp-8+arg_8], rbx
0x18004fa8d  push    rbp
0x18004fa8e  push    rsi
0x18004fa8f  push    rdi
0x18004fa90  push    r12
0x18004fa92  push    r13
0x18004fa94  push    r14
0x18004fa96  push    r15
0x18004fa98  lea     rbp, [rsp-27h]
0x18004fa9d  sub     rsp, 0F0h
0x18004faa4  mov     r15, r8
0x18004faa7  mov     rbx, rdx
0x18004faaa  mov     rsi, rcx
0x18004faad  xor     r13d, r13d
0x18004fab0  mov     [rbp+57h+arg_0], r13d
0x18004fab4  lea     rcx, [rbp+57h+var_A0]; void *
0x18004fab8  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004fabd  nop
0x18004fabe  mov     [rbp+57h+arg_18], r13
0x18004fac2  mov     edi, r13d
0x18004fac5  mov     r12b, r13b
0x18004fac8  xorps   xmm0, xmm0
0x18004facb  movdqu  [rbp+57h+var_90], xmm0
0x18004fad0  mov     [rbp+57h+var_80], r13
0x18004fad4  xorps   xmm1, xmm1
0x18004fad7  movdqu  [rbp+57h+var_78], xmm1
0x18004fadc  mov     [rbp+57h+var_68], 0Ah
0x18004fae3  lea     r9, [rbp+57h+arg_0]
0x18004fae7  lea     r8, aP2pcertificate_0; "P2PCertificatesHelper::LoadUserInfoFrom"...
0x18004faee  lea     r14, aOnecoreuapDsEx_12+21h; "p2pcertificateshelper.cpp"
0x18004faf5  mov     rdx, r14
0x18004faf8  lea     rcx, [rbp+57h+var_60]
0x18004fafc  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18004fb01  nop
0x18004fb02  test    rsi, rsi
0x18004fb05  jz      loc_18004FDFD
0x18004fb0b  cmp     [rbx], r13
0x18004fb0e  jz      loc_18004FDFD
0x18004fb14  test    r15, r15
0x18004fb17  jz      loc_18004FDFD
0x18004fb1d  mov     [r15], r13
0x18004fb20  lea     r8, [rbp+57h+arg_18]
0x18004fb24  lea     rdx, [rbp+57h+var_A0]
0x18004fb28  mov     rcx, rbx
0x18004fb2b  call    ?ParseUserCertificateSubject@P2PCertificatesHelper@@CAJAEAVCertificateContext@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAX@Z; P2PCertificatesHelper::ParseUserCertificateSubject(CertificateContext &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,void * *)
0x18004fb30  mov     ecx, eax
0x18004fb32  mov     [rbp+57h+arg_0], eax
0x18004fb35  test    eax, eax
0x18004fb37  jns     short loc_18004FB5B
0x18004fb39  lea     rax, base
0x18004fb40  mov     [rsp+120h+var_E0], rax
0x18004fb45  lea     rax, aNtstatus; "NTSTATUS"
0x18004fb4c  mov     [rsp+120h+var_E8], rax
0x18004fb51  mov     dword ptr [rsp+120h+var_F0], 13Eh
0x18004fb59  jmp     short loc_18004FB90
0x18004fb5b  lea     rdx, [rbp+57h+var_90]
0x18004fb5f  mov     rcx, rbx
0x18004fb62  call    ?GetGroupsSIDsFromCert@P2PCertificatesHelper@@SAJAEAVCertificateContext@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; P2PCertificatesHelper::GetGroupsSIDsFromCert(CertificateContext &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x18004fb67  mov     ecx, eax
0x18004fb69  mov     [rbp+57h+arg_0], eax
0x18004fb6c  test    eax, eax
0x18004fb6e  jns     short loc_18004FB97
0x18004fb70  lea     rax, base
0x18004fb77  mov     [rsp+120h+var_E0], rax
0x18004fb7c  lea     rax, aNtstatus; "NTSTATUS"
0x18004fb83  mov     [rsp+120h+var_E8], rax
0x18004fb88  mov     dword ptr [rsp+120h+var_F0], 141h
0x18004fb90  mov     [rsp+120h+var_F8], r14
0x18004fb95  jmp     short loc_18004FBFE
0x18004fb97  mov     r14d, dword ptr [rbp+57h+var_80]
0x18004fb9b  test    r14d, r14d
0x18004fb9e  jz      loc_18004FCF4
0x18004fba4  mov     ebx, r14d
0x18004fba7  shl     rbx, 3
0x18004fbab  mov     rax, [rsi]
0x18004fbae  mov     r8, rbx
0x18004fbb1  mov     edx, 40h ; '@'
0x18004fbb6  mov     rcx, rsi
0x18004fbb9  mov     rax, [rax+8]
0x18004fbbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fbc2  mov     rdi, rax
0x18004fbc5  test    rax, rax
0x18004fbc8  jnz     short loc_18004FC1F
0x18004fbca  mov     ecx, 0C0000017h
0x18004fbcf  mov     [rbp+57h+arg_0], ecx
0x18004fbd2  lea     rax, base
0x18004fbd9  mov     [rsp+120h+var_E0], rax
0x18004fbde  lea     rax, aNtstatus; "NTSTATUS"
0x18004fbe5  mov     [rsp+120h+var_E8], rax
0x18004fbea  mov     dword ptr [rsp+120h+var_F0], 14Ch
0x18004fbf2  lea     rax, aOnecoreuapDsEx_12+21h; "p2pcertificateshelper.cpp"
0x18004fbf9  mov     [rsp+120h+var_F8], rax
0x18004fbfe  mov     dword ptr [rsp+120h+var_100], ecx
0x18004fc02  mov     ebx, 2
0x18004fc07  mov     r9d, ebx
0x18004fc0a  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004fc11  xor     edx, edx
0x18004fc13  mov     ecx, ebx
0x18004fc15  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004fc1a  jmp     loc_18004FE9D
0x18004fc1f  mov     r8, rbx; Size
0x18004fc22  xor     edx, edx; Val
0x18004fc24  mov     rcx, rdi; void *
0x18004fc27  call    memset_0
0x18004fc2c  mov     r12b, 1
0x18004fc2f  mov     ebx, r13d
0x18004fc32  mov     rcx, qword ptr [rbp+57h+var_90]
0x18004fc36  mov     [rbp+57h+var_98], rcx
0x18004fc3a  test    rcx, rcx
0x18004fc3d  jz      loc_18004FCF4
0x18004fc43  test    rcx, rcx
0x18004fc46  jz      loc_18004FEF6
0x18004fc4c  movsxd  rax, ebx
0x18004fc4f  lea     rdx, [rdi+rax*8]; Sid
0x18004fc53  mov     rcx, [rcx+10h]; StringSid
0x18004fc57  call    cs:__imp_ConvertStringSidToSidW
0x18004fc5d  test    eax, eax
0x18004fc5f  jnz     short loc_18004FC8B
0x18004fc61  call    cs:__imp_GetLastError
0x18004fc67  test    eax, eax
0x18004fc69  jg      short loc_18004FC75
0x18004fc6b  call    cs:__imp_GetLastError
0x18004fc71  mov     ecx, eax
0x18004fc73  jmp     short loc_18004FC84
0x18004fc75  call    cs:__imp_GetLastError
0x18004fc7b  movzx   ecx, ax
0x18004fc7e  or      ecx, 0C0070000h
0x18004fc84  mov     [rbp+57h+arg_0], ecx
0x18004fc87  test    ecx, ecx
0x18004fc89  js      short loc_18004FCA1
0x18004fc8b  lea     rdx, [rbp+57h+var_98]
0x18004fc8f  call    ?GetNext@?$CAtlList@UJsonKeyStringValueItem@@V?$CElementTraits@UJsonKeyStringValueItem@@@ATL@@@ATL@@QEAAAEAUJsonKeyStringValueItem@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(__POSITION * &)
0x18004fc94  mov     rcx, [rbp+57h+var_98]
0x18004fc98  test    rcx, rcx
0x18004fc9b  jz      short loc_18004FCF4
0x18004fc9d  inc     ebx
0x18004fc9f  jmp     short loc_18004FC43
0x18004fca1  lea     rax, base
0x18004fca8  mov     [rsp+120h+var_E0], rax
0x18004fcad  lea     rax, aNtstatus; "NTSTATUS"
0x18004fcb4  mov     [rsp+120h+var_E8], rax
0x18004fcb9  mov     dword ptr [rsp+120h+var_F0], 15Ch
0x18004fcc1  lea     rax, aOnecoreuapDsEx_12+21h; "p2pcertificateshelper.cpp"
0x18004fcc8  mov     [rsp+120h+var_F8], rax
0x18004fccd  mov     dword ptr [rsp+120h+var_100], ecx
0x18004fcd1  mov     ebx, 2
0x18004fcd6  mov     r9d, ebx
0x18004fcd9  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004fce0  xor     edx, edx
0x18004fce2  mov     ecx, ebx
0x18004fce4  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004fce9  mov     r15, rdi
0x18004fcec  mov     ebx, r13d
0x18004fcef  jmp     loc_18004FE6A
0x18004fcf4  mov     rax, [rsi]
0x18004fcf7  mov     rcx, rsi
0x18004fcfa  mov     rax, [rax+30h]
0x18004fcfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fd03  mov     [rsp+120h+var_B8], r15
0x18004fd08  mov     [rsp+120h+var_C0], r13d
0x18004fd0d  mov     [rsp+120h+var_C8], r13
0x18004fd12  mov     [rsp+120h+var_D0], r13
0x18004fd17  mov     [rsp+120h+var_D8], r13
0x18004fd1c  mov     rcx, [rbp+57h+var_A0]
0x18004fd20  mov     [rsp+120h+var_E0], rcx
0x18004fd25  mov     [rsp+120h+var_E8], r13
0x18004fd2a  mov     [rsp+120h+var_F0], r13
0x18004fd2f  mov     [rsp+120h+var_F8], r13
0x18004fd34  mov     [rsp+120h+var_100], r13
0x18004fd39  mov     r9, rdi
0x18004fd3c  mov     r8d, r14d
0x18004fd3f  mov     rdx, [rbp+57h+arg_18]
0x18004fd43  mov     ebx, 2
0x18004fd48  mov     ecx, ebx
0x18004fd4a  mov     rax, [rax+30h]
0x18004fd4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fd53  mov     ecx, eax
0x18004fd55  mov     [rbp+57h+arg_0], eax
0x18004fd58  test    eax, eax
0x18004fd5a  jns     short loc_18004FDA4
0x18004fd5c  lea     rax, base
0x18004fd63  mov     [rsp+120h+var_E0], rax
0x18004fd68  lea     rax, aNtstatus; "NTSTATUS"
0x18004fd6f  mov     [rsp+120h+var_E8], rax
0x18004fd74  mov     dword ptr [rsp+120h+var_F0], 172h
0x18004fd7c  lea     rax, aOnecoreuapDsEx_12+21h; "p2pcertificateshelper.cpp"
0x18004fd83  mov     [rsp+120h+var_F8], rax
0x18004fd88  mov     dword ptr [rsp+120h+var_100], ecx
0x18004fd8c  mov     r9d, ebx
0x18004fd8f  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004fd96  xor     edx, edx
0x18004fd98  mov     ecx, ebx
0x18004fd9a  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004fd9f  jmp     loc_18004FE55
0x18004fda4  cmp     [r15], r13
0x18004fda7  jnz     loc_18004FE50
0x18004fdad  lea     rax, base
0x18004fdb4  mov     [rsp+120h+var_E0], rax
0x18004fdb9  lea     rax, aHresult; "HRESULT"
0x18004fdc0  mov     [rsp+120h+var_E8], rax
0x18004fdc5  mov     dword ptr [rsp+120h+var_F0], 177h
0x18004fdcd  lea     rax, aOnecoreuapDsEx_12+21h; "p2pcertificateshelper.cpp"
0x18004fdd4  mov     [rsp+120h+var_F8], rax
0x18004fdd9  mov     dword ptr [rsp+120h+var_100], 80048441h
0x18004fde1  mov     r9d, ebx
0x18004fde4  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004fdeb  xor     edx, edx
0x18004fded  mov     ecx, ebx
0x18004fdef  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004fdf4  mov     [rbp+57h+arg_0], 0C0048441h
0x18004fdfb  jmp     short loc_18004FE55
0x18004fdfd  mov     r14d, r13d
0x18004fe00  mov     ecx, 0C000000Dh
0x18004fe05  mov     [rbp+57h+arg_0], ecx
0x18004fe08  lea     rax, base
0x18004fe0f  mov     [rsp+120h+var_E0], rax
0x18004fe14  lea     rax, aNtstatus; "NTSTATUS"
0x18004fe1b  mov     [rsp+120h+var_E8], rax
0x18004fe20  mov     dword ptr [rsp+120h+var_F0], 138h
0x18004fe28  lea     rax, aOnecoreuapDsEx_12+21h; "p2pcertificateshelper.cpp"
0x18004fe2f  mov     [rsp+120h+var_F8], rax
0x18004fe34  mov     dword ptr [rsp+120h+var_100], ecx
0x18004fe38  mov     ebx, 2
0x18004fe3d  mov     r9d, ebx
0x18004fe40  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004fe47  xor     edx, edx
0x18004fe49  mov     ecx, ebx
0x18004fe4b  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004fe50  test    rsi, rsi
0x18004fe53  jz      short loc_18004FEB5
0x18004fe55  mov     r15, rdi
0x18004fe58  test    rdi, rdi
0x18004fe5b  jz      short loc_18004FE9D
0x18004fe5d  test    r12b, r12b
0x18004fe60  jz      short loc_18004FE8B
0x18004fe62  mov     ebx, r13d
0x18004fe65  test    r14d, r14d
0x18004fe68  jz      short loc_18004FE8B
0x18004fe6a  mov     eax, ebx
0x18004fe6c  mov     rdx, [r15+rax*8]
0x18004fe70  test    rdx, rdx
0x18004fe73  jz      short loc_18004FE84
0x18004fe75  mov     rax, [rsi]
0x18004fe78  mov     rcx, rsi
0x18004fe7b  mov     rax, [rax+10h]
0x18004fe7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe84  inc     ebx
0x18004fe86  cmp     ebx, r14d
0x18004fe89  jb      short loc_18004FE6A
0x18004fe8b  mov     rax, [rsi]
0x18004fe8e  mov     rdx, rdi
0x18004fe91  mov     rcx, rsi
0x18004fe94  mov     rax, [rax+10h]
0x18004fe98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe9d  mov     rdx, [rbp+57h+arg_18]
0x18004fea1  test    rdx, rdx
0x18004fea4  jz      short loc_18004FEB5
0x18004fea6  mov     rax, [rsi]
0x18004fea9  mov     rcx, rsi
0x18004feac  mov     rax, [rax+10h]
0x18004feb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004feb5  mov     ebx, [rbp+57h+arg_0]
0x18004feb8  lea     rcx, [rbp+57h+var_60]
0x18004febc  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18004fec1  nop
0x18004fec2  lea     rcx, [rbp+57h+var_90]
0x18004fec6  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x18004fecb  nop
0x18004fecc  mov     rcx, [rbp+57h+var_A0]
0x18004fed0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004fed4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004fed9  mov     eax, ebx
0x18004fedb  mov     rbx, [rsp+120h+arg_8]
0x18004fee3  add     rsp, 0F0h
0x18004feea  pop     r15
0x18004feec  pop     r14
0x18004feee  pop     r13
0x18004fef0  pop     r12
0x18004fef2  pop     rdi
0x18004fef3  pop     rsi
0x18004fef4  pop     rbp
0x18004fef5  retn
0x18004fef6  mov     ecx, 80004005h; int
0x18004fefb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
