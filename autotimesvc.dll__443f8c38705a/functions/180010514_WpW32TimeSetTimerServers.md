# WpW32TimeSetTimerServers

- ea: `0x180010514`
- end: `0x180010572`
- name: `WpW32TimeSetTimerServers`
- size: `94`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000d330`

## callees

- `0x18000dfa8`
- `0x18000e048`
- `0x18000eef0`
- `0x180010514`

## string_xrefs

- `0x18001052c`: `HKLM\System\ControlSet001\Services\W32Time\Parameters`

## pseudocode

```c
__int64 __fastcall WpW32TimeSetTimerServers(unsigned __int16 *a1)
{
  const char *v2; // r9
  __int64 result; // rax
  __int128 v4; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = 0;
  try
  {
    RegKey::Create(
      (RegKey *)&v4,
      L"W32TimeParameters",
      L"HKLM\\System\\ControlSet001\\Services\\W32Time\\Parameters",
      0x20006u);
    RegKey::SetString((RegKey *)&v4, L"NTPServer", a1);
    RegKey::~RegKey((RegKey *)&v4);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x218,
                           (int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
                           v2);
  }
  return result;
}

```

## disassembly

```asm
0x180010514  push    rbx
0x180010516  sub     rsp, 30h
0x18001051a  mov     rbx, rcx
0x18001051d  xorps   xmm0, xmm0
0x180010520  movdqu  [rsp+38h+var_18], xmm0
0x180010526  mov     r9d, 20006h; unsigned int
0x18001052c  lea     r8, aHklmSystemCont_0; "HKLM\\System\\ControlSet001\\Services\\"...
0x180010533  lea     rdx, aW32timeparamet; "W32TimeParameters"
0x18001053a  lea     rcx, [rsp+38h+var_18]; this
0x18001053f  call    ?Create@RegKey@@QEAAXPEBG0K@Z; RegKey::Create(ushort const *,ushort const *,ulong)
0x180010544  mov     r8, rbx; unsigned __int16 *
0x180010547  lea     rdx, aNtpserver; "NTPServer"
0x18001054e  lea     rcx, [rsp+38h+var_18]; this
0x180010553  call    ?SetString@RegKey@@QEBAXPEBG0@Z; RegKey::SetString(ushort const *,ushort const *)
0x180010558  nop
0x180010559  lea     rcx, [rsp+38h+var_18]; this
0x18001055e  call    ??1RegKey@@QEAA@XZ; RegKey::~RegKey(void)
0x180010563  xor     eax, eax
0x180010565  jmp     short loc_18001056B
0x180010567  mov     eax, [rsp+38h+arg_8]
0x18001056b  add     rsp, 30h
0x18001056f  pop     rbx
0x180010570  retn
```
