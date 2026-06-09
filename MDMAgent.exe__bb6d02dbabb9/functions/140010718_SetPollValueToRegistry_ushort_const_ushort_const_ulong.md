# SetPollValueToRegistry(ushort const *,ushort const *,ulong)

- ea: `0x140010718`
- end: `0x14001080f`
- name: `?SetPollValueToRegistry@@YAJPEBG0K@Z`
- size: `247`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValueName, unsigned int)`
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
- `0x140010718`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400107db`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400107db`

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
0x140010718  push    rbx
0x14001071a  push    rsi
0x14001071b  push    rdi
0x14001071c  sub     rsp, 100h
0x140010723  mov     rax, cs:__security_cookie
0x14001072a  xor     rax, rsp
0x14001072d  mov     [rsp+118h+var_28], rax
0x140010735  mov     rdi, rdx
0x140010738  mov     [rsp+118h+Data], r8d
0x14001073d  mov     rbx, rcx
0x140010740  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x140010745  mov     esi, 55h ; 'U'
0x14001074a  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x14001074f  mov     edx, esi; unsigned __int64
0x140010751  mov     r8, rax; unsigned __int16 *
0x140010754  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140010759  test    eax, eax
0x14001075b  js      loc_1400107F3
0x140010761  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x140010768  mov     edx, esi; unsigned __int64
0x14001076a  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x14001076f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140010774  test    eax, eax
0x140010776  js      short loc_1400107F3
0x140010778  mov     r8, rbx; unsigned __int16 *
0x14001077b  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x140010780  mov     edx, esi; unsigned __int64
0x140010782  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140010787  test    eax, eax
0x140010789  js      short loc_1400107F3
0x14001078b  lea     r8, asc_14001C460; "\\"
0x140010792  mov     edx, esi; unsigned __int64
0x140010794  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x140010799  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001079e  test    eax, eax
0x1400107a0  js      short loc_1400107F3
0x1400107a2  lea     r8, ?c_szEnrollmentsDBPoll@@3PAGA; "Poll"
0x1400107a9  mov     edx, esi; unsigned __int64
0x1400107ab  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x1400107b0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400107b5  test    eax, eax
0x1400107b7  js      short loc_1400107F3
0x1400107b9  lea     r9d, [rsi-51h]; dwType
0x1400107bd  mov     r8, rdi; lpValueName
0x1400107c0  lea     rax, [rsp+118h+Data]
0x1400107c5  mov     [rsp+118h+cbData], r9d; cbData
0x1400107ca  lea     rdx, [rsp+118h+SubKey]; lpSubKey
0x1400107cf  mov     [rsp+118h+lpData], rax; lpData
0x1400107d4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400107db  call    cs:__imp_RegSetKeyValueW
0x1400107e2  nop     dword ptr [rax+rax+00h]
0x1400107e7  test    eax, eax
0x1400107e9  jle     short loc_1400107F3
0x1400107eb  movzx   eax, ax
0x1400107ee  or      eax, 80070000h
0x1400107f3  mov     rcx, [rsp+118h+var_28]
0x1400107fb  xor     rcx, rsp; StackCookie
0x1400107fe  call    __security_check_cookie
0x140010803  add     rsp, 100h
0x14001080a  pop     rdi
0x14001080b  pop     rsi
0x14001080c  pop     rbx
0x14001080d  retn
```
