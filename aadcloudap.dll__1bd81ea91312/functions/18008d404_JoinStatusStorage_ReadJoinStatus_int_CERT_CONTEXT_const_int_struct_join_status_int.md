# JoinStatusStorage::ReadJoinStatus(int,_CERT_CONTEXT const *,int,struct_join_status *,int)

- ea: `0x18008d404`
- end: `0x18008d75a`
- name: `?ReadJoinStatus@JoinStatusStorage@@SAJHPEBU_CERT_CONTEXT@@HPEAUstruct_join_status@@H@Z`
- size: `854`
- prototype: `__int64 __fastcall(int, const struct _CERT_CONTEXT *, int, struct struct_join_status *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1800883b0`

## callees

- `0x1800871b4`
- `0x180087468`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`
- `0x18008c6fc`
- `0x18008cde4`
- `0x18008d02c`
- `0x18008d404`
- `0x18008d760`
- `0x180090378`
- `0x1800909c4`
- `0x180092250`
- `0x1800924b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008d715`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008d71f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008d715`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008d71f`

## string_xrefs

- `0x18008d474`: `JoinStatusStorage::ReadJoinStatus`
- `0x18008d498`: `JoinStatusStorage::ReadJoinStatus`
- `0x18008d4b2`: `JoinStatusStorage::ReadJoinStatus`
- `0x18008d4d4`: `JoinStatusStorage::ReadJoinStatus`
- `0x18008d50c`: `JoinStatusStorage::ReadJoinStatus`
- `0x18008d565`: `JoinStatusStorage::ReadJoinStatus`
- `0x18008d5ac`: `JoinStatusStorage::ReadJoinStatus`
- `0x18008d5ff`: `JoinStatusStorage::ReadJoinStatus`
- `0x18008d656`: `JoinStatusStorage::ReadJoinStatus`
- `0x18008d6ab`: `JoinStatusStorage::ReadJoinStatus`
- `0x18008d6ef`: `JoinStatusStorage::ReadJoinStatus`
- `0x18008d728`: `JoinStatusStorage::ReadJoinStatus`
- `0x18008d55e`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18008d6a4`: `RegistryPath::Append`
- `0x18008d5a2`: `JoinStatusStorage::ReadDeviceKey`
- `0x18008d6e5`: `JoinStatusStorage::ReadTenantKey`

## pseudocode

