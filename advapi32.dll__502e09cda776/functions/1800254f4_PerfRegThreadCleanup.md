# PerfRegThreadCleanup

- ea: `0x1800254f4`
- end: `0x180025617`
- name: `PerfRegThreadCleanup`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800254c0`

## callees

- `0x180003b64`
- `0x180003ba0`
- `0x180006fe0`
- `0x18000c2bc`
- `0x1800254f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002553b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002553b`
- `KERNEL32!LocalFree` at `0x180025597`
- `KERNEL32!LocalFree` at `0x1800255a7`
- `KERNEL32!LocalFree` at `0x1800255b7`
- `KERNEL32!LocalFree` at `0x1800255c7`
- `KERNEL32!LocalFree` at `0x1800255e6`
- `KERNEL32!LocalFree` at `0x180025602`
- `KERNEL32!LocalFree` at `0x180025597`
- `KERNEL32!LocalFree` at `0x1800255a7`
- `KERNEL32!LocalFree` at `0x1800255b7`
- `KERNEL32!LocalFree` at `0x1800255c7`
- `KERNEL32!LocalFree` at `0x1800255e6`
- `KERNEL32!LocalFree` at `0x180025602`

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
0x1800254f4  mov     [rsp+arg_0], rbx
0x1800254f9  mov     [rsp+arg_8], rsi
0x1800254fe  push    rdi
0x1800254ff  sub     rsp, 20h
0x180025503  cmp     cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA, 0; PERFI_THREAD_QUERY * g_QueryList
0x18002550b  jnz     short loc_18002551E
0x18002550d  mov     rbx, [rsp+28h+arg_0]
0x180025512  mov     rsi, [rsp+28h+arg_8]
0x180025517  add     rsp, 20h
0x18002551b  pop     rdi
0x18002551c  retn
0x18002551e  mov     rax, gs:30h
0x180025527  cmp     qword ptr [rax+1728h], 0
0x18002552f  jz      short loc_18002550D
0x180025531  cmp     cs:?g_hGlobalMutex@@3PEAXEA, 0; void * g_hGlobalMutex
0x180025539  jz      short loc_18002550D
0x18002553b  call    cs:__imp_GetCurrentThreadId
0x180025542  nop     dword ptr [rax+rax+00h]
0x180025547  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x18002554e  mov     esi, eax
0x180025550  call    ?PerflibciLocalWaitForMutex@@YAKPEAX@Z; PerflibciLocalWaitForMutex(void *)
0x180025555  test    eax, eax
0x180025557  jnz     short loc_18002550D
0x180025559  mov     rbx, cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA; PERFI_THREAD_QUERY * g_QueryList
0x180025560  xor     edi, edi
0x180025562  test    rbx, rbx
0x180025565  jz      short loc_180025575
0x180025567  cmp     [rbx+18h], esi
0x18002556a  jz      short loc_180025583
0x18002556c  mov     rdi, rbx
0x18002556f  mov     rbx, [rbx+8]
0x180025573  jmp     short loc_180025562
0x180025575  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x18002557c  call    ?PerflibciLocalReleaseMutex@@YAKPEAX@Z; PerflibciLocalReleaseMutex(void *)
0x180025581  jmp     short loc_18002550D
0x180025583  mov     rcx, [rbx]; struct _PERF_QUERY *
0x180025586  call    PerflibciCloseLocalQueryHandle
0x18002558b  mov     rcx, [rbx]
0x18002558e  call    PerflibciFreeLocalQueryHandle
0x180025593  mov     rcx, [rbx+48h]; hMem
0x180025597  call    cs:__imp_LocalFree
0x18002559e  nop     dword ptr [rax+rax+00h]
0x1800255a3  mov     rcx, [rbx+38h]; hMem
0x1800255a7  call    cs:__imp_LocalFree
0x1800255ae  nop     dword ptr [rax+rax+00h]
0x1800255b3  mov     rcx, [rbx+58h]; hMem
0x1800255b7  call    cs:__imp_LocalFree
0x1800255be  nop     dword ptr [rax+rax+00h]
0x1800255c3  mov     rcx, [rbx+28h]; hMem
0x1800255c7  call    cs:__imp_LocalFree
0x1800255ce  nop     dword ptr [rax+rax+00h]
0x1800255d3  mov     rax, [rbx+8]
0x1800255d7  mov     rcx, rbx; hMem
0x1800255da  test    rdi, rdi
0x1800255dd  jnz     short loc_1800255FE
0x1800255df  mov     cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA, rax; PERFI_THREAD_QUERY * g_QueryList
0x1800255e6  call    cs:__imp_LocalFree
0x1800255ed  nop     dword ptr [rax+rax+00h]
0x1800255f2  mov     rbx, cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA; PERFI_THREAD_QUERY * g_QueryList
0x1800255f9  jmp     loc_180025562
0x1800255fe  mov     [rdi+8], rax
0x180025602  call    cs:__imp_LocalFree
0x180025609  nop     dword ptr [rax+rax+00h]
0x18002560e  mov     rbx, [rdi+8]
0x180025612  jmp     loc_180025562
```
