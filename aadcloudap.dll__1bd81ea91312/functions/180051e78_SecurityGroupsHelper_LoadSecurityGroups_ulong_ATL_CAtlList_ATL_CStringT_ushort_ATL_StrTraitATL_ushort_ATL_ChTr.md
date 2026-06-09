# SecurityGroupsHelper::LoadSecurityGroups(ulong,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)

- ea: `0x180051e78`
- end: `0x1800522eb`
- name: `?LoadSecurityGroups@SecurityGroupsHelper@@CAJKAEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z`
- size: `1139`
- prototype: `__int64 __fastcall(DWORD nSubAuthority1)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800522f4`

## callees

- `0x180003c20`
- `0x180004a24`
- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x1800090d0`
- `0x1800399b8`
- `0x180039e70`
- `0x18003d390`
- `0x18004e228`
- `0x180050598`
- `0x180051970`
- `0x180051e78`
- `0x180071e14`
- `0x1800779bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005203b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052045`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005204d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005203b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052045`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005204d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180051f8c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180051f8c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800522a2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800522a2`
- `samcli!NetLocalGroupGetMembers` at `0x1800520b4`
- `samcli!NetLocalGroupGetMembers` at `0x1800520b4`
- `netutils!NetApiBufferFree` at `0x180052293`
- `netutils!NetApiBufferFree` at `0x180052293`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180052031`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180052031`

## string_xrefs

- `0x180051f36`: `SecurityGroupsHelper::LoadSecurityGroups`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SecurityGroupsHelper::LoadSecurityGroups(DWORD nSubAuthority1, __int64 a2)
{
  int v4; // edx
  int v5; // r8d
  int v6; // r9d
  signed int Members; // eax
  int v8; // esi
  int v9; // ebx
  const WCHAR *v10; // rbx
  const WCHAR *v11; // rax
  unsigned int v12; // ebx
  DWORD nSubAuthority2[2]; // [rsp+20h] [rbp-E0h]
  DWORD nSubAuthority4[2]; // [rsp+30h] [rbp-D0h]
  DWORD nSubAuthority4a[2]; // [rsp+30h] [rbp-D0h]
  unsigned int v17; // [rsp+60h] [rbp-A0h] BYREF
  DWORD entriesread; // [rsp+64h] [rbp-9Ch] BYREF
  LPBYTE bufptr; // [rsp+68h] [rbp-98h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchReferencedDomainName; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  DWORD totalentries; // [rsp+7Ch] [rbp-84h] BYREF
  int v24; // [rsp+80h] [rbp-80h] BYREF
  int v25; // [rsp+84h] [rbp-7Ch] BYREF
  const WCHAR *v26; // [rsp+88h] [rbp-78h] BYREF
  PSID Sid; // [rsp+90h] [rbp-70h] BYREF
  __int64 v28; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v29[80]; // [rsp+A0h] [rbp-60h] BYREF
  const char *v30[6]; // [rsp+F0h] [rbp-10h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+120h] [rbp+20h] BYREF
  WCHAR Name[264]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+340h] [rbp+240h] BYREF

  v17 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  bufptr = 0;
  Sid = 0;
  memset_0(Name, 0, 0x208u);
  cchName = 260;
  memset_0(ReferencedDomainName, 0, 0x208u);
  cchReferencedDomainName = 260;
  entriesread = 0;
  totalentries = 0;
  peUse = 0;
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>>>::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>>>(
    (unsigned int)v29,
    v4,
    v5,
    v6,
    LODWORD(FLOAT_2_25));
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v30,
    (int)"securitygroupshelper.cpp",
    (int)"SecurityGroupsHelper::LoadSecurityGroups",
    (int)&v17);
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, nSubAuthority1, 0, 0, 0, 0, 0, 0, &Sid) )
  {
    Members = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
    v17 = Members;
    if ( Members < 0 )
    {
      nSubAuthority4[0] = 156;
LABEL_7:
      nSubAuthority2[0] = Members;
      WPPTraceLogA(
        2,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        2,
        *(_QWORD *)nSubAuthority2,
        "securitygroupshelper.cpp",
        *(_QWORD *)nSubAuthority4,
        "NTSTATUS",
        &base);
      goto LABEL_27;
    }
  }
  if ( !LookupAccountSidW(0, Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    Members = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
    v17 = Members;
    if ( Members < 0 )
    {
      nSubAuthority4[0] = 161;
      goto LABEL_7;
    }
  }
  Members = NetLocalGroupGetMembers(0, Name, 0, &bufptr, 0xFFFFFFFF, &entriesread, &totalentries, 0);
  v17 = Members;
  if ( Members < 0 )
  {
    nSubAuthority4[0] = 164;
    goto LABEL_7;
  }
  v8 = 0;
  if ( !entriesread )
    goto LABEL_27;
  while ( (int)SecurityGroupsHelper::CheckSidIsAad(*(PSID *)&bufptr[8 * v8]) < 0 )
  {
LABEL_24:
    if ( ++v8 >= entriesread )
      goto LABEL_27;
  }
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v26);
  v9 = StringUtility::SidToString(*(PSID *)&bufptr[8 * v8]);
  if ( v9 >= 0 )
  {
    v25 = 0;
    v24 = 0;
    v28 = 0;
    v10 = v26;
    if ( !ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNode(
            (unsigned int)v29,
            (_DWORD)v26,
            (unsigned int)&v25,
            (unsigned int)&v24,
            (__int64)&v28) )
    {
      ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
        a2,
        v10);
      *(_DWORD *)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,int,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<int>>::operator[](
                   v29,
                   v10) = 1;
      WPPTraceLogA(
        4,
        0,
        "%x 0x%08x %s:%u : %s:%u",
        4,
        0,
        "securitygroupshelper.cpp",
        178,
        "LocalSubAuthority",
        nSubAuthority1);
      v11 = &base;
      if ( v10 )
        v11 = v10;
      nSubAuthority4a[0] = 179;
      WPPTraceLogA(
        4,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        4,
        0,
        "securitygroupshelper.cpp",
        *(_QWORD *)nSubAuthority4a,
        "SID",
        v11);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
    goto LABEL_24;
  }
  nSubAuthority4[0] = 172;
  nSubAuthority2[0] = v9;
  WPPTraceLogA(
    2,
    0,
    "%x 0x%08x %s:%u : %s:%ws",
    2,
    *(_QWORD *)nSubAuthority2,
    "securitygroupshelper.cpp",
    *(_QWORD *)nSubAuthority4,
    "HRESULT",
    &base);
  v17 = v9 & 0xAFFFFFFF | 0x40000000;
  ATL::CStringData::Release((ATL::CStringData *)(v26 - 12));
LABEL_27:
  if ( bufptr )
    NetApiBufferFree(bufptr);
  if ( Sid )
    FreeSid(Sid);
  v12 = v17;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v30);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::RemoveAll(v29);
  return v12;
}

```

