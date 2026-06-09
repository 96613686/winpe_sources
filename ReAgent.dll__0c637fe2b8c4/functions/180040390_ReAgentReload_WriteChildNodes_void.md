# ReAgentReload::WriteChildNodes(void)

- ea: `0x180040390`
- end: `0x1800407a5`
- name: `?WriteChildNodes@ReAgentReload@@EEAAKXZ`
- size: `1045`
- prototype: `unsigned int __fastcall(ReAgentReload *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800059fc`
- `0x180016164`
- `0x180016a50`
- `0x180040390`
- `0x18005f010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180040788`
- `ntdll!RtlNtStatusToDosError` at `0x180040788`

## string_xrefs

- `0x1800403ca`: `failed to begin open element`
- `0x1800404b1`: `failed to begin open element`
- `0x18004058d`: `failed to begin open element`
- `0x180040481`: `failed to end open element`
- `0x18004055d`: `failed to end open element`
- `0x180040639`: `failed to end open element`
- `0x18004075f`: `base\diagnosis\srt\reagent2\reagent\parserex.cpp`
- `0x18004076b`: `ReAgentReload::WriteChildNodes %s (0x%x) in file %S line %d`
- `0x180040410`: `failed to write state attribute`
- `0x1800404f3`: `failed to write state attribute`
- `0x1800405cf`: `failed to write state attribute`
- `0x180040455`: `failed to write status attribute`
- `0x180040531`: `failed to write status attribute`
- `0x18004060d`: `failed to write status attribute`
- `0x180040680`: `failed to write single node status`
- `0x1800406c4`: `failed to write single node sqm machine guid`
- `0x180040708`: `failed to write single node sqm user guid`
- `0x180040753`: `failed to write single node sqm optin`

## pseudocode

