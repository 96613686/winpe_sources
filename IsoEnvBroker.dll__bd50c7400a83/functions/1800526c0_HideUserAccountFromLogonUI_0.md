# HideUserAccountFromLogonUI_0

- ea: `0x1800526c0`
- end: `0x180052c4d`
- name: `HideUserAccountFromLogonUI_0`
- size: `1421`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800507a8`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x18000a464`
- `0x1800526c0`
- `0x180063980`
- `0x180063a08`
- `0x180063bf4`

## import_xrefs

- `SAMLIB!SamOpenDomain` at `0x180052875`
- `SAMLIB!SamOpenDomain` at `0x180052875`
- `SAMLIB!SamLookupNamesInDomain` at `0x18005293c`
- `SAMLIB!SamLookupNamesInDomain` at `0x18005293c`
- `SAMLIB!SamCloseHandle` at `0x180052829`
- `SAMLIB!SamCloseHandle` at `0x1800528a7`
- `SAMLIB!SamCloseHandle` at `0x1800528b7`
- `SAMLIB!SamCloseHandle` at `0x1800529df`
- `SAMLIB!SamCloseHandle` at `0x1800529ef`
- `SAMLIB!SamCloseHandle` at `0x180052a69`
- `SAMLIB!SamCloseHandle` at `0x180052aa3`
- `SAMLIB!SamCloseHandle` at `0x180052ab3`
- `SAMLIB!SamCloseHandle` at `0x180052b3b`
- `SAMLIB!SamCloseHandle` at `0x180052b75`
- `SAMLIB!SamCloseHandle` at `0x180052b85`
- `SAMLIB!SamCloseHandle` at `0x180052bb7`
- `SAMLIB!SamCloseHandle` at `0x180052bf1`
- `SAMLIB!SamCloseHandle` at `0x180052c01`
- `SAMLIB!SamCloseHandle` at `0x180052829`
- `SAMLIB!SamCloseHandle` at `0x1800528a7`
- `SAMLIB!SamCloseHandle` at `0x1800528b7`
- `SAMLIB!SamCloseHandle` at `0x1800529df`
- `SAMLIB!SamCloseHandle` at `0x1800529ef`
- `SAMLIB!SamCloseHandle` at `0x180052a69`
- `SAMLIB!SamCloseHandle` at `0x180052aa3`
- `SAMLIB!SamCloseHandle` at `0x180052ab3`
- `SAMLIB!SamCloseHandle` at `0x180052b3b`
- `SAMLIB!SamCloseHandle` at `0x180052b75`
- `SAMLIB!SamCloseHandle` at `0x180052b85`
- `SAMLIB!SamCloseHandle` at `0x180052bb7`
- `SAMLIB!SamCloseHandle` at `0x180052bf1`
- `SAMLIB!SamCloseHandle` at `0x180052c01`
- `SAMLIB!SamConnect` at `0x1800527f7`
- `SAMLIB!SamConnect` at `0x1800527f7`
- `SAMLIB!SamFreeMemory` at `0x180052963`
- `SAMLIB!SamFreeMemory` at `0x180052982`
- `SAMLIB!SamFreeMemory` at `0x1800529ba`
- `SAMLIB!SamFreeMemory` at `0x1800529cf`
- `SAMLIB!SamFreeMemory` at `0x180052a7e`
- `SAMLIB!SamFreeMemory` at `0x180052a93`
- `SAMLIB!SamFreeMemory` at `0x180052b50`
- `SAMLIB!SamFreeMemory` at `0x180052b65`
- `SAMLIB!SamFreeMemory` at `0x180052bcc`
- `SAMLIB!SamFreeMemory` at `0x180052be1`
- `SAMLIB!SamFreeMemory` at `0x180052963`
- `SAMLIB!SamFreeMemory` at `0x180052982`
- `SAMLIB!SamFreeMemory` at `0x1800529ba`
- `SAMLIB!SamFreeMemory` at `0x1800529cf`
- `SAMLIB!SamFreeMemory` at `0x180052a7e`
- `SAMLIB!SamFreeMemory` at `0x180052a93`
- `SAMLIB!SamFreeMemory` at `0x180052b50`
- `SAMLIB!SamFreeMemory` at `0x180052b65`
- `SAMLIB!SamFreeMemory` at `0x180052bcc`
- `SAMLIB!SamFreeMemory` at `0x180052be1`
- `SAMLIB!SamSetInformationUser` at `0x180052b05`
- `SAMLIB!SamSetInformationUser` at `0x180052b05`
- `SAMLIB!SamOpenUser` at `0x180052a33`
- `SAMLIB!SamOpenUser` at `0x180052a33`
- `ntdll!RtlInitUnicodeString` at `0x1800528eb`
- `ntdll!RtlInitUnicodeString` at `0x1800528eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800527b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005283a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800528c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800529f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052abd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052b8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052c0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800527b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005283a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800528c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800529f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052abd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052b8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052c0b`

