# SE_ShimDllLoaded

- ea: `0x18002f270`
- end: `0x18002f308`
- name: `SE_ShimDllLoaded`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000f114`
- `0x18001f3c4`
- `0x18002f270`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002f2af`
- `ntdll!RtlEnterCriticalSection` at `0x18002f280`
- `ntdll!RtlEnterCriticalSection` at `0x18002f280`

## string_xrefs

- `0x18002f2c3`: `SE_ShimDllLoaded`
- `0x18002f2f5`: `SE_ShimDllLoaded`
- `0x18002f2e8`: `Failed to register shim dll`

## pseudocode

```c
NTSTATUS __fastcall SE_ShimDllLoaded(void *a1)
{
  __int64 v2; // rcx

  if ( RtlEnterCriticalSection(&g_EngineLock) < 0 )
    return AslLogCallPrintf(1, "SE_ShimDllLoaded", 3071, "Failed to lock engine");
  if ( (unsigned int)(g_InitState - 1) > 1 )
  {
    AslLogCallPrintf(1, "SE_ShimDllLoaded", 3084, "Engine not in initialization state.");
  }
  else if ( (int)SeEngineShimDllLoaded(v2, a1) < 0 )
  {
    AslLogCallPrintf(1, "SE_ShimDllLoaded", 3095, "Failed to register shim dll");
  }
  return RtlLeaveCriticalSection(&g_EngineLock);
}

```

## disassembly

```asm
0x18002f270  push    rbx
0x18002f272  sub     rsp, 20h
0x18002f276  mov     rbx, rcx
0x18002f279  lea     rcx, g_EngineLock; CriticalSection
0x18002f280  call    cs:__imp_RtlEnterCriticalSection
0x18002f286  test    eax, eax
0x18002f288  js      short loc_18002F2B6
0x18002f28a  mov     eax, cs:g_InitState
0x18002f290  dec     eax
0x18002f292  cmp     eax, 1
0x18002f295  ja      short loc_18002F2D9
0x18002f297  mov     rdx, rbx
0x18002f29a  call    SeEngineShimDllLoaded
0x18002f29f  test    eax, eax
0x18002f2a1  js      short loc_18002F2E8
0x18002f2a3  lea     rcx, g_EngineLock
0x18002f2aa  add     rsp, 20h
0x18002f2ae  pop     rbx
0x18002f2af  jmp     cs:__imp_RtlLeaveCriticalSection
0x18002f2b6  lea     r9, aFailedToLockEn; "Failed to lock engine"
0x18002f2bd  mov     r8d, 0BFFh
0x18002f2c3  lea     rdx, aSeShimdllloade_0; "SE_ShimDllLoaded"
0x18002f2ca  mov     ecx, 1
0x18002f2cf  add     rsp, 20h
0x18002f2d3  pop     rbx
0x18002f2d4  jmp     AslLogCallPrintf
0x18002f2d9  lea     r9, aEngineNotInIni; "Engine not in initialization state."
0x18002f2e0  mov     r8d, 0C0Ch
0x18002f2e6  jmp     short loc_18002F2F5
0x18002f2e8  lea     r9, aFailedToRegist; "Failed to register shim dll"
0x18002f2ef  mov     r8d, 0C17h
0x18002f2f5  lea     rdx, aSeShimdllloade_0; "SE_ShimDllLoaded"
0x18002f2fc  mov     ecx, 1
0x18002f301  call    AslLogCallPrintf
0x18002f306  jmp     short loc_18002F2A3
```
