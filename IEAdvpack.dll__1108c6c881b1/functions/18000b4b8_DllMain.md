# DllMain

- ea: `0x18000b4b8`
- end: `0x18000b55a`
- name: `DllMain`
- size: `162`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800013a4`

## callees

- `0x18000b4b8`
- `0x18000c334`
- `0x18000c3b8`
- `0x18000c574`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000b531`
- `KERNEL32!CloseHandle` at `0x18000b531`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18000b4ce`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18000b4ce`
- `KERNEL32!InitializeCriticalSection` at `0x18000b4e2`
- `KERNEL32!InitializeCriticalSection` at `0x18000b4e2`
- `KERNEL32!DeleteCriticalSection` at `0x18000b549`
- `KERNEL32!DeleteCriticalSection` at `0x18000b549`

## string_xrefs

- `0x18000b505`: `-------------------- advpack.dll is loaded or Attached ------------------------------\n`
- `0x18000b518`: `-------------------- advpack.dll is unloaded or Detached ----------------------------\n`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      g_hInst = hinstDLL;
      InitializeCriticalSection(&CSPctxSave);
      g_hinstMUI = g_hInst;
      if ( g_hAdvLogFile == (HANDLE)-1LL )
        AdvStartLogging();
      AdvWriteToLog(L"-------------------- advpack.dll is loaded or Attached ------------------------------\r\n");
      AdvLogDateAndTime();
    }
  }
  else
  {
    AdvWriteToLog(
      L"-------------------- advpack.dll is unloaded or Detached ----------------------------\r\n",
      fdwReason,
      lpvReserved);
    if ( g_hAdvLogFile != (HANDLE)-1LL )
    {
      CloseHandle(g_hAdvLogFile);
      g_hAdvLogFile = (HANDLE)-1LL;
    }
    DeleteCriticalSection(&CSPctxSave);
  }
  return 1;
}

```

## disassembly

```asm
0x18000b4b8  push    rbx
0x18000b4ba  sub     rsp, 20h
0x18000b4be  mov     rbx, rcx
0x18000b4c1  test    edx, edx
0x18000b4c3  jz      short loc_18000B518
0x18000b4c5  cmp     edx, 1
0x18000b4c8  jnz     loc_18000B54F
0x18000b4ce  call    cs:__imp_DisableThreadLibraryCalls
0x18000b4d4  lea     rcx, ?CSPctxSave@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b4db  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInst
0x18000b4e2  call    cs:__imp_InitializeCriticalSection
0x18000b4e8  cmp     cs:?g_hAdvLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hAdvLogFile
0x18000b4f0  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x18000b4f7  mov     cs:g_hinstMUI, rax
0x18000b4fe  jnz     short loc_18000B505
0x18000b500  call    ?AdvStartLogging@@YAXXZ; AdvStartLogging(void)
0x18000b505  lea     rcx, aAdvpackDllIsLo; "-------------------- advpack.dll is loa"...
0x18000b50c  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000b511  call    ?AdvLogDateAndTime@@YAXXZ; AdvLogDateAndTime(void)
0x18000b516  jmp     short loc_18000B54F
0x18000b518  lea     rcx, aAdvpackDllIsUn; "-------------------- advpack.dll is unl"...
0x18000b51f  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000b524  mov     rcx, cs:?g_hAdvLogFile@@3PEAXEA; hObject
0x18000b52b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b52f  jz      short loc_18000B542
0x18000b531  call    cs:__imp_CloseHandle
0x18000b537  mov     cs:?g_hAdvLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hAdvLogFile
0x18000b542  lea     rcx, ?CSPctxSave@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b549  call    cs:__imp_DeleteCriticalSection
0x18000b54f  mov     eax, 1
0x18000b554  add     rsp, 20h
0x18000b558  pop     rbx
0x18000b559  retn
```
