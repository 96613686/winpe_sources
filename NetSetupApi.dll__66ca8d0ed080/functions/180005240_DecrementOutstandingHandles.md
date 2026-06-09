# DecrementOutstandingHandles

- ea: `0x180005240`
- end: `0x18000529e`
- name: `DecrementOutstandingHandles`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180003970`

## callees

- `0x180005240`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180005271`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180005271`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005297`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000524d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000524d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005253`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005253`

## pseudocode

```c
void DecrementOutstandingHandles()
{
  AcquireSRWLockExclusive(&g_NetSetupHandleCountLock);
  dword_180025A68 = GetCurrentThreadId();
  if ( !--g_NumNetSetupHandles )
  {
    FreeLibrary(g_NetSetupEngine);
    g_NetSetupEngine = 0;
    g_NetSetupGetEnginePfn = 0;
  }
  dword_180025A68 = 0;
  ReleaseSRWLockExclusive(&g_NetSetupHandleCountLock);
}

```

## disassembly

```asm
0x180005240  push    rbx
0x180005242  sub     rsp, 20h
0x180005246  lea     rcx, ?g_NetSetupHandleCountLock@@3VRtlSrwLock@@A; SRWLock
0x18000524d  call    cs:__imp_AcquireSRWLockExclusive
0x180005253  call    cs:__imp_GetCurrentThreadId
0x180005259  xor     ebx, ebx
0x18000525b  mov     cs:dword_180025A68, eax
0x180005261  add     cs:?g_NumNetSetupHandles@@3KA, 0FFFFFFFFh; ulong g_NumNetSetupHandles
0x180005268  jnz     short loc_180005285
0x18000526a  mov     rcx, cs:?g_NetSetupEngine@@3PEAUHINSTANCE__@@EA; hLibModule
0x180005271  call    cs:__imp_FreeLibrary
0x180005277  mov     cs:?g_NetSetupEngine@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_NetSetupEngine
0x18000527e  mov     cs:?g_NetSetupGetEnginePfn@@3P6APEAVNetSetupImplementation@@KPEAU_NETSETUP_ENVIRONMENT@@@ZEA, rbx; NetSetupImplementation * (*g_NetSetupGetEnginePfn)(ulong,_NETSETUP_ENVIRONMENT *)
0x180005285  lea     rcx, ?g_NetSetupHandleCountLock@@3VRtlSrwLock@@A; RtlSrwLock g_NetSetupHandleCountLock
0x18000528c  mov     cs:dword_180025A68, ebx
0x180005292  add     rsp, 20h
0x180005296  pop     rbx
0x180005297  jmp     cs:__imp_ReleaseSRWLockExclusive
```
