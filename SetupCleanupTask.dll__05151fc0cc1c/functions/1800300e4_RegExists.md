# RegExists

- ea: `0x1800300e4`
- end: `0x180030195`
- name: `RegExists`
- size: `177`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001cc9c`

## callees

- `0x1800300e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003011f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003011f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003017a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003017a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003015c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003015c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030182`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030182`

## pseudocode

```c
_BOOL8 __fastcall RegExists(__int64 a1, const WCHAR *a2, const WCHAR *a3)
{
  __int64 v5; // rcx
  BOOL v6; // ebx
  LSTATUS Value; // eax
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF

  v9 = 0;
  v5 = -2147483646;
  if ( a2 )
  {
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, (PHKEY)&v9) || (v5 = v9) == 0 )
    {
      v6 = 0;
      goto LABEL_11;
    }
  }
  else
  {
    v9 = -2147483646;
  }
  if ( a3 )
  {
    Value = RegQueryValueExW((HKEY)v5, a3, 0, 0, 0, 0);
    v5 = v9;
    v6 = Value == 0;
  }
  else
  {
    v6 = 1;
  }
  if ( a2 )
    RegCloseKey((HKEY)v5);
LABEL_11:
  SetLastError(0);
  return v6;
}

```

## disassembly

```asm
0x1800300e4  mov     r11, rsp
0x1800300e7  mov     [r11+10h], rbx
0x1800300eb  mov     [r11+8], rcx
0x1800300ef  push    rdi
0x1800300f0  sub     rsp, 30h
0x1800300f4  mov     qword ptr [r11+8], 0
0x1800300fc  mov     rbx, r8
0x1800300ff  mov     rdi, rdx
0x180030102  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180030109  test    rdx, rdx
0x18003010c  jz      short loc_180030137
0x18003010e  lea     rax, [r11+8]
0x180030112  mov     r9d, 20019h; samDesired
0x180030118  xor     r8d, r8d; ulOptions
0x18003011b  mov     [r11-18h], rax
0x18003011f  call    cs:__imp_RegOpenKeyExW
0x180030125  test    eax, eax
0x180030127  jnz     short loc_180030133
0x180030129  mov     rcx, [rsp+38h+arg_0]
0x18003012e  test    rcx, rcx
0x180030131  jnz     short loc_18003013C
0x180030133  xor     ebx, ebx
0x180030135  jmp     short loc_180030180
0x180030137  mov     [rsp+38h+arg_0], rcx
0x18003013c  test    rbx, rbx
0x18003013f  jz      short loc_180030170
0x180030141  mov     [rsp+38h+lpcbData], 0; lpcbData
0x18003014a  xor     r9d, r9d; lpType
0x18003014d  xor     r8d, r8d; lpReserved
0x180030150  mov     [rsp+38h+lpData], 0; lpData
0x180030159  mov     rdx, rbx; lpValueName
0x18003015c  call    cs:__imp_RegQueryValueExW
0x180030162  mov     rcx, [rsp+38h+arg_0]
0x180030167  xor     ebx, ebx
0x180030169  test    eax, eax
0x18003016b  setz    bl
0x18003016e  jmp     short loc_180030175
0x180030170  mov     ebx, 1
0x180030175  test    rdi, rdi
0x180030178  jz      short loc_180030180
0x18003017a  call    cs:__imp_RegCloseKey
0x180030180  xor     ecx, ecx; dwErrCode
0x180030182  call    cs:__imp_SetLastError
0x180030188  mov     eax, ebx
0x18003018a  mov     rbx, [rsp+38h+arg_8]
0x18003018f  add     rsp, 30h
0x180030193  pop     rdi
0x180030194  retn
```
