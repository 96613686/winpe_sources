# CReflectedDump::Cleanup(void)

- ea: `0x140016c24`
- end: `0x140016cda`
- name: `?Cleanup@CReflectedDump@@QEAAXXZ`
- size: `182`
- prototype: `void __fastcall(CReflectedDump *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1400168b8`
- `0x140017998`

## callees

- `0x1400033ab`
- `0x140016c24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140016c99`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140016c99`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140016c65`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140016c65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016cbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016cbd`
- `wer!WerpAddTerminationReason` at `0x140016c84`
- `wer!WerpAddTerminationReason` at `0x140016c84`

## pseudocode

```c
void __fastcall CReflectedDump::Cleanup(CReflectedDump *this)
{
  const WCHAR *v1; // rdi
  void *v3; // rcx
  DWORD ProcessId; // eax
  void *v5; // rcx

  v1 = (const WCHAR *)((char *)this + 8);
  if ( *((_WORD *)this + 4) && !*((_DWORD *)this + 135) )
  {
    DeleteFileW_0(v1);
    *v1 = 0;
  }
  v3 = (void *)*((_QWORD *)this + 66);
  if ( (unsigned __int64)v3 + 1 > 1 )
  {
    ProcessId = GetProcessId(v3);
    WerpAddTerminationReason(ProcessId, 4, L"WerReflectedProcessCleanup");
    TerminateProcess(*((HANDLE *)this + 66), 0);
    v5 = (void *)*((_QWORD *)this + 66);
    *((_QWORD *)this + 66) = 0;
    if ( (unsigned __int64)v5 + 1 > 1 )
      CloseHandle(v5);
  }
}

```

## disassembly

```asm
0x140016c24  mov     [rsp+arg_0], rbx
0x140016c29  mov     [rsp+arg_8], rsi
0x140016c2e  push    rdi
0x140016c2f  sub     rsp, 20h
0x140016c33  lea     rdi, [rcx+8]
0x140016c37  xor     esi, esi
0x140016c39  mov     rbx, rcx
0x140016c3c  cmp     [rdi], si
0x140016c3f  jz      short loc_140016C54
0x140016c41  cmp     [rcx+21Ch], esi
0x140016c47  jnz     short loc_140016C54
0x140016c49  mov     rcx, rdi; lpFileName
0x140016c4c  call    DeleteFileW_0
0x140016c51  mov     [rdi], si
0x140016c54  mov     rcx, [rbx+210h]; Process
0x140016c5b  lea     rax, [rcx+1]
0x140016c5f  cmp     rax, 1
0x140016c63  jbe     short loc_140016CC9
0x140016c65  call    cs:__imp_GetProcessId
0x140016c6c  nop     dword ptr [rax+rax+00h]
0x140016c71  mov     r9d, 1
0x140016c77  lea     r8, aWerreflectedpr; "WerReflectedProcessCleanup"
0x140016c7e  mov     ecx, eax
0x140016c80  lea     edx, [r9+3]
0x140016c84  call    cs:__imp_WerpAddTerminationReason
0x140016c8b  nop     dword ptr [rax+rax+00h]
0x140016c90  mov     rcx, [rbx+210h]; hProcess
0x140016c97  xor     edx, edx; uExitCode
0x140016c99  call    cs:__imp_TerminateProcess
0x140016ca0  nop     dword ptr [rax+rax+00h]
0x140016ca5  mov     rcx, [rbx+210h]; hObject
0x140016cac  mov     [rbx+210h], rsi
0x140016cb3  lea     rax, [rcx+1]
0x140016cb7  cmp     rax, 1
0x140016cbb  jbe     short loc_140016CC9
0x140016cbd  call    cs:__imp_CloseHandle
0x140016cc4  nop     dword ptr [rax+rax+00h]
0x140016cc9  mov     rbx, [rsp+28h+arg_0]
0x140016cce  mov     rsi, [rsp+28h+arg_8]
0x140016cd3  add     rsp, 20h
0x140016cd7  pop     rdi
0x140016cd8  retn
```
