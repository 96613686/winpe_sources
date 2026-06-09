# DllProcessAttach(HINSTANCE__ *)

- ea: `0x18000ddc8`
- end: `0x18000de9e`
- name: `?DllProcessAttach@@YAHPEAUHINSTANCE__@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000fc30`

## callees

- `0x18000ddc8`
- `0x18000dea4`
- `0x18000e968`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000ddef`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000ddef`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000de8a`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000de8a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000de19`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000de19`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ddcc`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ddcc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000de4c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000de4c`

## pseudocode

```c
__int64 __fastcall DllProcessAttach(HINSTANCE a1)
{
  int v1; // edx
  struct _RTL_CRITICAL_SECTION **v2; // rcx
  int v3; // edx
  struct _RTL_CRITICAL_SECTION **v4; // rcx
  __int64 result; // rax
  _SYSTEM_INFO SystemInfo; // [rsp+20h] [rbp-38h] BYREF

  DisableThreadLibraryCalls(a1);
  hHeap = NtCurrentPeb()->ProcessHeap;
  if ( hHeap )
  {
    gTlsIndex = TlsAlloc();
    if ( gTlsIndex != -1 )
    {
      if ( (unsigned int)mmInitializeMultipleCriticalSections(v2, v1) )
      {
        hEventApiInit = CreateEventW(0, 1, 0, 0);
        if ( hEventApiInit )
        {
          gfValidCS = 1;
          memset(&SystemInfo, 0, sizeof(SystemInfo));
          GetSystemInfo(&SystemInfo);
          result = 1;
          gdwMinVirtualAddress = (__int64)SystemInfo.lpMinimumApplicationAddress;
          gdwMaxVirtualAddress = (__int64)SystemInfo.lpMaximumApplicationAddress;
          return result;
        }
        hEventApiInit = 0;
        mmDeleteMultipleCriticalSections(v4, v3);
      }
      TlsFree(gTlsIndex);
      gTlsIndex = -1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000ddc8  sub     rsp, 58h
0x18000ddcc  call    cs:__imp_DisableThreadLibraryCalls
0x18000ddd2  mov     rax, gs:60h
0x18000dddb  mov     rcx, [rax+30h]
0x18000dddf  mov     cs:hHeap, rcx
0x18000dde6  test    rcx, rcx
0x18000dde9  jz      loc_18000DE9A
0x18000ddef  call    cs:__imp_TlsAlloc
0x18000ddf5  mov     cs:gTlsIndex, eax
0x18000ddfb  cmp     eax, 0FFFFFFFFh
0x18000ddfe  jz      loc_18000DE9A
0x18000de04  call    ?mmInitializeMultipleCriticalSections@@YAHPEAPEAU_RTL_CRITICAL_SECTION@@J@Z; mmInitializeMultipleCriticalSections(_RTL_CRITICAL_SECTION * *,long)
0x18000de09  test    eax, eax
0x18000de0b  jz      short loc_18000DE84
0x18000de0d  xor     r9d, r9d; lpName
0x18000de10  xor     r8d, r8d; bInitialState
0x18000de13  xor     ecx, ecx; lpEventAttributes
0x18000de15  lea     edx, [r9+1]; bManualReset
0x18000de19  call    cs:__imp_CreateEventW
0x18000de1f  mov     cs:hEventApiInit, rax
0x18000de26  test    rax, rax
0x18000de29  jz      short loc_18000DE74
0x18000de2b  xorps   xmm0, xmm0
0x18000de2e  mov     cs:?gfValidCS@@3HA, 1; int gfValidCS
0x18000de38  lea     rcx, [rsp+58h+SystemInfo]; lpSystemInfo
0x18000de3d  movups  xmmword ptr [rsp+58h+SystemInfo], xmm0
0x18000de42  movups  xmmword ptr [rsp+58h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18000de47  movups  xmmword ptr [rsp+58h+SystemInfo.dwNumberOfProcessors], xmm0
0x18000de4c  call    cs:__imp_GetSystemInfo
0x18000de52  mov     rcx, [rsp+58h+SystemInfo.lpMinimumApplicationAddress]
0x18000de57  mov     eax, 1
0x18000de5c  mov     cs:gdwMinVirtualAddress, rcx
0x18000de63  mov     rcx, [rsp+58h+SystemInfo.lpMaximumApplicationAddress]
0x18000de68  mov     cs:gdwMaxVirtualAddress, rcx
0x18000de6f  add     rsp, 58h
0x18000de73  retn
0x18000de74  mov     cs:hEventApiInit, 0
0x18000de7f  call    ?mmDeleteMultipleCriticalSections@@YAXPEAPEAU_RTL_CRITICAL_SECTION@@J@Z; mmDeleteMultipleCriticalSections(_RTL_CRITICAL_SECTION * *,long)
0x18000de84  mov     ecx, cs:gTlsIndex; dwTlsIndex
0x18000de8a  call    cs:__imp_TlsFree
0x18000de90  mov     cs:gTlsIndex, 0FFFFFFFFh
0x18000de9a  xor     eax, eax
0x18000de9c  jmp     short loc_18000DE6F
```
