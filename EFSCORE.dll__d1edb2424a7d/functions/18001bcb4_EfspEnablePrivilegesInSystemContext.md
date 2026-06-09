# EfspEnablePrivilegesInSystemContext

- ea: `0x18001bcb4`
- end: `0x18001bf16`
- name: `EfspEnablePrivilegesInSystemContext`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001cdb0`

## callees

- `0x1800102f0`
- `0x180010bf0`
- `0x18001bcb4`
- `0x180063698`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bde2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bde2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bdc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bdc7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001bdd8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001bdd8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001be8b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001be8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bebc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001becc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bebc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001becc`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001be0e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001be0e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001be4a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001be4a`
- `RPCRT4!RpcRevertToSelf` at `0x18001bd6c`
- `RPCRT4!RpcRevertToSelf` at `0x18001bd6c`
- `RPCRT4!RpcImpersonateClient` at `0x18001bedc`
- `RPCRT4!RpcImpersonateClient` at `0x18001bedc`

## pseudocode

```c
__int64 __fastcall EfspEnablePrivilegesInSystemContext(int *a1)
{
  int v1; // ebp
  char *v3; // rax
  struct _TOKEN_PRIVILEGES *v4; // rsi
  unsigned int v5; // ebx
  int v6; // eax
  DWORD LastError; // eax
  char v8; // r14
  int v9; // eax
  HANDLE CurrentProcess; // rax
  RPC_STATUS v11; // eax
  HANDLE Token; // [rsp+60h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+18h] BYREF
  __int64 v15; // [rsp+78h] [rbp+20h]

  v1 = 0;
  TokenHandle = 0;
  Token = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
  v3 = (char *)wil::details::heap_allocator::allocate(0x10u);
  v4 = (struct _TOKEN_PRIVILEGES *)v3;
  if ( !v3 )
  {
    v5 = 8;
    v6 = fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, 16, 10, 154);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v6, 10, 154);
    goto LABEL_20;
  }
  *(_DWORD *)v3 = 1;
  *((_DWORD *)v3 + 3) = 2;
  v15 = *a1;
  *(_QWORD *)(v3 + 4) = (int)v15;
  LastError = RpcRevertToSelf();
  if ( LastError )
  {
    v5 = 1008;
    v8 = -83;
  }
  else
  {
    v1 = 1;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x2Eu, &TokenHandle) )
    {
      if ( DuplicateTokenEx(TokenHandle, 0, 0, SecurityImpersonation, TokenImpersonation, &Token) )
      {
        if ( AdjustTokenPrivileges(Token, 0, v4, 0, 0, 0) )
        {
          if ( GetLastError() )
          {
            LastError = GetLastError();
            v5 = LastError;
            v8 = -33;
          }
          else
          {
            if ( SetThreadToken(0, Token) )
            {
              v5 = 0;
              goto LABEL_19;
            }
            LastError = GetLastError();
            v5 = LastError;
            v8 = -23;
          }
        }
        else
        {
          LastError = GetLastError();
          v5 = LastError;
          v8 = -45;
        }
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        v8 = -56;
      }
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      v8 = -67;
    }
  }
  v9 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 10, v8);
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v9, 10, v8);
LABEL_19:
  EfsFreeHeap(v4);
