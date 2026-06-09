# Locks_Initialize

- ea: `0x18002f1c0`
- end: `0x18002f2c7`
- name: `Locks_Initialize`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180034558`

## callees

- `0x18002f1c0`
- `0x18002f2d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f1ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f1ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f217`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f22e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f245`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f217`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f22e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f245`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002f1d7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002f1d7`

## string_xrefs

- `0x18002f1f8`: `kernel32.dll`
- `0x18002f20d`: `SwitchToThread`

## pseudocode

```c
__int64 Locks_Initialize()
{
  HMODULE ModuleHandleW; // rax
  HMODULE v1; // rbx
  unsigned int (*ProcAddress)(struct _RTL_CRITICAL_SECTION *, unsigned int); // rax

  if ( !g_fLocksInitialized )
  {
    while ( _InterlockedExchange((volatile __int32 *)&g_lckInit, 1) )
      Sleep(0);
    if ( !g_fLocksInitialized )
    {
      ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
      v1 = ModuleHandleW;
      if ( ModuleHandleW )
      {
        g_pfnSwitchToThread = (int (*)(void))GetProcAddress(ModuleHandleW, "SwitchToThread");
        g_pfnTryEnterCritSec = (int (*)(struct _RTL_CRITICAL_SECTION *))GetProcAddress(v1, "TryEnterCriticalSection");
        ProcAddress = (unsigned int (*)(struct _RTL_CRITICAL_SECTION *, unsigned int))GetProcAddress(
                                                                                        v1,
                                                                                        "SetCriticalSectionSpinCount");
        g_pfnSetCSSpinCount = ProcAddress;
      }
      else
      {
        ProcAddress = g_pfnSetCSSpinCount;
      }
      if ( !g_pfnSwitchToThread )
        g_pfnSwitchToThread = (int (*)(void))OBJECT_EXTENSION_TABLE::startPrefixMapping;
      if ( !g_pfnTryEnterCritSec )
        g_pfnTryEnterCritSec = (int (*)(struct _RTL_CRITICAL_SECTION *))OBJECT_EXTENSION_TABLE::startPrefixMapping;
      if ( !ProcAddress )
        g_pfnSetCSSpinCount = (unsigned int (*)(struct _RTL_CRITICAL_SECTION *, unsigned int))OBJECT_EXTENSION_TABLE::startPrefixMapping;
      g_cProcessors = NumProcessors();
      _InterlockedExchange(&g_fLocksInitialized, 1);
    }
    _InterlockedExchange((volatile __int32 *)&g_lckInit, 0);
  }
  return 1;
}

```

## disassembly

```asm
0x18002f1c0  push    rbx
0x18002f1c2  sub     rsp, 20h
0x18002f1c6  cmp     cs:?g_fLocksInitialized@@3HA, 0; int g_fLocksInitialized
0x18002f1cd  jnz     loc_18002F2BC
0x18002f1d3  jmp     short loc_18002F1DD
0x18002f1d5  xor     ecx, ecx; dwMilliseconds
0x18002f1d7  call    cs:__imp_Sleep
0x18002f1dd  mov     eax, 1
0x18002f1e2  xchg    eax, cs:?g_lckInit@@3VCSimpleLock@@A; CSimpleLock g_lckInit
0x18002f1e8  test    eax, eax
0x18002f1ea  jnz     short loc_18002F1D5
0x18002f1ec  cmp     cs:?g_fLocksInitialized@@3HA, eax; int g_fLocksInitialized
0x18002f1f2  jnz     loc_18002F2B4
0x18002f1f8  lea     rcx, ModuleName; "kernel32.dll"
0x18002f1ff  call    cs:__imp_GetModuleHandleW
0x18002f205  mov     rbx, rax
0x18002f208  test    rax, rax
0x18002f20b  jz      short loc_18002F254
0x18002f20d  lea     rdx, ProcName; "SwitchToThread"
0x18002f214  mov     rcx, rax; hModule
0x18002f217  call    cs:__imp_GetProcAddress
0x18002f21d  lea     rdx, aTryentercritic; "TryEnterCriticalSection"
0x18002f224  mov     rcx, rbx; hModule
0x18002f227  mov     cs:?g_pfnSwitchToThread@@3P6AHXZEA, rax; int (*g_pfnSwitchToThread)(void)
0x18002f22e  call    cs:__imp_GetProcAddress
0x18002f234  lea     rdx, aSetcriticalsec; "SetCriticalSectionSpinCount"
0x18002f23b  mov     rcx, rbx; hModule
0x18002f23e  mov     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, rax; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x18002f245  call    cs:__imp_GetProcAddress
0x18002f24b  mov     cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA, rax; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x18002f252  jmp     short loc_18002F25B
0x18002f254  mov     rax, cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x18002f25b  cmp     cs:?g_pfnSwitchToThread@@3P6AHXZEA, 0; int (*g_pfnSwitchToThread)(void)
0x18002f263  jnz     short loc_18002F273
0x18002f265  lea     rcx, ?startPrefixMapping@OBJECT_EXTENSION_TABLE@@UEAAJPEBGH0H@Z; OBJECT_EXTENSION_TABLE::startPrefixMapping(ushort const *,int,ushort const *,int)
0x18002f26c  mov     cs:?g_pfnSwitchToThread@@3P6AHXZEA, rcx; int (*g_pfnSwitchToThread)(void)
0x18002f273  cmp     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, 0; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x18002f27b  jnz     short loc_18002F28B
0x18002f27d  lea     rcx, ?startPrefixMapping@OBJECT_EXTENSION_TABLE@@UEAAJPEBGH0H@Z; OBJECT_EXTENSION_TABLE::startPrefixMapping(ushort const *,int,ushort const *,int)
0x18002f284  mov     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, rcx; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x18002f28b  test    rax, rax
0x18002f28e  jnz     short loc_18002F29E
0x18002f290  lea     rcx, ?startPrefixMapping@OBJECT_EXTENSION_TABLE@@UEAAJPEBGH0H@Z; OBJECT_EXTENSION_TABLE::startPrefixMapping(ushort const *,int,ushort const *,int)
0x18002f297  mov     cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA, rcx; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x18002f29e  call    NumProcessors
0x18002f2a3  mov     ecx, 1
0x18002f2a8  mov     cs:?g_cProcessors@@3KA, eax; ulong g_cProcessors
0x18002f2ae  xchg    ecx, cs:?g_fLocksInitialized@@3HA; int g_fLocksInitialized
0x18002f2b4  xor     ecx, ecx
0x18002f2b6  xchg    ecx, cs:?g_lckInit@@3VCSimpleLock@@A; CSimpleLock g_lckInit
0x18002f2bc  mov     eax, 1
0x18002f2c1  add     rsp, 20h
0x18002f2c5  pop     rbx
0x18002f2c6  retn
```
