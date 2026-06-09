# GetPollValueFromRegistry(ushort const *,ushort const *,ulong *)

- ea: `0x18000a864`
- end: `0x18000a9a8`
- name: `?GetPollValueFromRegistry@@YAJPEBG0PEAK@Z`
- size: `324`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValue, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180010340`

## callees

- `0x180001c60`
- `0x180009e40`
- `0x18000a864`
- `0x18000ff18`
- `0x18000ff80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a96a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a96a`

## pseudocode

```c
signed int __fastcall GetPollValueFromRegistry(const unsigned __int16 *a1, LPCWSTR lpValue, unsigned int *a3)
{
  LSTATUS ValueW; // ecx
  size_t *v7; // rax
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
  v7 = (size_t *)DMGetNonVolatileRegPrefix();
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
0x18000a864  push    rbp
0x18000a866  push    rbx
0x18000a867  push    rsi
0x18000a868  push    rdi
0x18000a869  push    r14
0x18000a86b  lea     rbp, [rsp-10h]
0x18000a870  sub     rsp, 110h
0x18000a877  mov     rax, cs:__security_cookie
0x18000a87e  xor     rax, rsp
0x18000a881  mov     [rbp+30h+var_30], rax
0x18000a885  mov     rdi, rcx
0x18000a888  mov     [rsp+130h+var_EC], 4
0x18000a890  xor     ecx, ecx
0x18000a892  mov     rbx, r8
0x18000a895  mov     [rsp+130h+var_E8], ecx
0x18000a899  mov     rsi, rdx
0x18000a89c  mov     [rsp+130h+var_F0], ecx
0x18000a8a0  test    rdx, rdx
0x18000a8a3  jz      loc_18000A98B
0x18000a8a9  test    rbx, rbx
0x18000a8ac  jz      loc_18000A98B
0x18000a8b2  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x18000a8b7  mov     r14d, 55h ; 'U'
0x18000a8bd  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x18000a8c2  mov     edx, r14d; unsigned __int64
0x18000a8c5  mov     r8, rax; unsigned __int16 *
0x18000a8c8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a8cd  test    eax, eax
0x18000a8cf  js      loc_18000A98D
0x18000a8d5  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x18000a8dc  mov     edx, r14d; unsigned __int64
0x18000a8df  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x18000a8e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a8e9  test    eax, eax
0x18000a8eb  js      loc_18000A98D
0x18000a8f1  mov     r8, rdi; unsigned __int16 *
0x18000a8f4  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x18000a8f9  mov     edx, r14d; unsigned __int64
0x18000a8fc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a901  test    eax, eax
0x18000a903  js      loc_18000A98D
0x18000a909  lea     r8, asc_180020DAC; "\\"
0x18000a910  mov     edx, r14d; unsigned __int64
0x18000a913  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x18000a918  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a91d  test    eax, eax
0x18000a91f  js      short loc_18000A98D
0x18000a921  lea     r8, ?c_szEnrollmentsDBPoll@@3PAGA; "Poll"
0x18000a928  mov     edx, r14d; unsigned __int64
0x18000a92b  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x18000a930  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a935  test    eax, eax
0x18000a937  js      short loc_18000A98D
0x18000a939  lea     rax, [rsp+130h+var_EC]
0x18000a93e  mov     r8, rsi; lpValue
0x18000a941  mov     [rsp+130h+pcbData], rax; pcbData
0x18000a946  lea     r9d, [r14-45h]; dwFlags
0x18000a94a  lea     rax, [rsp+130h+var_F0]
0x18000a94f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000a956  mov     [rsp+130h+pvData], rax; pvData
0x18000a95b  lea     rdx, [rsp+130h+SubKey]; lpSubKey
0x18000a960  lea     rax, [rsp+130h+var_E8]
0x18000a965  mov     [rsp+130h+pdwType], rax; pdwType
0x18000a96a  call    cs:__imp_RegGetValueW
0x18000a971  nop     dword ptr [rax+rax+00h]
0x18000a976  mov     ecx, eax
0x18000a978  mov     eax, [rsp+130h+var_F0]
0x18000a97c  mov     [rbx], eax
0x18000a97e  test    ecx, ecx
0x18000a980  jle     short loc_18000A98B
0x18000a982  movzx   ecx, cx
0x18000a985  or      ecx, 80070000h
0x18000a98b  mov     eax, ecx
0x18000a98d  mov     rcx, [rbp+30h+var_30]
0x18000a991  xor     rcx, rsp; StackCookie
0x18000a994  call    __security_check_cookie
0x18000a999  add     rsp, 110h
0x18000a9a0  pop     r14
0x18000a9a2  pop     rdi
0x18000a9a3  pop     rsi
0x18000a9a4  pop     rbx
0x18000a9a5  pop     rbp
0x18000a9a6  retn
```
