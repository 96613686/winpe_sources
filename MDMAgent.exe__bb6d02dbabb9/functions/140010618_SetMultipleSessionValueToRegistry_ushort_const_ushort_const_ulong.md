# SetMultipleSessionValueToRegistry(ushort const *,ushort const *,ulong)

- ea: `0x140010618`
- end: `0x14001070f`
- name: `?SetMultipleSessionValueToRegistry@@YAJPEBG0K@Z`
- size: `247`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValueName, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400112b0`

## callees

- `0x1400029c0`
- `0x1400074ec`
- `0x1400075e4`
- `0x14000b7c0`
- `0x140010618`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400106db`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400106db`

## pseudocode

```c
LSTATUS __fastcall SetMultipleSessionValueToRegistry(const unsigned __int16 *a1, LPCWSTR lpValueName, int a3)
{
  const unsigned __int16 *v5; // rax
  LSTATUS result; // eax
  _DWORD Data[4]; // [rsp+30h] [rbp-F8h] BYREF
  WCHAR SubKey[96]; // [rsp+40h] [rbp-E8h] BYREF

  Data[0] = a3;
  v5 = DMGetNonVolatileRegPrefix();
  result = StringCchCopyW(SubKey, 0x60u, v5);
  if ( result >= 0 )
  {
    result = StringCchCatW(SubKey, 0x60u, c_szEnrollmentsDB);
    if ( result >= 0 )
    {
      result = StringCchCatW(SubKey, 0x60u, a1);
      if ( result >= 0 )
      {
        result = StringCchCatW(SubKey, 0x60u, L"\\");
        if ( result >= 0 )
        {
          result = StringCchCatW(SubKey, 0x60u, c_szEnrollmentsDBMultipleSession);
          if ( result >= 0 )
          {
            result = RegSetKeyValueW(HKEY_LOCAL_MACHINE, SubKey, lpValueName, 4u, Data, 4u);
            if ( result > 0 )
              return (unsigned __int16)result | 0x80070000;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140010618  push    rbx
0x14001061a  push    rsi
0x14001061b  push    rdi
0x14001061c  sub     rsp, 110h
0x140010623  mov     rax, cs:__security_cookie
0x14001062a  xor     rax, rsp
0x14001062d  mov     [rsp+128h+var_28], rax
0x140010635  mov     rdi, rdx
0x140010638  mov     [rsp+128h+Data], r8d
0x14001063d  mov     rbx, rcx
0x140010640  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x140010645  mov     esi, 60h ; '`'
0x14001064a  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x14001064f  mov     edx, esi; unsigned __int64
0x140010651  mov     r8, rax; unsigned __int16 *
0x140010654  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140010659  test    eax, eax
0x14001065b  js      loc_1400106F3
0x140010661  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x140010668  mov     edx, esi; unsigned __int64
0x14001066a  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x14001066f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140010674  test    eax, eax
0x140010676  js      short loc_1400106F3
0x140010678  mov     r8, rbx; unsigned __int16 *
0x14001067b  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x140010680  mov     edx, esi; unsigned __int64
0x140010682  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140010687  test    eax, eax
0x140010689  js      short loc_1400106F3
0x14001068b  lea     r8, asc_14001C460; "\\"
0x140010692  mov     edx, esi; unsigned __int64
0x140010694  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x140010699  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001069e  test    eax, eax
0x1400106a0  js      short loc_1400106F3
0x1400106a2  lea     r8, ?c_szEnrollmentsDBMultipleSession@@3PAGA; "MultipleSession"
0x1400106a9  mov     edx, esi; unsigned __int64
0x1400106ab  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x1400106b0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400106b5  test    eax, eax
0x1400106b7  js      short loc_1400106F3
0x1400106b9  lea     r9d, [rsi-5Ch]; dwType
0x1400106bd  mov     r8, rdi; lpValueName
0x1400106c0  lea     rax, [rsp+128h+Data]
0x1400106c5  mov     [rsp+128h+cbData], r9d; cbData
0x1400106ca  lea     rdx, [rsp+128h+SubKey]; lpSubKey
0x1400106cf  mov     [rsp+128h+lpData], rax; lpData
0x1400106d4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400106db  call    cs:__imp_RegSetKeyValueW
0x1400106e2  nop     dword ptr [rax+rax+00h]
0x1400106e7  test    eax, eax
0x1400106e9  jle     short loc_1400106F3
0x1400106eb  movzx   eax, ax
0x1400106ee  or      eax, 80070000h
0x1400106f3  mov     rcx, [rsp+128h+var_28]
0x1400106fb  xor     rcx, rsp; StackCookie
0x1400106fe  call    __security_check_cookie
0x140010703  add     rsp, 110h
0x14001070a  pop     rdi
0x14001070b  pop     rsi
0x14001070c  pop     rbx
0x14001070d  retn
```
