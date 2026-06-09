# enter_thread_access_token_context

- ea: `0x18005800c`
- end: `0x1800580ae`
- name: `enter_thread_access_token_context`
- size: `162`
- prototype: `DWORD __fastcall(HANDLE hToken, __int64)`
- caller_count: `12`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180057f68`
- `0x1800686c0`
- `0x180068790`
- `0x180068880`
- `0x1800689a0`
- `0x180068af0`
- `0x180068c20`
- `0x180068e60`
- `0x180068f60`
- `0x1800690b0`
- `0x1800a7070`
- `0x1800a7180`

## callees

- `0x18005800c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180058048`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180058048`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005802f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005802f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058098`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005806b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005806b`

## pseudocode

```c
DWORD __fastcall enter_thread_access_token_context(HANDLE hToken, __int64 a2)
{
  HANDLE CurrentThread; // rax
  char v5; // di
  DWORD result; // eax
  HANDLE v7; // rbx
  HANDLE TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  TokenHandle = 0;
  *(_OWORD *)a2 = xmmword_1800B6698;
  CurrentThread = GetCurrentThread();
  v5 = 1;
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    v7 = TokenHandle;
  }
  else
  {
    result = GetLastError();
    if ( result == 1008 )
    {
      v7 = 0;
      v5 = 0;
    }
    else
    {
      if ( result )
        return result;
      v5 = 0;
      v7 = 0;
    }
  }
  if ( !ImpersonateLoggedOnUser(hToken) )
    return GetLastError();
  *(_QWORD *)(a2 + 8) = v7;
  *(_DWORD *)(a2 + 1) = 0;
  *(_WORD *)(a2 + 5) = 0;
  *(_BYTE *)a2 = v5 == 0;
  result = 0;
  *(_BYTE *)(a2 + 7) = 0;
  return result;
}

```

## disassembly

```asm
0x18005800c  push    rbx
0x18005800e  push    rbp
0x18005800f  push    rsi
0x180058010  push    rdi
0x180058011  sub     rsp, 28h
0x180058015  movups  xmm0, cs:xmmword_1800B6698
0x18005801c  mov     rsi, rdx
0x18005801f  mov     [rsp+48h+TokenHandle], 0
0x180058028  mov     rbp, rcx
0x18005802b  movdqu  xmmword ptr [rdx], xmm0
0x18005802f  call    cs:__imp_GetCurrentThread
0x180058035  mov     edi, 1
0x18005803a  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18005803f  mov     rcx, rax; ThreadHandle
0x180058042  mov     r8d, edi; OpenAsSelf
0x180058045  lea     edx, [rdi+0Bh]; DesiredAccess
0x180058048  call    cs:__imp_OpenThreadToken
0x18005804e  test    eax, eax
0x180058050  jnz     short loc_1800580A0
0x180058052  call    cs:__imp_GetLastError
0x180058058  cmp     eax, 3F0h
0x18005805d  jz      short loc_1800580A7
0x18005805f  test    eax, eax
0x180058061  jnz     short loc_18005808F
0x180058063  xor     dil, dil
0x180058066  xor     ebx, ebx
0x180058068  mov     rcx, rbp; hToken
0x18005806b  call    cs:__imp_ImpersonateLoggedOnUser
0x180058071  test    eax, eax
0x180058073  jz      short loc_180058098
0x180058075  test    dil, dil
0x180058078  mov     [rsi+8], rbx
0x18005807c  setz    al
0x18005807f  xor     ecx, ecx
0x180058081  mov     [rsi+1], ecx
0x180058084  mov     [rsi+5], cx
0x180058088  mov     [rsi], al
0x18005808a  xor     eax, eax
0x18005808c  mov     [rsi+7], cl
0x18005808f  add     rsp, 28h
0x180058093  pop     rdi
0x180058094  pop     rsi
0x180058095  pop     rbp
0x180058096  pop     rbx
0x180058097  retn
0x180058098  call    cs:__imp_GetLastError
0x18005809e  jmp     short loc_18005808F
0x1800580a0  mov     rbx, [rsp+48h+TokenHandle]
0x1800580a5  jmp     short loc_180058068
0x1800580a7  xor     ebx, ebx
0x1800580a9  xor     dil, dil
0x1800580ac  jmp     short loc_180058068
```
