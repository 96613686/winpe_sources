# RegReader::Open(HKEY__ *,ushort const *)

- ea: `0x18001600c`
- end: `0x1800160b8`
- name: `?Open@RegReader@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `172`
- prototype: `__int64 __fastcall(HKEY *this, HKEY, unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001094c`
- `0x180013d40`
- `0x1800140b0`
- `0x180015054`

## callees

- `0x18001600c`
- `0x18001619c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016076`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016066`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016089`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016066`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016089`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001605e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016081`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001605e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016081`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegReader::Open(HKEY *this, HKEY a2, unsigned __int16 *a3, unsigned int a4)
{
  int v5; // eax
  HKEY v6; // rsi
  int v7; // edi
  HKEY v8; // rbp
  DWORD v9; // ebx
  DWORD LastError; // ebx
  HKEY *v12; // [rsp+28h] [rbp-20h]
  HKEY v13; // [rsp+68h] [rbp+20h] BYREF

  v13 = 0;
  v5 = RegHelpers::RegOpenKeyExW(a2, (HKEY)a3, a3, a4, (unsigned int)&v13, v12);
  v6 = *this;
  v7 = v5;
  if ( v5 )
  {
    if ( v6 )
    {
      LastError = GetLastError();
      RegCloseKey(v6);
      SetLastError(LastError);
    }
    *this = 0;
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
  }
  else
  {
    v8 = v13;
    if ( v6 )
    {
      v9 = GetLastError();
      RegCloseKey(v6);
      SetLastError(v9);
    }
    *this = v8;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001600c  mov     r11, rsp
0x18001600f  mov     [r11+8], rbx
0x180016013  mov     [r11+10h], rbp
0x180016017  push    rsi
0x180016018  push    rdi
0x180016019  push    r14
0x18001601b  sub     rsp, 30h
0x18001601f  mov     r14, rcx
0x180016022  mov     qword ptr [r11+20h], 0
0x18001602a  lea     rcx, [r11+20h]
0x18001602e  mov     rax, rdx
0x180016031  mov     [r11-28h], rcx
0x180016035  mov     rdx, r8; lpSubKey
0x180016038  mov     rcx, rax; hKey
0x18001603b  call    ?RegOpenKeyExW@RegHelpers@@YAJPEAUHKEY__@@PEBGKKPEAPEAU2@@Z; RegHelpers::RegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180016040  mov     rsi, [r14]
0x180016043  mov     edi, eax
0x180016045  test    eax, eax
0x180016047  jnz     short loc_180016071
0x180016049  mov     rbp, [rsp+48h+arg_18]
0x18001604e  test    rsi, rsi
0x180016051  jz      short loc_18001606C
0x180016053  call    cs:__imp_GetLastError
0x180016059  mov     rcx, rsi; hKey
0x18001605c  mov     ebx, eax
0x18001605e  call    cs:__imp_RegCloseKey
0x180016064  mov     ecx, ebx; dwErrCode
0x180016066  call    cs:__imp_SetLastError
0x18001606c  mov     [r14], rbp
0x18001606f  jmp     short loc_1800160A3
0x180016071  test    rsi, rsi
0x180016074  jz      short loc_18001608F
0x180016076  call    cs:__imp_GetLastError
0x18001607c  mov     rcx, rsi; hKey
0x18001607f  mov     ebx, eax
0x180016081  call    cs:__imp_RegCloseKey
0x180016087  mov     ecx, ebx; dwErrCode
0x180016089  call    cs:__imp_SetLastError
0x18001608f  mov     qword ptr [r14], 0
0x180016096  test    edi, edi
0x180016098  jle     short loc_1800160A3
0x18001609a  movzx   edi, di
0x18001609d  or      edi, 80070000h
0x1800160a3  mov     rbx, [rsp+48h+arg_0]
0x1800160a8  mov     eax, edi
0x1800160aa  mov     rbp, [rsp+48h+arg_8]
0x1800160af  add     rsp, 30h
0x1800160b3  pop     r14
0x1800160b5  pop     rdi
0x1800160b6  pop     rsi
0x1800160b7  retn
```
