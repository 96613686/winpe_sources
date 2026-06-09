# IsBeingDebugged(ulong)

- ea: `0x140018cd4`
- end: `0x140018db3`
- name: `?IsBeingDebugged@@YAHK@Z`
- size: `223`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140019374`

## callees

- `0x140014474`
- `0x140018cd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018d7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018d5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018d5c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140018cee`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140018cee`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x140018d09`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x140018d09`

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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids, LastError);
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids, v4);
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
0x140018cd4  mov     [rsp+arg_0], rbx
0x140018cd9  push    rdi
0x140018cda  sub     rsp, 20h
0x140018cde  mov     r8d, ecx; dwProcessId
0x140018ce1  xor     ebx, ebx
0x140018ce3  mov     ecx, 400h; dwDesiredAccess
0x140018ce8  mov     [rsp+28h+pbDebuggerPresent], ebx
0x140018cec  xor     edx, edx; bInheritHandle
0x140018cee  call    cs:__imp_OpenProcess
0x140018cf4  mov     rdi, rax
0x140018cf7  lea     rcx, [rax+1]
0x140018cfb  cmp     rcx, 1
0x140018cff  jbe     short loc_140018D64
0x140018d01  lea     rdx, [rsp+28h+pbDebuggerPresent]; pbDebuggerPresent
0x140018d06  mov     rcx, rax; hProcess
0x140018d09  call    cs:__imp_CheckRemoteDebuggerPresent
0x140018d0f  test    eax, eax
0x140018d11  jnz     short loc_140018D55
0x140018d13  mov     rax, cs:WPP_GLOBAL_Control
0x140018d1a  lea     rcx, WPP_GLOBAL_Control
0x140018d21  cmp     rax, rcx
0x140018d24  jz      short loc_140018D4F
0x140018d26  test    byte ptr [rax+1Ch], 2
0x140018d2a  jz      short loc_140018D4F
0x140018d2c  call    cs:__imp_GetLastError
0x140018d32  mov     rcx, cs:WPP_GLOBAL_Control
0x140018d39  lea     edx, [rbx+1Eh]
0x140018d3c  mov     r9d, eax
0x140018d3f  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x140018d46  mov     rcx, [rcx+10h]
0x140018d4a  call    WPP_SF_d
0x140018d4f  mov     [rsp+28h+pbDebuggerPresent], ebx
0x140018d53  jmp     short loc_140018D59
0x140018d55  mov     ebx, [rsp+28h+pbDebuggerPresent]
0x140018d59  mov     rcx, rdi; hObject
0x140018d5c  call    cs:__imp_CloseHandle
0x140018d62  jmp     short loc_140018DA6
0x140018d64  mov     rax, cs:WPP_GLOBAL_Control
0x140018d6b  lea     rcx, WPP_GLOBAL_Control
0x140018d72  cmp     rax, rcx
0x140018d75  jz      short loc_140018DA2
0x140018d77  test    byte ptr [rax+1Ch], 2
0x140018d7b  jz      short loc_140018DA2
0x140018d7d  call    cs:__imp_GetLastError
0x140018d83  mov     rcx, cs:WPP_GLOBAL_Control
0x140018d8a  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x140018d91  mov     edx, 1Fh
0x140018d96  mov     r9d, eax
0x140018d99  mov     rcx, [rcx+10h]
0x140018d9d  call    WPP_SF_d
0x140018da2  mov     ebx, [rsp+28h+pbDebuggerPresent]
0x140018da6  mov     eax, ebx
0x140018da8  mov     rbx, [rsp+28h+arg_0]
0x140018dad  add     rsp, 20h
0x140018db1  pop     rdi
0x140018db2  retn
```
