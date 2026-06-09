# CRegUtilT<ushort *,CRegType,0,0>::SetValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x18000c45c`
- end: `0x18000c554`
- name: `?SetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG11K@Z`
- size: `248`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *, const BYTE *, DWORD cbData)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800156d0`
- `0x180015864`
- `0x1800161b0`
- `0x180016320`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000c45c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c4d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c543`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c4d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c543`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c517`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c517`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c491`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c491`

## pseudocode

```c
__int64 __fastcall CRegUtilT<unsigned short *,CRegType,0,0>::SetValue(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        const BYTE *a4,
        DWORD cbData)
{
  int v7; // eax
  HKEY v8; // rdi
  signed int v9; // ebx
  LSTATUS v10; // eax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  v7 = RegOpenKeyExW(HKEY_CLASSES_ROOT, a2, 0, 2u, &hKey);
  if ( v7 )
  {
    v8 = 0;
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    v9 = v7;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
  }
  else
  {
    v8 = hKey;
    v9 = 0;
    hKey = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v9 < 0 )
    goto LABEL_9;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v10 = RegSetValueExW(v8, a3, 0, 1u, a4, cbData);
  v9 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
LABEL_9:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
    goto LABEL_14;
  }
  v9 = 0;
LABEL_14:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( v8 )
    RegCloseKey(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000c45c  mov     r11, rsp
0x18000c45f  mov     [r11+8], rcx
0x18000c463  push    rbx
0x18000c464  push    rbp
0x18000c465  push    rsi
0x18000c466  push    rdi
0x18000c467  sub     rsp, 38h
0x18000c46b  mov     rsi, r9
0x18000c46e  mov     qword ptr [r11+8], 0
0x18000c476  mov     rbp, r8
0x18000c479  lea     rax, [r11+8]
0x18000c47d  mov     r9d, 2; samDesired
0x18000c483  mov     [r11-38h], rax
0x18000c487  xor     r8d, r8d; ulOptions
0x18000c48a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000c491  call    cs:__imp_RegOpenKeyExW
0x18000c497  test    eax, eax
0x18000c499  jz      short loc_18000C4B4
0x18000c49b  xor     edi, edi
0x18000c49d  test    eax, eax
0x18000c49f  jle     short loc_18000C4A9
0x18000c4a1  movzx   eax, ax
0x18000c4a4  or      eax, 80070000h
0x18000c4a9  mov     ecx, eax
0x18000c4ab  mov     ebx, eax
0x18000c4ad  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c4b2  jmp     short loc_18000C4C4
0x18000c4b4  mov     rdi, [rsp+58h+hKey]
0x18000c4b9  xor     ebx, ebx
0x18000c4bb  mov     [rsp+58h+hKey], 0
0x18000c4c4  mov     ecx, ebx
0x18000c4c6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c4cb  mov     rcx, [rsp+58h+hKey]; hKey
0x18000c4d0  test    rcx, rcx
0x18000c4d3  jz      short loc_18000C4E4
0x18000c4d5  call    cs:__imp_RegCloseKey
0x18000c4db  mov     [rsp+58h+hKey], 0
0x18000c4e4  test    ebx, ebx
0x18000c4e6  jns     short loc_18000C4F1
0x18000c4e8  mov     ecx, ebx
0x18000c4ea  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c4ef  jmp     short loc_18000C534
0x18000c4f1  xor     ecx, ecx
0x18000c4f3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c4f8  mov     eax, [rsp+58h+arg_20]
0x18000c4ff  mov     r9d, 1; dwType
0x18000c505  mov     [rsp+58h+cbData], eax; cbData
0x18000c509  xor     r8d, r8d; Reserved
0x18000c50c  mov     rdx, rbp; lpValueName
0x18000c50f  mov     [rsp+58h+lpData], rsi; lpData
0x18000c514  mov     rcx, rdi; hKey
0x18000c517  call    cs:__imp_RegSetValueExW
0x18000c51d  mov     ebx, eax
0x18000c51f  test    eax, eax
0x18000c521  jz      short loc_18000C532
0x18000c523  test    eax, eax
0x18000c525  jle     short loc_18000C4E8
0x18000c527  movzx   ebx, bx
0x18000c52a  or      ebx, 80070000h
0x18000c530  jmp     short loc_18000C4E8
0x18000c532  xor     ebx, ebx
0x18000c534  mov     ecx, ebx
0x18000c536  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c53b  test    rdi, rdi
0x18000c53e  jz      short loc_18000C549
0x18000c540  mov     rcx, rdi; hKey
0x18000c543  call    cs:__imp_RegCloseKey
0x18000c549  mov     eax, ebx
0x18000c54b  add     rsp, 38h
0x18000c54f  pop     rdi
0x18000c550  pop     rsi
0x18000c551  pop     rbp
0x18000c552  pop     rbx
0x18000c553  retn
```
