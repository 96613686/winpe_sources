# RevokeClassFactory(void)

- ea: `0x402bbc`
- end: `0x402bee`
- name: `?RevokeClassFactory@@YGJXZ`
- size: `50`
- prototype: `HRESULT __stdcall()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x402bf4`
- `0x409212`

## callees

- `0x402bbc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x402be0`
- `KERNEL32!DeleteCriticalSection` at `0x402be0`
- `ole32!CoRevokeClassObject` at `0x402bd3`
- `ole32!CoRevokeClassObject` at `0x402bd3`

## pseudocode

```c
HRESULT __stdcall RevokeClassFactory()
{
  HRESULT v0; // esi

  if ( _InterlockedExchange(&g_fClassRegistered, 0) != 1 )
    return 0;
  v0 = CoRevokeClassObject(g_dwRegister);
  DeleteCriticalSection(&g_DetourCriticalSection);
  return v0;
}

```

## disassembly

```asm
0x402bbc  mov     edi, edi
0x402bbe  push    esi
0x402bbf  xor     eax, eax
0x402bc1  mov     ecx, offset ?g_fClassRegistered@@3JA; long g_fClassRegistered
0x402bc6  xchg    eax, [ecx]
0x402bc8  cmp     eax, 1
0x402bcb  jnz     short loc_402BE8
0x402bcd  push    ?g_dwRegister@@3KA; dwRegister
0x402bd3  call    ds:__imp__CoRevokeClassObject@4; CoRevokeClassObject(x)
0x402bd9  push    offset ?g_DetourCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x402bde  mov     esi, eax
0x402be0  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x402be6  jmp     short loc_402BEA
0x402be8  xor     esi, esi
0x402bea  mov     eax, esi
0x402bec  pop     esi
0x402bed  retn
```
