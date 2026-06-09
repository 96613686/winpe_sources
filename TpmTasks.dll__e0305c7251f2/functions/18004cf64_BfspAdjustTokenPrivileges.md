# BfspAdjustTokenPrivileges

- ea: `0x18004cf64`
- end: `0x18004d110`
- name: `BfspAdjustTokenPrivileges`
- size: `428`
- prototype: `__int64 __fastcall(PTOKEN_PRIVILEGES NewState)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004646c`
- `0x180049234`
- `0x18004b38c`

## callees

- `0x18004cdd4`
- `0x18004cf64`
- `0x18004d35c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d057`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d0e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d057`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d0e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cfe0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d049`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d060`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d0db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cfe0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d049`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d060`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d0db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cfee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d06e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cfee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d06e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d0f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d0f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cfa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d0a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cfa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d0a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d0cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d0cc`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18004d024`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18004d097`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18004d024`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18004d097`

## string_xrefs

- `0x18004d0a9`: `Failed to adjust token priveleges! Error code = %#x`
- `0x18004cfa9`: `Failed to get user token! Error code = %#x`

## pseudocode

```c
__int64 __fastcall BfspAdjustTokenPrivileges(PTOKEN_PRIVILEGES NewState, struct _TOKEN_PRIVILEGES **a2)
{
  unsigned int UserToken; // edi
  struct _TOKEN_PRIVILEGES *PreviousState; // rbx
  DWORD LastError; // eax
  const wchar_t *v7; // rdx
  DWORD v8; // esi
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  struct _TOKEN_PRIVILEGES *v11; // rax
  DWORD v12; // r9d
  int v13; // r12d
  BOOL v14; // eax
  HANDLE v15; // rax
  DWORD v16; // ebx
  HANDLE v17; // rax
  HANDLE v18; // rax
  DWORD BufferLength; // [rsp+70h] [rbp+40h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp+48h] BYREF

  BufferLength = 0;
  TokenHandle = 0;
  UserToken = BfspGetUserToken(&TokenHandle);
  if ( !UserToken )
  {
    PreviousState = 0;
    LastError = GetLastError();
    v7 = L"Failed to get user token! Error code = %#x";
LABEL_3:
    v8 = LastError;
    BfspLogMessage(4, v7, LastError);
    goto LABEL_19;
  }
  v8 = 8;
  if ( a2 )
  {
    BufferLength = 12 * NewState->PrivilegeCount + 4;
    v9 = BufferLength;
    ProcessHeap = GetProcessHeap();
    v11 = (struct _TOKEN_PRIVILEGES *)HeapAlloc(ProcessHeap, 8u, v9);
    v12 = BufferLength;
    v13 = 0;
    PreviousState = v11;
  }
  else
  {
    PreviousState = 0;
    v12 = 0;
    BufferLength = 0;
    v13 = 1;
  }
  v14 = AdjustTokenPrivileges(TokenHandle, 0, NewState, v12, PreviousState, &BufferLength);
  UserToken = v14;
  if ( v13 )
  {
LABEL_14:
    if ( !UserToken )
      goto LABEL_15;
    goto LABEL_17;
  }
  if ( !v14 )
  {
    if ( GetLastError() != 122 )
    {
LABEL_15:
      LastError = GetLastError();
      v7 = L"Failed to adjust token priveleges! Error code = %#x";
      goto LABEL_3;
    }
    if ( PreviousState )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, PreviousState);
    }
    v16 = BufferLength;
    v17 = GetProcessHeap();
    PreviousState = (struct _TOKEN_PRIVILEGES *)HeapAlloc(v17, 8u, v16);
    if ( !PreviousState )
    {
      UserToken = 0;
      goto LABEL_19;
    }
    UserToken = AdjustTokenPrivileges(TokenHandle, 0, NewState, BufferLength, PreviousState, &BufferLength);
    goto LABEL_14;
  }
LABEL_17:
  v8 = 0;
  if ( a2 )
    *a2 = PreviousState;
LABEL_19:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( !UserToken )
  {
    if ( PreviousState )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, PreviousState);
    }
    SetLastError(v8);
  }
  return UserToken;
}

```

## disassembly

