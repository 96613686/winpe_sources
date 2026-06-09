# ClassFactory::UnregisterCoClass(ushort const *,_GUID const *)

- ea: `0x180010bc8`
- end: `0x180010d64`
- name: `?UnregisterCoClass@ClassFactory@@CAJPEBGPEBU_GUID@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, UUID *Uuid)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003270`

## callees

- `0x18000a640`
- `0x18000a690`
- `0x1800104b0`
- `0x180010bc8`
- `0x180011840`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180010d25`
- `RPCRT4!RpcStringFreeW` at `0x180010d25`
- `RPCRT4!UuidToStringW` at `0x180010c48`
- `RPCRT4!UuidToStringW` at `0x180010c48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010cd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010cd2`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180010cab`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180010ce6`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180010cab`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180010ce6`

## string_xrefs

- `0x180010cc8`: `CLSID`

## pseudocode

```c
__int64 __fastcall ClassFactory::UnregisterCoClass(LPCWSTR lpSubKey, UUID *Uuid)
{
  int v3; // ebx
  const unsigned __int16 *v4; // rdx
  __int64 v5; // r8
  LSTATUS v6; // eax
  bool v7; // cc
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v11[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+44h] [rbp-BCh]
  LPCWSTR lpSubKeya; // [rsp+48h] [rbp-B8h]
  int v14; // [rsp+50h] [rbp-B0h]
  __int16 v15; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  lpSubKeya = (LPCWSTR)&v15;
  StringUuid = 0;
  v11[2] = 0;
  v12 = 512;
  v14 = 0;
  v15 = 0;
  if ( lpSubKey )
  {
    v3 = UuidToStringW(Uuid, &StringUuid);
    if ( !v3 )
    {
      v3 = STRU::Copy((STRU *)v11, v4, v5);
      if ( v3 >= 0 )
      {
        v3 = STRU::Append((STRU *)v11, StringUuid, 0);
        if ( v3 >= 0 )
        {
          v3 = STRU::Append((STRU *)v11, L"}", 0);
          if ( v3 >= 0 )
          {
            v6 = RegDeleteKeyW(HKEY_CLASSES_ROOT, lpSubKey);
            v7 = v6 <= 0;
            if ( v6
              || (v6 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0xF003Fu, &hKey), v7 = v6 <= 0, v6)
              || (v6 = RegDeleteKeyW(hKey, lpSubKeya), v7 = v6 <= 0, v6) )
            {
              if ( v7 )
                v3 = v6;
              else
                v3 = (unsigned __int16)v6 | 0x80070000;
            }
          }
        }
      }
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    if ( StringUuid )
    {
      RpcStringFreeW(&StringUuid);
      StringUuid = 0;
    }
  }
  else
  {
    v3 = -2147024809;
  }
  BUFFER::~BUFFER((BUFFER *)v11);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180010bc8  mov     [rsp-8+arg_10], rbx
0x180010bcd  mov     [rsp-8+arg_18], rdi
0x180010bd2  push    rbp
0x180010bd3  lea     rbp, [rsp-170h]
0x180010bdb  sub     rsp, 270h
0x180010be2  mov     rax, cs:__security_cookie
0x180010be9  xor     rax, rsp
0x180010bec  mov     [rbp+170h+var_10], rax
0x180010bf3  lea     rax, [rsp+270h+var_210]
0x180010bf8  mov     [rsp+270h+hKey], 0
0x180010c01  mov     [rsp+270h+lpSubKey], rax
0x180010c06  mov     r8, rdx
0x180010c09  xor     eax, eax
0x180010c0b  mov     [rsp+270h+StringUuid], 0
0x180010c14  mov     [rsp+270h+var_22E], 0
0x180010c19  mov     rdi, rcx
0x180010c1c  mov     [rsp+270h+var_22C], 200h
0x180010c24  mov     [rsp+270h+var_220], 0
0x180010c2c  mov     [rsp+270h+var_210], ax
0x180010c31  test    rcx, rcx
0x180010c34  jnz     short loc_180010C40
0x180010c36  mov     ebx, 80070057h
0x180010c3b  jmp     loc_180010D34
0x180010c40  lea     rdx, [rsp+270h+StringUuid]; StringUuid
0x180010c45  mov     rcx, r8; Uuid
0x180010c48  call    cs:__imp_UuidToStringW
0x180010c4e  mov     ebx, eax
0x180010c50  test    eax, eax
0x180010c52  jnz     loc_180010CFF
0x180010c58  lea     rcx, [rsp+270h+var_230]; this
0x180010c5d  call    ?Copy@STRU@@QEAAJPEBGKK@Z; STRU::Copy(ushort const *,ulong,ulong)
0x180010c62  mov     ebx, eax
0x180010c64  test    eax, eax
0x180010c66  js      loc_180010CFF
0x180010c6c  mov     rdx, [rsp+270h+StringUuid]; unsigned __int16 *
0x180010c71  lea     rcx, [rsp+270h+var_230]; this
0x180010c76  xor     r8d, r8d; unsigned int
0x180010c79  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x180010c7e  mov     ebx, eax
0x180010c80  test    eax, eax
0x180010c82  js      short loc_180010CFF
0x180010c84  xor     r8d, r8d; unsigned int
0x180010c87  lea     rdx, asc_18001726C; "}"
0x180010c8e  lea     rcx, [rsp+270h+var_230]; this
0x180010c93  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x180010c98  mov     ebx, eax
0x180010c9a  test    eax, eax
0x180010c9c  js      short loc_180010CFF
0x180010c9e  mov     rdx, rdi; lpSubKey
0x180010ca1  mov     rdi, 0FFFFFFFF80000000h
0x180010ca8  mov     rcx, rdi; hKey
0x180010cab  call    cs:__imp_RegDeleteKeyW
0x180010cb1  test    eax, eax
0x180010cb3  jnz     short loc_180010CF0
0x180010cb5  lea     rax, [rsp+270h+hKey]
0x180010cba  mov     r9d, 0F003Fh; samDesired
0x180010cc0  xor     r8d, r8d; ulOptions
0x180010cc3  mov     [rsp+270h+phkResult], rax; phkResult
0x180010cc8  lea     rdx, SubKey; "CLSID"
0x180010ccf  mov     rcx, rdi; hKey
0x180010cd2  call    cs:__imp_RegOpenKeyExW
0x180010cd8  test    eax, eax
0x180010cda  jnz     short loc_180010CF0
0x180010cdc  mov     rdx, [rsp+270h+lpSubKey]; lpSubKey
0x180010ce1  mov     rcx, [rsp+270h+hKey]; hKey
0x180010ce6  call    cs:__imp_RegDeleteKeyW
0x180010cec  test    eax, eax
0x180010cee  jz      short loc_180010CFF
0x180010cf0  jg      short loc_180010CF6
0x180010cf2  mov     ebx, eax
0x180010cf4  jmp     short loc_180010CFF
0x180010cf6  movzx   ebx, ax
0x180010cf9  or      ebx, 80070000h
0x180010cff  mov     rcx, [rsp+270h+hKey]; hKey
0x180010d04  test    rcx, rcx
0x180010d07  jz      short loc_180010D18
0x180010d09  call    cs:__imp_RegCloseKey
0x180010d0f  mov     [rsp+270h+hKey], 0
0x180010d18  cmp     [rsp+270h+StringUuid], 0
0x180010d1e  jz      short loc_180010D34
0x180010d20  lea     rcx, [rsp+270h+StringUuid]; String
0x180010d25  call    cs:__imp_RpcStringFreeW
0x180010d2b  mov     [rsp+270h+StringUuid], 0
0x180010d34  lea     rcx, [rsp+270h+var_230]; this
0x180010d39  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010d3e  mov     eax, ebx
0x180010d40  mov     rcx, [rbp+170h+var_10]
0x180010d47  xor     rcx, rsp; StackCookie
0x180010d4a  call    __security_check_cookie
0x180010d4f  lea     r11, [rsp+270h+var_s0]
0x180010d57  mov     rbx, [r11+20h]
0x180010d5b  mov     rdi, [r11+28h]
0x180010d5f  mov     rsp, r11
0x180010d62  pop     rbp
0x180010d63  retn
```
