# CConnectedUserStore::FindConnectedUserBySid(uchar *,ulong,IConnectedUser * *)

- ea: `0x180002500`
- end: `0x180002c78`
- name: `?FindConnectedUserBySid@CConnectedUserStore@@UEAAJPEAEKPEAPEAUIConnectedUser@@@Z`
- size: `1912`
- prototype: `__int64 __fastcall(CConnectedUserStore *this, unsigned __int8 *, __int64, struct IConnectedUser **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800014fc`
- `0x180002500`
- `0x180003560`
- `0x1800037a0`
- `0x180003a70`
- `0x180014430`
- `0x1800144b4`
- `0x1800144f4`
- `0x1800191ac`
- `0x180019210`
- `0x180019750`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000267f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800028fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002af0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000267f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800028fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002af0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800025ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800025ea`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000259e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800025df`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000259e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800025df`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000258d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000258d`
- `ntdll!RtlSubAuthoritySid` at `0x180002647`
- `ntdll!RtlSubAuthoritySid` at `0x180002647`
- `ntdll!RtlCopySid` at `0x180002605`
- `ntdll!RtlCopySid` at `0x180002605`
- `ntdll!RtlEqualSid` at `0x18000266e`
- `ntdll!RtlEqualSid` at `0x18000266e`
- `ntdll!RtlSubAuthorityCountSid` at `0x180002619`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000262b`
- `ntdll!RtlSubAuthorityCountSid` at `0x180002657`
- `ntdll!RtlSubAuthorityCountSid` at `0x180002619`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000262b`
- `ntdll!RtlSubAuthorityCountSid` at `0x180002657`

## string_xrefs

- `0x1800025ac`: `CConnectedUserStore::GetRidFromLocalSid`
- `0x180002861`: `CConnectedUserStore::CoCreateConnectedUser`
- `0x180002b62`: `CConnectedUserStore::CoCreateConnectedUser`
- `0x180002bc4`: `CConnectedUserStore::CoCreateConnectedUser`
- `0x1800027be`: `CConnectedUserStore::FindConnectedUserBySid`
- `0x1800029d7`: `CConnectedUserStore::FindConnectedUserBySid`
- `0x180002c62`: `CConnectedUserStore::FindConnectedUserBySid`

## pseudocode

