# Throttler::DeleteAllOccursForThrottleId(HKEY__ *)

- ea: `0x180006370`
- end: `0x180006528`
- name: `?DeleteAllOccursForThrottleId@Throttler@@AEAAXPEAUHKEY__@@@Z`
- size: `440`
- prototype: `void(Throttler *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005ee4`

## callees

- `0x180002590`
- `0x180006370`
- `0x180007040`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x18000641d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000641d`
- `ADVAPI32!RegEnumValueW` at `0x1800064a0`
- `ADVAPI32!RegEnumValueW` at `0x1800064a0`
- `ADVAPI32!RegDeleteValueW` at `0x1800064e1`
- `ADVAPI32!RegDeleteValueW` at `0x1800064e1`

## string_xrefs

- `0x1800064f9`: `THROTTLE CONFIGURATION ERROR - unexpected registry value  %s:%d\n`
- `0x180006431`: `Throttler::DeleteAllOccursForThrottleId`
- `0x1800064bd`: `Throttler::DeleteAllOccursForThrottleId`
- `0x1800064f2`: `Throttler::DeleteAllOccursForThrottleId`

## pseudocode

```c
void __fastcall Throttler::DeleteAllOccursForThrottleId(Throttler *this, HKEY a2)
{
  LSTATUS v3; // eax
  DWORD i; // ebx
  LSTATUS v5; // eax
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-29h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-25h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-21h] BYREF
  DWORD cchValueName; // [rsp+6Ch] [rbp-1Dh] BYREF
  DWORD Type; // [rsp+70h] [rbp-19h] BYREF
  DWORD cValues; // [rsp+74h] [rbp-15h] BYREF
  BYTE Data[8]; // [rsp+78h] [rbp-11h] BYREF
  WCHAR ValueName[40]; // [rsp+80h] [rbp-9h] BYREF

  cchValueName = 40;
  Type = 0;
  cbData = 8;
  *(_QWORD *)Data = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v3 = RegQueryInfoKeyW(a2, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v3 )
  {
    DebugPrint(0, "THROTTLE ERROR: %s:%d - ret = %d\n", "Throttler::DeleteAllOccursForThrottleId", 656, v3);
  }
  else if ( cbMaxValueNameLen > 0x28 || cbMaxValueLen > 8 )
  {
    DebugPrint(
      0,
      "THROTTLE CONFIGURATION ERROR - unexpected registry value  %s:%d\n",
      "Throttler::DeleteAllOccursForThrottleId",
      662);
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      cchValueName = 40;
      cbData = 8;
      v5 = RegEnumValueW(a2, i, ValueName, &cchValueName, 0, &Type, Data, &cbData);
      if ( v5 == 259 )
        break;
      if ( v5 )
      {
        DebugPrint(0, "THROTTLE ERROR: %s:%d - ret = %d\n", "Throttler::DeleteAllOccursForThrottleId", 685, v5);
      }
      else if ( Type == 11 )
      {
        RegDeleteValueW(a2, ValueName);
      }
    }
  }
}

