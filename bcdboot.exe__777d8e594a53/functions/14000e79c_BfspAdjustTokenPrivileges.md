# BfspAdjustTokenPrivileges

- ea: `0x14000e79c`
- end: `0x14000e948`
- name: `BfspAdjustTokenPrivileges`
- size: `428`
- prototype: `__int64 __fastcall(PTOKEN_PRIVILEGES NewState, struct _TOKEN_PRIVILEGES **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140002928`
- `0x140009fd4`
- `0x14000c5e0`

## callees

- `0x14000e628`
- `0x14000e79c`
- `0x14000eb94`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000e929`
- `KERNEL32!SetLastError` at `0x14000e929`
- `KERNEL32!GetLastError` at `0x14000e7db`
- `KERNEL32!GetLastError` at `0x14000e871`
- `KERNEL32!GetLastError` at `0x14000e8db`
- `KERNEL32!GetLastError` at `0x14000e7db`
- `KERNEL32!GetLastError` at `0x14000e871`
- `KERNEL32!GetLastError` at `0x14000e8db`
- `KERNEL32!HeapFree` at `0x14000e88f`
- `KERNEL32!HeapFree` at `0x14000e921`
- `KERNEL32!HeapFree` at `0x14000e88f`
- `KERNEL32!HeapFree` at `0x14000e921`
- `KERNEL32!HeapAlloc` at `0x14000e826`
- `KERNEL32!HeapAlloc` at `0x14000e8a6`
- `KERNEL32!HeapAlloc` at `0x14000e826`
- `KERNEL32!HeapAlloc` at `0x14000e8a6`
- `KERNEL32!GetProcessHeap` at `0x14000e818`
- `KERNEL32!GetProcessHeap` at `0x14000e881`
- `KERNEL32!GetProcessHeap` at `0x14000e898`
- `KERNEL32!GetProcessHeap` at `0x14000e913`
- `KERNEL32!GetProcessHeap` at `0x14000e818`
- `KERNEL32!GetProcessHeap` at `0x14000e881`
- `KERNEL32!GetProcessHeap` at `0x14000e898`
- `KERNEL32!GetProcessHeap` at `0x14000e913`
- `KERNEL32!CloseHandle` at `0x14000e904`
- `KERNEL32!CloseHandle` at `0x14000e904`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14000e85c`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14000e8cf`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14000e85c`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14000e8cf`

## string_xrefs

- `0x14000e8e1`: `Failed to adjust token priveleges! Error code = %#x`
- `0x14000e7e1`: `Failed to get user token! Error code = %#x`

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
0x14000e79c  mov     [rsp-28h+arg_0], rbx
0x14000e7a1  mov     [rsp-28h+arg_8], rsi
0x14000e7a6  push    rbp
0x14000e7a7  push    rdi
0x14000e7a8  push    r12
0x14000e7aa  push    r14
0x14000e7ac  push    r15
0x14000e7ae  mov     rbp, rsp
0x14000e7b1  sub     rsp, 30h
0x14000e7b5  mov     r15, rcx
0x14000e7b8  mov     [rbp+BufferLength], 0
0x14000e7bf  lea     rcx, [rbp+TokenHandle]; TokenHandle
0x14000e7c3  mov     [rbp+TokenHandle], 0
0x14000e7cb  mov     r14, rdx
0x14000e7ce  call    BfspGetUserToken
0x14000e7d3  mov     edi, eax
0x14000e7d5  test    eax, eax
0x14000e7d7  jnz     short loc_14000E7FC
0x14000e7d9  xor     ebx, ebx
0x14000e7db  call    cs:__imp_GetLastError
0x14000e7e1  lea     rdx, aFailedToGetUse; "Failed to get user token! Error code = "...
0x14000e7e8  mov     r8d, eax
0x14000e7eb  mov     ecx, 4
0x14000e7f0  mov     esi, eax
0x14000e7f2  call    BfspLogMessage
0x14000e7f7  jmp     loc_14000E8FB
0x14000e7fc  mov     esi, 8
0x14000e801  test    r14, r14
0x14000e804  jz      short loc_14000E838
0x14000e806  mov     eax, [r15]
0x14000e809  lea     ecx, [rax+rax*2]
0x14000e80c  lea     ecx, ds:4[rcx*4]
0x14000e813  mov     [rbp+BufferLength], ecx
0x14000e816  mov     ebx, ecx
0x14000e818  call    cs:__imp_GetProcessHeap
0x14000e81e  mov     r8d, ebx; dwBytes
0x14000e821  mov     edx, esi; dwFlags
0x14000e823  mov     rcx, rax; hHeap
0x14000e826  call    cs:__imp_HeapAlloc
0x14000e82c  mov     r9d, [rbp+BufferLength]
0x14000e830  xor     r12d, r12d
0x14000e833  mov     rbx, rax
0x14000e836  jmp     short loc_14000E845
0x14000e838  xor     ebx, ebx
0x14000e83a  xor     r9d, r9d; BufferLength
0x14000e83d  mov     [rbp+BufferLength], r9d
0x14000e841  lea     r12d, [rbx+1]
0x14000e845  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14000e849  lea     rax, [rbp+BufferLength]
0x14000e84d  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14000e852  mov     r8, r15; NewState
0x14000e855  xor     edx, edx; DisableAllPrivileges
0x14000e857  mov     [rsp+30h+PreviousState], rbx; PreviousState
0x14000e85c  call    cs:__imp_AdjustTokenPrivileges
0x14000e862  mov     edi, eax
0x14000e864  test    r12d, r12d
0x14000e867  jnz     short loc_14000E8D7
0x14000e869  test    eax, eax
0x14000e86b  jnz     loc_14000E8F1
0x14000e871  call    cs:__imp_GetLastError
0x14000e877  cmp     eax, 7Ah ; 'z'
0x14000e87a  jnz     short loc_14000E8DB
0x14000e87c  test    rbx, rbx
0x14000e87f  jz      short loc_14000E895
0x14000e881  call    cs:__imp_GetProcessHeap
0x14000e887  mov     r8, rbx; lpMem
0x14000e88a  xor     edx, edx; dwFlags
0x14000e88c  mov     rcx, rax; hHeap
0x14000e88f  call    cs:__imp_HeapFree
0x14000e895  mov     ebx, [rbp+BufferLength]
0x14000e898  call    cs:__imp_GetProcessHeap
0x14000e89e  mov     r8d, ebx; dwBytes
0x14000e8a1  mov     edx, esi; dwFlags
0x14000e8a3  mov     rcx, rax; hHeap
0x14000e8a6  call    cs:__imp_HeapAlloc
0x14000e8ac  mov     rbx, rax
0x14000e8af  test    rax, rax
0x14000e8b2  jz      short loc_14000E8ED
0x14000e8b4  mov     r9d, [rbp+BufferLength]; BufferLength
0x14000e8b8  lea     rax, [rbp+BufferLength]
0x14000e8bc  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14000e8c0  mov     r8, r15; NewState
0x14000e8c3  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14000e8c8  xor     edx, edx; DisableAllPrivileges
0x14000e8ca  mov     [rsp+30h+PreviousState], rbx; PreviousState
0x14000e8cf  call    cs:__imp_AdjustTokenPrivileges
0x14000e8d5  mov     edi, eax
0x14000e8d7  test    edi, edi
0x14000e8d9  jnz     short loc_14000E8F1
0x14000e8db  call    cs:__imp_GetLastError
0x14000e8e1  lea     rdx, aFailedToAdjust; "Failed to adjust token priveleges! Erro"...
0x14000e8e8  jmp     loc_14000E7E8
0x14000e8ed  xor     edi, edi
0x14000e8ef  jmp     short loc_14000E8FB
0x14000e8f1  xor     esi, esi
0x14000e8f3  test    r14, r14
0x14000e8f6  jz      short loc_14000E8FB
0x14000e8f8  mov     [r14], rbx
0x14000e8fb  mov     rcx, [rbp+TokenHandle]; hObject
0x14000e8ff  test    rcx, rcx
0x14000e902  jz      short loc_14000E90A
0x14000e904  call    cs:__imp_CloseHandle
0x14000e90a  test    edi, edi
0x14000e90c  jnz     short loc_14000E92F
0x14000e90e  test    rbx, rbx
0x14000e911  jz      short loc_14000E927
0x14000e913  call    cs:__imp_GetProcessHeap
0x14000e919  mov     r8, rbx; lpMem
0x14000e91c  xor     edx, edx; dwFlags
0x14000e91e  mov     rcx, rax; hHeap
0x14000e921  call    cs:__imp_HeapFree
0x14000e927  mov     ecx, esi; dwErrCode
0x14000e929  call    cs:__imp_SetLastError
0x14000e92f  mov     rbx, [rsp+30h+arg_0]
0x14000e934  mov     eax, edi
0x14000e936  mov     rsi, [rsp+30h+arg_8]
0x14000e93b  add     rsp, 30h
0x14000e93f  pop     r15
0x14000e941  pop     r14
0x14000e943  pop     r12
0x14000e945  pop     rdi
0x14000e946  pop     rbp
0x14000e947  retn
```
