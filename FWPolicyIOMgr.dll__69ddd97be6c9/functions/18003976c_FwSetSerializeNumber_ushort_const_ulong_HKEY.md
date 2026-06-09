# FwSetSerializeNumber(ushort const *,ulong,HKEY__ *)

- ea: `0x18003976c`
- end: `0x1800397ee`
- name: `?FwSetSerializeNumber@@YAJPEBGKPEAUHKEY__@@@Z`
- size: `130`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, HKEY)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038b20`
- `0x180039218`

## callees

- `0x18000cff0`
- `0x18001e9ac`
- `0x18001f650`
- `0x18003976c`

## import_xrefs

- `fwbase!FwRegSetString` at `0x1800397cd`
- `fwbase!FwRegSetString` at `0x1800397cd`

## pseudocode

```c
__int64 __fastcall FwSetSerializeNumber(const unsigned __int16 *a1, int a2, HKEY a3)
{
  wchar_t pszDest[16]; // [rsp+40h] [rbp-38h] BYREF

  if ( (int)StringCchPrintfExW(pszDest, 0xEu, 0, 0, 0x800u, L"%d", a2) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return FwRegSetString(a3, 0, a1, pszDest);
}

```

## disassembly

```asm
0x18003976c  mov     [rsp+arg_18], rbx
0x180039771  push    rdi
0x180039772  sub     rsp, 70h
0x180039776  mov     rax, cs:__security_cookie
0x18003977d  xor     rax, rsp
0x180039780  mov     [rsp+78h+var_18], rax
0x180039785  mov     [rsp+78h+var_48], edx
0x180039789  lea     rax, aD; "%d"
0x180039790  xor     r9d, r9d; unsigned __int64 *
0x180039793  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x180039798  mov     rdi, r8
0x18003979b  mov     [rsp+78h+var_58], 800h; unsigned int
0x1800397a3  mov     rbx, rcx
0x1800397a6  xor     r8d, r8d; unsigned __int16 **
0x1800397a9  lea     rcx, [rsp+78h+pszDest]; pszDest
0x1800397ae  lea     edx, [r9+0Eh]; unsigned __int64
0x1800397b2  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800397b7  test    eax, eax
0x1800397b9  jns     short loc_1800397C0
0x1800397bb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800397c0  lea     r9, [rsp+78h+pszDest]
0x1800397c5  mov     r8, rbx
0x1800397c8  xor     edx, edx
0x1800397ca  mov     rcx, rdi
0x1800397cd  call    cs:__imp_FwRegSetString
0x1800397d3  mov     rcx, [rsp+78h+var_18]
0x1800397d8  xor     rcx, rsp; StackCookie
0x1800397db  call    __security_check_cookie
0x1800397e0  mov     rbx, [rsp+78h+arg_18]
0x1800397e8  add     rsp, 70h
0x1800397ec  pop     rdi
0x1800397ed  retn
```
