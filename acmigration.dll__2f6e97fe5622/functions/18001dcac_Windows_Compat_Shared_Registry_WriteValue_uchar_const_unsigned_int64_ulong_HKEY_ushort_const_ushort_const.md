# Windows::Compat::Shared::Registry::WriteValue(uchar const *,unsigned __int64,ulong,HKEY__ *,ushort const *,ushort const *)

- ea: `0x18001dcac`
- end: `0x18001dd7c`
- name: `?WriteValue@Registry@Shared@Compat@Windows@@SAJPEBE_KKPEAUHKEY__@@PEBG3@Z`
- size: `208`
- prototype: `__int64 __usercall@<rax>(BYTE *lpData@<rcx>, DWORD cbData@<edx>, DWORD dwType@<r8d>, HKEY@<r9>, LPCWSTR lpSubKey, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cad0`

## callees

- `0x18001dcac`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001dd6b`
- `ADVAPI32!RegCloseKey` at `0x18001dd6b`
- `ADVAPI32!RegSetValueExW` at `0x18001dd52`
- `ADVAPI32!RegSetValueExW` at `0x18001dd52`
- `ADVAPI32!RegCreateKeyExW` at `0x18001dd09`
- `ADVAPI32!RegCreateKeyExW` at `0x18001dd09`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Shared::Registry::WriteValue(
        BYTE *lpData,
        unsigned __int64 cbData,
        DWORD dwType,
        HKEY a4,
        LPCWSTR lpSubKey,
        const unsigned __int16 *lpValueName)
{
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  bool v11; // cc
  HKEY hKey; // [rsp+98h] [rbp+20h] BYREF

  hKey = 0;
  v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20106u, 0, &hKey, 0);
  v10 = v9;
  v11 = v9 <= 0;
  if ( v9 )
    goto LABEL_2;
  if ( cbData > 0xFFFFFFFF )
  {
    v10 = -2147024809;
    goto LABEL_7;
  }
  v9 = RegSetValueExW(hKey, lpValueName, 0, dwType, lpData, cbData);
  v10 = v9;
  v11 = v9 <= 0;
  if ( v9 )
  {
LABEL_2:
    if ( !v11 )
      v10 = (unsigned __int16)v9 | 0x80070000;
  }
LABEL_7:
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x18001dcac  mov     r11, rsp
0x18001dcaf  mov     [r11+20h], r9
0x18001dcb3  push    rbx
0x18001dcb4  push    rbp
0x18001dcb5  push    rsi
0x18001dcb6  push    rdi
0x18001dcb7  sub     rsp, 58h
0x18001dcbb  mov     qword ptr [r11-38h], 0
0x18001dcc3  lea     rax, [r11+20h]
0x18001dcc7  mov     [r11-40h], rax
0x18001dccb  mov     esi, r8d
0x18001dcce  mov     qword ptr [r11-48h], 0
0x18001dcd6  mov     rdi, rdx
0x18001dcd9  mov     rdx, [rsp+78h+lpSubKey]; lpSubKey
0x18001dce1  mov     rbp, rcx
0x18001dce4  mov     [rsp+78h+samDesired], 20106h; samDesired
0x18001dcec  xor     r9d, r9d; lpClass
0x18001dcef  xor     r8d, r8d; Reserved
0x18001dcf2  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18001dcfa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001dd01  mov     qword ptr [r11+20h], 0
0x18001dd09  call    cs:__imp_RegCreateKeyExW
0x18001dd0f  mov     ebx, eax
0x18001dd11  test    eax, eax
0x18001dd13  jz      short loc_18001DD22
0x18001dd15  jle     short loc_18001DD5E
0x18001dd17  movzx   ebx, ax
0x18001dd1a  or      ebx, 80070000h
0x18001dd20  jmp     short loc_18001DD5E
0x18001dd22  mov     eax, 0FFFFFFFFh
0x18001dd27  cmp     rdi, rax
0x18001dd2a  jbe     short loc_18001DD33
0x18001dd2c  mov     ebx, 80070057h
0x18001dd31  jmp     short loc_18001DD5E
0x18001dd33  mov     rdx, [rsp+78h+lpValueName]; lpValueName
0x18001dd3b  mov     r9d, esi; dwType
0x18001dd3e  mov     rcx, [rsp+78h+hKey]; hKey
0x18001dd46  xor     r8d, r8d; Reserved
0x18001dd49  mov     [rsp+78h+samDesired], edi; cbData
0x18001dd4d  mov     qword ptr [rsp+78h+dwOptions], rbp; lpData
0x18001dd52  call    cs:__imp_RegSetValueExW
0x18001dd58  mov     ebx, eax
0x18001dd5a  test    eax, eax
0x18001dd5c  jnz     short loc_18001DD15
0x18001dd5e  mov     rcx, [rsp+78h+hKey]; hKey
0x18001dd66  test    rcx, rcx
0x18001dd69  jz      short loc_18001DD71
0x18001dd6b  call    cs:__imp_RegCloseKey
0x18001dd71  mov     eax, ebx
0x18001dd73  add     rsp, 58h
0x18001dd77  pop     rdi
0x18001dd78  pop     rsi
0x18001dd79  pop     rbp
0x18001dd7a  pop     rbx
0x18001dd7b  retn
```
