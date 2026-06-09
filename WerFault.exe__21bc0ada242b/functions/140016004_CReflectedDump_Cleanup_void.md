# CReflectedDump::Cleanup(void)

- ea: `0x140016004`
- end: `0x1400160a1`
- name: `?Cleanup@CReflectedDump@@QEAAXXZ`
- size: `157`
- prototype: `void __fastcall(CReflectedDump *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140015cb8`
- `0x140016cbc`

## callees

- `0x14000335b`
- `0x140016004`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14001606d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14001606d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140016045`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140016045`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001608b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001608b`
- `wer!WerpAddTerminationReason` at `0x14001605e`
- `wer!WerpAddTerminationReason` at `0x14001605e`

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
0x140016004  mov     [rsp+arg_0], rbx
0x140016009  mov     [rsp+arg_8], rsi
0x14001600e  push    rdi
0x14001600f  sub     rsp, 20h
0x140016013  lea     rdi, [rcx+8]
0x140016017  xor     esi, esi
0x140016019  mov     rbx, rcx
0x14001601c  cmp     [rdi], si
0x14001601f  jz      short loc_140016034
0x140016021  cmp     [rcx+21Ch], esi
0x140016027  jnz     short loc_140016034
0x140016029  mov     rcx, rdi; lpFileName
0x14001602c  call    DeleteFileW_0
0x140016031  mov     [rdi], si
0x140016034  mov     rcx, [rbx+210h]; Process
0x14001603b  lea     rax, [rcx+1]
0x14001603f  cmp     rax, 1
0x140016043  jbe     short loc_140016091
0x140016045  call    cs:__imp_GetProcessId
0x14001604b  mov     r9d, 1
0x140016051  lea     r8, aWerreflectedpr; "WerReflectedProcessCleanup"
0x140016058  mov     ecx, eax
0x14001605a  lea     edx, [r9+3]
0x14001605e  call    cs:__imp_WerpAddTerminationReason
0x140016064  mov     rcx, [rbx+210h]; hProcess
0x14001606b  xor     edx, edx; uExitCode
0x14001606d  call    cs:__imp_TerminateProcess
0x140016073  mov     rcx, [rbx+210h]; hObject
0x14001607a  mov     [rbx+210h], rsi
0x140016081  lea     rax, [rcx+1]
0x140016085  cmp     rax, 1
0x140016089  jbe     short loc_140016091
0x14001608b  call    cs:__imp_CloseHandle
0x140016091  mov     rbx, [rsp+28h+arg_0]
0x140016096  mov     rsi, [rsp+28h+arg_8]
0x14001609b  add     rsp, 20h
0x14001609f  pop     rdi
0x1400160a0  retn
```
