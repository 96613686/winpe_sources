# RegHelper::WriteQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64)

- ea: `0x18002d7ec`
- end: `0x18002d885`
- name: `?WriteQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBG_K@Z`
- size: `153`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800209a8`
- `0x180021898`
- `0x1800219d4`

## callees

- `0x18000ee1c`
- `0x1800161e0`
- `0x18002d7ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d85a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d85a`

## pseudocode

```c
__int64 __fastcall RegHelper::WriteQWORDValue(__int64 a1, const WCHAR *a2, __int64 a3)
{
  unsigned int v5; // ebx
  HKEY hKey[5]; // [rsp+30h] [rbp-28h] BYREF
  __int64 Data; // [rsp+78h] [rbp+20h] BYREF

  memset(hKey, 0, 24);
  v5 = ATL::CRegKey::Open(
         (ATL::CRegKey *)hKey,
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSATAPI",
         2u);
  if ( !v5 )
  {
    Data = a3;
    v5 = RegSetValueExW(hKey[0], a2, 0, 0xBu, (const BYTE *)&Data, 8u);
  }
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return v5;
}

```

## disassembly

```asm
0x18002d7ec  mov     rax, rsp
0x18002d7ef  mov     [rax+8], rbx
0x18002d7f3  mov     [rax+10h], rsi
0x18002d7f7  push    rdi
0x18002d7f8  sub     rsp, 50h
0x18002d7fc  and     qword ptr [rax-28h], 0
0x18002d801  lea     rcx, [rax-28h]; this
0x18002d805  and     qword ptr [rax-20h], 0
0x18002d80a  mov     rdi, r8
0x18002d80d  and     qword ptr [rax-18h], 0
0x18002d812  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002d819  mov     rsi, rdx
0x18002d81c  mov     r9d, 2; unsigned int
0x18002d822  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002d829  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002d82e  mov     ebx, eax
0x18002d830  test    eax, eax
0x18002d832  jnz     short loc_18002D868
0x18002d834  mov     rcx, [rsp+58h+hKey]; hKey
0x18002d839  lea     rax, [rsp+58h+Data]
0x18002d83e  mov     [rsp+58h+cbData], 8; cbData
0x18002d846  lea     r9d, [rbx+0Bh]; dwType
0x18002d84a  xor     r8d, r8d; Reserved
0x18002d84d  mov     [rsp+58h+lpData], rax; lpData
0x18002d852  mov     rdx, rsi; lpValueName
0x18002d855  mov     [rsp+58h+Data], rdi
0x18002d85a  call    cs:__imp_RegSetValueExW
0x18002d861  nop     dword ptr [rax+rax+00h]
0x18002d866  mov     ebx, eax
0x18002d868  lea     rcx, [rsp+58h+hKey]; this
0x18002d86d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002d872  mov     rsi, [rsp+58h+arg_8]
0x18002d877  mov     eax, ebx
0x18002d879  mov     rbx, [rsp+58h+arg_0]
0x18002d87e  add     rsp, 50h
0x18002d882  pop     rdi
0x18002d883  retn
```
