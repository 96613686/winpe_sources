# SetWinsatRegKeyULONGLONG

- ea: `0x140011fd0`
- end: `0x1400120a4`
- name: `SetWinsatRegKeyULONGLONG`
- size: `212`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000fcb8`
- `0x140011920`
- `0x140012710`

## callees

- `0x140011fd0`
- `0x14003ec14`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14001207b`
- `ADVAPI32!RegSetValueExW` at `0x14001207b`
- `ADVAPI32!RegCreateKeyExW` at `0x14001202b`
- `ADVAPI32!RegCreateKeyExW` at `0x14001202b`
- `ADVAPI32!RegFlushKey` at `0x140012088`
- `ADVAPI32!RegFlushKey` at `0x140012088`
- `ADVAPI32!RegCloseKey` at `0x140012093`
- `ADVAPI32!RegCloseKey` at `0x140012093`

## string_xrefs

- `0x14001203c`: `ERROR: could not create %ws reg key. error = %u`

## pseudocode

```c
bool __fastcall SetWinsatRegKeyULONGLONG(LPCWSTR lpValueName, __int64 a2)
{
  LSTATUS v3; // eax
  LSTATUS v5; // ebx
  DWORD dwOptions[2]; // [rsp+20h] [rbp-38h]
  __int64 Data; // [rsp+68h] [rbp+10h] BYREF
  DWORD v8; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  Data = a2;
  hKey = 0;
  v8 = 0;
  v3 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSAT",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         &v8);
  if ( v3 )
  {
    dwOptions[0] = v3;
    Log_Text_F(
      "base\\winsat\\exe\\main.cpp",
      2558,
      "ERROR: could not create %ws reg key. error = %u",
      lpValueName,
      *(_QWORD *)dwOptions);
    return 0;
  }
  else
  {
    v5 = RegSetValueExW(hKey, lpValueName, 0, 0xBu, (const BYTE *)&Data, 8u);
    RegFlushKey(hKey);
    RegCloseKey(hKey);
    return v5 == 0;
  }
}

```

## disassembly

```asm
0x140011fd0  mov     r11, rsp
0x140011fd3  mov     [r11+10h], rdx
0x140011fd7  push    rbx
0x140011fd8  sub     rsp, 50h
0x140011fdc  lea     rax, [r11+18h]
0x140011fe0  mov     qword ptr [r11+20h], 0
0x140011fe8  mov     [r11-18h], rax
0x140011fec  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140011ff3  lea     rax, [r11+20h]
0x140011ff7  mov     [rsp+58h+arg_10], 0
0x140011fff  mov     [r11-20h], rax
0x140012003  mov     rbx, rcx
0x140012006  mov     qword ptr [r11-28h], 0
0x14001200e  xor     r9d, r9d; lpClass
0x140012011  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x140012019  xor     r8d, r8d; Reserved
0x14001201c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140012023  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14001202b  call    cs:__imp_RegCreateKeyExW
0x140012031  test    eax, eax
0x140012033  jz      short loc_140012058
0x140012035  mov     r9, rbx
0x140012038  mov     [rsp+58h+dwOptions], eax
0x14001203c  lea     r8, aErrorCouldNotC; "ERROR: could not create %ws reg key. er"...
0x140012043  mov     edx, 9FEh
0x140012048  lea     rcx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x14001204f  call    Log_Text_F
0x140012054  xor     al, al
0x140012056  jmp     short loc_14001209E
0x140012058  mov     rcx, [rsp+58h+hKey]; hKey
0x14001205d  lea     rax, [rsp+58h+Data]
0x140012062  mov     [rsp+58h+samDesired], 8; cbData
0x14001206a  mov     r9d, 0Bh; dwType
0x140012070  xor     r8d, r8d; Reserved
0x140012073  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x140012078  mov     rdx, rbx; lpValueName
0x14001207b  call    cs:__imp_RegSetValueExW
0x140012081  mov     rcx, [rsp+58h+hKey]; hKey
0x140012086  mov     ebx, eax
0x140012088  call    cs:__imp_RegFlushKey
0x14001208e  mov     rcx, [rsp+58h+hKey]; hKey
0x140012093  call    cs:__imp_RegCloseKey
0x140012099  test    ebx, ebx
0x14001209b  setz    al
0x14001209e  add     rsp, 50h
0x1400120a2  pop     rbx
0x1400120a3  retn
```
