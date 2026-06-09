# SE_LdrEntryRemoved

- ea: `0x18001d190`
- end: `0x18001d2a0`
- name: `SE_LdrEntryRemoved`
- size: `272`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f114`
- `0x18001d190`
- `0x18001d2a8`
- `0x18001d358`
- `0x18001d604`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001d232`
- `ntdll!RtlEnterCriticalSection` at `0x18001d1d6`
- `ntdll!RtlEnterCriticalSection` at `0x18001d1d6`

## string_xrefs

- `0x18001d1af`: `SE_LdrEntryRemoved`
- `0x18001d261`: `SE_LdrEntryRemoved`
- `0x18001d28a`: `SE_LdrEntryRemoved`
- `0x18001d278`: `Failed to Com unhook %S`

## pseudocode

```c
NTSTATUS __fastcall SE_LdrEntryRemoved(__int64 a1)
{
  if ( g_InitState != 3 || !g_Engine )
    return (unsigned int)AslLogCallPrintf(1, "SE_LdrEntryRemoved", 2346, "Engine not initialized");
  if ( RtlEnterCriticalSection(&g_EngineLock) < 0 )
    return (unsigned int)AslLogCallPrintf(1, "SE_LdrEntryRemoved", 2358, "Failed to lock engine");
  if ( (int)SeRouterUnhookDll(*(_QWORD *)(g_Engine + 48), a1) < 0 )
    AslLogCallPrintf(1, "SE_LdrEntryRemoved", 2368, "Failed to unhook %S", *(const wchar_t **)(a1 + 96));
  if ( (int)SeComRouterUnhookDll(*(PRTL_CRITICAL_SECTION *)(g_Engine + 56), a1) < 0 )
    AslLogCallPrintf(1, "SE_LdrEntryRemoved", 2373, "Failed to Com unhook %S", *(const wchar_t **)(a1 + 96));
  SeShimManagerNotifyShims(*(_QWORD *)(g_Engine + 16), 105, a1);
  return RtlLeaveCriticalSection(&g_EngineLock);
}

```

## disassembly

```asm
0x18001d190  push    rbx
0x18001d192  sub     rsp, 30h
0x18001d196  cmp     cs:g_InitState, 3
0x18001d19d  mov     rbx, rcx
0x18001d1a0  jz      short loc_18001D1C5
0x18001d1a2  lea     r9, aEngineNotIniti_0; "Engine not initialized"
0x18001d1a9  mov     r8d, 92Ah
0x18001d1af  lea     rdx, aSeLdrentryremo_0; "SE_LdrEntryRemoved"
0x18001d1b6  mov     ecx, 1
0x18001d1bb  add     rsp, 30h
0x18001d1bf  pop     rbx
0x18001d1c0  jmp     AslLogCallPrintf
0x18001d1c5  cmp     cs:g_Engine, 0
0x18001d1cd  jz      short loc_18001D1A2
0x18001d1cf  lea     rcx, g_EngineLock; CriticalSection
0x18001d1d6  call    cs:__imp_RtlEnterCriticalSection
0x18001d1dc  test    eax, eax
0x18001d1de  js      short loc_18001D239
0x18001d1e0  mov     rcx, cs:g_Engine
0x18001d1e7  mov     rdx, rbx
0x18001d1ea  mov     rcx, [rcx+30h]
0x18001d1ee  call    SeRouterUnhookDll
0x18001d1f3  test    eax, eax
0x18001d1f5  js      short loc_18001D24B
0x18001d1f7  mov     rcx, cs:g_Engine
0x18001d1fe  mov     rdx, rbx
0x18001d201  mov     rcx, [rcx+38h]; CriticalSection
0x18001d205  call    SeComRouterUnhookDll
0x18001d20a  test    eax, eax
0x18001d20c  js      short loc_18001D274
0x18001d20e  mov     rcx, cs:g_Engine
0x18001d215  mov     r8, rbx
0x18001d218  mov     edx, 69h ; 'i'
0x18001d21d  mov     rcx, [rcx+10h]
0x18001d221  call    SeShimManagerNotifyShims
0x18001d226  lea     rcx, g_EngineLock
0x18001d22d  add     rsp, 30h
0x18001d231  pop     rbx
0x18001d232  jmp     cs:__imp_RtlLeaveCriticalSection
0x18001d239  lea     r9, aFailedToLockEn; "Failed to lock engine"
0x18001d240  mov     r8d, 936h
0x18001d246  jmp     loc_18001D1AF
0x18001d24b  mov     rax, [rbx+60h]
0x18001d24f  lea     r9, aFailedToUnhook; "Failed to unhook %S"
0x18001d256  mov     r8d, 940h
0x18001d25c  mov     [rsp+38h+var_18], rax
0x18001d261  lea     rdx, aSeLdrentryremo_0; "SE_LdrEntryRemoved"
0x18001d268  mov     ecx, 1
0x18001d26d  call    AslLogCallPrintf
0x18001d272  jmp     short loc_18001D1F7
0x18001d274  mov     rax, [rbx+60h]
0x18001d278  lea     r9, aFailedToComUnh; "Failed to Com unhook %S"
0x18001d27f  mov     r8d, 945h
0x18001d285  mov     [rsp+38h+var_18], rax
0x18001d28a  lea     rdx, aSeLdrentryremo_0; "SE_LdrEntryRemoved"
0x18001d291  mov     ecx, 1
0x18001d296  call    AslLogCallPrintf
0x18001d29b  jmp     loc_18001D20E
```