```c
__int64 __fastcall JoinStatusStorage::ReadJoinStatus(int a1, const struct _CERT_CONTEXT *a2, int a3, void **a4, int a5)
{
  const wchar_t *v9; // r14
  const wchar_t *v10; // r12
  signed int DeviceKey; // ebx
  const unsigned __int16 *v12; // rdx
  int DeviceId; // eax
  const unsigned __int16 *v14; // r8
  int ExistingDeviceKeyPath; // eax
  const wchar_t *v16; // rax
  const unsigned __int16 *v17; // rcx
  const wchar_t *v18; // rax
  unsigned __int16 *v19; // rcx
  const wchar_t *v20; // rax
  unsigned int v21; // eax
  int TenantKey; // eax
  void *Block; // [rsp+30h] [rbp-41h] BYREF
  _QWORD v25[4]; // [rsp+40h] [rbp-31h] BYREF
  __int128 v26; // [rsp+60h] [rbp-11h]
  __int64 v27; // [rsp+70h] [rbp-1h]
  __int64 v28; // [rsp+78h] [rbp+7h]
  unsigned __int16 *v29; // [rsp+D8h] [rbp+67h] BYREF

  Block = 0;
  v29 = 0;
  memset(v25, 0, sizeof(v25));
  v9 = L"TRUE";
  v26 = 0;
  v10 = L"TRUE";
  v27 = 0;
  if ( !a1 )
    v10 = L"FALSE";
  v28 = 0;
  Logger::TraceVerbose(L"%s started. %s: %s.", L"JoinStatusStorage::ReadJoinStatus", L"isDevice", v10);
  if ( !a2 )
  {
    DeviceKey = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"JoinStatusStorage::ReadJoinStatus", L"pCert");
    v12 = L"pCert";
LABEL_5:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"JoinStatusStorage::ReadJoinStatus", v12);
    goto LABEL_36;
  }
  if ( !a4 )
  {
    DeviceKey = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"JoinStatusStorage::ReadJoinStatus", L"pJoinStatus");
    v12 = L"pJoinStatus";
    goto LABEL_5;
  }
  DeviceId = RegistrationCertStatus::GetDeviceId(a2, (unsigned __int16 **)&Block);
  DeviceKey = DeviceId;
  if ( DeviceId < 0 )
  {
    v14 = L"RegistrationCertStatus::GetDeviceId";
LABEL_10:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"JoinStatusStorage::ReadJoinStatus",
      v14,
      (unsigned int)DeviceId);
    goto LABEL_36;
  }
  DeviceId = RegistrationCertStatus::GetTenantId(a2, &v29, 0);
  DeviceKey = DeviceId;
  if ( DeviceId < 0 )
  {
    v14 = L"RegistrationCertStatus::GetTenantId";
    goto LABEL_10;
  }
  ExistingDeviceKeyPath = JoinStatusStorage::GetExistingDeviceKeyPath(a1, a2, (struct RegistryPath *)v25);
  DeviceKey = ExistingDeviceKeyPath;
  if ( ExistingDeviceKeyPath >= 0 )
  {
    DeviceKey = JoinStatusStorage::ReadDeviceKey((struct struct_join_status *)a4, (struct RegistryPath *)v25, a3);
    if ( DeviceKey >= 0 )
      goto LABEL_19;
    v16 = L"TRUE";
    if ( !a3 )
      v16 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"JoinStatusStorage::ReadJoinStatus",
      L"JoinStatusStorage::ReadDeviceKey",
      (unsigned int)DeviceKey,
      v16);
    if ( a3 )
    {
LABEL_19:
      SafeFree(*a4);
      v17 = (const unsigned __int16 *)Block;
      *a4 = 0;
      DeviceKey = StringDup(v17, (unsigned __int16 **)a4, 0);
      if ( DeviceKey >= 0 )
        goto LABEL_23;
      v18 = L"TRUE";
      if ( !a3 )
        v18 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"JoinStatusStorage::ReadJoinStatus",
        L"StringDup",
        (unsigned int)DeviceKey,
        v18);
      if ( a3 )
      {
LABEL_23:
        SafeFree(a4[2]);
        v19 = v29;
        a4[2] = 0;
        DeviceKey = StringDup(v19, (unsigned __int16 **)a4 + 2, 0);
        if ( DeviceKey >= 0 )
          goto LABEL_27;
        v20 = L"TRUE";
        if ( !a3 )
          v20 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"JoinStatusStorage::ReadJoinStatus",
          L"StringDup",
          (unsigned int)DeviceKey,
          v20);
        if ( a3 )
        {
LABEL_27:
          RegistryPath::Pop((RegistryPath *)v25, 2);
          v21 = RegistryPath::Append((RegistryPath *)v25, L"TenantInfo", v29);
          DeviceKey = v21;
          if ( v21 )
          {
            Logger::TraceError(
              L"%s: %s failed with win32 error code: 0x%08x.",
              L"JoinStatusStorage::ReadJoinStatus",
              L"RegistryPath::Append",
              v21);
            if ( DeviceKey > 0 )
              DeviceKey = (unsigned __int16)DeviceKey | 0x80070000;
          }
          else
          {
            TenantKey = JoinStatusStorage::ReadTenantKey(
                          (struct struct_join_status *)a4,
                          (struct RegistryPath *)v25,
                          a5);
            DeviceKey = TenantKey;
            if ( TenantKey >= 0 )
              goto LABEL_34;
            if ( !a3 )
              v9 = L"FALSE";
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
              L"JoinStatusStorage::ReadJoinStatus",
              L"JoinStatusStorage::ReadTenantKey",
              (unsigned int)TenantKey,
              v9);
            if ( a3 )
            {
LABEL_34:
              if ( a3 )
                DeviceKey = 0;
            }
          }
        }
      }
    }
  }
  else
  {
    Logger::TraceError(
      L"%s: %s(%s) failed with error code: 0x%08x.",
      L"JoinStatusStorage::ReadJoinStatus",
      L"JoinStatusStorage::GetExistingDeviceKeyPath",
      v10,
      ExistingDeviceKeyPath);
  }
LABEL_36:
  free(Block);
  free(v29);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"JoinStatusStorage::ReadJoinStatus", (unsigned int)DeviceKey);
  RegistryPath::Reset((RegistryPath *)v25);
  return (unsigned int)DeviceKey;
}

```