LABEL_20:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( Token )
    CloseHandle(Token);
  if ( v5 )
  {
    if ( v1 )
    {
      v11 = RpcImpersonateClient(0);
      if ( v11 )
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v11, 10, 4);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001bcb4  mov     [rsp+arg_8], rbx
0x18001bcb9  push    rbp
0x18001bcba  push    rsi
0x18001bcbb  push    rdi
0x18001bcbc  push    r12
0x18001bcbe  push    r14
0x18001bcc0  sub     rsp, 30h
0x18001bcc4  xor     ebp, ebp
0x18001bcc6  mov     rbx, rcx
0x18001bcc9  mov     [rsp+58h+TokenHandle], rbp
0x18001bcce  mov     [rsp+58h+Token], rbp
0x18001bcd3  test    rcx, rcx
0x18001bcd6  jnz     short loc_18001BCDD
0x18001bcd8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "rgulPrivileges != NULL")
0x18001bcdd  mov     r14d, 10h
0x18001bce3  mov     ecx, r14d; unsigned __int64
0x18001bce6  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x18001bceb  lea     r12, EFS_API_ERROR
0x18001bcf2  mov     rsi, rax
0x18001bcf5  test    rax, rax
0x18001bcf8  jnz     short loc_18001BD44
0x18001bcfa  mov     rcx, cs:g_hPublisher
0x18001bd01  lea     edi, [rax+0Ah]
0x18001bd04  mov     esi, 0F9Ah
0x18001bd09  lea     rdx, EFS_ERROR_MEMORY
0x18001bd10  mov     r9d, edi
0x18001bd13  mov     [rsp+58h+TokenType], esi
0x18001bd17  mov     r8d, r14d
0x18001bd1a  lea     ebx, [rax+8]
0x18001bd1d  call    fnEfsLogTrace1
0x18001bd22  mov     rcx, cs:g_hPublisher
0x18001bd29  lea     rdx, EFS_TRACE_ERROR
0x18001bd30  mov     r9d, edi
0x18001bd33  mov     [rsp+58h+TokenType], esi
0x18001bd37  mov     r8d, eax
0x18001bd3a  call    fnEfsLogTrace1
0x18001bd3f  jmp     loc_18001BEB2
0x18001bd44  mov     dword ptr [rax], 1
0x18001bd4a  mov     r14d, 2
0x18001bd50  mov     [rax+0Ch], r14d
0x18001bd54  movsxd  rax, dword ptr [rbx]
0x18001bd57  mov     dword ptr [rsp+58h+arg_18], eax
0x18001bd5b  shr     rax, 20h
0x18001bd5f  mov     dword ptr [rsp+58h+arg_18+4], eax
0x18001bd63  mov     rax, [rsp+58h+arg_18]
0x18001bd68  mov     [rsi+4], rax
0x18001bd6c  call    cs:__imp_RpcRevertToSelf
0x18001bd72  lea     edi, [r14+8]
0x18001bd76  test    eax, eax
0x18001bd78  jz      short loc_18001BDC2
0x18001bd7a  mov     ebx, 3F0h
0x18001bd7f  mov     r14d, 0FADh
0x18001bd85  mov     rcx, cs:g_hPublisher
0x18001bd8c  mov     r9d, edi
0x18001bd8f  mov     r8d, eax
0x18001bd92  mov     [rsp+58h+TokenType], r14d
0x18001bd97  mov     rdx, r12
0x18001bd9a  call    fnEfsLogTrace1
0x18001bd9f  mov     rcx, cs:g_hPublisher
0x18001bda6  lea     rdx, EFS_TRACE_ERROR
0x18001bdad  mov     r9d, edi
0x18001bdb0  mov     [rsp+58h+TokenType], r14d
0x18001bdb5  mov     r8d, eax
0x18001bdb8  call    fnEfsLogTrace1
0x18001bdbd  jmp     loc_18001BEAA
0x18001bdc2  mov     ebp, 1
0x18001bdc7  call    cs:__imp_GetCurrentProcess
0x18001bdcd  mov     rcx, rax; ProcessHandle
0x18001bdd0  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18001bdd5  lea     edx, [rbp+2Dh]; DesiredAccess
0x18001bdd8  call    cs:__imp_OpenProcessToken
0x18001bdde  test    eax, eax
0x18001bde0  jnz     short loc_18001BDF2
0x18001bde2  call    cs:__imp_GetLastError
0x18001bde8  mov     ebx, eax
0x18001bdea  mov     r14d, 0FBDh
0x18001bdf0  jmp     short loc_18001BD85
0x18001bdf2  mov     rcx, [rsp+58h+TokenHandle]; hExistingToken
0x18001bdf7  lea     rax, [rsp+58h+Token]
0x18001bdfc  mov     [rsp+58h+phNewToken], rax; phNewToken
0x18001be01  mov     r9d, r14d; ImpersonationLevel
0x18001be04  xor     r8d, r8d; lpTokenAttributes
0x18001be07  mov     [rsp+58h+TokenType], r14d; TokenType
0x18001be0c  xor     edx, edx; dwDesiredAccess
0x18001be0e  call    cs:__imp_DuplicateTokenEx
0x18001be14  test    eax, eax
0x18001be16  jnz     short loc_18001BE2B
0x18001be18  call    cs:__imp_GetLastError
0x18001be1e  mov     ebx, eax
0x18001be20  mov     r14d, 0FC8h
0x18001be26  jmp     loc_18001BD85
0x18001be2b  mov     rcx, [rsp+58h+Token]; TokenHandle
0x18001be30  xor     r9d, r9d; BufferLength
0x18001be33  mov     [rsp+58h+phNewToken], 0; ReturnLength
0x18001be3c  mov     r8, rsi; NewState
0x18001be3f  xor     edx, edx; DisableAllPrivileges
0x18001be41  mov     qword ptr [rsp+58h+TokenType], 0; PreviousState
0x18001be4a  call    cs:__imp_AdjustTokenPrivileges
0x18001be50  test    eax, eax
0x18001be52  jnz     short loc_18001BE67
0x18001be54  call    cs:__imp_GetLastError
0x18001be5a  mov     ebx, eax
0x18001be5c  mov     r14d, 0FD3h
0x18001be62  jmp     loc_18001BD85
0x18001be67  call    cs:__imp_GetLastError
0x18001be6d  test    eax, eax
0x18001be6f  jz      short loc_18001BE84
0x18001be71  call    cs:__imp_GetLastError
0x18001be77  mov     ebx, eax
0x18001be79  mov     r14d, 0FDFh
0x18001be7f  jmp     loc_18001BD85
0x18001be84  mov     rdx, [rsp+58h+Token]; Token
0x18001be89  xor     ecx, ecx; Thread
0x18001be8b  call    cs:__imp_SetThreadToken
0x18001be91  test    eax, eax
0x18001be93  jnz     short loc_18001BEA8
0x18001be95  call    cs:__imp_GetLastError
0x18001be9b  mov     ebx, eax
0x18001be9d  mov     r14d, 0FE9h
0x18001bea3  jmp     loc_18001BD85
0x18001bea8  xor     ebx, ebx
0x18001beaa  mov     rcx, rsi; lpMem
0x18001bead  call    EfsFreeHeap
0x18001beb2  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18001beb7  test    rcx, rcx
0x18001beba  jz      short loc_18001BEC2
0x18001bebc  call    cs:__imp_CloseHandle
0x18001bec2  mov     rcx, [rsp+58h+Token]; hObject
0x18001bec7  test    rcx, rcx
0x18001beca  jz      short loc_18001BED2
0x18001becc  call    cs:__imp_CloseHandle
0x18001bed2  test    ebx, ebx
0x18001bed4  jz      short loc_18001BF03
0x18001bed6  test    ebp, ebp
0x18001bed8  jz      short loc_18001BF03
0x18001beda  xor     ecx, ecx; BindingHandle
0x18001bedc  call    cs:__imp_RpcImpersonateClient
0x18001bee2  test    eax, eax
0x18001bee4  jz      short loc_18001BF03
0x18001bee6  mov     rcx, cs:g_hPublisher
0x18001beed  mov     r9d, edi
0x18001bef0  mov     r8d, eax
0x18001bef3  mov     [rsp+58h+TokenType], 1004h
0x18001befb  mov     rdx, r12
0x18001befe  call    fnEfsLogTrace1
0x18001bf03  mov     eax, ebx
0x18001bf05  mov     rbx, [rsp+58h+arg_8]
0x18001bf0a  add     rsp, 30h
0x18001bf0e  pop     r14
0x18001bf10  pop     r12
0x18001bf12  pop     rdi
0x18001bf13  pop     rsi
0x18001bf14  pop     rbp
0x18001bf15  retn
```
