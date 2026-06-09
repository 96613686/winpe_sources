# CMsiOpExecute::GetSDFromService(SC_HANDLE__ * const,IMsiStream * &)

- ea: `0x1801e0d78`
- end: `0x1801e0ffc`
- name: `?GetSDFromService@CMsiOpExecute@@IEAA_NQEAUSC_HANDLE__@@AEAPEAVIMsiStream@@@Z`
- size: `644`
- prototype: `bool(CMsiOpExecute *__hidden this, struct SC_HANDLE__ *const, struct IMsiStream **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1801ee834`

## callees

- `0x180025a18`
- `0x180060580`
- `0x1800620e4`
- `0x1801e0d78`
- `0x1801f006c`
- `0x18025ab12`
- `0x18025ab2a`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!QueryServiceObjectSecurity` at `0x1801e0e44`
- `ADVAPI32!QueryServiceObjectSecurity` at `0x1801e0efb`
- `ADVAPI32!QueryServiceObjectSecurity` at `0x1801e0e44`
- `ADVAPI32!QueryServiceObjectSecurity` at `0x1801e0efb`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1801e0f30`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1801e0f30`
- `KERNEL32!GetLastError` at `0x1801e0e53`
- `KERNEL32!GetLastError` at `0x1801e0e82`
- `KERNEL32!GetLastError` at `0x1801e0f12`
- `KERNEL32!GetLastError` at `0x1801e0f51`
- `KERNEL32!GetLastError` at `0x1801e0e53`
- `KERNEL32!GetLastError` at `0x1801e0e82`
- `KERNEL32!GetLastError` at `0x1801e0f12`
- `KERNEL32!GetLastError` at `0x1801e0f51`

## string_xrefs

- `0x1801e0dcf`: `Error: Invalid Argument. Failed while querying service security.`
- `0x1801e0e98`: `Error %d. Failed to allocate space while querying service security.`
- `0x1801e0f57`: `Error %d. Failed to allocate space while querying service security.`
- `0x1801e0f18`: `Error %d. Failed while querying service security.`

## pseudocode

```c
char __fastcall CMsiOpExecute::GetSDFromService(
        CMsiOpExecute *this,
        struct SC_HANDLE__ *const a2,
        struct IMsiStream **a3)
{
  DWORD LastError; // eax
  PSECURITY_DESCRIPTOR v6; // r8
  DWORD v7; // eax
  PSECURITY_DESCRIPTOR v8; // rcx
  const unsigned __int16 *v9; // r9
  char *MemoryStream; // rax
  DWORD cbBufSize[4]; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR lpSecurityDescriptor; // [rsp+70h] [rbp-90h] BYREF
  int v14; // [rsp+78h] [rbp-88h]
  _BYTE SecurityDescriptor[1024]; // [rsp+80h] [rbp-80h] BYREF

