# CERTMAP_AUTH_PROVIDER::InitializeInstance(void)

- ea: `0x180002110`
- end: `0x180002258`
- name: `?InitializeInstance@CERTMAP_AUTH_PROVIDER@@QEAAJXZ`
- size: `328`
- prototype: `__int64 __fastcall(CERTMAP_AUTH_PROVIDER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002c60`

## callees

- `0x180002110`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002174`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002174`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002161`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000217e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000217e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021c2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800021b8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002206`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800021b8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002206`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002240`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002240`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800021d5`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800021d5`

## pseudocode

```c
__int64 __fastcall CERTMAP_AUTH_PROVIDER::InitializeInstance(CERTMAP_AUTH_PROVIDER *this)
{
  char *v1; // rdi
  _QWORD *v2; // rsi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  CERTMAP_AUTH_PROVIDER *TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  TokenInformationLength = this;
  v1 = (char *)s_pCertmapAuthProvider;
  TokenHandle = 0;
  v2 = (_QWORD *)*((_QWORD *)s_pCertmapAuthProvider + 6);
  LODWORD(TokenInformationLength) = *((_DWORD *)s_pCertmapAuthProvider + 14);
  (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)s_pCertmapAuthProvider + 64LL))(s_pCertmapAuthProvider, 128);
  *((_OWORD *)v1 + 4) = 0;
  *((_OWORD *)v1 + 5) = 0;
  *((_OWORD *)v1 + 6) = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    goto LABEL_2;
  if ( GetTokenInformation(TokenHandle, TokenUser, v2, (DWORD)TokenInformationLength, (PDWORD)&TokenInformationLength) )
    goto LABEL_9;
  if ( GetLastError() != 122 )
    goto LABEL_2;
  if ( !BUFFER::Resize((BUFFER *)(v1 + 16), (unsigned int)TokenInformationLength) )
  {
    v5 = -2147024888;
    goto LABEL_10;
  }
  v2 = (_QWORD *)*((_QWORD *)v1 + 6);
  if ( GetTokenInformation(TokenHandle, TokenUser, v2, (DWORD)TokenInformationLength, (PDWORD)&TokenInformationLength) )
  {
LABEL_9:
    v5 = 0;
    *((_DWORD *)v1 + 16) = 983551;
    *((_DWORD *)v1 + 23) = 0;
    *(_QWORD *)(v1 + 68) = 2;
    *((_DWORD *)v1 + 24) = 1;
    *((_QWORD *)v1 + 13) = *v2;
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_10:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x180002110  mov     rax, rsp
0x180002113  mov     [rax+18h], rbx
0x180002117  mov     [rax+20h], rsi
0x18000211b  mov     [rax+8], rcx
0x18000211f  push    rdi
0x180002120  sub     rsp, 30h
0x180002124  mov     rdi, cs:?s_pCertmapAuthProvider@@3PEAVCERTMAP_AUTH_PROVIDER@@EA; CERTMAP_AUTH_PROVIDER * s_pCertmapAuthProvider
0x18000212b  mov     edx, 80h
0x180002130  mov     qword ptr [rax+10h], 0
0x180002138  mov     rcx, rdi
0x18000213b  mov     eax, [rdi+38h]
0x18000213e  mov     rsi, [rdi+30h]
0x180002142  mov     dword ptr [rsp+38h+TokenInformationLength], eax
0x180002146  mov     rax, [rdi]
0x180002149  mov     rax, [rax+40h]
0x18000214d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002152  xorps   xmm0, xmm0
0x180002155  movups  xmmword ptr [rdi+40h], xmm0
0x180002159  movups  xmmword ptr [rdi+50h], xmm0
0x18000215d  movups  xmmword ptr [rdi+60h], xmm0
0x180002161  call    cs:__imp_GetCurrentProcess
0x180002167  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18000216c  mov     edx, 20008h; DesiredAccess
0x180002171  mov     rcx, rax; ProcessHandle
0x180002174  call    cs:__imp_OpenProcessToken
0x18000217a  test    eax, eax
0x18000217c  jnz     short loc_18000219C
0x18000217e  call    cs:__imp_GetLastError
0x180002184  mov     ebx, eax
0x180002186  test    eax, eax
0x180002188  jle     loc_180002236
0x18000218e  movzx   ebx, ax
0x180002191  or      ebx, 80070000h
0x180002197  jmp     loc_180002236
0x18000219c  mov     r9d, dword ptr [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800021a1  lea     rax, [rsp+38h+TokenInformationLength]
0x1800021a6  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800021ab  mov     r8, rsi; TokenInformation
0x1800021ae  mov     edx, 1; TokenInformationClass
0x1800021b3  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800021b8  call    cs:__imp_GetTokenInformation
0x1800021be  test    eax, eax
0x1800021c0  jnz     short loc_180002214
0x1800021c2  call    cs:__imp_GetLastError
0x1800021c8  cmp     eax, 7Ah ; 'z'
0x1800021cb  jnz     short loc_18000217E
0x1800021cd  mov     edx, dword ptr [rsp+38h+TokenInformationLength]
0x1800021d1  lea     rcx, [rdi+10h]
0x1800021d5  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800021db  test    al, al
0x1800021dd  jnz     short loc_1800021E6
0x1800021df  mov     ebx, 80070008h
0x1800021e4  jmp     short loc_180002236
0x1800021e6  mov     rsi, [rdi+30h]
0x1800021ea  lea     rax, [rsp+38h+TokenInformationLength]
0x1800021ef  mov     r9d, dword ptr [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800021f4  mov     r8, rsi; TokenInformation
0x1800021f7  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800021fc  mov     edx, 1; TokenInformationClass
0x180002201  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180002206  call    cs:__imp_GetTokenInformation
0x18000220c  test    eax, eax
0x18000220e  jz      loc_18000217E
0x180002214  xor     ebx, ebx
0x180002216  mov     dword ptr [rdi+40h], 0F01FFh
0x18000221d  mov     [rdi+5Ch], ebx
0x180002220  mov     qword ptr [rdi+44h], 2
0x180002228  mov     dword ptr [rdi+60h], 1
0x18000222f  mov     rcx, [rsi]
0x180002232  mov     [rdi+68h], rcx
0x180002236  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18000223b  test    rcx, rcx
0x18000223e  jz      short loc_180002246
0x180002240  call    cs:__imp_CloseHandle
0x180002246  mov     rsi, [rsp+38h+arg_18]
0x18000224b  mov     eax, ebx
0x18000224d  mov     rbx, [rsp+38h+arg_10]
0x180002252  add     rsp, 30h
0x180002256  pop     rdi
0x180002257  retn
```
