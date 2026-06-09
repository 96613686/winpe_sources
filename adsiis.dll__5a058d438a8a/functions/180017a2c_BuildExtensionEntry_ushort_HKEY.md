# BuildExtensionEntry(ushort *,HKEY__ *)

- ea: `0x180017a2c`
- end: `0x180017b97`
- name: `?BuildExtensionEntry@@YAPEAU_extension_entry@@PEAGPEAUHKEY__@@@Z`
- size: `363`
- prototype: `struct _extension_entry *__fastcall(LPCOLESTR lpsz, HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017704`

## callees

- `0x180017a2c`
- `0x18001d66a`
- `0x18001d6c0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180017ae0`
- `msvcrt!wcscpy_s` at `0x180017b07`
- `msvcrt!wcscpy_s` at `0x180017b4b`
- `msvcrt!wcscpy_s` at `0x180017ae0`
- `msvcrt!wcscpy_s` at `0x180017b07`
- `msvcrt!wcscpy_s` at `0x180017b4b`
- `ole32!CLSIDFromString` at `0x180017b5b`
- `ole32!CLSIDFromString` at `0x180017b5b`
- `ole32!IIDFromString` at `0x180017b1c`
- `ole32!IIDFromString` at `0x180017b1c`
- `ADVAPI32!RegQueryValueExW` at `0x180017abb`
- `ADVAPI32!RegQueryValueExW` at `0x180017abb`
- `KERNEL32!lstrlenW` at `0x180017b2f`
- `KERNEL32!lstrlenW` at `0x180017b2f`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180017a6a`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180017aeb`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180017a6a`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180017aeb`

## pseudocode

```c
struct _extension_entry *__fastcall BuildExtensionEntry(LPCOLESTR lpsz, HKEY hKey)
{
  char *v4; // rbx
  wchar_t *v5; // r14
  const wchar_t *v6; // rdi
  wchar_t *v7; // rax
  wchar_t *v8; // rsi
  DWORD cbData[4]; // [rsp+30h] [rbp-468h] BYREF
  BYTE Data[528]; // [rsp+40h] [rbp-458h] BYREF
  wchar_t Destination[264]; // [rsp+250h] [rbp-248h] BYREF

  cbData[0] = 0;
  v4 = (char *)AllocADsMem(0x250u);
  if ( v4 )
  {
    v5 = 0;
    memset_0(Data, 0, 0x208u);
    cbData[0] = 520;
    RegQueryValueExW(hKey, L"Interfaces", 0, 0, Data, cbData);
    v6 = (const wchar_t *)Data;
    do
    {
      if ( !*v6 )
        break;
      wcscpy_s(Destination, 0x104u, v6);
      v7 = (wchar_t *)AllocADsMem(0x220u);
      v8 = v7;
      if ( v7 )
      {
        wcscpy_s(v7, 0x104u, Destination);
        IIDFromString(Destination, (LPIID)(v8 + 260));
        *((_QWORD *)v8 + 67) = v5;
        v5 = v8;
      }
      v6 += lstrlenW(v6) + 1;
    }
    while ( v6 );
    wcscpy_s((wchar_t *)v4, 0x104u, lpsz);
    CLSIDFromString(lpsz, (LPCLSID)(v4 + 520));
    *((_QWORD *)v4 + 71) = v5;
  }
  return (struct _extension_entry *)v4;
}

```

## disassembly

