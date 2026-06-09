# JoinStatusStorage::ReadJoinStatus(int,_CERT_CONTEXT const *,int,struct_join_status *,int)

- ea: `0x18007e3c8`
- end: `0x18007e70a`
- name: `?ReadJoinStatus@JoinStatusStorage@@SAJHPEBU_CERT_CONTEXT@@HPEAUstruct_join_status@@H@Z`
- size: `834`
- prototype: `__int64 __fastcall(int, const struct _CERT_CONTEXT *, int, struct struct_join_status *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18007ab58`

## callees

- `0x180007db4`
- `0x180079de0`
- `0x18007a058`
- `0x18007d1b8`
- `0x18007d22c`
- `0x18007d2a4`
- `0x18007d7ac`
- `0x18007ddc4`
- `0x18007dffc`
- `0x18007e3c8`
- `0x18007e710`
- `0x1800805c4`
- `0x180080754`
- `0x180081c48`
- `0x180081e1c`

## string_xrefs

- `0x18007e438`: `JoinStatusStorage::ReadJoinStatus`
- `0x18007e45c`: `JoinStatusStorage::ReadJoinStatus`
- `0x18007e476`: `JoinStatusStorage::ReadJoinStatus`
- `0x18007e498`: `JoinStatusStorage::ReadJoinStatus`
- `0x18007e4d0`: `JoinStatusStorage::ReadJoinStatus`
- `0x18007e529`: `JoinStatusStorage::ReadJoinStatus`
- `0x18007e570`: `JoinStatusStorage::ReadJoinStatus`
- `0x18007e5c0`: `JoinStatusStorage::ReadJoinStatus`
- `0x18007e614`: `JoinStatusStorage::ReadJoinStatus`
- `0x18007e65d`: `JoinStatusStorage::ReadJoinStatus`
- `0x18007e6a1`: `JoinStatusStorage::ReadJoinStatus`
- `0x18007e6d8`: `JoinStatusStorage::ReadJoinStatus`
- `0x18007e656`: `RegistryPath::Append`
- `0x18007e522`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18007e566`: `JoinStatusStorage::ReadDeviceKey`
- `0x18007e697`: `JoinStatusStorage::ReadTenantKey`

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
  int v18; // r8d
  const wchar_t *v19; // rax
  unsigned __int16 *v20; // rcx
  int v21; // r8d
  int v22; // edx
  const wchar_t *v23; // rax
  const unsigned __int16 *v24; // rdx
  unsigned int v25; // eax
  int TenantKey; // eax
  void *Block; // [rsp+30h] [rbp-41h] BYREF
  _QWORD v29[4]; // [rsp+40h] [rbp-31h] BYREF
  __int128 v30; // [rsp+60h] [rbp-11h]
  __int64 v31; // [rsp+70h] [rbp-1h]
  __int64 v32; // [rsp+78h] [rbp+7h]
  unsigned __int16 *v33; // [rsp+D8h] [rbp+67h] BYREF

  Block = 0;
  v33 = 0;
  memset(v29, 0, sizeof(v29));
  v9 = L"TRUE";
  v30 = 0;
  v10 = L"TRUE";
  v31 = 0;
  if ( !a1 )
    v10 = L"FALSE";
  v32 = 0;
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
  DeviceId = RegistrationCertStatus::GetTenantId(a2, &v33, 0);
  DeviceKey = DeviceId;
  if ( DeviceId < 0 )
  {
    v14 = L"RegistrationCertStatus::GetTenantId";
    goto LABEL_10;
  }
  ExistingDeviceKeyPath = JoinStatusStorage::GetExistingDeviceKeyPath(a1, a2, (struct RegistryPath *)v29);
  DeviceKey = ExistingDeviceKeyPath;
  if ( ExistingDeviceKeyPath >= 0 )
  {
    DeviceKey = JoinStatusStorage::ReadDeviceKey((struct struct_join_status *)a4, (struct RegistryPath *)v29, a3);
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
      DeviceKey = StringDup(v17, (unsigned __int16 **)a4, v18);
      if ( DeviceKey >= 0 )
        goto LABEL_23;
      v19 = L"TRUE";
      if ( !a3 )
        v19 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"JoinStatusStorage::ReadJoinStatus",
        L"StringDup",
        (unsigned int)DeviceKey,
        v19);
      if ( a3 )
      {
LABEL_23:
        SafeFree(a4[2]);
        v20 = v33;
        a4[2] = 0;
        DeviceKey = StringDup(v20, (unsigned __int16 **)a4 + 2, v21);
        if ( DeviceKey >= 0 )
          goto LABEL_27;
        v23 = L"TRUE";
        if ( !a3 )
          v23 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"JoinStatusStorage::ReadJoinStatus",
          L"StringDup",
          (unsigned int)DeviceKey,
          v23);
        if ( a3 )
        {
LABEL_27:
          RegistryPath::Pop((RegistryPath *)v29, v22);
          v25 = RegistryPath::Append((RegistryPath *)v29, v24, v33);
          DeviceKey = v25;
          if ( v25 )
          {
            Logger::TraceError(
              L"%s: %s failed with win32 error code: 0x%08x.",
              L"JoinStatusStorage::ReadJoinStatus",
              L"RegistryPath::Append",
              v25);
            if ( DeviceKey > 0 )
              DeviceKey = (unsigned __int16)DeviceKey | 0x80070000;
          }
          else
          {
            TenantKey = JoinStatusStorage::ReadTenantKey(
                          (struct struct_join_status *)a4,
                          (struct RegistryPath *)v29,
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
  operator delete(Block);
  operator delete(v33);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"JoinStatusStorage::ReadJoinStatus", (unsigned int)DeviceKey);
  RegistryPath::Reset((RegistryPath *)v29);
  return (unsigned int)DeviceKey;
}

```

