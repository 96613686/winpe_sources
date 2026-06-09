# IsBeingDebugged(ulong)

- ea: `0x140019b6c`
- end: `0x140019c6a`
- name: `?IsBeingDebugged@@YAHK@Z`
- size: `254`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14001a274`

## callees

- `0x140014f14`
- `0x140019b6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019bd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019c2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019bd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019c2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019c06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019c06`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140019b86`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140019b86`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x140019ba7`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x140019ba7`

## pseudocode

```c
__int64 __fastcall IsBeingDebugged(DWORD dwProcessId)
{
  unsigned int v1; // ebx
  HANDLE v2; // rax
  void *v3; // rdi
  DWORD v4; // eax
  DWORD LastError; // eax
  WINBOOL pbDebuggerPresent; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  pbDebuggerPresent = 0;
  v2 = OpenProcess(0x400u, 0, dwProcessId);
  v3 = v2;
  if ( (unsigned __int64)v2 + 1 <= 1 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids, LastError);
    }
    return (unsigned int)pbDebuggerPresent;
  }
  else
  {
    if ( CheckRemoteDebuggerPresent(v2, &pbDebuggerPresent) )
    {
      v1 = pbDebuggerPresent;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v4 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids, v4);
      }
      pbDebuggerPresent = 0;
    }
    CloseHandle(v3);
  }
  return v1;
}

```

## disassembly

```asm
0x140019b6c  mov     [rsp+arg_0], rbx
0x140019b71  push    rdi
0x140019b72  sub     rsp, 20h
0x140019b76  mov     r8d, ecx; dwProcessId
0x140019b79  xor     ebx, ebx
0x140019b7b  mov     ecx, 400h; dwDesiredAccess
0x140019b80  mov     [rsp+28h+pbDebuggerPresent], ebx
0x140019b84  xor     edx, edx; bInheritHandle
0x140019b86  call    cs:__imp_OpenProcess
0x140019b8d  nop     dword ptr [rax+rax+00h]
0x140019b92  mov     rdi, rax
0x140019b95  lea     rcx, [rax+1]
0x140019b99  cmp     rcx, 1
0x140019b9d  jbe     short loc_140019C14
0x140019b9f  lea     rdx, [rsp+28h+pbDebuggerPresent]; pbDebuggerPresent
0x140019ba4  mov     rcx, rax; hProcess
0x140019ba7  call    cs:__imp_CheckRemoteDebuggerPresent
0x140019bae  nop     dword ptr [rax+rax+00h]
0x140019bb3  test    eax, eax
0x140019bb5  jnz     short loc_140019BFF
0x140019bb7  mov     rax, cs:WPP_GLOBAL_Control
0x140019bbe  lea     rcx, WPP_GLOBAL_Control
0x140019bc5  cmp     rax, rcx
0x140019bc8  jz      short loc_140019BF9
0x140019bca  test    byte ptr [rax+1Ch], 2
0x140019bce  jz      short loc_140019BF9
0x140019bd0  call    cs:__imp_GetLastError
0x140019bd7  nop     dword ptr [rax+rax+00h]
0x140019bdc  mov     rcx, cs:WPP_GLOBAL_Control
0x140019be3  lea     edx, [rbx+1Eh]
0x140019be6  mov     r9d, eax
0x140019be9  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x140019bf0  mov     rcx, [rcx+10h]
0x140019bf4  call    WPP_SF_d
0x140019bf9  mov     [rsp+28h+pbDebuggerPresent], ebx
0x140019bfd  jmp     short loc_140019C03
0x140019bff  mov     ebx, [rsp+28h+pbDebuggerPresent]
0x140019c03  mov     rcx, rdi; hObject
0x140019c06  call    cs:__imp_CloseHandle
0x140019c0d  nop     dword ptr [rax+rax+00h]
0x140019c12  jmp     short loc_140019C5C
0x140019c14  mov     rax, cs:WPP_GLOBAL_Control
0x140019c1b  lea     rcx, WPP_GLOBAL_Control
0x140019c22  cmp     rax, rcx
0x140019c25  jz      short loc_140019C58
0x140019c27  test    byte ptr [rax+1Ch], 2
0x140019c2b  jz      short loc_140019C58
0x140019c2d  call    cs:__imp_GetLastError
0x140019c34  nop     dword ptr [rax+rax+00h]
0x140019c39  mov     rcx, cs:WPP_GLOBAL_Control
0x140019c40  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x140019c47  mov     edx, 1Fh
0x140019c4c  mov     r9d, eax
0x140019c4f  mov     rcx, [rcx+10h]
0x140019c53  call    WPP_SF_d
0x140019c58  mov     ebx, [rsp+28h+pbDebuggerPresent]
0x140019c5c  mov     eax, ebx
0x140019c5e  mov     rbx, [rsp+28h+arg_0]
0x140019c63  add     rsp, 20h
0x140019c67  pop     rdi
0x140019c68  retn
```
