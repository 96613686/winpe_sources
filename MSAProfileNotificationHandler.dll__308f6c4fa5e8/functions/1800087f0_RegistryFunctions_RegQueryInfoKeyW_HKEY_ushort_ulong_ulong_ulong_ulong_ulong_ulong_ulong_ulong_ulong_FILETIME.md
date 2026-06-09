# RegistryFunctions::RegQueryInfoKeyW(HKEY__ *,ushort *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,_FILETIME *)

- ea: `0x1800087f0`
- end: `0x180008881`
- name: `?RegQueryInfoKeyW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEAGPEAK22222222PEAU_FILETIME@@@Z`
- size: `145`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, unsigned __int16 *, unsigned int *, unsigned int *lpReserved, unsigned int *lpcSubKeys, unsigned int *lpcbMaxSubKeyLen, unsigned int *lpcbMaxClassLen, unsigned int *lpcValues, unsigned int *lpcbMaxValueNameLen, unsigned int *lpcbMaxValueLen, unsigned int *lpcbSecurityDescriptor, struct _FILETIME *lpftLastWriteTime)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180008875`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180008875`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegQueryInfoKeyW(
        RegistryFunctions *this,
        HKEY a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        unsigned int *lpReserved,
        unsigned int *lpcSubKeys,
        unsigned int *lpcbMaxSubKeyLen,
        unsigned int *lpcbMaxClassLen,
        unsigned int *lpcValues,
        unsigned int *lpcbMaxValueNameLen,
        unsigned int *lpcbMaxValueLen,
        unsigned int *lpcbSecurityDescriptor,
        struct _FILETIME *lpftLastWriteTime)
{
  return RegQueryInfoKeyW(
           a2,
           a3,
           a4,
           lpReserved,
           lpcSubKeys,
           lpcbMaxSubKeyLen,
           lpcbMaxClassLen,
           lpcValues,
           lpcbMaxValueNameLen,
           lpcbMaxValueLen,
           lpcbSecurityDescriptor,
           lpftLastWriteTime);
}

```

## disassembly

```asm
0x1800087f0  push    rbx
0x1800087f2  sub     rsp, 60h
0x1800087f6  mov     rax, [rsp+68h+arg_60]
0x1800087fe  mov     r10, r9
0x180008801  mov     r9, [rsp+68h+lpReserved]; lpReserved
0x180008809  mov     r11, r8
0x18000880c  mov     [rsp+68h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180008811  mov     rcx, rdx; hKey
0x180008814  mov     rax, [rsp+68h+arg_58]
0x18000881c  mov     r8, r10; lpcchClass
0x18000881f  mov     [rsp+68h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x180008824  mov     rdx, r11; lpClass
0x180008827  mov     rax, [rsp+68h+arg_50]
0x18000882f  mov     [rsp+68h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180008834  mov     rax, [rsp+68h+arg_48]
0x18000883c  mov     [rsp+68h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180008841  mov     rax, [rsp+68h+arg_40]
0x180008849  mov     [rsp+68h+lpcValues], rax; lpcValues
0x18000884e  mov     rax, [rsp+68h+arg_38]
0x180008856  mov     [rsp+68h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x18000885b  mov     rax, [rsp+68h+arg_30]
0x180008863  mov     [rsp+68h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180008868  mov     rax, [rsp+68h+arg_28]
0x180008870  mov     [rsp+68h+lpcSubKeys], rax; lpcSubKeys
0x180008875  call    cs:__imp_RegQueryInfoKeyW
0x18000887b  add     rsp, 60h
0x18000887f  pop     rbx
0x180008880  retn
```
