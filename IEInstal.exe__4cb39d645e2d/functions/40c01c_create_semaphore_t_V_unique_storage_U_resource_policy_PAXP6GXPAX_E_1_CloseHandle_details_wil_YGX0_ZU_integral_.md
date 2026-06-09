# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QAEJJJPBGKPAU_SECURITY_ATTRIBUTES@@PA_N@Z

- ea: `0x40c01c`
- end: `0x40c060`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QAEJJJPBGKPAU_SECURITY_ATTRIBUTES@@PA_N@Z`
- size: `68`
- prototype: `int __thiscall(void *this, LONG lInitialCount, LONG lMaximumCount, const WCHAR *lpName, int, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x40aec9`

## callees

- `0x40a9c3`
- `0x40c01c`
- `0x40c066`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x40c037`
- `KERNEL32!CreateSemaphoreExW` at `0x40c037`
- `KERNEL32!GetLastError` at `0x40c043`
- `KERNEL32!GetLastError` at `0x40c043`

## pseudocode

```c
int __thiscall _create___semaphore_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJJJPBGKPAU_SECURITY_ATTRIBUTES__PA_N_Z(
        void *this,
        LONG lInitialCount,
        LONG lMaximumCount,
        const WCHAR *lpName,
        int a5,
        int a6,
        int a7)
{
  HANDLE Semaphore; // esi
  wil::details *v10; // [esp+0h] [ebp-8h]

  Semaphore = CreateSemaphoreExW(0, lInitialCount, lMaximumCount, lpName, 0, 0x1F0003u);
  if ( !Semaphore )
    return wil::details::GetLastErrorFailHr(v10);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__QAEXPAX_Z(
    this,
    Semaphore);
  return 0;
}

```

## disassembly

```asm
0x40c01c  mov     edi, edi
0x40c01e  push    ebp
0x40c01f  mov     ebp, esp
0x40c021  push    esi
0x40c022  push    edi; this
0x40c023  push    1F0003h; dwDesiredAccess
0x40c028  push    0; dwFlags
0x40c02a  push    [ebp+lpName]; lpName
0x40c02d  mov     edi, ecx
0x40c02f  push    [ebp+lMaximumCount]; lMaximumCount
0x40c032  push    [ebp+lInitialCount]; lInitialCount
0x40c035  push    0; lpSemaphoreAttributes
0x40c037  call    ds:__imp__CreateSemaphoreExW@24; CreateSemaphoreExW(x,x,x,x,x,x)
0x40c03d  mov     esi, eax
0x40c03f  test    esi, esi
0x40c041  jz      short loc_40C055
0x40c043  call    ds:__imp__GetLastError@0; GetLastError()
0x40c049  push    esi
0x40c04a  mov     ecx, edi
0x40c04c  call    ?reset@?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAEXPAX@Z
0x40c051  xor     eax, eax
0x40c053  jmp     short loc_40C05A
0x40c055  call    ?GetLastErrorFailHr@details@wil@@YGJXZ; wil::details::GetLastErrorFailHr(void)
0x40c05a  pop     edi
0x40c05b  pop     esi
0x40c05c  pop     ebp
0x40c05d  retn    18h
```
