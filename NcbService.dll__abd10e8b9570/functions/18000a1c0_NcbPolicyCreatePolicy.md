# NcbPolicyCreatePolicy

- ea: `0x18000a1c0`
- end: `0x18000a735`
- name: `NcbPolicyCreatePolicy`
- size: `1397`
- prototype: `__int64 __fastcall(PSID Sid, PSID SourceSid)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009990`
- `0x180009dd0`

## callees

- `0x18000a0a0`
- `0x18000a1c0`
- `0x18000ed20`
- `0x18001d8e0`
- `0x18001e368`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18000a272`
- `ntdll!RtlCopySid` at `0x18000a2c7`
- `ntdll!RtlCopySid` at `0x18000a272`
- `ntdll!RtlCopySid` at `0x18000a2c7`
- `ntdll!RtlLengthSid` at `0x18000a23b`
- `ntdll!RtlLengthSid` at `0x18000a290`
- `ntdll!RtlLengthSid` at `0x18000a23b`
- `ntdll!RtlLengthSid` at `0x18000a290`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a243`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a298`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a313`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a3c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a4ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a243`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a298`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a313`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a3c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a4ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a209`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a254`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a2a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a324`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a3d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a4e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a209`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a254`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a2a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a324`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a3d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a4e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a604`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a645`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a678`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a6a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a6e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a604`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a645`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a678`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a6a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a6e3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a27f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a27f`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000a457`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000a457`

## string_xrefs

- `0x18000a5ee`: `NcbPolicy: NcbPolicyCreatePolicy failed allocation of policy entry - `
- `0x18000a61b`: `NcbPolicy: NcbPolicyCreatePolicy failed allocation of user SID - `
- `0x18000a634`: `NcbPolicy: NcbPolicyCreatePolicy failed to convert user SID to string - `
- `0x18000a65c`: `NcbPolicy: NcbPolicyCreatePolicy failed allocation of package SID - `
- `0x18000a68f`: `NcbPolicy: NcbPolicyCreatePolicy failed allocation of app name - `
- `0x18000a6b8`: `NcbPolicy: NcbPolicyCreatePolicy failed allocation of package full name - `
- `0x18000a70e`: `NcbPolicy: NcbPolicyCreatePolicy failed allocation of app user model ID - `

## pseudocode

