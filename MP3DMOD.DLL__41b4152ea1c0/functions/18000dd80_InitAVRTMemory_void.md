# InitAVRTMemory(void)

- ea: `0x18000dd80`
- end: `0x18000de41`
- name: `?InitAVRTMemory@@YAXXZ`
- size: `193`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000bf40`
- `0x18000e084`

## callees

- `0x18000dd80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd8b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000de0b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000de0b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000dde1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000dde1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ddb0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ddb0`

## pseudocode

```c
void InitAVRTMemory(void)
{
  HMODULE Library; // rcx

  EnterCriticalSection(&g_CriticalSection);
  if ( !pAddRTMemorySection || !pRemoveRTMemorySection )
  {
    if ( GetModuleHandleW(L"mfplat") )
    {
      pAddRTMemorySection = (int (*)(void *, void **))DummyRemoveRTMemorySection;
LABEL_8:
      pRemoveRTMemorySection = (int (*)(void *))DummyRemoveRTMemorySection;
      goto LABEL_9;
    }
    Library = LoadLibraryExW(L"mfplat", 0, 0x800u);
    if ( !Library )
    {
      pAddRTMemorySection = (int (*)(void *, void **))DummyAddRTMemorySection;
      goto LABEL_8;
    }
    pAddRTMemorySection = (int (*)(void *, void **))DummyRemoveRTMemorySection;
    pRemoveRTMemorySection = (int (*)(void *))DummyRemoveRTMemorySection;
    FreeLibrary(Library);
  }
LABEL_9:
  LeaveCriticalSection(&g_CriticalSection);
}

```

## disassembly

```asm
0x18000dd80  sub     rsp, 28h
0x18000dd84  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dd8b  call    cs:__imp_EnterCriticalSection
0x18000dd91  cmp     cs:?pAddRTMemorySection@@3P6AJPEAXPEAPEAX@ZEA, 0; long (*pAddRTMemorySection)(void *,void * *)
0x18000dd99  jz      short loc_18000DDA9
0x18000dd9b  cmp     cs:?pRemoveRTMemorySection@@3P6AJPEAX@ZEA, 0; long (*pRemoveRTMemorySection)(void *)
0x18000dda3  jnz     loc_18000DE2F
0x18000dda9  lea     rcx, ModuleName; "mfplat"
0x18000ddb0  call    cs:__imp_GetModuleHandleW
0x18000ddb6  test    rax, rax
0x18000ddb9  jz      short loc_18000DDD2
0x18000ddbb  lea     rax, ?DummyRemoveRTMemorySection@@YAJPEAX@Z; DummyRemoveRTMemorySection(void *)
0x18000ddc2  mov     cs:?pAddRTMemorySection@@3P6AJPEAXPEAPEAX@ZEA, rax; long (*pAddRTMemorySection)(void *,void * *)
0x18000ddc9  lea     rax, ?DummyRemoveRTMemorySection@@YAJPEAX@Z; DummyRemoveRTMemorySection(void *)
0x18000ddd0  jmp     short loc_18000DE28
0x18000ddd2  xor     edx, edx; hFile
0x18000ddd4  lea     rcx, ModuleName; "mfplat"
0x18000dddb  mov     r8d, 800h; dwFlags
0x18000dde1  call    cs:__imp_LoadLibraryExW
0x18000dde7  mov     rcx, rax; hLibModule
0x18000ddea  test    rax, rax
0x18000dded  jz      short loc_18000DE13
0x18000ddef  lea     rax, ?DummyRemoveRTMemorySection@@YAJPEAX@Z; DummyRemoveRTMemorySection(void *)
0x18000ddf6  mov     cs:?pAddRTMemorySection@@3P6AJPEAXPEAPEAX@ZEA, rax; long (*pAddRTMemorySection)(void *,void * *)
0x18000ddfd  lea     rax, ?DummyRemoveRTMemorySection@@YAJPEAX@Z; DummyRemoveRTMemorySection(void *)
0x18000de04  mov     cs:?pRemoveRTMemorySection@@3P6AJPEAX@ZEA, rax; long (*pRemoveRTMemorySection)(void *)
0x18000de0b  call    cs:__imp_FreeLibrary
0x18000de11  jmp     short loc_18000DE2F
0x18000de13  lea     rax, ?DummyAddRTMemorySection@@YAJPEAXPEAPEAX@Z; DummyAddRTMemorySection(void *,void * *)
0x18000de1a  mov     cs:?pAddRTMemorySection@@3P6AJPEAXPEAPEAX@ZEA, rax; long (*pAddRTMemorySection)(void *,void * *)
0x18000de21  lea     rax, ?DummyRemoveRTMemorySection@@YAJPEAX@Z; DummyRemoveRTMemorySection(void *)
0x18000de28  mov     cs:?pRemoveRTMemorySection@@3P6AJPEAX@ZEA, rax; long (*pRemoveRTMemorySection)(void *)
0x18000de2f  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CriticalSection
0x18000de36  add     rsp, 28h
0x18000de3a  jmp     cs:__imp_LeaveCriticalSection
```
