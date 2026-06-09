# sih::CSls::GetSlsData(CCallerIdentity const *,_GUID)

- ea: `0x140024f14`
- end: `0x140025402`
- name: `?GetSlsData@CSls@sih@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBVCCallerIdentity@@U_GUID@@@Z`
- size: `1262`
- prototype: `_OWORD *__fastcall(sih::CSls *this, _OWORD *, __int64, const struct _GUID *)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14001a10c`
- `0x14001fb74`

## callees

- `0x140006408`
- `0x14000ce30`
- `0x14000ce9c`
- `0x1400116a4`
- `0x140011958`
- `0x1400154b4`
- `0x14001ed4c`
- `0x140024f14`
- `0x1400254e8`
- `0x140025aa0`
- `0x140025dfc`
- `0x140027e28`
- `0x140032b84`
- `0x1400333b4`
- `0x140033e34`
- `0x14003be88`
- `0x140045dc0`
- `0x1400481f8`
- `0x14004cd80`
- `0x14004d140`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025344`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025344`
- `OLEAUT32!__imp_SysFreeString` at `0x140025373`
- `OLEAUT32!__imp_SysFreeString` at `0x140025373`

## pseudocode

```c
_OWORD *__fastcall sih::CSls::GetSlsData(sih::CSls *this, _OWORD *a2, __int64 a3, const struct _GUID *a4)
{
  wchar_t *v8; // rbx
  int Response; // esi
  sih::CSls *v10; // rcx
  CHAR *v11; // rdi
  void *v12; // rax
  wchar_t *v13; // rcx
  sih::SlsCache *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rdx
  char *v17; // r15
  __int64 v18; // rsi
  char *v20; // [rsp+20h] [rbp-E0h]
  char *v21; // [rsp+20h] [rbp-E0h]
  bool v22; // [rsp+30h] [rbp-D0h] BYREF
  bool v23; // [rsp+31h] [rbp-CFh] BYREF
  unsigned int v24[3]; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t *v25; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv[11]; // [rsp+48h] [rbp-B8h] BYREF
  GUID pExceptionObject; // [rsp+A0h] [rbp-60h] BYREF
  void *v28[2]; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v29; // [rsp+C0h] [rbp-40h]
  bool v30; // [rsp+C8h] [rbp-38h]
  int v31; // [rsp+C9h] [rbp-37h]
  __int16 v32; // [rsp+CDh] [rbp-33h]
  char v33; // [rsp+CFh] [rbp-31h]
  wchar_t *v34[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v35[8]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v36[2]; // [rsp+120h] [rbp+20h] BYREF
  void *v37[2]; // [rsp+140h] [rbp+40h]
  __int64 v38; // [rsp+150h] [rbp+50h] BYREF

  pv[9] = a2;
  memset(v36, 0, sizeof(v36));
  v37[0] = 0;
  v37[1] = 0;
  v38 = 0;
  memset(v35, 0, sizeof(v35));
  memset(&v35[5], 0, 20);
  memset(&v35[1], 0, 28);
  v22 = 0;
  v23 = 0;
  v24[0] = 0;
  pv[0] = 0;
  v8 = 0;
  v25 = 0;
  *a2 = 0;
  *((_QWORD *)a2 + 2) = 0;
  *((_QWORD *)a2 + 3) = 7;
  *(_WORD *)a2 = 0;
  v24[1] = 1;
  if ( !a3 )
  {
    Response = -2147024809;
    goto LABEL_57;
  }
  v36[0] = *a4;
  Response = CSLSRequest::BuildRequest((CSLSRequest *)v36);
  if ( Response < 0 )
    goto LABEL_57;
  WUTrace(0, 0, 0x400000, 5, 0, L"Getting sls response ...");
  Response = sih::CSls::GetResponse(this, (const struct CSLSRequest *)v36, (struct CSLSResponse *)v35, &v23);
  if ( Response < 0 )
    goto LABEL_57;
  WUTrace(0, 0, 0x400000, 5, 0, L"Validating sls response ...");
  pExceptionObject = 0;
  v28[0] = 0;
  Response = CSLSResponse::Validate(
               (CSLSResponse *)v35,
               a4,
               (const struct CSLSClient::RevisionCheck *)&pExceptionObject,
               &v22,
               v21);
  if ( Response < 0 )
    goto LABEL_57;
  if ( !v22 )
  {
    Response = -2145103866;
    goto LABEL_57;
  }
  Response = CSLSResponse::GetData((CSLSResponse *)v35, (char **)pv, v24);
  if ( Response < 0 )
  {
LABEL_57:
    LODWORD(v20) = Response;
    WUTrace(0, 0, 0x400000, 1, v20, L"GetSlsData");
    sih::hr_exception::hr_exception((sih::hr_exception *)&pExceptionObject, Response);
    throw (sih::hr_exception *)&pExceptionObject;
  }
  v11 = (CHAR *)pv[0];
  if ( LODWORD(v35[4]) != 1 )
  {
    if ( !v23 )
    {
      pExceptionObject = GUID_NULL;
      *(_OWORD *)v28 = 0;
      v29 = 0;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      *(_OWORD *)v34 = 0;
      memset(&pv[1], 0, 0x40u);
      *(struct _GUID *)&pv[1] = *a4;
      pv[4] = (LPVOID)v35[0];
      pv[5] = (LPVOID)v35[1];
      LODWORD(pv[6]) = HIBYTE(v35[3]) != 0;
      v12 = SafeSusAllocArray(LODWORD(v35[7]), 1u);
      pv[7] = v12;
      if ( !v12 )
      {
        Response = -2147024882;
LABEL_16:
        SusFree(v12);
        SusFree(pv[8]);
LABEL_17:
        v13 = v34[1];
LABEL_18:
        if ( v13 )
        {
          SusFree(v13);
          v34[1] = 0;
        }
        if ( v34[0] )
        {
          SusFree(v34[0]);
          v34[0] = 0;
        }
        if ( v28[0] )
          SusFree(v28[0]);
        goto LABEL_57;
      }
      memmove(v12, (const void *)v35[6], LODWORD(v35[7]));
      HIDWORD(pv[6]) = v35[7];
      Response = DuplicateOptionalString<wchar_t *,wchar_t *>(v35[5], &pv[8]);
      if ( Response < 0 )
      {
        v12 = pv[7];
        goto LABEL_16;
      }
      if ( v28[0] )
      {
        SusFree(v28[0]);
        v28[0] = 0;
      }
      Response = DuplicateString<wchar_t *,wchar_t *>(v37[0], v28);
      if ( Response < 0 )
        goto LABEL_17;
      pExceptionObject = *(GUID *)&pv[1];
      v28[1] = pv[4];
      v29 = pv[5];
      v30 = LODWORD(pv[6]) != 0;
      if ( v34[1] )
        SusFree(v34[1]);
      v34[1] = (wchar_t *)pv[8];
      if ( v34[0] )
      {
        SusFree(v34[0]);
        v34[0] = 0;
      }
      Response = ConvertAnsiToWide_Alloc((LPCCH)pv[7], v34);
      SusFree(pv[7]);
      if ( Response < 0 )
        goto LABEL_17;
      Response = sih::SlsCache::UpdateEntry(v14, (const struct sih::SlsCacheEntry *)&pExceptionObject);
      v13 = v34[1];
      if ( Response < 0 )
        goto LABEL_18;
      if ( v34[1] )
      {
        SusFree(v34[1]);
        v34[1] = 0;
      }
      if ( v34[0] )
      {
        SusFree(v34[0]);
        v34[0] = 0;
      }
      if ( v28[0] )
        SusFree(v28[0]);
    }
    Response = ConvertAnsiToWide_Alloc(v11, &v25);
    if ( Response < 0 )
      goto LABEL_57;
    v16 = v24[0];
    if ( (unsigned __int64)v24[0] > *((_QWORD *)a2 + 3) )
    {
      v8 = v25;
      std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(a2, v24[0], v15, v25);
    }
    else
    {
      v17 = (char *)a2;
      if ( *((_QWORD *)a2 + 3) > 7u )
        v17 = *(char **)a2;
      *((_QWORD *)a2 + 2) = v24[0];
      v18 = 2 * v16;
      v8 = v25;
      memmove(v17, v25, 2 * v16);
      *(_WORD *)&v17[v18] = 0;
    }
    goto LABEL_45;
  }
  Response = sih::CSls::HandleSlsErrorResponse(v10, (const struct CSLSResponse *)v35);
  if ( Response < 0 )
    goto LABEL_57;
LABEL_45:
  if ( v8 )
    SusFree(v8);
  if ( v11 )
    CoTaskMemFree(v11);
  if ( v35[6] )
  {
    SusFree((void *)v35[6]);
    v35[6] = 0;
  }
  if ( v35[5] )
  {
    SusFree((void *)v35[5]);
    v35[5] = 0;
  }
  SysFreeString((BSTR)v35[2]);
  v35[2] = 0;
  WuSmartPtr::XPtrBase<AADDeviceDataBoundaryInfo,WuSmartPtr::Policies::FreeMethodPolicy<AADDeviceDataBoundaryInfo,&void FreeAADDeviceDataBoundaryInfo(void *)>>::~XPtrBase<AADDeviceDataBoundaryInfo,WuSmartPtr::Policies::FreeMethodPolicy<AADDeviceDataBoundaryInfo,&void FreeAADDeviceDataBoundaryInfo(void *)>>(&v38);
  if ( v37[0] )
    SusFree(v37[0]);
  return a2;
}

```

