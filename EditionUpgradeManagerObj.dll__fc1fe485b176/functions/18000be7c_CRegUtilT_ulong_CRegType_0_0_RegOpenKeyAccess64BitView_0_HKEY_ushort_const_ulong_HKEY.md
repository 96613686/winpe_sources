# CRegUtilT<ulong,CRegType,0,0>::RegOpenKeyAccess64BitView<0>(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x18000be7c`
- end: `0x18000bef9`
- name: `??$RegOpenKeyAccess64BitView@$0A@@?$CRegUtilT@KUCRegType@@$0A@$0A@@@CAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z`
- size: `125`
- prototype: `__int64 __fastcall(HKEY, __int64, REGSAM, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bf00`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000be7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000beeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000beeb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bea8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bea8`

## pseudocode

```c
__int64 __fastcall CRegUtilT<unsigned long,CRegType,0,0>::RegOpenKeyAccess64BitView<0>(
        HKEY a1,
        __int64 a2,
        REGSAM a3,
        HKEY *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v5 = RegOpenKeyExW(a1, L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsAnytimeUpgrade", 0, a3, &hKey);
  if ( v5 )
  {
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    v6 = v5;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v5);
  }
  else
  {
    *a4 = hKey;
    v6 = 0;
    hKey = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18000be7c  mov     r11, rsp
0x18000be7f  mov     [r11+10h], rdx
0x18000be83  push    rbx
0x18000be84  sub     rsp, 30h
0x18000be88  mov     rbx, r9
0x18000be8b  mov     qword ptr [r11+10h], 0
0x18000be93  mov     r9d, r8d; samDesired
0x18000be96  lea     rax, [r11+10h]
0x18000be9a  xor     r8d, r8d; ulOptions
0x18000be9d  mov     [r11-18h], rax
0x18000bea1  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000bea8  call    cs:__imp_RegOpenKeyExW
0x18000beae  test    eax, eax
0x18000beb0  jz      short loc_18000BEC7
0x18000beb2  jle     short loc_18000BEBC
0x18000beb4  movzx   eax, ax
0x18000beb7  or      eax, 80070000h
0x18000bebc  mov     ecx, eax
0x18000bebe  mov     ebx, eax
0x18000bec0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000bec5  jmp     short loc_18000BEDA
0x18000bec7  mov     rax, [rsp+38h+hKey]
0x18000becc  mov     [rbx], rax
0x18000becf  xor     ebx, ebx
0x18000bed1  mov     [rsp+38h+hKey], 0
0x18000beda  mov     ecx, ebx
0x18000bedc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000bee1  mov     rcx, [rsp+38h+hKey]; hKey
0x18000bee6  test    rcx, rcx
0x18000bee9  jz      short loc_18000BEF1
0x18000beeb  call    cs:__imp_RegCloseKey
0x18000bef1  mov     eax, ebx
0x18000bef3  add     rsp, 30h
0x18000bef7  pop     rbx
0x18000bef8  retn
```
