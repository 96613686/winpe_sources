# ImpersonateOther_Save(void *,SavedImpersonationState &)

- ea: `0x180011420`
- end: `0x1800114d6`
- name: `?ImpersonateOther_Save@@YAJPEAXAEAUSavedImpersonationState@@@Z`
- size: `182`
- prototype: `__int64 __fastcall(HANDLE Token, struct SavedImpersonationState *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800116d8`
- `0x180025350`

## callees

- `0x180011420`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011479`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011479`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011448`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011448`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001145d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001145d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800114b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800114b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800114c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800114c7`

## pseudocode

```c
signed int __fastcall ImpersonateOther_Save(HANDLE Token, struct SavedImpersonationState *a2)
{
  HANDLE *v2; // rdi
  HANDLE CurrentThread; // rax
  signed int result; // eax
  signed int LastError; // ebx

  *(_BYTE *)a2 = 0;
  v2 = (HANDLE *)((char *)a2 + 8);
  *((_QWORD *)a2 + 1) = 0;
  if ( !Token )
    return 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, v2) || (result = GetLastError(), result == 1008) )
  {
    if ( SetThreadToken(0, Token) )
    {
      *(_BYTE *)a2 = 1;
      return 0;
    }
    LastError = GetLastError();
    if ( *v2 )
    {
      CloseHandle(*v2);
      *v2 = 0;
    }
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return LastError;
  }
  else if ( result > 0 )
  {
    return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180011420  mov     [rsp+arg_0], rbx
0x180011425  mov     [rsp+arg_8], rsi
0x18001142a  push    rdi
0x18001142b  sub     rsp, 20h
0x18001142f  mov     byte ptr [rdx], 0
0x180011432  lea     rdi, [rdx+8]
0x180011436  mov     qword ptr [rdi], 0
0x18001143d  mov     rbx, rdx
0x180011440  mov     rsi, rcx
0x180011443  test    rcx, rcx
0x180011446  jz      short loc_180011486
0x180011448  call    cs:__imp_GetCurrentThread
0x18001144e  mov     edx, 4; DesiredAccess
0x180011453  mov     r9, rdi; TokenHandle
0x180011456  mov     rcx, rax; ThreadHandle
0x180011459  lea     r8d, [rdx-3]; OpenAsSelf
0x18001145d  call    cs:__imp_OpenThreadToken
0x180011463  test    eax, eax
0x180011465  jnz     short loc_180011474
0x180011467  call    cs:__imp_GetLastError
0x18001146d  cmp     eax, 3F0h
0x180011472  jnz     short loc_180011498
0x180011474  mov     rdx, rsi; Token
0x180011477  xor     ecx, ecx; Thread
0x180011479  call    cs:__imp_SetThreadToken
0x18001147f  test    eax, eax
0x180011481  jz      short loc_1800114B7
0x180011483  mov     byte ptr [rbx], 1
0x180011486  xor     eax, eax
0x180011488  mov     rbx, [rsp+28h+arg_0]
0x18001148d  mov     rsi, [rsp+28h+arg_8]
0x180011492  add     rsp, 20h
0x180011496  pop     rdi
0x180011497  retn
0x180011498  test    eax, eax
0x18001149a  jle     short loc_180011488
0x18001149c  movzx   eax, ax
0x18001149f  or      eax, 80070000h
0x1800114a4  jmp     short loc_180011488
0x1800114a6  test    ebx, ebx
0x1800114a8  jle     short loc_1800114B3
0x1800114aa  movzx   ebx, bx
0x1800114ad  or      ebx, 80070000h
0x1800114b3  mov     eax, ebx
0x1800114b5  jmp     short loc_180011488
0x1800114b7  call    cs:__imp_GetLastError
0x1800114bd  mov     rcx, [rdi]; hObject
0x1800114c0  mov     ebx, eax
0x1800114c2  test    rcx, rcx
0x1800114c5  jz      short loc_1800114A6
0x1800114c7  call    cs:__imp_CloseHandle
0x1800114cd  mov     qword ptr [rdi], 0
0x1800114d4  jmp     short loc_1800114A6
```
