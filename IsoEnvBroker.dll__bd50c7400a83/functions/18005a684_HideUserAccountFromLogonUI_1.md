# HideUserAccountFromLogonUI_1

- ea: `0x18005a684`
- end: `0x18005ac0f`
- name: `HideUserAccountFromLogonUI_1`
- size: `1419`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180059200`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x18000a464`
- `0x18005a684`
- `0x180063980`
- `0x180063a08`
- `0x180063bf4`

## import_xrefs

- `SAMLIB!SamOpenDomain` at `0x18005a837`
- `SAMLIB!SamOpenDomain` at `0x18005a837`
- `SAMLIB!SamLookupNamesInDomain` at `0x18005a8fe`
- `SAMLIB!SamLookupNamesInDomain` at `0x18005a8fe`
- `SAMLIB!SamCloseHandle` at `0x18005a7eb`
- `SAMLIB!SamCloseHandle` at `0x18005a869`
- `SAMLIB!SamCloseHandle` at `0x18005a879`
- `SAMLIB!SamCloseHandle` at `0x18005a9a1`
- `SAMLIB!SamCloseHandle` at `0x18005a9b1`
- `SAMLIB!SamCloseHandle` at `0x18005aa2b`
- `SAMLIB!SamCloseHandle` at `0x18005aa65`
- `SAMLIB!SamCloseHandle` at `0x18005aa75`
- `SAMLIB!SamCloseHandle` at `0x18005aafd`
- `SAMLIB!SamCloseHandle` at `0x18005ab37`
- `SAMLIB!SamCloseHandle` at `0x18005ab47`
- `SAMLIB!SamCloseHandle` at `0x18005ab79`
- `SAMLIB!SamCloseHandle` at `0x18005abb3`
- `SAMLIB!SamCloseHandle` at `0x18005abc3`
- `SAMLIB!SamCloseHandle` at `0x18005a7eb`
- `SAMLIB!SamCloseHandle` at `0x18005a869`
- `SAMLIB!SamCloseHandle` at `0x18005a879`
- `SAMLIB!SamCloseHandle` at `0x18005a9a1`
- `SAMLIB!SamCloseHandle` at `0x18005a9b1`
- `SAMLIB!SamCloseHandle` at `0x18005aa2b`
- `SAMLIB!SamCloseHandle` at `0x18005aa65`
- `SAMLIB!SamCloseHandle` at `0x18005aa75`
- `SAMLIB!SamCloseHandle` at `0x18005aafd`
- `SAMLIB!SamCloseHandle` at `0x18005ab37`
- `SAMLIB!SamCloseHandle` at `0x18005ab47`
- `SAMLIB!SamCloseHandle` at `0x18005ab79`
- `SAMLIB!SamCloseHandle` at `0x18005abb3`
- `SAMLIB!SamCloseHandle` at `0x18005abc3`
- `SAMLIB!SamConnect` at `0x18005a7b9`
- `SAMLIB!SamConnect` at `0x18005a7b9`
- `SAMLIB!SamFreeMemory` at `0x18005a925`
- `SAMLIB!SamFreeMemory` at `0x18005a944`
- `SAMLIB!SamFreeMemory` at `0x18005a97c`
- `SAMLIB!SamFreeMemory` at `0x18005a991`
- `SAMLIB!SamFreeMemory` at `0x18005aa40`
- `SAMLIB!SamFreeMemory` at `0x18005aa55`
- `SAMLIB!SamFreeMemory` at `0x18005ab12`
- `SAMLIB!SamFreeMemory` at `0x18005ab27`
- `SAMLIB!SamFreeMemory` at `0x18005ab8e`
- `SAMLIB!SamFreeMemory` at `0x18005aba3`
- `SAMLIB!SamFreeMemory` at `0x18005a925`
- `SAMLIB!SamFreeMemory` at `0x18005a944`
- `SAMLIB!SamFreeMemory` at `0x18005a97c`
- `SAMLIB!SamFreeMemory` at `0x18005a991`
- `SAMLIB!SamFreeMemory` at `0x18005aa40`
- `SAMLIB!SamFreeMemory` at `0x18005aa55`
- `SAMLIB!SamFreeMemory` at `0x18005ab12`
- `SAMLIB!SamFreeMemory` at `0x18005ab27`
- `SAMLIB!SamFreeMemory` at `0x18005ab8e`
- `SAMLIB!SamFreeMemory` at `0x18005aba3`
- `SAMLIB!SamSetInformationUser` at `0x18005aac7`
- `SAMLIB!SamSetInformationUser` at `0x18005aac7`
- `SAMLIB!SamOpenUser` at `0x18005a9f5`
- `SAMLIB!SamOpenUser` at `0x18005a9f5`
- `ntdll!RtlInitUnicodeString` at `0x18005a8ad`
- `ntdll!RtlInitUnicodeString` at `0x18005a8ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a775`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a7fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a883`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a9bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005aa7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ab51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005abcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a775`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a7fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a883`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a9bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005aa7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ab51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005abcd`