```

## disassembly

```asm
0x180006370  mov     [rsp-8+arg_0], rbx
0x180006375  mov     [rsp-8+arg_10], rdi
0x18000637a  push    rbp
0x18000637b  lea     rbp, [rsp-57h]
0x180006380  sub     rsp, 0E0h
0x180006387  mov     rax, cs:__security_cookie
0x18000638e  xor     rax, rsp
0x180006391  mov     [rbp+57h+var_10], rax
0x180006395  mov     [rsp+0E0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000639e  lea     rax, [rbp+57h+cbMaxValueLen]
0x1800063a2  mov     [rsp+0E0h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x1800063ab  mov     rdi, rdx
0x1800063ae  mov     [rsp+0E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800063b3  xor     r9d, r9d; lpReserved
0x1800063b6  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x1800063ba  mov     [rbp+57h+cchValueName], 28h ; '('
0x1800063c1  mov     [rsp+0E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800063c6  xor     r8d, r8d; lpcchClass
0x1800063c9  lea     rax, [rbp+57h+cValues]
0x1800063cd  mov     [rbp+57h+Type], 0
0x1800063d4  mov     [rsp+0E0h+lpcValues], rax; lpcValues
0x1800063d9  xor     edx, edx; lpClass
0x1800063db  mov     [rsp+0E0h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x1800063e4  mov     rcx, rdi; hKey
0x1800063e7  mov     [rsp+0E0h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x1800063f0  mov     [rsp+0E0h+lpcSubKeys], 0; lpcSubKeys
0x1800063f9  mov     [rbp+57h+cbData], 8
0x180006400  mov     qword ptr [rbp+57h+Data], 0
0x180006408  mov     [rbp+57h+cValues], 0
0x18000640f  mov     [rbp+57h+cbMaxValueNameLen], 0
0x180006416  mov     [rbp+57h+cbMaxValueLen], 0
0x18000641d  call    cs:__imp_RegQueryInfoKeyW
0x180006423  test    eax, eax
0x180006425  jz      short loc_18000644B
0x180006427  mov     r9d, 290h
0x18000642d  mov     dword ptr [rsp+0E0h+lpcSubKeys], eax
0x180006431  lea     r8, aThrottlerDelet; "Throttler::DeleteAllOccursForThrottleId"
0x180006438  xor     ecx, ecx; Level
0x18000643a  lea     rdx, aThrottleErrorS; "THROTTLE ERROR: %s:%d - ret = %d\n"
0x180006441  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180006446  jmp     loc_180006507
0x18000644b  cmp     [rbp+57h+cbMaxValueNameLen], 28h ; '('
0x18000644f  ja      loc_1800064EC
0x180006455  cmp     [rbp+57h+cbMaxValueLen], 8
0x180006459  ja      loc_1800064EC
0x18000645f  xor     ebx, ebx
0x180006461  lea     rax, [rbp+57h+cbData]
0x180006465  mov     [rbp+57h+cchValueName], 28h ; '('
0x18000646c  mov     [rsp+0E0h+lpcValues], rax; lpcbData
0x180006471  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180006475  lea     rax, [rbp+57h+Data]
0x180006479  mov     [rbp+57h+cbData], 8
0x180006480  mov     [rsp+0E0h+lpcbMaxClassLen], rax; lpData
0x180006485  lea     r8, [rbp+57h+ValueName]; lpValueName
0x180006489  lea     rax, [rbp+57h+Type]
0x18000648d  mov     edx, ebx; dwIndex
0x18000648f  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpType
0x180006494  mov     rcx, rdi; hKey
0x180006497  mov     [rsp+0E0h+lpcSubKeys], 0; lpReserved
0x1800064a0  call    cs:__imp_RegEnumValueW
0x1800064a6  cmp     eax, 103h
0x1800064ab  jz      short loc_180006507
0x1800064ad  inc     ebx
0x1800064af  test    eax, eax
0x1800064b1  jz      short loc_1800064D4
0x1800064b3  mov     r9d, 2ADh
0x1800064b9  mov     dword ptr [rsp+0E0h+lpcSubKeys], eax
0x1800064bd  lea     r8, aThrottlerDelet; "Throttler::DeleteAllOccursForThrottleId"
0x1800064c4  xor     ecx, ecx; Level
0x1800064c6  lea     rdx, aThrottleErrorS; "THROTTLE ERROR: %s:%d - ret = %d\n"
0x1800064cd  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x1800064d2  jmp     short loc_180006461
0x1800064d4  cmp     [rbp+57h+Type], 0Bh
0x1800064d8  jnz     short loc_180006461
0x1800064da  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x1800064de  mov     rcx, rdi; hKey
0x1800064e1  call    cs:__imp_RegDeleteValueW
0x1800064e7  jmp     loc_180006461
0x1800064ec  mov     r9d, 296h
0x1800064f2  lea     r8, aThrottlerDelet; "Throttler::DeleteAllOccursForThrottleId"
0x1800064f9  lea     rdx, aThrottleConfig; "THROTTLE CONFIGURATION ERROR - unexpect"...
0x180006500  xor     ecx, ecx; Level
0x180006502  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180006507  mov     rcx, [rbp+57h+var_10]
0x18000650b  xor     rcx, rsp; StackCookie
0x18000650e  call    __security_check_cookie
0x180006513  lea     r11, [rsp+0E0h+var_s0]
0x18000651b  mov     rbx, [r11+10h]
0x18000651f  mov     rdi, [r11+20h]
0x180006523  mov     rsp, r11
0x180006526  pop     rbp
0x180006527  retn
```
