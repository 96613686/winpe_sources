# StateRepository::ResourcePriority::AutoThreadPriority<49,bool,_THREAD_POWER_THROTTLING_STATE>::~AutoThreadPriority<49,bool,_THREAD_POWER_THROTTLING_STATE>(void)

- ea: `0x1800f853c`
- end: `0x1800f85a2`
- name: `??1?$AutoThreadPriority@$0DB@_NU_THREAD_POWER_THROTTLING_STATE@@@ResourcePriority@StateRepository@@QEAA@XZ`
- size: `102`
- prototype: `int __fastcall(char **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800f85a8`

## callees

- `0x1800f853c`
- `0x1800fcde4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f8558`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f8558`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f8596`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f8596`
- `ntdll!NtSetInformationThread` at `0x1800f856e`
- `ntdll!NtSetInformationThread` at `0x1800f856e`

## pseudocode

```c
int __fastcall StateRepository::ResourcePriority::AutoThreadPriority<49,bool,_THREAD_POWER_THROTTLING_STATE>::~AutoThreadPriority<49,bool,_THREAD_POWER_THROTTLING_STATE>(
        char **a1)
{
  char *CurrentThread; // rcx
  NTSTATUS v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  unsigned __int64 v6; // rax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_BYTE *)a1 + 8) )
  {
    CurrentThread = *a1;
    if ( (unsigned __int64)(CurrentThread - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      CurrentThread = (char *)GetCurrentThread();
    v3 = NtSetInformationThread(CurrentThread, ThreadHideFromDebugger|0x20, (char *)a1 + 12, 0xCu);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_NtStatus(retaddr, v4, v5, (const char *)(unsigned int)v3, v8);
    *((_BYTE *)a1 + 8) = 0;
  }
  v6 = (unsigned __int64)(*a1 - 1);
  if ( v6 <= 0xFFFFFFFFFFFFFFFDuLL )
    LODWORD(v6) = CloseHandle(*a1);
  return v6;
}

```

## disassembly

```asm
0x1800f853c  push    rbx; int
0x1800f853e  sub     rsp, 20h
0x1800f8542  cmp     byte ptr [rcx+8], 0
0x1800f8546  mov     rbx, rcx
0x1800f8549  jz      short loc_1800F8589
0x1800f854b  mov     rcx, [rcx]
0x1800f854e  lea     rax, [rcx-1]
0x1800f8552  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f8556  jbe     short loc_1800F8561
0x1800f8558  call    cs:__imp_GetCurrentThread
0x1800f855e  mov     rcx, rax; ThreadHandle
0x1800f8561  mov     edx, 31h ; '1'; ThreadInformationClass
0x1800f8566  lea     r8, [rbx+0Ch]; ThreadInformation
0x1800f856a  lea     r9d, [rdx-25h]; ThreadInformationLength
0x1800f856e  call    cs:__imp_NtSetInformationThread
0x1800f8574  test    eax, eax
0x1800f8576  jns     short loc_1800F8585
0x1800f8578  mov     rcx, [rsp+28h]; this
0x1800f857d  mov     r9d, eax; char *
0x1800f8580  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800f8585  mov     byte ptr [rbx+8], 0
0x1800f8589  mov     rcx, [rbx]; hObject
0x1800f858c  lea     rax, [rcx-1]
0x1800f8590  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f8594  ja      short loc_1800F859C
0x1800f8596  call    cs:__imp_CloseHandle
0x1800f859c  add     rsp, 20h
0x1800f85a0  pop     rbx
0x1800f85a1  retn
```
