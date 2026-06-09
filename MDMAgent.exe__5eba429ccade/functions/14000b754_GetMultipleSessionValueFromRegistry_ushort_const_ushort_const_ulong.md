# GetMultipleSessionValueFromRegistry(ushort const *,ushort const *,ulong *)

- ea: `0x14000b754`
- end: `0x14000b88d`
- name: `?GetMultipleSessionValueFromRegistry@@YAJPEBG0PEAK@Z`
- size: `313`
- prototype: `signed int __fastcall(const unsigned __int16 *, LPCWSTR lpValue, unsigned int *)`
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
- `0x14000b754`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000b856`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000b856`

## pseudocode

```c
signed int __fastcall GetMultipleSessionValueFromRegistry(
        const unsigned __int16 *a1,
        LPCWSTR lpValue,
        unsigned int *a3)
{
  LSTATUS ValueW; // ecx
  const unsigned __int16 *v7; // rax
  signed int result; // eax
  unsigned int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pdwType; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[96]; // [rsp+50h] [rbp-B0h] BYREF

  pcbData = 4;
  ValueW = 0;
  pdwType = 0;
  pvData = 0;
  if ( !lpValue || !a3 )
    return ValueW;
  v7 = DMGetNonVolatileRegPrefix();
  result = StringCchCopyW(SubKey, 0x60u, v7);
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
            ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, lpValue, 0x10u, &pdwType, &pvData, &pcbData);
            *a3 = pvData;
            if ( ValueW > 0 )
              return (unsigned __int16)ValueW | 0x80070000;
            return ValueW;
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
0x14000b754  push    rbp
0x14000b756  push    rbx
0x14000b757  push    rsi
0x14000b758  push    rdi
0x14000b759  push    r14
0x14000b75b  lea     rbp, [rsp-20h]
0x14000b760  sub     rsp, 120h
0x14000b767  mov     rax, cs:__security_cookie
0x14000b76e  xor     rax, rsp
0x14000b771  mov     [rbp+40h+var_30], rax
0x14000b775  mov     rdi, rcx
0x14000b778  mov     [rsp+140h+var_FC], 4
0x14000b780  xor     ecx, ecx
0x14000b782  mov     rbx, r8
0x14000b785  mov     [rsp+140h+var_F8], ecx
0x14000b789  mov     rsi, rdx
0x14000b78c  mov     [rsp+140h+var_100], ecx
0x14000b790  test    rdx, rdx
0x14000b793  jz      loc_14000B871
0x14000b799  test    rbx, rbx
0x14000b79c  jz      loc_14000B871
0x14000b7a2  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x14000b7a7  mov     r14d, 60h ; '`'
0x14000b7ad  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x14000b7b2  mov     edx, r14d; unsigned __int64
0x14000b7b5  mov     r8, rax; unsigned __int16 *
0x14000b7b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000b7bd  test    eax, eax
0x14000b7bf  js      loc_14000B873
0x14000b7c5  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x14000b7cc  mov     edx, r14d; unsigned __int64
0x14000b7cf  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x14000b7d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b7d9  test    eax, eax
0x14000b7db  js      loc_14000B873
0x14000b7e1  mov     r8, rdi; unsigned __int16 *
0x14000b7e4  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x14000b7e9  mov     edx, r14d; unsigned __int64
0x14000b7ec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b7f1  test    eax, eax
0x14000b7f3  js      short loc_14000B873
0x14000b7f5  lea     r8, asc_14001B460; "\\"
0x14000b7fc  mov     edx, r14d; unsigned __int64
0x14000b7ff  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x14000b804  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b809  test    eax, eax
0x14000b80b  js      short loc_14000B873
0x14000b80d  lea     r8, ?c_szEnrollmentsDBMultipleSession@@3PAGA; "MultipleSession"
0x14000b814  mov     edx, r14d; unsigned __int64
0x14000b817  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x14000b81c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b821  test    eax, eax
0x14000b823  js      short loc_14000B873
0x14000b825  lea     rax, [rsp+140h+var_FC]
0x14000b82a  mov     r8, rsi; lpValue
0x14000b82d  mov     [rsp+140h+pcbData], rax; pcbData
0x14000b832  lea     r9d, [r14-50h]; dwFlags
0x14000b836  lea     rax, [rsp+140h+var_100]
0x14000b83b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14000b842  mov     [rsp+140h+pvData], rax; pvData
0x14000b847  lea     rdx, [rsp+140h+SubKey]; lpSubKey
0x14000b84c  lea     rax, [rsp+140h+var_F8]
0x14000b851  mov     [rsp+140h+pdwType], rax; pdwType
0x14000b856  call    cs:__imp_RegGetValueW
0x14000b85c  mov     ecx, eax
0x14000b85e  mov     eax, [rsp+140h+var_100]
0x14000b862  mov     [rbx], eax
0x14000b864  test    ecx, ecx
0x14000b866  jle     short loc_14000B871
0x14000b868  movzx   ecx, cx
0x14000b86b  or      ecx, 80070000h
0x14000b871  mov     eax, ecx
0x14000b873  mov     rcx, [rbp+40h+var_30]
0x14000b877  xor     rcx, rsp; StackCookie
0x14000b87a  call    __security_check_cookie
0x14000b87f  add     rsp, 120h
0x14000b886  pop     r14
0x14000b888  pop     rdi
0x14000b889  pop     rsi
0x14000b88a  pop     rbx
0x14000b88b  pop     rbp
0x14000b88c  retn
```
