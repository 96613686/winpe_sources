# DMUI_GetUserPermission

- ea: `0x180007a40`
- end: `0x180007b3a`
- name: `DMUI_GetUserPermission`
- size: `250`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, const unsigned __int16 *, __int64, unsigned __int16 *, unsigned __int16 *, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000743c`
- `0x1800074dc`
- `0x180007a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180007a68`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180007a68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007afb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007afb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007b1b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007b1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007a77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007adc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007a77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007adc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b0c`

## pseudocode

```c
__int64 __fastcall DMUI_GetUserPermission(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        __int64 a7,
        _DWORD *a8)
{
  int CommandLine; // ebx
  HLOCAL hMem; // [rsp+30h] [rbp-18h] BYREF

  hMem = 0;
  InitializeCriticalSection(&g_csDmUi);
  EnterCriticalSection(&g_csDmUi);
  g_fUserAccepted = 0;
  LeaveCriticalSection(&g_csDmUi);
  CommandLine = CreateCommandLine(a2, a3, a5, a6, 0, (unsigned __int16 **)&hMem);
  if ( CommandLine >= 0 )
  {
    CommandLine = LaunchDmDesktopUI((LPWSTR)hMem);
    if ( CommandLine >= 0 )
    {
      EnterCriticalSection(&g_csDmUi);
      *a8 = g_fUserAccepted;
      LeaveCriticalSection(&g_csDmUi);
    }
  }
  LocalFree(hMem);
  DeleteCriticalSection(&g_csDmUi);
  return (unsigned int)CommandLine;
}

```

## disassembly

```asm
0x180007a40  mov     [rsp+arg_0], rbx
0x180007a45  mov     [rsp+arg_8], rsi
0x180007a4a  push    rdi
0x180007a4b  sub     rsp, 40h
0x180007a4f  lea     rsi, ?g_csDmUi@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csDmUi
0x180007a56  mov     [rsp+48h+hMem], 0
0x180007a5f  mov     rcx, rsi; lpCriticalSection
0x180007a62  mov     rbx, r8
0x180007a65  mov     rdi, rdx
0x180007a68  call    cs:__imp_InitializeCriticalSection
0x180007a6f  nop     dword ptr [rax+rax+00h]
0x180007a74  mov     rcx, rsi; lpCriticalSection
0x180007a77  call    cs:__imp_EnterCriticalSection
0x180007a7e  nop     dword ptr [rax+rax+00h]
0x180007a83  mov     rcx, rsi; lpCriticalSection
0x180007a86  mov     cs:?g_fUserAccepted@@3HA, 0; int g_fUserAccepted
0x180007a90  call    cs:__imp_LeaveCriticalSection
0x180007a97  nop     dword ptr [rax+rax+00h]
0x180007a9c  mov     r9, [rsp+48h+arg_28]; unsigned __int16 *
0x180007aa1  lea     rax, [rsp+48h+hMem]
0x180007aa6  mov     r8, [rsp+48h+arg_20]; unsigned __int16 *
0x180007aab  mov     rdx, rbx; unsigned __int16 *
0x180007aae  mov     [rsp+48h+var_20], rax; unsigned __int16 **
0x180007ab3  mov     rcx, rdi; unsigned __int16 *
0x180007ab6  mov     [rsp+48h+var_28], 0; int
0x180007abe  call    ?CreateCommandLine@@YAJPEBG000HPEAPEAG@Z; CreateCommandLine(ushort const *,ushort const *,ushort const *,ushort const *,int,ushort * *)
0x180007ac3  mov     ebx, eax
0x180007ac5  test    eax, eax
0x180007ac7  js      short loc_180007B07
0x180007ac9  mov     rcx, [rsp+48h+hMem]; lpCommandLine
0x180007ace  call    ?LaunchDmDesktopUI@@YAJPEAG@Z; LaunchDmDesktopUI(ushort *)
0x180007ad3  mov     ebx, eax
0x180007ad5  test    eax, eax
0x180007ad7  js      short loc_180007B07
0x180007ad9  mov     rcx, rsi; lpCriticalSection
0x180007adc  call    cs:__imp_EnterCriticalSection
0x180007ae3  nop     dword ptr [rax+rax+00h]
0x180007ae8  mov     rdx, [rsp+48h+arg_38]
0x180007af0  mov     rcx, rsi; lpCriticalSection
0x180007af3  mov     eax, cs:?g_fUserAccepted@@3HA; int g_fUserAccepted
0x180007af9  mov     [rdx], eax
0x180007afb  call    cs:__imp_LeaveCriticalSection
0x180007b02  nop     dword ptr [rax+rax+00h]
0x180007b07  mov     rcx, [rsp+48h+hMem]; hMem
0x180007b0c  call    cs:__imp_LocalFree
0x180007b13  nop     dword ptr [rax+rax+00h]
0x180007b18  mov     rcx, rsi; lpCriticalSection
0x180007b1b  call    cs:__imp_DeleteCriticalSection
0x180007b22  nop     dword ptr [rax+rax+00h]
0x180007b27  mov     rsi, [rsp+48h+arg_8]
0x180007b2c  mov     eax, ebx
0x180007b2e  mov     rbx, [rsp+48h+arg_0]
0x180007b33  add     rsp, 40h
0x180007b37  pop     rdi
0x180007b38  retn
```
