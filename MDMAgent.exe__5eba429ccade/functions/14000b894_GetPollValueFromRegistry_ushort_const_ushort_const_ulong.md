# GetPollValueFromRegistry(ushort const *,ushort const *,ulong *)

- ea: `0x14000b894`
- end: `0x14000b9cd`
- name: `?GetPollValueFromRegistry@@YAJPEBG0PEAK@Z`
- size: `313`
- prototype: `signed int __fastcall(const unsigned __int16 *, LPCWSTR lpValue, unsigned int *)`
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
- `0x14000b894`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000b996`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000b996`

## pseudocode

```c
signed int __fastcall GetPollValueFromRegistry(const unsigned __int16 *a1, LPCWSTR lpValue, unsigned int *a3)
{
  LSTATUS ValueW; // ecx
  const unsigned __int16 *v7; // rax
  signed int result; // eax
  unsigned int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pdwType; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[88]; // [rsp+50h] [rbp-B0h] BYREF

  pcbData = 4;
  ValueW = 0;
  pdwType = 0;
  pvData = 0;
  if ( !lpValue || !a3 )
    return ValueW;
  v7 = DMGetNonVolatileRegPrefix();
  result = StringCchCopyW(SubKey, 0x55u, v7);
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
0x14000b894  push    rbp
0x14000b896  push    rbx
0x14000b897  push    rsi
0x14000b898  push    rdi
0x14000b899  push    r14
0x14000b89b  lea     rbp, [rsp-10h]
0x14000b8a0  sub     rsp, 110h
0x14000b8a7  mov     rax, cs:__security_cookie
0x14000b8ae  xor     rax, rsp
0x14000b8b1  mov     [rbp+30h+var_30], rax
0x14000b8b5  mov     rdi, rcx
0x14000b8b8  mov     [rsp+130h+var_EC], 4
0x14000b8c0  xor     ecx, ecx
0x14000b8c2  mov     rbx, r8
0x14000b8c5  mov     [rsp+130h+var_E8], ecx
0x14000b8c9  mov     rsi, rdx
0x14000b8cc  mov     [rsp+130h+var_F0], ecx
0x14000b8d0  test    rdx, rdx
0x14000b8d3  jz      loc_14000B9B1
0x14000b8d9  test    rbx, rbx
0x14000b8dc  jz      loc_14000B9B1
0x14000b8e2  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x14000b8e7  mov     r14d, 55h ; 'U'
0x14000b8ed  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x14000b8f2  mov     edx, r14d; unsigned __int64
0x14000b8f5  mov     r8, rax; unsigned __int16 *
0x14000b8f8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000b8fd  test    eax, eax
0x14000b8ff  js      loc_14000B9B3
0x14000b905  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x14000b90c  mov     edx, r14d; unsigned __int64
0x14000b90f  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x14000b914  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b919  test    eax, eax
0x14000b91b  js      loc_14000B9B3
0x14000b921  mov     r8, rdi; unsigned __int16 *
0x14000b924  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x14000b929  mov     edx, r14d; unsigned __int64
0x14000b92c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b931  test    eax, eax
0x14000b933  js      short loc_14000B9B3
0x14000b935  lea     r8, asc_14001B460; "\\"
0x14000b93c  mov     edx, r14d; unsigned __int64
0x14000b93f  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x14000b944  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b949  test    eax, eax
0x14000b94b  js      short loc_14000B9B3
0x14000b94d  lea     r8, ?c_szEnrollmentsDBPoll@@3PAGA; "Poll"
0x14000b954  mov     edx, r14d; unsigned __int64
0x14000b957  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x14000b95c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b961  test    eax, eax
0x14000b963  js      short loc_14000B9B3
0x14000b965  lea     rax, [rsp+130h+var_EC]
0x14000b96a  mov     r8, rsi; lpValue
0x14000b96d  mov     [rsp+130h+pcbData], rax; pcbData
0x14000b972  lea     r9d, [r14-45h]; dwFlags
0x14000b976  lea     rax, [rsp+130h+var_F0]
0x14000b97b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14000b982  mov     [rsp+130h+pvData], rax; pvData
0x14000b987  lea     rdx, [rsp+130h+SubKey]; lpSubKey
0x14000b98c  lea     rax, [rsp+130h+var_E8]
0x14000b991  mov     [rsp+130h+pdwType], rax; pdwType
0x14000b996  call    cs:__imp_RegGetValueW
0x14000b99c  mov     ecx, eax
0x14000b99e  mov     eax, [rsp+130h+var_F0]
0x14000b9a2  mov     [rbx], eax
0x14000b9a4  test    ecx, ecx
0x14000b9a6  jle     short loc_14000B9B1
0x14000b9a8  movzx   ecx, cx
0x14000b9ab  or      ecx, 80070000h
0x14000b9b1  mov     eax, ecx
0x14000b9b3  mov     rcx, [rbp+30h+var_30]
0x14000b9b7  xor     rcx, rsp; StackCookie
0x14000b9ba  call    __security_check_cookie
0x14000b9bf  add     rsp, 110h
0x14000b9c6  pop     r14
0x14000b9c8  pop     rdi
0x14000b9c9  pop     rsi
0x14000b9ca  pop     rbx
0x14000b9cb  pop     rbp
0x14000b9cc  retn
```
