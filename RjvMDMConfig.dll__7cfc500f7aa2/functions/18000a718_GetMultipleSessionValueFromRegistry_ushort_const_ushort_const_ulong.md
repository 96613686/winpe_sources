# GetMultipleSessionValueFromRegistry(ushort const *,ushort const *,ulong *)

- ea: `0x18000a718`
- end: `0x18000a85c`
- name: `?GetMultipleSessionValueFromRegistry@@YAJPEBG0PEAK@Z`
- size: `324`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValue, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180010804`

## callees

- `0x180001c60`
- `0x180009e40`
- `0x18000a718`
- `0x18000ff18`
- `0x18000ff80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a81e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a81e`

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
0x18000a718  push    rbp
0x18000a71a  push    rbx
0x18000a71b  push    rsi
0x18000a71c  push    rdi
0x18000a71d  push    r14
0x18000a71f  lea     rbp, [rsp-20h]
0x18000a724  sub     rsp, 120h
0x18000a72b  mov     rax, cs:__security_cookie
0x18000a732  xor     rax, rsp
0x18000a735  mov     [rbp+40h+var_30], rax
0x18000a739  mov     rdi, rcx
0x18000a73c  mov     [rsp+140h+var_FC], 4
0x18000a744  xor     ecx, ecx
0x18000a746  mov     rbx, r8
0x18000a749  mov     [rsp+140h+var_F8], ecx
0x18000a74d  mov     rsi, rdx
0x18000a750  mov     [rsp+140h+var_100], ecx
0x18000a754  test    rdx, rdx
0x18000a757  jz      loc_18000A83F
0x18000a75d  test    rbx, rbx
0x18000a760  jz      loc_18000A83F
0x18000a766  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x18000a76b  mov     r14d, 60h ; '`'
0x18000a771  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x18000a776  mov     edx, r14d; unsigned __int64
0x18000a779  mov     r8, rax; unsigned __int16 *
0x18000a77c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a781  test    eax, eax
0x18000a783  js      loc_18000A841
0x18000a789  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x18000a790  mov     edx, r14d; unsigned __int64
0x18000a793  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x18000a798  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a79d  test    eax, eax
0x18000a79f  js      loc_18000A841
0x18000a7a5  mov     r8, rdi; unsigned __int16 *
0x18000a7a8  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x18000a7ad  mov     edx, r14d; unsigned __int64
0x18000a7b0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a7b5  test    eax, eax
0x18000a7b7  js      loc_18000A841
0x18000a7bd  lea     r8, asc_180020DAC; "\\"
0x18000a7c4  mov     edx, r14d; unsigned __int64
0x18000a7c7  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x18000a7cc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a7d1  test    eax, eax
0x18000a7d3  js      short loc_18000A841
0x18000a7d5  lea     r8, ?c_szEnrollmentsDBMultipleSession@@3PAGA; "MultipleSession"
0x18000a7dc  mov     edx, r14d; unsigned __int64
0x18000a7df  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x18000a7e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a7e9  test    eax, eax
0x18000a7eb  js      short loc_18000A841
0x18000a7ed  lea     rax, [rsp+140h+var_FC]
0x18000a7f2  mov     r8, rsi; lpValue
0x18000a7f5  mov     [rsp+140h+pcbData], rax; pcbData
0x18000a7fa  lea     r9d, [r14-50h]; dwFlags
0x18000a7fe  lea     rax, [rsp+140h+var_100]
0x18000a803  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000a80a  mov     [rsp+140h+pvData], rax; pvData
0x18000a80f  lea     rdx, [rsp+140h+SubKey]; lpSubKey
0x18000a814  lea     rax, [rsp+140h+var_F8]
0x18000a819  mov     [rsp+140h+pdwType], rax; pdwType
0x18000a81e  call    cs:__imp_RegGetValueW
0x18000a825  nop     dword ptr [rax+rax+00h]
0x18000a82a  mov     ecx, eax
0x18000a82c  mov     eax, [rsp+140h+var_100]
0x18000a830  mov     [rbx], eax
0x18000a832  test    ecx, ecx
0x18000a834  jle     short loc_18000A83F
0x18000a836  movzx   ecx, cx
0x18000a839  or      ecx, 80070000h
0x18000a83f  mov     eax, ecx
0x18000a841  mov     rcx, [rbp+40h+var_30]
0x18000a845  xor     rcx, rsp; StackCookie
0x18000a848  call    __security_check_cookie
0x18000a84d  add     rsp, 120h
0x18000a854  pop     r14
0x18000a856  pop     rdi
0x18000a857  pop     rsi
0x18000a858  pop     rbx
0x18000a859  pop     rbp
0x18000a85a  retn
```