## disassembly

```asm
0x18008d404  push    rbp
0x18008d406  push    rbx
0x18008d407  push    rsi
0x18008d408  push    rdi
0x18008d409  push    r12
0x18008d40b  push    r13
0x18008d40d  push    r14
0x18008d40f  push    r15
0x18008d411  lea     rbp, [rsp-17h]
0x18008d416  sub     rsp, 88h
0x18008d41d  xor     ebx, ebx
0x18008d41f  lea     rax, aFalse_0; "FALSE"
0x18008d426  test    ecx, ecx
0x18008d428  mov     [rbp+4Fh+Block], rbx
0x18008d42c  mov     rsi, r9
0x18008d42f  mov     [rbp+4Fh+arg_8], rbx
0x18008d433  mov     edi, r8d
0x18008d436  mov     [rbp+4Fh+var_80], rbx
0x18008d43a  mov     r15, rdx
0x18008d43d  mov     [rbp+4Fh+var_78], rbx
0x18008d441  mov     r13d, ecx
0x18008d444  mov     [rbp+4Fh+var_70], rbx
0x18008d448  xorps   xmm0, xmm0
0x18008d44b  mov     [rbp+4Fh+var_68], rbx
0x18008d44f  lea     r14, aTrue_0; "TRUE"
0x18008d456  movdqa  [rbp+4Fh+var_60], xmm0
0x18008d45b  mov     r12, r14
0x18008d45e  mov     [rbp+4Fh+var_50], rbx
0x18008d462  cmovz   r12, rax
0x18008d466  mov     [rbp+4Fh+var_48], rbx
0x18008d46a  mov     r9, r12
0x18008d46d  lea     r8, aIsdevice; "isDevice"
0x18008d474  lea     rdx, aJoinstatusstor_5; "JoinStatusStorage::ReadJoinStatus"
0x18008d47b  lea     rcx, aSStartedSS; "%s started. %s: %s."
0x18008d482  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18008d487  test    r15, r15
0x18008d48a  jnz     short loc_18008D4C3
0x18008d48c  lea     r8, aPcert; "pCert"
0x18008d493  mov     ebx, 80070057h
0x18008d498  lea     rdx, aJoinstatusstor_5; "JoinStatusStorage::ReadJoinStatus"
0x18008d49f  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008d4a6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d4ab  lea     rdx, aPcert; "pCert"
0x18008d4b2  lea     rcx, aJoinstatusstor_5; "JoinStatusStorage::ReadJoinStatus"
0x18008d4b9  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18008d4be  jmp     loc_18008D711
0x18008d4c3  test    rsi, rsi
0x18008d4c6  jnz     short loc_18008D4F0
0x18008d4c8  lea     r8, aPjoinstatus; "pJoinStatus"
0x18008d4cf  mov     ebx, 80070057h
0x18008d4d4  lea     rdx, aJoinstatusstor_5; "JoinStatusStorage::ReadJoinStatus"
0x18008d4db  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008d4e2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d4e7  lea     rdx, aPjoinstatus; "pJoinStatus"
0x18008d4ee  jmp     short loc_18008D4B2
0x18008d4f0  lea     rdx, [rbp+4Fh+Block]; unsigned __int16 **
0x18008d4f4  mov     rcx, r15; struct _CERT_CONTEXT *
0x18008d4f7  call    ?GetDeviceId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; RegistrationCertStatus::GetDeviceId(_CERT_CONTEXT const *,ushort * *)
0x18008d4fc  mov     ebx, eax
0x18008d4fe  test    eax, eax
0x18008d500  jns     short loc_18008D524
0x18008d502  lea     r8, aRegistrationce_8; "RegistrationCertStatus::GetDeviceId"
0x18008d509  mov     r9d, eax
0x18008d50c  lea     rdx, aJoinstatusstor_5; "JoinStatusStorage::ReadJoinStatus"
0x18008d513  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18008d51a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d51f  jmp     loc_18008D711
0x18008d524  xor     r8d, r8d; int *
0x18008d527  lea     rdx, [rbp+4Fh+arg_8]; unsigned __int16 **
0x18008d52b  mov     rcx, r15; struct _CERT_CONTEXT *
0x18008d52e  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x18008d533  mov     ebx, eax
0x18008d535  test    eax, eax
0x18008d537  jns     short loc_18008D542
0x18008d539  lea     r8, aRegistrationce_7; "RegistrationCertStatus::GetTenantId"
0x18008d540  jmp     short loc_18008D509
0x18008d542  lea     r8, [rbp+4Fh+var_80]; struct RegistryPath *
0x18008d546  mov     rdx, r15; struct _CERT_CONTEXT *
0x18008d549  mov     ecx, r13d; int
0x18008d54c  call    ?GetExistingDeviceKeyPath@JoinStatusStorage@@CAJHPEBU_CERT_CONTEXT@@AEAVRegistryPath@@@Z; JoinStatusStorage::GetExistingDeviceKeyPath(int,_CERT_CONTEXT const *,RegistryPath &)
0x18008d551  mov     ebx, eax
0x18008d553  test    eax, eax
0x18008d555  jns     short loc_18008D57D
0x18008d557  mov     r9, r12
0x18008d55a  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18008d55e  lea     r8, aJoinstatusstor_6; "JoinStatusStorage::GetExistingDeviceKey"...
0x18008d565  lea     rdx, aJoinstatusstor_5; "JoinStatusStorage::ReadJoinStatus"
0x18008d56c  lea     rcx, aSSSFailedWithE; "%s: %s(%s) failed with error code: 0x%0"...
0x18008d573  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d578  jmp     loc_18008D711
0x18008d57d  mov     r8d, edi; int
0x18008d580  lea     rdx, [rbp+4Fh+var_80]; struct RegistryPath *
0x18008d584  mov     rcx, rsi; struct struct_join_status *
0x18008d587  call    ?ReadDeviceKey@JoinStatusStorage@@CAJPEAUstruct_join_status@@AEAVRegistryPath@@H@Z; JoinStatusStorage::ReadDeviceKey(struct_join_status *,RegistryPath &,int)
0x18008d58c  lea     r15, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x18008d593  mov     ebx, eax
0x18008d595  lea     r12, aFalse_0; "FALSE"
0x18008d59c  test    eax, eax
0x18008d59e  jns     short loc_18008D5CF
0x18008d5a0  test    edi, edi
0x18008d5a2  lea     r8, aJoinstatusstor; "JoinStatusStorage::ReadDeviceKey"
0x18008d5a9  mov     rax, r14
0x18008d5ac  lea     rdx, aJoinstatusstor_5; "JoinStatusStorage::ReadJoinStatus"
0x18008d5b3  cmovz   rax, r12
0x18008d5b7  mov     r9d, ebx
0x18008d5ba  mov     rcx, r15; unsigned __int16 *
0x18008d5bd  mov     [rsp+0C0h+var_A0], rax
0x18008d5c2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d5c7  test    edi, edi
0x18008d5c9  jz      loc_18008D711
0x18008d5cf  mov     rcx, [rsi]; void *
0x18008d5d2  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d5d7  mov     rcx, [rbp+4Fh+Block]; unsigned __int16 *
0x18008d5db  xor     r8d, r8d; int
0x18008d5de  mov     rdx, rsi; unsigned __int16 **
0x18008d5e1  mov     qword ptr [rsi], 0
0x18008d5e8  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18008d5ed  mov     ebx, eax
0x18008d5ef  test    eax, eax
0x18008d5f1  jns     short loc_18008D622
0x18008d5f3  test    edi, edi
0x18008d5f5  lea     r8, aStringdup; "StringDup"
0x18008d5fc  mov     rax, r14
0x18008d5ff  lea     rdx, aJoinstatusstor_5; "JoinStatusStorage::ReadJoinStatus"
0x18008d606  cmovz   rax, r12
0x18008d60a  mov     r9d, ebx
0x18008d60d  mov     rcx, r15; unsigned __int16 *
0x18008d610  mov     [rsp+0C0h+var_A0], rax
0x18008d615  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d61a  test    edi, edi
0x18008d61c  jz      loc_18008D711
0x18008d622  lea     rbx, [rsi+10h]
0x18008d626  mov     rcx, [rbx]; void *
0x18008d629  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d62e  mov     rcx, [rbp+4Fh+arg_8]; unsigned __int16 *
0x18008d632  xor     r8d, r8d; int
0x18008d635  mov     rdx, rbx; unsigned __int16 **
0x18008d638  mov     qword ptr [rbx], 0
0x18008d63f  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18008d644  mov     ebx, eax
0x18008d646  test    eax, eax
0x18008d648  jns     short loc_18008D679
0x18008d64a  test    edi, edi
0x18008d64c  lea     r8, aStringdup; "StringDup"
0x18008d653  mov     rax, r14
0x18008d656  lea     rdx, aJoinstatusstor_5; "JoinStatusStorage::ReadJoinStatus"
0x18008d65d  cmovz   rax, r12
0x18008d661  mov     r9d, ebx
0x18008d664  mov     rcx, r15; unsigned __int16 *
0x18008d667  mov     [rsp+0C0h+var_A0], rax
0x18008d66c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d671  test    edi, edi
0x18008d673  jz      loc_18008D711
0x18008d679  mov     edx, 2; int
0x18008d67e  lea     rcx, [rbp+4Fh+var_80]; this
0x18008d682  call    ?Pop@RegistryPath@@QEAAHH@Z; RegistryPath::Pop(int)
0x18008d687  mov     r8, [rbp+4Fh+arg_8]; unsigned __int16 *
0x18008d68b  lea     rdx, aTenantinfo; "TenantInfo"
0x18008d692  lea     rcx, [rbp+4Fh+var_80]; this
0x18008d696  call    ?Append@RegistryPath@@QEAAKPEBG0@Z; RegistryPath::Append(ushort const *,ushort const *)
0x18008d69b  mov     ebx, eax
0x18008d69d  test    eax, eax
0x18008d69f  jz      short loc_18008D6CD
0x18008d6a1  mov     r9d, eax
0x18008d6a4  lea     r8, aRegistrypathAp; "RegistryPath::Append"
0x18008d6ab  lea     rdx, aJoinstatusstor_5; "JoinStatusStorage::ReadJoinStatus"
0x18008d6b2  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18008d6b9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d6be  test    ebx, ebx
0x18008d6c0  jle     short loc_18008D711
0x18008d6c2  movzx   ebx, bx
0x18008d6c5  or      ebx, 80070000h
0x18008d6cb  jmp     short loc_18008D711
0x18008d6cd  mov     r8d, [rbp+4Fh+arg_20]; int
0x18008d6d1  lea     rdx, [rbp+4Fh+var_80]; this
0x18008d6d5  mov     rcx, rsi; struct struct_join_status *
0x18008d6d8  call    ?ReadTenantKey@JoinStatusStorage@@CAJPEAUstruct_join_status@@AEAVRegistryPath@@H@Z; JoinStatusStorage::ReadTenantKey(struct_join_status *,RegistryPath &,int)
0x18008d6dd  mov     ebx, eax
0x18008d6df  test    eax, eax
0x18008d6e1  jns     short loc_18008D70B
0x18008d6e3  test    edi, edi
0x18008d6e5  lea     r8, aJoinstatusstor_10; "JoinStatusStorage::ReadTenantKey"
0x18008d6ec  mov     r9d, eax
0x18008d6ef  lea     rdx, aJoinstatusstor_5; "JoinStatusStorage::ReadJoinStatus"
0x18008d6f6  cmovz   r14, r12
0x18008d6fa  mov     rcx, r15; unsigned __int16 *
0x18008d6fd  mov     [rsp+0C0h+var_A0], r14
0x18008d702  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d707  test    edi, edi
0x18008d709  jz      short loc_18008D711
0x18008d70b  test    edi, edi
0x18008d70d  jz      short loc_18008D711
0x18008d70f  xor     ebx, ebx
0x18008d711  mov     rcx, [rbp+4Fh+Block]; Block
0x18008d715  call    cs:__imp_free
0x18008d71b  mov     rcx, [rbp+4Fh+arg_8]; Block
0x18008d71f  call    cs:__imp_free
0x18008d725  mov     r8d, ebx
0x18008d728  lea     rdx, aJoinstatusstor_5; "JoinStatusStorage::ReadJoinStatus"
0x18008d72f  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18008d736  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18008d73b  lea     rcx, [rbp+4Fh+var_80]; this
0x18008d73f  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x18008d744  mov     eax, ebx
0x18008d746  add     rsp, 88h
0x18008d74d  pop     r15
0x18008d74f  pop     r14
0x18008d751  pop     r13
0x18008d753  pop     r12
0x18008d755  pop     rdi
0x18008d756  pop     rsi
0x18008d757  pop     rbx
0x18008d758  pop     rbp
0x18008d759  retn
```
