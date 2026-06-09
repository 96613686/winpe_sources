# WinSATRegValueIsNonZero(ushort const *,bool &)

- ea: `0x14004ad08`
- end: `0x14004adae`
- name: `?WinSATRegValueIsNonZero@@YAKPEBGAEA_N@Z`
- size: `166`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140041b40`

## callees

- `0x14004ad08`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x14004ad80`
- `ADVAPI32!RegQueryValueExW` at `0x14004ad80`
- `ADVAPI32!RegOpenKeyExW` at `0x14004ad45`
- `ADVAPI32!RegOpenKeyExW` at `0x14004ad45`
- `ADVAPI32!RegCloseKey` at `0x14004ad9e`
- `ADVAPI32!RegCloseKey` at `0x14004ad9e`

## pseudocode

```c
LSTATUS __fastcall WinSATRegValueIsNonZero(const unsigned __int16 *a1, bool *a2)
{
  LSTATUS result; // eax
  LSTATUS v4; // ebx
  const unsigned __int16 *Type; // [rsp+50h] [rbp+20h] BYREF
  int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  Type = a1;
  *a2 = 0;
  hKey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSAT", 0, 1u, &hKey);
  if ( !result )
  {
    LODWORD(Type) = 0;
    Data = 0;
    cbData = 4;
    v4 = RegQueryValueExW(hKey, L"SFEC", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData);
    if ( !v4 && (_DWORD)Type == 4 )
      *a2 = Data != 0;
    RegCloseKey(hKey);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x14004ad08  mov     [rsp-18h+Type], rcx
0x14004ad0d  push    rbp
0x14004ad0e  push    rbx
0x14004ad0f  push    rdi
0x14004ad10  mov     rbp, rsp
0x14004ad13  sub     rsp, 30h
0x14004ad17  mov     rdi, rdx
0x14004ad1a  mov     byte ptr [rdx], 0
0x14004ad1d  lea     rax, [rbp+hKey]
0x14004ad21  mov     [rbp+hKey], 0
0x14004ad29  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14004ad30  mov     [rsp+30h+phkResult], rax; phkResult
0x14004ad35  mov     r9d, 1; samDesired
0x14004ad3b  xor     r8d, r8d; ulOptions
0x14004ad3e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14004ad45  call    cs:__imp_RegOpenKeyExW
0x14004ad4b  test    eax, eax
0x14004ad4d  jnz     short loc_14004ADA6
0x14004ad4f  mov     rcx, [rbp+hKey]; hKey
0x14004ad53  lea     r9, [rbp+Type]; lpType
0x14004ad57  mov     dword ptr [rbp+Type], eax
0x14004ad5a  lea     rdx, aSfec; "SFEC"
0x14004ad61  mov     [rbp+Data], eax
0x14004ad64  xor     r8d, r8d; lpReserved
0x14004ad67  lea     rax, [rbp+cbData]
0x14004ad6b  mov     [rbp+cbData], 4
0x14004ad72  mov     [rsp+30h+lpcbData], rax; lpcbData
0x14004ad77  lea     rax, [rbp+Data]
0x14004ad7b  mov     [rsp+30h+phkResult], rax; lpData
0x14004ad80  call    cs:__imp_RegQueryValueExW
0x14004ad86  mov     ebx, eax
0x14004ad88  test    eax, eax
0x14004ad8a  jnz     short loc_14004AD9A
0x14004ad8c  cmp     dword ptr [rbp+Type], 4
0x14004ad90  jnz     short loc_14004AD9A
0x14004ad92  cmp     [rbp+Data], eax
0x14004ad95  setnz   cl
0x14004ad98  mov     [rdi], cl
0x14004ad9a  mov     rcx, [rbp+hKey]; hKey
0x14004ad9e  call    cs:__imp_RegCloseKey
0x14004ada4  mov     eax, ebx
0x14004ada6  add     rsp, 30h
0x14004adaa  pop     rdi
0x14004adab  pop     rbx
0x14004adac  pop     rbp
0x14004adad  retn
```
