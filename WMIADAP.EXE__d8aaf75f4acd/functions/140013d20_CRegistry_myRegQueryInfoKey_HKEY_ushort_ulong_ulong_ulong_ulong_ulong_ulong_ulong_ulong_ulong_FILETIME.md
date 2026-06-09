# CRegistry::myRegQueryInfoKey(HKEY__ *,ushort *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,_FILETIME *)

- ea: `0x140013d20`
- end: `0x140013db1`
- name: `?myRegQueryInfoKey@CRegistry@@AEAAJPEAUHKEY__@@PEAGPEAK22222222PEAU_FILETIME@@@Z`
- size: `145`
- prototype: `LSTATUS __fastcall(CRegistry *this, HKEY, unsigned __int16 *, unsigned int *, unsigned int *lpReserved, unsigned int *lpcSubKeys, unsigned int *lpcbMaxSubKeyLen, unsigned int *lpcbMaxClassLen, unsigned int *lpcValues, unsigned int *lpcbMaxValueNameLen, unsigned int *lpcbMaxValueLen, unsigned int *lpcbSecurityDescriptor, struct _FILETIME *lpftLastWriteTime)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140013da5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140013da5`

## pseudocode

```c
LSTATUS __fastcall CRegistry::myRegQueryInfoKey(
        CRegistry *this,
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
0x140013d20  push    rbx
0x140013d22  sub     rsp, 60h
0x140013d26  mov     rax, [rsp+68h+arg_60]
0x140013d2e  mov     r10, r9
0x140013d31  mov     r9, [rsp+68h+lpReserved]; lpReserved
0x140013d39  mov     r11, r8
0x140013d3c  mov     [rsp+68h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140013d41  mov     rcx, rdx; hKey
0x140013d44  mov     rax, [rsp+68h+arg_58]
0x140013d4c  mov     r8, r10; lpcchClass
0x140013d4f  mov     [rsp+68h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x140013d54  mov     rdx, r11; lpClass
0x140013d57  mov     rax, [rsp+68h+arg_50]
0x140013d5f  mov     [rsp+68h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x140013d64  mov     rax, [rsp+68h+arg_48]
0x140013d6c  mov     [rsp+68h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x140013d71  mov     rax, [rsp+68h+arg_40]
0x140013d79  mov     [rsp+68h+lpcValues], rax; lpcValues
0x140013d7e  mov     rax, [rsp+68h+arg_38]
0x140013d86  mov     [rsp+68h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x140013d8b  mov     rax, [rsp+68h+arg_30]
0x140013d93  mov     [rsp+68h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140013d98  mov     rax, [rsp+68h+arg_28]
0x140013da0  mov     [rsp+68h+lpcSubKeys], rax; lpcSubKeys
0x140013da5  call    cs:__imp_RegQueryInfoKeyW
0x140013dab  add     rsp, 60h
0x140013daf  pop     rbx
0x140013db0  retn
```
