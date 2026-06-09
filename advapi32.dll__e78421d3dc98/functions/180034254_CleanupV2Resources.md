# CleanupV2Resources

- ea: `0x180034254`
- end: `0x1800343bd`
- name: `CleanupV2Resources`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180022e70`

## callees

- `0x180003730`
- `0x180003764`
- `0x180003784`
- `0x180034254`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003428a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003428a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800342bd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800342bd`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800342ab`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800342ab`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18003429f`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18003429f`
- `KERNEL32!LocalFree` at `0x1800342df`
- `KERNEL32!LocalFree` at `0x1800342e8`
- `KERNEL32!LocalFree` at `0x180034334`
- `KERNEL32!LocalFree` at `0x180034361`
- `KERNEL32!LocalFree` at `0x1800342df`
- `KERNEL32!LocalFree` at `0x1800342e8`
- `KERNEL32!LocalFree` at `0x180034334`
- `KERNEL32!LocalFree` at `0x180034361`
- `KERNEL32!EnterCriticalSection` at `0x180034319`
- `KERNEL32!EnterCriticalSection` at `0x180034319`
- `KERNEL32!LeaveCriticalSection` at `0x180034322`
- `KERNEL32!LeaveCriticalSection` at `0x180034322`
- `KERNEL32!CloseHandle` at `0x180034394`
- `KERNEL32!CloseHandle` at `0x180034394`
- `KERNEL32!DeleteCriticalSection` at `0x18003432b`
- `KERNEL32!DeleteCriticalSection` at `0x18003432b`

## pseudocode

