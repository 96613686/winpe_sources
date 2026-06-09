# Wallet::WalletDatabaseESE::SetCorruptionRegKey(int)

- ea: `0x180011f20`
- end: `0x180011fc3`
- name: `?SetCorruptionRegKey@WalletDatabaseESE@Wallet@@CAJH@Z`
- size: `163`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fab0`
- `0x18000fe14`

## callees

- `0x18000de7c`
- `0x18001108c`
- `0x180011f20`
- `0x18001248c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f63`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180011fbb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180011fbb`

## pseudocode

```c
__int64 __fastcall Wallet::WalletDatabaseESE::SetCorruptionRegKey(int a1)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  HKEY hKey[5]; // [rsp+20h] [rbp-28h] BYREF

  memset(hKey, 0, 24);
  if ( (unsigned int)ATL::CRegKey::Open(hKey, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Wallet", 0x2001Fu)
    || (!a1
      ? (v4 = RegDeleteValueW(hKey[0], L"DatabaseCorrupt"))
      : (v4 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"DatabaseCorrupt", 1u)),
        v4) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v3 = -2143748092;
    }
  }
  else
  {
    v3 = 0;
  }
  ATL::CRegKey::Close(hKey);
  return v3;
}

```

## disassembly

```asm
0x180011f20  mov     rax, rsp
0x180011f23  push    rbx
0x180011f24  sub     rsp, 40h
0x180011f28  mov     ebx, ecx
0x180011f2a  mov     qword ptr [rax-28h], 0
0x180011f32  lea     rcx, [rax-28h]; this
0x180011f36  mov     qword ptr [rax-20h], 0
0x180011f3e  mov     r9d, 2001Fh; unsigned int
0x180011f44  mov     qword ptr [rax-18h], 0
0x180011f4c  lea     r8, ?sc_szWalletRegKey@WalletDatabaseESE@Wallet@@0QBGB; "Software\\Microsoft\\Wallet"
0x180011f53  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180011f5a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180011f5f  test    eax, eax
0x180011f61  jz      short loc_180011F83
0x180011f63  call    cs:__imp_GetLastError
0x180011f69  mov     ebx, eax
0x180011f6b  test    eax, eax
0x180011f6d  jz      short loc_180011F7C
0x180011f6f  jle     short loc_180011FA4
0x180011f71  movzx   ebx, ax
0x180011f74  or      ebx, 80070000h
0x180011f7a  jmp     short loc_180011FA4
0x180011f7c  mov     ebx, 80390004h
0x180011f81  jmp     short loc_180011FA4
0x180011f83  lea     rdx, ?sc_szDatabaseCorruptRegValue@WalletDatabaseESE@Wallet@@0QBGB; "DatabaseCorrupt"
0x180011f8a  test    ebx, ebx
0x180011f8c  jz      short loc_180011FB6
0x180011f8e  mov     r8d, 1; unsigned int
0x180011f94  lea     rcx, [rsp+48h+hKey]; this
0x180011f99  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180011f9e  test    eax, eax
0x180011fa0  jnz     short loc_180011F63
0x180011fa2  xor     ebx, ebx
0x180011fa4  lea     rcx, [rsp+48h+hKey]; this
0x180011fa9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180011fae  mov     eax, ebx
0x180011fb0  add     rsp, 40h
0x180011fb4  pop     rbx
0x180011fb5  retn
0x180011fb6  mov     rcx, [rsp+48h+hKey]; hKey
0x180011fbb  call    cs:__imp_RegDeleteValueW
0x180011fc1  jmp     short loc_180011F9E
```