```c
__int64 __fastcall ReAgentReload::WriteChildNodes(ReAgentReload *this)
{
  NTSTATUS v2; // ebx
  const struct _LUTF8_STRING *v3; // r8
  const wchar_t *v4; // r10
  int v5; // eax
  const struct _LUTF8_STRING *v6; // r8
  const struct _LUTF8_STRING *v7; // r8
  const struct _LUTF8_STRING *v8; // r8
  const struct _LUTF8_STRING *v9; // r8
  const struct _LUTF8_STRING *v10; // r8
  const struct _LUTF8_STRING *v11; // r9
  const struct _LUTF8_STRING *v12; // r9
  const struct _LUTF8_STRING *v13; // r9
  const struct _LUTF8_STRING *v14; // r9
  unsigned int v15; // esi
  struct _GUID *v17; // [rsp+28h] [rbp-18h]
  unsigned __int64 v18; // [rsp+60h] [rbp+20h] BYREF

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *))(**((_QWORD **)this + 5) + 40LL))(
         *((_QWORD *)this + 5),
         0,
         &ReAgentXMLParser::Utf8ScheduledOperation);
  if ( v2 < 0 )
  {
    v4 = L"failed to begin open element";
    v5 = 224;
LABEL_33:
    LODWORD(v17) = v5;
    UnattendLogW(
      2,
      L"ReAgentReload::WriteChildNodes %s (0x%x) in file %S line %d",
      v4,
      (unsigned int)v2,
      "base\\diagnosis\\srt\\reagent2\\reagent\\parserex.cpp",
      v17);
    return RtlNtStatusToDosError(v2);
  }
  v18 = *(int *)(*((_QWORD *)this + 8) + 5612LL);
  v2 = ReAgentXMLParser::WriteAttribute(
         this,
         (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StateAttrTag,
         v3,
         0,
         0,
         &v18);
  if ( v2 < 0 )
  {
    v4 = L"failed to write state attribute";
    v5 = 226;
    goto LABEL_33;
  }
  v18 = *(unsigned int *)(*((_QWORD *)this + 10) + 32LL);
  v2 = ReAgentXMLParser::WriteAttribute(
         this,
         (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StatusAttrTag,
         v6,
         0,
         0,
         &v18);
  if ( v2 < 0 )
  {
    v4 = L"failed to write status attribute";
    v5 = 228;
    goto LABEL_33;
  }
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 48LL))(*((_QWORD *)this + 5), 1);
  if ( v2 < 0 )
  {
    v4 = L"failed to end open element";
    v5 = 229;
    goto LABEL_33;
  }
  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *))(**((_QWORD **)this + 5) + 40LL))(
         *((_QWORD *)this + 5),
         0,
         &ReAgentReload::UtfBackupLaunchTag);
  if ( v2 < 0 )
  {
    v4 = L"failed to begin open element";
    v5 = 232;
    goto LABEL_33;
  }
  v18 = *(unsigned int *)(*((_QWORD *)this + 10) + 12LL);
  v2 = ReAgentXMLParser::WriteAttribute(
         this,
         (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StateAttrTag,
         v7,
         0,
         0,
         &v18);
  if ( v2 < 0 )
  {
    v4 = L"failed to write state attribute";
    v5 = 234;
    goto LABEL_33;
  }
  v18 = *(unsigned int *)(*((_QWORD *)this + 10) + 16LL);
  v2 = ReAgentXMLParser::WriteAttribute(
         this,
         (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StatusAttrTag,
         v8,
         0,
         0,
         &v18);
  if ( v2 < 0 )
  {
    v4 = L"failed to write status attribute";
    v5 = 236;
    goto LABEL_33;
  }
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 48LL))(*((_QWORD *)this + 5), 1);
  if ( v2 < 0 )
  {
    v4 = L"failed to end open element";
    v5 = 237;
    goto LABEL_33;
  }
  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *))(**((_QWORD **)this + 5) + 40LL))(
         *((_QWORD *)this + 5),
         0,
         &ReAgentReload::UtfBackupCompleteTag);
  if ( v2 < 0 )
  {
    v4 = L"failed to begin open element";
    v5 = 240;
    goto LABEL_33;
  }
  v18 = *(unsigned int *)(*((_QWORD *)this + 10) + 20LL);
  v2 = ReAgentXMLParser::WriteAttribute(
         this,
         (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StateAttrTag,
         v9,
         0,
         0,
         &v18);
  if ( v2 < 0 )
  {
    v4 = L"failed to write state attribute";
    v5 = 242;
    goto LABEL_33;
  }
  v18 = *(unsigned int *)(*((_QWORD *)this + 10) + 24LL);
  v2 = ReAgentXMLParser::WriteAttribute(
         this,
         (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StatusAttrTag,
         v10,
         0,
         0,
         &v18);
  if ( v2 < 0 )
  {
    v4 = L"failed to write status attribute";
    v5 = 244;
    goto LABEL_33;
  }
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 48LL))(*((_QWORD *)this + 5), 1);
  if ( v2 < 0 )
  {
    v4 = L"failed to end open element";
    v5 = 245;
    goto LABEL_33;
  }
  v18 = *(unsigned int *)(*((_QWORD *)this + 10) + 24LL);
  v2 = ReAgentXMLParser::WriteSingleNode(
         this,
         (const struct _LUTF8_STRING *)&ReAgentReload::UtfBackupResultTag,
         (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StatusAttrTag,
         v11,
         0,
         0,
         &v18);
  if ( v2 < 0 )
  {
    v4 = L"failed to write single node status";
    v5 = 250;
    goto LABEL_33;
  }
  v2 = ReAgentXMLParser::WriteSingleNode(
         this,
         (const struct _LUTF8_STRING *)&ReAgentReload::Utf8SqmMachineGuid,
         (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8IdAttrTag,
         v12,
         0,
         (struct _GUID *)(*((_QWORD *)this + 10) + 36LL),
         0);
  if ( v2 < 0 )
  {
    v4 = L"failed to write single node sqm machine guid";
    v5 = 254;
    goto LABEL_33;
  }
  v2 = ReAgentXMLParser::WriteSingleNode(
         this,
         (const struct _LUTF8_STRING *)&ReAgentReload::Utf8SqmUserGuid,
         (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8IdAttrTag,
         v13,
         0,
         (struct _GUID *)(*((_QWORD *)this + 10) + 52LL),
         0);
  if ( v2 < 0 )
  {
    v4 = L"failed to write single node sqm user guid";
    v5 = 258;
    goto LABEL_33;
  }
  v15 = 0;
  v18 = *(unsigned int *)(*((_QWORD *)this + 10) + 68LL);
  v2 = ReAgentXMLParser::WriteSingleNode(
         this,
         (const struct _LUTF8_STRING *)&ReAgentReload::Utf8SqmOptIn,
         (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StateAttrTag,
         v14,
         0,
         0,
         &v18);
  if ( v2 < 0 )
  {
    v4 = L"failed to write single node sqm optin";
    v5 = 263;
    goto LABEL_33;
  }
  return v15;
}

```

