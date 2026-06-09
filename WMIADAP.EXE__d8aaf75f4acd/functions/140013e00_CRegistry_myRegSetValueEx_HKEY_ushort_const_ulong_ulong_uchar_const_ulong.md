# CRegistry::myRegSetValueEx(HKEY__ *,ushort const *,ulong,ulong,uchar const *,ulong)

- ea: `0x140013e00`
- end: `0x140013e38`
- name: `?myRegSetValueEx@CRegistry@@AEAAJPEAUHKEY__@@PEBGKKPEBEK@Z`
- size: `56`
- prototype: `LSTATUS __fastcall(CRegistry *this, HKEY, const unsigned __int16 *, DWORD, DWORD dwType, BYTE *lpData, DWORD cbData)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013e2c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013e2c`

## pseudocode

```c
LSTATUS __fastcall CRegistry::myRegSetValueEx(
        CRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3,
        DWORD a4,
        DWORD dwType,
        BYTE *lpData,
        DWORD cbData)
{
  return RegSetValueExW(a2, a3, a4, dwType, lpData, cbData);
}

```

## disassembly

```asm
0x140013e00  push    rbx
0x140013e02  sub     rsp, 30h
0x140013e06  mov     eax, [rsp+38h+arg_30]
0x140013e0a  mov     r10d, r9d
0x140013e0d  mov     r9d, [rsp+38h+dwType]; dwType
0x140013e12  mov     r11, r8
0x140013e15  mov     [rsp+38h+cbData], eax; cbData
0x140013e19  mov     rcx, rdx; hKey
0x140013e1c  mov     rax, [rsp+38h+arg_28]
0x140013e21  mov     r8d, r10d; Reserved
0x140013e24  mov     rdx, r11; lpValueName
0x140013e27  mov     [rsp+38h+lpData], rax; lpData
0x140013e2c  call    cs:__imp_RegSetValueExW
0x140013e32  add     rsp, 30h
0x140013e36  pop     rbx
0x140013e37  retn
```