```asm
0x18004cf64  mov     [rsp-28h+arg_0], rbx
0x18004cf69  mov     [rsp-28h+arg_8], rsi
0x18004cf6e  push    rbp
0x18004cf6f  push    rdi
0x18004cf70  push    r12
0x18004cf72  push    r14
0x18004cf74  push    r15
0x18004cf76  mov     rbp, rsp
0x18004cf79  sub     rsp, 30h
0x18004cf7d  mov     r15, rcx
0x18004cf80  mov     [rbp+BufferLength], 0
0x18004cf87  lea     rcx, [rbp+TokenHandle]; TokenHandle
0x18004cf8b  mov     [rbp+TokenHandle], 0
0x18004cf93  mov     r14, rdx
0x18004cf96  call    BfspGetUserToken
0x18004cf9b  mov     edi, eax
0x18004cf9d  test    eax, eax
0x18004cf9f  jnz     short loc_18004CFC4
0x18004cfa1  xor     ebx, ebx
0x18004cfa3  call    cs:__imp_GetLastError
0x18004cfa9  lea     rdx, aFailedToGetUse; "Failed to get user token! Error code = "...
0x18004cfb0  mov     r8d, eax
0x18004cfb3  mov     ecx, 4
0x18004cfb8  mov     esi, eax
0x18004cfba  call    BfspLogMessage
0x18004cfbf  jmp     loc_18004D0C3
0x18004cfc4  mov     esi, 8
0x18004cfc9  test    r14, r14
0x18004cfcc  jz      short loc_18004D000
0x18004cfce  mov     eax, [r15]
0x18004cfd1  lea     ecx, [rax+rax*2]
0x18004cfd4  lea     ecx, ds:4[rcx*4]
0x18004cfdb  mov     [rbp+BufferLength], ecx
0x18004cfde  mov     ebx, ecx
0x18004cfe0  call    cs:__imp_GetProcessHeap
0x18004cfe6  mov     r8d, ebx; dwBytes
0x18004cfe9  mov     edx, esi; dwFlags
0x18004cfeb  mov     rcx, rax; hHeap
0x18004cfee  call    cs:__imp_HeapAlloc
0x18004cff4  mov     r9d, [rbp+BufferLength]
0x18004cff8  xor     r12d, r12d
0x18004cffb  mov     rbx, rax
0x18004cffe  jmp     short loc_18004D00D
0x18004d000  xor     ebx, ebx
0x18004d002  xor     r9d, r9d; BufferLength
0x18004d005  mov     [rbp+BufferLength], r9d
0x18004d009  lea     r12d, [rbx+1]
0x18004d00d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004d011  lea     rax, [rbp+BufferLength]
0x18004d015  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18004d01a  mov     r8, r15; NewState
0x18004d01d  xor     edx, edx; DisableAllPrivileges
0x18004d01f  mov     [rsp+30h+PreviousState], rbx; PreviousState
0x18004d024  call    cs:__imp_AdjustTokenPrivileges
0x18004d02a  mov     edi, eax
0x18004d02c  test    r12d, r12d
0x18004d02f  jnz     short loc_18004D09F
0x18004d031  test    eax, eax
0x18004d033  jnz     loc_18004D0B9
0x18004d039  call    cs:__imp_GetLastError
0x18004d03f  cmp     eax, 7Ah ; 'z'
0x18004d042  jnz     short loc_18004D0A3
0x18004d044  test    rbx, rbx
0x18004d047  jz      short loc_18004D05D
0x18004d049  call    cs:__imp_GetProcessHeap
0x18004d04f  mov     r8, rbx; lpMem
0x18004d052  xor     edx, edx; dwFlags
0x18004d054  mov     rcx, rax; hHeap
0x18004d057  call    cs:__imp_HeapFree
0x18004d05d  mov     ebx, [rbp+BufferLength]
0x18004d060  call    cs:__imp_GetProcessHeap
0x18004d066  mov     r8d, ebx; dwBytes
0x18004d069  mov     edx, esi; dwFlags
0x18004d06b  mov     rcx, rax; hHeap
0x18004d06e  call    cs:__imp_HeapAlloc
0x18004d074  mov     rbx, rax
0x18004d077  test    rax, rax
0x18004d07a  jz      short loc_18004D0B5
0x18004d07c  mov     r9d, [rbp+BufferLength]; BufferLength
0x18004d080  lea     rax, [rbp+BufferLength]
0x18004d084  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004d088  mov     r8, r15; NewState
0x18004d08b  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18004d090  xor     edx, edx; DisableAllPrivileges
0x18004d092  mov     [rsp+30h+PreviousState], rbx; PreviousState
0x18004d097  call    cs:__imp_AdjustTokenPrivileges
0x18004d09d  mov     edi, eax
0x18004d09f  test    edi, edi
0x18004d0a1  jnz     short loc_18004D0B9
0x18004d0a3  call    cs:__imp_GetLastError
0x18004d0a9  lea     rdx, aFailedToAdjust; "Failed to adjust token priveleges! Erro"...
0x18004d0b0  jmp     loc_18004CFB0
0x18004d0b5  xor     edi, edi
0x18004d0b7  jmp     short loc_18004D0C3
0x18004d0b9  xor     esi, esi
0x18004d0bb  test    r14, r14
0x18004d0be  jz      short loc_18004D0C3
0x18004d0c0  mov     [r14], rbx
0x18004d0c3  mov     rcx, [rbp+TokenHandle]; hObject
0x18004d0c7  test    rcx, rcx
0x18004d0ca  jz      short loc_18004D0D2
0x18004d0cc  call    cs:__imp_CloseHandle
0x18004d0d2  test    edi, edi
0x18004d0d4  jnz     short loc_18004D0F7
0x18004d0d6  test    rbx, rbx
0x18004d0d9  jz      short loc_18004D0EF
0x18004d0db  call    cs:__imp_GetProcessHeap
0x18004d0e1  mov     r8, rbx; lpMem
0x18004d0e4  xor     edx, edx; dwFlags
0x18004d0e6  mov     rcx, rax; hHeap
0x18004d0e9  call    cs:__imp_HeapFree
0x18004d0ef  mov     ecx, esi; dwErrCode
0x18004d0f1  call    cs:__imp_SetLastError
0x18004d0f7  mov     rbx, [rsp+30h+arg_0]
0x18004d0fc  mov     eax, edi
0x18004d0fe  mov     rsi, [rsp+30h+arg_8]
0x18004d103  add     rsp, 30h
0x18004d107  pop     r15
0x18004d109  pop     r14
0x18004d10b  pop     r12
0x18004d10d  pop     rdi
0x18004d10e  pop     rbp
0x18004d10f  retn
```
