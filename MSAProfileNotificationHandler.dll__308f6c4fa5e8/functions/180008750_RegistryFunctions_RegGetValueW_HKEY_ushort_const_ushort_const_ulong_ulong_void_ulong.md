# RegistryFunctions::RegGetValueW(HKEY__ *,ushort const *,ushort const *,ulong,ulong *,void *,ulong *)

- ea: `0x180008750`
- end: `0x18000879a`
- name: `?RegGetValueW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBG1KPEAKPEAX2@Z`
- size: `74`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, const unsigned __int16 *, const unsigned __int16 *, DWORD dwFlags, unsigned int *pdwType, PVOID pvData, unsigned int *pcbData)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000878e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000878e`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegGetValueW(
        RegistryFunctions *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwFlags,
        unsigned int *pdwType,
        PVOID pvData,
        unsigned int *pcbData)
{
  return RegGetValueW(a2, a3, a4, dwFlags, pdwType, pvData, pcbData);
}

```

## disassembly

```asm
0x180008750  push    rbx
0x180008752  sub     rsp, 40h
0x180008756  mov     rax, [rsp+48h+arg_38]
0x18000875e  mov     r10, r9
0x180008761  mov     r9d, [rsp+48h+dwFlags]; dwFlags
0x180008766  mov     r11, r8
0x180008769  mov     [rsp+48h+pcbData], rax; pcbData
0x18000876e  mov     rcx, rdx; hkey
0x180008771  mov     rax, [rsp+48h+arg_30]
0x180008779  mov     r8, r10; lpValue
0x18000877c  mov     [rsp+48h+pvData], rax; pvData
0x180008781  mov     rdx, r11; lpSubKey
0x180008784  mov     rax, [rsp+48h+arg_28]
0x180008789  mov     [rsp+48h+pdwType], rax; pdwType
0x18000878e  call    cs:__imp_RegGetValueW
0x180008794  add     rsp, 40h
0x180008798  pop     rbx
0x180008799  retn
```
