# GetPollValueFromRegistry(ushort const *,ushort const *,ulong *)

- ea: `0x14000bdd4`
- end: `0x14000bf18`
- name: `?GetPollValueFromRegistry@@YAJPEBG0PEAK@Z`
- size: `324`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValue, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140010cf0`

## callees

- `0x1400029c0`
- `0x1400074ec`
- `0x1400075e4`
- `0x14000b7c0`
- `0x14000bdd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000beda`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000beda`

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
0x14000bdd4  push    rbp
0x14000bdd6  push    rbx
0x14000bdd7  push    rsi
0x14000bdd8  push    rdi
0x14000bdd9  push    r14
0x14000bddb  lea     rbp, [rsp-10h]
0x14000bde0  sub     rsp, 110h
0x14000bde7  mov     rax, cs:__security_cookie
0x14000bdee  xor     rax, rsp
0x14000bdf1  mov     [rbp+30h+var_30], rax
0x14000bdf5  mov     rdi, rcx
0x14000bdf8  mov     [rsp+130h+var_EC], 4
0x14000be00  xor     ecx, ecx
0x14000be02  mov     rbx, r8
0x14000be05  mov     [rsp+130h+var_E8], ecx
0x14000be09  mov     rsi, rdx
0x14000be0c  mov     [rsp+130h+var_F0], ecx
0x14000be10  test    rdx, rdx
0x14000be13  jz      loc_14000BEFB
0x14000be19  test    rbx, rbx
0x14000be1c  jz      loc_14000BEFB
0x14000be22  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x14000be27  mov     r14d, 55h ; 'U'
0x14000be2d  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x14000be32  mov     edx, r14d; unsigned __int64
0x14000be35  mov     r8, rax; unsigned __int16 *
0x14000be38  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000be3d  test    eax, eax
0x14000be3f  js      loc_14000BEFD
0x14000be45  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x14000be4c  mov     edx, r14d; unsigned __int64
0x14000be4f  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x14000be54  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000be59  test    eax, eax
0x14000be5b  js      loc_14000BEFD
0x14000be61  mov     r8, rdi; unsigned __int16 *
0x14000be64  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x14000be69  mov     edx, r14d; unsigned __int64
0x14000be6c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000be71  test    eax, eax
0x14000be73  js      loc_14000BEFD
0x14000be79  lea     r8, asc_14001C460; "\\"
0x14000be80  mov     edx, r14d; unsigned __int64
0x14000be83  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x14000be88  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000be8d  test    eax, eax
0x14000be8f  js      short loc_14000BEFD
0x14000be91  lea     r8, ?c_szEnrollmentsDBPoll@@3PAGA; "Poll"
0x14000be98  mov     edx, r14d; unsigned __int64
0x14000be9b  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x14000bea0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000bea5  test    eax, eax
0x14000bea7  js      short loc_14000BEFD
0x14000bea9  lea     rax, [rsp+130h+var_EC]
0x14000beae  mov     r8, rsi; lpValue
0x14000beb1  mov     [rsp+130h+pcbData], rax; pcbData
0x14000beb6  lea     r9d, [r14-45h]; dwFlags
0x14000beba  lea     rax, [rsp+130h+var_F0]
0x14000bebf  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14000bec6  mov     [rsp+130h+pvData], rax; pvData
0x14000becb  lea     rdx, [rsp+130h+SubKey]; lpSubKey
0x14000bed0  lea     rax, [rsp+130h+var_E8]
0x14000bed5  mov     [rsp+130h+pdwType], rax; pdwType
0x14000beda  call    cs:__imp_RegGetValueW
0x14000bee1  nop     dword ptr [rax+rax+00h]
0x14000bee6  mov     ecx, eax
0x14000bee8  mov     eax, [rsp+130h+var_F0]
0x14000beec  mov     [rbx], eax
0x14000beee  test    ecx, ecx
0x14000bef0  jle     short loc_14000BEFB
0x14000bef2  movzx   ecx, cx
0x14000bef5  or      ecx, 80070000h
0x14000befb  mov     eax, ecx
0x14000befd  mov     rcx, [rbp+30h+var_30]
0x14000bf01  xor     rcx, rsp; StackCookie
0x14000bf04  call    __security_check_cookie
0x14000bf09  add     rsp, 110h
0x14000bf10  pop     r14
0x14000bf12  pop     rdi
0x14000bf13  pop     rsi
0x14000bf14  pop     rbx
0x14000bf15  pop     rbp
0x14000bf16  retn
```
