# PerfRegThreadCleanup

- ea: `0x180022d74`
- end: `0x180022e69`
- name: `PerfRegThreadCleanup`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180022d40`

## callees

- `0x1800034c8`
- `0x180003730`
- `0x180003764`
- `0x180003784`
- `0x180022d74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022dba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022dba`
- `KERNEL32!LocalFree` at `0x180022e10`
- `KERNEL32!LocalFree` at `0x180022e1a`
- `KERNEL32!LocalFree` at `0x180022e24`
- `KERNEL32!LocalFree` at `0x180022e2e`
- `KERNEL32!LocalFree` at `0x180022e47`
- `KERNEL32!LocalFree` at `0x180022e5a`
- `KERNEL32!LocalFree` at `0x180022e10`
- `KERNEL32!LocalFree` at `0x180022e1a`
- `KERNEL32!LocalFree` at `0x180022e24`
- `KERNEL32!LocalFree` at `0x180022e2e`
- `KERNEL32!LocalFree` at `0x180022e47`
- `KERNEL32!LocalFree` at `0x180022e5a`

## pseudocode

```c
void PerfRegThreadCleanup()
{
  DWORD CurrentThreadId; // esi
  _QWORD *v1; // rbx
  _QWORD *v2; // rdi

  if ( g_QueryList )
  {
    if ( NtCurrentTeb()->EtwLocalData )
    {
      if ( g_hGlobalMutex )
      {
        CurrentThreadId = GetCurrentThreadId();
        if ( !PerflibciLocalWaitForMutex(g_hGlobalMutex) )
        {
          v1 = g_QueryList;
          v2 = 0;
          while ( v1 )
          {
            if ( *((_DWORD *)v1 + 6) == CurrentThreadId )
            {
              PerflibciCloseLocalQueryHandle((struct _PERF_QUERY *)*v1);
              PerflibciFreeLocalQueryHandle(*v1);
              LocalFree((HLOCAL)v1[9]);
              LocalFree((HLOCAL)v1[7]);
              LocalFree((HLOCAL)v1[11]);
              LocalFree((HLOCAL)v1[5]);
              if ( v2 )
              {
                v2[1] = v1[1];
                LocalFree(v1);
                v1 = (_QWORD *)v2[1];
              }
              else
              {
                g_QueryList = (HLOCAL)v1[1];
                LocalFree(v1);
                v1 = g_QueryList;
              }
            }
            else
            {
              v2 = v1;
              v1 = (_QWORD *)v1[1];
            }
          }
          PerflibciLocalReleaseMutex(g_hGlobalMutex);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180022d74  mov     [rsp+arg_0], rbx
0x180022d79  mov     [rsp+arg_8], rsi
0x180022d7e  push    rdi
0x180022d7f  sub     rsp, 20h
0x180022d83  cmp     cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA, 0; PERFI_THREAD_QUERY * g_QueryList
0x180022d8b  jnz     short loc_180022D9D
0x180022d8d  mov     rbx, [rsp+28h+arg_0]
0x180022d92  mov     rsi, [rsp+28h+arg_8]
0x180022d97  add     rsp, 20h
0x180022d9b  pop     rdi
0x180022d9c  retn
0x180022d9d  mov     rax, gs:30h
0x180022da6  cmp     qword ptr [rax+1728h], 0
0x180022dae  jz      short loc_180022D8D
0x180022db0  cmp     cs:?g_hGlobalMutex@@3PEAXEA, 0; void * g_hGlobalMutex
0x180022db8  jz      short loc_180022D8D
0x180022dba  call    cs:__imp_GetCurrentThreadId
0x180022dc0  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x180022dc7  mov     esi, eax
0x180022dc9  call    ?PerflibciLocalWaitForMutex@@YAKPEAX@Z; PerflibciLocalWaitForMutex(void *)
0x180022dce  test    eax, eax
0x180022dd0  jnz     short loc_180022D8D
0x180022dd2  mov     rbx, cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA; PERFI_THREAD_QUERY * g_QueryList
0x180022dd9  xor     edi, edi
0x180022ddb  test    rbx, rbx
0x180022dde  jz      short loc_180022DEE
0x180022de0  cmp     [rbx+18h], esi
0x180022de3  jz      short loc_180022DFC
0x180022de5  mov     rdi, rbx
0x180022de8  mov     rbx, [rbx+8]
0x180022dec  jmp     short loc_180022DDB
0x180022dee  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x180022df5  call    ?PerflibciLocalReleaseMutex@@YAKPEAX@Z; PerflibciLocalReleaseMutex(void *)
0x180022dfa  jmp     short loc_180022D8D
0x180022dfc  mov     rcx, [rbx]; struct _PERF_QUERY *
0x180022dff  call    PerflibciCloseLocalQueryHandle
0x180022e04  mov     rcx, [rbx]
0x180022e07  call    PerflibciFreeLocalQueryHandle
0x180022e0c  mov     rcx, [rbx+48h]; hMem
0x180022e10  call    cs:__imp_LocalFree
0x180022e16  mov     rcx, [rbx+38h]; hMem
0x180022e1a  call    cs:__imp_LocalFree
0x180022e20  mov     rcx, [rbx+58h]; hMem
0x180022e24  call    cs:__imp_LocalFree
0x180022e2a  mov     rcx, [rbx+28h]; hMem
0x180022e2e  call    cs:__imp_LocalFree
0x180022e34  mov     rax, [rbx+8]
0x180022e38  mov     rcx, rbx; hMem
0x180022e3b  test    rdi, rdi
0x180022e3e  jnz     short loc_180022E56
0x180022e40  mov     cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA, rax; PERFI_THREAD_QUERY * g_QueryList
0x180022e47  call    cs:__imp_LocalFree
0x180022e4d  mov     rbx, cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA; PERFI_THREAD_QUERY * g_QueryList
0x180022e54  jmp     short loc_180022DDB
0x180022e56  mov     [rdi+8], rax
0x180022e5a  call    cs:__imp_LocalFree
0x180022e60  mov     rbx, [rdi+8]
0x180022e64  jmp     loc_180022DDB
```
