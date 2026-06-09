# CWinSATTaskMangerTask::ShouldTryRunWinSAT(bool &)

- ea: `0x180020fa0`
- end: `0x180021066`
- name: `?ShouldTryRunWinSAT@CWinSATTaskMangerTask@@AEAAJAEA_N@Z`
- size: `198`
- prototype: `__int64 __fastcall(CWinSATTaskMangerTask *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1800213a4`

## callees

- `0x18000f0e8`
- `0x180011484`
- `0x180020fa0`
- `0x18002ed6c`
- `0x18002fb50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fd1`

## string_xrefs

- `0x180021010`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x180021036`: `base\winsat\api-dll\winsattaskmangertask.cpp`

## pseudocode

```c
__int64 __fastcall CWinSATTaskMangerTask::ShouldTryRunWinSAT(CWinSATTaskMangerTask *this, bool *a2)
{
  DWORD LastError; // eax
  bool v5; // [rsp+20h] [rbp-138h] BYREF
  CHAR Buffer[256]; // [rsp+30h] [rbp-128h] BYREF
  DWORD v7; // [rsp+130h] [rbp-28h]
  char v8; // [rsp+134h] [rbp-24h]
  __int64 v9; // [rsp+138h] [rbp-20h]

  v5 = 0;
  if ( HasActiveConsoleWindow(&v5) )
  {
    LastError = GetLastError();
    v9 = 0;
    v7 = LastError;
    v8 = 1;
    mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
    Log_Text_F(
      (__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp",
      172,
      "Cannot determine who has the active console Window: %s",
      Buffer);
    return 2147500037LL;
  }
  else
  {
    if ( v5 )
    {
      *a2 = 1;
    }
    else
    {
      Log_Text_F(
        (__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp",
        176,
        "The Active Console Window is not available, cannot run WinSAT");
      *a2 = 0;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180020fa0  push    rbx
0x180020fa2  sub     rsp, 150h
0x180020fa9  mov     rax, cs:__security_cookie
0x180020fb0  xor     rax, rsp
0x180020fb3  mov     [rsp+158h+var_18], rax
0x180020fbb  lea     rcx, [rsp+158h+var_138]; bool *
0x180020fc0  mov     [rsp+158h+var_138], 0
0x180020fc5  mov     rbx, rdx
0x180020fc8  call    ?HasActiveConsoleWindow@@YAKAEA_N@Z; HasActiveConsoleWindow(bool &)
0x180020fcd  test    eax, eax
0x180020fcf  jz      short loc_180021023
0x180020fd1  call    cs:__imp_GetLastError
0x180020fd8  nop     dword ptr [rax+rax+00h]
0x180020fdd  and     [rsp+158h+var_20], 0
0x180020fe6  lea     rcx, [rsp+158h+Buffer]; lpBuffer
0x180020feb  mov     [rsp+158h+var_28], eax
0x180020ff2  mov     [rsp+158h+var_24], 1
0x180020ffa  call    ?fmt_desc@?$WinErrorT@DU?$char_traits@D@std@@V?$m_traits@D@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(void)
0x180020fff  lea     r9, [rsp+158h+Buffer]
0x180021004  mov     edx, 0ACh
0x180021009  lea     r8, aCannotDetermin_0; "Cannot determine who has the active con"...
0x180021010  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021017  call    Log_Text_F
0x18002101c  mov     eax, 80004005h
0x180021021  jmp     short loc_18002104C
0x180021023  cmp     [rsp+158h+var_138], 0
0x180021028  jnz     short loc_180021047
0x18002102a  lea     r8, aTheActiveConso; "The Active Console Window is not availa"...
0x180021031  mov     edx, 0B0h
0x180021036  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x18002103d  call    Log_Text_F
0x180021042  mov     byte ptr [rbx], 0
0x180021045  jmp     short loc_18002104A
0x180021047  mov     byte ptr [rbx], 1
0x18002104a  xor     eax, eax
0x18002104c  mov     rcx, [rsp+158h+var_18]
0x180021054  xor     rcx, rsp; StackCookie
0x180021057  call    __security_check_cookie
0x18002105c  add     rsp, 150h
0x180021063  pop     rbx
0x180021064  retn
```
