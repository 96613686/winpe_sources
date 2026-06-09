# ClassFactory::UnregisterCoClass(ushort const *,_GUID const *)

- ea: `0x180012458`
- end: `0x1800125ff`
- name: `?UnregisterCoClass@ClassFactory@@CAJPEBGPEBU_GUID@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, UUID *Uuid)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f910`

## callees

- `0x1800021e0`
- `0x18000ab38`
- `0x180010144`
- `0x180012458`
- `0x1800130a0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800125a3`
- `ADVAPI32!RegCloseKey` at `0x1800125a3`
- `ADVAPI32!RegOpenKeyExW` at `0x18001256c`
- `ADVAPI32!RegOpenKeyExW` at `0x18001256c`
- `ADVAPI32!RegDeleteKeyW` at `0x180012545`
- `ADVAPI32!RegDeleteKeyW` at `0x180012580`
- `ADVAPI32!RegDeleteKeyW` at `0x180012545`
- `ADVAPI32!RegDeleteKeyW` at `0x180012580`
- `RPCRT4!RpcStringFreeW` at `0x1800125bf`
- `RPCRT4!RpcStringFreeW` at `0x1800125bf`
- `RPCRT4!UuidToStringW` at `0x1800124d8`
- `RPCRT4!UuidToStringW` at `0x1800124d8`

## string_xrefs

- `0x180012562`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClassFactory::UnregisterCoClass(LPCWSTR lpSubKey, UUID *Uuid)
{
  int v3; // ebx
  unsigned int v4; // r9d
  unsigned int v5; // r9d
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
  StringUuid = 0;
  v11[2] = 0;
  v12 = 512;
  lpSubKeya = (LPCWSTR)&v15;
  v14 = 0;
  v15 = 0;
  if ( lpSubKey )
  {
    v3 = UuidToStringW(Uuid, &StringUuid);
    if ( !v3 )
    {
      v3 = STRU::Copy((STRU *)v11, L"{", 0);
      if ( v3 >= 0 )
      {
        v3 = STRU::Append((STRU *)v11, StringUuid, 0, v4);
        if ( v3 >= 0 )
        {
          v3 = STRU::Append((STRU *)v11, L"}", 0, v5);
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
0x180012458  mov     [rsp-8+arg_10], rbx
0x18001245d  mov     [rsp-8+arg_18], rdi
0x180012462  push    rbp
0x180012463  lea     rbp, [rsp-170h]
0x18001246b  sub     rsp, 270h
0x180012472  mov     rax, cs:__security_cookie
0x180012479  xor     rax, rsp
0x18001247c  mov     [rbp+170h+var_10], rax
0x180012483  mov     r8, rdx
0x180012486  mov     rdi, rcx
0x180012489  mov     [rsp+270h+hKey], 0
0x180012492  mov     [rsp+270h+StringUuid], 0
0x18001249b  mov     [rsp+270h+var_22E], 0
0x1800124a0  mov     [rsp+270h+var_22C], 200h
0x1800124a8  lea     rax, [rsp+270h+var_210]
0x1800124ad  mov     [rsp+270h+lpSubKey], rax
0x1800124b2  mov     [rsp+270h+var_220], 0
0x1800124ba  xor     eax, eax
0x1800124bc  mov     [rsp+270h+var_210], ax
0x1800124c1  test    rcx, rcx
0x1800124c4  jnz     short loc_1800124D0
0x1800124c6  mov     ebx, 80070057h
0x1800124cb  jmp     loc_1800125CE
0x1800124d0  lea     rdx, [rsp+270h+StringUuid]; StringUuid
0x1800124d5  mov     rcx, r8; Uuid
0x1800124d8  call    cs:__imp_UuidToStringW
0x1800124de  mov     ebx, eax
0x1800124e0  test    eax, eax
0x1800124e2  jnz     loc_180012599
0x1800124e8  xor     r8d, r8d; unsigned int
0x1800124eb  lea     rdx, asc_180018CD8; "{"
0x1800124f2  lea     rcx, [rsp+270h+var_230]; this
0x1800124f7  call    ?Copy@STRU@@QEAAJPEBGKK@Z; STRU::Copy(ushort const *,ulong,ulong)
0x1800124fc  mov     ebx, eax
0x1800124fe  test    eax, eax
0x180012500  js      loc_180012599
0x180012506  xor     r8d, r8d; unsigned int
0x180012509  mov     rdx, [rsp+270h+StringUuid]; unsigned __int16 *
0x18001250e  lea     rcx, [rsp+270h+var_230]; this
0x180012513  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x180012518  mov     ebx, eax
0x18001251a  test    eax, eax
0x18001251c  js      short loc_180012599
0x18001251e  xor     r8d, r8d; unsigned int
0x180012521  lea     rdx, asc_180018CDC; "}"
0x180012528  lea     rcx, [rsp+270h+var_230]; this
0x18001252d  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x180012532  mov     ebx, eax
0x180012534  test    eax, eax
0x180012536  js      short loc_180012599
0x180012538  mov     rdx, rdi; lpSubKey
0x18001253b  mov     rdi, 0FFFFFFFF80000000h
0x180012542  mov     rcx, rdi; hKey
0x180012545  call    cs:__imp_RegDeleteKeyW
0x18001254b  test    eax, eax
0x18001254d  jnz     short loc_18001258A
0x18001254f  lea     rax, [rsp+270h+hKey]
0x180012554  mov     [rsp+270h+phkResult], rax; phkResult
0x180012559  mov     r9d, 0F003Fh; samDesired
0x18001255f  xor     r8d, r8d; ulOptions
0x180012562  lea     rdx, SubKey; "CLSID"
0x180012569  mov     rcx, rdi; hKey
0x18001256c  call    cs:__imp_RegOpenKeyExW
0x180012572  test    eax, eax
0x180012574  jnz     short loc_18001258A
0x180012576  mov     rdx, [rsp+270h+lpSubKey]; lpSubKey
0x18001257b  mov     rcx, [rsp+270h+hKey]; hKey
0x180012580  call    cs:__imp_RegDeleteKeyW
0x180012586  test    eax, eax
0x180012588  jz      short loc_180012599
0x18001258a  jg      short loc_180012590
0x18001258c  mov     ebx, eax
0x18001258e  jmp     short loc_180012599
0x180012590  movzx   ebx, ax
0x180012593  or      ebx, 80070000h
0x180012599  mov     rcx, [rsp+270h+hKey]; hKey
0x18001259e  test    rcx, rcx
0x1800125a1  jz      short loc_1800125B2
0x1800125a3  call    cs:__imp_RegCloseKey
0x1800125a9  mov     [rsp+270h+hKey], 0
0x1800125b2  cmp     [rsp+270h+StringUuid], 0
0x1800125b8  jz      short loc_1800125CE
0x1800125ba  lea     rcx, [rsp+270h+StringUuid]; String
0x1800125bf  call    cs:__imp_RpcStringFreeW
0x1800125c5  mov     [rsp+270h+StringUuid], 0
0x1800125ce  lea     rcx, [rsp+270h+var_230]; this
0x1800125d3  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800125d8  nop
0x1800125d9  mov     eax, ebx
0x1800125db  mov     rcx, [rbp+170h+var_10]
0x1800125e2  xor     rcx, rsp; StackCookie
0x1800125e5  call    __security_check_cookie
0x1800125ea  lea     r11, [rsp+270h+var_s0]
0x1800125f2  mov     rbx, [r11+20h]
0x1800125f6  mov     rdi, [r11+28h]
0x1800125fa  mov     rsp, r11
0x1800125fd  pop     rbp
0x1800125fe  retn
```
