# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x140003cec`
- end: `0x140003e6b`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `383`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140004d30`

## callees

- `0x1400023a4`
- `0x140002ac0`
- `0x140003cec`
- `0x14000493c`
- `0x140005010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140003df3`
- `KERNEL32!HeapFree` at `0x140003df3`
- `KERNEL32!SetLastError` at `0x140003d7b`
- `KERNEL32!SetLastError` at `0x140003dad`
- `KERNEL32!SetLastError` at `0x140003dd7`
- `KERNEL32!SetLastError` at `0x140003d7b`
- `KERNEL32!SetLastError` at `0x140003dad`
- `KERNEL32!SetLastError` at `0x140003dd7`
- `KERNEL32!ReleaseMutex` at `0x140003dcb`
- `KERNEL32!ReleaseMutex` at `0x140003e03`
- `KERNEL32!ReleaseMutex` at `0x140003dcb`
- `KERNEL32!ReleaseMutex` at `0x140003e03`
- `KERNEL32!GetLastError` at `0x140003d60`
- `KERNEL32!GetLastError` at `0x140003d92`
- `KERNEL32!GetLastError` at `0x140003dc0`
- `KERNEL32!GetLastError` at `0x140003d60`
- `KERNEL32!GetLastError` at `0x140003d92`
- `KERNEL32!GetLastError` at `0x140003dc0`
- `KERNEL32!WaitForSingleObjectEx` at `0x140003d2b`
- `KERNEL32!WaitForSingleObjectEx` at `0x140003d2b`
- `KERNEL32!CloseHandle` at `0x140003d6b`
- `KERNEL32!CloseHandle` at `0x140003d9d`
- `KERNEL32!CloseHandle` at `0x140003d6b`
- `KERNEL32!CloseHandle` at `0x140003d9d`
- `KERNEL32!GetProcessHeap` at `0x140003de5`
- `KERNEL32!GetProcessHeap` at `0x140003de5`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  const char *v6; // r9
  int result; // eax
  void *v8; // rsi
  DWORD LastError; // ebp
  unsigned int v10; // r8d
  const char *v11; // r9
  void *v12; // rsi
  DWORD v13; // ebp
  unsigned int v14; // r8d
  const char *v15; // r9
  DWORD v16; // esi
  unsigned int v17; // r8d
  const char *v18; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v20; // r8d
  const char *v21; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return --*(_DWORD *)lpMem;
  }
  else
  {
    v2 = (void *)lpMem[1];
    v3 = WaitForSingleObjectEx(v2, 0xFFFFFFFF, 0);
    if ( v3 == 258 )
    {
      v2 = 0;
    }
    else if ( (v3 & 0xFFFFFF7F) != 0 )
    {
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v4, v5, v6);
    }
    result = --*(_DWORD *)lpMem;
    if ( *(_DWORD *)lpMem )
    {
      if ( v2 )
      {
        result = ReleaseMutex(v2);
        if ( !result )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v20, v21);
      }
    }
    else
    {
      v8 = (void *)lpMem[2];
      if ( v8 )
      {
        LastError = GetLastError();
        if ( !CloseHandle(v8) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
        SetLastError(LastError);
      }
      lpMem[2] = 0;
      v12 = (void *)lpMem[3];
      if ( v12 )
      {
        v13 = GetLastError();
        if ( !CloseHandle(v12) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
        SetLastError(v13);
      }
      lpMem[3] = 0;
      if ( v2 )
      {
        v16 = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v17, v18);
        SetLastError(v16);
      }
      wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(lpMem);
      ProcessHeap = GetProcessHeap();
      return HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003cec  push    rbx
0x140003cee  push    rbp
0x140003cef  push    rsi
0x140003cf0  push    rdi
0x140003cf1  sub     rsp, 28h
0x140003cf5  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140003cfc  mov     rbx, rcx
0x140003cff  jnz     loc_140003E0F
0x140003d05  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140003d0c  test    rax, rax
0x140003d0f  jz      short loc_140003D1E
0x140003d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d16  test    al, al
0x140003d18  jnz     loc_140003E0F
0x140003d1e  mov     rdi, [rbx+8]
0x140003d22  xor     r8d, r8d; bAlertable
0x140003d25  mov     rcx, rdi; hHandle
0x140003d28  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003d2b  call    cs:__imp_WaitForSingleObjectEx
0x140003d31  cmp     eax, 102h
0x140003d36  jz      short loc_140003D45
0x140003d38  test    eax, 0FFFFFF7Fh
0x140003d3d  jnz     loc_140003E30
0x140003d43  jmp     short loc_140003D47
0x140003d45  xor     edi, edi
0x140003d47  mov     eax, [rbx]
0x140003d49  dec     eax
0x140003d4b  mov     [rbx], eax
0x140003d4d  mov     eax, [rbx]
0x140003d4f  test    eax, eax
0x140003d51  jnz     loc_140003DFB
0x140003d57  mov     rsi, [rbx+10h]
0x140003d5b  test    rsi, rsi
0x140003d5e  jz      short loc_140003D81
0x140003d60  call    cs:__imp_GetLastError
0x140003d66  mov     rcx, rsi; hObject
0x140003d69  mov     ebp, eax
0x140003d6b  call    cs:__imp_CloseHandle
0x140003d71  test    eax, eax
0x140003d73  jz      loc_140003E4B
0x140003d79  mov     ecx, ebp; dwErrCode
0x140003d7b  call    cs:__imp_SetLastError
0x140003d81  mov     qword ptr [rbx+10h], 0
0x140003d89  mov     rsi, [rbx+18h]
0x140003d8d  test    rsi, rsi
0x140003d90  jz      short loc_140003DB3
0x140003d92  call    cs:__imp_GetLastError
0x140003d98  mov     rcx, rsi; hObject
0x140003d9b  mov     ebp, eax
0x140003d9d  call    cs:__imp_CloseHandle
0x140003da3  test    eax, eax
0x140003da5  jz      loc_140003E5B
0x140003dab  mov     ecx, ebp; dwErrCode
0x140003dad  call    cs:__imp_SetLastError
0x140003db3  mov     qword ptr [rbx+18h], 0
0x140003dbb  test    rdi, rdi
0x140003dbe  jz      short loc_140003DDD
0x140003dc0  call    cs:__imp_GetLastError
0x140003dc6  mov     rcx, rdi; hMutex
0x140003dc9  mov     esi, eax
0x140003dcb  call    cs:__imp_ReleaseMutex
0x140003dd1  test    eax, eax
0x140003dd3  jz      short loc_140003E20
0x140003dd5  mov     ecx, esi; dwErrCode
0x140003dd7  call    cs:__imp_SetLastError
0x140003ddd  mov     rcx, rbx
0x140003de0  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x140003de5  call    cs:__imp_GetProcessHeap
0x140003deb  mov     r8, rbx; lpMem
0x140003dee  xor     edx, edx; dwFlags
0x140003df0  mov     rcx, rax; hHeap
0x140003df3  call    cs:__imp_HeapFree
0x140003df9  jmp     short loc_140003E17
0x140003dfb  test    rdi, rdi
0x140003dfe  jz      short loc_140003E17
0x140003e00  mov     rcx, rdi; hMutex
0x140003e03  call    cs:__imp_ReleaseMutex
0x140003e09  test    eax, eax
0x140003e0b  jz      short loc_140003E3B
0x140003e0d  jmp     short loc_140003E17
0x140003e0f  mov     eax, [rbx]
0x140003e11  dec     eax
0x140003e13  mov     [rbx], eax
0x140003e15  mov     eax, [rbx]
0x140003e17  add     rsp, 28h
0x140003e1b  pop     rdi
0x140003e1c  pop     rsi
0x140003e1d  pop     rbp
0x140003e1e  pop     rbx
0x140003e1f  retn
0x140003e20  mov     rcx, [rsp+48h]; this
0x140003e25  mov     edx, 0A15h; void *
0x140003e2a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003e30  mov     rcx, [rsp+48h]; this
0x140003e35  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140003e3b  mov     rcx, [rsp+48h]; this
0x140003e40  mov     edx, 0A15h; void *
0x140003e45  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003e4b  mov     rcx, [rsp+48h]; this
0x140003e50  mov     edx, 0A0Bh; void *
0x140003e55  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003e5b  mov     rcx, [rsp+48h]; this
0x140003e60  mov     edx, 0A0Bh; void *
0x140003e65  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
