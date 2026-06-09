# CRegUtilT<ulong,CRegType,0,0>::SetValue(HKEY__ *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x1400113b0`
- end: `0x1400114cb`
- name: `?SetValue@?$CRegUtilT@KUCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG1KK@Z`
- size: `283`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, int, DWORD cbData)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140007dcc`
- `0x140011354`

## callees

- `0x140003454`
- `0x140004780`
- `0x1400113b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140011487`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140011487`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011443`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400114b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011443`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400114b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400113ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400113ff`

## pseudocode

```c
__int64 __fastcall CRegUtilT<unsigned long,CRegType,0,0>::SetValue(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        int a4,
        DWORD cbData)
{
  int v8; // eax
  HKEY v9; // rdi
  unsigned int v10; // ebx
  LSTATUS v11; // eax
  HKEY hKeya; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+58h] [rbp+20h] BYREF

  Data = a4;
  if ( hKey == HKEY_CURRENT_USER )
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  hKeya = 0;
  v8 = RegOpenKeyExW(hKey, lpSubKey, 0, 2u, &hKeya);
  if ( v8 )
  {
    v9 = 0;
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v10 = v8;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
  }
  else
  {
    v9 = hKeya;
    v10 = 0;
    hKeya = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  if ( (v10 & 0x80000000) != 0 )
    goto LABEL_11;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v11 = RegSetValueExW(v9, lpValueName, 0, 4u, (const BYTE *)&Data, cbData);
  v10 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v10 = (unsigned __int16)v11 | 0x80070000;
LABEL_11:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
    goto LABEL_16;
  }
  v10 = 0;
LABEL_16:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
  if ( v9 )
    RegCloseKey(v9);
  return v10;
}

```

## disassembly

```asm
0x1400113b0  mov     [rsp+arg_8], rbx
0x1400113b5  mov     [rsp+arg_10], rsi
0x1400113ba  mov     [rsp+Data], r9d
0x1400113bf  push    rdi
0x1400113c0  sub     rsp, 30h
0x1400113c4  mov     rsi, r8
0x1400113c7  mov     rdi, rdx
0x1400113ca  mov     rbx, rcx
0x1400113cd  cmp     rcx, 0FFFFFFFF80000001h
0x1400113d4  jnz     short loc_1400113DD
0x1400113d6  xor     ecx, ecx
0x1400113d8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400113dd  lea     rax, [rsp+38h+hKey]
0x1400113e2  mov     [rsp+38h+hKey], 0
0x1400113eb  mov     r9d, 2; samDesired
0x1400113f1  mov     [rsp+38h+phkResult], rax; phkResult
0x1400113f6  xor     r8d, r8d; ulOptions
0x1400113f9  mov     rdx, rdi; lpSubKey
0x1400113fc  mov     rcx, rbx; hKey
0x1400113ff  call    cs:__imp_RegOpenKeyExW
0x140011405  test    eax, eax
0x140011407  jz      short loc_140011422
0x140011409  xor     edi, edi
0x14001140b  test    eax, eax
0x14001140d  jle     short loc_140011417
0x14001140f  movzx   eax, ax
0x140011412  or      eax, 80070000h
0x140011417  mov     ecx, eax
0x140011419  mov     ebx, eax
0x14001141b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140011420  jmp     short loc_140011432
0x140011422  mov     rdi, [rsp+38h+hKey]
0x140011427  xor     ebx, ebx
0x140011429  mov     [rsp+38h+hKey], 0
0x140011432  mov     ecx, ebx
0x140011434  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140011439  mov     rcx, [rsp+38h+hKey]; hKey
0x14001143e  test    rcx, rcx
0x140011441  jz      short loc_140011452
0x140011443  call    cs:__imp_RegCloseKey
0x140011449  mov     [rsp+38h+hKey], 0
0x140011452  test    ebx, ebx
0x140011454  jns     short loc_14001145F
0x140011456  mov     ecx, ebx
0x140011458  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001145d  jmp     short loc_1400114A4
0x14001145f  xor     ecx, ecx
0x140011461  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140011466  mov     eax, [rsp+38h+arg_20]
0x14001146a  mov     r9d, 4; dwType
0x140011470  mov     [rsp+38h+cbData], eax; cbData
0x140011474  xor     r8d, r8d; Reserved
0x140011477  lea     rax, [rsp+38h+Data]
0x14001147c  mov     rdx, rsi; lpValueName
0x14001147f  mov     rcx, rdi; hKey
0x140011482  mov     [rsp+38h+phkResult], rax; lpData
0x140011487  call    cs:__imp_RegSetValueExW
0x14001148d  mov     ebx, eax
0x14001148f  test    eax, eax
0x140011491  jz      short loc_1400114A2
0x140011493  test    eax, eax
0x140011495  jle     short loc_140011456
0x140011497  movzx   ebx, bx
0x14001149a  or      ebx, 80070000h
0x1400114a0  jmp     short loc_140011456
0x1400114a2  xor     ebx, ebx
0x1400114a4  mov     ecx, ebx
0x1400114a6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400114ab  test    rdi, rdi
0x1400114ae  jz      short loc_1400114B9
0x1400114b0  mov     rcx, rdi; hKey
0x1400114b3  call    cs:__imp_RegCloseKey
0x1400114b9  mov     rsi, [rsp+38h+arg_10]
0x1400114be  mov     eax, ebx
0x1400114c0  mov     rbx, [rsp+38h+arg_8]
0x1400114c5  add     rsp, 30h
0x1400114c9  pop     rdi
0x1400114ca  retn
```
