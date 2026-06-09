# CSmsRpcUtils::IsCallerLocalSystem(void)

- ea: `0x180027368`
- end: `0x180027461`
- name: `?IsCallerLocalSystem@CSmsRpcUtils@@SAHXZ`
- size: `249`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003c580`

## callees

- `0x180003a60`
- `0x18002723c`
- `0x180027368`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027440`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027440`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800273ff`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800273ff`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800273e9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800273e9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180027427`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180027427`

## pseudocode

```c
_BOOL8 CSmsRpcUtils::IsCallerLocalSystem(void)
{
  int v1; // edi
  WINBOOL IsMember; // [rsp+60h] [rbp+7h] BYREF
  HANDLE TokenHandle; // [rsp+68h] [rbp+Fh] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp+17h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  TokenHandle = 0;
  if ( ImpersonateAndGetToken(&TokenHandle) < 0 )
    return 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( !CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) || (v1 = 0, !IsMember) )
      v1 = 5;
  }
  else
  {
    v1 = 14;
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v1 == 0;
}

```

## disassembly

```asm
0x180027368  push    rbp
0x18002736a  push    rsi
0x18002736b  push    rdi
0x18002736c  push    r14
0x18002736e  lea     rbp, [rsp-3Fh]
0x180027373  sub     rsp, 98h
0x18002737a  mov     rax, cs:__security_cookie
0x180027381  xor     rax, rsp
0x180027384  mov     [rbp+57h+var_30], rax
0x180027388  xor     r14d, r14d
0x18002738b  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180027391  lea     rcx, [rbp+57h+TokenHandle]; void **
0x180027395  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x180027399  mov     [rbp+57h+SidToCheck], r14
0x18002739d  mov     [rbp+57h+IsMember], r14d
0x1800273a1  mov     [rbp+57h+TokenHandle], r14
0x1800273a5  call    ?ImpersonateAndGetToken@@YAJPEAPEAX@Z; ImpersonateAndGetToken(void * *)
0x1800273aa  test    eax, eax
0x1800273ac  jns     short loc_1800273B5
0x1800273ae  xor     eax, eax
0x1800273b0  jmp     loc_180027448
0x1800273b5  lea     rax, [rbp+57h+SidToCheck]
0x1800273b9  xor     r9d, r9d; nSubAuthority1
0x1800273bc  mov     [rsp+0B0h+pSid], rax; pSid
0x1800273c1  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800273c5  mov     [rsp+0B0h+nSubAuthority7], r14d; nSubAuthority7
0x1800273ca  mov     dl, 1; nSubAuthorityCount
0x1800273cc  mov     [rsp+0B0h+nSubAuthority6], r14d; nSubAuthority6
0x1800273d1  mov     [rsp+0B0h+nSubAuthority5], r14d; nSubAuthority5
0x1800273d6  lea     r8d, [r9+12h]; nSubAuthority0
0x1800273da  mov     [rsp+0B0h+nSubAuthority4], r14d; nSubAuthority4
0x1800273df  mov     [rsp+0B0h+nSubAuthority3], r14d; nSubAuthority3
0x1800273e4  mov     [rsp+0B0h+nSubAuthority2], r14d; nSubAuthority2
0x1800273e9  call    cs:__imp_AllocateAndInitializeSid
0x1800273ef  test    eax, eax
0x1800273f1  jz      short loc_180027419
0x1800273f3  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1800273f7  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800273fb  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800273ff  call    cs:__imp_CheckTokenMembership
0x180027405  test    eax, eax
0x180027407  jz      short loc_180027412
0x180027409  mov     edi, r14d
0x18002740c  cmp     [rbp+57h+IsMember], r14d
0x180027410  jnz     short loc_18002741E
0x180027412  mov     edi, 5
0x180027417  jmp     short loc_18002741E
0x180027419  mov     edi, 0Eh
0x18002741e  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x180027422  test    rcx, rcx
0x180027425  jz      short loc_18002742D
0x180027427  call    cs:__imp_FreeSid
0x18002742d  test    edi, edi
0x18002742f  mov     esi, r14d
0x180027432  setz    sil
0x180027436  cmp     [rbp+57h+TokenHandle], r14
0x18002743a  jz      short loc_180027446
0x18002743c  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180027440  call    cs:__imp_CloseHandle
0x180027446  mov     eax, esi
0x180027448  mov     rcx, [rbp+57h+var_30]
0x18002744c  xor     rcx, rsp; StackCookie
0x18002744f  call    __security_check_cookie
0x180027454  add     rsp, 98h
0x18002745b  pop     r14
0x18002745d  pop     rdi
0x18002745e  pop     rsi
0x18002745f  pop     rbp
0x180027460  retn
```