```c
__int64 __fastcall CConnectedUserStore::FindConnectedUserBySid(
        CConnectedUserStore *this,
        unsigned __int8 *a2,
        __int64 a3,
        struct IConnectedUser **a4)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // xmm6
  ULONG v5; // r15d
  DWORD v7; // edi
  CConnectedUserStore *v9; // r13
  CIdentityProfileHandler *v10; // rcx
  unsigned int v11; // esi
  ULONG LengthSid; // r12d
  void *v13; // rax
  void *v14; // rdi
  NTSTATUS v15; // r12d
  int v16; // r13d
  __int64 v17; // rdx
  __int64 v18; // r8
  int v19; // edi
  int v20; // eax
  struct IConnectedUser *v21; // rbx
  int v22; // eax
  CConnectedUser *v23; // r12
  struct IConnectedUserSite *v24; // r9
  __int64 v25; // rdx
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // r8
  int RidFromInternetSid; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r9
  int v37; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v38; // [rsp+34h] [rbp-4Ch] BYREF
  CConnectedUser *v39; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v40; // [rsp+40h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v41; // [rsp+50h] [rbp-30h] BYREF

  v4 = (struct _EVENT_DATA_DESCRIPTOR)GUID_NULL;
  v5 = 0;
  v39 = this;
  v38 = 0;
  v41 = (struct _EVENT_DATA_DESCRIPTOR)GUID_NULL;
  v7 = a3;
  v9 = this;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CConnectedUserStore::FindConnectedUserBySid");
    v10 = WPP_GLOBAL_Control;
  }
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
  {
    McGenEventWrite_EventWriteTransfer((int)v10, (int)&FindUserBySidStart, a3, (int)a4, &v40);
    v10 = WPP_GLOBAL_Control;
  }
  v11 = -2147024809;
  if ( !a2 )
  {
    if ( v10 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v10 + 2), 73, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, 2147500035LL);
      v10 = WPP_GLOBAL_Control;
    }
    v19 = -2147467261;
    goto LABEL_40;
  }
  if ( !IsValidSid(a2) || GetLengthSid(a2) > v7 )
  {
    v10 = WPP_GLOBAL_Control;
    v19 = -2147024809;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_40;
    }
    v25 = 74;
    v26 = 2147942487LL;
    goto LABEL_65;
  }
  v37 = 0;
  *(_QWORD *)&v40.Size = "CConnectedUserStore::GetRidFromLocalSid";
  v40.Ptr = (ULONGLONG)&v37;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CConnectedUserStore::GetRidFromLocalSid");
  }
  LengthSid = GetLengthSid(a2);
  v13 = CoTaskMemAlloc(LengthSid);
  v14 = v13;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, 3221225626LL);
    }
    CoTaskMemFree(0);
    v19 = -805306214;
    v37 = -805306214;
    CLogBlock::~CLogBlock((CLogBlock *)&v40, v31, v32);
    goto LABEL_69;
  }
  v15 = RtlCopySid(LengthSid, v13, a2);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids,
        (unsigned int)v15);
    }
  }
  else
  {
    v16 = *RtlSubAuthorityCountSid(v14);
    if ( v16 != *RtlSubAuthorityCountSid(*((PSID *)v39 + 11)) + 1 )
    {
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, 3221225592LL);
      }
      CoTaskMemFree(v14);
      v19 = -805306248;
      v37 = -805306248;
      CLogBlock::~CLogBlock((CLogBlock *)&v40, v33, v34);
      v9 = v39;
      goto LABEL_69;
    }
    v5 = *RtlSubAuthoritySid(v14, v16 - 1);
    v38 = v5;
    *RtlSubAuthorityCountSid(v14) = v16 - 1;
    v9 = v39;
    if ( !RtlEqualSid(*((PSID *)v39 + 11), v14) )
    {
      v15 = -1073741704;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, 3221225592LL);
        CoTaskMemFree(v14);
        v19 = -805306248;
        v37 = -805306248;
        CLogBlock::~CLogBlock((CLogBlock *)&v40, v27, v28);
LABEL_69:
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            75,
            WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids,
            (unsigned int)v19);
        }
        RidFromInternetSid = CConnectedUserStore::GetRidFromInternetSid(v9, a2, &v38, (struct _GUID *)&v41);
        v19 = RidFromInternetSid;
        if ( RidFromInternetSid >= 0 )
        {
          v5 = v38;
          v20 = 0;
          v4 = v41;
          goto LABEL_20;
        }
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
LABEL_40:
          if ( !a4 )
            goto LABEL_43;
          *a4 = 0;
          goto LABEL_42;
        }
        v25 = 76;
        v26 = (unsigned int)RidFromInternetSid;
LABEL_65:
        WPP_SF_d(*((_QWORD *)v10 + 2), v25, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v26);
        v10 = WPP_GLOBAL_Control;
        goto LABEL_40;
      }
    }
  }
  CoTaskMemFree(v14);
  v19 = 0;
  if ( v15 < 0 )
    v19 = v15 | 0x10000000;
  v37 = v19;
  CLogBlock::~CLogBlock((CLogBlock *)&v40, v17, v18);
  if ( v19 < 0 )
    goto LABEL_69;
  v20 = 1;
LABEL_20:
  if ( !a4 && !v20 )
    goto LABEL_42;
  v21 = 0;
  v39 = 0;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CConnectedUserStore::CoCreateConnectedUser");
  }
  v22 = ATL::CComObject<CConnectedUser>::CreateInstance(&v39);
  v19 = v22;
  if ( v22 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      goto LABEL_37;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_59;
    v35 = 105;
    v36 = (unsigned int)v22;
LABEL_99:
    WPP_SF_d(*((_QWORD *)v10 + 2), v35, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v36);
    v10 = WPP_GLOBAL_Control;
    goto LABEL_59;
  }
  v23 = v39;
  (*(void (__fastcall **)(CConnectedUser *))(*(_QWORD *)v39 + 8LL))(v39);
  v41 = v4;
  v24 = (CConnectedUserStore *)((char *)v9 + 8);
  if ( !v9 )
    v24 = 0;
  v19 = CConnectedUser::InitializeConnectedUser(v23, v5, (struct _GUID *)&v41, v24);
  if ( v19 >= 0 )
  {
    v21 = v23;
    goto LABEL_29;
  }
  (*(void (__fastcall **)(CConnectedUser *))(*(_QWORD *)v23 + 16LL))(v23);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
  {
LABEL_37:
    if ( v21 )
    {
      (*(void (__fastcall **)(struct IConnectedUser *))(*(_QWORD *)v21 + 16LL))(v21);
      v10 = WPP_GLOBAL_Control;
    }
    v19 = -805305819;
    goto LABEL_40;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v35 = 106;
    v36 = (unsigned int)v19;
    goto LABEL_99;
  }
LABEL_59:
  if ( v10 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
    goto LABEL_37;
  if ( (*((_BYTE *)v10 + 28) & 4) == 0 )
    goto LABEL_30;
  WPP_SF_sL(*((_QWORD *)v10 + 2), (_DWORD)a2, a3, (unsigned int)"CConnectedUserStore::CoCreateConnectedUser", v19);
LABEL_29:
  v10 = WPP_GLOBAL_Control;
LABEL_30:
  if ( v10 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)v10 + 2), 12, a3, "CConnectedUserStore::CoCreateConnectedUser");
    v10 = WPP_GLOBAL_Control;
  }
  if ( v19 < 0 )
  {
    if ( v10 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
    {
      WPP_SF_DD(*((_QWORD *)v10 + 2), 77, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v5, v19);
      v10 = WPP_GLOBAL_Control;
    }
    goto LABEL_37;
  }
  if ( a4 )
  {
    *a4 = v21;
    goto LABEL_42;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(struct IConnectedUser *))(*(_QWORD *)v21 + 16LL))(v21);
LABEL_42:
    v10 = WPP_GLOBAL_Control;
  }
LABEL_43:
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
  {
    McGenEventWrite_EventWriteTransfer((int)v10, (int)&FindUserBySidStop, a3, (int)a4, &v41);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v19 == -805306334 )
  {
    v11 = -2147024891;
  }
  else if ( v19 != -805306355 )
  {
    v11 = v19;
    if ( v19 >= 0 )
      goto LABEL_73;
  }
  if ( v10 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
    return v11;
  if ( (*((_BYTE *)v10 + 28) & 4) != 0 )
  {
    WPP_SF_sL(*((_QWORD *)v10 + 2), (_DWORD)a2, a3, (unsigned int)"CConnectedUserStore::FindConnectedUserBySid", v19);
    v10 = WPP_GLOBAL_Control;
  }
LABEL_73:
  if ( v10 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x400) != 0 )
    WPP_SF_s(*((_QWORD *)v10 + 2), 12, a3, "CConnectedUserStore::FindConnectedUserBySid");
  return v11;
}

```

