# WerKernelSubmitReport

- ea: `0x140058c20`
- end: `0x140059209`
- name: `WerKernelSubmitReport`
- size: `1513`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x1400809b8`

## callees

- `0x1400588d8`
- `0x140058c20`
- `0x140059210`
- `0x140059350`
- `0x140059418`
- `0x140059690`
- `0x1400596b4`
- `0x1400597d4`
- `0x140059970`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!ZwQuerySystemInformation` at `0x140058f0a`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140058f0a`
- `ntoskrnl!DbgPrintEx` at `0x140058d19`
- `ntoskrnl!DbgPrintEx` at `0x140058e17`
- `ntoskrnl!DbgPrintEx` at `0x140058e41`
- `ntoskrnl!DbgPrintEx` at `0x14005915d`
- `ntoskrnl!DbgPrintEx` at `0x140059189`
- `ntoskrnl!DbgPrintEx` at `0x140058d19`
- `ntoskrnl!DbgPrintEx` at `0x140058e17`
- `ntoskrnl!DbgPrintEx` at `0x140058e41`
- `ntoskrnl!DbgPrintEx` at `0x14005915d`
- `ntoskrnl!DbgPrintEx` at `0x140059189`
- `ntoskrnl!RtlInitUnicodeString` at `0x140058ea3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140058ea3`
- `ntoskrnl!ZwClose` at `0x140058d40`
- `ntoskrnl!ZwClose` at `0x1400591a7`
- `ntoskrnl!ZwClose` at `0x1400591cf`
- `ntoskrnl!ZwClose` at `0x140058d40`
- `ntoskrnl!ZwClose` at `0x1400591a7`
- `ntoskrnl!ZwClose` at `0x1400591cf`
- `ntoskrnl!ZwQueryKey` at `0x140058d68`
- `ntoskrnl!ZwQueryKey` at `0x140058ded`
- `ntoskrnl!ZwQueryKey` at `0x140058d68`
- `ntoskrnl!ZwQueryKey` at `0x140058ded`
- `ntoskrnl!ZwAlpcSendWaitReceivePort` at `0x140059127`
- `ntoskrnl!ZwAlpcSendWaitReceivePort` at `0x140059127`
- `ntoskrnl!ZwDeleteKey` at `0x140058d2f`
- `ntoskrnl!ZwDeleteKey` at `0x140058d2f`
- `ntoskrnl!ZwAlpcConnectPort` at `0x140058fef`
- `ntoskrnl!ZwAlpcConnectPort` at `0x140058fef`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140058da9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140058da9`

## string_xrefs

- `0x140058d07`: `WERLIVEKERNELREPORTING:%u: ERROR WerpGetRegistryKey failed for the busy key 0x%x\n`
- `0x140058e98`: `\WindowsErrorReportingServicePort`
- `0x14005908e`: `WERLIVEKERNELREPORTING:%u: ERROR StringCchCopy failed for key with 0x%x\n`
- `0x1400590cd`: `WERLIVEKERNELREPORTING:%u: ERROR StringCchCopy failed for id with 0x%x\n`
- `0x14005914f`: `WERLIVEKERNELREPORTING:%u: ERROR Service returned failure\n`

## pseudocode

