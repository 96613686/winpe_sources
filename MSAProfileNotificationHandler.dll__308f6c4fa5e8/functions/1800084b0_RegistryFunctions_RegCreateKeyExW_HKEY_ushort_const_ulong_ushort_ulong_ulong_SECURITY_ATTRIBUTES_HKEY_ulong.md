# RegistryFunctions::RegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)

- ea: `0x1800084b0`
- end: `0x180008516`
- name: `?RegCreateKeyExW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z`
- size: `102`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, const unsigned __int16 *, DWORD, unsigned __int16 *lpClass, DWORD dwOptions, REGSAM samDesired, struct _SECURITY_ATTRIBUTES *lpSecurityAttributes, HKEY *phkResult, unsigned int *lpdwDisposition)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000850a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000850a`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegCreateKeyExW(
        RegistryFunctions *this,
        HKEY a2,
        const unsigned __int16 *a3,
        DWORD a4,
        unsigned __int16 *lpClass,
        DWORD dwOptions,
        REGSAM samDesired,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        HKEY *phkResult,
        unsigned int *lpdwDisposition)
{
  return RegCreateKeyExW(a2, a3, a4, lpClass, dwOptions, samDesired, lpSecurityAttributes, phkResult, lpdwDisposition);
}

```

## disassembly

```asm
0x1800084b0  push    rbx
0x1800084b2  sub     rsp, 50h
0x1800084b6  mov     rax, [rsp+58h+arg_48]
0x1800084be  mov     r10d, r9d
0x1800084c1  mov     r9, [rsp+58h+lpClass]; lpClass
0x1800084c9  mov     r11, r8
0x1800084cc  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800084d1  mov     rcx, rdx; hKey
0x1800084d4  mov     rax, [rsp+58h+arg_40]
0x1800084dc  mov     r8d, r10d; Reserved
0x1800084df  mov     [rsp+58h+phkResult], rax; phkResult
0x1800084e4  mov     rdx, r11; lpSubKey
0x1800084e7  mov     rax, [rsp+58h+arg_38]
0x1800084ef  mov     [rsp+58h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800084f4  mov     eax, [rsp+58h+arg_30]
0x1800084fb  mov     [rsp+58h+samDesired], eax; samDesired
0x1800084ff  mov     eax, [rsp+58h+arg_28]
0x180008506  mov     [rsp+58h+dwOptions], eax; dwOptions
0x18000850a  call    cs:__imp_RegCreateKeyExW
0x180008510  add     rsp, 50h
0x180008514  pop     rbx
0x180008515  retn
```
