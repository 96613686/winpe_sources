# CRuntimeBroker::CheckClientAccess(bool *,void *)

- ea: `0x14000b018`
- end: `0x14000b19c`
- name: `?CheckClientAccess@CRuntimeBroker@@AEAAJPEA_NPEAX@Z`
- size: `388`
- prototype: `int(CRuntimeBroker *__hidden this, bool *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000aef0`

## callees

- `0x140008c80`
- `0x14000b018`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x14000b0a5`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x14000b0e0`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x14000b0a5`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x14000b0e0`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x14000b078`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x14000b078`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x14000b136`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x14000b136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b0ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b0ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b140`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000b089`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000b0c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000b089`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000b0c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000b0ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000b0ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000b160`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000b160`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x14000b171`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x14000b171`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::CheckClientAccess(CRuntimeBroker *this, bool *a2, void *a3)
{
  HANDLE CurrentProcess; // rax
  void *v6; // rsi
  DWORD v7; // ebx
  signed int v8; // edi
  HANDLE v9; // rax
  signed int LastError; // eax
  signed int v11; // eax
  DWORD nLengthNeeded; // [rsp+40h] [rbp-19h] BYREF
  DWORD AccessMask; // [rsp+44h] [rbp-15h] BYREF
  WINBOOL AccessStatus; // [rsp+48h] [rbp-11h] BYREF
  DWORD GrantedAccess; // [rsp+4Ch] [rbp-Dh] BYREF
  DWORD PrivilegeSetLength; // [rsp+50h] [rbp-9h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+58h] [rbp-1h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+68h] [rbp+Fh] BYREF

  AccessStatus = 0;
  GrantedAccess = 0;
  PrivilegeSetLength = 20;
  AccessMask = 0x1FFFFF;
  GenericMapping = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  MapGenericMask(&AccessMask, &GenericMapping);
  *a2 = 0;
  nLengthNeeded = 0;
  CurrentProcess = GetCurrentProcess();
  GetKernelObjectSecurity(CurrentProcess, 7u, 0, 0, &nLengthNeeded);
  v6 = CoTaskMemAlloc(nLengthNeeded);
  if ( v6 )
  {
    v7 = nLengthNeeded;
    v8 = 0;
    v9 = GetCurrentProcess();
    if ( GetKernelObjectSecurity(v9, 7u, v6, v7, &nLengthNeeded) )
      goto LABEL_15;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
    {
LABEL_15:
      if ( AccessCheck(
             v6,
             a3,
             AccessMask,
             &GenericMapping,
             &PrivilegeSet,
             &PrivilegeSetLength,
             &GrantedAccess,
             &AccessStatus) )
      {
        *a2 = AccessStatus != 0;
      }
      else
      {
        v11 = GetLastError();
        v8 = v11;
        if ( v11 > 0 )
          v8 = (unsigned __int16)v11 | 0x80070000;
      }
    }
    CoTaskMemFree(v6);
  }
  else
  {
    v8 = -2147024882;
    RoOriginateError(2147942414LL, 0);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000b018  mov     [rsp-8+arg_0], rbx
0x14000b01d  push    rbp
0x14000b01e  push    rsi
0x14000b01f  push    rdi
0x14000b020  push    r14
0x14000b022  push    r15
0x14000b024  lea     rbp, [rsp-37h]
0x14000b029  sub     rsp, 90h
0x14000b030  mov     rax, cs:__security_cookie
0x14000b037  xor     rax, rsp
0x14000b03a  mov     [rbp+57h+var_30], rax
0x14000b03e  xorps   xmm0, xmm0
0x14000b041  mov     [rbp+57h+var_68], 0
0x14000b048  mov     r14, rdx
0x14000b04b  mov     [rbp+57h+var_64], 0
0x14000b052  xor     eax, eax
0x14000b054  mov     [rbp+57h+var_60], 14h
0x14000b05b  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x14000b05f  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x14000b062  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x14000b066  mov     [rbp+57h+AccessMask], 1FFFFFh
0x14000b06d  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x14000b071  mov     r15, r8
0x14000b074  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x14000b078  call    cs:__imp_MapGenericMask
0x14000b07e  mov     byte ptr [r14], 0
0x14000b082  mov     [rbp+57h+nLengthNeeded], 0
0x14000b089  call    cs:__imp_GetCurrentProcess
0x14000b08f  xor     r9d, r9d; nLength
0x14000b092  lea     rcx, [rbp+57h+nLengthNeeded]
0x14000b096  mov     [rsp+0B0h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x14000b09b  xor     r8d, r8d; pSecurityDescriptor
0x14000b09e  mov     rcx, rax; Handle
0x14000b0a1  lea     edx, [r9+7]; RequestedInformation
0x14000b0a5  call    cs:__imp_GetKernelObjectSecurity
0x14000b0ab  mov     ecx, [rbp+57h+nLengthNeeded]; cb
0x14000b0ae  call    cs:__imp_CoTaskMemAlloc
0x14000b0b4  mov     rsi, rax
0x14000b0b7  test    rax, rax
0x14000b0ba  jz      loc_14000B168
0x14000b0c0  mov     ebx, [rbp+57h+nLengthNeeded]
0x14000b0c3  xor     edi, edi
0x14000b0c5  call    cs:__imp_GetCurrentProcess
0x14000b0cb  lea     rcx, [rbp+57h+nLengthNeeded]
0x14000b0cf  mov     r9d, ebx; nLength
0x14000b0d2  mov     [rsp+0B0h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x14000b0d7  lea     edx, [rdi+7]; RequestedInformation
0x14000b0da  mov     rcx, rax; Handle
0x14000b0dd  mov     r8, rsi; pSecurityDescriptor
0x14000b0e0  call    cs:__imp_GetKernelObjectSecurity
0x14000b0e6  mov     ebx, 80070000h
0x14000b0eb  test    eax, eax
0x14000b0ed  jnz     short loc_14000B104
0x14000b0ef  call    cs:__imp_GetLastError
0x14000b0f5  mov     edi, eax
0x14000b0f7  test    eax, eax
0x14000b0f9  jle     short loc_14000B100
0x14000b0fb  movzx   edi, ax
0x14000b0fe  or      edi, ebx
0x14000b100  test    edi, edi
0x14000b102  js      short loc_14000B15D
0x14000b104  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x14000b108  lea     rax, [rbp+57h+var_68]
0x14000b10c  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x14000b111  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x14000b115  lea     rax, [rbp+57h+var_64]
0x14000b119  mov     rdx, r15; ClientToken
0x14000b11c  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x14000b121  mov     rcx, rsi; pSecurityDescriptor
0x14000b124  lea     rax, [rbp+57h+var_60]
0x14000b128  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x14000b12d  lea     rax, [rbp+57h+PrivilegeSet]
0x14000b131  mov     [rsp+0B0h+lpnLengthNeeded], rax; PrivilegeSet
0x14000b136  call    cs:__imp_AccessCheck
0x14000b13c  test    eax, eax
0x14000b13e  jnz     short loc_14000B153
0x14000b140  call    cs:__imp_GetLastError
0x14000b146  mov     edi, eax
0x14000b148  test    eax, eax
0x14000b14a  jle     short loc_14000B15D
0x14000b14c  movzx   edi, ax
0x14000b14f  or      edi, ebx
0x14000b151  jmp     short loc_14000B15D
0x14000b153  cmp     [rbp+57h+var_68], 0
0x14000b157  setnz   al
0x14000b15a  mov     [r14], al
0x14000b15d  mov     rcx, rsi; pv
0x14000b160  call    cs:__imp_CoTaskMemFree
0x14000b166  jmp     short loc_14000B177
0x14000b168  mov     edi, 8007000Eh
0x14000b16d  xor     edx, edx
0x14000b16f  mov     ecx, edi
0x14000b171  call    cs:__imp_RoOriginateError
0x14000b177  mov     eax, edi
0x14000b179  mov     rcx, [rbp+57h+var_30]
0x14000b17d  xor     rcx, rsp; StackCookie
0x14000b180  call    __security_check_cookie
0x14000b185  mov     rbx, [rsp+0B0h+arg_0]
0x14000b18d  add     rsp, 90h
0x14000b194  pop     r15
0x14000b196  pop     r14
0x14000b198  pop     rdi
0x14000b199  pop     rsi
0x14000b19a  pop     rbp
0x14000b19b  retn
```