  if ( !a2 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        L"Error: Invalid Argument. Failed while querying service security.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    return 0;
  }
  cbBufSize[0] = 1024;
  memset_0(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v14 = 1024;
  lpSecurityDescriptor = SecurityDescriptor;
  if ( !QueryServiceObjectSecurity(a2, 7u, SecurityDescriptor, 0x400u, cbBufSize) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      if ( g_dmDiagnosticMode )
        goto LABEL_14;
      goto LABEL_21;
    }
    CTempBuffer<unsigned char,1024>::SetSize(&lpSecurityDescriptor, cbBufSize[0]);
    v6 = lpSecurityDescriptor;
    if ( !lpSecurityDescriptor )
    {
      if ( g_dmDiagnosticMode )
      {
        v7 = GetLastError();
        DebugString(
          10,
          0,
          0,
          L"Error %d. Failed to allocate space while querying service security.",
          (const unsigned __int16 *)v7,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
        v6 = lpSecurityDescriptor;
      }
      if ( v14 <= 1024 )
        return 0;
      v8 = v6;
      goto LABEL_23;
    }
    if ( !QueryServiceObjectSecurity(a2, 7u, lpSecurityDescriptor, cbBufSize[0], cbBufSize) )
    {
      if ( g_dmDiagnosticMode )
      {
        LastError = GetLastError();
LABEL_14:
        v9 = L"Error %d. Failed while querying service security.";
LABEL_20:
        DebugString(
          10,
          0,
          0,
          v9,
          (const unsigned __int16 *)LastError,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
LABEL_21:
      if ( v14 <= 1024 )
        return 0;
      v8 = lpSecurityDescriptor;
LABEL_23:
      operator delete(v8);
      return 0;
    }
  }
  cbBufSize[0] = GetSecurityDescriptorLength(lpSecurityDescriptor);
  MemoryStream = AllocateMemoryStream(cbBufSize[0], a3);
  if ( !MemoryStream )
  {
    if ( g_dmDiagnosticMode )
    {
      LastError = GetLastError();
      v9 = L"Error %d. Failed to allocate space while querying service security.";
      goto LABEL_20;
    }
    goto LABEL_21;
  }
  memcpy_0(MemoryStream, lpSecurityDescriptor, cbBufSize[0]);
  if ( v14 > 1024 )
    operator delete(lpSecurityDescriptor);
  return 1;
}

```

## disassembly

```asm
0x1801e0d78  mov     [rsp-8+arg_0], rbx
0x1801e0d7d  mov     [rsp-8+arg_18], rsi
0x1801e0d82  push    rbp
0x1801e0d83  push    rdi
0x1801e0d84  push    r14
0x1801e0d86  lea     rbp, [rsp-390h]
0x1801e0d8e  sub     rsp, 490h
0x1801e0d95  mov     rax, cs:__security_cookie
0x1801e0d9c  xor     rax, rsp
0x1801e0d9f  mov     [rbp+3A0h+var_20], rax
0x1801e0da6  xor     esi, esi
0x1801e0da8  mov     rdi, r8
0x1801e0dab  mov     rbx, rdx
0x1801e0dae  test    rdx, rdx
0x1801e0db1  jnz     short loc_1801E0E04
0x1801e0db3  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801e0db9  jz      loc_1801E0FAC
0x1801e0dbf  lea     rcx, aNull; "(NULL)"
0x1801e0dc6  mov     [rsp+4A0h+var_448], rsi; void *
0x1801e0dcb  mov     [rsp+4A0h+var_450], esi; unsigned int
0x1801e0dcf  lea     r9, aErrorInvalidAr_0; "Error: Invalid Argument. Failed while q"...
0x1801e0dd6  mov     [rsp+4A0h+var_458], rcx; unsigned __int16 *
0x1801e0ddb  xor     r8d, r8d; int
0x1801e0dde  mov     [rsp+4A0h+var_460], rcx; unsigned __int16 *
0x1801e0de3  mov     [rsp+4A0h+var_468], rcx; unsigned __int16 *
0x1801e0de8  mov     [rsp+4A0h+var_470], rcx; unsigned __int16 *
0x1801e0ded  mov     [rsp+4A0h+var_478], rcx; unsigned __int16 *
0x1801e0df2  mov     [rsp+4A0h+pcbBytesNeeded], rcx; unsigned __int16 *
0x1801e0df7  lea     ecx, [rdx+0Ah]; int
0x1801e0dfa  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801e0dff  jmp     loc_1801E0FAC
0x1801e0e04  mov     r14d, 400h
0x1801e0e0a  lea     rcx, [rbp+3A0h+SecurityDescriptor]; void *
0x1801e0e0e  mov     r8d, r14d; Size
0x1801e0e11  mov     [rsp+4A0h+cbBufSize], r14d
0x1801e0e16  xor     edx, edx; Val
0x1801e0e18  call    memset_0
0x1801e0e1d  lea     rax, [rbp+3A0h+SecurityDescriptor]
0x1801e0e21  mov     [rsp+4A0h+var_428], r14d
0x1801e0e26  mov     [rsp+4A0h+lpSecurityDescriptor], rax
0x1801e0e2b  lea     r8, [rbp+3A0h+SecurityDescriptor]; lpSecurityDescriptor
0x1801e0e2f  lea     rax, [rsp+4A0h+cbBufSize]
0x1801e0e34  mov     r9d, r14d; cbBufSize
0x1801e0e37  mov     edx, 7; dwSecurityInformation
0x1801e0e3c  mov     [rsp+4A0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1801e0e41  mov     rcx, rbx; hService
0x1801e0e44  call    cs:__imp_QueryServiceObjectSecurity
0x1801e0e4a  cmp     eax, 1
0x1801e0e4d  jz      loc_1801E0F2B
0x1801e0e53  call    cs:__imp_GetLastError
0x1801e0e59  cmp     eax, 7Ah ; 'z'
0x1801e0e5c  jnz     loc_1801E0F21
0x1801e0e62  mov     edx, [rsp+4A0h+cbBufSize]
0x1801e0e66  lea     rcx, [rsp+4A0h+lpSecurityDescriptor]
0x1801e0e6b  call    ?SetSize@?$CTempBuffer@E$0EAA@@@QEAAXH@Z; CTempBuffer<uchar,1024>::SetSize(int)
0x1801e0e70  mov     r8, [rsp+4A0h+lpSecurityDescriptor]; lpSecurityDescriptor
0x1801e0e75  test    r8, r8
0x1801e0e78  jnz     short loc_1801E0EE4
0x1801e0e7a  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801e0e80  jz      short loc_1801E0ED1
0x1801e0e82  call    cs:__imp_GetLastError
0x1801e0e88  lea     rcx, aNull; "(NULL)"
0x1801e0e8f  mov     [rsp+4A0h+var_448], rsi; void *
0x1801e0e94  mov     [rsp+4A0h+var_450], esi; unsigned int
0x1801e0e98  lea     r9, aErrorDFailedTo_0; "Error %d. Failed to allocate space whil"...
0x1801e0e9f  mov     [rsp+4A0h+var_458], rcx; unsigned __int16 *
0x1801e0ea4  xor     edx, edx; unsigned __int16
0x1801e0ea6  mov     [rsp+4A0h+var_460], rcx; unsigned __int16 *
0x1801e0eab  xor     r8d, r8d; int
0x1801e0eae  mov     [rsp+4A0h+var_468], rcx; unsigned __int16 *
0x1801e0eb3  mov     [rsp+4A0h+var_470], rcx; unsigned __int16 *
0x1801e0eb8  mov     [rsp+4A0h+var_478], rcx; unsigned __int16 *
0x1801e0ebd  lea     ecx, [rdx+0Ah]; int
0x1801e0ec0  mov     eax, eax
0x1801e0ec2  mov     [rsp+4A0h+pcbBytesNeeded], rax; unsigned __int16 *
0x1801e0ec7  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801e0ecc  mov     r8, [rsp+4A0h+lpSecurityDescriptor]
0x1801e0ed1  cmp     [rsp+4A0h+var_428], r14d
0x1801e0ed6  jle     loc_1801E0FAC
0x1801e0edc  mov     rcx, r8
0x1801e0edf  jmp     loc_1801E0FA7
0x1801e0ee4  mov     r9d, [rsp+4A0h+cbBufSize]; cbBufSize
0x1801e0ee9  lea     rax, [rsp+4A0h+cbBufSize]
0x1801e0eee  mov     edx, 7; dwSecurityInformation
0x1801e0ef3  mov     [rsp+4A0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1801e0ef8  mov     rcx, rbx; hService
0x1801e0efb  call    cs:__imp_QueryServiceObjectSecurity
0x1801e0f01  cmp     eax, 1
0x1801e0f04  jz      short loc_1801E0F2B
0x1801e0f06  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801e0f0c  jz      loc_1801E0F9B
0x1801e0f12  call    cs:__imp_GetLastError
0x1801e0f18  lea     r9, aErrorDFailedWh; "Error %d. Failed while querying service"...
0x1801e0f1f  jmp     short loc_1801E0F5E
0x1801e0f21  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801e0f27  jz      short loc_1801E0F9B
0x1801e0f29  jmp     short loc_1801E0F18
0x1801e0f2b  mov     rcx, [rsp+4A0h+lpSecurityDescriptor]; pSecurityDescriptor
0x1801e0f30  call    cs:__imp_GetSecurityDescriptorLength
0x1801e0f36  mov     ecx, eax; unsigned int
0x1801e0f38  mov     [rsp+4A0h+cbBufSize], eax
0x1801e0f3c  mov     rdx, rdi; struct IMsiStream **
0x1801e0f3f  call    ?AllocateMemoryStream@@YAPEADIAEAPEAVIMsiStream@@@Z; AllocateMemoryStream(uint,IMsiStream * &)
0x1801e0f44  test    rax, rax
0x1801e0f47  jnz     short loc_1801E0FB0
0x1801e0f49  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801e0f4f  jz      short loc_1801E0F9B
0x1801e0f51  call    cs:__imp_GetLastError
0x1801e0f57  lea     r9, aErrorDFailedTo_0; "Error %d. Failed to allocate space whil"...
0x1801e0f5e  mov     [rsp+4A0h+var_448], rsi; void *
0x1801e0f63  lea     rcx, aNull; "(NULL)"
0x1801e0f6a  mov     [rsp+4A0h+var_450], esi; unsigned int
0x1801e0f6e  xor     edx, edx; unsigned __int16
0x1801e0f70  mov     [rsp+4A0h+var_458], rcx; unsigned __int16 *
0x1801e0f75  xor     r8d, r8d; int
0x1801e0f78  mov     [rsp+4A0h+var_460], rcx; unsigned __int16 *
0x1801e0f7d  mov     [rsp+4A0h+var_468], rcx; unsigned __int16 *
0x1801e0f82  mov     [rsp+4A0h+var_470], rcx; unsigned __int16 *
0x1801e0f87  mov     [rsp+4A0h+var_478], rcx; unsigned __int16 *
0x1801e0f8c  lea     ecx, [rdx+0Ah]; int
0x1801e0f8f  mov     eax, eax
0x1801e0f91  mov     [rsp+4A0h+pcbBytesNeeded], rax; unsigned __int16 *
0x1801e0f96  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801e0f9b  cmp     [rsp+4A0h+var_428], r14d
0x1801e0fa0  jle     short loc_1801E0FAC
0x1801e0fa2  mov     rcx, [rsp+4A0h+lpSecurityDescriptor]; void *
0x1801e0fa7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801e0fac  xor     al, al
0x1801e0fae  jmp     short loc_1801E0FD5
0x1801e0fb0  mov     r8d, [rsp+4A0h+cbBufSize]; Size
0x1801e0fb5  mov     rcx, rax; void *
0x1801e0fb8  mov     rdx, [rsp+4A0h+lpSecurityDescriptor]; Src
0x1801e0fbd  call    memcpy_0
0x1801e0fc2  cmp     [rsp+4A0h+var_428], r14d
0x1801e0fc7  jle     short loc_1801E0FD3
0x1801e0fc9  mov     rcx, [rsp+4A0h+lpSecurityDescriptor]; void *
0x1801e0fce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801e0fd3  mov     al, 1
0x1801e0fd5  mov     rcx, [rbp+3A0h+var_20]
0x1801e0fdc  xor     rcx, rsp; StackCookie
0x1801e0fdf  call    __security_check_cookie
0x1801e0fe4  lea     r11, [rsp+4A0h+var_10]
0x1801e0fec  mov     rbx, [r11+20h]
0x1801e0ff0  mov     rsi, [r11+38h]
0x1801e0ff4  mov     rsp, r11
0x1801e0ff7  pop     r14
0x1801e0ff9  pop     rdi
0x1801e0ffa  pop     rbp
0x1801e0ffb  retn
```
