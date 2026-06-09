# LogSimpleMessage(int,ushort const *,char const *)

- ea: `0x180002204`
- end: `0x180002306`
- name: `?LogSimpleMessage@@YAXHPEBGPEBD@Z`
- size: `258`
- prototype: `void __fastcall(__int16, const unsigned __int16 *, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180002008`

## callees

- `0x180001400`
- `0x180001fd8`
- `0x180002204`
- `0x18000230c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002230`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002230`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800022db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800022db`

## string_xrefs

- `0x180002275`: `onecoreuap\enduser\winstore\licensemanager\tslexchangetask\logging.cpp`

## pseudocode

```c
void __fastcall LogSimpleMessage(__int16 a1, const unsigned __int16 *a2, const char *a3)
{
  const char *v6; // rbx
  WCHAR OutputString[1000]; // [rsp+40h] [rbp-7E8h] BYREF

  if ( IsDebuggerPresent() )
  {
    switch ( a1 )
    {
      case 1:
        v6 = "ERROR";
        break;
      case 2:
        v6 = " WARN";
        break;
      case 3:
        v6 = " info";
        break;
      default:
        v6 = "UNKWN";
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\tslexchangetask\\logging.cpp",
          0x19u,
          "LogSimpleMessage",
          (wchar_t *)L"Assert (%s): %s",
          L"0",
          L"Failed");
        break;
    }
    StringCchPrintfW(OutputString, 0x3E8u, L"%hs: %ws (%hs)\n", v6, a2, a3);
    OutputDebugStringW(OutputString);
  }
}

```

## disassembly

```asm
0x180002204  mov     [rsp+arg_0], rbx
0x180002209  mov     [rsp+arg_18], rsi
0x18000220e  push    rdi
0x18000220f  sub     rsp, 820h
0x180002216  mov     rax, cs:__security_cookie
0x18000221d  xor     rax, rsp
0x180002220  mov     [rsp+828h+var_18], rax
0x180002228  mov     rsi, r8
0x18000222b  mov     rdi, rdx
0x18000222e  mov     ebx, ecx
0x180002230  call    cs:__imp_IsDebuggerPresent
0x180002236  test    eax, eax
0x180002238  jz      loc_1800022E1
0x18000223e  movzx   ecx, bx
0x180002241  sub     ecx, 1
0x180002244  jz      short loc_1800022AC
0x180002246  sub     ecx, 1
0x180002249  jz      short loc_1800022A3
0x18000224b  cmp     ecx, 1
0x18000224e  jz      short loc_18000229A
0x180002250  lea     rax, aFailed; "Failed"
0x180002257  mov     r8d, 19h; unsigned int
0x18000225d  mov     [rsp+828h+var_7F8], rax
0x180002262  lea     r9, aLogsimplemessa; "LogSimpleMessage"
0x180002269  lea     rax, a0; "0"
0x180002270  mov     [rsp+828h+var_800], rax
0x180002275  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000227c  lea     rax, aAssertSS; "Assert (%s): %s"
0x180002283  lea     ecx, [r8-18h]; unsigned int
0x180002287  mov     [rsp+828h+var_808], rax; unsigned __int16 *
0x18000228c  lea     rbx, aUnkwn; "UNKWN"
0x180002293  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180002298  jmp     short loc_1800022B3
0x18000229a  lea     rbx, aInfo; " info"
0x1800022a1  jmp     short loc_1800022B3
0x1800022a3  lea     rbx, aWarn; " WARN"
0x1800022aa  jmp     short loc_1800022B3
0x1800022ac  lea     rbx, aError; "ERROR"
0x1800022b3  mov     [rsp+828h+var_800], rsi
0x1800022b8  lea     r8, aHsWsHs; "%hs: %ws (%hs)\n"
0x1800022bf  mov     r9, rbx
0x1800022c2  mov     [rsp+828h+var_808], rdi
0x1800022c7  mov     edx, 3E8h; unsigned __int64
0x1800022cc  lea     rcx, [rsp+828h+OutputString]; unsigned __int16 *
0x1800022d1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800022d6  lea     rcx, [rsp+828h+OutputString]; lpOutputString
0x1800022db  call    cs:__imp_OutputDebugStringW
0x1800022e1  mov     rcx, [rsp+828h+var_18]
0x1800022e9  xor     rcx, rsp; StackCookie
0x1800022ec  call    __security_check_cookie
0x1800022f1  lea     r11, [rsp+828h+var_8]
0x1800022f9  mov     rbx, [r11+10h]
0x1800022fd  mov     rsi, [r11+28h]
0x180002301  mov     rsp, r11
0x180002304  pop     rdi
0x180002305  retn
```
