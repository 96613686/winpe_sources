# InitDetoursRedirectToHKCU(void)

- ea: `0x409e9d`
- end: `0x409f0d`
- name: `?InitDetoursRedirectToHKCU@@YGJXZ`
- size: `112`
- prototype: `int __stdcall()`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x409e01`

## callees

- `0x409e9d`
- `0x40d840`
- `0x40dd60`
- `0x40ddf0`
- `0x40e280`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x409ec2`
- `KERNEL32!GetCurrentThread` at `0x409ec2`
- `KERNEL32!LeaveCriticalSection` at `0x409f02`
- `KERNEL32!LeaveCriticalSection` at `0x409f02`
- `KERNEL32!EnterCriticalSection` at `0x409ea9`
- `KERNEL32!EnterCriticalSection` at `0x409ea9`

## pseudocode

```c
int __stdcall InitDetoursRedirectToHKCU()
{
  int v0; // esi
  HANDLE CurrentThread; // eax

  v0 = 0;
  EnterCriticalSection(&g_DetourCriticalSection);
  if ( !g_fRegisterTypeLibDetoured )
  {
    v0 = DetourTransactionBegin();
    if ( !v0 )
    {
      CurrentThread = GetCurrentThread();
      DetourUpdateThread(CurrentThread);
      DetourAttach((int)&dword_40F5A0, Detour_RegisterTypeLib);
      DetourAttach((int)&dword_40F5A4, Detour_UnRegisterTypeLib);
      v0 = DetourTransactionCommit();
      if ( !v0 )
        g_fRegisterTypeLibDetoured = 1;
    }
  }
  LeaveCriticalSection(&g_DetourCriticalSection);
  return v0;
}

```

## disassembly

```asm
0x409e9d  mov     edi, edi
0x409e9f  push    esi
0x409ea0  push    edi
0x409ea1  mov     edi, offset ?g_DetourCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_DetourCriticalSection
0x409ea6  xor     esi, esi
0x409ea8  push    edi; lpCriticalSection
0x409ea9  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x409eaf  cmp     ?g_fRegisterTypeLibDetoured@@3HA, esi; int g_fRegisterTypeLibDetoured
0x409eb5  jnz     short loc_409F01
0x409eb7  call    _DetourTransactionBegin@0; DetourTransactionBegin()
0x409ebc  mov     esi, eax
0x409ebe  test    esi, esi
0x409ec0  jnz     short loc_409F01
0x409ec2  call    ds:__imp__GetCurrentThread@0; GetCurrentThread()
0x409ec8  push    eax; hThread
0x409ec9  call    _DetourUpdateThread@4; DetourUpdateThread(x)
0x409ece  push    offset ?Detour_RegisterTypeLib@@YGJPAUITypeLib@@PAG1@Z; lpAddress
0x409ed3  push    offset dword_40F5A0; int
0x409ed8  call    _DetourAttach@8; DetourAttach(x,x)
0x409edd  push    offset ?Detour_UnRegisterTypeLib@@YGJABU_GUID@@GGKW4tagSYSKIND@@@Z; lpAddress
0x409ee2  push    offset dword_40F5A4; int
0x409ee7  call    _DetourAttach@8; DetourAttach(x,x)
0x409eec  call    _DetourTransactionCommit@0; DetourTransactionCommit()
0x409ef1  mov     esi, eax
0x409ef3  test    esi, esi
0x409ef5  jnz     short loc_409F01
0x409ef7  mov     ?g_fRegisterTypeLibDetoured@@3HA, 1; int g_fRegisterTypeLibDetoured
0x409f01  push    edi; lpCriticalSection
0x409f02  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x409f08  pop     edi
0x409f09  mov     eax, esi
0x409f0b  pop     esi
0x409f0c  retn
```
