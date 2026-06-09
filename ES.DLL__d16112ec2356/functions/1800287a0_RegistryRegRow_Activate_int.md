# RegistryRegRow::Activate(int)

- ea: `0x1800287a0`
- end: `0x18002887a`
- name: `?Activate@RegistryRegRow@@UEAAJH@Z`
- size: `218`
- prototype: `__int64 __fastcall(RegistryRegRow *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800287a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028800`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028800`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002883f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002883f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002885b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002885b`

## pseudocode

```c
__int64 __fastcall RegistryRegRow::Activate(RegistryRegRow *this, int a2)
{
  const WCHAR *v3; // rdx
  HKEY v4; // rcx
  LSTATUS v5; // eax
  signed int v6; // ebx
  LSTATUS v7; // eax
  int Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  if ( !a2 )
    goto LABEL_9;
  v3 = (const WCHAR *)*((_QWORD *)this + 15);
  v4 = (HKEY)*((_QWORD *)this + 16);
  Data = 1;
  hKey = 0;
  v5 = RegCreateKeyExW(v4, v3, 0, 0, 0, 2u, 0, &hKey, 0);
  v6 = v5;
  if ( !v5 )
    goto LABEL_13;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_13:
    v7 = RegSetValueExW(hKey, L"Active", 0, 4u, (const BYTE *)&Data, 4u);
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    RegCloseKey(hKey);
    if ( v6 >= 0 )
    {
LABEL_9:
      *((_WORD *)this + 24) = 256;
      return 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800287a0  mov     r11, rsp
0x1800287a3  mov     [r11+8], rbx
0x1800287a7  push    rdi
0x1800287a8  sub     rsp, 50h
0x1800287ac  mov     rdi, rcx
0x1800287af  test    edx, edx
0x1800287b1  jz      loc_180028865
0x1800287b7  mov     rdx, [rcx+78h]; lpSubKey
0x1800287bb  lea     rax, [r11+18h]
0x1800287bf  mov     rcx, [rcx+80h]; hKey
0x1800287c6  xor     r9d, r9d; lpClass
0x1800287c9  mov     qword ptr [r11-18h], 0
0x1800287d1  xor     r8d, r8d; Reserved
0x1800287d4  mov     [r11-20h], rax
0x1800287d8  mov     qword ptr [r11-28h], 0
0x1800287e0  mov     [rsp+58h+samDesired], 2; samDesired
0x1800287e8  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800287f0  mov     [rsp+58h+Data], 1
0x1800287f8  mov     qword ptr [r11+18h], 0
0x180028800  call    cs:__imp_RegCreateKeyExW
0x180028806  mov     ebx, eax
0x180028808  test    eax, eax
0x18002880a  jz      short loc_18002881B
0x18002880c  jle     short loc_180028817
0x18002880e  movzx   ebx, ax
0x180028811  or      ebx, 80070000h
0x180028817  test    ebx, ebx
0x180028819  js      short loc_18002886D
0x18002881b  mov     rcx, [rsp+58h+hKey]; hKey
0x180028820  lea     rax, [rsp+58h+Data]
0x180028825  mov     r9d, 4; dwType
0x18002882b  lea     rdx, Value; "Active"
0x180028832  mov     [rsp+58h+samDesired], r9d; cbData
0x180028837  xor     r8d, r8d; Reserved
0x18002883a  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18002883f  call    cs:__imp_RegSetValueExW
0x180028845  mov     ebx, eax
0x180028847  test    eax, eax
0x180028849  jz      short loc_180028856
0x18002884b  jle     short loc_180028856
0x18002884d  movzx   ebx, ax
0x180028850  or      ebx, 80070000h
0x180028856  mov     rcx, [rsp+58h+hKey]; hKey
0x18002885b  call    cs:__imp_RegCloseKey
0x180028861  test    ebx, ebx
0x180028863  js      short loc_18002886D
0x180028865  mov     word ptr [rdi+30h], 100h
0x18002886b  xor     ebx, ebx
0x18002886d  mov     eax, ebx
0x18002886f  mov     rbx, [rsp+58h+arg_0]
0x180028874  add     rsp, 50h
0x180028878  pop     rdi
0x180028879  retn
```
