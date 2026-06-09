# RegistryFunctions::RegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)

- ea: `0x1800162c0`
- end: `0x180016326`
- name: `?RegCreateKeyExW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z`
- size: `102`
- prototype: `int(RegistryFunctions *__hidden this, HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, HKEY *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001631a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001631a`

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
0x1800162c0  push    rbx
0x1800162c2  sub     rsp, 50h
0x1800162c6  mov     rax, [rsp+58h+arg_48]
0x1800162ce  mov     r10d, r9d
0x1800162d1  mov     r9, [rsp+58h+lpClass]; lpClass
0x1800162d9  mov     r11, r8
0x1800162dc  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800162e1  mov     rcx, rdx; hKey
0x1800162e4  mov     rax, [rsp+58h+arg_40]
0x1800162ec  mov     r8d, r10d; Reserved
0x1800162ef  mov     [rsp+58h+phkResult], rax; phkResult
0x1800162f4  mov     rdx, r11; lpSubKey
0x1800162f7  mov     rax, [rsp+58h+arg_38]
0x1800162ff  mov     [rsp+58h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180016304  mov     eax, [rsp+58h+arg_30]
0x18001630b  mov     [rsp+58h+samDesired], eax; samDesired
0x18001630f  mov     eax, [rsp+58h+arg_28]
0x180016316  mov     [rsp+58h+dwOptions], eax; dwOptions
0x18001631a  call    cs:__imp_RegCreateKeyExW
0x180016320  add     rsp, 50h
0x180016324  pop     rbx
0x180016325  retn
```
