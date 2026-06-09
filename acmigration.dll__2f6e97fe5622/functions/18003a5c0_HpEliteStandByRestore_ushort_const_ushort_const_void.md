# HpEliteStandByRestore(ushort const *,ushort const *,void *)

- ea: `0x18003a5c0`
- end: `0x18003a64e`
- name: `?HpEliteStandByRestore@@YAJPEBG0PEAX@Z`
- size: `142`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18003a5c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18003a633`
- `ADVAPI32!RegCloseKey` at `0x18003a633`
- `ADVAPI32!RegSetValueExW` at `0x18003a626`
- `ADVAPI32!RegSetValueExW` at `0x18003a626`
- `ADVAPI32!RegOpenKeyExW` at `0x18003a5f8`
- `ADVAPI32!RegOpenKeyExW` at `0x18003a5f8`

## pseudocode

```c
__int64 __fastcall HpEliteStandByRestore(const unsigned __int16 *a1, const unsigned __int16 *a2, void *a3)
{
  LSTATUS v3; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  int Data; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  Data = 1;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Power", 0, 0x20006u, &hKey);
  if ( !v3 )
  {
    v3 = RegSetValueExW(hKey, L"EnforceDisconnectedStandby", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
  }
  if ( v3 > 0 )
    return (unsigned __int16)v3 | 0x80070000;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003a5c0  push    rbx
0x18003a5c2  sub     rsp, 40h
0x18003a5c6  lea     rax, [rsp+48h+hKey]
0x18003a5cb  mov     [rsp+48h+hKey], 0
0x18003a5d4  mov     r9d, 20006h; samDesired
0x18003a5da  mov     [rsp+48h+phkResult], rax; phkResult
0x18003a5df  xor     r8d, r8d; ulOptions
0x18003a5e2  mov     [rsp+48h+Data], 1
0x18003a5ea  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Pow"...
0x18003a5f1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003a5f8  call    cs:__imp_RegOpenKeyExW
0x18003a5fe  mov     ebx, eax
0x18003a600  test    eax, eax
0x18003a602  jnz     short loc_18003A639
0x18003a604  mov     rcx, [rsp+48h+hKey]; hKey
0x18003a609  lea     r9d, [rax+4]; dwType
0x18003a60d  lea     rax, [rsp+48h+Data]
0x18003a612  mov     [rsp+48h+cbData], r9d; cbData
0x18003a617  xor     r8d, r8d; Reserved
0x18003a61a  mov     [rsp+48h+phkResult], rax; lpData
0x18003a61f  lea     rdx, aEnforcedisconn; "EnforceDisconnectedStandby"
0x18003a626  call    cs:__imp_RegSetValueExW
0x18003a62c  mov     rcx, [rsp+48h+hKey]; hKey
0x18003a631  mov     ebx, eax
0x18003a633  call    cs:__imp_RegCloseKey
0x18003a639  test    ebx, ebx
0x18003a63b  jle     short loc_18003A646
0x18003a63d  movzx   ebx, bx
0x18003a640  or      ebx, 80070000h
0x18003a646  mov     eax, ebx
0x18003a648  add     rsp, 40h
0x18003a64c  pop     rbx
0x18003a64d  retn
```
