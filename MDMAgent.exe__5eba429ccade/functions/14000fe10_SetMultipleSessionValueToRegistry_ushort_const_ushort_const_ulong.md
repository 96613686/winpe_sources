# SetMultipleSessionValueToRegistry(ushort const *,ushort const *,ulong)

- ea: `0x14000fe10`
- end: `0x14000ff00`
- name: `?SetMultipleSessionValueToRegistry@@YAJPEBG0K@Z`
- size: `240`
- prototype: `LSTATUS __fastcall(const unsigned __int16 *, LPCWSTR lpValueName, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140010a68`

## callees

- `0x140002930`
- `0x140007230`
- `0x140007324`
- `0x14000b2c0`
- `0x14000fe10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000fed3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000fed3`

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
0x14000fe10  push    rbx
0x14000fe12  push    rsi
0x14000fe13  push    rdi
0x14000fe14  sub     rsp, 110h
0x14000fe1b  mov     rax, cs:__security_cookie
0x14000fe22  xor     rax, rsp
0x14000fe25  mov     [rsp+128h+var_28], rax
0x14000fe2d  mov     rdi, rdx
0x14000fe30  mov     [rsp+128h+Data], r8d
0x14000fe35  mov     rbx, rcx
0x14000fe38  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x14000fe3d  mov     esi, 60h ; '`'
0x14000fe42  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x14000fe47  mov     edx, esi; unsigned __int64
0x14000fe49  mov     r8, rax; unsigned __int16 *
0x14000fe4c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000fe51  test    eax, eax
0x14000fe53  js      loc_14000FEE5
0x14000fe59  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x14000fe60  mov     edx, esi; unsigned __int64
0x14000fe62  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x14000fe67  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000fe6c  test    eax, eax
0x14000fe6e  js      short loc_14000FEE5
0x14000fe70  mov     r8, rbx; unsigned __int16 *
0x14000fe73  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x14000fe78  mov     edx, esi; unsigned __int64
0x14000fe7a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000fe7f  test    eax, eax
0x14000fe81  js      short loc_14000FEE5
0x14000fe83  lea     r8, asc_14001B460; "\\"
0x14000fe8a  mov     edx, esi; unsigned __int64
0x14000fe8c  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x14000fe91  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000fe96  test    eax, eax
0x14000fe98  js      short loc_14000FEE5
0x14000fe9a  lea     r8, ?c_szEnrollmentsDBMultipleSession@@3PAGA; "MultipleSession"
0x14000fea1  mov     edx, esi; unsigned __int64
0x14000fea3  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x14000fea8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000fead  test    eax, eax
0x14000feaf  js      short loc_14000FEE5
0x14000feb1  lea     r9d, [rsi-5Ch]; dwType
0x14000feb5  mov     r8, rdi; lpValueName
0x14000feb8  lea     rax, [rsp+128h+Data]
0x14000febd  mov     [rsp+128h+cbData], r9d; cbData
0x14000fec2  lea     rdx, [rsp+128h+SubKey]; lpSubKey
0x14000fec7  mov     [rsp+128h+lpData], rax; lpData
0x14000fecc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000fed3  call    cs:__imp_RegSetKeyValueW
0x14000fed9  test    eax, eax
0x14000fedb  jle     short loc_14000FEE5
0x14000fedd  movzx   eax, ax
0x14000fee0  or      eax, 80070000h
0x14000fee5  mov     rcx, [rsp+128h+var_28]
0x14000feed  xor     rcx, rsp; StackCookie
0x14000fef0  call    __security_check_cookie
0x14000fef5  add     rsp, 110h
0x14000fefc  pop     rdi
0x14000fefd  pop     rsi
0x14000fefe  pop     rbx
0x14000feff  retn
```