## disassembly

```asm
0x18007e3c8  push    rbp
0x18007e3ca  push    rbx
0x18007e3cb  push    rsi
0x18007e3cc  push    rdi
0x18007e3cd  push    r12
0x18007e3cf  push    r13
0x18007e3d1  push    r14
0x18007e3d3  push    r15
0x18007e3d5  lea     rbp, [rsp-17h]
0x18007e3da  sub     rsp, 88h
0x18007e3e1  xor     ebx, ebx
0x18007e3e3  lea     rax, aFalse_0; "FALSE"
0x18007e3ea  test    ecx, ecx
0x18007e3ec  mov     [rbp+4Fh+Block], rbx
0x18007e3f0  mov     rsi, r9
0x18007e3f3  mov     [rbp+4Fh+arg_8], rbx
0x18007e3f7  mov     edi, r8d
0x18007e3fa  mov     [rbp+4Fh+var_80], rbx
0x18007e3fe  mov     r15, rdx
0x18007e401  mov     [rbp+4Fh+var_78], rbx
0x18007e405  mov     r13d, ecx
0x18007e408  mov     [rbp+4Fh+var_70], rbx
0x18007e40c  xorps   xmm0, xmm0
0x18007e40f  mov     [rbp+4Fh+var_68], rbx
0x18007e413  lea     r14, aTrue_0; "TRUE"
0x18007e41a  movdqa  [rbp+4Fh+var_60], xmm0
0x18007e41f  mov     r12, r14
0x18007e422  mov     [rbp+4Fh+var_50], rbx
0x18007e426  cmovz   r12, rax
0x18007e42a  mov     [rbp+4Fh+var_48], rbx
0x18007e42e  mov     r9, r12
0x18007e431  lea     r8, aIsdevice; "isDevice"
0x18007e438  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x18007e43f  lea     rcx, aSStartedSS; "%s started. %s: %s."
0x18007e446  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007e44b  test    r15, r15
0x18007e44e  jnz     short loc_18007E487
0x18007e450  lea     r8, aPcert; "pCert"
0x18007e457  mov     ebx, 80070057h
0x18007e45c  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x18007e463  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007e46a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e46f  lea     rdx, aPcert; "pCert"
0x18007e476  lea     rcx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x18007e47d  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007e482  jmp     loc_18007E6C3
0x18007e487  test    rsi, rsi
0x18007e48a  jnz     short loc_18007E4B4
0x18007e48c  lea     r8, aPjoinstatus; "pJoinStatus"
0x18007e493  mov     ebx, 80070057h
0x18007e498  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x18007e49f  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007e4a6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e4ab  lea     rdx, aPjoinstatus; "pJoinStatus"
0x18007e4b2  jmp     short loc_18007E476
0x18007e4b4  lea     rdx, [rbp+4Fh+Block]; unsigned __int16 **
0x18007e4b8  mov     rcx, r15; struct _CERT_CONTEXT *
0x18007e4bb  call    ?GetDeviceId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; RegistrationCertStatus::GetDeviceId(_CERT_CONTEXT const *,ushort * *)
0x18007e4c0  mov     ebx, eax
0x18007e4c2  test    eax, eax
0x18007e4c4  jns     short loc_18007E4E8
0x18007e4c6  lea     r8, aRegistrationce_4; "RegistrationCertStatus::GetDeviceId"
0x18007e4cd  mov     r9d, eax
0x18007e4d0  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x18007e4d7  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18007e4de  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e4e3  jmp     loc_18007E6C3
0x18007e4e8  xor     r8d, r8d; int *
0x18007e4eb  lea     rdx, [rbp+4Fh+arg_8]; unsigned __int16 **
0x18007e4ef  mov     rcx, r15; struct _CERT_CONTEXT *
0x18007e4f2  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x18007e4f7  mov     ebx, eax
0x18007e4f9  test    eax, eax
0x18007e4fb  jns     short loc_18007E506
0x18007e4fd  lea     r8, aRegistrationce_3; "RegistrationCertStatus::GetTenantId"
0x18007e504  jmp     short loc_18007E4CD
0x18007e506  lea     r8, [rbp+4Fh+var_80]; struct RegistryPath *
0x18007e50a  mov     rdx, r15; struct _CERT_CONTEXT *
0x18007e50d  mov     ecx, r13d; int
0x18007e510  call    ?GetExistingDeviceKeyPath@JoinStatusStorage@@CAJHPEBU_CERT_CONTEXT@@AEAVRegistryPath@@@Z; JoinStatusStorage::GetExistingDeviceKeyPath(int,_CERT_CONTEXT const *,RegistryPath &)
0x18007e515  mov     ebx, eax
0x18007e517  test    eax, eax
0x18007e519  jns     short loc_18007E541
0x18007e51b  mov     r9, r12
0x18007e51e  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18007e522  lea     r8, aJoinstatusstor_2; "JoinStatusStorage::GetExistingDeviceKey"...
0x18007e529  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x18007e530  lea     rcx, aSSSFailedWithE; "%s: %s(%s) failed with error code: 0x%0"...
0x18007e537  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e53c  jmp     loc_18007E6C3
0x18007e541  mov     r8d, edi; int
0x18007e544  lea     rdx, [rbp+4Fh+var_80]; struct RegistryPath *
0x18007e548  mov     rcx, rsi; struct struct_join_status *
0x18007e54b  call    ?ReadDeviceKey@JoinStatusStorage@@CAJPEAUstruct_join_status@@AEAVRegistryPath@@H@Z; JoinStatusStorage::ReadDeviceKey(struct_join_status *,RegistryPath &,int)
0x18007e550  lea     r15, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x18007e557  mov     ebx, eax
0x18007e559  lea     r12, aFalse_0; "FALSE"
0x18007e560  test    eax, eax
0x18007e562  jns     short loc_18007E593
0x18007e564  test    edi, edi
0x18007e566  lea     r8, aJoinstatusstor; "JoinStatusStorage::ReadDeviceKey"
0x18007e56d  mov     rax, r14
0x18007e570  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x18007e577  cmovz   rax, r12
0x18007e57b  mov     r9d, ebx
0x18007e57e  mov     rcx, r15; unsigned __int16 *
0x18007e581  mov     [rsp+0C0h+var_A0], rax
0x18007e586  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e58b  test    edi, edi
0x18007e58d  jz      loc_18007E6C3
0x18007e593  mov     rcx, [rsi]; void *
0x18007e596  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e59b  mov     rcx, [rbp+4Fh+Block]; unsigned __int16 *
0x18007e59f  mov     rdx, rsi; unsigned __int16 **
0x18007e5a2  mov     qword ptr [rsi], 0
0x18007e5a9  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18007e5ae  mov     ebx, eax
0x18007e5b0  test    eax, eax
0x18007e5b2  jns     short loc_18007E5E3
0x18007e5b4  test    edi, edi
0x18007e5b6  lea     r8, aStringdup; "StringDup"
0x18007e5bd  mov     rax, r14
0x18007e5c0  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x18007e5c7  cmovz   rax, r12
0x18007e5cb  mov     r9d, ebx
0x18007e5ce  mov     rcx, r15; unsigned __int16 *
0x18007e5d1  mov     [rsp+0C0h+var_A0], rax
0x18007e5d6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e5db  test    edi, edi
0x18007e5dd  jz      loc_18007E6C3
0x18007e5e3  lea     rbx, [rsi+10h]
0x18007e5e7  mov     rcx, [rbx]; void *
0x18007e5ea  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e5ef  mov     rcx, [rbp+4Fh+arg_8]; unsigned __int16 *
0x18007e5f3  mov     rdx, rbx; unsigned __int16 **
0x18007e5f6  mov     qword ptr [rbx], 0
0x18007e5fd  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18007e602  mov     ebx, eax
0x18007e604  test    eax, eax
0x18007e606  jns     short loc_18007E637
0x18007e608  test    edi, edi
0x18007e60a  lea     r8, aStringdup; "StringDup"
0x18007e611  mov     rax, r14
0x18007e614  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x18007e61b  cmovz   rax, r12
0x18007e61f  mov     r9d, ebx
0x18007e622  mov     rcx, r15; unsigned __int16 *
0x18007e625  mov     [rsp+0C0h+var_A0], rax
0x18007e62a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e62f  test    edi, edi
0x18007e631  jz      loc_18007E6C3
0x18007e637  lea     rcx, [rbp+4Fh+var_80]; this
0x18007e63b  call    ?Pop@RegistryPath@@QEAAHH@Z; RegistryPath::Pop(int)
0x18007e640  mov     r8, [rbp+4Fh+arg_8]; unsigned __int16 *
0x18007e644  lea     rcx, [rbp+4Fh+var_80]; this
0x18007e648  call    ?Append@RegistryPath@@QEAAKPEBG0@Z; RegistryPath::Append(ushort const *,ushort const *)
0x18007e64d  mov     ebx, eax
0x18007e64f  test    eax, eax
0x18007e651  jz      short loc_18007E67F
0x18007e653  mov     r9d, eax
0x18007e656  lea     r8, aRegistrypathAp; "RegistryPath::Append"
0x18007e65d  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x18007e664  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18007e66b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e670  test    ebx, ebx
0x18007e672  jle     short loc_18007E6C3
0x18007e674  movzx   ebx, bx
0x18007e677  or      ebx, 80070000h
0x18007e67d  jmp     short loc_18007E6C3
0x18007e67f  mov     r8d, [rbp+4Fh+arg_20]; int
0x18007e683  lea     rdx, [rbp+4Fh+var_80]; this
0x18007e687  mov     rcx, rsi; struct struct_join_status *
0x18007e68a  call    ?ReadTenantKey@JoinStatusStorage@@CAJPEAUstruct_join_status@@AEAVRegistryPath@@H@Z; JoinStatusStorage::ReadTenantKey(struct_join_status *,RegistryPath &,int)
0x18007e68f  mov     ebx, eax
0x18007e691  test    eax, eax
0x18007e693  jns     short loc_18007E6BD
0x18007e695  test    edi, edi
0x18007e697  lea     r8, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18007e69e  mov     r9d, eax
0x18007e6a1  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x18007e6a8  cmovz   r14, r12
0x18007e6ac  mov     rcx, r15; unsigned __int16 *
0x18007e6af  mov     [rsp+0C0h+var_A0], r14
0x18007e6b4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e6b9  test    edi, edi
0x18007e6bb  jz      short loc_18007E6C3
0x18007e6bd  test    edi, edi
0x18007e6bf  jz      short loc_18007E6C3
0x18007e6c1  xor     ebx, ebx
0x18007e6c3  mov     rcx, [rbp+4Fh+Block]; Block
0x18007e6c7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007e6cc  mov     rcx, [rbp+4Fh+arg_8]; Block
0x18007e6d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007e6d5  mov     r8d, ebx
0x18007e6d8  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x18007e6df  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18007e6e6  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007e6eb  lea     rcx, [rbp+4Fh+var_80]; this
0x18007e6ef  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x18007e6f4  mov     eax, ebx
0x18007e6f6  add     rsp, 88h
0x18007e6fd  pop     r15
0x18007e6ff  pop     r14
0x18007e701  pop     r13
0x18007e703  pop     r12
0x18007e705  pop     rdi
0x18007e706  pop     rsi
0x18007e707  pop     rbx
0x18007e708  pop     rbp
0x18007e709  retn
```
