# WriteRegQWORDValue(HKEY__ *,ushort const *,ushort const *,__int64,_SECURITY_ATTRIBUTES *)

- ea: `0x1400183f0`
- end: `0x140018517`
- name: `?WriteRegQWORDValue@@YAJPEAUHKEY__@@PEBG1_JPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001a0c4`

## callees

- `0x14000740c`
- `0x1400183f0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400184f7`
- `ADVAPI32!RegCloseKey` at `0x1400184f7`
- `ADVAPI32!RegCreateKeyExW` at `0x14001845b`
- `ADVAPI32!RegCreateKeyExW` at `0x14001845b`
- `ADVAPI32!RegSetValueExW` at `0x1400184b1`
- `ADVAPI32!RegSetValueExW` at `0x1400184b1`
- `KERNEL32!SetLastError` at `0x1400184ff`
- `KERNEL32!SetLastError` at `0x1400184ff`
- `KERNEL32!GetLastError` at `0x140018478`
- `KERNEL32!GetLastError` at `0x1400184ce`
- `KERNEL32!GetLastError` at `0x140018478`
- `KERNEL32!GetLastError` at `0x1400184ce`

## string_xrefs

- `0x140018481`: `RegCreateKeyEx for subkey %1 failed  with Status = %2!d!. GetLastError is 0x%3!x!`
- `0x1400184db`: `RegSetValueEx for value %1 failed  with Status = %2!d!. GetLastError is 0x%3!x!`

## pseudocode

```c
__int64 __fastcall WriteRegQWORDValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, __int64 a4)
{
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  unsigned int v7; // edi
  DWORD LastError; // eax
  LSTATUS v9; // eax
  unsigned int v10; // edi
  DWORD v11; // eax
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF
  __int64 Data; // [rsp+78h] [rbp+20h] BYREF

  Data = a4;
  hKey = 0;
  if ( a2 )
  {
    v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 0x20106u, 0, &hKey, 0);
    v7 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      else
        v5 = v6;
      LastError = GetLastError();
      LogError(L"RegCreateKeyEx for subkey %1 failed  with Status = %2!d!. GetLastError is 0x%3!x!", a2, v7, LastError);
    }
    else
    {
      v5 = 0;
      v9 = RegSetValueExW(hKey, L"EnforcementStartTime", 0, 0xBu, (const BYTE *)&Data, 8u);
      v10 = v9;
      if ( v9 )
      {
        if ( v9 > 0 )
          v5 = (unsigned __int16)v9 | 0x80070000;
        else
          v5 = v9;
        v11 = GetLastError();
        LogError(
          L"RegSetValueEx for value %1 failed  with Status = %2!d!. GetLastError is 0x%3!x!",
          L"EnforcementStartTime",
          v10,
          v11);
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    v5 = -2147024809;
  }
  SetLastError(0);
  return v5;
}

```

## disassembly

```asm
0x1400183f0  mov     rax, rsp
0x1400183f3  mov     [rax+8], rbx
0x1400183f7  mov     [rax+10h], rsi
0x1400183fb  mov     [rax+20h], r9
0x1400183ff  mov     [rax+18h], r8
0x140018403  push    rdi
0x140018404  sub     rsp, 50h
0x140018408  mov     qword ptr [rax+18h], 0
0x140018410  mov     rsi, rdx
0x140018413  test    rdx, rdx
0x140018416  jnz     short loc_140018422
0x140018418  mov     ebx, 80070057h
0x14001841d  jmp     loc_1400184FD
0x140018422  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x14001842b  lea     rax, [rsp+58h+hKey]
0x140018430  mov     [rsp+58h+phkResult], rax; phkResult
0x140018435  xor     r9d, r9d; lpClass
0x140018438  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140018441  xor     r8d, r8d; Reserved
0x140018444  mov     [rsp+58h+samDesired], 20106h; samDesired
0x14001844c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140018453  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14001845b  call    cs:__imp_RegCreateKeyExW
0x140018461  mov     edi, eax
0x140018463  test    eax, eax
0x140018465  jz      short loc_14001848A
0x140018467  test    eax, eax
0x140018469  jg      short loc_14001846F
0x14001846b  mov     ebx, eax
0x14001846d  jmp     short loc_140018478
0x14001846f  movzx   ebx, di
0x140018472  or      ebx, 80070000h
0x140018478  call    cs:__imp_GetLastError
0x14001847e  mov     rdx, rsi
0x140018481  lea     rcx, aRegcreatekeyex_0; "RegCreateKeyEx for subkey %1 failed  wi"...
0x140018488  jmp     short loc_1400184E2
0x14001848a  mov     rcx, [rsp+58h+hKey]; hKey
0x14001848f  lea     rax, [rsp+58h+Data]
0x140018494  xor     ebx, ebx
0x140018496  mov     [rsp+58h+samDesired], 8; cbData
0x14001849e  xor     r8d, r8d; Reserved
0x1400184a1  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1400184a6  lea     rdx, aEnforcementsta; "EnforcementStartTime"
0x1400184ad  lea     r9d, [rbx+0Bh]; dwType
0x1400184b1  call    cs:__imp_RegSetValueExW
0x1400184b7  mov     edi, eax
0x1400184b9  test    eax, eax
0x1400184bb  jz      short loc_1400184ED
0x1400184bd  test    eax, eax
0x1400184bf  jg      short loc_1400184C5
0x1400184c1  mov     ebx, eax
0x1400184c3  jmp     short loc_1400184CE
0x1400184c5  movzx   ebx, di
0x1400184c8  or      ebx, 80070000h
0x1400184ce  call    cs:__imp_GetLastError
0x1400184d4  lea     rdx, aEnforcementsta; "EnforcementStartTime"
0x1400184db  lea     rcx, aRegsetvalueexF; "RegSetValueEx for value %1 failed  with"...
0x1400184e2  mov     r9d, eax
0x1400184e5  mov     r8d, edi
0x1400184e8  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x1400184ed  mov     rcx, [rsp+58h+hKey]; hKey
0x1400184f2  test    rcx, rcx
0x1400184f5  jz      short loc_1400184FD
0x1400184f7  call    cs:__imp_RegCloseKey
0x1400184fd  xor     ecx, ecx; dwErrCode
0x1400184ff  call    cs:__imp_SetLastError
0x140018505  mov     rsi, [rsp+58h+arg_8]
0x14001850a  mov     eax, ebx
0x14001850c  mov     rbx, [rsp+58h+arg_0]
0x140018511  add     rsp, 50h
0x140018515  pop     rdi
0x140018516  retn
```
