# Windows::Compat::Inventory::MareDataWriter::SetFileSecurityW(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180022364`
- end: `0x1800227b7`
- name: `?SetFileSecurityW@MareDataWriter@Inventory@Compat@Windows@@AEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `1107`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017778`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x1800134b8`
- `0x180022364`
- `0x18004c020`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x18002245c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18002245c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800224ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800225cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800224ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800225cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002249b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002249b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022718`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022740`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800224a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800225c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022751`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022762`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022773`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800224a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800225c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022751`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022762`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022773`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002262b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002262b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002265c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002265c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800225e8`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800225e8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800226c1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800226c1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002270e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002270e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800224cd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800224cd`

## string_xrefs

- `0x18002246c`: `RtlAllocateAndInitializeSid failed [%#x]`
- `0x180022479`: `Windows::Compat::Inventory::MareDataWriter::SetFileSecurityW`
- `0x1800224ee`: `Windows::Compat::Inventory::MareDataWriter::SetFileSecurityW`
- `0x180022605`: `Windows::Compat::Inventory::MareDataWriter::SetFileSecurityW`
- `0x1800224dd`: `ConvertStringSidToSidW failed %d`
- `0x1800226df`: `CreateFileW failed [%d]`
- `0x18002271e`: `CreateFileW failed [%d]`
- `0x1800225f8`: `SetEntriesInAcl [%d]`
- `0x18002263b`: `InitializeSecurityDescriptor failed [%d]`
- `0x18002266c`: `SetSecurityDescriptorDacl failed [%d]`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::MareDataWriter::SetFileSecurityW(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rbx
  NTSTATUS v6; // eax
  NTSTATUS v7; // edi
  int v8; // edi
  const WCHAR *v9; // rcx
  DWORD LastError; // eax
  const char *v11; // r9
  __int64 v12; // r8
  signed int v13; // eax
  DWORD v14; // eax
  const WCHAR *v15; // rcx
  ULONG SubAuthority2[2]; // [rsp+20h] [rbp-E0h]
  __int16 Buffer; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v19; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-90h] BYREF
  PSID Sid; // [rsp+78h] [rbp-88h] BYREF
  __int64 v22; // [rsp+80h] [rbp-80h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+88h] [rbp-78h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v25; // [rsp+C0h] [rbp-40h]
  __int64 v26; // [rsp+C8h] [rbp-38h]
  __int64 v27; // [rsp+D0h] [rbp-30h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD v29[4]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v30[4]; // [rsp+F0h] [rbp-10h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+100h] [rbp+0h] BYREF
  int v32; // [rsp+130h] [rbp+30h]
  int v33; // [rsp+134h] [rbp+34h]
  int v34; // [rsp+138h] [rbp+38h]
  int v35; // [rsp+14Ch] [rbp+4Ch]
  int v36; // [rsp+150h] [rbp+50h]
  _DWORD *v37; // [rsp+158h] [rbp+58h]
  int v38; // [rsp+160h] [rbp+60h]
  int v39; // [rsp+164h] [rbp+64h]
  int v40; // [rsp+168h] [rbp+68h]
  int v41; // [rsp+17Ch] [rbp+7Ch]
  int v42; // [rsp+180h] [rbp+80h]
  PSID v43; // [rsp+188h] [rbp+88h]
  unsigned int v44; // [rsp+190h] [rbp+90h]
  int v45; // [rsp+194h] [rbp+94h]
  int v46; // [rsp+198h] [rbp+98h]
  int v47; // [rsp+1ACh] [rbp+ACh]
  int v48; // [rsp+1B0h] [rbp+B0h]
  HLOCAL v49; // [rsp+1B8h] [rbp+B8h]

  v26 = a2;
  v27 = a3;
  pListOfExplicitEntries.grfAccessPermissions = 0;
  memset_0(&pListOfExplicitEntries.grfAccessMode, 0, 0xBCu);
  v29[0] = 257;
  v29[1] = 83886080;
  v29[2] = 18;
  v30[0] = 257;
  v30[1] = 83886080;
  v30[2] = 19;
  hMem = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v19 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v25 = 0;
  v5 = -1;
  v22 = -1;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  Sid = 0;
  v6 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Sid);
  v7 = v6;
  if ( v6 < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareDataWriter::SetFileSecurityW",
      573,
      "RtlAllocateAndInitializeSid failed [%#x]",
      v6);
    v8 = v7 | 0x10000000;
    goto LABEL_26;
  }
  hMem = 0;
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v9 = (const WCHAR *)a3;
  else
    v9 = *(const WCHAR **)a3;
  if ( !ConvertStringSidToSidW(v9, &hMem) )
  {
    LastError = GetLastError();
    v11 = "ConvertStringSidToSidW failed %d";
    v12 = 580;
LABEL_8:
    SubAuthority2[0] = LastError;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareDataWriter::SetFileSecurityW",
      v12,
      v11,
      *(_QWORD *)SubAuthority2);
    v13 = GetLastError();
    v8 = v13;
    if ( v13 <= 0 )
      goto LABEL_26;
    v8 = (unsigned __int16)v13;
    goto LABEL_10;
  }
  pListOfExplicitEntries.grfAccessPermissions = 269418496;
  pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
  pListOfExplicitEntries.grfInheritance = 3;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)v29;
  v32 = 269418496;
  v33 = 2;
  v34 = 3;
  v35 = 0;
  v36 = 2;
  v37 = v30;
  v38 = 269418496;
  v39 = 2;
  v40 = 3;
  v41 = 0;
  v42 = 2;
  v43 = Sid;
  v44 = 0x80000000;
  v45 = 2;
  v46 = 3;
  v47 = 0;
  v48 = 1;
  v49 = hMem;
  v19 = 0;
  v14 = SetEntriesInAclW(4u, &pListOfExplicitEntries, 0, (PACL *)&v19);
  v8 = v14;
  if ( v14 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareDataWriter::SetFileSecurityW",
      618,
      "SetEntriesInAcl [%d]",
      v14);
    if ( v8 > 0 )
    {
      v8 = (unsigned __int16)v8;
LABEL_10:
      v8 |= 0x80070000;
    }
  }
  else
  {
    if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      LastError = GetLastError();
      v11 = "InitializeSecurityDescriptor failed [%d]";
      v12 = 625;
      goto LABEL_8;
    }
    if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, (PACL)v19, 0) )
    {
      LastError = GetLastError();
      v11 = "SetSecurityDescriptorDacl failed [%d]";
      v12 = 632;
      goto LABEL_8;
    }
    SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = pSecurityDescriptor;
    SecurityAttributes.bInheritHandle = 0;
    if ( *(_QWORD *)(a2 + 24) <= 7u )
      v15 = (const WCHAR *)a2;
    else
      v15 = *(const WCHAR **)a2;
    v5 = (__int64)CreateFileW(v15, 0x40000000u, 0, &SecurityAttributes, 2u, 0x80u, 0);
    v22 = v5;
    if ( ((v5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      v11 = "CreateFileW failed [%d]";
      v12 = 644;
      goto LABEL_8;
    }
    Buffer = 123;
    if ( !WriteFile((HANDLE)v5, &Buffer, 1u, 0, 0) )
    {
      LastError = GetLastError();
      v11 = "CreateFileW failed [%d]";
      v12 = 653;
      goto LABEL_8;
    }
    v8 = 0;
  }
LABEL_26:
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v5);
  if ( v19 )
    LocalFree(v19);
  if ( hMem )
    LocalFree(hMem);
  if ( Sid )
    LocalFree(Sid);
  std::wstring::~wstring(a2);
  std::wstring::~wstring(a3);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180022364  mov     [rsp-8+arg_0], rbx
