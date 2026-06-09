# Common::AutoNoImpersonateDuringScope::DropImpersonation(void)

- ea: `0x18003d814`
- end: `0x18003d8af`
- name: `?DropImpersonation@AutoNoImpersonateDuringScope@Common@@QEAAJXZ`
- size: `155`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800079d0`
- `0x18003bc00`
- `0x18003bec4`
- `0x180092880`
- `0x1800d8ea0`
- `0x1800dfbd0`
- `0x1800eb2e8`
- `0x180180350`
- `0x1801861f0`

## callees

- `0x18003d814`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d871`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003d861`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003d861`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003d846`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003d846`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003d88f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003d88f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d8a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d8a1`

## pseudocode

```c
signed int __fastcall Common::AutoNoImpersonateDuringScope::DropImpersonation(PHANDLE TokenHandle)
{
  signed int result; // eax
  char *v3; // rcx
  HANDLE CurrentThread; // rax

  if ( !NtCurrentTeb()->IsImpersonating )
    return 0;
  v3 = (char *)*TokenHandle;
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v3);
  *TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, TokenHandle) )
  {
    if ( SetThreadToken(0, 0) )
      return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18003d814  push    rbx
0x18003d816  sub     rsp, 20h
0x18003d81a  mov     eax, gs:179Ch
0x18003d822  mov     rbx, rcx
0x18003d825  test    eax, eax
0x18003d827  jnz     short loc_18003D832
0x18003d829  xor     eax, eax
0x18003d82b  add     rsp, 20h
0x18003d82f  pop     rbx
0x18003d830  retn
0x18003d832  mov     rcx, [rcx]; hObject
0x18003d835  lea     rax, [rcx-1]
0x18003d839  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003d83d  jbe     short loc_18003D8A1
0x18003d83f  mov     qword ptr [rbx], 0
0x18003d846  call    cs:__imp_GetCurrentThread
0x18003d84d  nop     dword ptr [rax+rax+00h]
0x18003d852  mov     edx, 4; DesiredAccess
0x18003d857  mov     r9, rbx; TokenHandle
0x18003d85a  mov     rcx, rax; ThreadHandle
0x18003d85d  lea     r8d, [rdx-3]; OpenAsSelf
0x18003d861  call    cs:__imp_OpenThreadToken
0x18003d868  nop     dword ptr [rax+rax+00h]
0x18003d86d  test    eax, eax
0x18003d86f  jnz     short loc_18003D88B
0x18003d871  call    cs:__imp_GetLastError
0x18003d878  nop     dword ptr [rax+rax+00h]
0x18003d87d  test    eax, eax
0x18003d87f  jle     short loc_18003D82B
0x18003d881  movzx   eax, ax
0x18003d884  or      eax, 80070000h
0x18003d889  jmp     short loc_18003D82B
0x18003d88b  xor     edx, edx; Token
0x18003d88d  xor     ecx, ecx; Thread
0x18003d88f  call    cs:__imp_SetThreadToken
0x18003d896  nop     dword ptr [rax+rax+00h]
0x18003d89b  test    eax, eax
0x18003d89d  jnz     short loc_18003D829
0x18003d89f  jmp     short loc_18003D871
0x18003d8a1  call    cs:__imp_CloseHandle
0x18003d8a8  nop     dword ptr [rax+rax+00h]
0x18003d8ad  jmp     short loc_18003D83F
```