## disassembly

```asm
0x180002500  mov     [rsp-38h+arg_10], rbx
0x180002505  push    rbp
0x180002506  push    rsi
0x180002507  push    rdi
0x180002508  push    r12
0x18000250a  push    r13
0x18000250c  push    r14
0x18000250e  push    r15
0x180002510  mov     rbp, rsp
0x180002513  sub     rsp, 80h
0x18000251a  movaps  [rsp+80h+var_10], xmm6
0x18000251f  mov     rax, cs:__security_cookie
0x180002526  xor     rax, rsp
0x180002529  mov     [rbp+var_20], rax
0x18000252d  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x180002534  xor     r15d, r15d
0x180002537  mov     [rbp+var_48], rcx
0x18000253b  mov     r14, r9
0x18000253e  mov     [rbp+var_4C], r15d
0x180002542  movaps  xmmword ptr [rbp+var_30.Ptr], xmm6
0x180002546  mov     edi, r8d
0x180002549  mov     rbx, rdx
0x18000254c  mov     r13, rcx
0x18000254f  mov     rcx, cs:WPP_GLOBAL_Control; int
0x180002556  lea     r12, WPP_GLOBAL_Control
0x18000255d  cmp     rcx, r12
0x180002560  jz      short loc_18000256F
0x180002562  test    dword ptr [rcx+1Ch], 400h
0x180002569  jnz     loc_1800029D3
0x18000256f  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x180002576  jnz     loc_1800029F4
0x18000257c  mov     esi, 80070057h
0x180002581  test    rbx, rbx
0x180002584  jz      loc_1800027DA
0x18000258a  mov     rcx, rbx; pSid
0x18000258d  call    cs:__imp_IsValidSid
0x180002593  test    eax, eax
0x180002595  jz      loc_180002876
0x18000259b  mov     rcx, rbx; pSid
0x18000259e  call    cs:__imp_GetLengthSid
0x1800025a4  cmp     eax, edi
0x1800025a6  ja      loc_180002876
0x1800025ac  lea     r9, aCconnecteduser_4; "CConnectedUserStore::GetRidFromLocalSid"
0x1800025b3  mov     [rbp+var_50], r15d
0x1800025b7  lea     rax, [rbp+var_50]
0x1800025bb  mov     qword ptr [rbp+var_40.Size], r9
0x1800025bf  mov     [rbp+var_40.Ptr], rax
0x1800025c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025ca  cmp     rcx, r12
0x1800025cd  jz      short loc_1800025DC
0x1800025cf  test    dword ptr [rcx+1Ch], 400h
0x1800025d6  jnz     loc_180002A15
0x1800025dc  mov     rcx, rbx; pSid
0x1800025df  call    cs:__imp_GetLengthSid
0x1800025e5  mov     ecx, eax; cb
0x1800025e7  mov     r12d, eax
0x1800025ea  call    cs:__imp_CoTaskMemAlloc
0x1800025f0  mov     rdi, rax
0x1800025f3  test    rax, rax
0x1800025f6  jz      loc_180002A28
0x1800025fc  mov     r8, rbx; SourceSid
0x1800025ff  mov     rdx, rax; DestinationSid
0x180002602  mov     ecx, r12d; DestinationSidLength
0x180002605  call    cs:__imp_RtlCopySid
0x18000260b  mov     r12d, eax
0x18000260e  test    eax, eax
0x180002610  js      loc_180002A7B
0x180002616  mov     rcx, rdi; Sid
0x180002619  call    cs:__imp_RtlSubAuthorityCountSid
0x18000261f  mov     rcx, [rbp+var_48]
0x180002623  movzx   r13d, byte ptr [rax]
0x180002627  mov     rcx, [rcx+58h]; Sid
0x18000262b  call    cs:__imp_RtlSubAuthorityCountSid
0x180002631  mov     edx, r13d
0x180002634  movzx   ecx, byte ptr [rax]
0x180002637  inc     ecx
0x180002639  cmp     r13d, ecx
0x18000263c  jnz     loc_180002AB9
0x180002642  dec     edx; SubAuthority
0x180002644  mov     rcx, rdi; Sid
0x180002647  call    cs:__imp_RtlSubAuthoritySid
0x18000264d  mov     rcx, rdi; Sid
0x180002650  mov     r15d, [rax]
0x180002653  mov     [rbp+var_4C], r15d
0x180002657  call    cs:__imp_RtlSubAuthorityCountSid
0x18000265d  dec     r13b
0x180002660  mov     rdx, rdi; Sid2
0x180002663  mov     [rax], r13b
0x180002666  mov     r13, [rbp+var_48]
0x18000266a  mov     rcx, [r13+58h]; Sid1
0x18000266e  call    cs:__imp_RtlEqualSid
0x180002674  test    al, al
0x180002676  jz      loc_1800028B9
0x18000267c  mov     rcx, rdi; pv
0x18000267f  call    cs:__imp_CoTaskMemFree
0x180002685  mov     eax, r12d
0x180002688  lea     rcx, [rbp+var_40]; this
0x18000268c  bts     eax, 1Ch
0x180002690  xor     edi, edi
0x180002692  test    r12d, r12d
0x180002695  cmovs   edi, eax
0x180002698  mov     [rbp+var_50], edi
0x18000269b  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x1800026a0  test    edi, edi
0x1800026a2  js      loc_180002915
0x1800026a8  mov     eax, 1
0x1800026ad  lea     r12, WPP_GLOBAL_Control
0x1800026b4  test    r14, r14
0x1800026b7  jz      loc_18000280C
0x1800026bd  xor     ebx, ebx
0x1800026bf  mov     [rbp+var_48], rbx
0x1800026c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026ca  cmp     rcx, r12
0x1800026cd  jz      short loc_1800026DC
0x1800026cf  test    dword ptr [rcx+1Ch], 400h
0x1800026d6  jnz     loc_180002B5E
0x1800026dc  lea     rcx, [rbp+var_48]
0x1800026e0  call    ?CreateInstance@?$CComObject@VCConnectedUser@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CConnectedUser>::CreateInstance(ATL::CComObject<CConnectedUser> * *)
0x1800026e5  mov     edi, eax
0x1800026e7  test    eax, eax
0x1800026e9  js      loc_180002B78
0x1800026ef  mov     r12, [rbp+var_48]
0x1800026f3  mov     rcx, r12
0x1800026f6  mov     rax, [r12]
0x1800026fa  mov     rax, [rax+8]
0x1800026fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002703  xor     eax, eax
0x180002705  movdqa  xmmword ptr [rbp+var_30.Ptr], xmm6
0x18000270a  test    r13, r13
0x18000270d  lea     r9, [r13+8]
0x180002711  lea     r8, [rbp+var_30]; struct _GUID
0x180002715  mov     edx, r15d; unsigned int
0x180002718  cmovz   r9, rax; struct IConnectedUserSite *
0x18000271c  mov     rcx, r12; this
0x18000271f  call    ?InitializeConnectedUser@CConnectedUser@@QEAAJKU_GUID@@PEAVIConnectedUserSite@@@Z; CConnectedUser::InitializeConnectedUser(ulong,_GUID,IConnectedUserSite *)
0x180002724  mov     edi, eax
0x180002726  test    eax, eax
0x180002728  js      loc_180002819
0x18000272e  mov     rbx, r12
0x180002731  lea     r12, WPP_GLOBAL_Control
0x180002738  mov     rcx, cs:WPP_GLOBAL_Control
0x18000273f  cmp     rcx, r12
0x180002742  jz      short loc_180002751
0x180002744  test    dword ptr [rcx+1Ch], 400h
0x18000274b  jnz     loc_180002BC0
0x180002751  test    edi, edi
0x180002753  jns     loc_1800027EA
0x180002759  cmp     rcx, r12
0x18000275c  jz      short loc_180002768
0x18000275e  test    byte ptr [rcx+1Ch], 4
0x180002762  jnz     loc_180002BE1
0x180002768  test    rbx, rbx
0x18000276b  jnz     loc_180002C09
0x180002771  mov     edi, 0D0000225h
0x180002776  test    r14, r14
0x180002779  jz      short loc_180002789
0x18000277b  mov     qword ptr [r14], 0
0x180002782  mov     rcx, cs:WPP_GLOBAL_Control; int
0x180002789  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x180002790  jnz     loc_180002C2C
0x180002796  cmp     edi, 0D0000022h
0x18000279c  jnz     loc_180002C4D
0x1800027a2  mov     esi, 80070005h
0x1800027a7  cmp     rcx, r12
0x1800027aa  jz      loc_180002974
0x1800027b0  test    byte ptr [rcx+1Ch], 4
0x1800027b4  jz      loc_180002962
0x1800027ba  mov     rcx, [rcx+10h]
0x1800027be  lea     r9, aCconnecteduser_13; "CConnectedUserStore::FindConnectedUserB"...
0x1800027c5  mov     dword ptr [rsp+80h+var_60], edi
0x1800027c9  call    WPP_SF_sL
0x1800027ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027d5  jmp     loc_180002962
0x1800027da  cmp     rcx, r12
0x1800027dd  jnz     loc_1800029A2
0x1800027e3  mov     edi, 80004003h
0x1800027e8  jmp     short loc_180002776
0x1800027ea  test    r14, r14
0x1800027ed  jnz     loc_180002C24
0x1800027f3  test    rbx, rbx
0x1800027f6  jz      short loc_180002789
0x1800027f8  mov     rax, [rbx]
0x1800027fb  mov     rcx, rbx
0x1800027fe  mov     rax, [rax+10h]
0x180002802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002807  jmp     loc_180002782
0x18000280c  test    eax, eax
0x18000280e  jnz     loc_1800026BD
0x180002814  jmp     loc_180002782
0x180002819  mov     rax, [r12]
0x18000281d  mov     rcx, r12
0x180002820  mov     rax, [rax+10h]
0x180002824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002829  mov     rcx, cs:WPP_GLOBAL_Control
0x180002830  lea     r12, WPP_GLOBAL_Control
0x180002837  cmp     rcx, r12
0x18000283a  jz      loc_180002768
0x180002840  test    byte ptr [rcx+1Ch], 4
0x180002844  jnz     loc_180002B9C
0x18000284a  cmp     rcx, r12
0x18000284d  jz      loc_180002768
0x180002853  test    byte ptr [rcx+1Ch], 4
0x180002857  jz      loc_18000273F
0x18000285d  mov     rcx, [rcx+10h]
0x180002861  lea     r9, aCconnecteduser_6; "CConnectedUserStore::CoCreateConnectedU"...
0x180002868  mov     dword ptr [rsp+80h+var_60], edi
0x18000286c  call    WPP_SF_sL
0x180002871  jmp     loc_180002738
0x180002876  mov     rcx, cs:WPP_GLOBAL_Control
0x18000287d  mov     edi, esi
0x18000287f  cmp     rcx, r12
0x180002882  jz      loc_180002776
0x180002888  test    byte ptr [rcx+1Ch], 4
0x18000288c  jz      loc_180002776
0x180002892  mov     edx, 4Ah ; 'J'
0x180002897  mov     r9d, 80070057h
0x18000289d  mov     rcx, [rcx+10h]
0x1800028a1  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x1800028a8  call    WPP_SF_d
0x1800028ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028b4  jmp     loc_180002776
0x1800028b9  mov     r12d, 0C0000078h
0x1800028bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028c6  lea     rax, WPP_GLOBAL_Control
0x1800028cd  cmp     rcx, rax
0x1800028d0  jz      loc_18000267C
0x1800028d6  test    byte ptr [rcx+1Ch], 4
0x1800028da  jz      loc_18000267C
0x1800028e0  mov     rcx, [rcx+10h]
0x1800028e4  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x1800028eb  mov     edx, 43h ; 'C'
0x1800028f0  mov     r9d, 0C0000078h
0x1800028f6  call    WPP_SF_d
0x1800028fb  mov     rcx, rdi; pv
0x1800028fe  call    cs:__imp_CoTaskMemFree
0x180002904  mov     edi, 0D0000078h
0x180002909  lea     rcx, [rbp+var_40]; this
0x18000290d  mov     [rbp+var_50], edi
0x180002910  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x180002915  lea     r12, WPP_GLOBAL_Control
0x18000291c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002923  cmp     rcx, r12
0x180002926  jnz     loc_180002B10
0x18000292c  lea     r9, [rbp+var_30]; struct _GUID *
0x180002930  mov     rdx, rbx; Sid
0x180002933  lea     r8, [rbp+var_4C]; unsigned int *
0x180002937  mov     rcx, r13; this
0x18000293a  call    ?GetRidFromInternetSid@CConnectedUserStore@@AEAAJPEAXPEAKPEAU_GUID@@@Z; CConnectedUserStore::GetRidFromInternetSid(void *,ulong *,_GUID *)
0x18000293f  mov     edi, eax
0x180002941  test    eax, eax
0x180002943  js      loc_180002B37
0x180002949  mov     r15d, [rbp+var_4C]
0x18000294d  xor     eax, eax
0x18000294f  movaps  xmm6, xmmword ptr [rbp+var_30.Ptr]
0x180002953  jmp     loc_1800026B4
0x180002958  mov     esi, edi
0x18000295a  test    edi, edi
0x18000295c  js      loc_1800027A7
0x180002962  cmp     rcx, r12
0x180002965  jz      short loc_180002974
0x180002967  test    dword ptr [rcx+1Ch], 400h
0x18000296e  jnz     loc_180002C5E
0x180002974  mov     eax, esi
0x180002976  mov     rcx, [rbp+var_20]
0x18000297a  xor     rcx, rsp; StackCookie
0x18000297d  call    __security_check_cookie
0x180002982  mov     rbx, [rsp+80h+arg_10]
0x18000298a  movaps  xmm6, [rsp+80h+var_10]
0x18000298f  add     rsp, 80h
0x180002996  pop     r15
0x180002998  pop     r14
0x18000299a  pop     r13
0x18000299c  pop     r12
0x18000299e  pop     rdi
0x18000299f  pop     rsi
0x1800029a0  pop     rbp
0x1800029a1  retn
0x1800029a2  test    byte ptr [rcx+1Ch], 4
0x1800029a6  jz      loc_1800027E3
0x1800029ac  mov     rcx, [rcx+10h]
0x1800029b0  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x1800029b7  mov     edx, 49h ; 'I'
0x1800029bc  mov     r9d, 80004003h
0x1800029c2  call    WPP_SF_d
0x1800029c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029ce  jmp     loc_1800027E3
0x1800029d3  mov     rcx, [rcx+10h]
0x1800029d7  lea     r9, aCconnecteduser_13; "CConnectedUserStore::FindConnectedUserB"...
0x1800029de  mov     edx, 0Ah
0x1800029e3  call    WPP_SF_s
0x1800029e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029ef  jmp     loc_18000256F
0x1800029f4  lea     rax, [rbp+var_40]
0x1800029f8  lea     rdx, FindUserBySidStart; int
0x1800029ff  mov     [rsp+80h+var_60], rax; PEVENT_DATA_DESCRIPTOR
0x180002a04  call    McGenEventWrite_EventWriteTransfer
0x180002a09  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a10  jmp     loc_18000257C
0x180002a15  mov     rcx, [rcx+10h]
0x180002a19  mov     edx, 0Ah
  ... truncated ...
```