0x180022369  push    rbp
0x18002236a  push    rsi
0x18002236b  push    rdi
0x18002236c  push    r12
0x18002236e  push    r13
0x180022370  push    r14
0x180022372  push    r15
0x180022374  lea     rbp, [rsp-0D0h]
0x18002237c  sub     rsp, 1D0h
0x180022383  mov     rax, cs:__security_cookie
0x18002238a  xor     rax, rsp
0x18002238d  mov     [rbp+100h+var_40], rax
0x180022394  mov     r15, r8
0x180022397  mov     r14, rdx
0x18002239a  mov     [rbp+100h+var_138], rdx
0x18002239e  mov     [rbp+100h+var_130], r8
0x1800223a2  xor     r12d, r12d
0x1800223a5  mov     [rbp+100h+pListOfExplicitEntries.grfAccessPermissions], r12d
0x1800223a9  xor     edx, edx; Val
0x1800223ab  mov     r8d, 0BCh; Size
0x1800223b1  lea     rcx, [rbp+100h+pListOfExplicitEntries.grfAccessMode]; void *
0x1800223b5  call    memset_0
0x1800223ba  lea     r13d, [r12+1]
0x1800223bf  mov     [rbp+100h+var_120], 101h
0x1800223c6  mov     [rbp+100h+var_11C], 5000000h
0x1800223cd  mov     [rbp+100h+var_118], 12h
0x1800223d4  mov     [rbp+100h+var_110], 101h
0x1800223db  mov     [rbp+100h+var_10C], 5000000h
0x1800223e2  mov     [rbp+100h+var_108], 13h
0x1800223e9  mov     [rsp+200h+hMem], r12
0x1800223ee  mov     dword ptr [rbp+100h+IdentifierAuthority.Value], r12d
0x1800223f2  mov     word ptr [rbp+100h+IdentifierAuthority.Value+4], 500h
0x1800223f8  mov     [rsp+200h+var_198], r12
0x1800223fd  xorps   xmm0, xmm0
0x180022400  xor     eax, eax
0x180022402  movups  [rbp+100h+pSecurityDescriptor], xmm0
0x180022406  movups  [rbp+100h+var_150], xmm0
0x18002240a  mov     [rbp+100h+var_140], rax
0x18002240e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180022412  mov     [rbp+100h+var_180], rbx
0x180022416  movups  xmmword ptr [rbp+100h+SecurityAttributes.nLength], xmm0
0x18002241a  mov     qword ptr [rbp+100h+SecurityAttributes.bInheritHandle], rax
0x18002241e  mov     [rsp+200h+var_188], r12
0x180022423  lea     rax, [rsp+200h+var_188]
0x180022428  mov     [rsp+200h+Sid], rax; Sid
0x18002242d  mov     [rsp+200h+SubAuthority7], r12d; SubAuthority7
0x180022432  mov     [rsp+200h+SubAuthority6], r12d; SubAuthority6
0x180022437  mov     [rsp+200h+SubAuthority5], r12d; SubAuthority5
0x18002243c  mov     [rsp+200h+SubAuthority4], r12d; SubAuthority4
0x180022441  mov     [rsp+200h+SubAuthority3], r12d; SubAuthority3
0x180022446  mov     [rsp+200h+SubAuthority2], r12d; SubAuthority2
0x18002244b  mov     r9d, 220h; SubAuthority1
0x180022451  lea     r8d, [r12+20h]; SubAuthority0
0x180022456  mov     dl, 2; SubAuthorityCount
0x180022458  lea     rcx, [rbp+100h+IdentifierAuthority]; IdentifierAuthority
0x18002245c  call    cs:__imp_RtlAllocateAndInitializeSid
0x180022462  mov     edi, eax
0x180022464  test    eax, eax
0x180022466  jns     short loc_180022491
0x180022468  mov     [rsp+200h+SubAuthority2], eax
0x18002246c  lea     r9, aRtlallocateand; "RtlAllocateAndInitializeSid failed [%#x"...
0x180022473  mov     r8d, 23Dh
0x180022479  lea     rdx, aWindowsCompatI; "Windows::Compat::Inventory::MareDataWri"...
0x180022480  mov     ecx, r13d
0x180022483  call    AslLogCallPrintf
0x180022488  bts     edi, 1Ch
0x18002248c  jmp     loc_180022733
0x180022491  mov     rsi, [rsp+200h+hMem]
0x180022496  test    rsi, rsi
0x180022499  jz      short loc_1800224B4
0x18002249b  call    cs:__imp_GetLastError
0x1800224a1  mov     edi, eax
0x1800224a3  mov     rcx, rsi; hMem
0x1800224a6  call    cs:__imp_LocalFree
0x1800224ac  mov     ecx, edi; dwErrCode
0x1800224ae  call    cs:__imp_SetLastError
0x1800224b4  mov     [rsp+200h+hMem], r12
0x1800224b9  cmp     qword ptr [r15+18h], 7
0x1800224be  jbe     short loc_1800224C5
0x1800224c0  mov     rcx, [r15]
0x1800224c3  jmp     short loc_1800224C8
0x1800224c5  mov     rcx, r15; StringSid
0x1800224c8  lea     rdx, [rsp+200h+hMem]; Sid
0x1800224cd  call    cs:__imp_ConvertStringSidToSidW
0x1800224d3  test    eax, eax
0x1800224d5  jnz     short loc_18002251B
0x1800224d7  call    cs:__imp_GetLastError
0x1800224dd  lea     r9, aConvertstrings; "ConvertStringSidToSidW failed %d"
0x1800224e4  mov     r8d, 244h
0x1800224ea  mov     [rsp+200h+SubAuthority2], eax
0x1800224ee  lea     rdx, aWindowsCompatI; "Windows::Compat::Inventory::MareDataWri"...
0x1800224f5  mov     ecx, r13d
0x1800224f8  call    AslLogCallPrintf
0x1800224fd  call    cs:__imp_GetLastError
0x180022503  mov     edi, eax
0x180022505  test    eax, eax
0x180022507  jle     loc_180022733
0x18002250d  movzx   edi, ax
0x180022510  or      edi, 80070000h
0x180022516  jmp     loc_180022733
0x18002251b  mov     ecx, 100F0000h
0x180022520  mov     [rbp+100h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x180022523  mov     r8d, 2
0x180022529  mov     [rbp+100h+pListOfExplicitEntries.grfAccessMode], r8d
0x18002252d  lea     edx, [r8+1]
0x180022531  mov     [rbp+100h+pListOfExplicitEntries.grfInheritance], edx
0x180022534  mov     [rbp+100h+pListOfExplicitEntries.Trustee.TrusteeForm], r12d
0x180022538  mov     [rbp+100h+pListOfExplicitEntries.Trustee.TrusteeType], r8d
0x18002253c  lea     rax, [rbp+100h+var_120]
0x180022540  mov     [rbp+100h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180022544  mov     [rbp+100h+var_D0], ecx
0x180022547  mov     [rbp+100h+var_CC], r8d
0x18002254b  mov     [rbp+100h+var_C8], edx
0x18002254e  mov     [rbp+100h+var_B4], r12d
0x180022552  mov     [rbp+100h+var_B0], r8d
0x180022556  lea     rax, [rbp+100h+var_110]
0x18002255a  mov     [rbp+100h+var_A8], rax
0x18002255e  mov     [rbp+100h+var_A0], ecx
0x180022561  mov     [rbp+100h+var_9C], r8d
0x180022565  mov     [rbp+100h+var_98], edx
0x180022568  mov     [rbp+100h+var_84], r12d
0x18002256c  mov     [rbp+100h+var_80], r8d
0x180022573  mov     rax, [rsp+200h+var_188]
0x180022578  mov     [rbp+100h+var_78], rax
0x18002257f  mov     [rbp+100h+var_70], 80000000h
0x180022589  mov     [rbp+100h+var_6C], r8d
0x180022590  mov     [rbp+100h+var_68], edx
0x180022596  mov     [rbp+100h+var_54], r12d
0x18002259d  mov     [rbp+100h+var_50], r13d
0x1800225a4  mov     rax, [rsp+200h+hMem]
0x1800225a9  mov     [rbp+100h+var_48], rax
0x1800225b0  mov     rsi, [rsp+200h+var_198]
0x1800225b5  test    rsi, rsi
0x1800225b8  jz      short loc_1800225D3
0x1800225ba  call    cs:__imp_GetLastError
0x1800225c0  mov     edi, eax
0x1800225c2  mov     rcx, rsi; hMem
0x1800225c5  call    cs:__imp_LocalFree
0x1800225cb  mov     ecx, edi; dwErrCode
0x1800225cd  call    cs:__imp_SetLastError
0x1800225d3  mov     [rsp+200h+var_198], r12
0x1800225d8  lea     r9, [rsp+200h+var_198]; NewAcl
0x1800225dd  xor     r8d, r8d; OldAcl
0x1800225e0  lea     rdx, [rbp+100h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800225e4  lea     ecx, [r8+4]; cCountOfExplicitEntries
0x1800225e8  call    cs:__imp_SetEntriesInAclW
0x1800225ee  mov     edi, eax
0x1800225f0  test    eax, eax
0x1800225f2  jz      short loc_180022624
0x1800225f4  mov     [rsp+200h+SubAuthority2], eax
0x1800225f8  lea     r9, aSetentriesinac; "SetEntriesInAcl [%d]"
0x1800225ff  mov     r8d, 26Ah
0x180022605  lea     rdx, aWindowsCompatI; "Windows::Compat::Inventory::MareDataWri"...
0x18002260c  mov     ecx, r13d
0x18002260f  call    AslLogCallPrintf
0x180022614  test    edi, edi
0x180022616  jle     loc_180022733
0x18002261c  movzx   edi, di
0x18002261f  jmp     loc_180022510
0x180022624  mov     edx, r13d; dwRevision
0x180022627  lea     rcx, [rbp+100h+pSecurityDescriptor]; pSecurityDescriptor
0x18002262b  call    cs:__imp_InitializeSecurityDescriptor
0x180022631  test    eax, eax
0x180022633  jnz     short loc_18002264D
0x180022635  call    cs:__imp_GetLastError
0x18002263b  lea     r9, aInitializesecu; "InitializeSecurityDescriptor failed [%d"...
0x180022642  mov     r8d, 271h
0x180022648  jmp     loc_1800224EA
0x18002264d  xor     r9d, r9d; bDaclDefaulted
0x180022650  mov     r8, [rsp+200h+var_198]; pDacl
0x180022655  mov     edx, r13d; bDaclPresent
0x180022658  lea     rcx, [rbp+100h+pSecurityDescriptor]; pSecurityDescriptor
0x18002265c  call    cs:__imp_SetSecurityDescriptorDacl
0x180022662  test    eax, eax
0x180022664  jnz     short loc_18002267E
0x180022666  call    cs:__imp_GetLastError
0x18002266c  lea     r9, aSetsecuritydes; "SetSecurityDescriptorDacl failed [%d]"
0x180022673  mov     r8d, 278h
0x180022679  jmp     loc_1800224EA
0x18002267e  mov     [rbp+100h+SecurityAttributes.nLength], 18h
0x180022685  lea     rax, [rbp+100h+pSecurityDescriptor]
0x180022689  mov     [rbp+100h+SecurityAttributes.lpSecurityDescriptor], rax
0x18002268d  mov     [rbp+100h+SecurityAttributes.bInheritHandle], r12d
0x180022691  cmp     qword ptr [r14+18h], 7
0x180022696  jbe     short loc_18002269D
0x180022698  mov     rcx, [r14]
0x18002269b  jmp     short loc_1800226A0
0x18002269d  mov     rcx, r14; lpFileName
0x1800226a0  mov     qword ptr [rsp+200h+SubAuthority4], r12; hTemplateFile
0x1800226a5  mov     [rsp+200h+SubAuthority3], 80h; dwFlagsAndAttributes
0x1800226ad  mov     [rsp+200h+SubAuthority2], 2; dwCreationDisposition
0x1800226b5  lea     r9, [rbp+100h+SecurityAttributes]; lpSecurityAttributes
0x1800226b9  xor     r8d, r8d; dwShareMode
0x1800226bc  mov     edx, 40000000h; dwDesiredAccess
0x1800226c1  call    cs:__imp_CreateFileW
0x1800226c7  mov     rbx, rax
0x1800226ca  mov     [rbp+100h+var_180], rax
0x1800226ce  inc     rax
0x1800226d1  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800226d7  jnz     short loc_1800226F1
0x1800226d9  call    cs:__imp_GetLastError
0x1800226df  lea     r9, aCreatefilewFai; "CreateFileW failed [%d]"
0x1800226e6  mov     r8d, 284h
0x1800226ec  jmp     loc_1800224EA
0x1800226f1  mov     eax, 7Bh ; '{'
0x1800226f6  mov     [rsp+200h+Buffer], ax
0x1800226fb  mov     qword ptr [rsp+200h+SubAuthority2], r12; lpOverlapped
0x180022700  xor     r9d, r9d; lpNumberOfBytesWritten
0x180022703  mov     r8d, r13d; nNumberOfBytesToWrite
0x180022706  lea     rdx, [rsp+200h+Buffer]; lpBuffer
0x18002270b  mov     rcx, rbx; hFile
0x18002270e  call    cs:__imp_WriteFile
0x180022714  test    eax, eax
0x180022716  jnz     short loc_180022730
0x180022718  call    cs:__imp_GetLastError
0x18002271e  lea     r9, aCreatefilewFai; "CreateFileW failed [%d]"
0x180022725  mov     r8d, 28Dh
0x18002272b  jmp     loc_1800224EA
0x180022730  mov     edi, r12d
0x180022733  lea     rax, [rbx-1]
0x180022737  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002273b  ja      short loc_180022747
0x18002273d  mov     rcx, rbx; hObject
0x180022740  call    cs:__imp_CloseHandle
0x180022746  nop
0x180022747  mov     rcx, [rsp+200h+var_198]; hMem
0x18002274c  test    rcx, rcx
0x18002274f  jz      short loc_180022758
0x180022751  call    cs:__imp_LocalFree
0x180022757  nop
0x180022758  mov     rcx, [rsp+200h+hMem]; hMem
0x18002275d  test    rcx, rcx
0x180022760  jz      short loc_180022769
0x180022762  call    cs:__imp_LocalFree
0x180022768  nop
0x180022769  mov     rcx, [rsp+200h+var_188]; hMem
0x18002276e  test    rcx, rcx
0x180022771  jz      short loc_18002277A
0x180022773  call    cs:__imp_LocalFree
0x180022779  nop
0x18002277a  mov     rcx, r14
0x18002277d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022782  nop
0x180022783  mov     rcx, r15
0x180022786  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002278b  mov     eax, edi
0x18002278d  mov     rcx, [rbp+100h+var_40]
0x180022794  xor     rcx, rsp; StackCookie
0x180022797  call    __security_check_cookie
0x18002279c  mov     rbx, [rsp+200h+arg_0]
0x1800227a4  add     rsp, 1D0h
0x1800227ab  pop     r15
0x1800227ad  pop     r14
0x1800227af  pop     r13
0x1800227b1  pop     r12
0x1800227b3  pop     rdi
0x1800227b4  pop     rsi
0x1800227b5  pop     rbp
0x1800227b6  retn
```