## string_xrefs

- `0x18005a70a`: `onecoreuap\windows\core\isoenvbroker\lib\v2\agentaccounthelpers.cpp`
- `0x18005a759`: `onecoreuap\windows\core\isoenvbroker\lib\v2\agentaccounthelpers.cpp`
- `0x18005a7d0`: `onecoreuap\windows\core\isoenvbroker\lib\v2\agentaccounthelpers.cpp`
- `0x18005a84e`: `onecoreuap\windows\core\isoenvbroker\lib\v2\agentaccounthelpers.cpp`
- `0x18005a95c`: `onecoreuap\windows\core\isoenvbroker\lib\v2\agentaccounthelpers.cpp`
- `0x18005aa10`: `onecoreuap\windows\core\isoenvbroker\lib\v2\agentaccounthelpers.cpp`
- `0x18005aae2`: `onecoreuap\windows\core\isoenvbroker\lib\v2\agentaccounthelpers.cpp`

## pseudocode

```c
__int64 __fastcall HideUserAccountFromLogonUI_1(struct _LSA_UNICODE_STRING *SourceString)
{
  NTSTATUS v2; // eax
  POLICY_INFORMATION_CLASS v3; // edx
  unsigned int v4; // ebx
  PVOID v6; // rdi
  NTSTATUS v7; // eax
  int v8; // eax
  PVOID v9; // rbx
  int v10; // eax
  unsigned int v11; // esi
  unsigned int *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int *v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  unsigned int *v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  unsigned int *v21; // rcx
  __int64 v22; // rcx
  unsigned int *v23; // rcx
  int v24; // [rsp+20h] [rbp-E0h]
  unsigned int *v25; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  PVOID Buffer; // [rsp+58h] [rbp-A8h] BYREF
  PVOID PolicyHandle; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int **v32; // [rsp+68h] [rbp-98h]
  unsigned int *v33; // [rsp+70h] [rbp-90h] BYREF
  char v34; // [rsp+78h] [rbp-88h]
  __int64 *v35; // [rsp+80h] [rbp-80h]
  int v36[2]; // [rsp+88h] [rbp-78h] BYREF
  char v37; // [rsp+90h] [rbp-70h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-38h] BYREF
  _DWORD v40[10]; // [rsp+E0h] [rbp-20h] BYREF
  char v41; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  PolicyHandle = 0;
  v2 = LsaOpenPolicy(SourceString, &ObjectAttributes, 1u, &PolicyHandle);
  v4 = v2 | 0x10000000;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\agentaccounthelpers.cpp",
      (const char *)v4,
      v24);
    if ( PolicyHandle )
      LsaClose(PolicyHandle);
    return v4;
  }
  Buffer = 0;
  v6 = PolicyHandle;
  v7 = LsaQueryInformationPolicy(PolicyHandle, v3, &Buffer);
  v4 = v7 | 0x10000000;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\agentaccounthelpers.cpp",
      (const char *)v4,
      v24);
    if ( Buffer )
      LocalFree(Buffer);
    if ( v6 )
      LsaClose(v6);
    return v4;
  }
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v28 = 0;
  v8 = SamConnect(0, &v28, 32, &ObjectAttributes);
  v4 = v8 | 0x10000000;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\agentaccounthelpers.cpp",
      (const char *)v4,
      v24);
    if ( v28 )
      SamCloseHandle(v28);
    if ( Buffer )
      LocalFree(Buffer);
    if ( v6 )
      LsaClose(v6);
    return v4;
  }
  v27 = 0;
  v9 = Buffer;
  v10 = SamOpenDomain(v28, 0x2000000, *((_QWORD *)Buffer + 2), &v27);
  v11 = v10 | 0x10000000;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\agentaccounthelpers.cpp",
      (const char *)v11,
      v24);
    if ( v27 )
      SamCloseHandle(v27);
    if ( v28 )
      SamCloseHandle(v28);
    LocalFree(v9);
    if ( v6 )
      LsaClose(v6);
    return v11;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, &SourceString->Length);
  v25 = 0;
  v26 = 0;
  v35 = &v26;
  *(_QWORD *)v36 = 0;
  v37 = 1;
  v32 = &v25;
  v33 = 0;
  v34 = 1;
  v11 = SamLookupNamesInDomain(v27, 1, &DestinationString, &v33) | 0x10000000;
  if ( v34 )
  {
    v12 = *v32;
    *v32 = v33;
    if ( v12 )
      SamFreeMemory(v12);
  }
  if ( v37 )
  {
    v13 = *v35;
    *v35 = *(_QWORD *)v36;
    if ( v13 )
      SamFreeMemory(v13);
  }
  if ( (v11 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\agentaccounthelpers.cpp",
      (const char *)v11,
      (int)v36);
    v14 = v26;
    v26 = 0;
    if ( v14 )
      SamFreeMemory(v14);
    v15 = v25;
    v25 = 0;
    if ( v15 )
      SamFreeMemory(v15);
    if ( v27 )
      SamCloseHandle(v27);
    if ( v28 )
      SamCloseHandle(v28);
    LocalFree(v9);
    if ( !v6 )
      return v11;
    goto LABEL_67;
  }
  v29 = 0;
  v16 = SamOpenUser(v27, 0x2000000, *v25, &v29);
  v11 = v16 | 0x10000000;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\agentaccounthelpers.cpp",
      (const char *)v11,
      (int)v36);
    if ( v29 )
      SamCloseHandle(v29);
    v17 = v26;
    v26 = 0;
    if ( v17 )
      SamFreeMemory(v17);
    v18 = v25;
    v25 = 0;
    if ( v18 )
      SamFreeMemory(v18);
    if ( v27 )
      SamCloseHandle(v27);
    if ( v28 )
      SamCloseHandle(v28);
    LocalFree(v9);
    if ( !v6 )
      return v11;
    goto LABEL_67;
  }
  memset_0(v40, 0, 0xA8u);
  v40[0] = 0x4000;
  v41 = 1;
  v19 = SamSetInformationUser(v29, 28, v40);
  v11 = v19 | 0x10000000;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\agentaccounthelpers.cpp",
      (const char *)v11,
      (int)v36);
    if ( v29 )
      SamCloseHandle(v29);
    v20 = v26;
    v26 = 0;
    if ( v20 )
      SamFreeMemory(v20);
    v21 = v25;
    v25 = 0;
    if ( v21 )
      SamFreeMemory(v21);
    if ( v27 )
      SamCloseHandle(v27);
    if ( v28 )
      SamCloseHandle(v28);
    LocalFree(v9);
    if ( !v6 )
      return v11;
LABEL_67:
    LsaClose(v6);
    return v11;
  }
  if ( v29 )
    SamCloseHandle(v29);
  v22 = v26;
  v26 = 0;
  if ( v22 )
    SamFreeMemory(v22);
  v23 = v25;
  v25 = 0;
  if ( v23 )
    SamFreeMemory(v23);
  if ( v27 )
    SamCloseHandle(v27);
  if ( v28 )
    SamCloseHandle(v28);
  LocalFree(v9);
  if ( v6 )
    LsaClose(v6);
  return 0;
}

```

