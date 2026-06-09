# SetPollValueToRegistry(ushort const *,ushort const *,ulong)

- ea: `0x14000ff08`
- end: `0x14000fff8`
- name: `?SetPollValueToRegistry@@YAJPEBG0K@Z`
- size: `240`
- prototype: `LSTATUS __fastcall(const unsigned __int16 *, LPCWSTR lpValueName, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400104c0`

## callees

- `0x140002930`
- `0x140007230`
- `0x140007324`
- `0x14000b2c0`
- `0x14000ff08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000ffcb`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000ffcb`

## pseudocode

```c
LSTATUS __fastcall SetPollValueToRegistry(const unsigned __int16 *a1, LPCWSTR lpValueName, int a3)
{
  const unsigned __int16 *v5; // rax
  LSTATUS result; // eax
  _DWORD Data[4]; // [rsp+30h] [rbp-E8h] BYREF
  WCHAR SubKey[88]; // [rsp+40h] [rbp-D8h] BYREF

  Data[0] = a3;
  v5 = DMGetNonVolatileRegPrefix();
  result = StringCchCopyW(SubKey, 0x55u, v5);
  if ( result >= 0 )
  {
    result = StringCchCatW(SubKey, 0x55u, c_szEnrollmentsDB);
    if ( result >= 0 )
    {
      result = StringCchCatW(SubKey, 0x55u, a1);
      if ( result >= 0 )
      {
        result = StringCchCatW(SubKey, 0x55u, L"\\");
        if ( result >= 0 )
        {
          result = StringCchCatW(SubKey, 0x55u, c_szEnrollmentsDBPoll);
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
0x14000ff08  push    rbx
0x14000ff0a  push    rsi
0x14000ff0b  push    rdi
0x14000ff0c  sub     rsp, 100h
0x14000ff13  mov     rax, cs:__security_cookie
0x14000ff1a  xor     rax, rsp
0x14000ff1d  mov     [rsp+118h+var_28], rax
0x14000ff25  mov     rdi, rdx
0x14000ff28  mov     [rsp+118h+Data], r8d
0x14000ff2d  mov     rbx, rcx
0x14000ff30  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x14000ff35  mov     esi, 55h ; 'U'
0x14000ff3a  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x14000ff3f  mov     edx, esi; unsigned __int64
0x14000ff41  mov     r8, rax; unsigned __int16 *
0x14000ff44  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000ff49  test    eax, eax
0x14000ff4b  js      loc_14000FFDD
0x14000ff51  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x14000ff58  mov     edx, esi; unsigned __int64
0x14000ff5a  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x14000ff5f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000ff64  test    eax, eax
0x14000ff66  js      short loc_14000FFDD
0x14000ff68  mov     r8, rbx; unsigned __int16 *
0x14000ff6b  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x14000ff70  mov     edx, esi; unsigned __int64
0x14000ff72  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000ff77  test    eax, eax
0x14000ff79  js      short loc_14000FFDD
0x14000ff7b  lea     r8, asc_14001B460; "\\"
0x14000ff82  mov     edx, esi; unsigned __int64
0x14000ff84  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x14000ff89  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000ff8e  test    eax, eax
0x14000ff90  js      short loc_14000FFDD
0x14000ff92  lea     r8, ?c_szEnrollmentsDBPoll@@3PAGA; "Poll"
0x14000ff99  mov     edx, esi; unsigned __int64
0x14000ff9b  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x14000ffa0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000ffa5  test    eax, eax
0x14000ffa7  js      short loc_14000FFDD
0x14000ffa9  lea     r9d, [rsi-51h]; dwType
0x14000ffad  mov     r8, rdi; lpValueName
0x14000ffb0  lea     rax, [rsp+118h+Data]
0x14000ffb5  mov     [rsp+118h+cbData], r9d; cbData
0x14000ffba  lea     rdx, [rsp+118h+SubKey]; lpSubKey
0x14000ffbf  mov     [rsp+118h+lpData], rax; lpData
0x14000ffc4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000ffcb  call    cs:__imp_RegSetKeyValueW
0x14000ffd1  test    eax, eax
0x14000ffd3  jle     short loc_14000FFDD
0x14000ffd5  movzx   eax, ax
0x14000ffd8  or      eax, 80070000h
0x14000ffdd  mov     rcx, [rsp+118h+var_28]
0x14000ffe5  xor     rcx, rsp; StackCookie
0x14000ffe8  call    __security_check_cookie
0x14000ffed  add     rsp, 100h
0x14000fff4  pop     rdi
0x14000fff5  pop     rsi
0x14000fff6  pop     rbx
0x14000fff7  retn
```
