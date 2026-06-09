# HideUserAccountFromLogonUI

- ea: `0x180044df4`
- end: `0x18004537f`
- name: `HideUserAccountFromLogonUI`
- size: `1419`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180041b64`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x18000a464`
- `0x180044df4`
- `0x180063980`
- `0x180063a08`
- `0x180063bf4`

## import_xrefs

- `SAMLIB!SamOpenDomain` at `0x180044fa7`
- `SAMLIB!SamOpenDomain` at `0x180044fa7`
- `SAMLIB!SamLookupNamesInDomain` at `0x18004506e`
- `SAMLIB!SamLookupNamesInDomain` at `0x18004506e`
- `SAMLIB!SamCloseHandle` at `0x180044f5b`
- `SAMLIB!SamCloseHandle` at `0x180044fd9`
- `SAMLIB!SamCloseHandle` at `0x180044fe9`
- `SAMLIB!SamCloseHandle` at `0x180045111`
- `SAMLIB!SamCloseHandle` at `0x180045121`
- `SAMLIB!SamCloseHandle` at `0x18004519b`
- `SAMLIB!SamCloseHandle` at `0x1800451d5`
- `SAMLIB!SamCloseHandle` at `0x1800451e5`
- `SAMLIB!SamCloseHandle` at `0x18004526d`
- `SAMLIB!SamCloseHandle` at `0x1800452a7`
- `SAMLIB!SamCloseHandle` at `0x1800452b7`
- `SAMLIB!SamCloseHandle` at `0x1800452e9`
- `SAMLIB!SamCloseHandle` at `0x180045323`
- `SAMLIB!SamCloseHandle` at `0x180045333`
- `SAMLIB!SamCloseHandle` at `0x180044f5b`
- `SAMLIB!SamCloseHandle` at `0x180044fd9`
- `SAMLIB!SamCloseHandle` at `0x180044fe9`
- `SAMLIB!SamCloseHandle` at `0x180045111`
- `SAMLIB!SamCloseHandle` at `0x180045121`
- `SAMLIB!SamCloseHandle` at `0x18004519b`
- `SAMLIB!SamCloseHandle` at `0x1800451d5`
- `SAMLIB!SamCloseHandle` at `0x1800451e5`
- `SAMLIB!SamCloseHandle` at `0x18004526d`
- `SAMLIB!SamCloseHandle` at `0x1800452a7`
- `SAMLIB!SamCloseHandle` at `0x1800452b7`
- `SAMLIB!SamCloseHandle` at `0x1800452e9`
- `SAMLIB!SamCloseHandle` at `0x180045323`
- `SAMLIB!SamCloseHandle` at `0x180045333`
- `SAMLIB!SamConnect` at `0x180044f29`
- `SAMLIB!SamConnect` at `0x180044f29`
- `SAMLIB!SamFreeMemory` at `0x180045095`
- `SAMLIB!SamFreeMemory` at `0x1800450b4`
- `SAMLIB!SamFreeMemory` at `0x1800450ec`
- `SAMLIB!SamFreeMemory` at `0x180045101`
- `SAMLIB!SamFreeMemory` at `0x1800451b0`
- `SAMLIB!SamFreeMemory` at `0x1800451c5`
- `SAMLIB!SamFreeMemory` at `0x180045282`
- `SAMLIB!SamFreeMemory` at `0x180045297`
- `SAMLIB!SamFreeMemory` at `0x1800452fe`
- `SAMLIB!SamFreeMemory` at `0x180045313`
- `SAMLIB!SamFreeMemory` at `0x180045095`
- `SAMLIB!SamFreeMemory` at `0x1800450b4`
- `SAMLIB!SamFreeMemory` at `0x1800450ec`
- `SAMLIB!SamFreeMemory` at `0x180045101`
- `SAMLIB!SamFreeMemory` at `0x1800451b0`
- `SAMLIB!SamFreeMemory` at `0x1800451c5`
- `SAMLIB!SamFreeMemory` at `0x180045282`
- `SAMLIB!SamFreeMemory` at `0x180045297`
- `SAMLIB!SamFreeMemory` at `0x1800452fe`
- `SAMLIB!SamFreeMemory` at `0x180045313`
- `SAMLIB!SamSetInformationUser` at `0x180045237`
- `SAMLIB!SamSetInformationUser` at `0x180045237`
- `SAMLIB!SamOpenUser` at `0x180045165`
- `SAMLIB!SamOpenUser` at `0x180045165`
- `ntdll!RtlInitUnicodeString` at `0x18004501d`
- `ntdll!RtlInitUnicodeString` at `0x18004501d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044ee5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044f6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044ff3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004512b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800451ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800452c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004533d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044ee5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044f6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044ff3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004512b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800451ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800452c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004533d`

