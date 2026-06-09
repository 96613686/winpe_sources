# CSqmManager::s_GetSkuAndDomain(CSqmManager::SWmsStaticTelemetryData *)

- ea: `0x140032c0c`
- end: `0x140032dfa`
- name: `?s_GetSkuAndDomain@CSqmManager@@CAJPEAUSWmsStaticTelemetryData@1@@Z`
- size: `494`
- prototype: `__int64 __fastcall(struct CSqmManager::SWmsStaticTelemetryData *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140031e98`

## callees

- `0x140032c0c`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140076208`

## import_xrefs

- `ADVAPI32!LsaOpenPolicy` at `0x140032c58`
- `ADVAPI32!LsaOpenPolicy` at `0x140032c58`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x140032d1f`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x140032d1f`
- `ADVAPI32!LsaFreeMemory` at `0x140032dcf`
- `ADVAPI32!LsaFreeMemory` at `0x140032dcf`
- `ADVAPI32!LsaClose` at `0x140032dde`
- `ADVAPI32!LsaClose` at `0x140032dde`
- `KERNEL32!IsDebuggerPresent` at `0x140032cab`
- `KERNEL32!IsDebuggerPresent` at `0x140032d6e`
- `KERNEL32!IsDebuggerPresent` at `0x140032cab`
- `KERNEL32!IsDebuggerPresent` at `0x140032d6e`

## pseudocode

```c
__int64 __fastcall CSqmManager::s_GetSkuAndDomain(struct CSqmManager::SWmsStaticTelemetryData *a1)
{
  NTSTATUS v2; // eax
  signed int IsConnector; // ebx
  __int64 v4; // r9
  __int64 v5; // r8
  NTSTATUS v6; // eax
  int *v7; // rdx
  unsigned int v8; // edi
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  int v11; // [rsp+A8h] [rbp+38h] BYREF
  PVOID Buffer; // [rsp+B0h] [rbp+40h] BYREF
  PVOID PolicyHandle; // [rsp+B8h] [rbp+48h] BYREF

  v11 = 0;
  PolicyHandle = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 0x80000001, &PolicyHandle);
  IsConnector = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      IsConnector = (unsigned __int16)v2 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
      0x291u,
      L"CSqmManager::s_GetSkuAndDomain",
      L"CBRAEx",
      L"status == ((NTSTATUS)0x00000000L)",
      IsConnector);
    if ( IsDebuggerPresent() )
    {
      v4 = 657;
LABEL_6:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
        v4,
        L"CSqmManager::s_GetSkuAndDomain",
        L"CBRAEx",
        L"status == ((NTSTATUS)0x00000000L)",
        IsConnector);
      goto LABEL_19;
    }
    v5 = 657;
LABEL_8:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
      v5,
      L"CSqmManager::s_GetSkuAndDomain",
      L"CBRAEx",
      L"status == ((NTSTATUS)0x00000000L)",
      IsConnector);
    goto LABEL_19;
  }
  v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, &Buffer);
  IsConnector = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      IsConnector = (unsigned __int16)v6 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
      0x296u,
      L"CSqmManager::s_GetSkuAndDomain",
      L"CBRAEx",
      L"status == ((NTSTATUS)0x00000000L)",
      IsConnector);
    if ( IsDebuggerPresent() )
    {
      v4 = 662;
      goto LABEL_6;
    }
    v5 = 662;
    goto LABEL_8;
  }
  v8 = *((_QWORD *)Buffer + 2) != 0 ? 2 : 0;
  IsConnector = PlatformSkuUtils::IsConnector((PlatformSkuUtils *)&v11, v7);
  if ( IsConnector >= 0 )
  {
    if ( v11 )
      ++v8;
    DEBUGMSG(L"CSqmManager::s_GetSkuAndDomain - Sku and Domain value 0x%x to SQM.\n", v8);
    *((_DWORD *)a1 + 4) = v8;
  }
LABEL_19:
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return (unsigned int)IsConnector;
}