## disassembly

```asm
0x18005a684  mov     [rsp-8+arg_8], rbx
0x18005a689  mov     [rsp-8+arg_10], rsi
0x18005a68e  push    rbp
0x18005a68f  push    rdi
0x18005a690  push    r12
0x18005a692  push    r14
0x18005a694  push    r15
0x18005a696  lea     rbp, [rsp-0A0h]
0x18005a69e  sub     rsp, 1A0h
0x18005a6a5  mov     rax, cs:__security_cookie
0x18005a6ac  xor     rax, rsp
0x18005a6af  mov     [rbp+0C0h+var_30], rax
0x18005a6b6  mov     r14, rcx
0x18005a6b9  xor     r15d, r15d
0x18005a6bc  mov     qword ptr [rbp+0C0h+ObjectAttributes.Length], 30h ; '0'
0x18005a6c4  mov     qword ptr [rbp+0C0h+ObjectAttributes.Attributes], r15
0x18005a6c8  lea     esi, [r15+30h]
0x18005a6cc  mov     [rbp+0C0h+ObjectAttributes.RootDirectory], r15
0x18005a6d0  mov     [rbp+0C0h+ObjectAttributes.ObjectName], r15
0x18005a6d4  xorps   xmm0, xmm0
0x18005a6d7  movdqu  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005a6dc  mov     [rsp+1C0h+PolicyHandle], r15
0x18005a6e1  lea     r9, [rsp+1C0h+PolicyHandle]; PolicyHandle
0x18005a6e6  lea     r8d, [r15+1]; DesiredAccess
0x18005a6ea  lea     rdx, [rbp+0C0h+ObjectAttributes]; ObjectAttributes
0x18005a6ee  call    LsaOpenPolicy
0x18005a6f3  mov     ebx, eax
0x18005a6f5  mov     r12d, 10000000h
0x18005a6fb  or      ebx, r12d
0x18005a6fe  jge     short loc_18005A731
0x18005a700  mov     rcx, [rbp+0C8h]; this
0x18005a707  mov     r9d, ebx; char *
0x18005a70a  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005a711  lea     edx, [rsi+4]; void *
0x18005a714  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a719  nop
0x18005a71a  mov     rcx, [rsp+1C0h+PolicyHandle]; ObjectHandle
0x18005a71f  test    rcx, rcx
0x18005a722  jz      short loc_18005A72A
0x18005a724  call    LsaClose
0x18005a729  nop
0x18005a72a  mov     eax, ebx
0x18005a72c  jmp     loc_18005ABE4
0x18005a731  mov     [rsp+1C0h+Buffer], r15
0x18005a736  lea     r8, [rsp+1C0h+Buffer]; Buffer
0x18005a73b  mov     rdi, [rsp+1C0h+PolicyHandle]
0x18005a740  mov     rcx, rdi; PolicyHandle
0x18005a743  call    LsaQueryInformationPolicy
0x18005a748  mov     ebx, eax
0x18005a74a  or      ebx, r12d
0x18005a74d  jge     short loc_18005A78C
0x18005a74f  mov     rcx, [rbp+0C8h]; this
0x18005a756  mov     r9d, ebx; char *
0x18005a759  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005a760  mov     edx, 3Ah ; ':'; void *
0x18005a765  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a76a  nop
0x18005a76b  mov     rcx, [rsp+1C0h+Buffer]; hMem
0x18005a770  test    rcx, rcx
0x18005a773  jz      short loc_18005A77C
0x18005a775  call    cs:__imp_LocalFree
0x18005a77b  nop
0x18005a77c  test    rdi, rdi
0x18005a77f  jz      short loc_18005A72A
0x18005a781  mov     rcx, rdi; ObjectHandle
0x18005a784  call    LsaClose
0x18005a789  nop
0x18005a78a  jmp     short loc_18005A72A
0x18005a78c  mov     [rbp+0C0h+ObjectAttributes.Length], esi
0x18005a78f  mov     [rbp+0C0h+ObjectAttributes.RootDirectory], r15
0x18005a793  mov     [rbp+0C0h+ObjectAttributes.Attributes], r15d
0x18005a797  mov     [rbp+0C0h+ObjectAttributes.ObjectName], r15
0x18005a79b  xorps   xmm0, xmm0
0x18005a79e  movdqu  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005a7a3  mov     [rsp+1C0h+var_178], r15
0x18005a7a8  lea     r9, [rbp+0C0h+ObjectAttributes]
0x18005a7ac  mov     r8d, 20h ; ' '
0x18005a7b2  lea     rdx, [rsp+1C0h+var_178]
0x18005a7b7  xor     ecx, ecx
0x18005a7b9  call    cs:__imp_SamConnect
0x18005a7bf  mov     ebx, eax
0x18005a7c1  or      ebx, r12d
0x18005a7c4  jge     short loc_18005A81A
0x18005a7c6  mov     rcx, [rbp+0C8h]; this
0x18005a7cd  mov     r9d, ebx; char *
0x18005a7d0  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005a7d7  mov     edx, 42h ; 'B'; void *
0x18005a7dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a7e1  mov     rcx, [rsp+1C0h+var_178]
0x18005a7e6  test    rcx, rcx
0x18005a7e9  jz      short loc_18005A7F2
0x18005a7eb  call    cs:__imp_SamCloseHandle
0x18005a7f1  nop
0x18005a7f2  mov     rcx, [rsp+1C0h+Buffer]; hMem
0x18005a7f7  test    rcx, rcx
0x18005a7fa  jz      short loc_18005A803
0x18005a7fc  call    cs:__imp_LocalFree
0x18005a802  nop
0x18005a803  test    rdi, rdi
0x18005a806  jz      loc_18005A72A
0x18005a80c  mov     rcx, rdi; ObjectHandle
0x18005a80f  call    LsaClose
0x18005a814  nop
0x18005a815  jmp     loc_18005A72A
0x18005a81a  mov     [rsp+1C0h+var_180], r15
0x18005a81f  lea     r9, [rsp+1C0h+var_180]
0x18005a824  mov     rbx, [rsp+1C0h+Buffer]
0x18005a829  mov     r8, [rbx+10h]
0x18005a82d  mov     edx, 2000000h
0x18005a832  mov     rcx, [rsp+1C0h+var_178]
0x18005a837  call    cs:__imp_SamOpenDomain
0x18005a83d  mov     esi, eax
0x18005a83f  or      esi, r12d
0x18005a842  jge     short loc_18005A89F
0x18005a844  mov     rcx, [rbp+0C8h]; this
0x18005a84b  mov     r9d, esi; char *
0x18005a84e  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005a855  mov     edx, 49h ; 'I'; void *
0x18005a85a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a85f  mov     rcx, [rsp+1C0h+var_180]
0x18005a864  test    rcx, rcx
0x18005a867  jz      short loc_18005A86F
0x18005a869  call    cs:__imp_SamCloseHandle
0x18005a86f  mov     rcx, [rsp+1C0h+var_178]
0x18005a874  test    rcx, rcx
0x18005a877  jz      short loc_18005A880
0x18005a879  call    cs:__imp_SamCloseHandle
0x18005a87f  nop
0x18005a880  mov     rcx, rbx; hMem
0x18005a883  call    cs:__imp_LocalFree
0x18005a889  nop
0x18005a88a  test    rdi, rdi
0x18005a88d  jz      short loc_18005A898
0x18005a88f  mov     rcx, rdi; ObjectHandle
0x18005a892  call    LsaClose
0x18005a897  nop
0x18005a898  mov     eax, esi
0x18005a89a  jmp     loc_18005ABE4
0x18005a89f  xorps   xmm0, xmm0
0x18005a8a2  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm0
0x18005a8a6  mov     rdx, r14; SourceString
0x18005a8a9  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x18005a8ad  call    cs:__imp_RtlInitUnicodeString
0x18005a8b3  mov     [rsp+1C0h+var_190], r15
0x18005a8b8  mov     [rsp+1C0h+var_188], r15
0x18005a8bd  lea     rax, [rsp+1C0h+var_188]
0x18005a8c2  mov     [rbp+0C0h+var_140], rax
0x18005a8c6  mov     qword ptr [rbp+0C0h+var_138], r15
0x18005a8ca  mov     [rbp+0C0h+var_130], 1
0x18005a8ce  lea     rax, [rsp+1C0h+var_190]
0x18005a8d3  mov     [rsp+1C0h+var_158], rax
0x18005a8d8  mov     [rsp+1C0h+var_150], r15
0x18005a8dd  mov     [rsp+1C0h+var_148], 1
0x18005a8e2  lea     rax, [rbp+0C0h+var_138]
0x18005a8e6  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x18005a8eb  lea     r9, [rsp+1C0h+var_150]
0x18005a8f0  lea     r8, [rbp+0C0h+DestinationString]
0x18005a8f4  mov     edx, 1
0x18005a8f9  mov     rcx, [rsp+1C0h+var_180]
0x18005a8fe  call    cs:__imp_SamLookupNamesInDomain
0x18005a904  mov     esi, eax
0x18005a906  or      esi, r12d
0x18005a909  cmp     [rsp+1C0h+var_148], r15b
0x18005a90e  jz      short loc_18005A92B
0x18005a910  mov     rdx, [rsp+1C0h+var_158]
0x18005a915  mov     rcx, [rdx]
0x18005a918  mov     rax, [rsp+1C0h+var_150]
0x18005a91d  mov     [rdx], rax
0x18005a920  test    rcx, rcx
0x18005a923  jz      short loc_18005A92B
0x18005a925  call    cs:__imp_SamFreeMemory
0x18005a92b  cmp     [rbp+0C0h+var_130], r15b
0x18005a92f  jz      short loc_18005A94A
0x18005a931  mov     rdx, [rbp+0C0h+var_140]
0x18005a935  mov     rcx, [rdx]
0x18005a938  mov     rax, qword ptr [rbp+0C0h+var_138]
0x18005a93c  mov     [rdx], rax
0x18005a93f  test    rcx, rcx
0x18005a942  jz      short loc_18005A94A
0x18005a944  call    cs:__imp_SamFreeMemory
0x18005a94a  test    esi, esi
0x18005a94c  jns     loc_18005A9D9
0x18005a952  mov     rcx, [rbp+0C8h]; this
0x18005a959  mov     r9d, esi; char *
0x18005a95c  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005a963  mov     edx, 54h ; 'T'; void *
0x18005a968  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a96d  mov     rcx, [rsp+1C0h+var_188]
0x18005a972  mov     [rsp+1C0h+var_188], r15
0x18005a977  test    rcx, rcx
0x18005a97a  jz      short loc_18005A982
0x18005a97c  call    cs:__imp_SamFreeMemory
0x18005a982  mov     rcx, [rsp+1C0h+var_190]
0x18005a987  mov     [rsp+1C0h+var_190], r15
0x18005a98c  test    rcx, rcx
0x18005a98f  jz      short loc_18005A997
0x18005a991  call    cs:__imp_SamFreeMemory
0x18005a997  mov     rcx, [rsp+1C0h+var_180]
0x18005a99c  test    rcx, rcx
0x18005a99f  jz      short loc_18005A9A7
0x18005a9a1  call    cs:__imp_SamCloseHandle
0x18005a9a7  mov     rcx, [rsp+1C0h+var_178]
0x18005a9ac  test    rcx, rcx
0x18005a9af  jz      short loc_18005A9B8
0x18005a9b1  call    cs:__imp_SamCloseHandle
0x18005a9b7  nop
0x18005a9b8  mov     rcx, rbx; hMem
0x18005a9bb  call    cs:__imp_LocalFree
0x18005a9c1  nop
0x18005a9c2  test    rdi, rdi
0x18005a9c5  jz      loc_18005A898
0x18005a9cb  mov     rcx, rdi; ObjectHandle
0x18005a9ce  call    LsaClose
0x18005a9d3  nop
0x18005a9d4  jmp     loc_18005A898
0x18005a9d9  mov     [rsp+1C0h+var_170], r15
0x18005a9de  lea     r9, [rsp+1C0h+var_170]
0x18005a9e3  mov     r8, [rsp+1C0h+var_190]
0x18005a9e8  mov     r8d, [r8]
0x18005a9eb  mov     edx, 2000000h
0x18005a9f0  mov     rcx, [rsp+1C0h+var_180]
0x18005a9f5  call    cs:__imp_SamOpenUser
0x18005a9fb  mov     esi, eax
0x18005a9fd  or      esi, r12d
0x18005aa00  jge     loc_18005AA9D
0x18005aa06  mov     rcx, [rbp+0C8h]; this
0x18005aa0d  mov     r9d, esi; char *
0x18005aa10  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005aa17  mov     edx, 5Bh ; '['; void *
0x18005aa1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005aa21  mov     rcx, [rsp+1C0h+var_170]
0x18005aa26  test    rcx, rcx
0x18005aa29  jz      short loc_18005AA31
0x18005aa2b  call    cs:__imp_SamCloseHandle
0x18005aa31  mov     rcx, [rsp+1C0h+var_188]
0x18005aa36  mov     [rsp+1C0h+var_188], r15
0x18005aa3b  test    rcx, rcx
0x18005aa3e  jz      short loc_18005AA46
0x18005aa40  call    cs:__imp_SamFreeMemory
0x18005aa46  mov     rcx, [rsp+1C0h+var_190]
0x18005aa4b  mov     [rsp+1C0h+var_190], r15
0x18005aa50  test    rcx, rcx
0x18005aa53  jz      short loc_18005AA5B
0x18005aa55  call    cs:__imp_SamFreeMemory
0x18005aa5b  mov     rcx, [rsp+1C0h+var_180]
0x18005aa60  test    rcx, rcx
0x18005aa63  jz      short loc_18005AA6B
0x18005aa65  call    cs:__imp_SamCloseHandle
0x18005aa6b  mov     rcx, [rsp+1C0h+var_178]
0x18005aa70  test    rcx, rcx
0x18005aa73  jz      short loc_18005AA7C
0x18005aa75  call    cs:__imp_SamCloseHandle
0x18005aa7b  nop
0x18005aa7c  mov     rcx, rbx; hMem
0x18005aa7f  call    cs:__imp_LocalFree
0x18005aa85  nop
0x18005aa86  test    rdi, rdi
0x18005aa89  jz      loc_18005A898
0x18005aa8f  mov     rcx, rdi; ObjectHandle
0x18005aa92  call    LsaClose
0x18005aa97  nop
0x18005aa98  jmp     loc_18005A898
0x18005aa9d  xor     edx, edx; Val
0x18005aa9f  mov     r8d, 0A8h; Size
0x18005aaa5  lea     rcx, [rbp+0C0h+var_E0]; void *
0x18005aaa9  call    memset_0
0x18005aaae  mov     [rbp+0C0h+var_E0], 4000h
0x18005aab5  mov     [rbp+0C0h+var_B8], 1
0x18005aab9  lea     r8, [rbp+0C0h+var_E0]
0x18005aabd  mov     edx, 1Ch
0x18005aac2  mov     rcx, [rsp+1C0h+var_170]
0x18005aac7  call    cs:__imp_SamSetInformationUser
0x18005aacd  mov     esi, eax
0x18005aacf  or      esi, r12d
0x18005aad2  jge     loc_18005AB6F
0x18005aad8  mov     rcx, [rbp+0C8h]; this
0x18005aadf  mov     r9d, esi; char *
0x18005aae2  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005aae9  mov     edx, 63h ; 'c'; void *
0x18005aaee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005aaf3  mov     rcx, [rsp+1C0h+var_170]
0x18005aaf8  test    rcx, rcx
0x18005aafb  jz      short loc_18005AB03
0x18005aafd  call    cs:__imp_SamCloseHandle
0x18005ab03  mov     rcx, [rsp+1C0h+var_188]
0x18005ab08  mov     [rsp+1C0h+var_188], r15
0x18005ab0d  test    rcx, rcx
0x18005ab10  jz      short loc_18005AB18
0x18005ab12  call    cs:__imp_SamFreeMemory
0x18005ab18  mov     rcx, [rsp+1C0h+var_190]
0x18005ab1d  mov     [rsp+1C0h+var_190], r15
0x18005ab22  test    rcx, rcx
0x18005ab25  jz      short loc_18005AB2D
0x18005ab27  call    cs:__imp_SamFreeMemory
0x18005ab2d  mov     rcx, [rsp+1C0h+var_180]
0x18005ab32  test    rcx, rcx
0x18005ab35  jz      short loc_18005AB3D
0x18005ab37  call    cs:__imp_SamCloseHandle
0x18005ab3d  mov     rcx, [rsp+1C0h+var_178]
0x18005ab42  test    rcx, rcx
  ... truncated ...
```
