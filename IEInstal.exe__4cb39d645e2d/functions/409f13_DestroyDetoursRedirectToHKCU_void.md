# DestroyDetoursRedirectToHKCU(void)

- ea: `0x409f13`
- end: `0x409f7e`
- name: `?DestroyDetoursRedirectToHKCU@@YGJXZ`
- size: `107`
- prototype: `int __stdcall()`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x4044ae`
- `0x409e01`

## callees

- `0x409f13`
- `0x40dc30`
- `0x40dd60`
- `0x40ddf0`
- `0x40e280`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x409f38`
- `KERNEL32!GetCurrentThread` at `0x409f38`
- `KERNEL32!LeaveCriticalSection` at `0x409f73`
- `KERNEL32!LeaveCriticalSection` at `0x409f73`
- `KERNEL32!EnterCriticalSection` at `0x409f1f`
- `KERNEL32!EnterCriticalSection` at `0x409f1f`

## pseudocode

```c
int __stdcall DestroyDetoursRedirectToHKCU()
{
  int v0; // esi
  HANDLE CurrentThread; // eax

  v0 = 0;
  EnterCriticalSection(&g_DetourCriticalSection);
  if ( g_fRegisterTypeLibDetoured )
  {
    v0 = DetourTransactionBegin();
    if ( !v0 )
    {
      CurrentThread = GetCurrentThread();
      DetourUpdateThread(CurrentThread);
      DetourDetach((int)&dword_40F5A0, Detour_RegisterTypeLib);
      DetourDetach((int)&dword_40F5A4, Detour_UnRegisterTypeLib);
      v0 = DetourTransactionCommit();
      if ( !v0 )
        g_fRegisterTypeLibDetoured = 0;
    }
  }
  LeaveCriticalSection(&g_DetourCriticalSection);
  return v0;
}

```

## disassembly

```asm
0x409f13  mov     edi, edi
0x409f15  push    esi
0x409f16  push    edi
0x409f17  mov     edi, offset ?g_DetourCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_DetourCriticalSection
0x409f1c  xor     esi, esi
0x409f1e  push    edi; lpCriticalSection
0x409f1f  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x409f25  cmp     ?g_fRegisterTypeLibDetoured@@3HA, esi; int g_fRegisterTypeLibDetoured
0x409f2b  jz      short loc_409F72
0x409f2d  call    _DetourTransactionBegin@0; DetourTransactionBegin()
0x409f32  mov     esi, eax
0x409f34  test    esi, esi
0x409f36  jnz     short loc_409F72
0x409f38  call    ds:__imp__GetCurrentThread@0; GetCurrentThread()
0x409f3e  push    eax; hThread
0x409f3f  call    _DetourUpdateThread@4; DetourUpdateThread(x)
0x409f44  push    offset ?Detour_RegisterTypeLib@@YGJPAUITypeLib@@PAG1@Z; lpAddress
0x409f49  push    offset dword_40F5A0; int
0x409f4e  call    _DetourDetach@8; DetourDetach(x,x)
0x409f53  push    offset ?Detour_UnRegisterTypeLib@@YGJABU_GUID@@GGKW4tagSYSKIND@@@Z; lpAddress
0x409f58  push    offset dword_40F5A4; int
0x409f5d  call    _DetourDetach@8; DetourDetach(x,x)
0x409f62  call    _DetourTransactionCommit@0; DetourTransactionCommit()
0x409f67  mov     esi, eax
0x409f69  test    esi, esi
0x409f6b  jnz     short loc_409F72
0x409f6d  mov     ?g_fRegisterTypeLibDetoured@@3HA, eax; int g_fRegisterTypeLibDetoured
0x409f72  push    edi; lpCriticalSection
0x409f73  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x409f79  pop     edi
0x409f7a  mov     eax, esi
0x409f7c  pop     esi
0x409f7d  retn
```