## disassembly

```asm
0x180051e78  mov     [rsp-8+arg_10], rbx
0x180051e7d  push    rbp
0x180051e7e  push    rsi
0x180051e7f  push    rdi
0x180051e80  push    r12
0x180051e82  push    r13
0x180051e84  push    r14
0x180051e86  push    r15
0x180051e88  lea     rbp, [rsp-460h]
0x180051e90  sub     rsp, 560h
0x180051e97  mov     rax, cs:__security_cookie
0x180051e9e  xor     rax, rsp
0x180051ea1  mov     [rbp+490h+var_40], rax
0x180051ea8  mov     r15, rdx
0x180051eab  mov     r14d, ecx
0x180051eae  xor     r12d, r12d
0x180051eb1  mov     [rsp+590h+var_530], r12d
0x180051eb6  mov     dword ptr [rbp+490h+pIdentifierAuthority.Value], r12d
0x180051eba  mov     word ptr [rbp+490h+pIdentifierAuthority.Value+4], 500h
0x180051ec0  mov     [rsp+590h+bufptr], r12
0x180051ec5  mov     [rbp+490h+Sid], r12
0x180051ec9  mov     edi, 208h
0x180051ece  mov     r8d, edi; Size
0x180051ed1  xor     edx, edx; Val
0x180051ed3  lea     rcx, [rbp+490h+Name]; void *
0x180051ed7  call    memset_0
0x180051edc  mov     ebx, 104h
0x180051ee1  mov     [rsp+590h+cchName], ebx
0x180051ee5  mov     r8d, edi; Size
0x180051ee8  xor     edx, edx; Val
0x180051eea  lea     rcx, [rbp+490h+ReferencedDomainName]; void *
0x180051ef1  call    memset_0
0x180051ef6  mov     [rsp+590h+cchReferencedDomainName], ebx
0x180051efa  mov     [rsp+590h+entriesread], r12d
0x180051eff  mov     [rsp+590h+totalentries], r12d
0x180051f04  mov     [rsp+590h+peUse], r12d
0x180051f09  movss   xmm0, cs:__real@40100000
0x180051f11  movss   [rsp+590h+nSubAuthority2], xmm0
0x180051f17  movss   xmm3, cs:__real@3e800000
0x180051f1f  movss   xmm2, cs:__real@3f400000
0x180051f27  lea     rcx, [rbp+490h+var_4F0]
0x180051f2b  call    ??0?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CAtlArray@UAADJoinInfo@@V?$CElementTraits@UAADJoinInfo@@@ATL@@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CAtlArray@UAADJoinInfo@@V?$CElementTraits@UAADJoinInfo@@@ATL@@@ATL@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>>>::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>>>(uint,float,float,float,uint)
0x180051f30  nop
0x180051f31  lea     r9, [rsp+590h+var_530]
0x180051f36  lea     r8, aSecuritygroups_2; "SecurityGroupsHelper::LoadSecurityGroup"...
0x180051f3d  lea     rbx, aOnecoreuapDsEx_37+21h; "securitygroupshelper.cpp"
0x180051f44  mov     rdx, rbx
0x180051f47  lea     rcx, [rbp+490h+var_4A0]
0x180051f4b  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180051f50  nop
0x180051f51  lea     rax, [rbp+490h+Sid]
0x180051f55  mov     [rsp+590h+pSid], rax; pSid
0x180051f5a  mov     [rsp+590h+nSubAuthority7], r12d; nSubAuthority7
0x180051f5f  mov     [rsp+590h+nSubAuthority6], r12d; nSubAuthority6
0x180051f64  mov     [rsp+590h+nSubAuthority5], r12d; nSubAuthority5
0x180051f69  mov     [rsp+590h+nSubAuthority4], r12d; nSubAuthority4
0x180051f6e  mov     [rsp+590h+nSubAuthority3], r12d; nSubAuthority3
0x180051f73  mov     [rsp+590h+nSubAuthority2], r12d; nSubAuthority2
0x180051f78  mov     r9d, r14d; nSubAuthority1
0x180051f7b  lea     r8d, [r12+20h]; nSubAuthority0
0x180051f80  lea     r13d, [r12+2]
0x180051f85  mov     dl, r13b; nSubAuthorityCount
0x180051f88  lea     rcx, [rbp+490h+pIdentifierAuthority]; pIdentifierAuthority
0x180051f8c  call    cs:__imp_AllocateAndInitializeSid
0x180051f92  mov     edi, 0C0070000h
0x180051f97  test    eax, eax
0x180051f99  jnz     short loc_180052002
0x180051f9b  call    cs:__imp_GetLastError
0x180051fa1  test    eax, eax
0x180051fa3  jg      short loc_180051FAD
0x180051fa5  call    cs:__imp_GetLastError
0x180051fab  jmp     short loc_180051FB8
0x180051fad  call    cs:__imp_GetLastError
0x180051fb3  movzx   eax, ax
0x180051fb6  or      eax, edi
0x180051fb8  mov     [rsp+590h+var_530], eax
0x180051fbc  test    eax, eax
0x180051fbe  jns     short loc_180052002
0x180051fc0  lea     rdi, base
0x180051fc7  mov     qword ptr [rsp+590h+nSubAuthority6], rdi
0x180051fcc  lea     rdx, aNtstatus; "NTSTATUS"
0x180051fd3  mov     qword ptr [rsp+590h+nSubAuthority5], rdx
0x180051fd8  mov     [rsp+590h+nSubAuthority4], 9Ch
0x180051fe0  mov     qword ptr [rsp+590h+nSubAuthority3], rbx
0x180051fe5  mov     [rsp+590h+nSubAuthority2], eax
0x180051fe9  mov     r9d, r13d
0x180051fec  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180051ff3  xor     edx, edx
0x180051ff5  mov     ecx, r13d
0x180051ff8  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180051ffd  jmp     loc_180052289
0x180052002  lea     rax, [rsp+590h+peUse]
0x180052007  mov     qword ptr [rsp+590h+nSubAuthority4], rax; peUse
0x18005200c  lea     rax, [rsp+590h+cchReferencedDomainName]
0x180052011  mov     qword ptr [rsp+590h+nSubAuthority3], rax; cchReferencedDomainName
0x180052016  lea     rax, [rbp+490h+ReferencedDomainName]
0x18005201d  mov     qword ptr [rsp+590h+nSubAuthority2], rax; ReferencedDomainName
0x180052022  lea     r9, [rsp+590h+cchName]; cchName
0x180052027  lea     r8, [rbp+490h+Name]; Name
0x18005202b  mov     rdx, [rbp+490h+Sid]; Sid
0x18005202f  xor     ecx, ecx; lpSystemName
0x180052031  call    cs:__imp_LookupAccountSidW
0x180052037  test    eax, eax
0x180052039  jnz     short loc_180052085
0x18005203b  call    cs:__imp_GetLastError
0x180052041  test    eax, eax
0x180052043  jg      short loc_18005204D
0x180052045  call    cs:__imp_GetLastError
0x18005204b  jmp     short loc_180052058
0x18005204d  call    cs:__imp_GetLastError
0x180052053  movzx   eax, ax
0x180052056  or      eax, edi
0x180052058  mov     [rsp+590h+var_530], eax
0x18005205c  test    eax, eax
0x18005205e  jns     short loc_180052085
0x180052060  lea     rdi, base
0x180052067  mov     qword ptr [rsp+590h+nSubAuthority6], rdi
0x18005206c  lea     rdx, aNtstatus; "NTSTATUS"
0x180052073  mov     qword ptr [rsp+590h+nSubAuthority5], rdx
0x180052078  mov     [rsp+590h+nSubAuthority4], 0A1h
0x180052080  jmp     loc_180051FE0
0x180052085  mov     qword ptr [rsp+590h+nSubAuthority5], r12; resumehandle
0x18005208a  lea     rax, [rsp+590h+totalentries]
0x18005208f  mov     qword ptr [rsp+590h+nSubAuthority4], rax; totalentries
0x180052094  lea     rax, [rsp+590h+entriesread]
0x180052099  mov     qword ptr [rsp+590h+nSubAuthority3], rax; entriesread
0x18005209e  mov     [rsp+590h+nSubAuthority2], 0FFFFFFFFh; prefmaxlen
0x1800520a6  lea     r9, [rsp+590h+bufptr]; bufptr
0x1800520ab  xor     r8d, r8d; level
0x1800520ae  lea     rdx, [rbp+490h+Name]; localgroupname
0x1800520b2  xor     ecx, ecx; servername
0x1800520b4  call    cs:__imp_NetLocalGroupGetMembers
0x1800520ba  mov     [rsp+590h+var_530], eax
0x1800520be  test    eax, eax
0x1800520c0  jns     short loc_1800520E7
0x1800520c2  lea     rdi, base
0x1800520c9  mov     qword ptr [rsp+590h+nSubAuthority6], rdi
0x1800520ce  lea     rdx, aNtstatus; "NTSTATUS"
0x1800520d5  mov     qword ptr [rsp+590h+nSubAuthority5], rdx
0x1800520da  mov     [rsp+590h+nSubAuthority4], 0A4h
0x1800520e2  jmp     loc_180051FE0
0x1800520e7  mov     esi, r12d
0x1800520ea  cmp     [rsp+590h+entriesread], r12d
0x1800520ef  jbe     loc_180052289
0x1800520f5  lea     rdi, base
0x1800520fc  mov     ebx, esi
0x1800520fe  mov     rcx, [rsp+590h+bufptr]
0x180052103  mov     rcx, [rcx+rbx*8]; pSid
0x180052107  call    ?CheckSidIsAad@SecurityGroupsHelper@@SAJPEAX@Z; SecurityGroupsHelper::CheckSidIsAad(void *)
0x18005210c  test    eax, eax
0x18005210e  js      loc_180052225
0x180052114  lea     rcx, [rbp+490h+var_508]; void *
0x180052118  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005211d  nop
0x18005211e  lea     rdx, [rbp+490h+var_508]
0x180052122  mov     rcx, [rsp+590h+bufptr]
0x180052127  mov     rcx, [rcx+rbx*8]; Sid
0x18005212b  call    ?SidToString@StringUtility@@SAJPEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; StringUtility::SidToString(void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180052130  mov     ebx, eax
0x180052132  test    eax, eax
0x180052134  js      loc_180052233
0x18005213a  mov     [rbp+490h+var_50C], r12d
0x18005213e  mov     [rbp+490h+var_510], r12d
0x180052142  mov     [rbp+490h+var_4F8], r12
0x180052146  lea     rax, [rbp+490h+var_4F8]
0x18005214a  mov     qword ptr [rsp+590h+nSubAuthority2], rax
0x18005214f  lea     r9, [rbp+490h+var_510]
0x180052153  lea     r8, [rbp+490h+var_50C]
0x180052157  mov     rbx, [rbp+490h+var_508]
0x18005215b  mov     rdx, rbx
0x18005215e  lea     rcx, [rbp+490h+var_4F0]
0x180052162  call    ?GetNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CNode * &)
0x180052167  test    rax, rax
0x18005216a  jnz     loc_18005221C
0x180052170  mov     rdx, rbx
0x180052173  mov     rcx, r15
0x180052176  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x18005217b  mov     rdx, rbx
0x18005217e  lea     rcx, [rbp+490h+var_4F0]
0x180052182  call    ??A?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HV?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@H@2@@ATL@@QEAAAEAHPEBG@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<int>>::operator[](ushort const *)
0x180052187  mov     dword ptr [rax], 1
0x18005218d  mov     [rsp+590h+nSubAuthority6], r14d
0x180052192  lea     rax, aLocalsubauthor; "LocalSubAuthority"
0x180052199  mov     qword ptr [rsp+590h+nSubAuthority5], rax
0x18005219e  mov     [rsp+590h+nSubAuthority4], 0B2h
0x1800521a6  lea     rax, aOnecoreuapDsEx_37+21h; "securitygroupshelper.cpp"
0x1800521ad  mov     qword ptr [rsp+590h+nSubAuthority3], rax
0x1800521b2  mov     qword ptr [rsp+590h+nSubAuthority2], r12
0x1800521b7  mov     eax, 4
0x1800521bc  mov     r9d, eax
0x1800521bf  lea     r8, aX0x08xSUSU; "%x 0x%08x %s:%u : %s:%u"
0x1800521c6  xor     edx, edx
0x1800521c8  mov     ecx, eax
0x1800521ca  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800521cf  mov     rax, rdi
0x1800521d2  test    rbx, rbx
0x1800521d5  cmovnz  rax, rbx
0x1800521d9  mov     qword ptr [rsp+590h+nSubAuthority6], rax
0x1800521de  lea     rax, aSid_0; "SID"
0x1800521e5  mov     qword ptr [rsp+590h+nSubAuthority5], rax
0x1800521ea  mov     [rsp+590h+nSubAuthority4], 0B3h
0x1800521f2  lea     rax, aOnecoreuapDsEx_37+21h; "securitygroupshelper.cpp"
0x1800521f9  mov     qword ptr [rsp+590h+nSubAuthority3], rax
0x1800521fe  mov     qword ptr [rsp+590h+nSubAuthority2], r12
0x180052203  mov     eax, 4
0x180052208  mov     r9d, eax
0x18005220b  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180052212  xor     edx, edx
0x180052214  mov     ecx, eax
0x180052216  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18005221b  nop
0x18005221c  lea     rcx, [rbx-18h]; this
0x180052220  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180052225  inc     esi
0x180052227  cmp     esi, [rsp+590h+entriesread]
0x18005222b  jb      loc_1800520FC
0x180052231  jmp     short loc_180052289
0x180052233  mov     qword ptr [rsp+590h+nSubAuthority6], rdi
0x180052238  lea     rax, aHresult; "HRESULT"
0x18005223f  mov     qword ptr [rsp+590h+nSubAuthority5], rax
0x180052244  mov     [rsp+590h+nSubAuthority4], 0ACh
0x18005224c  lea     rax, aOnecoreuapDsEx_37+21h; "securitygroupshelper.cpp"
0x180052253  mov     qword ptr [rsp+590h+nSubAuthority3], rax
0x180052258  mov     [rsp+590h+nSubAuthority2], ebx
0x18005225c  mov     r9d, r13d
0x18005225f  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180052266  xor     edx, edx
0x180052268  mov     ecx, r13d
0x18005226b  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180052270  btr     ebx, 1Ch
0x180052274  bts     ebx, 1Eh
0x180052278  mov     [rsp+590h+var_530], ebx
0x18005227c  mov     rcx, [rbp+490h+var_508]
0x180052280  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180052284  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180052289  mov     rcx, [rsp+590h+bufptr]; Buffer
0x18005228e  test    rcx, rcx
0x180052291  jz      short loc_180052299
0x180052293  call    cs:__imp_NetApiBufferFree
0x180052299  mov     rcx, [rbp+490h+Sid]; pSid
0x18005229d  test    rcx, rcx
0x1800522a0  jz      short loc_1800522A8
0x1800522a2  call    cs:__imp_FreeSid
0x1800522a8  mov     ebx, [rsp+590h+var_530]
0x1800522ac  lea     rcx, [rbp+490h+var_4A0]
0x1800522b0  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x1800522b5  nop
0x1800522b6  lea     rcx, [rbp+490h+var_4F0]
0x1800522ba  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_NV?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@_N@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<bool>>::RemoveAll(void)
0x1800522bf  mov     eax, ebx
0x1800522c1  mov     rcx, [rbp+490h+var_40]
0x1800522c8  xor     rcx, rsp; StackCookie
0x1800522cb  call    __security_check_cookie
0x1800522d0  mov     rbx, [rsp+590h+arg_10]
0x1800522d8  add     rsp, 560h
0x1800522df  pop     r15
0x1800522e1  pop     r14
0x1800522e3  pop     r13
0x1800522e5  pop     r12
0x1800522e7  pop     rdi
0x1800522e8  pop     rsi
0x1800522e9  pop     rbp
0x1800522ea  retn
```
