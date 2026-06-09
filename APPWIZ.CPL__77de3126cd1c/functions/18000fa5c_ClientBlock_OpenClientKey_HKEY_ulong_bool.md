# ClientBlock::_OpenClientKey(HKEY__ *,ulong,bool)

- ea: `0x18000fa5c`
- end: `0x18000fb12`
- name: `?_OpenClientKey@ClientBlock@@AEAAPEAUHKEY__@@PEAU2@K_N@Z`
- size: `182`
- prototype: `HKEY(ClientBlock *__hidden this, HKEY, unsigned int, bool)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009550`
- `0x18000b9dc`
- `0x18000f200`
- `0x18000f83c`
- `0x18000f99c`

## callees

- `0x180007960`
- `0x18000add0`
- `0x18000fa5c`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fae1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fae1`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000faec`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000faec`

## pseudocode

```c
HKEY __fastcall ClientBlock::_OpenClientKey(ClientBlock *this, HKEY a2, int a3, unsigned __int8 a4)
{
  int v5; // ebx
  const unsigned __int16 *ClientTypeString; // rax
  struct DirectUI::Value *v9; // [rsp+30h] [rbp-248h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-240h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-238h] BYREF

  v5 = a4;
  phkResult = 0;
  v9 = 0;
  ClientTypeString = ClientBlock::GetClientTypeString(this, &v9);
  if ( ClientTypeString )
  {
    if ( StringCchPrintfW(SubKey, 0x104u, L"Software\\Clients\\%s", ClientTypeString) >= 0 )
      RegOpenKeyExW(a2, SubKey, 0, a3 | ((v5 + 1) << 8), &phkResult);
    DirectUI::Value::Release(v9);
  }
  return phkResult;
}

```

## disassembly

```asm
0x18000fa5c  push    rbx
0x18000fa5e  push    rsi
0x18000fa5f  push    rdi
0x18000fa60  sub     rsp, 260h
0x18000fa67  mov     rax, cs:__security_cookie
0x18000fa6e  xor     rax, rsp
0x18000fa71  mov     [rsp+278h+var_28], rax
0x18000fa79  mov     rdi, rdx
0x18000fa7c  movzx   ebx, r9b
0x18000fa80  lea     rdx, [rsp+278h+var_248]; struct DirectUI::Value **
0x18000fa85  mov     [rsp+278h+var_240], 0
0x18000fa8e  mov     esi, r8d
0x18000fa91  mov     [rsp+278h+var_248], 0
0x18000fa9a  call    ?GetClientTypeString@ClientBlock@@QEAAPEBGPEAPEAVValue@DirectUI@@@Z; ClientBlock::GetClientTypeString(DirectUI::Value * *)
0x18000fa9f  test    rax, rax
0x18000faa2  jz      short loc_18000FAF2
0x18000faa4  mov     r9, rax
0x18000faa7  lea     r8, aSoftwareClient; "Software\\Clients\\%s"
0x18000faae  mov     edx, 104h; unsigned __int64
0x18000fab3  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x18000fab8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fabd  test    eax, eax
0x18000fabf  js      short loc_18000FAE7
0x18000fac1  lea     r9d, [rbx+1]
0x18000fac5  xor     r8d, r8d; ulOptions
0x18000fac8  shl     r9d, 8
0x18000facc  lea     rax, [rsp+278h+var_240]
0x18000fad1  or      r9d, esi; samDesired
0x18000fad4  mov     [rsp+278h+phkResult], rax; phkResult
0x18000fad9  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x18000fade  mov     rcx, rdi; hKey
0x18000fae1  call    cs:__imp_RegOpenKeyExW
0x18000fae7  mov     rcx, [rsp+278h+var_248]
0x18000faec  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000faf2  mov     rax, [rsp+278h+var_240]
0x18000faf7  mov     rcx, [rsp+278h+var_28]
0x18000faff  xor     rcx, rsp; StackCookie
0x18000fb02  call    __security_check_cookie
0x18000fb07  add     rsp, 260h
0x18000fb0e  pop     rdi
0x18000fb0f  pop     rsi
0x18000fb10  pop     rbx
0x18000fb11  retn
```
