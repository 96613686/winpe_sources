# CRegUtilT<ulong,CRegType,0,0>::SetValue(HKEY__ *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x18002cdac`
- end: `0x18002ceb6`
- name: `?SetValue@?$CRegUtilT@KUCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG1KK@Z`
- size: `266`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18002bae0`

## callees

- `0x180027008`
- `0x1800293a4`
- `0x18002cdac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002cdeb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002cdeb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ce77`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ce77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ce2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cea3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ce2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cea3`

## string_xrefs

- `0x18002ce56`: `RemoveWindowsOld`

## pseudocode

```c
__int64 __fastcall CRegUtilT<unsigned long,CRegType,0,0>::SetValue(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        DWORD cbData)
{
  int v5; // eax
  HKEY v6; // rdi
  signed int v7; // ebx
  LSTATUS v8; // eax
  BYTE Data[24]; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  *(_DWORD *)Data = 0;
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 2u, &hKey);
  if ( v5 )
  {
    v6 = 0;
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    v7 = v5;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
  }
  else
  {
    v6 = hKey;
    v7 = 0;
    hKey = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v7 < 0 )
    goto LABEL_9;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v8 = RegSetValueExW(v6, L"RemoveWindowsOld", 0, 4u, Data, cbData);
  v7 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
LABEL_9:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_14;
  }
  v7 = 0;
LABEL_14:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v6 )
    RegCloseKey(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002cdac  mov     rax, rsp
0x18002cdaf  mov     [rax+8], rbx
0x18002cdb3  mov     [rax+18h], r8
0x18002cdb7  push    rdi
0x18002cdb8  sub     rsp, 40h
0x18002cdbc  mov     dword ptr [rax-18h], 0
0x18002cdc3  mov     r9d, 2; samDesired
0x18002cdc9  mov     qword ptr [rax+18h], 0
0x18002cdd1  lea     rax, [rax+18h]
0x18002cdd5  xor     r8d, r8d; ulOptions
0x18002cdd8  mov     [rsp+48h+phkResult], rax; phkResult
0x18002cddd  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x18002cde4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002cdeb  call    cs:__imp_RegOpenKeyExW
0x18002cdf1  test    eax, eax
0x18002cdf3  jz      short loc_18002CE0E
0x18002cdf5  xor     edi, edi
0x18002cdf7  test    eax, eax
0x18002cdf9  jle     short loc_18002CE03
0x18002cdfb  movzx   eax, ax
0x18002cdfe  or      eax, 80070000h
0x18002ce03  mov     ecx, eax
0x18002ce05  mov     ebx, eax
0x18002ce07  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002ce0c  jmp     short loc_18002CE1E
0x18002ce0e  mov     rdi, [rsp+48h+hKey]
0x18002ce13  xor     ebx, ebx
0x18002ce15  mov     [rsp+48h+hKey], 0
0x18002ce1e  mov     ecx, ebx
0x18002ce20  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002ce25  mov     rcx, [rsp+48h+hKey]; hKey
0x18002ce2a  test    rcx, rcx
0x18002ce2d  jz      short loc_18002CE3E
0x18002ce2f  call    cs:__imp_RegCloseKey
0x18002ce35  mov     [rsp+48h+hKey], 0
0x18002ce3e  test    ebx, ebx
0x18002ce40  jns     short loc_18002CE4B
0x18002ce42  mov     ecx, ebx
0x18002ce44  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002ce49  jmp     short loc_18002CE94
0x18002ce4b  xor     ecx, ecx
0x18002ce4d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002ce52  mov     eax, [rsp+48h+arg_20]
0x18002ce56  lea     rdx, aRemovewindowso; "RemoveWindowsOld"
0x18002ce5d  mov     [rsp+48h+cbData], eax; cbData
0x18002ce61  mov     r9d, 4; dwType
0x18002ce67  lea     rax, [rsp+48h+Data]
0x18002ce6c  xor     r8d, r8d; Reserved
0x18002ce6f  mov     rcx, rdi; hKey
0x18002ce72  mov     [rsp+48h+phkResult], rax; lpData
0x18002ce77  call    cs:__imp_RegSetValueExW
0x18002ce7d  mov     ebx, eax
0x18002ce7f  test    eax, eax
0x18002ce81  jz      short loc_18002CE92
0x18002ce83  test    eax, eax
0x18002ce85  jle     short loc_18002CE42
0x18002ce87  movzx   ebx, bx
0x18002ce8a  or      ebx, 80070000h
0x18002ce90  jmp     short loc_18002CE42
0x18002ce92  xor     ebx, ebx
0x18002ce94  mov     ecx, ebx
0x18002ce96  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002ce9b  test    rdi, rdi
0x18002ce9e  jz      short loc_18002CEA9
0x18002cea0  mov     rcx, rdi; hKey
0x18002cea3  call    cs:__imp_RegCloseKey
0x18002cea9  mov     eax, ebx
0x18002ceab  mov     rbx, [rsp+48h+arg_0]
0x18002ceb0  add     rsp, 40h
0x18002ceb4  pop     rdi
0x18002ceb5  retn
```