```c
__int64 __fastcall WerKernelSubmitReport(HANDLE KeyHandle)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  NTSTATUS RegistryKey; // eax
  int v6; // ebx
  __int64 v7; // r9
  const CHAR *v8; // r8
  size_t v9; // rbx
  _DWORD *PoolWithTag; // rax
  _DWORD *v11; // rdi
  NTSTATUS started; // eax
  __int64 v13; // r9
  const CHAR *v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  char v18; // dl
  __int64 *v19; // rsi
  size_t v20; // r9
  size_t v21; // r9
  int v22; // eax
  PULONG ResultLength; // [rsp+20h] [rbp-E0h]
  PULONG ResultLengtha; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+30h] [rbp-D0h]
  int v27; // [rsp+38h] [rbp-C8h]
  int v28; // [rsp+40h] [rbp-C0h]
  int v29; // [rsp+48h] [rbp-B8h]
  ULONG Length; // [rsp+60h] [rbp-A0h] BYREF
  size_t cchToCopy; // [rsp+64h] [rbp-9Ch] BYREF
  HANDLE KeyHandlea; // [rsp+70h] [rbp-90h] BYREF
  __int64 SystemInformation; // [rsp+78h] [rbp-88h] BYREF
  __int64 v34; // [rsp+80h] [rbp-80h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp-78h] BYREF
  __int64 v36; // [rsp+90h] [rbp-70h] BYREF
  STRSAFE_PCNZWCH pszSrc; // [rsp+98h] [rbp-68h] BYREF
  STRSAFE_PCNZWCH v38; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v40[48]; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-20h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v43[10]; // [rsp+100h] [rbp+0h] BYREF
  _DWORD v44[352]; // [rsp+150h] [rbp+50h] BYREF
  _DWORD v45[352]; // [rsp+6D0h] [rbp+5D0h] BYREF

  Handle = 0;
  memset(v44, 0, 0x578u);
  memset(v45, 0, 0x578u);
  v39 = 0;
  v34 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v36 = 0;
  Length = 0;
  pszSrc = 0;
  DestinationString = 0;
  v38 = 0;
  memset(v40, 0, 44);
  cchToCopy = 0;
  KeyHandlea = 0;
  memset(v43, 0, 0x48u);
  SystemInformation = 0;
  if ( !KeyHandle )
    return 3221225485LL;
  RegistryKey = WerpGetRegistryKey(KeyHandle, v2, v3, &KeyHandlea);
  v6 = RegistryKey;
  if ( RegistryKey >= 0 )
  {
    ZwDeleteKey(KeyHandlea);
    ZwClose(KeyHandlea);
    KeyHandlea = 0;
    RegistryKey = ZwQueryKey(KeyHandle, KeyNameInformation, 0, 0, &Length);
    v6 = RegistryKey;
    if ( RegistryKey != -2147483643 && RegistryKey != -1073741789 )
    {
      v7 = 1001;
      v8 = "WERLIVEKERNELREPORTING:%u: ERROR ZwQueryKey failed while determining the size with 0x%x\n";
      goto LABEL_5;
    }
    v9 = (int)Length;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, (int)Length, 0x7765726Bu);
    v11 = PoolWithTag;
    if ( ExPoolZeroingNativelySupported )
    {
      if ( PoolWithTag )
      {
LABEL_12:
        started = ZwQueryKey(KeyHandle, KeyNameInformation, v11, Length, &Length);
        v6 = started;
        if ( started >= 0 )
        {
          started = WerpParseKeyName(
                      (int)v11 + 4,
                      *v11 >> 1,
                      (unsigned int)&pszSrc,
                      (unsigned int)&cchToCopy,
                      (__int64)&v38,
                      (__int64)&cchToCopy + 4);
          v6 = started;
          if ( started >= 0 )
          {
            RtlInitUnicodeString(&DestinationString, L"\\WindowsErrorReportingServicePort");
            memset(v43, 0, 0x48u);
            v43[2] = 1400;
            v6 = WerpAllocateAndInitializeSid(
                   &IdentifierAuthority,
                   v15,
                   v16,
                   v17,
                   (int)ResultLengtha,
                   v25,
                   v26,
                   v27,
                   v28,
                   v29,
                   &v34);
            if ( v6 < 0 )
              goto LABEL_51;
            started = WerStartSystemErrorHandler();
            v6 = started;
            if ( started >= 0 )
            {
              started = ZwQuerySystemInformation(SystemErrorPortTimeouts, &SystemInformation, 8u, 0);
              v6 = started;
              if ( started >= 0 )
              {
                started = WerWaitForSystemErrorHandler((unsigned int)SystemInformation);
                v6 = started;
                if ( started >= 0 )
                {
                  if ( started == 258 )
                  {
                    started = -1073740973;
                    v14 = "WERLIVEKERNELREPORTING:%u: ERROR WerWaitForSystemErrorHandler timed out, failing the call with 0x%x\n";
                    v6 = -1073740973;
                    v13 = 1101;
                  }
                  else
                  {
                    *(_OWORD *)&v40[32] = 0;
                    *(_DWORD *)v40 = 48;
                    *(_QWORD *)&v40[8] = 0;
                    *(_DWORD *)&v40[24] = 512;
                    *(_QWORD *)&v40[16] = 0;
                    if ( HIDWORD(SystemInformation) == -1 )
                    {
                      v18 = 1;
                    }
                    else
                    {
                      v18 = 0;
                      v36 = -10000LL * SHIDWORD(SystemInformation);
                    }
                    v19 = &v36;
                    if ( v18 )
                      v19 = 0;
                    started = ZwAlpcConnectPort(&Handle, &DestinationString, v40, v43, 0x20000, v34, 0, 0, 0, 0, v19);
                    v6 = started;
                    if ( started >= 0 )
                    {
                      if ( started == 258 )
                      {
                        started = -1073740973;
                        v14 = "WERLIVEKERNELREPORTING:%u: ERROR ZwAlpcConnectPort timed out, failing the call with 0x%x\n";
                        v6 = -1073740973;
                        v13 = 1138;
                      }
                      else
                      {
                        memset(v44, 0, 0x578u);
                        v20 = 15;
                        v44[0] = 91751760;
                        v44[10] = 1610612736;
                        LOWORD(v44[1]) = 0;
                        v44[12] = 0;
                        if ( (unsigned int)cchToCopy <= 0xF )
                          v20 = (unsigned int)cchToCopy;
                        started = RtlStringCchCopyNW((NTSTRSAFE_PWSTR)&v44[14], 0x10u, pszSrc, v20);
                        v6 = started;
                        if ( started >= 0 )
                        {
                          v21 = 39;
                          if ( HIDWORD(cchToCopy) <= 0x27 )
                            v21 = HIDWORD(cchToCopy);
                          started = RtlStringCchCopyNW((NTSTRSAFE_PWSTR)&v44[22], 0x28u, v38, v21);
                          v6 = started;
                          if ( started >= 0 )
                          {
                            memset(&v45[1], 0, 0x574u);
                            v45[0] = 91751760;
                            v39 = 1400;
                            v22 = ZwAlpcSendWaitReceivePort(Handle, 0, v44, 0, v45, &v39, 0, v19);
                            v6 = v22;
                            if ( v22 < 0 || v22 == 258 )
                            {
                              DbgPrintEx(
                                0x96u,
                                0,
                                "WERLIVEKERNELREPORTING:%u: ERROR ZwAlpcSendWaitReceivePort failed\n",
                                1194);
                            }
                            else if ( v45[11] >= 0 )
                            {
                              v6 = 0;
                            }
                            else
                            {
                              DbgPrintEx(0x96u, 0, "WERLIVEKERNELREPORTING:%u: ERROR Service returned failure\n", 1200);
                              v6 = -1073741823;
                            }
                            goto LABEL_51;
                          }
                          v13 = 1175;
                          v14 = "WERLIVEKERNELREPORTING:%u: ERROR StringCchCopy failed for id with 0x%x\n";
                        }
                        else
                        {
                          v13 = 1163;
                          v14 = "WERLIVEKERNELREPORTING:%u: ERROR StringCchCopy failed for key with 0x%x\n";
                        }
                      }
                    }
                    else
                    {
                      v13 = 1131;
                      v14 = "WERLIVEKERNELREPORTING:%u: ERROR ZwAlpcConnectPort failed with 0x%x\n";
                    }
                  }
                }
                else
                {
                  v13 = 1094;
                  v14 = "WERLIVEKERNELREPORTING:%u: ERROR WerWaitForSystemErrorHandler failed with 0x%x\n";
                }
              }
              else
              {
                v13 = 1087;
                v14 = "WERLIVEKERNELREPORTING:%u: ERROR ZwQuerySysInfo(ErrorPortTimeouts) failed with 0x%x\n";
              }
            }
            else
            {
              v13 = 1073;
              v14 = "WERLIVEKERNELREPORTING:%u: ERROR WerStartSystemErrorHandler failed with 0x%x\n";
            }
          }
          else
          {
            v13 = 1040;
            v14 = "WERLIVEKERNELREPORTING:%u: ERROR ParseKeyName failed with 0x%x\n";
          }
        }
        else
        {
          v13 = 1027;
          v14 = "WERLIVEKERNELREPORTING:%u: ERROR ZwQueryKey failed with 0x%x\n";
        }
        LODWORD(ResultLengtha) = started;
        DbgPrintEx(0x96u, 0, v14, v13, ResultLengtha);
LABEL_51:
        WerpFreeMem(v11);
        goto LABEL_52;
      }
    }
    else if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, v9);
      goto LABEL_12;
    }
    DbgPrintEx(0x96u, 0, "WERLIVEKERNELREPORTING:%u: ERROR OOM\n", 1009);
    v6 = -1073741801;
    goto LABEL_52;
  }
  v7 = 979;
  v8 = "WERLIVEKERNELREPORTING:%u: ERROR WerpGetRegistryKey failed for the busy key 0x%x\n";
LABEL_5:
  LODWORD(ResultLength) = RegistryKey;
  DbgPrintEx(0x96u, 0, v8, v7, ResultLength);
LABEL_52:
  if ( KeyHandlea )
  {
    ZwClose(KeyHandlea);
    KeyHandlea = 0;
  }
  if ( v34 )
    WerpFreeMem(v34);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140058c20  mov     [rsp-8+arg_8], rbx
0x140058c25  mov     [rsp-8+arg_10], rsi
0x140058c2a  push    rbp
0x140058c2b  push    rdi
0x140058c2c  push    r12
0x140058c2e  push    r13
0x140058c30  push    r14
0x140058c32  lea     rbp, [rsp-0B60h]
0x140058c3a  sub     rsp, 0C60h
0x140058c41  mov     rax, cs:__security_cookie
0x140058c48  xor     rax, rsp
0x140058c4b  mov     [rbp+0B80h+var_30], rax
0x140058c52  mov     rsi, rcx
0x140058c55  mov     r12d, 578h
0x140058c5b  xor     r14d, r14d
0x140058c5e  lea     rcx, [rbp+0B80h+var_B30]; void *
0x140058c62  mov     r8d, r12d; Size
0x140058c65  mov     [rbp+0B80h+Handle], r14
0x140058c69  xor     edx, edx; Val
0x140058c6b  call    memset
0x140058c70  mov     r8d, r12d; Size
0x140058c73  lea     rcx, [rbp+0B80h+var_5B0]; void *
0x140058c7a  xor     edx, edx; Val
0x140058c7c  call    memset
0x140058c81  xorps   xmm0, xmm0
0x140058c84  mov     [rbp+0B80h+var_BD8], r14
0x140058c88  movups  [rbp+0B80h+var_BC0], xmm0
0x140058c8c  lea     r13d, [r14+48h]
0x140058c90  mov     [rbp+0B80h+var_C00], r14
0x140058c94  xor     eax, eax
0x140058c96  mov     dword ptr [rbp+0B80h+IdentifierAuthority.Value], r14d
0x140058c9a  mov     r8d, r13d; Size
0x140058c9d  mov     word ptr [rbp+0B80h+IdentifierAuthority.Value+4], 500h
0x140058ca3  xor     edx, edx; Val
0x140058ca5  mov     [rbp+0B80h+var_BF0], r14
0x140058ca9  lea     rcx, [rbp+0B80h+var_B80]; void *
0x140058cad  mov     [rsp+0C80h+Length], r14d
0x140058cb2  movups  [rbp+0B80h+var_BC0+0Ch], xmm0
0x140058cb6  mov     [rbp+0B80h+pszSrc], r14
0x140058cba  movups  xmmword ptr [rbp+0B80h+DestinationString.Length], xmm0
0x140058cbe  mov     [rbp+0B80h+var_BE0], r14
0x140058cc2  movups  [rbp+0B80h+var_BD0], xmm0
0x140058cc6  mov     dword ptr [rsp+0C80h+cchToCopy], r14d
0x140058ccb  mov     dword ptr [rsp+0C80h+cchToCopy+4], r14d
0x140058cd0  mov     [rsp+0C80h+KeyHandle], r14
0x140058cd5  call    memset
0x140058cda  mov     [rsp+0C80h+SystemInformation], r14
0x140058cdf  test    rsi, rsi
0x140058ce2  jnz     short loc_140058CEE
0x140058ce4  mov     eax, 0C000000Dh
0x140058ce9  jmp     loc_1400591DD
0x140058cee  lea     r9, [rsp+0C80h+KeyHandle]
0x140058cf3  mov     rcx, rsi
0x140058cf6  call    WerpGetRegistryKey
0x140058cfb  mov     ebx, eax
0x140058cfd  test    eax, eax
0x140058cff  jns     short loc_140058D2A
0x140058d01  mov     r9d, 3D3h
0x140058d07  lea     r8, aWerlivekernelr_6; "WERLIVEKERNELREPORTING:%u: ERROR WerpGe"...
0x140058d0e  xor     edx, edx; Level
0x140058d10  mov     dword ptr [rsp+0C80h+ResultLength], eax
0x140058d14  mov     ecx, 96h; ComponentId
0x140058d19  call    cs:__imp_DbgPrintEx
0x140058d20  nop     dword ptr [rax+rax+00h]
0x140058d25  jmp     loc_14005919D
0x140058d2a  mov     rcx, [rsp+0C80h+KeyHandle]; KeyHandle
0x140058d2f  call    cs:__imp_ZwDeleteKey
0x140058d36  nop     dword ptr [rax+rax+00h]
0x140058d3b  mov     rcx, [rsp+0C80h+KeyHandle]; Handle
0x140058d40  call    cs:__imp_ZwClose
0x140058d47  nop     dword ptr [rax+rax+00h]
0x140058d4c  xor     r9d, r9d; Length
0x140058d4f  mov     [rsp+0C80h+KeyHandle], r14
0x140058d54  lea     rax, [rsp+0C80h+Length]
0x140058d59  xor     r8d, r8d; KeyInformation
0x140058d5c  mov     rcx, rsi; KeyHandle
0x140058d5f  mov     [rsp+0C80h+ResultLength], rax; ResultLength
0x140058d64  lea     edx, [r9+3]; KeyInformationClass
0x140058d68  call    cs:__imp_ZwQueryKey
0x140058d6f  nop     dword ptr [rax+rax+00h]
0x140058d74  mov     ebx, eax
0x140058d76  cmp     eax, 80000005h
0x140058d7b  jz      short loc_140058D96
0x140058d7d  cmp     eax, 0C0000023h
0x140058d82  jz      short loc_140058D96
0x140058d84  mov     r9d, 3E9h
0x140058d8a  lea     r8, aWerlivekernelr_2; "WERLIVEKERNELREPORTING:%u: ERROR ZwQuer"...
0x140058d91  jmp     loc_140058D0E
0x140058d96  movsxd  rbx, [rsp+0C80h+Length]
0x140058d9b  mov     r8d, 7765726Bh; Tag
0x140058da1  mov     rdx, rbx; NumberOfBytes
0x140058da4  mov     ecx, 401h; PoolType
0x140058da9  call    cs:__imp_ExAllocatePoolWithTag
0x140058db0  nop     dword ptr [rax+rax+00h]
0x140058db5  cmp     cs:ExPoolZeroingNativelySupported, r14b
0x140058dbc  mov     rdi, rax
0x140058dbf  jnz     short loc_140058E28
0x140058dc1  test    rax, rax
0x140058dc4  jz      short loc_140058E2D
0x140058dc6  mov     r8, rbx; Size
0x140058dc9  xor     edx, edx; Val
0x140058dcb  mov     rcx, rax; void *
0x140058dce  call    memset
0x140058dd3  mov     r9d, [rsp+0C80h+Length]; Length
0x140058dd8  lea     rax, [rsp+0C80h+Length]
0x140058ddd  mov     r8, rdi; KeyInformation
0x140058de0  mov     [rsp+0C80h+ResultLength], rax; ResultLength
0x140058de5  mov     edx, 3; KeyInformationClass
0x140058dea  mov     rcx, rsi; KeyHandle
0x140058ded  call    cs:__imp_ZwQueryKey
0x140058df4  nop     dword ptr [rax+rax+00h]
0x140058df9  mov     ebx, eax
0x140058dfb  test    eax, eax
0x140058dfd  jns     short loc_140058E57
0x140058dff  mov     r9d, 403h
0x140058e05  lea     r8, aWerlivekernelr_21; "WERLIVEKERNELREPORTING:%u: ERROR ZwQuer"...
0x140058e0c  xor     edx, edx; Level
0x140058e0e  mov     dword ptr [rsp+0C80h+ResultLength], eax
0x140058e12  mov     ecx, 96h; ComponentId
0x140058e17  call    cs:__imp_DbgPrintEx
0x140058e1e  nop     dword ptr [rax+rax+00h]
0x140058e23  jmp     loc_140059195
0x140058e28  test    rdi, rdi
0x140058e2b  jnz     short loc_140058DD3
0x140058e2d  mov     r9d, 3F1h
0x140058e33  lea     r8, aWerlivekernelr_13; "WERLIVEKERNELREPORTING:%u: ERROR OOM\n"
0x140058e3a  xor     edx, edx; Level
0x140058e3c  mov     ecx, 96h; ComponentId
0x140058e41  call    cs:__imp_DbgPrintEx
0x140058e48  nop     dword ptr [rax+rax+00h]
0x140058e4d  mov     ebx, 0C0000017h
0x140058e52  jmp     loc_14005919D
0x140058e57  mov     edx, [rdi]
0x140058e59  lea     rax, [rsp+0C80h+cchToCopy+4]
0x140058e5e  mov     qword ptr [rsp+0C80h+var_C58], rax; int
0x140058e63  lea     rcx, [rdi+4]
0x140058e67  lea     rax, [rbp+0B80h+var_BE0]
0x140058e6b  shr     edx, 1
0x140058e6d  lea     r9, [rsp+0C80h+cchToCopy]
0x140058e72  mov     [rsp+0C80h+ResultLength], rax; int
0x140058e77  lea     r8, [rbp+0B80h+pszSrc]
0x140058e7b  call    WerpParseKeyName
0x140058e80  mov     ebx, eax
0x140058e82  test    eax, eax
0x140058e84  jns     short loc_140058E98
0x140058e86  mov     r9d, 410h
0x140058e8c  lea     r8, aWerlivekernelr_0; "WERLIVEKERNELREPORTING:%u: ERROR ParseK"...
0x140058e93  jmp     loc_140058E0C
0x140058e98  lea     rdx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x140058e9f  lea     rcx, [rbp+0B80h+DestinationString]; DestinationString
0x140058ea3  call    cs:__imp_RtlInitUnicodeString
0x140058eaa  nop     dword ptr [rax+rax+00h]
0x140058eaf  mov     r8, r13; Size
0x140058eb2  lea     rcx, [rbp+0B80h+var_B80]; void *
0x140058eb6  xor     edx, edx; Val
0x140058eb8  call    memset
0x140058ebd  lea     rax, [rbp+0B80h+var_C00]
0x140058ec1  mov     [rbp+0B80h+var_B70], r12
0x140058ec5  lea     rcx, [rbp+0B80h+IdentifierAuthority]; IdentifierAuthority
0x140058ec9  mov     [rsp+0C80h+var_C30], rax; __int64
0x140058ece  call    WerpAllocateAndInitializeSid
0x140058ed3  mov     ebx, eax
0x140058ed5  test    eax, eax
0x140058ed7  js      loc_140059195
0x140058edd  call    WerStartSystemErrorHandler
0x140058ee2  mov     ebx, eax
0x140058ee4  test    eax, eax
0x140058ee6  jns     short loc_140058EFA
0x140058ee8  mov     r9d, 431h
0x140058eee  lea     r8, aWerlivekernelr_8; "WERLIVEKERNELREPORTING:%u: ERROR WerSta"...
0x140058ef5  jmp     loc_140058E0C
0x140058efa  xor     r9d, r9d; ReturnLength
0x140058efd  lea     rdx, [rsp+0C80h+SystemInformation]; SystemInformation
0x140058f02  lea     r8d, [r9+8]; SystemInformationLength
0x140058f06  lea     ecx, [r9+73h]; SystemInformationClass
0x140058f0a  call    cs:__imp_ZwQuerySystemInformation
0x140058f11  nop     dword ptr [rax+rax+00h]
0x140058f16  mov     ebx, eax
0x140058f18  test    eax, eax
0x140058f1a  jns     short loc_140058F2E
0x140058f1c  mov     r9d, 43Fh
0x140058f22  lea     r8, aWerlivekernelr_20; "WERLIVEKERNELREPORTING:%u: ERROR ZwQuer"...
0x140058f29  jmp     loc_140058E0C
0x140058f2e  mov     ecx, dword ptr [rsp+0C80h+SystemInformation]
0x140058f32  call    WerWaitForSystemErrorHandler
0x140058f37  mov     ebx, eax
0x140058f39  test    eax, eax
0x140058f3b  jns     short loc_140058F4F
0x140058f3d  mov     r9d, 446h
0x140058f43  lea     r8, aWerlivekernelr_4; "WERLIVEKERNELREPORTING:%u: ERROR WerWai"...
0x140058f4a  jmp     loc_140058E0C
0x140058f4f  cmp     eax, 102h
0x140058f54  jnz     short loc_140058F6F
0x140058f56  mov     eax, 0C0000353h
0x140058f5b  lea     r8, aWerlivekernelr_3; "WERLIVEKERNELREPORTING:%u: ERROR WerWai"...
0x140058f62  mov     ebx, eax
0x140058f64  mov     r9d, 44Dh
0x140058f6a  jmp     loc_140058E0C
0x140058f6f  cmp     dword ptr [rsp+0C80h+SystemInformation+4], 0FFFFFFFFh
0x140058f74  xorps   xmm0, xmm0
0x140058f77  movdqu  [rbp+0B80h+var_BB0], xmm0
0x140058f7c  mov     dword ptr [rbp+0B80h+var_BD0], 30h ; '0'
0x140058f83  mov     qword ptr [rbp+0B80h+var_BD0+8], r14
0x140058f87  mov     dword ptr [rbp+0B80h+var_BC0+8], 200h
0x140058f8e  mov     qword ptr [rbp+0B80h+var_BC0], r14
0x140058f92  jnz     short loc_140058F98
0x140058f94  mov     dl, 1
0x140058f96  jmp     short loc_140058FAB
0x140058f98  movsxd  rax, dword ptr [rsp+0C80h+SystemInformation+4]
0x140058f9d  mov     dl, r14b
0x140058fa0  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x140058fa7  mov     [rbp+0B80h+var_BF0], rcx
0x140058fab  mov     rax, [rbp+0B80h+var_C00]
0x140058faf  lea     rsi, [rbp+0B80h+var_BF0]
0x140058fb3  test    dl, dl
0x140058fb5  lea     r9, [rbp+0B80h+var_B80]
0x140058fb9  lea     r8, [rbp+0B80h+var_BD0]
0x140058fbd  cmovnz  rsi, r14
0x140058fc1  lea     rdx, [rbp+0B80h+DestinationString]
0x140058fc5  mov     [rsp+0C80h+var_C30], rsi
0x140058fca  lea     rcx, [rbp+0B80h+Handle]
0x140058fce  mov     [rsp+0C80h+var_C38], r14
0x140058fd3  mov     [rsp+0C80h+var_C40], r14
0x140058fd8  mov     [rsp+0C80h+var_C48], r14
0x140058fdd  mov     [rsp+0C80h+var_C50], r14
0x140058fe2  mov     qword ptr [rsp+0C80h+var_C58], rax
0x140058fe7  mov     dword ptr [rsp+0C80h+ResultLength], 20000h
0x140058fef  call    cs:__imp_ZwAlpcConnectPort
0x140058ff6  nop     dword ptr [rax+rax+00h]
0x140058ffb  mov     ebx, eax
0x140058ffd  test    eax, eax
0x140058fff  jns     short loc_140059013
0x140059001  mov     r9d, 46Bh
0x140059007  lea     r8, aWerlivekernelr_9; "WERLIVEKERNELREPORTING:%u: ERROR ZwAlpc"...
0x14005900e  jmp     loc_140058E0C
0x140059013  cmp     eax, 102h
0x140059018  jnz     short loc_140059033
0x14005901a  mov     eax, 0C0000353h
0x14005901f  lea     r8, aWerlivekernelr_5; "WERLIVEKERNELREPORTING:%u: ERROR ZwAlpc"...
0x140059026  mov     ebx, eax
0x140059028  mov     r9d, 472h
0x14005902e  jmp     loc_140058E0C
0x140059033  mov     r8, r12; Size
0x140059036  lea     rcx, [rbp+0B80h+var_B30]; void *
0x14005903a  xor     edx, edx; Val
0x14005903c  call    memset
0x140059041  mov     r9d, 0Fh
0x140059047  mov     [rbp+0B80h+var_B30], 5780550h
0x14005904e  mov     [rbp+0B80h+var_B08], 60000000h
0x140059055  mov     [rbp+0B80h+var_B2C], r14w
0x14005905a  mov     [rbp+0B80h+var_B00], r14d
0x140059061  cmp     dword ptr [rsp+0C80h+cchToCopy], r9d
0x140059066  ja      short loc_14005906D
0x140059068  mov     r9d, dword ptr [rsp+0C80h+cchToCopy]; cchToCopy
0x14005906d  mov     r8, [rbp+0B80h+pszSrc]; pszSrc
0x140059071  lea     rcx, [rbp+0B80h+pszDest]; pszDest
0x140059078  mov     edx, 10h; cchDest
0x14005907d  call    RtlStringCchCopyNW
0x140059082  mov     ebx, eax
0x140059084  test    eax, eax
0x140059086  jns     short loc_14005909A
0x140059088  mov     r9d, 48Bh
0x14005908e  lea     r8, aWerlivekernelr_15; "WERLIVEKERNELREPORTING:%u: ERROR String"...
0x140059095  jmp     loc_140058E0C
0x14005909a  mov     r9d, 27h ; '''
0x1400590a0  cmp     dword ptr [rsp+0C80h+cchToCopy+4], r9d
0x1400590a5  ja      short loc_1400590AC
0x1400590a7  mov     r9d, dword ptr [rsp+0C80h+cchToCopy+4]; cchToCopy
0x1400590ac  mov     r8, [rbp+0B80h+var_BE0]; pszSrc
0x1400590b0  lea     rcx, [rbp+0B80h+var_AD8]; pszDest
0x1400590b7  mov     edx, 28h ; '('; cchDest
0x1400590bc  call    RtlStringCchCopyNW
0x1400590c1  mov     ebx, eax
0x1400590c3  test    eax, eax
0x1400590c5  jns     short loc_1400590D9
0x1400590c7  mov     r9d, 497h
0x1400590cd  lea     r8, aWerlivekernelr_29; "WERLIVEKERNELREPORTING:%u: ERROR String"...
0x1400590d4  jmp     loc_140058E0C
0x1400590d9  xor     edx, edx; Val
0x1400590db  lea     rcx, [rbp+0B80h+var_5AC]; void *
0x1400590e2  mov     r8d, 574h; Size
0x1400590e8  call    memset
0x1400590ed  mov     rcx, [rbp+0B80h+Handle]
0x1400590f1  lea     rax, [rbp+0B80h+var_BD8]
0x1400590f5  mov     [rsp+0C80h+var_C48], rsi
0x1400590fa  lea     r8, [rbp+0B80h+var_B30]
0x1400590fe  mov     [rsp+0C80h+var_C50], r14
0x140059103  xor     r9d, r9d
0x140059106  mov     qword ptr [rsp+0C80h+var_C58], rax
0x14005910b  xor     edx, edx
0x14005910d  lea     rax, [rbp+0B80h+var_5B0]
0x140059114  mov     [rbp+0B80h+var_5B0], 5780550h
0x14005911e  mov     [rsp+0C80h+ResultLength], rax
0x140059123  mov     [rbp+0B80h+var_BD8], r12
0x140059127  call    cs:__imp_ZwAlpcSendWaitReceivePort
0x14005912e  nop     dword ptr [rax+rax+00h]
0x140059133  mov     ebx, eax
0x140059135  test    eax, eax
0x140059137  js      short loc_140059175
0x140059139  cmp     eax, 102h
  ... truncated ...
```