```asm
0x180017a2c  mov     [rsp+arg_10], rbx
0x180017a31  mov     [rsp+arg_18], rbp
0x180017a36  push    rsi
0x180017a37  push    rdi
0x180017a38  push    r12
0x180017a3a  push    r14
0x180017a3c  push    r15
0x180017a3e  sub     rsp, 470h
0x180017a45  mov     rax, cs:__security_cookie
0x180017a4c  xor     rax, rsp
0x180017a4f  mov     [rsp+498h+var_38], rax
0x180017a57  mov     rbp, rcx
0x180017a5a  xor     r15d, r15d
0x180017a5d  mov     ecx, 250h; cb
0x180017a62  mov     [rsp+498h+cbData], r15d
0x180017a67  mov     rdi, rdx
0x180017a6a  call    cs:__imp_AllocADsMem
0x180017a70  mov     rbx, rax
0x180017a73  test    rax, rax
0x180017a76  jz      loc_180017B68
0x180017a7c  mov     esi, 208h
0x180017a81  lea     rcx, [rsp+498h+Data]; void *
0x180017a86  mov     r8d, esi; Size
0x180017a89  xor     edx, edx; Val
0x180017a8b  mov     r14d, r15d
0x180017a8e  call    memset_0
0x180017a93  lea     rax, [rsp+498h+cbData]
0x180017a98  mov     [rsp+498h+cbData], esi
0x180017a9c  mov     [rsp+498h+lpcbData], rax; lpcbData
0x180017aa1  lea     rdx, ValueName; "Interfaces"
0x180017aa8  lea     rax, [rsp+498h+Data]
0x180017aad  xor     r9d, r9d; lpType
0x180017ab0  xor     r8d, r8d; lpReserved
0x180017ab3  mov     [rsp+498h+lpData], rax; lpData
0x180017ab8  mov     rcx, rdi; hKey
0x180017abb  call    cs:__imp_RegQueryValueExW
0x180017ac1  lea     rdi, [rsp+498h+Data]
0x180017ac6  mov     r12d, 104h
0x180017acc  cmp     [rdi], r15w
0x180017ad0  jz      short loc_180017B42
0x180017ad2  mov     r8, rdi; Source
0x180017ad5  lea     rcx, [rsp+498h+Destination]; Destination
0x180017add  mov     rdx, r12; SizeInWords
0x180017ae0  call    cs:__imp_wcscpy_s
0x180017ae6  mov     ecx, 220h; cb
0x180017aeb  call    cs:__imp_AllocADsMem
0x180017af1  mov     rsi, rax
0x180017af4  test    rax, rax
0x180017af7  jz      short loc_180017B2C
0x180017af9  lea     r8, [rsp+498h+Destination]; Source
0x180017b01  mov     rdx, r12; SizeInWords
0x180017b04  mov     rcx, rax; Destination
0x180017b07  call    cs:__imp_wcscpy_s
0x180017b0d  lea     rdx, [rsi+208h]; lpiid
0x180017b14  lea     rcx, [rsp+498h+Destination]; lpsz
0x180017b1c  call    cs:__imp_IIDFromString
0x180017b22  mov     [rsi+218h], r14
0x180017b29  mov     r14, rsi
0x180017b2c  mov     rcx, rdi; lpString
0x180017b2f  call    cs:__imp_lstrlenW
0x180017b35  movsxd  r8, eax
0x180017b38  lea     rdi, [rdi+r8*2]
0x180017b3c  add     rdi, 2
0x180017b40  jnz     short loc_180017ACC
0x180017b42  mov     r8, rbp; Source
0x180017b45  mov     rdx, r12; SizeInWords
0x180017b48  mov     rcx, rbx; Destination
0x180017b4b  call    cs:__imp_wcscpy_s
0x180017b51  lea     rdx, [rbx+208h]; pclsid
0x180017b58  mov     rcx, rbp; lpsz
0x180017b5b  call    cs:__imp_CLSIDFromString
0x180017b61  mov     [rbx+238h], r14
0x180017b68  mov     rax, rbx
0x180017b6b  mov     rcx, [rsp+498h+var_38]
0x180017b73  xor     rcx, rsp; StackCookie
0x180017b76  call    __security_check_cookie
0x180017b7b  lea     r11, [rsp+498h+var_28]
0x180017b83  mov     rbx, [r11+40h]
0x180017b87  mov     rbp, [r11+48h]
0x180017b8b  mov     rsp, r11
0x180017b8e  pop     r15
0x180017b90  pop     r14
0x180017b92  pop     r12
0x180017b94  pop     rdi
0x180017b95  pop     rsi
0x180017b96  retn
```
