# CSecurityData::Init(IKdcBackend &)

- ea: `0x18005a5fc`
- end: `0x18005acca`
- name: `?Init@CSecurityData@@QEAAJAEAUIKdcBackend@@@Z`
- size: `1742`
- prototype: `NTSTATUS __fastcall(CSecurityData *this, struct IKdcBackend *, unsigned __int8)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003a5fc`

## callees

- `0x180002ad0`
- `0x180002edc`
- `0x1800038f0`
- `0x1800101c4`
- `0x1800101ec`
- `0x1800142cc`
- `0x180020230`
- `0x18003669c`
- `0x18005a060`
- `0x18005a5fc`
- `0x18005ae00`
- `0x18005b334`
- `0x180072338`
- `0x18007c4d4`
- `0x18007cad0`
- `0x18007cbb0`
- `0x18007da34`
- `0x180083c70`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18005a702`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18005a702`
- `ntdll!RtlInitUnicodeString` at `0x18005a6d7`
- `ntdll!RtlInitUnicodeString` at `0x18005a71e`
- `ntdll!RtlInitUnicodeString` at `0x18005aaaf`
- `ntdll!RtlInitUnicodeString` at `0x18005aac0`
- `ntdll!RtlInitUnicodeString` at `0x18005aad1`
- `ntdll!RtlInitUnicodeString` at `0x18005a6d7`
- `ntdll!RtlInitUnicodeString` at `0x18005a71e`
- `ntdll!RtlInitUnicodeString` at `0x18005aaaf`
- `ntdll!RtlInitUnicodeString` at `0x18005aac0`
- `ntdll!RtlInitUnicodeString` at `0x18005aad1`
- `ntdll!RtlInitializeGenericTable` at `0x18005ab9f`
- `ntdll!RtlInitializeGenericTable` at `0x18005ac1b`
- `ntdll!RtlInitializeGenericTable` at `0x18005ab9f`
- `ntdll!RtlInitializeGenericTable` at `0x18005ac1b`
- `SAMSRV!SamIQueryCapabilities` at `0x18005a6b7`
- `SAMSRV!SamIQueryCapabilities` at `0x18005a6b7`
- `LSASRV!LsaIRegisterPolicyChangeNotificationCallback` at `0x18005ac52`
- `LSASRV!LsaIRegisterPolicyChangeNotificationCallback` at `0x18005ac6a`
- `LSASRV!LsaIRegisterPolicyChangeNotificationCallback` at `0x18005ac52`
- `LSASRV!LsaIRegisterPolicyChangeNotificationCallback` at `0x18005ac6a`

## pseudocode