## string_xrefs

- `0x180044e7a`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentaccounthelpers.cpp`
- `0x180044ec9`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentaccounthelpers.cpp`
- `0x180044f40`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentaccounthelpers.cpp`
- `0x180044fbe`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentaccounthelpers.cpp`
- `0x1800450cc`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentaccounthelpers.cpp`
- `0x180045180`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentaccounthelpers.cpp`
- `0x180045252`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentaccounthelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HideUserAccountFromLogonUI(struct _LSA_UNICODE_STRING *SourceString)
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
      (void *)0x35,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentaccounthelpers.cpp",
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
      (void *)0x3B,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentaccounthelpers.cpp",
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
      (void *)0x43,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentaccounthelpers.cpp",
      (const char *)v4,
      v24);
    if ( v28 )
      SamCloseHandle();
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
      (void *)0x4A,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentaccounthelpers.cpp",
      (const char *)v11,
      v24);
    if ( v27 )
      SamCloseHandle();
    if ( v28 )
      SamCloseHandle();
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
      SamFreeMemory();
  }
  if ( v37 )
  {
    v13 = *v35;
    *v35 = *(_QWORD *)v36;
    if ( v13 )
      SamFreeMemory();
  }
  if ( (v11 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentaccounthelpers.cpp",
      (const char *)v11,
      (int)v36);
    v14 = v26;
    v26 = 0;
    if ( v14 )
      SamFreeMemory();
    v15 = v25;
    v25 = 0;
    if ( v15 )
      SamFreeMemory();
    if ( v27 )
      SamCloseHandle();
    if ( v28 )
      SamCloseHandle();
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
      (void *)0x5C,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentaccounthelpers.cpp",
      (const char *)v11,
      (int)v36);
    if ( v29 )
      SamCloseHandle();
    v17 = v26;
    v26 = 0;
    if ( v17 )
      SamFreeMemory();
    v18 = v25;
    v25 = 0;
    if ( v18 )
      SamFreeMemory();
    if ( v27 )
      SamCloseHandle();
    if ( v28 )
      SamCloseHandle();
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
      (void *)0x64,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentaccounthelpers.cpp",
      (const char *)v11,
      (int)v36);
    if ( v29 )
      SamCloseHandle();
    v20 = v26;
    v26 = 0;
    if ( v20 )
      SamFreeMemory();
    v21 = v25;
    v25 = 0;
    if ( v21 )
      SamFreeMemory();
    if ( v27 )
      SamCloseHandle();
    if ( v28 )
      SamCloseHandle();
    LocalFree(v9);
    if ( !v6 )
      return v11;
LABEL_67:
    LsaClose(v6);
    return v11;
  }
  if ( v29 )
    SamCloseHandle();
  v22 = v26;
  v26 = 0;
  if ( v22 )
    SamFreeMemory();
  v23 = v25;
  v25 = 0;
  if ( v23 )
    SamFreeMemory();
  if ( v27 )
    SamCloseHandle();
  if ( v28 )
    SamCloseHandle();
  LocalFree(v9);
  if ( v6 )
    LsaClose(v6);
  return 0;
}