## disassembly

```asm
0x140024f14  mov     [rsp-8+arg_10], rbx
0x140024f19  push    rbp
0x140024f1a  push    rsi
0x140024f1b  push    rdi
0x140024f1c  push    r12
0x140024f1e  push    r13
0x140024f20  push    r14
0x140024f22  push    r15
0x140024f24  lea     rbp, [rsp-60h]
0x140024f29  sub     rsp, 160h
0x140024f30  mov     rax, cs:__security_cookie
0x140024f37  xor     rax, rsp
0x140024f3a  mov     [rbp+90h+var_38], rax
0x140024f3e  mov     r15, r9
0x140024f41  mov     rdi, r8
0x140024f44  mov     r14, rdx
0x140024f47  mov     r12, rcx
0x140024f4a  mov     [rbp+90h+var_100], rdx
0x140024f4e  xor     r13d, r13d
0x140024f51  mov     [rsp+190h+var_158], r13d
0x140024f56  xorps   xmm0, xmm0
0x140024f59  movups  [rbp+90h+var_60], xmm0
0x140024f5d  movups  xmmword ptr [rbp+90h+var_50], xmm0
0x140024f61  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140024f68  movdqu  [rbp+90h+var_70], xmm0
0x140024f6d  mov     [rbp+90h+var_50], r13
0x140024f71  mov     byte ptr [rbp+90h+var_50+8], r13b
0x140024f75  mov     [rbp+90h+var_40], r13
0x140024f79  xor     edx, edx; Val
0x140024f7b  lea     r8d, [r13+40h]; Size
0x140024f7f  lea     rcx, [rbp+90h+var_B0]; void *
0x140024f83  call    memset
0x140024f88  mov     [rbp+90h+bstrString], r13
0x140024f8c  mov     [rbp+90h+var_98], r13d
0x140024f90  mov     [rbp+90h+var_94], r13
0x140024f94  mov     [rbp+90h+var_88], r13
0x140024f98  mov     [rbp+90h+Src], r13
0x140024f9c  mov     dword ptr [rbp+90h+Size], r13d
0x140024fa0  xor     eax, eax
0x140024fa2  mov     [rbp+90h+var_A8], rax
0x140024fa6  mov     [rsp+190h+var_160], r13b
0x140024fab  mov     [rsp+190h+var_15F], r13b
0x140024fb0  mov     [rsp+190h+var_15C], r13d
0x140024fb5  mov     [rsp+190h+pv], r13
0x140024fba  mov     ebx, r13d
0x140024fbd  mov     [rsp+190h+var_150], rbx
0x140024fc2  xorps   xmm0, xmm0
0x140024fc5  movups  xmmword ptr [r14], xmm0
0x140024fc9  mov     [r14+10h], r13
0x140024fcd  mov     qword ptr [r14+18h], 7
0x140024fd5  mov     [r14], r13w
0x140024fd9  mov     [rsp+190h+var_158], 1
0x140024fe1  test    rdi, rdi
0x140024fe4  jz      loc_1400253BE
0x140024fea  movups  xmm0, xmmword ptr [r15]
0x140024fee  movdqu  [rbp+90h+var_70], xmm0
0x140024ff3  lea     rcx, [rbp+90h+var_70]; this
0x140024ff7  call    ?BuildRequest@CSLSRequest@@QEAAJXZ; CSLSRequest::BuildRequest(void)
0x140024ffc  mov     esi, eax
0x140024ffe  test    eax, eax
0x140025000  js      loc_1400253C3
0x140025006  lea     rax, aGettingSlsResp; "Getting sls response ..."
0x14002500d  mov     [rsp+190h+var_168], rax
0x140025012  mov     [rsp+190h+var_170], r13
0x140025017  lea     edi, [r13+5]
0x14002501b  mov     r9d, edi
0x14002501e  xor     edx, edx
0x140025020  xor     ecx, ecx
0x140025022  mov     r8d, 400000h
0x140025028  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002502d  lea     r9, [rsp+190h+var_15F]; bool *
0x140025032  lea     r8, [rbp+90h+var_B0]; struct CSLSResponse *
0x140025036  lea     rdx, [rbp+90h+var_70]; struct CSLSRequest *
0x14002503a  mov     rcx, r12; this
0x14002503d  call    ?GetResponse@CSls@sih@@AEAAJAEBVCSLSRequest@@AEAVCSLSResponse@@PEA_N@Z; sih::CSls::GetResponse(CSLSRequest const &,CSLSResponse &,bool *)
0x140025042  mov     esi, eax
0x140025044  test    eax, eax
0x140025046  js      loc_1400253C3
0x14002504c  lea     rax, aValidatingSlsR; "Validating sls response ..."
0x140025053  mov     [rsp+190h+var_168], rax
0x140025058  mov     [rsp+190h+var_170], r13; char *
0x14002505d  mov     r9d, edi
0x140025060  xor     edx, edx
0x140025062  xor     ecx, ecx
0x140025064  mov     r8d, 400000h
0x14002506a  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002506f  xorps   xmm0, xmm0
0x140025072  xor     eax, eax
0x140025074  movups  [rbp+90h+pExceptionObject], xmm0
0x140025078  mov     [rbp+90h+var_E0], rax
0x14002507c  lea     r9, [rsp+190h+var_160]; bool *
0x140025081  lea     r8, [rbp+90h+pExceptionObject]; struct CSLSClient::RevisionCheck *
0x140025085  mov     rdx, r15; struct _GUID *
0x140025088  lea     rcx, [rbp+90h+var_B0]; this
0x14002508c  call    ?Validate@CSLSResponse@@QEAAJAEBU_GUID@@AEBURevisionCheck@CSLSClient@@PEA_NPEBD@Z; CSLSResponse::Validate(_GUID const &,CSLSClient::RevisionCheck const &,bool *,char const *)
0x140025091  mov     esi, eax
0x140025093  test    eax, eax
0x140025095  js      loc_1400253C3
0x14002509b  cmp     [rsp+190h+var_160], r13b
0x1400250a0  jnz     short loc_1400250AC
0x1400250a2  mov     esi, 80245006h
0x1400250a7  jmp     loc_1400253C3
0x1400250ac  lea     r8, [rsp+190h+var_15C]; unsigned int *
0x1400250b1  lea     rdx, [rsp+190h+pv]; char **
0x1400250b6  lea     rcx, [rbp+90h+var_B0]; this
0x1400250ba  call    ?GetData@CSLSResponse@@QEAAJPEAPEADPEAK@Z; CSLSResponse::GetData(char * *,ulong *)
0x1400250bf  mov     esi, eax
0x1400250c1  test    eax, eax
0x1400250c3  js      loc_1400253C3
0x1400250c9  mov     rdi, [rsp+190h+pv]
0x1400250ce  cmp     dword ptr [rbp+90h+var_94+4], 1
0x1400250d2  jnz     short loc_1400250EC
0x1400250d4  lea     rdx, [rbp+90h+var_B0]; struct CSLSResponse *
0x1400250d8  call    ?HandleSlsErrorResponse@CSls@sih@@AEBAJAEBVCSLSResponse@@@Z; sih::CSls::HandleSlsErrorResponse(CSLSResponse const &)
0x1400250dd  mov     esi, eax
0x1400250df  test    eax, eax
0x1400250e1  jns     loc_14002532E
0x1400250e7  jmp     loc_1400253C3
0x1400250ec  cmp     [rsp+190h+var_15F], r13b
0x1400250f1  jnz     loc_1400252CD
0x1400250f7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400250fe  movdqu  [rbp+90h+pExceptionObject], xmm0
0x140025103  xorps   xmm0, xmm0
0x140025106  movdqa  xmmword ptr [rbp+90h+var_E0], xmm0
0x14002510b  xor     eax, eax
0x14002510d  mov     [rbp+90h+var_D0], rax
0x140025111  mov     [rbp+90h+var_C8], r13b
0x140025115  mov     [rbp+90h+var_C7], eax
0x140025118  mov     [rbp+90h+var_C3], ax
0x14002511c  mov     [rbp+90h+var_C1], al
0x14002511f  movdqa  xmmword ptr [rbp+90h+var_C0], xmm0
0x140025124  xor     edx, edx; Val
0x140025126  lea     r8d, [rax+40h]; Size
0x14002512a  lea     rcx, [rsp+190h+var_140]; void *
0x14002512f  call    memset
0x140025134  movups  xmm0, xmmword ptr [r15]
0x140025138  movdqu  [rsp+190h+var_140], xmm0
0x14002513e  mov     rax, [rbp+90h+var_B0]
0x140025142  mov     [rsp+190h+var_128], rax
0x140025147  mov     rax, [rbp+90h+var_A8]
0x14002514b  mov     [rsp+190h+var_120], rax
0x140025150  mov     eax, r13d
0x140025153  cmp     byte ptr [rbp+90h+var_94+3], r13b
0x140025157  setnz   al
0x14002515a  mov     [rsp+190h+var_118], eax
0x14002515e  mov     ecx, dword ptr [rbp+90h+Size]; unsigned __int64
0x140025161  mov     edx, 1; unsigned __int64
0x140025166  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x14002516b  mov     [rbp+90h+lpMultiByteStr], rax
0x14002516f  test    rax, rax
0x140025172  jnz     short loc_14002517B
0x140025174  mov     esi, 8007000Eh
0x140025179  jmp     short loc_1400251A9
0x14002517b  mov     r8d, dword ptr [rbp+90h+Size]; Size
0x14002517f  mov     rdx, [rbp+90h+Src]; Src
0x140025183  mov     rcx, rax; void *
0x140025186  call    memmove
0x14002518b  mov     eax, dword ptr [rbp+90h+Size]
0x14002518e  mov     [rsp+190h+var_114], eax
0x140025192  lea     rdx, [rbp+90h+lpMem]
0x140025196  mov     rcx, [rbp+90h+var_88]
0x14002519a  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x14002519f  mov     esi, eax
0x1400251a1  test    eax, eax
0x1400251a3  jns     short loc_1400251F6
0x1400251a5  mov     rax, [rbp+90h+lpMultiByteStr]
0x1400251a9  mov     rcx, rax; lpMem
0x1400251ac  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400251b1  mov     rcx, [rbp+90h+lpMem]; lpMem
0x1400251b5  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400251ba  nop
0x1400251bb  mov     rcx, [rbp+90h+var_C0+8]; lpMem
0x1400251bf  test    rcx, rcx
0x1400251c2  jz      short loc_1400251CD
0x1400251c4  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400251c9  mov     [rbp+90h+var_C0+8], r13
0x1400251cd  mov     rcx, [rbp+90h+var_C0]; lpMem
0x1400251d1  test    rcx, rcx
0x1400251d4  jz      short loc_1400251DF
0x1400251d6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400251db  mov     [rbp+90h+var_C0], r13
0x1400251df  mov     rcx, [rbp+90h+var_E0]; lpMem
0x1400251e3  test    rcx, rcx
0x1400251e6  jz      loc_1400253C3
0x1400251ec  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400251f1  jmp     loc_1400253C3
0x1400251f6  mov     rcx, [rbp+90h+var_E0]; lpMem
0x1400251fa  test    rcx, rcx
0x1400251fd  jz      short loc_140025208
0x1400251ff  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140025204  mov     [rbp+90h+var_E0], r13
0x140025208  lea     rdx, [rbp+90h+var_E0]
0x14002520c  mov     rcx, [rbp+90h+var_50]
0x140025210  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x140025215  mov     esi, eax
0x140025217  test    eax, eax
0x140025219  js      short loc_1400251BB
0x14002521b  movaps  xmm0, [rsp+190h+var_140]
0x140025220  movdqu  [rbp+90h+pExceptionObject], xmm0
0x140025225  mov     rax, [rsp+190h+var_128]
0x14002522a  mov     [rbp+90h+var_E0+8], rax
0x14002522e  mov     rax, [rsp+190h+var_120]
0x140025233  mov     [rbp+90h+var_D0], rax
0x140025237  cmp     [rsp+190h+var_118], r13d
0x14002523c  setnz   [rbp+90h+var_C8]
0x140025240  mov     rcx, [rbp+90h+var_C0+8]; lpMem
0x140025244  test    rcx, rcx
0x140025247  jz      short loc_14002524E
0x140025249  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14002524e  mov     rax, [rbp+90h+lpMem]
0x140025252  mov     [rbp+90h+var_C0+8], rax
0x140025256  mov     rcx, [rbp+90h+var_C0]; lpMem
0x14002525a  test    rcx, rcx
0x14002525d  jz      short loc_140025268
0x14002525f  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140025264  mov     [rbp+90h+var_C0], r13
0x140025268  lea     rdx, [rbp+90h+var_C0]; wchar_t **
0x14002526c  mov     rcx, [rbp+90h+lpMultiByteStr]; lpMultiByteStr
0x140025270  call    ?ConvertAnsiToWide_Alloc@@YAJPEBDPEAPEA_W@Z; ConvertAnsiToWide_Alloc(char const *,wchar_t * *)
0x140025275  mov     esi, eax
0x140025277  mov     rcx, [rbp+90h+lpMultiByteStr]; lpMem
0x14002527b  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140025280  test    esi, esi
0x140025282  js      loc_1400251BB
0x140025288  lea     rdx, [rbp+90h+pExceptionObject]; struct sih::SlsCacheEntry *
0x14002528c  call    ?UpdateEntry@SlsCache@sih@@QEAAJAEBUSlsCacheEntry@2@@Z; sih::SlsCache::UpdateEntry(sih::SlsCacheEntry const &)
0x140025291  mov     esi, eax
0x140025293  mov     rcx, [rbp+90h+var_C0+8]; lpMem
0x140025297  test    eax, eax
0x140025299  js      loc_1400251BF
0x14002529f  test    rcx, rcx
0x1400252a2  jz      short loc_1400252AD
0x1400252a4  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400252a9  mov     [rbp+90h+var_C0+8], r13
0x1400252ad  mov     rcx, [rbp+90h+var_C0]; lpMem
0x1400252b1  test    rcx, rcx
0x1400252b4  jz      short loc_1400252BF
0x1400252b6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400252bb  mov     [rbp+90h+var_C0], r13
0x1400252bf  mov     rcx, [rbp+90h+var_E0]; lpMem
0x1400252c3  test    rcx, rcx
0x1400252c6  jz      short loc_1400252CD
0x1400252c8  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400252cd  lea     rdx, [rsp+190h+var_150]; wchar_t **
0x1400252d2  mov     rcx, rdi; lpMultiByteStr
0x1400252d5  call    ?ConvertAnsiToWide_Alloc@@YAJPEBDPEAPEA_W@Z; ConvertAnsiToWide_Alloc(char const *,wchar_t * *)
0x1400252da  mov     esi, eax
0x1400252dc  test    eax, eax
0x1400252de  js      loc_1400253C3
0x1400252e4  mov     edx, [rsp+190h+var_15C]
0x1400252e8  cmp     rdx, [r14+18h]
0x1400252ec  ja      short loc_14002531D
0x1400252ee  mov     r15, r14
0x1400252f1  cmp     qword ptr [r14+18h], 7
0x1400252f6  jbe     short loc_1400252FB
0x1400252f8  mov     r15, [r14]
0x1400252fb  mov     [r14+10h], rdx
0x1400252ff  lea     rsi, [rdx+rdx]
0x140025303  mov     r8, rsi; Size
0x140025306  mov     rbx, [rsp+190h+var_150]
0x14002530b  mov     rdx, rbx; Src
0x14002530e  mov     rcx, r15; void *
0x140025311  call    memmove
0x140025316  mov     [rsi+r15], r13w
0x14002531b  jmp     short loc_14002532E
0x14002531d  mov     rbx, [rsp+190h+var_150]
0x140025322  mov     r9, rbx
0x140025325  mov     rcx, r14
0x140025328  call    ??$_Reallocate_for@V_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(unsigned __int64,_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *)
0x14002532d  nop
0x14002532e  test    rbx, rbx
0x140025331  jz      short loc_14002533C
0x140025333  mov     rcx, rbx; lpMem
0x140025336  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14002533b  nop
0x14002533c  test    rdi, rdi
0x14002533f  jz      short loc_14002534B
0x140025341  mov     rcx, rdi; pv
0x140025344  call    cs:__imp_CoTaskMemFree
0x14002534a  nop
0x14002534b  mov     rcx, [rbp+90h+Src]; lpMem
0x14002534f  test    rcx, rcx
0x140025352  jz      short loc_14002535D
0x140025354  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140025359  mov     [rbp+90h+Src], r13
0x14002535d  mov     rcx, [rbp+90h+var_88]; lpMem
0x140025361  test    rcx, rcx
0x140025364  jz      short loc_14002536F
0x140025366  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14002536b  mov     [rbp+90h+var_88], r13
0x14002536f  mov     rcx, [rbp+90h+bstrString]; bstrString
0x140025373  call    cs:__imp_SysFreeString
0x140025379  mov     [rbp+90h+bstrString], r13
0x14002537d  lea     rcx, [rbp+90h+var_40]
0x140025381  call    ??1?$XPtrBase@VAADDeviceDataBoundaryInfo@@U?$FreeMethodPolicy@VAADDeviceDataBoundaryInfo@@$1?FreeAADDeviceDataBoundaryInfo@@YAXPEAX@Z@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ; WuSmartPtr::XPtrBase<AADDeviceDataBoundaryInfo,WuSmartPtr::Policies::FreeMethodPolicy<AADDeviceDataBoundaryInfo,&FreeAADDeviceDataBoundaryInfo(void *)>>::~XPtrBase<AADDeviceDataBoundaryInfo,WuSmartPtr::Policies::FreeMethodPolicy<AADDeviceDataBoundaryInfo,&FreeAADDeviceDataBoundaryInfo(void *)>>(void)
0x140025386  mov     rcx, [rbp+90h+var_50]; lpMem
0x14002538a  test    rcx, rcx
0x14002538d  jz      short loc_140025394
0x14002538f  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140025394  mov     rax, r14
  ... truncated ...
```
