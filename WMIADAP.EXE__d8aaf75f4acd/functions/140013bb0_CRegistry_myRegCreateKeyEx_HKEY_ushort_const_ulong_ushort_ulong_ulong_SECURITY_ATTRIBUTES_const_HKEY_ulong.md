# CRegistry::myRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)

- ea: `0x140013bb0`
- end: `0x140013c16`
- name: `?myRegCreateKeyEx@CRegistry@@AEAAJPEAUHKEY__@@PEBGKPEAGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z`
- size: `102`
- prototype: `LSTATUS __fastcall(CRegistry *this, HKEY, const unsigned __int16 *, DWORD, unsigned __int16 *lpClass, DWORD dwOptions, REGSAM samDesired, struct _SECURITY_ATTRIBUTES *const lpSecurityAttributes, HKEY *phkResult, unsigned int *lpdwDisposition)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140013c0a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140013c0a`

## pseudocode

```c
LSTATUS __fastcall CRegistry::myRegCreateKeyEx(
        CRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3,
        DWORD a4,
        unsigned __int16 *lpClass,
        DWORD dwOptions,
        REGSAM samDesired,
        struct _SECURITY_ATTRIBUTES *const lpSecurityAttributes,
        HKEY *phkResult,
        unsigned int *lpdwDisposition)
{
  return RegCreateKeyExW(a2, a3, a4, lpClass, dwOptions, samDesired, lpSecurityAttributes, phkResult, lpdwDisposition);
}

```

## disassembly

```asm
0x140013bb0  push    rbx
0x140013bb2  sub     rsp, 50h
0x140013bb6  mov     rax, [rsp+58h+arg_48]
0x140013bbe  mov     r10d, r9d
0x140013bc1  mov     r9, [rsp+58h+lpClass]; lpClass
0x140013bc9  mov     r11, r8
0x140013bcc  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x140013bd1  mov     rcx, rdx; hKey
0x140013bd4  mov     rax, [rsp+58h+arg_40]
0x140013bdc  mov     r8d, r10d; Reserved
0x140013bdf  mov     [rsp+58h+phkResult], rax; phkResult
0x140013be4  mov     rdx, r11; lpSubKey
0x140013be7  mov     rax, [rsp+58h+arg_38]
0x140013bef  mov     [rsp+58h+lpSecurityAttributes], rax; lpSecurityAttributes
0x140013bf4  mov     eax, [rsp+58h+arg_30]
0x140013bfb  mov     [rsp+58h+samDesired], eax; samDesired
0x140013bff  mov     eax, [rsp+58h+arg_28]
0x140013c06  mov     [rsp+58h+dwOptions], eax; dwOptions
0x140013c0a  call    cs:__imp_RegCreateKeyExW
0x140013c10  add     rsp, 50h
0x140013c14  pop     rbx
0x140013c15  retn
```
