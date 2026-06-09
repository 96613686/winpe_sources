# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x140029ed8`
- end: `0x140029f90`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `184`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002526c`
- `0x1400302fc`
- `0x14003b004`

## callees

- `0x140029ed8`

## import_xrefs

- `KERNEL32!RegCreateKeyExW` at `0x140029f28`
- `KERNEL32!RegCreateKeyExW` at `0x140029f28`
- `KERNEL32!RegSetValueExW` at `0x140029f61`
- `KERNEL32!RegSetValueExW` at `0x140029f61`
- `KERNEL32!RegCloseKey` at `0x140029f73`
- `KERNEL32!RegCloseKey` at `0x140029f73`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        BYTE *lpData,
        DWORD cbData)
{
  HKEY v8; // rbx
  unsigned int v9; // edi
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  hKey = 0;
  v8 = a1;
  if ( a2 && *a2 )
  {
    v9 = RegCreateKeyExW(a1, a2, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v9 )
      return v9;
    a1 = hKey;
  }
  else
  {
    hKey = a1;
  }
  v9 = RegSetValueExW(a1, a3, 0, a4, lpData, cbData);
  if ( hKey != v8 )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x140029ed8  mov     r11, rsp
0x140029edb  mov     [r11+8], rbx
0x140029edf  mov     [r11+18h], rbp
0x140029ee3  push    rsi
0x140029ee4  push    rdi
0x140029ee5  push    r14
0x140029ee7  sub     rsp, 50h
0x140029eeb  xor     r14d, r14d
0x140029eee  mov     esi, r9d
0x140029ef1  mov     [r11+10h], r14
0x140029ef5  mov     rbp, r8
0x140029ef8  mov     rbx, rcx
0x140029efb  test    rdx, rdx
0x140029efe  jz      short loc_140029F3B
0x140029f00  cmp     [rdx], r14w
0x140029f04  jz      short loc_140029F3B
0x140029f06  mov     [r11-28h], r14
0x140029f0a  lea     rax, [r11+10h]
0x140029f0e  mov     [r11-30h], rax
0x140029f12  xor     r9d, r9d; lpClass
0x140029f15  mov     [r11-38h], r14
0x140029f19  xor     r8d, r8d; Reserved
0x140029f1c  mov     [rsp+68h+samDesired], 2; samDesired
0x140029f24  mov     [r11-48h], r14d
0x140029f28  call    cs:__imp_RegCreateKeyExW
0x140029f2e  mov     edi, eax
0x140029f30  test    eax, eax
0x140029f32  jnz     short loc_140029F79
0x140029f34  mov     rcx, [rsp+68h+hKey]; hKey
0x140029f39  jmp     short loc_140029F40
0x140029f3b  mov     [rsp+68h+hKey], rbx
0x140029f40  mov     eax, [rsp+68h+cbData]
0x140029f47  mov     r9d, esi; dwType
0x140029f4a  mov     [rsp+68h+samDesired], eax; cbData
0x140029f4e  xor     r8d, r8d; Reserved
0x140029f51  mov     rax, [rsp+68h+arg_20]
0x140029f59  mov     rdx, rbp; lpValueName
0x140029f5c  mov     [rsp+68h+lpData], rax; lpData
0x140029f61  call    cs:__imp_RegSetValueExW
0x140029f67  mov     rcx, [rsp+68h+hKey]; hKey
0x140029f6c  mov     edi, eax
0x140029f6e  cmp     rcx, rbx
0x140029f71  jz      short loc_140029F79
0x140029f73  call    cs:__imp_RegCloseKey
0x140029f79  lea     r11, [rsp+68h+var_18]
0x140029f7e  mov     eax, edi
0x140029f80  mov     rbx, [r11+20h]
0x140029f84  mov     rbp, [r11+30h]
0x140029f88  mov     rsp, r11
0x140029f8b  pop     r14
0x140029f8d  pop     rdi
0x140029f8e  pop     rsi
0x140029f8f  retn
```
