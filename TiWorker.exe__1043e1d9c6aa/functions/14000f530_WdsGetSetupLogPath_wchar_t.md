# WdsGetSetupLogPath(wchar_t * *)

- ea: `0x14000f530`
- end: `0x14000f5a7`
- name: `?WdsGetSetupLogPath@@YAJPEAPEA_W@Z`
- size: `119`
- prototype: `__int64 __fastcall(wchar_t **, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000f5b0`

## callees

- `0x140006514`
- `0x14000f530`
- `0x140011550`

## string_xrefs

- `0x14000f556`: `WorkingDirectory`

## pseudocode

```c
__int64 __fastcall WdsGetSetupLogPath(wchar_t **a1, __int64 a2, unsigned int a3)
{
  const struct std::nothrow_t *v4; // rdx
  int StringValue; // edi
  wchar_t *v6; // rcx
  wchar_t *v8[3]; // [rsp+30h] [rbp-18h] BYREF

  v8[0] = 0;
  if ( a1 )
    *a1 = 0;
  StringValue = CbsRegQueryStringValue((HKEY)a1, L"SYSTEM\\Setup", a3, L"WorkingDirectory", v8);
  if ( StringValue >= 0 )
  {
    v6 = v8[0];
    if ( *v8[0] )
    {
      v8[0] = 0;
      if ( a1 )
        *a1 = v6;
    }
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((__int64 *)v8, v4);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x14000f530  mov     [rsp+arg_8], rbx
0x14000f535  mov     [rsp+arg_10], rsi
0x14000f53a  push    rdi
0x14000f53b  sub     rsp, 40h
0x14000f53f  xor     esi, esi
0x14000f541  mov     rbx, rcx
0x14000f544  mov     [rsp+48h+var_18], rsi
0x14000f549  test    rcx, rcx
0x14000f54c  jz      short loc_14000F551
0x14000f54e  mov     [rcx], rsi
0x14000f551  lea     rax, [rsp+48h+var_18]
0x14000f556  lea     r9, aWorkingdirecto; "WorkingDirectory"
0x14000f55d  mov     [rsp+48h+var_28], rax; wchar_t **
0x14000f562  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x14000f569  call    ?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z; CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)
0x14000f56e  mov     edi, eax
0x14000f570  test    eax, eax
0x14000f572  js      short loc_14000F58B
0x14000f574  mov     rcx, [rsp+48h+var_18]
0x14000f579  cmp     [rcx], si
0x14000f57c  jz      short loc_14000F58B
0x14000f57e  mov     [rsp+48h+var_18], rsi
0x14000f583  test    rbx, rbx
0x14000f586  jz      short loc_14000F58B
0x14000f588  mov     [rbx], rcx
0x14000f58b  lea     rcx, [rsp+48h+var_18]
0x14000f590  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000f595  mov     rbx, [rsp+48h+arg_8]
0x14000f59a  mov     eax, edi
0x14000f59c  mov     rsi, [rsp+48h+arg_10]
0x14000f5a1  add     rsp, 40h
0x14000f5a5  pop     rdi
0x14000f5a6  retn
```
