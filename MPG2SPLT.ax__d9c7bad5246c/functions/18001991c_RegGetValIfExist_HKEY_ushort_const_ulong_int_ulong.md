# RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)

- ea: `0x18001991c`
- end: `0x1800199bb`
- name: `?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z`
- size: `159`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, unsigned int@<r8d>, int@<r9d>, unsigned int *)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180012acc`
- `0x1800156e4`
- `0x180015a0c`
- `0x18001ceb8`
- `0x18001d190`
- `0x18002506c`
- `0x18002813c`

## callees

- `0x18001991c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800199a1`
- `ADVAPI32!RegSetValueExW` at `0x1800199a1`
- `ADVAPI32!RegQueryValueExW` at `0x18001996f`
- `ADVAPI32!RegQueryValueExW` at `0x18001996f`

## pseudocode

```c
LSTATUS __fastcall RegGetValIfExist(HKEY hKey, LPCWSTR lpValueName, unsigned int a3, int a4, BYTE *a5)
{
  BYTE *v5; // rbx
  LSTATUS result; // eax
  DWORD v10; // [rsp+50h] [rbp+8h] BYREF
  int lpData; // [rsp+60h] [rbp+18h] BYREF

  v5 = a5;
  lpData = 0;
  *(_DWORD *)a5 = a3;
  if ( !hKey )
    return 110;
  LODWORD(a5) = 4;
  v10 = 4;
  result = RegQueryValueExW(hKey, lpValueName, 0, &v10, (LPBYTE)&lpData, (LPDWORD)&a5);
  if ( result )
  {
    if ( a4 )
      return RegSetValueExW(hKey, lpValueName, 0, 4u, v5, 4u);
  }
  else
  {
    *(_DWORD *)v5 = lpData;
  }
  return result;
}

```

## disassembly

```asm
0x18001991c  mov     r11, rsp
0x18001991f  mov     [r11+10h], rbx
0x180019923  push    rbp
0x180019924  push    rsi
0x180019925  push    rdi
0x180019926  sub     rsp, 30h
0x18001992a  mov     rbx, [rsp+48h+arg_20]
0x18001992f  mov     ebp, r9d
0x180019932  mov     [rsp+48h+arg_10], 0
0x18001993a  mov     rsi, rdx
0x18001993d  mov     rdi, rcx
0x180019940  mov     [rbx], r8d
0x180019943  test    rcx, rcx
0x180019946  jz      short loc_1800199A9
0x180019948  lea     rax, [r11+28h]
0x18001994c  mov     dword ptr [rsp+48h+arg_20], 4
0x180019954  mov     [r11-20h], rax
0x180019958  lea     r9, [r11+8]; lpType
0x18001995c  lea     rax, [r11+18h]
0x180019960  mov     [rsp+48h+arg_0], 4
0x180019968  xor     r8d, r8d; lpReserved
0x18001996b  mov     [r11-28h], rax
0x18001996f  call    cs:__imp_RegQueryValueExW
0x180019975  test    eax, eax
0x180019977  jnz     short loc_180019981
0x180019979  mov     ecx, [rsp+48h+arg_10]
0x18001997d  mov     [rbx], ecx
0x18001997f  jmp     short loc_1800199AE
0x180019981  test    ebp, ebp
0x180019983  jz      short loc_1800199AE
0x180019985  mov     [rsp+48h+cbData], 4; cbData
0x18001998d  mov     r9d, 4; dwType
0x180019993  xor     r8d, r8d; Reserved
0x180019996  mov     [rsp+48h+lpData], rbx; lpData
0x18001999b  mov     rdx, rsi; lpValueName
0x18001999e  mov     rcx, rdi; hKey
0x1800199a1  call    cs:__imp_RegSetValueExW
0x1800199a7  jmp     short loc_1800199AE
0x1800199a9  mov     eax, 6Eh ; 'n'
0x1800199ae  mov     rbx, [rsp+48h+arg_8]
0x1800199b3  add     rsp, 30h
0x1800199b7  pop     rdi
0x1800199b8  pop     rsi
0x1800199b9  pop     rbp
0x1800199ba  retn
```
