# RegistryRegRow::Deactivate(int)

- ea: `0x18003a940`
- end: `0x18003aa22`
- name: `?Deactivate@RegistryRegRow@@UEAAJH@Z`
- size: `226`
- prototype: `__int64 __fastcall(RegistryRegRow *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18003a940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a9aa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a9aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a9e9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a9e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003aa05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003aa05`

## pseudocode

```c
__int64 __fastcall RegistryRegRow::Deactivate(RegistryRegRow *this, int a2)
{
  const WCHAR *v3; // rdx
  HKEY v4; // rcx
  LSTATUS v5; // eax
  signed int v6; // ebx
  LSTATUS v7; // eax
  int Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  if ( !a2 || *((_BYTE *)this + 48) )
    goto LABEL_10;
  v3 = (const WCHAR *)*((_QWORD *)this + 15);
  v4 = (HKEY)*((_QWORD *)this + 16);
  Data = 0;
  hKey = 0;
  v5 = RegCreateKeyExW(v4, v3, 0, 0, 0, 2u, 0, &hKey, 0);
  v6 = v5;
  if ( !v5 )
    goto LABEL_14;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_14:
    v7 = RegSetValueExW(hKey, L"Active", 0, 4u, (const BYTE *)&Data, 4u);
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    RegCloseKey(hKey);
    if ( v6 >= 0 )
    {
LABEL_10:
      *((_BYTE *)this + 49) = 0;
      return 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003a940  mov     r11, rsp
0x18003a943  mov     [r11+8], rbx
0x18003a947  push    rdi
0x18003a948  sub     rsp, 50h
0x18003a94c  mov     rdi, rcx
0x18003a94f  test    edx, edx
0x18003a951  jz      loc_18003AA0F
0x18003a957  cmp     byte ptr [rcx+30h], 0
0x18003a95b  jnz     loc_18003AA0F
0x18003a961  mov     rdx, [rcx+78h]; lpSubKey
0x18003a965  lea     rax, [r11+18h]
0x18003a969  mov     rcx, [rcx+80h]; hKey
0x18003a970  xor     r9d, r9d; lpClass
0x18003a973  mov     qword ptr [r11-18h], 0
0x18003a97b  xor     r8d, r8d; Reserved
0x18003a97e  mov     [r11-20h], rax
0x18003a982  mov     qword ptr [r11-28h], 0
0x18003a98a  mov     [rsp+58h+samDesired], 2; samDesired
0x18003a992  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18003a99a  mov     [rsp+58h+Data], 0
0x18003a9a2  mov     qword ptr [r11+18h], 0
0x18003a9aa  call    cs:__imp_RegCreateKeyExW
0x18003a9b0  mov     ebx, eax
0x18003a9b2  test    eax, eax
0x18003a9b4  jz      short loc_18003A9C5
0x18003a9b6  jle     short loc_18003A9C1
0x18003a9b8  movzx   ebx, ax
0x18003a9bb  or      ebx, 80070000h
0x18003a9c1  test    ebx, ebx
0x18003a9c3  js      short loc_18003AA15
0x18003a9c5  mov     rcx, [rsp+58h+hKey]; hKey
0x18003a9ca  lea     rax, [rsp+58h+Data]
0x18003a9cf  mov     r9d, 4; dwType
0x18003a9d5  lea     rdx, Value; "Active"
0x18003a9dc  mov     [rsp+58h+samDesired], r9d; cbData
0x18003a9e1  xor     r8d, r8d; Reserved
0x18003a9e4  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18003a9e9  call    cs:__imp_RegSetValueExW
0x18003a9ef  mov     ebx, eax
0x18003a9f1  test    eax, eax
0x18003a9f3  jz      short loc_18003AA00
0x18003a9f5  jle     short loc_18003AA00
0x18003a9f7  movzx   ebx, ax
0x18003a9fa  or      ebx, 80070000h
0x18003aa00  mov     rcx, [rsp+58h+hKey]; hKey
0x18003aa05  call    cs:__imp_RegCloseKey
0x18003aa0b  test    ebx, ebx
0x18003aa0d  js      short loc_18003AA15
0x18003aa0f  mov     byte ptr [rdi+31h], 0
0x18003aa13  xor     ebx, ebx
0x18003aa15  mov     eax, ebx
0x18003aa17  mov     rbx, [rsp+58h+arg_0]
0x18003aa1c  add     rsp, 50h
0x18003aa20  pop     rdi
0x18003aa21  retn
```