## disassembly

```asm
0x180040390  mov     [rsp-18h+arg_8], rbx
0x180040395  mov     [rsp-18h+arg_10], rsi
0x18004039a  push    rbp
0x18004039b  push    rdi
0x18004039c  push    r14
0x18004039e  mov     rbp, rsp
0x1800403a1  sub     rsp, 40h
0x1800403a5  mov     rdi, rcx
0x1800403a8  lea     r8, ?Utf8ScheduledOperation@ReAgentXMLParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const ReAgentXMLParser::Utf8ScheduledOperation
0x1800403af  mov     rcx, [rcx+28h]
0x1800403b3  xor     edx, edx
0x1800403b5  mov     rax, [rcx]
0x1800403b8  mov     rax, [rax+28h]
0x1800403bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403c1  xor     r14d, r14d
0x1800403c4  mov     ebx, eax
0x1800403c6  test    eax, eax
0x1800403c8  jns     short loc_1800403DB
0x1800403ca  lea     r10, aFailedToBeginO_1; "failed to begin open element"
0x1800403d1  mov     eax, 0E0h
0x1800403d6  jmp     loc_18004075F
0x1800403db  mov     rax, [rdi+40h]
0x1800403df  lea     rdx, ?Utf8StateAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x1800403e6  xor     r9d, r9d; unsigned __int16 *
0x1800403e9  movsxd  rcx, dword ptr [rax+15ECh]
0x1800403f0  lea     rax, [rbp+arg_0]
0x1800403f4  mov     [rbp+arg_0], rcx
0x1800403f8  mov     rcx, rdi; this
0x1800403fb  mov     [rsp+40h+var_18], rax; unsigned __int64 *
0x180040400  mov     [rsp+40h+var_20], r14; struct _GUID *
0x180040405  call    ?WriteAttribute@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x18004040a  mov     ebx, eax
0x18004040c  test    eax, eax
0x18004040e  jns     short loc_180040421
0x180040410  lea     r10, aFailedToWriteS_0; "failed to write state attribute"
0x180040417  mov     eax, 0E2h
0x18004041c  jmp     loc_18004075F
0x180040421  mov     rax, [rdi+50h]
0x180040425  lea     rsi, ?Utf8StatusAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const ReAgentXMLParser::Utf8StatusAttrTag
0x18004042c  xor     r9d, r9d; unsigned __int16 *
0x18004042f  mov     rdx, rsi; struct _LUTF8_STRING *
0x180040432  mov     ecx, [rax+20h]
0x180040435  lea     rax, [rbp+arg_0]
0x180040439  mov     [rbp+arg_0], rcx
0x18004043d  mov     rcx, rdi; this
0x180040440  mov     [rsp+40h+var_18], rax; unsigned __int64 *
0x180040445  mov     [rsp+40h+var_20], r14; struct _GUID *
0x18004044a  call    ?WriteAttribute@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x18004044f  mov     ebx, eax
0x180040451  test    eax, eax
0x180040453  jns     short loc_180040466
0x180040455  lea     r10, aFailedToWriteS; "failed to write status attribute"
0x18004045c  mov     eax, 0E4h
0x180040461  jmp     loc_18004075F
0x180040466  mov     rcx, [rdi+28h]
0x18004046a  mov     edx, 1
0x18004046f  mov     rax, [rcx]
0x180040472  mov     rax, [rax+30h]
0x180040476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004047b  mov     ebx, eax
0x18004047d  test    eax, eax
0x18004047f  jns     short loc_180040492
0x180040481  lea     r10, aFailedToEndOpe; "failed to end open element"
0x180040488  mov     eax, 0E5h
0x18004048d  jmp     loc_18004075F
0x180040492  mov     rcx, [rdi+28h]
0x180040496  lea     r8, ?UtfBackupLaunchTag@ReAgentReload@@0U_LUTF8_STRING@@B; _LUTF8_STRING const ReAgentReload::UtfBackupLaunchTag
0x18004049d  xor     edx, edx
0x18004049f  mov     rax, [rcx]
0x1800404a2  mov     rax, [rax+28h]
0x1800404a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800404ab  mov     ebx, eax
0x1800404ad  test    eax, eax
0x1800404af  jns     short loc_1800404C2
0x1800404b1  lea     r10, aFailedToBeginO_1; "failed to begin open element"
0x1800404b8  mov     eax, 0E8h
0x1800404bd  jmp     loc_18004075F
0x1800404c2  mov     rax, [rdi+50h]
0x1800404c6  lea     rdx, ?Utf8StateAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x1800404cd  xor     r9d, r9d; unsigned __int16 *
0x1800404d0  mov     ecx, [rax+0Ch]
0x1800404d3  lea     rax, [rbp+arg_0]
0x1800404d7  mov     [rbp+arg_0], rcx
0x1800404db  mov     rcx, rdi; this
0x1800404de  mov     [rsp+40h+var_18], rax; unsigned __int64 *
0x1800404e3  mov     [rsp+40h+var_20], r14; struct _GUID *
0x1800404e8  call    ?WriteAttribute@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x1800404ed  mov     ebx, eax
0x1800404ef  test    eax, eax
0x1800404f1  jns     short loc_180040504
0x1800404f3  lea     r10, aFailedToWriteS_0; "failed to write state attribute"
0x1800404fa  mov     eax, 0EAh
0x1800404ff  jmp     loc_18004075F
0x180040504  mov     rax, [rdi+50h]
0x180040508  xor     r9d, r9d; unsigned __int16 *
0x18004050b  mov     rdx, rsi; struct _LUTF8_STRING *
0x18004050e  mov     ecx, [rax+10h]
0x180040511  lea     rax, [rbp+arg_0]
0x180040515  mov     [rbp+arg_0], rcx
0x180040519  mov     rcx, rdi; this
0x18004051c  mov     [rsp+40h+var_18], rax; unsigned __int64 *
0x180040521  mov     [rsp+40h+var_20], r14; struct _GUID *
0x180040526  call    ?WriteAttribute@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x18004052b  mov     ebx, eax
0x18004052d  test    eax, eax
0x18004052f  jns     short loc_180040542
0x180040531  lea     r10, aFailedToWriteS; "failed to write status attribute"
0x180040538  mov     eax, 0ECh
0x18004053d  jmp     loc_18004075F
0x180040542  mov     rcx, [rdi+28h]
0x180040546  mov     edx, 1
0x18004054b  mov     rax, [rcx]
0x18004054e  mov     rax, [rax+30h]
0x180040552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040557  mov     ebx, eax
0x180040559  test    eax, eax
0x18004055b  jns     short loc_18004056E
0x18004055d  lea     r10, aFailedToEndOpe; "failed to end open element"
0x180040564  mov     eax, 0EDh
0x180040569  jmp     loc_18004075F
0x18004056e  mov     rcx, [rdi+28h]
0x180040572  lea     r8, ?UtfBackupCompleteTag@ReAgentReload@@0U_LUTF8_STRING@@B; _LUTF8_STRING const ReAgentReload::UtfBackupCompleteTag
0x180040579  xor     edx, edx
0x18004057b  mov     rax, [rcx]
0x18004057e  mov     rax, [rax+28h]
0x180040582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040587  mov     ebx, eax
0x180040589  test    eax, eax
0x18004058b  jns     short loc_18004059E
0x18004058d  lea     r10, aFailedToBeginO_1; "failed to begin open element"
0x180040594  mov     eax, 0F0h
0x180040599  jmp     loc_18004075F
0x18004059e  mov     rax, [rdi+50h]
0x1800405a2  lea     rdx, ?Utf8StateAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x1800405a9  xor     r9d, r9d; unsigned __int16 *
0x1800405ac  mov     ecx, [rax+14h]
0x1800405af  lea     rax, [rbp+arg_0]
0x1800405b3  mov     [rbp+arg_0], rcx
0x1800405b7  mov     rcx, rdi; this
0x1800405ba  mov     [rsp+40h+var_18], rax; unsigned __int64 *
0x1800405bf  mov     [rsp+40h+var_20], r14; struct _GUID *
0x1800405c4  call    ?WriteAttribute@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x1800405c9  mov     ebx, eax
0x1800405cb  test    eax, eax
0x1800405cd  jns     short loc_1800405E0
0x1800405cf  lea     r10, aFailedToWriteS_0; "failed to write state attribute"
0x1800405d6  mov     eax, 0F2h
0x1800405db  jmp     loc_18004075F
0x1800405e0  mov     rax, [rdi+50h]
0x1800405e4  xor     r9d, r9d; unsigned __int16 *
0x1800405e7  mov     rdx, rsi; struct _LUTF8_STRING *
0x1800405ea  mov     ecx, [rax+18h]
0x1800405ed  lea     rax, [rbp+arg_0]
0x1800405f1  mov     [rbp+arg_0], rcx
0x1800405f5  mov     rcx, rdi; this
0x1800405f8  mov     [rsp+40h+var_18], rax; unsigned __int64 *
0x1800405fd  mov     [rsp+40h+var_20], r14; struct _GUID *
0x180040602  call    ?WriteAttribute@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180040607  mov     ebx, eax
0x180040609  test    eax, eax
0x18004060b  jns     short loc_18004061E
0x18004060d  lea     r10, aFailedToWriteS; "failed to write status attribute"
0x180040614  mov     eax, 0F4h
0x180040619  jmp     loc_18004075F
0x18004061e  mov     rcx, [rdi+28h]
0x180040622  mov     edx, 1
0x180040627  mov     rax, [rcx]
0x18004062a  mov     rax, [rax+30h]
0x18004062e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040633  mov     ebx, eax
0x180040635  test    eax, eax
0x180040637  jns     short loc_18004064A
0x180040639  lea     r10, aFailedToEndOpe; "failed to end open element"
0x180040640  mov     eax, 0F5h
0x180040645  jmp     loc_18004075F
0x18004064a  mov     rax, [rdi+50h]
0x18004064e  lea     rdx, ?UtfBackupResultTag@ReAgentReload@@0U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180040655  mov     r8, rsi; struct _LUTF8_STRING *
0x180040658  mov     ecx, [rax+18h]
0x18004065b  lea     rax, [rbp+arg_0]
0x18004065f  mov     [rsp+40h+var_10], rax; unsigned __int64 *
0x180040664  mov     [rbp+arg_0], rcx
0x180040668  mov     rcx, rdi; this
0x18004066b  mov     [rsp+40h+var_18], r14; struct _GUID *
0x180040670  mov     [rsp+40h+var_20], r14; unsigned __int16 *
0x180040675  call    ?WriteSingleNode@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@00PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteSingleNode(_LUTF8_STRING const *,_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x18004067a  mov     ebx, eax
0x18004067c  test    eax, eax
0x18004067e  jns     short loc_180040691
0x180040680  lea     r10, aFailedToWriteS_2; "failed to write single node status"
0x180040687  mov     eax, 0FAh
0x18004068c  jmp     loc_18004075F
0x180040691  mov     rax, [rdi+50h]
0x180040695  lea     r8, ?Utf8IdAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x18004069c  add     rax, 24h ; '$'
0x1800406a0  mov     [rsp+40h+var_10], r14; unsigned __int64 *
0x1800406a5  mov     [rsp+40h+var_18], rax; struct _GUID *
0x1800406aa  lea     rdx, ?Utf8SqmMachineGuid@ReAgentReload@@0U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x1800406b1  mov     rcx, rdi; this
0x1800406b4  mov     [rsp+40h+var_20], r14; unsigned __int16 *
0x1800406b9  call    ?WriteSingleNode@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@00PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteSingleNode(_LUTF8_STRING const *,_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x1800406be  mov     ebx, eax
0x1800406c0  test    eax, eax
0x1800406c2  jns     short loc_1800406D5
0x1800406c4  lea     r10, aFailedToWriteS_1; "failed to write single node sqm machine"...
0x1800406cb  mov     eax, 0FEh
0x1800406d0  jmp     loc_18004075F
0x1800406d5  mov     rax, [rdi+50h]
0x1800406d9  lea     r8, ?Utf8IdAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x1800406e0  add     rax, 34h ; '4'
0x1800406e4  mov     [rsp+40h+var_10], r14; unsigned __int64 *
0x1800406e9  mov     [rsp+40h+var_18], rax; struct _GUID *
0x1800406ee  lea     rdx, ?Utf8SqmUserGuid@ReAgentReload@@0U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x1800406f5  mov     rcx, rdi; this
0x1800406f8  mov     [rsp+40h+var_20], r14; unsigned __int16 *
0x1800406fd  call    ?WriteSingleNode@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@00PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteSingleNode(_LUTF8_STRING const *,_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180040702  mov     ebx, eax
0x180040704  test    eax, eax
0x180040706  jns     short loc_180040716
0x180040708  lea     r10, aFailedToWriteS_3; "failed to write single node sqm user gu"...
0x18004070f  mov     eax, 102h
0x180040714  jmp     short loc_18004075F
0x180040716  mov     rax, [rdi+50h]
0x18004071a  lea     r8, ?Utf8StateAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180040721  lea     rdx, ?Utf8SqmOptIn@ReAgentReload@@0U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180040728  mov     esi, r14d
0x18004072b  mov     ecx, [rax+44h]
0x18004072e  lea     rax, [rbp+arg_0]
0x180040732  mov     [rsp+40h+var_10], rax; unsigned __int64 *
0x180040737  mov     [rbp+arg_0], rcx
0x18004073b  mov     rcx, rdi; this
0x18004073e  mov     [rsp+40h+var_18], r14; struct _GUID *
0x180040743  mov     [rsp+40h+var_20], r14; unsigned __int16 *
0x180040748  call    ?WriteSingleNode@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@00PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteSingleNode(_LUTF8_STRING const *,_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x18004074d  mov     ebx, eax
0x18004074f  test    eax, eax
0x180040751  jns     short loc_180040790
0x180040753  lea     r10, aFailedToWriteS_4; "failed to write single node sqm optin"
0x18004075a  mov     eax, 107h
0x18004075f  lea     r8, aBaseDiagnosisS; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180040766  mov     ecx, 2
0x18004076b  lea     rdx, aReagentreloadW; "ReAgentReload::WriteChildNodes %s (0x%x"...
0x180040772  mov     dword ptr [rsp+40h+var_18], eax
0x180040776  mov     r9d, ebx
0x180040779  mov     [rsp+40h+var_20], r8
0x18004077e  mov     r8, r10
0x180040781  call    UnattendLogW
0x180040786  mov     ecx, ebx; Status
0x180040788  call    cs:__imp_RtlNtStatusToDosError
0x18004078e  mov     esi, eax
0x180040790  mov     rbx, [rsp+40h+arg_8]
0x180040795  mov     eax, esi
0x180040797  mov     rsi, [rsp+40h+arg_10]
0x18004079c  add     rsp, 40h
0x1800407a0  pop     r14
0x1800407a2  pop     rdi
0x1800407a3  pop     rbp
0x1800407a4  retn
```
