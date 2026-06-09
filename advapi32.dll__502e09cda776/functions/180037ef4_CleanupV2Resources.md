# CleanupV2Resources

- ea: `0x180037ef4`
- end: `0x1800380a6`
- name: `CleanupV2Resources`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180025620`

## callees

- `0x180003ba0`
- `0x180006fe0`
- `0x18000c2bc`
- `0x180037ef4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180037f2a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180037f2a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180037f6f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180037f6f`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180037f57`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180037f57`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180037f45`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180037f45`
- `KERNEL32!LocalFree` at `0x180037f97`
- `KERNEL32!LocalFree` at `0x180037fa6`
- `KERNEL32!LocalFree` at `0x18003800a`
- `KERNEL32!LocalFree` at `0x18003803d`
- `KERNEL32!LocalFree` at `0x180037f97`
- `KERNEL32!LocalFree` at `0x180037fa6`
- `KERNEL32!LocalFree` at `0x18003800a`
- `KERNEL32!LocalFree` at `0x18003803d`
- `KERNEL32!EnterCriticalSection` at `0x180037fdd`
- `KERNEL32!EnterCriticalSection` at `0x180037fdd`
- `KERNEL32!LeaveCriticalSection` at `0x180037fec`
- `KERNEL32!LeaveCriticalSection` at `0x180037fec`
- `KERNEL32!CloseHandle` at `0x180038076`
- `KERNEL32!CloseHandle` at `0x180038076`
- `KERNEL32!DeleteCriticalSection` at `0x180037ffb`
- `KERNEL32!DeleteCriticalSection` at `0x180037ffb`

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
      RtlAcquireSRWLockExclusive(&qword_1800B22F8);
      while ( 1 )
      {
        v1 = RtlEnumerateGenericTableAvl(&Table, 1u);
        if ( !v1 )
          break;
        RtlDeleteElementGenericTableAvl(&Table, v1);
      }
      RtlReleaseSRWLockExclusive(&qword_1800B22F8);
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
      qword_1800B2298 = 0;
      while ( 1 )
      {
        v6 = qword_1800B2290;
        if ( !qword_1800B2290 )
          break;
        qword_1800B2290 = (HLOCAL)*((_QWORD *)qword_1800B2290 + 3);
        LocalFree(v6);
      }
      qword_1800B2290 = 0;
      qword_1800B2288 = 0;
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
0x180037ef4  mov     [rsp+arg_0], rbx
0x180037ef9  mov     [rsp+arg_8], rsi
0x180037efe  push    rdi
0x180037eff  sub     rsp, 20h
0x180037f03  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x180037f0a  mov     sil, 1
0x180037f0d  test    rcx, rcx
0x180037f10  jz      loc_180038092
0x180037f16  call    ?PerflibciLocalWaitForMutex@@YAKPEAX@Z; PerflibciLocalWaitForMutex(void *)
0x180037f1b  test    eax, eax
0x180037f1d  jnz     loc_18003808F
0x180037f23  lea     rcx, qword_1800B22F8
0x180037f2a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180037f31  nop     dword ptr [rax+rax+00h]
0x180037f36  lea     rbx, Table
0x180037f3d  jmp     short loc_180037F51
0x180037f3f  mov     rdx, rax; Buffer
0x180037f42  mov     rcx, rbx; Table
0x180037f45  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180037f4c  nop     dword ptr [rax+rax+00h]
0x180037f51  mov     dl, sil; Restart
0x180037f54  mov     rcx, rbx; Table
0x180037f57  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180037f5e  nop     dword ptr [rax+rax+00h]
0x180037f63  test    rax, rax
0x180037f66  jnz     short loc_180037F3F
0x180037f68  lea     rcx, qword_1800B22F8
0x180037f6f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180037f76  nop     dword ptr [rax+rax+00h]
0x180037f7b  mov     rdi, cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA; PERFI_THREAD_QUERY * g_QueryList
0x180037f82  test    rdi, rdi
0x180037f85  jz      short loc_180037FBA
0x180037f87  mov     rcx, [rdi]; struct _PERF_QUERY *
0x180037f8a  mov     rbx, [rdi+8]
0x180037f8e  call    PerflibciCloseLocalQueryHandle
0x180037f93  mov     rcx, [rdi+28h]; hMem
0x180037f97  call    cs:__imp_LocalFree
0x180037f9e  nop     dword ptr [rax+rax+00h]
0x180037fa3  mov     rcx, rdi; hMem
0x180037fa6  call    cs:__imp_LocalFree
0x180037fad  nop     dword ptr [rax+rax+00h]
0x180037fb2  mov     rdi, rbx
0x180037fb5  test    rbx, rbx
0x180037fb8  jnz     short loc_180037F87
0x180037fba  mov     cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA, 0; PERFI_THREAD_QUERY * g_QueryList
0x180037fc5  jmp     short loc_180038016
0x180037fc7  mov     rbx, [rdi+20h]
0x180037fcb  mov     rax, [rdi+18h]
0x180037fcf  add     rbx, 28h ; '('
0x180037fd3  mov     rcx, rbx; lpCriticalSection
0x180037fd6  mov     cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA, rax; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x180037fdd  call    cs:__imp_EnterCriticalSection
0x180037fe4  nop     dword ptr [rax+rax+00h]
0x180037fe9  mov     rcx, rbx; lpCriticalSection
0x180037fec  call    cs:__imp_LeaveCriticalSection
0x180037ff3  nop     dword ptr [rax+rax+00h]
0x180037ff8  mov     rcx, rbx; lpCriticalSection
0x180037ffb  call    cs:__imp_DeleteCriticalSection
0x180038002  nop     dword ptr [rax+rax+00h]
0x180038007  mov     rcx, rdi; hMem
0x18003800a  call    cs:__imp_LocalFree
0x180038011  nop     dword ptr [rax+rax+00h]
0x180038016  mov     rdi, cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x18003801d  test    rdi, rdi
0x180038020  jnz     short loc_180037FC7
0x180038022  mov     cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA, rdi; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x180038029  mov     cs:qword_1800B2298, rdi
0x180038030  jmp     short loc_180038049
0x180038032  mov     rax, [rcx+18h]
0x180038036  mov     cs:qword_1800B2290, rax
0x18003803d  call    cs:__imp_LocalFree
0x180038044  nop     dword ptr [rax+rax+00h]
0x180038049  mov     rcx, cs:qword_1800B2290; hMem
0x180038050  test    rcx, rcx
0x180038053  jnz     short loc_180038032
0x180038055  mov     cs:qword_1800B2290, rcx
0x18003805c  mov     cs:qword_1800B2288, rcx
0x180038063  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x18003806a  call    ?PerflibciLocalReleaseMutex@@YAKPEAX@Z; PerflibciLocalReleaseMutex(void *)
0x18003806f  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; hObject
0x180038076  call    cs:__imp_CloseHandle
0x18003807d  nop     dword ptr [rax+rax+00h]
0x180038082  mov     cs:?g_hGlobalMutex@@3PEAXEA, 0; void * g_hGlobalMutex
0x18003808d  jmp     short loc_180038092
0x18003808f  xor     sil, sil
0x180038092  mov     rbx, [rsp+28h+arg_0]
0x180038097  mov     al, sil
0x18003809a  mov     rsi, [rsp+28h+arg_8]
0x18003809f  add     rsp, 20h
0x1800380a3  pop     rdi
0x1800380a4  retn
```