```c
NTSTATUS __fastcall CSecurityData::Init(CSecurityData *this, struct IKdcBackend *a2, unsigned __int8 a3)
{
  NTSTATUS result; // eax
  unsigned __int8 v4; // r8
  unsigned __int8 v5; // r8
  struct IKdcBackend *v6; // rax
  WCHAR *v7; // rax
  WCHAR *v8; // rax
  WCHAR *v9; // rax
  WCHAR *v10; // rax
  int v11; // r9d
  unsigned __int64 v12; // r8
  int v13; // r8d
  int v14; // r9d
  void *v15; // rdx
  CSecurityData *v16; // rcx
  int Parameters; // ebx
  CSecurityData *v18; // rcx
  __int64 v19; // rdx
  union _LARGE_INTEGER v20; // rbx
  struct _RTL_GENERIC_TABLE *v21; // rax
  struct _RTL_GENERIC_TABLE *v22; // rdi
  struct _RTL_GENERIC_TABLE *v23; // rax
  struct _RTL_GENERIC_TABLE *v24; // rdi
  CSecurityData *v25; // rcx
  int updated; // eax
  int v27; // ecx
  DWORD nSize; // [rsp+30h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-31h] BYREF
  struct _RTL_GENERIC_TABLE *v30; // [rsp+48h] [rbp-21h]
  struct _UNICODE_STRING v31; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING v32; // [rsp+60h] [rbp-9h] BYREF
  WCHAR Buffer[8]; // [rsp+70h] [rbp+7h] BYREF
  __int128 v34; // [rsp+80h] [rbp+17h]

  qword_1800B2F18 = (__int64)a2;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  DestinationString = 0;
  *(_OWORD *)Buffer = 0;
  v34 = 0;
  nSize = 16;
  v31 = 0;
  v32 = 0;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_39025eb542cc3a17cc5bb89d70ac2bcd_Traceguids);
  result = KerbDuplicateStringEx(&stru_1800B2D60, &GlobalDomainName, a3);
  if ( result < 0 )
    return result;
  if ( (unsigned int)KerbConvertUnicodeStringToRealm(&SecData, &GlobalDomainName) )
    return -1073741670;
  KdcGlobalCDC = (SamIQueryCapabilities() & 5) == 1;
  RtlInitUnicodeString(&DestinationString, L"krbtgt");
  result = KerbDuplicateStringEx(&String2, &DestinationString, v4);
  if ( result < 0 )
    return result;
  if ( !GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
    return -1073741789;
  RtlInitUnicodeString(&DestinationString, Buffer);
  result = KerbDuplicateStringEx(&::DestinationString, &DestinationString, v5);
  if ( result < 0 )
    return result;
  v6 = GlobalKdcService::Get();
  result = (*(__int64 (__fastcall **)(struct IKdcBackend *, struct _UNICODE_STRING *))(*(_QWORD *)v6 + 72LL))(
             v6,
             &DomainName2);
  if ( result < 0 )
    return result;
  if ( (unsigned int)KerbConvertUnicodeStringToRealm(&qword_1800B2D58, &DomainName2) )
    return -1073741670;
  stru_1800B2DE0.Length = ::DestinationString.Length + 2;
  stru_1800B2DE0.MaximumLength = ::DestinationString.Length + 4;
  v7 = (WCHAR *)MIDL_user_allocate((unsigned __int16)(::DestinationString.Length + 4));
  stru_1800B2DE0.Buffer = v7;
  if ( !v7 )
    return -1073741670;
  memcpy_0(v7, ::DestinationString.Buffer, ::DestinationString.Length);
  stru_1800B2DE0.Buffer[(unsigned __int64)::DestinationString.Length >> 1] = 36;
  stru_1800B2DE0.Buffer[(unsigned __int64)stru_1800B2DE0.Length >> 1] = 0;
  stru_1800B2DF0.Length = ::DestinationString.Length + DomainName2.Length + 4;
  stru_1800B2DF0.MaximumLength = ::DestinationString.Length + DomainName2.Length + 6;
  v8 = (WCHAR *)MIDL_user_allocate((unsigned __int16)(::DestinationString.Length + DomainName2.Length + 6));
  stru_1800B2DF0.Buffer = v8;
  if ( !v8 )
    return -1073741670;
  memcpy_0(v8, ::DestinationString.Buffer, ::DestinationString.Length);
  stru_1800B2DF0.Buffer[(unsigned __int64)::DestinationString.Length >> 1] = 36;
  stru_1800B2DF0.Buffer[((unsigned __int64)::DestinationString.Length >> 1) + 1] = 64;
  memcpy_0(
    &stru_1800B2DF0.Buffer[((unsigned __int64)::DestinationString.Length >> 1) + 2],
    DomainName2.Buffer,
    DomainName2.Length);
  stru_1800B2DF0.Buffer[(unsigned __int64)stru_1800B2DF0.Length >> 1] = 0;
  if ( (unsigned int)KerbBuildFullServiceName(&stru_1800B2D60, &String2, &stru_1800B2D90) )
    return -1073741670;
  if ( (unsigned int)KerbBuildFullServiceName(&DomainName2, &String2, &stru_1800B2DA0) )
    return -1073741670;
  stru_1800B2DC0.Length = stru_1800B2D60.Length + String2.Length + 2;
  stru_1800B2DC0.MaximumLength = stru_1800B2D60.Length + String2.Length + 4;
  v9 = (WCHAR *)MIDL_user_allocate((unsigned __int16)(stru_1800B2D60.Length + String2.Length + 4));
  stru_1800B2DC0.Buffer = v9;
  if ( !v9 )
    return -1073741670;
  memcpy_0(v9, String2.Buffer, String2.Length);
  stru_1800B2DC0.Buffer[(unsigned __int64)String2.Length >> 1] = 47;
  memcpy_0(
    &stru_1800B2DC0.Buffer[((unsigned __int64)String2.Length >> 1) + 1],
    stru_1800B2D60.Buffer,
    stru_1800B2D60.Length);
  stru_1800B2DC0.Buffer[(unsigned __int64)stru_1800B2DC0.Length >> 1] = 0;
  stru_1800B2DB0.Length = DomainName2.Length + String2.Length + 2;
  stru_1800B2DB0.MaximumLength = DomainName2.Length + String2.Length + 4;
  v10 = (WCHAR *)MIDL_user_allocate((unsigned __int16)(DomainName2.Length + String2.Length + 4));
  stru_1800B2DB0.Buffer = v10;
  if ( !v10 )
    return -1073741670;
  memcpy_0(v10, String2.Buffer, String2.Length);
  stru_1800B2DB0.Buffer[(unsigned __int64)String2.Length >> 1] = 47;
  memcpy_0(&stru_1800B2DB0.Buffer[((unsigned __int64)String2.Length >> 1) + 1], DomainName2.Buffer, DomainName2.Length);
  v12 = (unsigned __int64)stru_1800B2DB0.Length >> 1;
  stru_1800B2DB0.Buffer[v12] = 0;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_ZZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_39025eb542cc3a17cc5bb89d70ac2bcd_Traceguids,
      (unsigned int)&String2,
      (__int64)&::DestinationString);
  if ( (unsigned int)KerbBuildFullServiceKdcNameWithSid(
                       (unsigned int)&DomainName2,
                       (unsigned int)&String2,
                       v12,
                       v11,
                       (__int64)&xmmword_1800B2E20) )
    return -1073741670;
  RtlInitUnicodeString(&stru_1800B2E10, L"kadmin/changepw");
  RtlInitUnicodeString(&v31, L"kadmin");
  RtlInitUnicodeString(&v32, L"changepw");
  if ( (unsigned int)KerbBuildFullServiceKdcNameWithSid(
                       (unsigned int)&v32,
                       (unsigned int)&v31,
                       v13,
                       v14,
                       (__int64)(&xmmword_1800B2E20 + 1)) )
    return -1073741670;
  SkewTime.QuadPart = 3000000000LL;
  Parameters = CSecurityData::LoadParameters(v16, v15);
  if ( Parameters < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return Parameters;
    v19 = 17;
LABEL_29:
    WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_39025eb542cc3a17cc5bb89d70ac2bcd_Traceguids, (unsigned int)Parameters);
    return Parameters;
  }
  v20 = SkewTime;
  v21 = (struct _RTL_GENERIC_TABLE *)operator new(0x88u, (const struct std::nothrow_t *)std::nothrow);
  v22 = v21;
  v30 = v21;
  if ( v21 )
  {
    v21[1].TableRoot = (PRTL_SPLAY_LINKS)v20.QuadPart;
    LODWORD(v21[1].InsertOrderList.Flink) = 1;
    BYTE4(v21[1].InsertOrderList.Flink) = 0;
    LOBYTE(v21[1].FreeRoutine) = 0;
    RtlInitializeGenericTable(v21, (PRTL_GENERIC_COMPARE_ROUTINE)Compare, AuthenAllocate, AuthenFree, 0);
  }
  else
  {
    v22 = 0;
  }
  Authenticators = v22;
  if ( !v22 )
    return -1073741670;
  result = CAuthenticatorList::Init((CAuthenticatorList *)v22);
  if ( result < 0 )
    return result;
  v23 = (struct _RTL_GENERIC_TABLE *)operator new(0x88u, (const struct std::nothrow_t *)std::nothrow);
  v24 = v23;
  v30 = v23;
  if ( v23 )
  {
    v23[1].TableRoot = (PRTL_SPLAY_LINKS)v20.QuadPart;
    LODWORD(v23[1].InsertOrderList.Flink) = 1;
    BYTE4(v23[1].InsertOrderList.Flink) = 0;
    LOBYTE(v23[1].FreeRoutine) = 0;
    RtlInitializeGenericTable(v23, (PRTL_GENERIC_COMPARE_ROUTINE)Compare, AuthenAllocate, AuthenFree, 0);
  }
  else
  {
    v24 = 0;
  }
  ReplayDetect = v24;
  if ( !v24 )
    return -1073741670;
  result = CAuthenticatorList::Init((CAuthenticatorList *)v24);
  if ( result >= 0 )
  {
    result = AsNegCacheInit();
    if ( result >= 0 )
    {
      Parameters = LsaIRegisterPolicyChangeNotificationCallback(KdcPolicyChangeCallBack, 6);
      if ( Parameters < 0
        || (Parameters = LsaIRegisterPolicyChangeNotificationCallback(KdcPolicyChangeCallBack, 1), Parameters < 0) )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          return Parameters;
        }
        v19 = 18;
        goto LABEL_29;
      }
      updated = CSecurityData::UpdateKrbtgtTicketInfo(v25);
      v27 = 0;
      if ( updated < 0 )
        return updated;
      return v27;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005a5fc  push    rbp
0x18005a5fe  push    rbx
0x18005a5ff  push    rdi
0x18005a600  push    r13
0x18005a602  push    r15
0x18005a604  lea     rbp, [rsp-37h]
0x18005a609  sub     rsp, 0A0h
0x18005a610  mov     rax, cs:__security_cookie
0x18005a617  xor     rax, rsp
0x18005a61a  mov     [rbp+57h+var_30], rax
0x18005a61e  mov     cs:qword_1800B2F18, rdx
0x18005a625  test    rdx, rdx
0x18005a628  jnz     short loc_18005A62F
0x18005a62a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005a62f  xorps   xmm0, xmm0
0x18005a632  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18005a636  xorps   xmm1, xmm1
0x18005a639  movups  xmmword ptr [rbp+57h+Buffer], xmm1
0x18005a63d  movups  [rbp+57h+var_40], xmm1
0x18005a641  mov     [rbp+57h+nSize], 10h
0x18005a648  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x18005a64c  movups  xmmword ptr [rbp+57h+var_60.Length], xmm1
0x18005a650  lea     r13, WPP_GLOBAL_Control
0x18005a657  mov     bx, 4
0x18005a65b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a662  cmp     rcx, r13
0x18005a665  jz      short loc_18005A681
0x18005a667  test    [rcx+1Ch], bl
0x18005a66a  jz      short loc_18005A681
0x18005a66c  mov     edx, 0Fh
0x18005a671  lea     r8, WPP_39025eb542cc3a17cc5bb89d70ac2bcd_Traceguids
0x18005a678  mov     rcx, [rcx+10h]
0x18005a67c  call    WPP_SF_
0x18005a681  lea     rdx, ?GlobalDomainName@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x18005a688  lea     rcx, stru_1800B2D60; struct _UNICODE_STRING *
0x18005a68f  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18005a694  test    eax, eax
0x18005a696  js      loc_18005ACAF
0x18005a69c  lea     rdx, ?GlobalDomainName@@3U_UNICODE_STRING@@A; _UNICODE_STRING GlobalDomainName
0x18005a6a3  lea     rcx, ?SecData@@3VCSecurityData@@A; CSecurityData SecData
0x18005a6aa  call    KerbConvertUnicodeStringToRealm
0x18005a6af  test    eax, eax
0x18005a6b1  jnz     loc_18005ACAA
0x18005a6b7  call    cs:__imp_SamIQueryCapabilities
0x18005a6bd  and     al, 5
0x18005a6bf  xor     ecx, ecx
0x18005a6c1  cmp     al, 1
0x18005a6c3  setz    cl
0x18005a6c6  mov     cs:?KdcGlobalCDC@@3HA, ecx; int KdcGlobalCDC
0x18005a6cc  lea     rdx, aKrbtgt; "krbtgt"
0x18005a6d3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18005a6d7  call    cs:__imp_RtlInitUnicodeString
0x18005a6dd  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x18005a6e1  lea     rdi, String2
0x18005a6e8  mov     rcx, rdi; struct _UNICODE_STRING *
0x18005a6eb  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18005a6f0  test    eax, eax
0x18005a6f2  js      loc_18005ACAF
0x18005a6f8  lea     r8, [rbp+57h+nSize]; nSize
0x18005a6fc  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18005a700  xor     ecx, ecx; NameType
0x18005a702  call    cs:__imp_GetComputerNameExW
0x18005a708  test    eax, eax
0x18005a70a  jnz     short loc_18005A716
0x18005a70c  mov     eax, 0C0000023h
0x18005a711  jmp     loc_18005ACAF
0x18005a716  lea     rdx, [rbp+57h+Buffer]; SourceString
0x18005a71a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18005a71e  call    cs:__imp_RtlInitUnicodeString
0x18005a724  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x18005a728  lea     rcx, DestinationString; struct _UNICODE_STRING *
0x18005a72f  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18005a734  test    eax, eax
0x18005a736  js      loc_18005ACAF
0x18005a73c  call    ?Get@GlobalKdcService@@SAAEAUIKdcBackend@@XZ; GlobalKdcService::Get(void)
0x18005a741  mov     r8, rax
0x18005a744  mov     rcx, [rax]
0x18005a747  mov     rax, [rcx+48h]
0x18005a74b  lea     r15, DomainName2
0x18005a752  mov     rdx, r15
0x18005a755  mov     rcx, r8
0x18005a758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a75d  test    eax, eax
0x18005a75f  js      loc_18005ACAF
0x18005a765  mov     rdx, r15
0x18005a768  lea     rcx, qword_1800B2D58
0x18005a76f  call    KerbConvertUnicodeStringToRealm
0x18005a774  test    eax, eax
0x18005a776  jnz     loc_18005ACAA
0x18005a77c  movzx   ecx, cs:DestinationString.Length
0x18005a783  lea     eax, [rcx+2]
0x18005a786  mov     cs:stru_1800B2DE0.Length, ax
0x18005a78d  add     cx, bx
0x18005a790  movzx   ecx, cx; size
0x18005a793  mov     cs:stru_1800B2DE0.MaximumLength, cx
0x18005a79a  call    MIDL_user_allocate
0x18005a79f  mov     cs:stru_1800B2DE0.Buffer, rax
0x18005a7a6  test    rax, rax
0x18005a7a9  jz      loc_18005ACAA
0x18005a7af  movzx   r8d, cs:DestinationString.Length; Size
0x18005a7b7  mov     rdx, cs:DestinationString.Buffer; Src
0x18005a7be  mov     rcx, rax; void *
0x18005a7c1  call    memcpy_0
0x18005a7c6  movzx   ecx, cs:DestinationString.Length
0x18005a7cd  shr     rcx, 1
0x18005a7d0  mov     rax, cs:stru_1800B2DE0.Buffer
0x18005a7d7  mov     word ptr [rax+rcx*2], 24h ; '$'
0x18005a7dd  movzx   edx, cs:stru_1800B2DE0.Length
0x18005a7e4  shr     rdx, 1
0x18005a7e7  xor     ecx, ecx
0x18005a7e9  mov     rax, cs:stru_1800B2DE0.Buffer
0x18005a7f0  mov     [rax+rdx*2], cx
0x18005a7f4  movzx   ecx, cs:DomainName2.Length
0x18005a7fb  add     cx, cs:DestinationString.Length
0x18005a802  lea     eax, [rbx+rcx]
0x18005a805  mov     cs:stru_1800B2DF0.Length, ax
0x18005a80c  add     cx, 6
0x18005a810  movzx   ecx, cx; size
0x18005a813  mov     cs:stru_1800B2DF0.MaximumLength, cx
0x18005a81a  call    MIDL_user_allocate
0x18005a81f  mov     cs:stru_1800B2DF0.Buffer, rax
0x18005a826  test    rax, rax
0x18005a829  jz      loc_18005ACAA
0x18005a82f  movzx   r8d, cs:DestinationString.Length; Size
0x18005a837  mov     rdx, cs:DestinationString.Buffer; Src
0x18005a83e  mov     rcx, rax; void *
0x18005a841  call    memcpy_0
0x18005a846  movzx   ecx, cs:DestinationString.Length
0x18005a84d  shr     rcx, 1
0x18005a850  mov     rax, cs:stru_1800B2DF0.Buffer
0x18005a857  mov     word ptr [rax+rcx*2], 24h ; '$'
0x18005a85d  movzx   ecx, cs:DestinationString.Length
0x18005a864  shr     rcx, 1
0x18005a867  mov     rax, cs:stru_1800B2DF0.Buffer
0x18005a86e  mov     word ptr [rax+rcx*2+2], 40h ; '@'
0x18005a875  movzx   r8d, cs:DomainName2.Length; Size
0x18005a87d  movzx   edx, cs:DestinationString.Length
0x18005a884  shr     rdx, 1
0x18005a887  mov     rax, cs:stru_1800B2DF0.Buffer
0x18005a88e  add     rax, 4
0x18005a892  lea     rcx, [rax+rdx*2]; void *
0x18005a896  mov     rdx, cs:DomainName2.Buffer; Src
0x18005a89d  call    memcpy_0
0x18005a8a2  movzx   r8d, cs:stru_1800B2DF0.Length
0x18005a8aa  shr     r8, 1
0x18005a8ad  xor     edx, edx
0x18005a8af  mov     rax, cs:stru_1800B2DF0.Buffer
0x18005a8b6  mov     [rax+r8*2], dx
0x18005a8bb  lea     r8, stru_1800B2D90
0x18005a8c2  mov     rdx, rdi
0x18005a8c5  lea     rcx, stru_1800B2D60
0x18005a8cc  call    KerbBuildFullServiceName
0x18005a8d1  test    eax, eax
0x18005a8d3  jnz     loc_18005ACAA
0x18005a8d9  lea     r8, stru_1800B2DA0
0x18005a8e0  mov     rdx, rdi
0x18005a8e3  mov     rcx, r15
0x18005a8e6  call    KerbBuildFullServiceName
0x18005a8eb  test    eax, eax
0x18005a8ed  jnz     loc_18005ACAA
0x18005a8f3  movzx   ecx, cs:String2.Length
0x18005a8fa  add     cx, cs:stru_1800B2D60.Length
0x18005a901  lea     eax, [rcx+2]
0x18005a904  mov     cs:stru_1800B2DC0.Length, ax
0x18005a90b  add     cx, bx
0x18005a90e  movzx   ecx, cx; size
0x18005a911  mov     cs:stru_1800B2DC0.MaximumLength, cx
0x18005a918  call    MIDL_user_allocate
0x18005a91d  mov     cs:stru_1800B2DC0.Buffer, rax
0x18005a924  test    rax, rax
0x18005a927  jz      loc_18005ACAA
0x18005a92d  movzx   r8d, cs:String2.Length; Size
0x18005a935  mov     rdx, cs:String2.Buffer; Src
0x18005a93c  mov     rcx, rax; void *
0x18005a93f  call    memcpy_0
0x18005a944  movzx   ecx, cs:String2.Length
0x18005a94b  shr     rcx, 1
0x18005a94e  mov     rax, cs:stru_1800B2DC0.Buffer
0x18005a955  mov     word ptr [rax+rcx*2], 2Fh ; '/'
0x18005a95b  movzx   r8d, cs:stru_1800B2D60.Length; Size
0x18005a963  movzx   ecx, cs:String2.Length
0x18005a96a  shr     rcx, 1
0x18005a96d  mov     rax, cs:stru_1800B2DC0.Buffer
0x18005a974  add     rax, 2
0x18005a978  lea     rcx, [rax+rcx*2]; void *
0x18005a97c  mov     rdx, cs:stru_1800B2D60.Buffer; Src
0x18005a983  call    memcpy_0
0x18005a988  movzx   edx, cs:stru_1800B2DC0.Length
0x18005a98f  shr     rdx, 1
0x18005a992  xor     ecx, ecx
0x18005a994  mov     rax, cs:stru_1800B2DC0.Buffer
0x18005a99b  mov     [rax+rdx*2], cx
0x18005a99f  movzx   ecx, cs:String2.Length
0x18005a9a6  add     cx, cs:DomainName2.Length
0x18005a9ad  lea     eax, [rcx+2]
0x18005a9b0  mov     cs:stru_1800B2DB0.Length, ax
0x18005a9b7  add     cx, bx
0x18005a9ba  movzx   ecx, cx; size
0x18005a9bd  mov     cs:stru_1800B2DB0.MaximumLength, cx
0x18005a9c4  call    MIDL_user_allocate
0x18005a9c9  mov     cs:stru_1800B2DB0.Buffer, rax
0x18005a9d0  test    rax, rax
0x18005a9d3  jz      loc_18005ACAA
0x18005a9d9  movzx   r8d, cs:String2.Length; Size
0x18005a9e1  mov     rdx, cs:String2.Buffer; Src
0x18005a9e8  mov     rcx, rax; void *
0x18005a9eb  call    memcpy_0
0x18005a9f0  movzx   ecx, cs:String2.Length
0x18005a9f7  shr     rcx, 1
0x18005a9fa  mov     rax, cs:stru_1800B2DB0.Buffer
0x18005aa01  mov     word ptr [rax+rcx*2], 2Fh ; '/'
0x18005aa07  movzx   r8d, cs:DomainName2.Length; Size
0x18005aa0f  movzx   ecx, cs:String2.Length
0x18005aa16  shr     rcx, 1
0x18005aa19  mov     rax, cs:stru_1800B2DB0.Buffer
0x18005aa20  add     rax, 2
0x18005aa24  lea     rcx, [rax+rcx*2]; void *
0x18005aa28  mov     rdx, cs:DomainName2.Buffer; Src
0x18005aa2f  call    memcpy_0
0x18005aa34  movzx   r8d, cs:stru_1800B2DB0.Length
0x18005aa3c  shr     r8, 1
0x18005aa3f  xor     ecx, ecx
0x18005aa41  mov     rax, cs:stru_1800B2DB0.Buffer
0x18005aa48  mov     [rax+r8*2], cx
0x18005aa4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aa54  cmp     rcx, r13
0x18005aa57  jz      short loc_18005AA82
0x18005aa59  test    [rcx+1Ch], bl
0x18005aa5c  jz      short loc_18005AA82
0x18005aa5e  mov     edx, 10h
0x18005aa63  lea     rax, DestinationString
0x18005aa6a  mov     [rsp+0C0h+TableContext], rax
0x18005aa6f  mov     r9, rdi
0x18005aa72  lea     r8, WPP_39025eb542cc3a17cc5bb89d70ac2bcd_Traceguids
0x18005aa79  mov     rcx, [rcx+10h]
0x18005aa7d  call    WPP_SF_ZZ
0x18005aa82  lea     rax, xmmword_1800B2E20
0x18005aa89  mov     [rsp+0C0h+TableContext], rax
0x18005aa8e  mov     rdx, rdi
0x18005aa91  mov     rcx, r15
0x18005aa94  call    KerbBuildFullServiceKdcNameWithSid
0x18005aa99  test    eax, eax
0x18005aa9b  jnz     loc_18005ACAA
0x18005aaa1  lea     rdx, aKadminChangepw; "kadmin/changepw"
0x18005aaa8  lea     rcx, stru_1800B2E10; DestinationString
0x18005aaaf  call    cs:__imp_RtlInitUnicodeString
0x18005aab5  lea     rdx, aKadmin; "kadmin"
0x18005aabc  lea     rcx, [rbp+57h+var_70]; DestinationString
0x18005aac0  call    cs:__imp_RtlInitUnicodeString
0x18005aac6  lea     rdx, aChangepw; "changepw"
0x18005aacd  lea     rcx, [rbp+57h+var_60]; DestinationString
0x18005aad1  call    cs:__imp_RtlInitUnicodeString
0x18005aad7  lea     rax, xmmword_1800B2E20+8
0x18005aade  mov     [rsp+0C0h+TableContext], rax
0x18005aae3  lea     rdx, [rbp+57h+var_70]
0x18005aae7  lea     rcx, [rbp+57h+var_60]
0x18005aaeb  call    KerbBuildFullServiceKdcNameWithSid
0x18005aaf0  test    eax, eax
0x18005aaf2  jnz     loc_18005ACAA
0x18005aaf8  mov     eax, 0B2D05E00h
0x18005aafd  mov     qword ptr cs:?SkewTime@@3T_LARGE_INTEGER@@A, rax; _LARGE_INTEGER SkewTime ...
0x18005ab04  call    ?LoadParameters@CSecurityData@@QEAAJPEAX@Z; CSecurityData::LoadParameters(void *)
0x18005ab09  mov     ebx, eax
0x18005ab0b  test    eax, eax
0x18005ab0d  jns     short loc_18005AB40
0x18005ab0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ab16  cmp     rcx, r13
0x18005ab19  jz      short loc_18005AB39
0x18005ab1b  test    byte ptr [rcx+1Ch], 1
0x18005ab1f  jz      short loc_18005AB39
0x18005ab21  mov     edx, 11h
0x18005ab26  mov     r9d, ebx
0x18005ab29  lea     r8, WPP_39025eb542cc3a17cc5bb89d70ac2bcd_Traceguids
0x18005ab30  mov     rcx, [rcx+10h]
0x18005ab34  call    WPP_SF_d
0x18005ab39  mov     eax, ebx
0x18005ab3b  jmp     loc_18005ACAF
0x18005ab40  mov     rbx, qword ptr cs:?SkewTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER SkewTime ...
0x18005ab47  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005ab4e  mov     r15d, 88h
0x18005ab54  mov     ecx, r15d; unsigned __int64
0x18005ab57  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005ab5c  mov     rdi, rax
0x18005ab5f  mov     [rbp+57h+var_78], rax
0x18005ab63  test    rax, rax
0x18005ab66  jz      short loc_18005ABA7
0x18005ab68  mov     [rax+48h], rbx
0x18005ab6c  mov     dword ptr [rax+50h], 1
0x18005ab73  mov     byte ptr [rax+54h], 0
0x18005ab77  mov     byte ptr [rax+80h], 0
0x18005ab7e  mov     [rsp+0C0h+TableContext], 0; TableContext
0x18005ab87  lea     r9, ?AuthenFree@@YAXPEAU_RTL_GENERIC_TABLE@@PEAX@Z; FreeRoutine
0x18005ab8e  lea     r8, ?AuthenAllocate@@YAPEAXPEAU_RTL_GENERIC_TABLE@@K@Z; AllocateRoutine
0x18005ab95  lea     rdx, ?Compare@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_GENERIC_TABLE@@PEAX1@Z; CompareRoutine
0x18005ab9c  mov     rcx, rax; Table
0x18005ab9f  call    cs:__imp_RtlInitializeGenericTable
0x18005aba5  jmp     short loc_18005ABA9
0x18005aba7  xor     edi, edi
0x18005aba9  mov     cs:?Authenticators@@3PEAVCAuthenticatorList@@EA, rdi; CAuthenticatorList * Authenticators
0x18005abb0  test    rdi, rdi
  ... truncated ...
```