```

## disassembly

```asm
0x180044df4  mov     [rsp-8+arg_8], rbx
0x180044df9  mov     [rsp-8+arg_10], rsi
0x180044dfe  push    rbp
0x180044dff  push    rdi
0x180044e00  push    r12
0x180044e02  push    r14
0x180044e04  push    r15
0x180044e06  lea     rbp, [rsp-0A0h]
0x180044e0e  sub     rsp, 1A0h
0x180044e15  mov     rax, cs:__security_cookie
0x180044e1c  xor     rax, rsp
0x180044e1f  mov     [rbp+0C0h+var_30], rax
0x180044e26  mov     r14, rcx
0x180044e29  xor     r15d, r15d
0x180044e2c  mov     qword ptr [rbp+0C0h+ObjectAttributes.Length], 30h ; '0'
0x180044e34  mov     qword ptr [rbp+0C0h+ObjectAttributes.Attributes], r15
0x180044e38  lea     esi, [r15+30h]
0x180044e3c  mov     [rbp+0C0h+ObjectAttributes.RootDirectory], r15
0x180044e40  mov     [rbp+0C0h+ObjectAttributes.ObjectName], r15
0x180044e44  xorps   xmm0, xmm0
0x180044e47  movdqu  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180044e4c  mov     [rsp+1C0h+PolicyHandle], r15
0x180044e51  lea     r9, [rsp+1C0h+PolicyHandle]; PolicyHandle
0x180044e56  lea     r8d, [r15+1]; DesiredAccess
0x180044e5a  lea     rdx, [rbp+0C0h+ObjectAttributes]; ObjectAttributes
0x180044e5e  call    LsaOpenPolicy
0x180044e63  mov     ebx, eax
0x180044e65  mov     r12d, 10000000h
0x180044e6b  or      ebx, r12d
0x180044e6e  jge     short loc_180044EA1
0x180044e70  mov     rcx, [rbp+0C8h]; this
0x180044e77  mov     r9d, ebx; char *
0x180044e7a  lea     r8, aOnecoreuapWind_30; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180044e81  lea     edx, [rsi+5]; void *
0x180044e84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044e89  nop
0x180044e8a  mov     rcx, [rsp+1C0h+PolicyHandle]; ObjectHandle
0x180044e8f  test    rcx, rcx
0x180044e92  jz      short loc_180044E9A
0x180044e94  call    LsaClose
0x180044e99  nop
0x180044e9a  mov     eax, ebx
0x180044e9c  jmp     loc_180045354
0x180044ea1  mov     [rsp+1C0h+Buffer], r15
0x180044ea6  lea     r8, [rsp+1C0h+Buffer]; Buffer
0x180044eab  mov     rdi, [rsp+1C0h+PolicyHandle]
0x180044eb0  mov     rcx, rdi; PolicyHandle
0x180044eb3  call    LsaQueryInformationPolicy
0x180044eb8  mov     ebx, eax
0x180044eba  or      ebx, r12d
0x180044ebd  jge     short loc_180044EFC
0x180044ebf  mov     rcx, [rbp+0C8h]; this
0x180044ec6  mov     r9d, ebx; char *
0x180044ec9  lea     r8, aOnecoreuapWind_30; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180044ed0  mov     edx, 3Bh ; ';'; void *
0x180044ed5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044eda  nop
0x180044edb  mov     rcx, [rsp+1C0h+Buffer]; hMem
0x180044ee0  test    rcx, rcx
0x180044ee3  jz      short loc_180044EEC
0x180044ee5  call    cs:__imp_LocalFree
0x180044eeb  nop
0x180044eec  test    rdi, rdi
0x180044eef  jz      short loc_180044E9A
0x180044ef1  mov     rcx, rdi; ObjectHandle
0x180044ef4  call    LsaClose
0x180044ef9  nop
0x180044efa  jmp     short loc_180044E9A
0x180044efc  mov     [rbp+0C0h+ObjectAttributes.Length], esi
0x180044eff  mov     [rbp+0C0h+ObjectAttributes.RootDirectory], r15
0x180044f03  mov     [rbp+0C0h+ObjectAttributes.Attributes], r15d
0x180044f07  mov     [rbp+0C0h+ObjectAttributes.ObjectName], r15
0x180044f0b  xorps   xmm0, xmm0
0x180044f0e  movdqu  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180044f13  mov     [rsp+1C0h+var_178], r15
0x180044f18  lea     r9, [rbp+0C0h+ObjectAttributes]
0x180044f1c  mov     r8d, 20h ; ' '
0x180044f22  lea     rdx, [rsp+1C0h+var_178]
0x180044f27  xor     ecx, ecx
0x180044f29  call    cs:__imp_SamConnect
0x180044f2f  mov     ebx, eax
0x180044f31  or      ebx, r12d
0x180044f34  jge     short loc_180044F8A
0x180044f36  mov     rcx, [rbp+0C8h]; this
0x180044f3d  mov     r9d, ebx; char *
0x180044f40  lea     r8, aOnecoreuapWind_30; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180044f47  mov     edx, 43h ; 'C'; void *
0x180044f4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044f51  mov     rcx, [rsp+1C0h+var_178]
0x180044f56  test    rcx, rcx
0x180044f59  jz      short loc_180044F62
0x180044f5b  call    cs:__imp_SamCloseHandle
0x180044f61  nop
0x180044f62  mov     rcx, [rsp+1C0h+Buffer]; hMem
0x180044f67  test    rcx, rcx
0x180044f6a  jz      short loc_180044F73
0x180044f6c  call    cs:__imp_LocalFree
0x180044f72  nop
0x180044f73  test    rdi, rdi
0x180044f76  jz      loc_180044E9A
0x180044f7c  mov     rcx, rdi; ObjectHandle
0x180044f7f  call    LsaClose
0x180044f84  nop
0x180044f85  jmp     loc_180044E9A
0x180044f8a  mov     [rsp+1C0h+var_180], r15
0x180044f8f  lea     r9, [rsp+1C0h+var_180]
0x180044f94  mov     rbx, [rsp+1C0h+Buffer]
0x180044f99  mov     r8, [rbx+10h]
0x180044f9d  mov     edx, 2000000h
0x180044fa2  mov     rcx, [rsp+1C0h+var_178]
0x180044fa7  call    cs:__imp_SamOpenDomain
0x180044fad  mov     esi, eax
0x180044faf  or      esi, r12d
0x180044fb2  jge     short loc_18004500F
0x180044fb4  mov     rcx, [rbp+0C8h]; this
0x180044fbb  mov     r9d, esi; char *
0x180044fbe  lea     r8, aOnecoreuapWind_30; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180044fc5  mov     edx, 4Ah ; 'J'; void *
0x180044fca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044fcf  mov     rcx, [rsp+1C0h+var_180]
0x180044fd4  test    rcx, rcx
0x180044fd7  jz      short loc_180044FDF
0x180044fd9  call    cs:__imp_SamCloseHandle
0x180044fdf  mov     rcx, [rsp+1C0h+var_178]
0x180044fe4  test    rcx, rcx
0x180044fe7  jz      short loc_180044FF0
0x180044fe9  call    cs:__imp_SamCloseHandle
0x180044fef  nop
0x180044ff0  mov     rcx, rbx; hMem
0x180044ff3  call    cs:__imp_LocalFree
0x180044ff9  nop
0x180044ffa  test    rdi, rdi
0x180044ffd  jz      short loc_180045008
0x180044fff  mov     rcx, rdi; ObjectHandle
0x180045002  call    LsaClose
0x180045007  nop
0x180045008  mov     eax, esi
0x18004500a  jmp     loc_180045354
0x18004500f  xorps   xmm0, xmm0
0x180045012  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm0
0x180045016  mov     rdx, r14; SourceString
0x180045019  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x18004501d  call    cs:__imp_RtlInitUnicodeString
0x180045023  mov     [rsp+1C0h+var_190], r15
0x180045028  mov     [rsp+1C0h+var_188], r15
0x18004502d  lea     rax, [rsp+1C0h+var_188]
0x180045032  mov     [rbp+0C0h+var_140], rax
0x180045036  mov     qword ptr [rbp+0C0h+var_138], r15
0x18004503a  mov     [rbp+0C0h+var_130], 1
0x18004503e  lea     rax, [rsp+1C0h+var_190]
0x180045043  mov     [rsp+1C0h+var_158], rax
0x180045048  mov     [rsp+1C0h+var_150], r15
0x18004504d  mov     [rsp+1C0h+var_148], 1
0x180045052  lea     rax, [rbp+0C0h+var_138]
0x180045056  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x18004505b  lea     r9, [rsp+1C0h+var_150]
0x180045060  lea     r8, [rbp+0C0h+DestinationString]
0x180045064  mov     edx, 1
0x180045069  mov     rcx, [rsp+1C0h+var_180]
0x18004506e  call    cs:__imp_SamLookupNamesInDomain
0x180045074  mov     esi, eax
0x180045076  or      esi, r12d
0x180045079  cmp     [rsp+1C0h+var_148], r15b
0x18004507e  jz      short loc_18004509B
0x180045080  mov     rdx, [rsp+1C0h+var_158]
0x180045085  mov     rcx, [rdx]
0x180045088  mov     rax, [rsp+1C0h+var_150]
0x18004508d  mov     [rdx], rax
0x180045090  test    rcx, rcx
0x180045093  jz      short loc_18004509B
0x180045095  call    cs:__imp_SamFreeMemory
0x18004509b  cmp     [rbp+0C0h+var_130], r15b
0x18004509f  jz      short loc_1800450BA
0x1800450a1  mov     rdx, [rbp+0C0h+var_140]
0x1800450a5  mov     rcx, [rdx]
0x1800450a8  mov     rax, qword ptr [rbp+0C0h+var_138]
0x1800450ac  mov     [rdx], rax
0x1800450af  test    rcx, rcx
0x1800450b2  jz      short loc_1800450BA
0x1800450b4  call    cs:__imp_SamFreeMemory
0x1800450ba  test    esi, esi
0x1800450bc  jns     loc_180045149
0x1800450c2  mov     rcx, [rbp+0C8h]; this
0x1800450c9  mov     r9d, esi; char *
0x1800450cc  lea     r8, aOnecoreuapWind_30; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800450d3  mov     edx, 55h ; 'U'; void *
0x1800450d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800450dd  mov     rcx, [rsp+1C0h+var_188]
0x1800450e2  mov     [rsp+1C0h+var_188], r15
0x1800450e7  test    rcx, rcx
0x1800450ea  jz      short loc_1800450F2
0x1800450ec  call    cs:__imp_SamFreeMemory
0x1800450f2  mov     rcx, [rsp+1C0h+var_190]
0x1800450f7  mov     [rsp+1C0h+var_190], r15
0x1800450fc  test    rcx, rcx
0x1800450ff  jz      short loc_180045107
0x180045101  call    cs:__imp_SamFreeMemory
0x180045107  mov     rcx, [rsp+1C0h+var_180]
0x18004510c  test    rcx, rcx
0x18004510f  jz      short loc_180045117
0x180045111  call    cs:__imp_SamCloseHandle
0x180045117  mov     rcx, [rsp+1C0h+var_178]
0x18004511c  test    rcx, rcx
0x18004511f  jz      short loc_180045128
0x180045121  call    cs:__imp_SamCloseHandle
0x180045127  nop
0x180045128  mov     rcx, rbx; hMem
0x18004512b  call    cs:__imp_LocalFree
0x180045131  nop
0x180045132  test    rdi, rdi
0x180045135  jz      loc_180045008
0x18004513b  mov     rcx, rdi; ObjectHandle
0x18004513e  call    LsaClose
0x180045143  nop
0x180045144  jmp     loc_180045008
0x180045149  mov     [rsp+1C0h+var_170], r15
0x18004514e  lea     r9, [rsp+1C0h+var_170]
0x180045153  mov     r8, [rsp+1C0h+var_190]
0x180045158  mov     r8d, [r8]
0x18004515b  mov     edx, 2000000h
0x180045160  mov     rcx, [rsp+1C0h+var_180]
0x180045165  call    cs:__imp_SamOpenUser
0x18004516b  mov     esi, eax
0x18004516d  or      esi, r12d
0x180045170  jge     loc_18004520D
0x180045176  mov     rcx, [rbp+0C8h]; this
0x18004517d  mov     r9d, esi; char *
0x180045180  lea     r8, aOnecoreuapWind_30; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180045187  mov     edx, 5Ch ; '\'; void *
0x18004518c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045191  mov     rcx, [rsp+1C0h+var_170]
0x180045196  test    rcx, rcx
0x180045199  jz      short loc_1800451A1
0x18004519b  call    cs:__imp_SamCloseHandle
0x1800451a1  mov     rcx, [rsp+1C0h+var_188]
0x1800451a6  mov     [rsp+1C0h+var_188], r15
0x1800451ab  test    rcx, rcx
0x1800451ae  jz      short loc_1800451B6
0x1800451b0  call    cs:__imp_SamFreeMemory
0x1800451b6  mov     rcx, [rsp+1C0h+var_190]
0x1800451bb  mov     [rsp+1C0h+var_190], r15
0x1800451c0  test    rcx, rcx
0x1800451c3  jz      short loc_1800451CB
0x1800451c5  call    cs:__imp_SamFreeMemory
0x1800451cb  mov     rcx, [rsp+1C0h+var_180]
0x1800451d0  test    rcx, rcx
0x1800451d3  jz      short loc_1800451DB
0x1800451d5  call    cs:__imp_SamCloseHandle
0x1800451db  mov     rcx, [rsp+1C0h+var_178]
0x1800451e0  test    rcx, rcx
0x1800451e3  jz      short loc_1800451EC
0x1800451e5  call    cs:__imp_SamCloseHandle
0x1800451eb  nop
0x1800451ec  mov     rcx, rbx; hMem
0x1800451ef  call    cs:__imp_LocalFree
0x1800451f5  nop
0x1800451f6  test    rdi, rdi
0x1800451f9  jz      loc_180045008
0x1800451ff  mov     rcx, rdi; ObjectHandle
0x180045202  call    LsaClose
0x180045207  nop
0x180045208  jmp     loc_180045008
0x18004520d  xor     edx, edx; Val
0x18004520f  mov     r8d, 0A8h; Size
0x180045215  lea     rcx, [rbp+0C0h+var_E0]; void *
0x180045219  call    memset_0
0x18004521e  mov     [rbp+0C0h+var_E0], 4000h
0x180045225  mov     [rbp+0C0h+var_B8], 1
0x180045229  lea     r8, [rbp+0C0h+var_E0]
0x18004522d  mov     edx, 1Ch
0x180045232  mov     rcx, [rsp+1C0h+var_170]
0x180045237  call    cs:__imp_SamSetInformationUser
0x18004523d  mov     esi, eax
0x18004523f  or      esi, r12d
0x180045242  jge     loc_1800452DF
0x180045248  mov     rcx, [rbp+0C8h]; this
0x18004524f  mov     r9d, esi; char *
0x180045252  lea     r8, aOnecoreuapWind_30; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180045259  mov     edx, 64h ; 'd'; void *
0x18004525e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045263  mov     rcx, [rsp+1C0h+var_170]
0x180045268  test    rcx, rcx
0x18004526b  jz      short loc_180045273
0x18004526d  call    cs:__imp_SamCloseHandle
0x180045273  mov     rcx, [rsp+1C0h+var_188]
0x180045278  mov     [rsp+1C0h+var_188], r15
0x18004527d  test    rcx, rcx
0x180045280  jz      short loc_180045288
0x180045282  call    cs:__imp_SamFreeMemory
0x180045288  mov     rcx, [rsp+1C0h+var_190]
0x18004528d  mov     [rsp+1C0h+var_190], r15
0x180045292  test    rcx, rcx
0x180045295  jz      short loc_18004529D
0x180045297  call    cs:__imp_SamFreeMemory
0x18004529d  mov     rcx, [rsp+1C0h+var_180]
0x1800452a2  test    rcx, rcx
0x1800452a5  jz      short loc_1800452AD
0x1800452a7  call    cs:__imp_SamCloseHandle
0x1800452ad  mov     rcx, [rsp+1C0h+var_178]
0x1800452b2  test    rcx, rcx
  ... truncated ...
```
