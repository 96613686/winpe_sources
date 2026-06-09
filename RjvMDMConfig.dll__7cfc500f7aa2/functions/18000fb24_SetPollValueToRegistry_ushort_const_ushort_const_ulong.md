# SetPollValueToRegistry(ushort const *,ushort const *,ulong)

- ea: `0x18000fb24`
- end: `0x18000fc1b`
- name: `?SetPollValueToRegistry@@YAJPEBG0K@Z`
- size: `247`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValueName, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180010340`

## callees

- `0x180001c60`
- `0x180009e40`
- `0x18000fb24`
- `0x18000ff18`
- `0x18000ff80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000fbe7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000fbe7`

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
0x18000fb24  push    rbx
0x18000fb26  push    rsi
0x18000fb27  push    rdi
0x18000fb28  sub     rsp, 100h
0x18000fb2f  mov     rax, cs:__security_cookie
0x18000fb36  xor     rax, rsp
0x18000fb39  mov     [rsp+118h+var_28], rax
0x18000fb41  mov     rdi, rdx
0x18000fb44  mov     [rsp+118h+Data], r8d
0x18000fb49  mov     rbx, rcx
0x18000fb4c  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x18000fb51  mov     esi, 55h ; 'U'
0x18000fb56  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x18000fb5b  mov     edx, esi; unsigned __int64
0x18000fb5d  mov     r8, rax; unsigned __int16 *
0x18000fb60  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fb65  test    eax, eax
0x18000fb67  js      loc_18000FBFF
0x18000fb6d  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x18000fb74  mov     edx, esi; unsigned __int64
0x18000fb76  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x18000fb7b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fb80  test    eax, eax
0x18000fb82  js      short loc_18000FBFF
0x18000fb84  mov     r8, rbx; unsigned __int16 *
0x18000fb87  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x18000fb8c  mov     edx, esi; unsigned __int64
0x18000fb8e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fb93  test    eax, eax
0x18000fb95  js      short loc_18000FBFF
0x18000fb97  lea     r8, asc_180020DAC; "\\"
0x18000fb9e  mov     edx, esi; unsigned __int64
0x18000fba0  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x18000fba5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fbaa  test    eax, eax
0x18000fbac  js      short loc_18000FBFF
0x18000fbae  lea     r8, ?c_szEnrollmentsDBPoll@@3PAGA; "Poll"
0x18000fbb5  mov     edx, esi; unsigned __int64
0x18000fbb7  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x18000fbbc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fbc1  test    eax, eax
0x18000fbc3  js      short loc_18000FBFF
0x18000fbc5  lea     r9d, [rsi-51h]; dwType
0x18000fbc9  mov     r8, rdi; lpValueName
0x18000fbcc  lea     rax, [rsp+118h+Data]
0x18000fbd1  mov     [rsp+118h+cbData], r9d; cbData
0x18000fbd6  lea     rdx, [rsp+118h+SubKey]; lpSubKey
0x18000fbdb  mov     [rsp+118h+lpData], rax; lpData
0x18000fbe0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fbe7  call    cs:__imp_RegSetKeyValueW
0x18000fbee  nop     dword ptr [rax+rax+00h]
0x18000fbf3  test    eax, eax
0x18000fbf5  jle     short loc_18000FBFF
0x18000fbf7  movzx   eax, ax
0x18000fbfa  or      eax, 80070000h
0x18000fbff  mov     rcx, [rsp+118h+var_28]
0x18000fc07  xor     rcx, rsp; StackCookie
0x18000fc0a  call    __security_check_cookie
0x18000fc0f  add     rsp, 100h
0x18000fc16  pop     rdi
0x18000fc17  pop     rsi
0x18000fc18  pop     rbx
0x18000fc19  retn
```
