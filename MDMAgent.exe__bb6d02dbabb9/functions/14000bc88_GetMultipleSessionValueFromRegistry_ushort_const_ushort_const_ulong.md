# GetMultipleSessionValueFromRegistry(ushort const *,ushort const *,ulong *)

- ea: `0x14000bc88`
- end: `0x14000bdcc`
- name: `?GetMultipleSessionValueFromRegistry@@YAJPEBG0PEAK@Z`
- size: `324`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValue, unsigned int *)`
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
- `0x14000bc88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000bd8e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000bd8e`

## pseudocode

```c
signed int __fastcall GetMultipleSessionValueFromRegistry(
        const unsigned __int16 *a1,
        LPCWSTR lpValue,
        unsigned int *a3)
{
  LSTATUS ValueW; // ecx
  size_t *v7; // rax
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
  v7 = (size_t *)DMGetNonVolatileRegPrefix();
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
0x14000bc88  push    rbp
0x14000bc8a  push    rbx
0x14000bc8b  push    rsi
0x14000bc8c  push    rdi
0x14000bc8d  push    r14
0x14000bc8f  lea     rbp, [rsp-20h]
0x14000bc94  sub     rsp, 120h
0x14000bc9b  mov     rax, cs:__security_cookie
0x14000bca2  xor     rax, rsp
0x14000bca5  mov     [rbp+40h+var_30], rax
0x14000bca9  mov     rdi, rcx
0x14000bcac  mov     [rsp+140h+var_FC], 4
0x14000bcb4  xor     ecx, ecx
0x14000bcb6  mov     rbx, r8
0x14000bcb9  mov     [rsp+140h+var_F8], ecx
0x14000bcbd  mov     rsi, rdx
0x14000bcc0  mov     [rsp+140h+var_100], ecx
0x14000bcc4  test    rdx, rdx
0x14000bcc7  jz      loc_14000BDAF
0x14000bccd  test    rbx, rbx
0x14000bcd0  jz      loc_14000BDAF
0x14000bcd6  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x14000bcdb  mov     r14d, 60h ; '`'
0x14000bce1  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x14000bce6  mov     edx, r14d; unsigned __int64
0x14000bce9  mov     r8, rax; unsigned __int16 *
0x14000bcec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000bcf1  test    eax, eax
0x14000bcf3  js      loc_14000BDB1
0x14000bcf9  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x14000bd00  mov     edx, r14d; unsigned __int64
0x14000bd03  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x14000bd08  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000bd0d  test    eax, eax
0x14000bd0f  js      loc_14000BDB1
0x14000bd15  mov     r8, rdi; unsigned __int16 *
0x14000bd18  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x14000bd1d  mov     edx, r14d; unsigned __int64
0x14000bd20  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000bd25  test    eax, eax
0x14000bd27  js      loc_14000BDB1
0x14000bd2d  lea     r8, asc_14001C460; "\\"
0x14000bd34  mov     edx, r14d; unsigned __int64
0x14000bd37  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x14000bd3c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000bd41  test    eax, eax
0x14000bd43  js      short loc_14000BDB1
0x14000bd45  lea     r8, ?c_szEnrollmentsDBMultipleSession@@3PAGA; "MultipleSession"
0x14000bd4c  mov     edx, r14d; unsigned __int64
0x14000bd4f  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x14000bd54  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000bd59  test    eax, eax
0x14000bd5b  js      short loc_14000BDB1
0x14000bd5d  lea     rax, [rsp+140h+var_FC]
0x14000bd62  mov     r8, rsi; lpValue
0x14000bd65  mov     [rsp+140h+pcbData], rax; pcbData
0x14000bd6a  lea     r9d, [r14-50h]; dwFlags
0x14000bd6e  lea     rax, [rsp+140h+var_100]
0x14000bd73  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14000bd7a  mov     [rsp+140h+pvData], rax; pvData
0x14000bd7f  lea     rdx, [rsp+140h+SubKey]; lpSubKey
0x14000bd84  lea     rax, [rsp+140h+var_F8]
0x14000bd89  mov     [rsp+140h+pdwType], rax; pdwType
0x14000bd8e  call    cs:__imp_RegGetValueW
0x14000bd95  nop     dword ptr [rax+rax+00h]
0x14000bd9a  mov     ecx, eax
0x14000bd9c  mov     eax, [rsp+140h+var_100]
0x14000bda0  mov     [rbx], eax
0x14000bda2  test    ecx, ecx
0x14000bda4  jle     short loc_14000BDAF
0x14000bda6  movzx   ecx, cx
0x14000bda9  or      ecx, 80070000h
0x14000bdaf  mov     eax, ecx
0x14000bdb1  mov     rcx, [rbp+40h+var_30]
0x14000bdb5  xor     rcx, rsp; StackCookie
0x14000bdb8  call    __security_check_cookie
0x14000bdbd  add     rsp, 120h
0x14000bdc4  pop     r14
0x14000bdc6  pop     rdi
0x14000bdc7  pop     rsi
0x14000bdc8  pop     rbx
0x14000bdc9  pop     rbp
0x14000bdca  retn
```
