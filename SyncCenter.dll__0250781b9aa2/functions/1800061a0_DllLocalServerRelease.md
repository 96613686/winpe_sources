# DllLocalServerRelease

- ea: `0x1800061a0`
- end: `0x1800061f9`
- name: `DllLocalServerRelease`
- size: `89`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001139c`
- `0x180012368`
- `0x180012ce0`
- `0x18001b260`
- `0x18001b520`
- `0x18001f2e4`
- `0x18001f610`
- `0x180021840`
- `0x180025bb4`

## callees

- `0x1800061a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800061c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800061c0`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x1800061ad`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x1800061ad`
- `USER32!PostThreadMessageW` at `0x1800061eb`
- `USER32!PostThreadMessageW` at `0x1800061eb`

## pseudocode

```c
ULONG DllLocalServerRelease()
{
  ULONG result; // eax

  _InterlockedDecrement(&g_cRefThisDll);
  result = CoReleaseServerProcess();
  if ( !result )
  {
    EnterCriticalSection(&g_DllCriticalSection);
    byte_180070BB0 = 1;
    LeaveCriticalSection(&g_DllCriticalSection);
    PostThreadMessageW(idThread, 0x12u, 0, 0);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800061a0  push    rbx
0x1800061a2  sub     rsp, 20h
0x1800061a6  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x1800061ad  call    cs:__imp_CoReleaseServerProcess
0x1800061b3  mov     ebx, eax
0x1800061b5  test    eax, eax
0x1800061b7  jnz     short loc_1800061F3
0x1800061b9  lea     rcx, ?g_DllCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800061c0  call    cs:__imp_EnterCriticalSection
0x1800061c6  lea     rcx, ?g_DllCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800061cd  mov     cs:byte_180070BB0, 1
0x1800061d4  call    cs:__imp_LeaveCriticalSection
0x1800061da  mov     ecx, cs:idThread; idThread
0x1800061e0  xor     r9d, r9d; lParam
0x1800061e3  xor     r8d, r8d; wParam
0x1800061e6  mov     edx, 12h; Msg
0x1800061eb  call    cs:__imp_PostThreadMessageW
0x1800061f1  mov     eax, ebx
0x1800061f3  add     rsp, 20h
0x1800061f7  pop     rbx
0x1800061f8  retn
```
