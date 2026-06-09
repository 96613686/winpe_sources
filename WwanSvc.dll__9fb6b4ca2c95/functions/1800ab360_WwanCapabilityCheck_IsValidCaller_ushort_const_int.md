# WwanCapabilityCheck::IsValidCaller(ushort const *,int *)

- ea: `0x1800ab360`
- end: `0x1800ab43c`
- name: `?IsValidCaller@WwanCapabilityCheck@@SAKPEBGPEAH@Z`
- size: `220`
- prototype: `unsigned int __fastcall(LPCWSTR StringSid, PBOOL IsMember)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ab75c`
- `0x1800ac4c0`
- `0x1800ac660`
- `0x1800acba0`
- `0x1800acd60`
- `0x1800ad680`

## callees

- `0x1800ab360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab3b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab3e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab3b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab3e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab407`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ab3ad`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ab3ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ab396`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ab396`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab417`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab417`
- `RPCRT4!RpcImpersonateClient` at `0x1800ab386`
- `RPCRT4!RpcImpersonateClient` at `0x1800ab386`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800ab3ca`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800ab3ca`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ab3fd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ab3fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab427`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab427`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ab3dc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ab3dc`

## pseudocode

```c
__int64 __fastcall WwanCapabilityCheck::IsValidCaller(LPCWSTR StringSid, PBOOL IsMember)
{
  DWORD LastError; // edi
  HANDLE CurrentThread; // rax
  void *v6; // rbx
  PSID Sid; // [rsp+50h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  Sid = 0;
  TokenHandle = 0;
  LastError = RpcImpersonateClient(0);
  if ( !LastError )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
    {
      v6 = TokenHandle;
    }
    else
    {
      v6 = 0;
      LastError = GetLastError();
    }
    RpcRevertToSelfEx(0);
    if ( !LastError
      && (ConvertStringSidToSidW(StringSid, &Sid) || (LastError = GetLastError()) == 0)
      && !CheckTokenMembership(v6, Sid, IsMember) )
    {
      LastError = GetLastError();
    }
    if ( v6 )
      CloseHandle(v6);
  }
  if ( Sid )
    LocalFree(Sid);
  return LastError;
}

```

## disassembly

```asm
0x1800ab360  mov     [rsp+arg_0], rbx
0x1800ab365  push    rbp
0x1800ab366  push    rsi
0x1800ab367  push    rdi
0x1800ab368  sub     rsp, 20h
0x1800ab36c  mov     rsi, rcx
0x1800ab36f  mov     [rsp+38h+Sid], 0
0x1800ab378  xor     ecx, ecx; BindingHandle
0x1800ab37a  mov     [rsp+38h+TokenHandle], 0
0x1800ab383  mov     rbp, rdx
0x1800ab386  call    cs:__imp_RpcImpersonateClient
0x1800ab38c  mov     edi, eax
0x1800ab38e  test    eax, eax
0x1800ab390  jnz     loc_1800AB41D
0x1800ab396  call    cs:__imp_GetCurrentThread
0x1800ab39c  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800ab3a1  mov     edx, 0F01FFh; DesiredAccess
0x1800ab3a6  mov     rcx, rax; ThreadHandle
0x1800ab3a9  lea     r8d, [rdi+1]; OpenAsSelf
0x1800ab3ad  call    cs:__imp_OpenThreadToken
0x1800ab3b3  test    eax, eax
0x1800ab3b5  jnz     short loc_1800AB3C3
0x1800ab3b7  xor     ebx, ebx
0x1800ab3b9  call    cs:__imp_GetLastError
0x1800ab3bf  mov     edi, eax
0x1800ab3c1  jmp     short loc_1800AB3C8
0x1800ab3c3  mov     rbx, [rsp+38h+TokenHandle]
0x1800ab3c8  xor     ecx, ecx; BindingHandle
0x1800ab3ca  call    cs:__imp_RpcRevertToSelfEx
0x1800ab3d0  test    edi, edi
0x1800ab3d2  jnz     short loc_1800AB40F
0x1800ab3d4  lea     rdx, [rsp+38h+Sid]; Sid
0x1800ab3d9  mov     rcx, rsi; StringSid
0x1800ab3dc  call    cs:__imp_ConvertStringSidToSidW
0x1800ab3e2  test    eax, eax
0x1800ab3e4  jnz     short loc_1800AB3F2
0x1800ab3e6  call    cs:__imp_GetLastError
0x1800ab3ec  mov     edi, eax
0x1800ab3ee  test    eax, eax
0x1800ab3f0  jnz     short loc_1800AB40F
0x1800ab3f2  mov     rdx, [rsp+38h+Sid]; SidToCheck
0x1800ab3f7  mov     r8, rbp; IsMember
0x1800ab3fa  mov     rcx, rbx; TokenHandle
0x1800ab3fd  call    cs:__imp_CheckTokenMembership
0x1800ab403  test    eax, eax
0x1800ab405  jnz     short loc_1800AB40F
0x1800ab407  call    cs:__imp_GetLastError
0x1800ab40d  mov     edi, eax
0x1800ab40f  test    rbx, rbx
0x1800ab412  jz      short loc_1800AB41D
0x1800ab414  mov     rcx, rbx; hObject
0x1800ab417  call    cs:__imp_CloseHandle
0x1800ab41d  mov     rcx, [rsp+38h+Sid]; hMem
0x1800ab422  test    rcx, rcx
0x1800ab425  jz      short loc_1800AB42D
0x1800ab427  call    cs:__imp_LocalFree
0x1800ab42d  mov     rbx, [rsp+38h+arg_0]
0x1800ab432  mov     eax, edi
0x1800ab434  add     rsp, 20h
0x1800ab438  pop     rdi
0x1800ab439  pop     rsi
0x1800ab43a  pop     rbp
0x1800ab43b  retn
```