```c
char CleanupV2Resources()
{
  char v0; // si
  PVOID v1; // rax
  HLOCAL v2; // rdi
  void *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  HLOCAL v5; // rdi
  HLOCAL v6; // rcx

  v0 = 1;
  if ( g_hGlobalMutex )
  {
    if ( PerflibciLocalWaitForMutex(g_hGlobalMutex) )
    {
      return 0;
    }
    else
    {
      RtlAcquireSRWLockExclusive(&qword_1800A31B0);
      while ( 1 )
      {
        v1 = RtlEnumerateGenericTableAvl(&Table, 1u);
        if ( !v1 )
          break;
        RtlDeleteElementGenericTableAvl(&Table, v1);
      }
      RtlReleaseSRWLockExclusive(&qword_1800A31B0);
      v2 = g_QueryList;
      if ( g_QueryList )
      {
        do
        {
          v3 = (void *)*((_QWORD *)v2 + 1);
          PerflibciCloseLocalQueryHandle(*(struct _PERF_QUERY **)v2);
          LocalFree(*((HLOCAL *)v2 + 5));
          LocalFree(v2);
          v2 = v3;
        }
        while ( v3 );
      }
      g_QueryList = 0;
      while ( 1 )
      {
        v5 = g_ObjectList;
        if ( !g_ObjectList )
          break;
        v4 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)g_ObjectList + 4) + 40LL);
        g_ObjectList = (HLOCAL)*((_QWORD *)g_ObjectList + 3);
        EnterCriticalSection(v4);
        LeaveCriticalSection(v4);
        DeleteCriticalSection(v4);
        LocalFree(v5);
      }
      g_ObjectList = 0;
      qword_1800A3148 = 0;
      while ( 1 )
      {
        v6 = qword_1800A3140;
        if ( !qword_1800A3140 )
          break;
        qword_1800A3140 = (HLOCAL)*((_QWORD *)qword_1800A3140 + 3);
        LocalFree(v6);
      }
      qword_1800A3140 = 0;
      qword_1800A3150 = 0;
      PerflibciLocalReleaseMutex(g_hGlobalMutex);
      CloseHandle(g_hGlobalMutex);
      g_hGlobalMutex = 0;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180034254  mov     [rsp+arg_0], rbx
0x180034259  mov     [rsp+arg_8], rsi
0x18003425e  push    rdi
0x18003425f  sub     rsp, 20h
0x180034263  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x18003426a  mov     sil, 1
0x18003426d  test    rcx, rcx
0x180034270  jz      loc_1800343AA
0x180034276  call    ?PerflibciLocalWaitForMutex@@YAKPEAX@Z; PerflibciLocalWaitForMutex(void *)
0x18003427b  test    eax, eax
0x18003427d  jnz     loc_1800343A7
0x180034283  lea     rcx, qword_1800A31B0
0x18003428a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180034290  lea     rbx, Table
0x180034297  jmp     short loc_1800342A5
0x180034299  mov     rdx, rax; Buffer
0x18003429c  mov     rcx, rbx; Table
0x18003429f  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800342a5  mov     dl, sil; Restart
0x1800342a8  mov     rcx, rbx; Table
0x1800342ab  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1800342b1  test    rax, rax
0x1800342b4  jnz     short loc_180034299
0x1800342b6  lea     rcx, qword_1800A31B0
0x1800342bd  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800342c3  mov     rdi, cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA; PERFI_THREAD_QUERY * g_QueryList
0x1800342ca  test    rdi, rdi
0x1800342cd  jz      short loc_1800342F6
0x1800342cf  mov     rcx, [rdi]; struct _PERF_QUERY *
0x1800342d2  mov     rbx, [rdi+8]
0x1800342d6  call    PerflibciCloseLocalQueryHandle
0x1800342db  mov     rcx, [rdi+28h]; hMem
0x1800342df  call    cs:__imp_LocalFree
0x1800342e5  mov     rcx, rdi; hMem
0x1800342e8  call    cs:__imp_LocalFree
0x1800342ee  mov     rdi, rbx
0x1800342f1  test    rbx, rbx
0x1800342f4  jnz     short loc_1800342CF
0x1800342f6  mov     cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA, 0; PERFI_THREAD_QUERY * g_QueryList
0x180034301  jmp     short loc_18003433A
0x180034303  mov     rbx, [rdi+20h]
0x180034307  mov     rax, [rdi+18h]
0x18003430b  add     rbx, 28h ; '('
0x18003430f  mov     rcx, rbx; lpCriticalSection
0x180034312  mov     cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA, rax; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x180034319  call    cs:__imp_EnterCriticalSection
0x18003431f  mov     rcx, rbx; lpCriticalSection
0x180034322  call    cs:__imp_LeaveCriticalSection
0x180034328  mov     rcx, rbx; lpCriticalSection
0x18003432b  call    cs:__imp_DeleteCriticalSection
0x180034331  mov     rcx, rdi; hMem
0x180034334  call    cs:__imp_LocalFree
0x18003433a  mov     rdi, cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x180034341  test    rdi, rdi
0x180034344  jnz     short loc_180034303
0x180034346  mov     cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA, rdi; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x18003434d  mov     cs:qword_1800A3148, rdi
0x180034354  jmp     short loc_180034367
0x180034356  mov     rax, [rcx+18h]
0x18003435a  mov     cs:qword_1800A3140, rax
0x180034361  call    cs:__imp_LocalFree
0x180034367  mov     rcx, cs:qword_1800A3140; hMem
0x18003436e  test    rcx, rcx
0x180034371  jnz     short loc_180034356
0x180034373  mov     cs:qword_1800A3140, rcx
0x18003437a  mov     cs:qword_1800A3150, rcx
0x180034381  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x180034388  call    ?PerflibciLocalReleaseMutex@@YAKPEAX@Z; PerflibciLocalReleaseMutex(void *)
0x18003438d  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; hObject
0x180034394  call    cs:__imp_CloseHandle
0x18003439a  mov     cs:?g_hGlobalMutex@@3PEAXEA, 0; void * g_hGlobalMutex
0x1800343a5  jmp     short loc_1800343AA
0x1800343a7  xor     sil, sil
0x1800343aa  mov     rbx, [rsp+28h+arg_0]
0x1800343af  mov     al, sil
0x1800343b2  mov     rsi, [rsp+28h+arg_8]
0x1800343b7  add     rsp, 20h
0x1800343bb  pop     rdi
0x1800343bc  retn
```
