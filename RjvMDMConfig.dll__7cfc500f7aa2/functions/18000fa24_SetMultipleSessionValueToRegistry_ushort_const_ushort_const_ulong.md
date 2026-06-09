# SetMultipleSessionValueToRegistry(ushort const *,ushort const *,ulong)

- ea: `0x18000fa24`
- end: `0x18000fb1b`
- name: `?SetMultipleSessionValueToRegistry@@YAJPEBG0K@Z`
- size: `247`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValueName, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180010804`

## callees

- `0x180001c60`
- `0x180009e40`
- `0x18000fa24`
- `0x18000ff18`
- `0x18000ff80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000fae7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000fae7`

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
0x18000fa24  push    rbx
0x18000fa26  push    rsi
0x18000fa27  push    rdi
0x18000fa28  sub     rsp, 110h
0x18000fa2f  mov     rax, cs:__security_cookie
0x18000fa36  xor     rax, rsp
0x18000fa39  mov     [rsp+128h+var_28], rax
0x18000fa41  mov     rdi, rdx
0x18000fa44  mov     [rsp+128h+Data], r8d
0x18000fa49  mov     rbx, rcx
0x18000fa4c  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x18000fa51  mov     esi, 60h ; '`'
0x18000fa56  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x18000fa5b  mov     edx, esi; unsigned __int64
0x18000fa5d  mov     r8, rax; unsigned __int16 *
0x18000fa60  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fa65  test    eax, eax
0x18000fa67  js      loc_18000FAFF
0x18000fa6d  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x18000fa74  mov     edx, esi; unsigned __int64
0x18000fa76  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x18000fa7b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fa80  test    eax, eax
0x18000fa82  js      short loc_18000FAFF
0x18000fa84  mov     r8, rbx; unsigned __int16 *
0x18000fa87  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x18000fa8c  mov     edx, esi; unsigned __int64
0x18000fa8e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fa93  test    eax, eax
0x18000fa95  js      short loc_18000FAFF
0x18000fa97  lea     r8, asc_180020DAC; "\\"
0x18000fa9e  mov     edx, esi; unsigned __int64
0x18000faa0  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x18000faa5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000faaa  test    eax, eax
0x18000faac  js      short loc_18000FAFF
0x18000faae  lea     r8, ?c_szEnrollmentsDBMultipleSession@@3PAGA; "MultipleSession"
0x18000fab5  mov     edx, esi; unsigned __int64
0x18000fab7  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x18000fabc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fac1  test    eax, eax
0x18000fac3  js      short loc_18000FAFF
0x18000fac5  lea     r9d, [rsi-5Ch]; dwType
0x18000fac9  mov     r8, rdi; lpValueName
0x18000facc  lea     rax, [rsp+128h+Data]
0x18000fad1  mov     [rsp+128h+cbData], r9d; cbData
0x18000fad6  lea     rdx, [rsp+128h+SubKey]; lpSubKey
0x18000fadb  mov     [rsp+128h+lpData], rax; lpData
0x18000fae0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fae7  call    cs:__imp_RegSetKeyValueW
0x18000faee  nop     dword ptr [rax+rax+00h]
0x18000faf3  test    eax, eax
0x18000faf5  jle     short loc_18000FAFF
0x18000faf7  movzx   eax, ax
0x18000fafa  or      eax, 80070000h
0x18000faff  mov     rcx, [rsp+128h+var_28]
0x18000fb07  xor     rcx, rsp; StackCookie
0x18000fb0a  call    __security_check_cookie
0x18000fb0f  add     rsp, 110h
0x18000fb16  pop     rdi
0x18000fb17  pop     rsi
0x18000fb18  pop     rbx
0x18000fb19  retn
```