```c
LPVOID __fastcall NcbPolicyCreatePolicy(PSID Sid, PSID SourceSid, _WORD *a3, const WCHAR *a4)
{
  HANDLE ProcessHeap; // rax
  LPVOID v9; // r13
  ULONG v10; // ebp
  HANDLE v11; // rax
  void *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  ULONG v15; // edi
  HANDLE v16; // rax
  void *v17; // rax
  __int64 v18; // rcx
  _WORD *v19; // rax
  __int64 v20; // rbx
  SIZE_T v21; // rbx
  HANDLE v22; // rax
  _WORD *v23; // rax
  _WORD *v24; // rdi
  unsigned __int64 v25; // rbx
  __int64 v26; // rsi
  __int64 v27; // rcx
  _WORD *v28; // rdx
  __int64 v29; // rcx
  const WCHAR *v30; // rax
  __int64 v31; // rbx
  SIZE_T v32; // rbx
  HANDLE v33; // rax
  _WORD *v34; // rax
  _WORD *v35; // rdi
  unsigned __int64 v36; // rbx
  __int64 v37; // rcx
  const WCHAR *v38; // rdx
  unsigned int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rcx
  WCHAR *v43; // rax
  unsigned __int64 v44; // rbp
  __int64 v45; // rcx
  _WORD *v46; // rax
  __int64 v47; // rdi
  HANDLE v48; // rax
  _WORD *v49; // rax
  _WORD *v50; // r10
  unsigned __int64 v51; // r8
  __int64 v52; // rcx
  WCHAR *v53; // rdx
  _WORD *v54; // r9
  unsigned __int64 v55; // rbp
  unsigned __int64 v56; // rcx
  _WORD *v57; // rdx
  _WORD *v58; // rax
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // rdx
  __int64 v69; // rcx
  UINT32 packageFamilyNameLength[4]; // [rsp+20h] [rbp-268h] BYREF
  WCHAR packageFamilyName[264]; // [rsp+30h] [rbp-258h] BYREF

  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 8u, 0x48u);
  if ( !v9 )
  {
    SetLastError(8u);
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v61,
        v60,
        L"NcbPolicy: NcbPolicyCreatePolicy failed allocation of policy entry - ",
        0);
    return 0;
  }
  *(_OWORD *)v9 = 0;
  *((_OWORD *)v9 + 1) = 0;
  *((_OWORD *)v9 + 2) = 0;
  *((_OWORD *)v9 + 3) = 0;
  *((_QWORD *)v9 + 8) = 0;
  v10 = RtlLengthSid(Sid);
  v11 = GetProcessHeap();
  v12 = HeapAlloc(v11, 8u, v10);
  if ( !v12 )
  {
    SetLastError(8u);
    *((_QWORD *)v9 + 3) = 0;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v63,
        v62,
        L"NcbPolicy: NcbPolicyCreatePolicy failed allocation of user SID - ",
        0);
    goto LABEL_92;
  }
  *((_QWORD *)v9 + 3) = v12;
  RtlCopySid(v10, v12, Sid);
  if ( !ConvertSidToStringSidW(Sid, (LPWSTR *)v9 + 4) )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v14,
        v13,
        L"NcbPolicy: NcbPolicyCreatePolicy failed to convert user SID to string - ",
        0);
    goto LABEL_92;
  }
  v15 = RtlLengthSid(SourceSid);
  v16 = GetProcessHeap();
  v17 = HeapAlloc(v16, 8u, v15);
  if ( !v17 )
  {
    SetLastError(8u);
    *((_QWORD *)v9 + 5) = 0;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v65,
        v64,
        L"NcbPolicy: NcbPolicyCreatePolicy failed allocation of package SID - ",
        0);
    goto LABEL_92;
  }
  *((_QWORD *)v9 + 5) = v17;
  RtlCopySid(v15, v17, SourceSid);
  if ( !a3 )
    goto LABEL_79;
  v18 = 0x7FFFFFFF;
  v19 = a3;
  while ( *v19 )
  {
    ++v19;
    if ( !--v18 )
    {
      v20 = 0;
      goto LABEL_11;
    }
  }
  v20 = 2 * (0x7FFFFFFF - v18);
LABEL_11:
  if ( !v18 )
LABEL_79:
    v20 = 0;
  v21 = v20 + 2;
  v22 = GetProcessHeap();
  v23 = HeapAlloc(v22, 8u, v21);
  v24 = v23;
  if ( !v23 )
  {
    SetLastError(8u);
    *((_QWORD *)v9 + 6) = 0;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v67,
        v66,
        L"NcbPolicy: NcbPolicyCreatePolicy failed allocation of app name - ",
        0);
    goto LABEL_92;
  }
  v25 = v21 >> 1;
  v26 = 2147483646;
  *((_QWORD *)v9 + 6) = v23;
  if ( v25 )
  {
    if ( v25 <= 0x7FFFFFFF )
    {
      v27 = 2147483646;
      v28 = a3;
      do
      {
        if ( !v27 )
          break;
        if ( !*v28 )
          break;
        *v24++ = *v28++;
        --v27;
        --v25;
      }
      while ( v25 );
      v23 = v24 - 1;
      if ( v25 )
        v23 = v24;
    }
    *v23 = 0;
  }
  if ( !a4 )
    goto LABEL_82;
  v29 = 0x7FFFFFFF;
  v30 = a4;
  while ( *v30 )
  {
    ++v30;
    if ( !--v29 )
    {
      v31 = 0;
      goto LABEL_28;
    }
  }
  v31 = 2 * (0x7FFFFFFF - v29);
LABEL_28:
  if ( !v29 )
LABEL_82:
    v31 = 0;
  v32 = v31 + 2;
  v33 = GetProcessHeap();
  v34 = HeapAlloc(v33, 8u, v32);
  v35 = v34;
  if ( !v34 )
  {
    SetLastError(8u);
    *((_QWORD *)v9 + 7) = 0;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v69,
        v68,
        L"NcbPolicy: NcbPolicyCreatePolicy failed allocation of package full name - ",
        0);
    goto LABEL_92;
  }
  v36 = v32 >> 1;
  *((_QWORD *)v9 + 7) = v34;
  if ( v36 )
  {
    if ( v36 <= 0x7FFFFFFF )
    {
      v37 = 2147483646;
      v38 = a4;
      do
      {
        if ( !v37 )
          break;
        if ( !*v38 )
          break;
        *v35++ = *v38++;
        --v37;
        --v36;
      }
      while ( v36 );
      v34 = v35 - 1;
      if ( v36 )
        v34 = v35;
    }
    *v34 = 0;
  }
  memset_0(packageFamilyName, 0, 0x208u);
  packageFamilyNameLength[0] = 260;
  v39 = PackageFamilyNameFromFullName(a4, packageFamilyNameLength, packageFamilyName);
  if ( v39 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v41, v40, L"NcbPolicy: PackageFamilyNameFromFullName failed with error - ", v39);
    goto LABEL_90;
  }
  v42 = 0x7FFFFFFF;
  v43 = packageFamilyName;
  while ( *v43 )
  {
    ++v43;
    if ( !--v42 )
    {
      v44 = 0;
      goto LABEL_45;
    }
  }
  v44 = 2 * (0x7FFFFFFF - v42);
LABEL_45:
  if ( !a3 )
    goto LABEL_87;
  v45 = 0x7FFFFFFF;
  v46 = a3;
  while ( *v46 )
  {
    ++v46;
    if ( !--v45 )
    {
      v47 = 0;
      goto LABEL_51;
    }
  }
  v47 = 2 * (0x7FFFFFFF - v45);
LABEL_51:
  if ( !v45 )
LABEL_87:
    v47 = 0;
  v48 = GetProcessHeap();
  v49 = HeapAlloc(v48, 8u, v47 + 4 + v44);
  v50 = v49;
  if ( !v49 )
  {
    SetLastError(8u);
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v41, v40, L"NcbPolicy: AppModelId allocation failed", 0);
LABEL_90:
    *((_QWORD *)v9 + 8) = 0;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v41,
        v40,
        L"NcbPolicy: NcbPolicyCreatePolicy failed allocation of app user model ID - ",
        0);
LABEL_92:
    NcbPolicyFreePolicy(v9);
    return 0;
  }
  v51 = (v44 + 2) >> 1;
  if ( v51 )
  {
    if ( v51 <= 0x7FFFFFFF )
    {
      v52 = 2147483646;
      v53 = packageFamilyName;
      v54 = v49;
      do
      {
        if ( !v52 )
          break;
        if ( !*v53 )
          break;
        *v54++ = *v53++;
        --v52;
        --v51;
      }
      while ( v51 );
      v49 = v54 - 1;
      if ( v51 )
        v49 = v54;
    }
    *v49 = 0;
  }
  v55 = v44 >> 1;
  v56 = (unsigned __int64)(v47 + 2) >> 1;
  v50[v55] = 33;
  if ( v56 )
  {
    v57 = &v50[v55 + 1];
    if ( v56 > 0x7FFFFFFF )
    {
      *v57 = 0;
    }
    else
    {
      do
      {
        if ( !v26 )
          break;
        if ( !*a3 )
          break;
        *v57++ = *a3++;
        --v26;
        --v56;
      }
      while ( v56 );
      v58 = v57 - 1;
      if ( v56 )
        v58 = v57;
      *v58 = 0;
    }
  }
  *((_QWORD *)v9 + 8) = v50;
  return v9;
}

```

