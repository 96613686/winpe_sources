# WdsGetSetupLogPath(wchar_t * *)

- ea: `0x1400185b0`
- end: `0x140018627`
- name: `?WdsGetSetupLogPath@@YAJPEAPEA_W@Z`
- size: `119`
- prototype: `__int64 __fastcall(wchar_t **, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140018630`

## callees

- `0x14000ee94`
- `0x1400185b0`
- `0x14001a7e4`

## string_xrefs

- `0x1400185d6`: `WorkingDirectory`

## pseudocode

```c
__int64 __fastcall WdsGetSetupLogPath(wchar_t **a1, __int64 a2, unsigned int a3)
{
  int StringValue; // edi
  wchar_t *v5; // rcx
  wchar_t *v7[3]; // [rsp+30h] [rbp-18h] BYREF

  v7[0] = 0;
  if ( a1 )
    *a1 = 0;
  StringValue = CbsRegQueryStringValue((HKEY)a1, L"SYSTEM\\Setup", a3, L"WorkingDirectory", v7);
  if ( StringValue >= 0 )
  {
    v5 = v7[0];
    if ( *v7[0] )
    {
      v7[0] = 0;
      if ( a1 )
        *a1 = v5;
    }
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v7);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x1400185b0  mov     [rsp+arg_8], rbx
0x1400185b5  mov     [rsp+arg_10], rsi
0x1400185ba  push    rdi
0x1400185bb  sub     rsp, 40h
0x1400185bf  xor     esi, esi
0x1400185c1  mov     rbx, rcx
0x1400185c4  mov     [rsp+48h+var_18], rsi
0x1400185c9  test    rcx, rcx
0x1400185cc  jz      short loc_1400185D1
0x1400185ce  mov     [rcx], rsi
0x1400185d1  lea     rax, [rsp+48h+var_18]
0x1400185d6  lea     r9, aWorkingdirecto; "WorkingDirectory"
0x1400185dd  mov     [rsp+48h+var_28], rax; wchar_t **
0x1400185e2  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x1400185e9  call    ?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z; CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)
0x1400185ee  mov     edi, eax
0x1400185f0  test    eax, eax
0x1400185f2  js      short loc_14001860B
0x1400185f4  mov     rcx, [rsp+48h+var_18]
0x1400185f9  cmp     [rcx], si
0x1400185fc  jz      short loc_14001860B
0x1400185fe  mov     [rsp+48h+var_18], rsi
0x140018603  test    rbx, rbx
0x140018606  jz      short loc_14001860B
0x140018608  mov     [rbx], rcx
0x14001860b  lea     rcx, [rsp+48h+var_18]
0x140018610  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140018615  mov     rbx, [rsp+48h+arg_8]
0x14001861a  mov     eax, edi
0x14001861c  mov     rsi, [rsp+48h+arg_10]
0x140018621  add     rsp, 40h
0x140018625  pop     rdi
0x140018626  retn
```