```

## disassembly

```asm
0x140032c0c  mov     [rsp-28h+arg_0], rbx
0x140032c11  push    rbp
0x140032c12  push    rsi
0x140032c13  push    rdi
0x140032c14  push    r14
0x140032c16  push    r15
0x140032c18  mov     rbp, rsp
0x140032c1b  sub     rsp, 70h
0x140032c1f  xorps   xmm0, xmm0
0x140032c22  mov     [rbp+arg_8], 0
0x140032c29  mov     rsi, rcx
0x140032c2c  mov     [rbp+PolicyHandle], 0
0x140032c34  xor     ecx, ecx; SystemName
0x140032c36  mov     [rbp+Buffer], 0
0x140032c3e  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x140032c42  mov     r8d, 80000001h; DesiredAccess
0x140032c48  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x140032c4c  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140032c50  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140032c54  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140032c58  call    cs:__imp_LsaOpenPolicy
0x140032c5e  mov     ebx, eax
0x140032c60  test    eax, eax
0x140032c62  jz      loc_140032D12
0x140032c68  jle     short loc_140032C73
0x140032c6a  movzx   ebx, ax
0x140032c6d  or      ebx, 80070000h
0x140032c73  lea     r15, aCbraex; "CBRAEx"
0x140032c7a  mov     [rsp+70h+var_48], ebx; int
0x140032c7e  lea     rsi, aCsqmmanagerSGe_12; "CSqmManager::s_GetSkuAndDomain"
0x140032c85  mov     r9, r15; unsigned __int16 *
0x140032c88  lea     rdi, aTermsrvWmsSrcD_30; "termsrv\\wms\\src\\devices\\wmssvc\\sqm"...
0x140032c8f  mov     r8, rsi; unsigned __int16 *
0x140032c92  lea     r14, aStatusNtstatus_0; "status == ((NTSTATUS)0x00000000L)"
0x140032c99  mov     rcx, rdi; unsigned __int16 *
0x140032c9c  mov     edx, 291h; unsigned int
0x140032ca1  mov     [rsp+70h+var_50], r14; unsigned __int16 *
0x140032ca6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140032cab  call    cs:__imp_IsDebuggerPresent
0x140032cb1  test    eax, eax
0x140032cb3  jz      short loc_140032CE7
0x140032cb5  mov     r9d, 291h
0x140032cbb  mov     [rsp+70h+var_38], ebx
0x140032cbf  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140032cc6  mov     [rsp+70h+var_40], r14
0x140032ccb  mov     r8, rdi
0x140032cce  mov     qword ptr [rsp+70h+var_48], r15
0x140032cd3  mov     ecx, 2; unsigned __int8
0x140032cd8  mov     [rsp+70h+var_50], rsi
0x140032cdd  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140032ce2  jmp     loc_140032DC6
0x140032ce7  mov     r8d, 291h
0x140032ced  mov     dword ptr [rsp+70h+var_40], ebx
0x140032cf1  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140032cf8  mov     qword ptr [rsp+70h+var_48], r14
0x140032cfd  mov     r9, rsi
0x140032d00  mov     rdx, rdi
0x140032d03  mov     [rsp+70h+var_50], r15
0x140032d08  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140032d0d  jmp     loc_140032DC6
0x140032d12  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x140032d16  lea     r8, [rbp+Buffer]; Buffer
0x140032d1a  mov     edx, 3; InformationClass
0x140032d1f  call    cs:__imp_LsaQueryInformationPolicy
0x140032d25  mov     ebx, eax
0x140032d27  test    eax, eax
0x140032d29  jz      short loc_140032D8E
0x140032d2b  jle     short loc_140032D36
0x140032d2d  movzx   ebx, ax
0x140032d30  or      ebx, 80070000h
0x140032d36  lea     r15, aCbraex; "CBRAEx"
0x140032d3d  mov     [rsp+70h+var_48], ebx; int
0x140032d41  lea     rsi, aCsqmmanagerSGe_12; "CSqmManager::s_GetSkuAndDomain"
0x140032d48  mov     r9, r15; unsigned __int16 *
0x140032d4b  lea     rdi, aTermsrvWmsSrcD_30; "termsrv\\wms\\src\\devices\\wmssvc\\sqm"...
0x140032d52  mov     r8, rsi; unsigned __int16 *
0x140032d55  lea     r14, aStatusNtstatus_0; "status == ((NTSTATUS)0x00000000L)"
0x140032d5c  mov     rcx, rdi; unsigned __int16 *
0x140032d5f  mov     edx, 296h; unsigned int
0x140032d64  mov     [rsp+70h+var_50], r14; unsigned __int16 *
0x140032d69  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140032d6e  call    cs:__imp_IsDebuggerPresent
0x140032d74  test    eax, eax
0x140032d76  jz      short loc_140032D83
0x140032d78  mov     r9d, 296h
0x140032d7e  jmp     loc_140032CBB
0x140032d83  mov     r8d, 296h
0x140032d89  jmp     loc_140032CED
0x140032d8e  mov     rax, [rbp+Buffer]
0x140032d92  mov     rcx, [rax+10h]
0x140032d96  neg     rcx
0x140032d99  lea     rcx, [rbp+arg_8]; this
0x140032d9d  sbb     edi, edi
0x140032d9f  and     edi, 2
0x140032da2  call    ?IsConnector@PlatformSkuUtils@@YAJPEAH@Z; PlatformSkuUtils::IsConnector(int *)
0x140032da7  mov     ebx, eax
0x140032da9  test    eax, eax
0x140032dab  js      short loc_140032DC6
0x140032dad  cmp     [rbp+arg_8], 0
0x140032db1  jz      short loc_140032DB5
0x140032db3  inc     edi
0x140032db5  mov     edx, edi
0x140032db7  lea     rcx, aCsqmmanagerSGe_7; "CSqmManager::s_GetSkuAndDomain - Sku an"...
0x140032dbe  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140032dc3  mov     [rsi+10h], edi
0x140032dc6  mov     rcx, [rbp+Buffer]; Buffer
0x140032dca  test    rcx, rcx
0x140032dcd  jz      short loc_140032DD5
0x140032dcf  call    cs:__imp_LsaFreeMemory
0x140032dd5  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x140032dd9  test    rcx, rcx
0x140032ddc  jz      short loc_140032DE4
0x140032dde  call    cs:__imp_LsaClose
0x140032de4  mov     eax, ebx
0x140032de6  mov     rbx, [rsp+70h+arg_0]
0x140032dee  add     rsp, 70h
0x140032df2  pop     r15
0x140032df4  pop     r14
0x140032df6  pop     rdi
0x140032df7  pop     rsi
0x140032df8  pop     rbp
0x140032df9  retn
```
