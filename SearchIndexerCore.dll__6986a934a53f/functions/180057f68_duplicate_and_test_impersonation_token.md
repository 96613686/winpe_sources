# duplicate_and_test_impersonation_token

- ea: `0x180057f68`
- end: `0x180058006`
- name: `duplicate_and_test_impersonation_token`
- size: `158`
- prototype: `DWORD __fastcall(void *, HANDLE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180068520`

## callees

- `0x180057f68`
- `0x18005800c`
- `0x1800580b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057fe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057fe9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057fdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057fdb`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180057f8f`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180057f8f`

## pseudocode

```c
DWORD __fastcall duplicate_and_test_impersonation_token(void *a1, HANDLE *a2)
{
  int v3; // ebx
  __int128 v5; // [rsp+20h] [rbp-18h] BYREF
  HANDLE DuplicateTokenHandle; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  DuplicateTokenHandle = 0;
  if ( !DuplicateToken(a1, SecurityImpersonation, &DuplicateTokenHandle) )
    return GetLastError();
  v5 = xmmword_1800B6698;
  v3 = enter_thread_access_token_context(DuplicateTokenHandle);
  if ( v3 || (v3 = exit_thread_access_token_context(&v5)) != 0 )
  {
    if ( CloseHandle(DuplicateTokenHandle) )
      return v3;
    return GetLastError();
  }
  *a2 = DuplicateTokenHandle;
  return 0;
}

```

## disassembly

```asm
0x180057f68  mov     [rsp+arg_0], rbx
0x180057f6d  push    rdi
0x180057f6e  sub     rsp, 30h
0x180057f72  mov     rdi, rdx
0x180057f75  mov     qword ptr [rdx], 0
0x180057f7c  mov     edx, 2; ImpersonationLevel
0x180057f81  mov     [rsp+38h+DuplicateTokenHandle], 0
0x180057f8a  lea     r8, [rsp+38h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180057f8f  call    cs:__imp_DuplicateToken
0x180057f95  test    eax, eax
0x180057f97  jz      short loc_180057FE9
0x180057f99  movups  xmm0, cs:xmmword_1800B6698
0x180057fa0  mov     rcx, [rsp+38h+DuplicateTokenHandle]; hToken
0x180057fa5  lea     rdx, [rsp+38h+var_18]
0x180057faa  movdqu  [rsp+38h+var_18], xmm0
0x180057fb0  call    enter_thread_access_token_context
0x180057fb5  mov     ebx, eax
0x180057fb7  test    eax, eax
0x180057fb9  jnz     short loc_180057FD6
0x180057fbb  movaps  xmm0, [rsp+38h+var_18]
0x180057fc0  lea     rcx, [rsp+38h+var_18]
0x180057fc5  movdqa  [rsp+38h+var_18], xmm0
0x180057fcb  call    exit_thread_access_token_context
0x180057fd0  mov     ebx, eax
0x180057fd2  test    eax, eax
0x180057fd4  jz      short loc_180057FF1
0x180057fd6  mov     rcx, [rsp+38h+DuplicateTokenHandle]; hObject
0x180057fdb  call    cs:__imp_CloseHandle
0x180057fe1  test    eax, eax
0x180057fe3  jz      short loc_180057FE9
0x180057fe5  mov     eax, ebx
0x180057fe7  jmp     short loc_180057FFB
0x180057fe9  call    cs:__imp_GetLastError
0x180057fef  jmp     short loc_180057FFB
0x180057ff1  mov     rax, [rsp+38h+DuplicateTokenHandle]
0x180057ff6  mov     [rdi], rax
0x180057ff9  xor     eax, eax
0x180057ffb  mov     rbx, [rsp+38h+arg_0]
0x180058000  add     rsp, 30h
0x180058004  pop     rdi
0x180058005  retn
```
