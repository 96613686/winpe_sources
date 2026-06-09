# EasEngineUninitialize

- ea: `0x180094c88`
- end: `0x180094d55`
- name: `EasEngineUninitialize`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009212c`

## callees

- `0x1800680e4`
- `0x180094c88`
- `0x180094fd4`
- `0x18009d010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180094c97`
- `ntdll!RtlAcquireResourceExclusive` at `0x180094c97`
- `ntdll!RtlReleaseResource` at `0x180094d47`
- `ntdll!RtlReleaseResource` at `0x180094d47`
- `ntdll!RtlDeleteResource` at `0x180094d1b`
- `ntdll!RtlDeleteResource` at `0x180094d1b`

## string_xrefs

- `0x180094cba`: `onecore\ds\security\eas\policyengine\initialize.cpp`

## pseudocode

```c
__int64 EasEngineUninitialize()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx

  RtlAcquireResourceExclusive(&g_lockObject, 1u);
  v0 = g_dwRefCount;
  v1 = 0;
  if ( g_dwRefCount )
  {
    --g_dwRefCount;
    if ( v0 == 1 )
    {
      g_bInitialized = 0;
      if ( g_Uninitialize )
      {
        g_Uninitialize();
        g_Uninitialize = 0;
      }
      RtlDeleteResource(&g_EvalLock);
      if ( qword_1800D4010 )
      {
        EncryptHandle::DestroyEncryptHandle(qword_1800D4010);
        qword_1800D4010 = 0;
      }
      g_pFnLog = 0;
    }
  }
  else
  {
    v1 = -2147483611;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      2147483685LL,
      L"onecore\\ds\\security\\eas\\policyengine\\initialize.cpp",
      116,
      L"Extra EasEngineUninitialize call",
      &sourceString);
  }
  RtlReleaseResource(&g_lockObject);
  return v1;
}

```

## disassembly

```asm
0x180094c88  push    rbx
0x180094c8a  sub     rsp, 40h
0x180094c8e  mov     dl, 1; Wait
0x180094c90  lea     rcx, ?g_lockObject@@3VLibraryInitLock@@A; Resource
0x180094c97  call    cs:__imp_RtlAcquireResourceExclusive
0x180094c9d  mov     eax, cs:?g_dwRefCount@@3KA; ulong g_dwRefCount
0x180094ca3  xor     ebx, ebx
0x180094ca5  test    eax, eax
0x180094ca7  jnz     short loc_180094CEB
0x180094ca9  lea     rax, sourceString
0x180094cb0  mov     ebx, 80000025h
0x180094cb5  mov     [rsp+48h+var_18], rax
0x180094cba  lea     r9, aOnecoreDsSecur_1; "onecore\\ds\\security\\eas\\policyengin"...
0x180094cc1  lea     rax, aExtraEasengine; "Extra EasEngineUninitialize call"
0x180094cc8  mov     r8d, ebx
0x180094ccb  mov     [rsp+48h+var_20], rax
0x180094cd0  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180094cd7  mov     ecx, 1; unsigned int
0x180094cdc  mov     [rsp+48h+var_28], 74h ; 't'
0x180094ce4  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180094ce9  jmp     short loc_180094D40
0x180094ceb  add     eax, 0FFFFFFFFh
0x180094cee  mov     cs:?g_dwRefCount@@3KA, eax; ulong g_dwRefCount
0x180094cf4  jnz     short loc_180094D40
0x180094cf6  mov     rax, cs:?g_Uninitialize@@3P6AXXZEA; void (*g_Uninitialize)(void)
0x180094cfd  mov     cs:?g_bInitialized@@3HA, ebx; int g_bInitialized
0x180094d03  test    rax, rax
0x180094d06  jz      short loc_180094D14
0x180094d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094d0d  mov     cs:?g_Uninitialize@@3P6AXXZEA, rbx; void (*g_Uninitialize)(void)
0x180094d14  lea     rcx, ?g_EvalLock@@3U_RTL_RESOURCE@@A; Resource
0x180094d1b  call    cs:__imp_RtlDeleteResource
0x180094d21  mov     rcx, cs:qword_1800D4010; struct EncryptHandle *
0x180094d28  test    rcx, rcx
0x180094d2b  jz      short loc_180094D39
0x180094d2d  call    ?DestroyEncryptHandle@EncryptHandle@@SAXPEAV1@@Z; EncryptHandle::DestroyEncryptHandle(EncryptHandle *)
0x180094d32  mov     cs:qword_1800D4010, rbx
0x180094d39  mov     cs:?g_pFnLog@@3P6AXKPEAG@ZEA, rbx; void (*g_pFnLog)(ulong,ushort *)
0x180094d40  lea     rcx, ?g_lockObject@@3VLibraryInitLock@@A; Resource
0x180094d47  call    cs:__imp_RtlReleaseResource
0x180094d4d  mov     eax, ebx
0x180094d4f  add     rsp, 40h
0x180094d53  pop     rbx
0x180094d54  retn
```
