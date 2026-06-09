# FwSuiteKeyCreate(HKEY__ *,ulong,HKEY__ * *)

- ea: `0x1800398b0`
- end: `0x180039936`
- name: `?FwSuiteKeyCreate@@YAJPEAUHKEY__@@KPEAPEAU1@@Z`
- size: `134`
- prototype: `__int64 __fastcall(HKEY, int, HKEY *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037db0`
- `0x180038b20`

## callees

- `0x18000cff0`
- `0x18001e9ac`
- `0x18001f650`
- `0x1800398b0`

## import_xrefs

- `fwbase!FwRegCreateKey` at `0x180039915`
- `fwbase!FwRegCreateKey` at `0x180039915`

## pseudocode

```c
__int64 __fastcall FwSuiteKeyCreate(HKEY a1, int a2, HKEY *a3)
{
  wchar_t pszDest[16]; // [rsp+40h] [rbp-38h] BYREF

  if ( (int)StringCchPrintfExW(pszDest, 0xEu, 0, 0, 0x800u, L"%04d", a2) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return FwRegCreateKey(a1, pszDest, 15, a3);
}

```

## disassembly

```asm
0x1800398b0  mov     [rsp+arg_18], rbx
0x1800398b5  push    rdi
0x1800398b6  sub     rsp, 70h
0x1800398ba  mov     rax, cs:__security_cookie
0x1800398c1  xor     rax, rsp
0x1800398c4  mov     [rsp+78h+var_18], rax
0x1800398c9  mov     [rsp+78h+var_48], edx
0x1800398cd  lea     rax, a04d; "%04d"
0x1800398d4  xor     r9d, r9d; unsigned __int64 *
0x1800398d7  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x1800398dc  mov     rdi, r8
0x1800398df  mov     [rsp+78h+var_58], 800h; unsigned int
0x1800398e7  mov     rbx, rcx
0x1800398ea  xor     r8d, r8d; unsigned __int16 **
0x1800398ed  lea     rcx, [rsp+78h+pszDest]; pszDest
0x1800398f2  lea     edx, [r9+0Eh]; unsigned __int64
0x1800398f6  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800398fb  test    eax, eax
0x1800398fd  jns     short loc_180039904
0x1800398ff  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180039904  mov     r9, rdi
0x180039907  lea     rdx, [rsp+78h+pszDest]
0x18003990c  mov     r8d, 0Fh
0x180039912  mov     rcx, rbx
0x180039915  call    cs:__imp_FwRegCreateKey
0x18003991b  mov     rcx, [rsp+78h+var_18]
0x180039920  xor     rcx, rsp; StackCookie
0x180039923  call    __security_check_cookie
0x180039928  mov     rbx, [rsp+78h+arg_18]
0x180039930  add     rsp, 70h
0x180039934  pop     rdi
0x180039935  retn
```