## string_xrefs

- `0x180052746`: `onecoreuap\windows\core\isoenvbroker\lib\v1\isolationenvironmentstatics.cpp`
- `0x180052797`: `onecoreuap\windows\core\isoenvbroker\lib\v1\isolationenvironmentstatics.cpp`
- `0x18005280e`: `onecoreuap\windows\core\isoenvbroker\lib\v1\isolationenvironmentstatics.cpp`
- `0x18005288c`: `onecoreuap\windows\core\isoenvbroker\lib\v1\isolationenvironmentstatics.cpp`
- `0x18005299a`: `onecoreuap\windows\core\isoenvbroker\lib\v1\isolationenvironmentstatics.cpp`
- `0x180052a4e`: `onecoreuap\windows\core\isoenvbroker\lib\v1\isolationenvironmentstatics.cpp`
- `0x180052b20`: `onecoreuap\windows\core\isoenvbroker\lib\v1\isolationenvironmentstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HideUserAccountFromLogonUI_0(struct _LSA_UNICODE_STRING *SourceString)
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
      (void *)0xB2,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v1\\isolationenvironmentstatics.cpp",
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
      (void *)0xB8,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v1\\isolationenvironmentstatics.cpp",
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
      (void *)0xC0,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v1\\isolationenvironmentstatics.cpp",
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
      (void *)0xC7,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v1\\isolationenvironmentstatics.cpp",
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
      (void *)0xD2,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v1\\isolationenvironmentstatics.cpp",
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
      (void *)0xD9,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v1\\isolationenvironmentstatics.cpp",
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
      (void *)0xE1,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v1\\isolationenvironmentstatics.cpp",
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
0x1800526c0  mov     [rsp-8+arg_8], rbx
0x1800526c5  mov     [rsp-8+arg_10], rsi
0x1800526ca  push    rbp
0x1800526cb  push    rdi
0x1800526cc  push    r12
0x1800526ce  push    r14
0x1800526d0  push    r15
0x1800526d2  lea     rbp, [rsp-0A0h]
0x1800526da  sub     rsp, 1A0h
0x1800526e1  mov     rax, cs:__security_cookie
0x1800526e8  xor     rax, rsp
0x1800526eb  mov     [rbp+0C0h+var_30], rax
0x1800526f2  mov     r14, rcx
0x1800526f5  xor     r15d, r15d
0x1800526f8  mov     qword ptr [rbp+0C0h+ObjectAttributes.Length], 30h ; '0'
0x180052700  mov     qword ptr [rbp+0C0h+ObjectAttributes.Attributes], r15
0x180052704  lea     esi, [r15+30h]
0x180052708  mov     [rbp+0C0h+ObjectAttributes.RootDirectory], r15
0x18005270c  mov     [rbp+0C0h+ObjectAttributes.ObjectName], r15
0x180052710  xorps   xmm0, xmm0
0x180052713  movdqu  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180052718  mov     [rsp+1C0h+PolicyHandle], r15
0x18005271d  lea     r9, [rsp+1C0h+PolicyHandle]; PolicyHandle
0x180052722  lea     r8d, [r15+1]; DesiredAccess
0x180052726  lea     rdx, [rbp+0C0h+ObjectAttributes]; ObjectAttributes
0x18005272a  call    LsaOpenPolicy
0x18005272f  mov     ebx, eax
0x180052731  mov     r12d, 10000000h
0x180052737  or      ebx, r12d
0x18005273a  jge     short loc_18005276F
0x18005273c  mov     rcx, [rbp+0C8h]; this
0x180052743  mov     r9d, ebx; char *
0x180052746  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005274d  mov     edx, 0B2h; void *
0x180052752  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052757  nop
0x180052758  mov     rcx, [rsp+1C0h+PolicyHandle]; ObjectHandle
0x18005275d  test    rcx, rcx
0x180052760  jz      short loc_180052768
0x180052762  call    LsaClose
0x180052767  nop
0x180052768  mov     eax, ebx
0x18005276a  jmp     loc_180052C22
0x18005276f  mov     [rsp+1C0h+Buffer], r15
0x180052774  lea     r8, [rsp+1C0h+Buffer]; Buffer
0x180052779  mov     rdi, [rsp+1C0h+PolicyHandle]
0x18005277e  mov     rcx, rdi; PolicyHandle
0x180052781  call    LsaQueryInformationPolicy
0x180052786  mov     ebx, eax
0x180052788  or      ebx, r12d
0x18005278b  jge     short loc_1800527CA
0x18005278d  mov     rcx, [rbp+0C8h]; this
0x180052794  mov     r9d, ebx; char *
0x180052797  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005279e  mov     edx, 0B8h; void *
0x1800527a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800527a8  nop
0x1800527a9  mov     rcx, [rsp+1C0h+Buffer]; hMem
0x1800527ae  test    rcx, rcx
0x1800527b1  jz      short loc_1800527BA
0x1800527b3  call    cs:__imp_LocalFree
0x1800527b9  nop
0x1800527ba  test    rdi, rdi
0x1800527bd  jz      short loc_180052768
0x1800527bf  mov     rcx, rdi; ObjectHandle
0x1800527c2  call    LsaClose
0x1800527c7  nop
0x1800527c8  jmp     short loc_180052768
0x1800527ca  mov     [rbp+0C0h+ObjectAttributes.Length], esi
0x1800527cd  mov     [rbp+0C0h+ObjectAttributes.RootDirectory], r15
0x1800527d1  mov     [rbp+0C0h+ObjectAttributes.Attributes], r15d
0x1800527d5  mov     [rbp+0C0h+ObjectAttributes.ObjectName], r15
0x1800527d9  xorps   xmm0, xmm0
0x1800527dc  movdqu  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800527e1  mov     [rsp+1C0h+var_178], r15
0x1800527e6  lea     r9, [rbp+0C0h+ObjectAttributes]
0x1800527ea  mov     r8d, 20h ; ' '
0x1800527f0  lea     rdx, [rsp+1C0h+var_178]
0x1800527f5  xor     ecx, ecx
0x1800527f7  call    cs:__imp_SamConnect
0x1800527fd  mov     ebx, eax
0x1800527ff  or      ebx, r12d
0x180052802  jge     short loc_180052858
0x180052804  mov     rcx, [rbp+0C8h]; this
0x18005280b  mov     r9d, ebx; char *
0x18005280e  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180052815  mov     edx, 0C0h; void *
0x18005281a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005281f  mov     rcx, [rsp+1C0h+var_178]
0x180052824  test    rcx, rcx
0x180052827  jz      short loc_180052830
0x180052829  call    cs:__imp_SamCloseHandle
0x18005282f  nop
0x180052830  mov     rcx, [rsp+1C0h+Buffer]; hMem
0x180052835  test    rcx, rcx
0x180052838  jz      short loc_180052841
0x18005283a  call    cs:__imp_LocalFree
0x180052840  nop
0x180052841  test    rdi, rdi
0x180052844  jz      loc_180052768
0x18005284a  mov     rcx, rdi; ObjectHandle
0x18005284d  call    LsaClose
0x180052852  nop
0x180052853  jmp     loc_180052768
0x180052858  mov     [rsp+1C0h+var_180], r15
0x18005285d  lea     r9, [rsp+1C0h+var_180]
0x180052862  mov     rbx, [rsp+1C0h+Buffer]
0x180052867  mov     r8, [rbx+10h]
0x18005286b  mov     edx, 2000000h
0x180052870  mov     rcx, [rsp+1C0h+var_178]
0x180052875  call    cs:__imp_SamOpenDomain
0x18005287b  mov     esi, eax
0x18005287d  or      esi, r12d
0x180052880  jge     short loc_1800528DD
0x180052882  mov     rcx, [rbp+0C8h]; this
0x180052889  mov     r9d, esi; char *
0x18005288c  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180052893  mov     edx, 0C7h; void *
0x180052898  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005289d  mov     rcx, [rsp+1C0h+var_180]
0x1800528a2  test    rcx, rcx
0x1800528a5  jz      short loc_1800528AD
0x1800528a7  call    cs:__imp_SamCloseHandle
0x1800528ad  mov     rcx, [rsp+1C0h+var_178]
0x1800528b2  test    rcx, rcx
0x1800528b5  jz      short loc_1800528BE
0x1800528b7  call    cs:__imp_SamCloseHandle
0x1800528bd  nop
0x1800528be  mov     rcx, rbx; hMem
0x1800528c1  call    cs:__imp_LocalFree
0x1800528c7  nop
0x1800528c8  test    rdi, rdi
0x1800528cb  jz      short loc_1800528D6
0x1800528cd  mov     rcx, rdi; ObjectHandle
0x1800528d0  call    LsaClose
0x1800528d5  nop
0x1800528d6  mov     eax, esi
0x1800528d8  jmp     loc_180052C22
0x1800528dd  xorps   xmm0, xmm0
0x1800528e0  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm0
0x1800528e4  mov     rdx, r14; SourceString
0x1800528e7  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x1800528eb  call    cs:__imp_RtlInitUnicodeString
0x1800528f1  mov     [rsp+1C0h+var_190], r15
0x1800528f6  mov     [rsp+1C0h+var_188], r15
0x1800528fb  lea     rax, [rsp+1C0h+var_188]
0x180052900  mov     [rbp+0C0h+var_140], rax
0x180052904  mov     qword ptr [rbp+0C0h+var_138], r15
0x180052908  mov     [rbp+0C0h+var_130], 1
0x18005290c  lea     rax, [rsp+1C0h+var_190]
0x180052911  mov     [rsp+1C0h+var_158], rax
0x180052916  mov     [rsp+1C0h+var_150], r15
0x18005291b  mov     [rsp+1C0h+var_148], 1
0x180052920  lea     rax, [rbp+0C0h+var_138]
0x180052924  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x180052929  lea     r9, [rsp+1C0h+var_150]
0x18005292e  lea     r8, [rbp+0C0h+DestinationString]
0x180052932  mov     edx, 1
0x180052937  mov     rcx, [rsp+1C0h+var_180]
0x18005293c  call    cs:__imp_SamLookupNamesInDomain
0x180052942  mov     esi, eax
0x180052944  or      esi, r12d
0x180052947  cmp     [rsp+1C0h+var_148], r15b
0x18005294c  jz      short loc_180052969
0x18005294e  mov     rdx, [rsp+1C0h+var_158]
0x180052953  mov     rcx, [rdx]
0x180052956  mov     rax, [rsp+1C0h+var_150]
0x18005295b  mov     [rdx], rax
0x18005295e  test    rcx, rcx
0x180052961  jz      short loc_180052969
0x180052963  call    cs:__imp_SamFreeMemory
0x180052969  cmp     [rbp+0C0h+var_130], r15b
0x18005296d  jz      short loc_180052988
0x18005296f  mov     rdx, [rbp+0C0h+var_140]
0x180052973  mov     rcx, [rdx]
0x180052976  mov     rax, qword ptr [rbp+0C0h+var_138]
0x18005297a  mov     [rdx], rax
0x18005297d  test    rcx, rcx
0x180052980  jz      short loc_180052988
0x180052982  call    cs:__imp_SamFreeMemory
0x180052988  test    esi, esi
0x18005298a  jns     loc_180052A17
0x180052990  mov     rcx, [rbp+0C8h]; this
0x180052997  mov     r9d, esi; char *
0x18005299a  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800529a1  mov     edx, 0D2h; void *
0x1800529a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800529ab  mov     rcx, [rsp+1C0h+var_188]
0x1800529b0  mov     [rsp+1C0h+var_188], r15
0x1800529b5  test    rcx, rcx
0x1800529b8  jz      short loc_1800529C0
0x1800529ba  call    cs:__imp_SamFreeMemory
0x1800529c0  mov     rcx, [rsp+1C0h+var_190]
0x1800529c5  mov     [rsp+1C0h+var_190], r15
0x1800529ca  test    rcx, rcx
0x1800529cd  jz      short loc_1800529D5
0x1800529cf  call    cs:__imp_SamFreeMemory
0x1800529d5  mov     rcx, [rsp+1C0h+var_180]
0x1800529da  test    rcx, rcx
0x1800529dd  jz      short loc_1800529E5
0x1800529df  call    cs:__imp_SamCloseHandle
0x1800529e5  mov     rcx, [rsp+1C0h+var_178]
0x1800529ea  test    rcx, rcx
0x1800529ed  jz      short loc_1800529F6
0x1800529ef  call    cs:__imp_SamCloseHandle
0x1800529f5  nop
0x1800529f6  mov     rcx, rbx; hMem
0x1800529f9  call    cs:__imp_LocalFree
0x1800529ff  nop
0x180052a00  test    rdi, rdi
0x180052a03  jz      loc_1800528D6
0x180052a09  mov     rcx, rdi; ObjectHandle
0x180052a0c  call    LsaClose
0x180052a11  nop
0x180052a12  jmp     loc_1800528D6
0x180052a17  mov     [rsp+1C0h+var_170], r15
0x180052a1c  lea     r9, [rsp+1C0h+var_170]
0x180052a21  mov     r8, [rsp+1C0h+var_190]
0x180052a26  mov     r8d, [r8]
0x180052a29  mov     edx, 2000000h
0x180052a2e  mov     rcx, [rsp+1C0h+var_180]
0x180052a33  call    cs:__imp_SamOpenUser
0x180052a39  mov     esi, eax
0x180052a3b  or      esi, r12d
0x180052a3e  jge     loc_180052ADB
0x180052a44  mov     rcx, [rbp+0C8h]; this
0x180052a4b  mov     r9d, esi; char *
0x180052a4e  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180052a55  mov     edx, 0D9h; void *
0x180052a5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052a5f  mov     rcx, [rsp+1C0h+var_170]
0x180052a64  test    rcx, rcx
0x180052a67  jz      short loc_180052A6F
0x180052a69  call    cs:__imp_SamCloseHandle
0x180052a6f  mov     rcx, [rsp+1C0h+var_188]
0x180052a74  mov     [rsp+1C0h+var_188], r15
0x180052a79  test    rcx, rcx
0x180052a7c  jz      short loc_180052A84
0x180052a7e  call    cs:__imp_SamFreeMemory
0x180052a84  mov     rcx, [rsp+1C0h+var_190]
0x180052a89  mov     [rsp+1C0h+var_190], r15
0x180052a8e  test    rcx, rcx
0x180052a91  jz      short loc_180052A99
0x180052a93  call    cs:__imp_SamFreeMemory
0x180052a99  mov     rcx, [rsp+1C0h+var_180]
0x180052a9e  test    rcx, rcx
0x180052aa1  jz      short loc_180052AA9
0x180052aa3  call    cs:__imp_SamCloseHandle
0x180052aa9  mov     rcx, [rsp+1C0h+var_178]
0x180052aae  test    rcx, rcx
0x180052ab1  jz      short loc_180052ABA
0x180052ab3  call    cs:__imp_SamCloseHandle
0x180052ab9  nop
0x180052aba  mov     rcx, rbx; hMem
0x180052abd  call    cs:__imp_LocalFree
0x180052ac3  nop
0x180052ac4  test    rdi, rdi
0x180052ac7  jz      loc_1800528D6
0x180052acd  mov     rcx, rdi; ObjectHandle
0x180052ad0  call    LsaClose
0x180052ad5  nop
0x180052ad6  jmp     loc_1800528D6
0x180052adb  xor     edx, edx; Val
0x180052add  mov     r8d, 0A8h; Size
0x180052ae3  lea     rcx, [rbp+0C0h+var_E0]; void *
0x180052ae7  call    memset_0
0x180052aec  mov     [rbp+0C0h+var_E0], 4000h
0x180052af3  mov     [rbp+0C0h+var_B8], 1
0x180052af7  lea     r8, [rbp+0C0h+var_E0]
0x180052afb  mov     edx, 1Ch
0x180052b00  mov     rcx, [rsp+1C0h+var_170]
0x180052b05  call    cs:__imp_SamSetInformationUser
0x180052b0b  mov     esi, eax
0x180052b0d  or      esi, r12d
0x180052b10  jge     loc_180052BAD
0x180052b16  mov     rcx, [rbp+0C8h]; this
0x180052b1d  mov     r9d, esi; char *
0x180052b20  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180052b27  mov     edx, 0E1h; void *
0x180052b2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052b31  mov     rcx, [rsp+1C0h+var_170]
0x180052b36  test    rcx, rcx
0x180052b39  jz      short loc_180052B41
0x180052b3b  call    cs:__imp_SamCloseHandle
0x180052b41  mov     rcx, [rsp+1C0h+var_188]
0x180052b46  mov     [rsp+1C0h+var_188], r15
0x180052b4b  test    rcx, rcx
0x180052b4e  jz      short loc_180052B56
0x180052b50  call    cs:__imp_SamFreeMemory
0x180052b56  mov     rcx, [rsp+1C0h+var_190]
0x180052b5b  mov     [rsp+1C0h+var_190], r15
0x180052b60  test    rcx, rcx
0x180052b63  jz      short loc_180052B6B
0x180052b65  call    cs:__imp_SamFreeMemory
0x180052b6b  mov     rcx, [rsp+1C0h+var_180]
0x180052b70  test    rcx, rcx
0x180052b73  jz      short loc_180052B7B
0x180052b75  call    cs:__imp_SamCloseHandle
0x180052b7b  mov     rcx, [rsp+1C0h+var_178]
0x180052b80  test    rcx, rcx
  ... truncated ...
```