## disassembly

```asm
0x18000a1c0  mov     [rsp+arg_10], rbx
0x18000a1c5  push    rbp
0x18000a1c6  push    rsi
0x18000a1c7  push    rdi
0x18000a1c8  push    r12
0x18000a1ca  push    r13
0x18000a1cc  push    r14
0x18000a1ce  push    r15
0x18000a1d0  sub     rsp, 250h
0x18000a1d7  mov     rax, cs:__security_cookie
0x18000a1de  xor     rax, rsp
0x18000a1e1  mov     [rsp+288h+var_48], rax
0x18000a1e9  mov     r15, r9
0x18000a1ec  mov     r14, r8
0x18000a1ef  mov     rsi, rdx
0x18000a1f2  mov     rdi, rcx
0x18000a1f5  call    cs:__imp_GetProcessHeap
0x18000a1fb  mov     edx, 8; dwFlags
0x18000a200  mov     r8d, 48h ; 'H'; dwBytes
0x18000a206  mov     rcx, rax; hHeap
0x18000a209  call    cs:__imp_HeapAlloc
0x18000a20f  mov     r13, rax
0x18000a212  test    rax, rax
0x18000a215  jz      loc_18000A5D3
0x18000a21b  xorps   xmm0, xmm0
0x18000a21e  xor     eax, eax
0x18000a220  movups  xmmword ptr [r13+0], xmm0
0x18000a225  mov     rcx, rdi; Sid
0x18000a228  movups  xmmword ptr [r13+10h], xmm0
0x18000a22d  movups  xmmword ptr [r13+20h], xmm0
0x18000a232  movups  xmmword ptr [r13+30h], xmm0
0x18000a237  mov     [r13+40h], rax
0x18000a23b  call    cs:__imp_RtlLengthSid
0x18000a241  mov     ebp, eax
0x18000a243  call    cs:__imp_GetProcessHeap
0x18000a249  mov     r8d, ebp; dwBytes
0x18000a24c  mov     edx, 8; dwFlags
0x18000a251  mov     rcx, rax; hHeap
0x18000a254  call    cs:__imp_HeapAlloc
0x18000a25a  mov     rbx, rax
0x18000a25d  test    rax, rax
0x18000a260  jz      loc_18000A5FF
0x18000a266  mov     r8, rdi; SourceSid
0x18000a269  mov     [r13+18h], rax
0x18000a26d  mov     rdx, rax; DestinationSid
0x18000a270  mov     ecx, ebp; DestinationSidLength
0x18000a272  call    cs:__imp_RtlCopySid
0x18000a278  lea     rdx, [r13+20h]; StringSid
0x18000a27c  mov     rcx, rdi; Sid
0x18000a27f  call    cs:__imp_ConvertSidToStringSidW
0x18000a285  test    eax, eax
0x18000a287  jz      loc_18000A627
0x18000a28d  mov     rcx, rsi; Sid
0x18000a290  call    cs:__imp_RtlLengthSid
0x18000a296  mov     edi, eax
0x18000a298  call    cs:__imp_GetProcessHeap
0x18000a29e  mov     r8d, edi; dwBytes
0x18000a2a1  mov     edx, 8; dwFlags
0x18000a2a6  mov     rcx, rax; hHeap
0x18000a2a9  call    cs:__imp_HeapAlloc
0x18000a2af  mov     rbx, rax
0x18000a2b2  test    rax, rax
0x18000a2b5  jz      loc_18000A640
0x18000a2bb  mov     r8, rsi; SourceSid
0x18000a2be  mov     [r13+28h], rax
0x18000a2c2  mov     rdx, rax; DestinationSid
0x18000a2c5  mov     ecx, edi; DestinationSidLength
0x18000a2c7  call    cs:__imp_RtlCopySid
0x18000a2cd  test    r14, r14
0x18000a2d0  jz      loc_18000A668
0x18000a2d6  mov     ecx, 7FFFFFFFh
0x18000a2db  mov     rax, r14
0x18000a2de  xchg    ax, ax
0x18000a2e0  cmp     word ptr [rax], 0
0x18000a2e4  jz      short loc_18000A2F8
0x18000a2e6  add     rax, 2
0x18000a2ea  sub     rcx, 1
0x18000a2ee  jnz     short loc_18000A2E0
0x18000a2f0  xor     r12d, r12d
0x18000a2f3  mov     ebx, r12d
0x18000a2f6  jmp     short loc_18000A306
0x18000a2f8  mov     ebx, 7FFFFFFFh
0x18000a2fd  sub     rbx, rcx
0x18000a300  add     rbx, rbx
0x18000a303  xor     r12d, r12d
0x18000a306  test    rcx, rcx
0x18000a309  jz      loc_18000A66B
0x18000a30f  add     rbx, 2
0x18000a313  call    cs:__imp_GetProcessHeap
0x18000a319  mov     r8, rbx; dwBytes
0x18000a31c  mov     edx, 8; dwFlags
0x18000a321  mov     rcx, rax; hHeap
0x18000a324  call    cs:__imp_HeapAlloc
0x18000a32a  mov     rdi, rax
0x18000a32d  test    rax, rax
0x18000a330  jz      loc_18000A673
0x18000a336  shr     rbx, 1
0x18000a339  mov     esi, 7FFFFFFEh
0x18000a33e  mov     [r13+30h], rax
0x18000a342  jz      short loc_18000A382
0x18000a344  cmp     rbx, 7FFFFFFFh
0x18000a34b  ja      short loc_18000A37E
0x18000a34d  mov     ecx, esi
0x18000a34f  mov     rdx, r14
0x18000a352  test    rcx, rcx
0x18000a355  jz      short loc_18000A373
0x18000a357  movzx   eax, word ptr [rdx]
0x18000a35a  test    ax, ax
0x18000a35d  jz      short loc_18000A373
0x18000a35f  mov     [rdi], ax
0x18000a362  add     rdx, 2
0x18000a366  add     rdi, 2
0x18000a36a  dec     rcx
0x18000a36d  sub     rbx, 1
0x18000a371  jnz     short loc_18000A352
0x18000a373  test    rbx, rbx
0x18000a376  lea     rax, [rdi-2]
0x18000a37a  cmovnz  rax, rdi
0x18000a37e  mov     [rax], r12w
0x18000a382  test    r15, r15
0x18000a385  jz      loc_18000A698
0x18000a38b  mov     ecx, 7FFFFFFFh
0x18000a390  mov     rax, r15
0x18000a393  cmp     word ptr [rax], 0
0x18000a397  jz      short loc_18000A3A8
0x18000a399  add     rax, 2
0x18000a39d  sub     rcx, 1
0x18000a3a1  jnz     short loc_18000A393
0x18000a3a3  mov     rbx, r12
0x18000a3a6  jmp     short loc_18000A3B3
0x18000a3a8  mov     ebx, 7FFFFFFFh
0x18000a3ad  sub     rbx, rcx
0x18000a3b0  add     rbx, rbx
0x18000a3b3  test    rcx, rcx
0x18000a3b6  jz      loc_18000A698
0x18000a3bc  add     rbx, 2
0x18000a3c0  call    cs:__imp_GetProcessHeap
0x18000a3c6  mov     r8, rbx; dwBytes
0x18000a3c9  mov     edx, 8; dwFlags
0x18000a3ce  mov     rcx, rax; hHeap
0x18000a3d1  call    cs:__imp_HeapAlloc
0x18000a3d7  mov     rdi, rax
0x18000a3da  test    rax, rax
0x18000a3dd  jz      loc_18000A6A0
0x18000a3e3  shr     rbx, 1
0x18000a3e6  mov     [r13+38h], rax
0x18000a3ea  jz      short loc_18000A430
0x18000a3ec  cmp     rbx, 7FFFFFFFh
0x18000a3f3  ja      short loc_18000A42C
0x18000a3f5  mov     rcx, rsi
0x18000a3f8  mov     rdx, r15
0x18000a3fb  nop     dword ptr [rax+rax+00h]
0x18000a400  test    rcx, rcx
0x18000a403  jz      short loc_18000A421
0x18000a405  movzx   eax, word ptr [rdx]
0x18000a408  test    ax, ax
0x18000a40b  jz      short loc_18000A421
0x18000a40d  mov     [rdi], ax
0x18000a410  add     rdx, 2
0x18000a414  add     rdi, 2
0x18000a418  dec     rcx
0x18000a41b  sub     rbx, 1
0x18000a41f  jnz     short loc_18000A400
0x18000a421  test    rbx, rbx
0x18000a424  lea     rax, [rdi-2]
0x18000a428  cmovnz  rax, rdi
0x18000a42c  mov     [rax], r12w
0x18000a430  xor     edx, edx; Val
0x18000a432  lea     rcx, [rsp+288h+packageFamilyName]; void *
0x18000a437  mov     r8d, 208h; Size
0x18000a43d  call    memset_0
0x18000a442  lea     r8, [rsp+288h+packageFamilyName]; packageFamilyName
0x18000a447  mov     [rsp+288h+packageFamilyNameLength], 104h
0x18000a44f  lea     rdx, [rsp+288h+packageFamilyNameLength]; packageFamilyNameLength
0x18000a454  mov     rcx, r15; packageFullName
0x18000a457  call    cs:__imp_PackageFamilyNameFromFullName
0x18000a45d  test    eax, eax
0x18000a45f  jnz     loc_18000A6C1
0x18000a465  mov     ecx, 7FFFFFFFh
0x18000a46a  lea     rax, [rsp+288h+packageFamilyName]
0x18000a46f  nop
0x18000a470  cmp     word ptr [rax], 0
0x18000a474  jz      short loc_18000A485
0x18000a476  add     rax, 2
0x18000a47a  sub     rcx, 1
0x18000a47e  jnz     short loc_18000A470
0x18000a480  mov     rbp, r12
0x18000a483  jmp     short loc_18000A490
0x18000a485  mov     ebp, 7FFFFFFFh
0x18000a48a  sub     rbp, rcx
0x18000a48d  add     rbp, rbp
0x18000a490  test    r14, r14
0x18000a493  jz      loc_18000A6D6
0x18000a499  mov     ecx, 7FFFFFFFh
0x18000a49e  mov     rax, r14
0x18000a4a1  cmp     word ptr [rax], 0
0x18000a4a5  jz      short loc_18000A4B6
0x18000a4a7  add     rax, 2
0x18000a4ab  sub     rcx, 1
0x18000a4af  jnz     short loc_18000A4A1
0x18000a4b1  mov     rdi, r12
0x18000a4b4  jmp     short loc_18000A4C1
0x18000a4b6  mov     edi, 7FFFFFFFh
0x18000a4bb  sub     rdi, rcx
0x18000a4be  add     rdi, rdi
0x18000a4c1  test    rcx, rcx
0x18000a4c4  jz      loc_18000A6D6
0x18000a4ca  lea     rbx, [rdi+4]
0x18000a4ce  call    cs:__imp_GetProcessHeap
0x18000a4d4  lea     r8, [rbx+rbp]; dwBytes
0x18000a4d8  mov     edx, 8; dwFlags
0x18000a4dd  mov     rcx, rax; hHeap
0x18000a4e0  call    cs:__imp_HeapAlloc
0x18000a4e6  mov     r10, rax
0x18000a4e9  test    rax, rax
0x18000a4ec  jz      loc_18000A6DE
0x18000a4f2  lea     r8, [rbp+2]
0x18000a4f6  shr     r8, 1
0x18000a4f9  jz      short loc_18000A541
0x18000a4fb  cmp     r8, 7FFFFFFFh
0x18000a502  ja      short loc_18000A53D
0x18000a504  mov     rcx, rsi
0x18000a507  lea     rdx, [rsp+288h+packageFamilyName]
0x18000a50c  mov     r9, rax
0x18000a50f  nop
0x18000a510  test    rcx, rcx
0x18000a513  jz      short loc_18000A532
0x18000a515  movzx   eax, word ptr [rdx]
0x18000a518  test    ax, ax
0x18000a51b  jz      short loc_18000A532
0x18000a51d  mov     [r9], ax
0x18000a521  add     rdx, 2
0x18000a525  add     r9, 2
0x18000a529  dec     rcx
0x18000a52c  sub     r8, 1
0x18000a530  jnz     short loc_18000A510
0x18000a532  test    r8, r8
0x18000a535  lea     rax, [r9-2]
0x18000a539  cmovnz  rax, r9
0x18000a53d  mov     [rax], r12w
0x18000a541  shr     rbp, 1
0x18000a544  lea     rcx, [rdi+2]
0x18000a548  shr     rcx, 1
0x18000a54b  mov     word ptr [r10+rbp*2], 21h ; '!'
0x18000a552  jz      short loc_18000A5A1
0x18000a554  lea     rdx, [r10+2]
0x18000a558  lea     rdx, [rdx+rbp*2]
0x18000a55c  cmp     rcx, 7FFFFFFFh
0x18000a563  ja      loc_18000A72C
0x18000a569  nop     dword ptr [rax+00000000h]
0x18000a570  test    rsi, rsi
0x18000a573  jz      short loc_18000A592
0x18000a575  movzx   eax, word ptr [r14]
0x18000a579  test    ax, ax
0x18000a57c  jz      short loc_18000A592
0x18000a57e  mov     [rdx], ax
0x18000a581  add     r14, 2
0x18000a585  add     rdx, 2
0x18000a589  dec     rsi
0x18000a58c  sub     rcx, 1
0x18000a590  jnz     short loc_18000A570
0x18000a592  test    rcx, rcx
0x18000a595  lea     rax, [rdx-2]
0x18000a599  cmovnz  rax, rdx
0x18000a59d  mov     [rax], r12w
0x18000a5a1  mov     [r13+40h], r10
0x18000a5a5  mov     rax, r13
0x18000a5a8  mov     rcx, [rsp+288h+var_48]
0x18000a5b0  xor     rcx, rsp; StackCookie
0x18000a5b3  call    __security_check_cookie
0x18000a5b8  mov     rbx, [rsp+288h+arg_10]
0x18000a5c0  add     rsp, 250h
0x18000a5c7  pop     r15
0x18000a5c9  pop     r14
0x18000a5cb  pop     r13
0x18000a5cd  pop     r12
0x18000a5cf  pop     rdi
0x18000a5d0  pop     rsi
0x18000a5d1  pop     rbp
0x18000a5d2  retn
0x18000a5d3  mov     ecx, 8; dwErrCode
0x18000a5d8  call    cs:__imp_SetLastError
0x18000a5de  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000a5e5  jz      loc_18000A725
0x18000a5eb  xor     r9d, r9d
0x18000a5ee  lea     r8, aNcbpolicyNcbpo_17; "NcbPolicy: NcbPolicyCreatePolicy failed"...
0x18000a5f5  call    McTemplateU0zq_EventWriteTransfer
0x18000a5fa  jmp     loc_18000A725
0x18000a5ff  mov     ecx, 8; dwErrCode
0x18000a604  call    cs:__imp_SetLastError
0x18000a60a  mov     [r13+18h], rbx
0x18000a60e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000a615  jz      loc_18000A71D
0x18000a61b  lea     r8, aNcbpolicyNcbpo_13; "NcbPolicy: NcbPolicyCreatePolicy failed"...
0x18000a622  jmp     loc_18000A715
0x18000a627  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000a62e  jz      loc_18000A71D
0x18000a634  lea     r8, aNcbpolicyNcbpo_1; "NcbPolicy: NcbPolicyCreatePolicy failed"...
0x18000a63b  jmp     loc_18000A715
0x18000a640  mov     ecx, 8; dwErrCode
  ... truncated ...
```
