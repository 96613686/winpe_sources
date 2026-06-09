# Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)

- ea: `0x1400ff188`
- end: `0x1400ff2fd`
- name: `?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ`
- size: `373`
- prototype: ``
- caller_count: `172`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400fecc0`
- `0x1400feeb8`
- `0x1400ffe24`
- `0x140100614`
- `0x1401010f8`
- `0x140101810`
- `0x1401019c0`
- `0x140101bd0`
- `0x140102c48`
- `0x140102f64`
- `0x140110dfc`
- `0x140112fe0`
- `0x140113030`
- `0x140113800`
- `0x140113ff0`
- `0x140114060`
- `0x140114260`
- `0x140114470`
- `0x140114520`
- `0x140114b80`
- `0x140114dc0`
- `0x140114f30`
- `0x140115110`
- `0x1401151e0`
- `0x1401152d0`
- `0x1401153a0`
- `0x140115d30`
- `0x140116bc8`
- `0x140119e14`
- `0x14011b120`
- `0x14011c570`
- `0x14011c960`
- `0x14011cc90`
- `0x14011cf20`
- `0x14011d2d0`
- `0x14011d6a0`
- `0x14011da90`
- `0x14011dea0`
- `0x14011e450`
- `0x14011e6f0`
- `0x14011ea90`
- `0x14012054c`
- `0x140121688`
- `0x140121c68`
- `0x140121e4c`
- `0x140122318`
- `0x14012251c`
- `0x140122af0`
- `0x140123480`
- `0x140123860`

## callees

- `0x14003a5c0`
- `0x14004e53c`
- `0x140086008`
- `0x1400fe2a0`
- `0x1400ff188`
- `0x140166990`

## import_xrefs

- `KERNEL32!OutputDebugStringA` at `0x1400ff2da`
- `KERNEL32!OutputDebugStringA` at `0x1400ff2da`
- `KERNEL32!GetCurrentThreadId` at `0x1400ff1fc`
- `KERNEL32!GetCurrentThreadId` at `0x1400ff1fc`
- `KERNEL32!GetSystemTime` at `0x1400ff1eb`
- `KERNEL32!GetSystemTime` at `0x1400ff1eb`

## pseudocode

```c
void Microsoft::Applications::Events::PlatformAbstraction::detail::log(_QWORD a1, _QWORD a2, const char *a3, ...)
{
  int v3; // edi
  unsigned __int64 *v4; // rax
  int v5; // eax
  int v6; // edi
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  struct _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-98h] BYREF
  CHAR OutputString[2048]; // [rsp+80h] [rbp-80h] BYREF
  va_list va; // [rsp+8D8h] [rbp+7D8h] BYREF

  va_start(va, a3);
  if ( Microsoft::Applications::Events::PlatformAbstraction::detail::isLoggingInited )
  {
    memset(OutputString, 0, sizeof(OutputString));
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    GetCurrentThreadId();
    v3 = sprintf_s<2048>(OutputString, "%04u-%02u-%02u %02u:%02u:%02u.%03u T#%u <%c> [%s] ");
    v4 = _local_stdio_printf_options();
    v5 = _stdio_common_vsprintf_s(*v4, &OutputString[v3], 2048LL - v3, a3, 0, va);
    if ( v5 < 0 )
      v5 = -1;
    v6 = v5 + v3;
    v7 = v6;
    if ( (unsigned __int64)v6 > 0x7FE )
      v7 = 2046;
    OutputString[v7] = 10;
    v8 = v6 + 1;
    if ( v8 > 0x7FF )
      v8 = 2047;
    OutputString[v8] = 0;
    OutputDebugStringA(OutputString);
  }
}

```

## disassembly

```asm
0x1400ff188  mov     [rsp-8+Format], r8
0x1400ff18d  mov     qword ptr [rsp-8+arg_18], r9
0x1400ff192  push    rbp
0x1400ff193  push    rbx
0x1400ff194  push    rsi
0x1400ff195  push    rdi
0x1400ff196  push    r14
0x1400ff198  lea     rbp, [rsp-790h]
0x1400ff1a0  sub     rsp, 890h
0x1400ff1a7  mov     rax, cs:__security_cookie
0x1400ff1ae  xor     rax, rsp
0x1400ff1b1  mov     [rbp+7B0h+var_30], rax
0x1400ff1b8  cmp     cs:?isLoggingInited@detail@PlatformAbstraction@Events@Applications@Microsoft@@3_NA, 0; bool Microsoft::Applications::Events::PlatformAbstraction::detail::isLoggingInited
0x1400ff1bf  mov     r14, rdx
0x1400ff1c2  movsxd  rbx, ecx
0x1400ff1c5  jz      loc_1400FF2E0
0x1400ff1cb  mov     esi, 800h
0x1400ff1d0  lea     rcx, [rbp+7B0h+OutputString]; void *
0x1400ff1d4  mov     r8d, esi; Size
0x1400ff1d7  xor     edx, edx; Val
0x1400ff1d9  call    memset
0x1400ff1de  xorps   xmm0, xmm0
0x1400ff1e1  lea     rcx, [rsp+8B0h+SystemTime]; lpSystemTime
0x1400ff1e6  movups  xmmword ptr [rsp+8B0h+SystemTime.wYear], xmm0
0x1400ff1eb  call    cs:__imp_GetSystemTime
0x1400ff1f1  lea     rcx, aEwid; "?EWID"
0x1400ff1f8  movsx   edi, byte ptr [rbx+rcx]
0x1400ff1fc  call    cs:__imp_GetCurrentThreadId
0x1400ff202  movzx   ecx, [rsp+8B0h+SystemTime.wMilliseconds]
0x1400ff207  movzx   edx, [rsp+8B0h+SystemTime.wSecond]
0x1400ff20c  movzx   r10d, [rsp+8B0h+SystemTime.wMinute]
0x1400ff212  movzx   r11d, [rsp+8B0h+SystemTime.wHour]
0x1400ff218  movzx   ebx, [rsp+8B0h+SystemTime.wDay]
0x1400ff21d  movzx   r9d, [rsp+8B0h+SystemTime.wMonth]
0x1400ff223  movzx   r8d, [rsp+8B0h+SystemTime.wYear]
0x1400ff229  mov     [rsp+8B0h+var_858], r14
0x1400ff22e  mov     [rsp+8B0h+var_860], edi
0x1400ff232  mov     [rsp+8B0h+var_868], eax
0x1400ff236  mov     [rsp+8B0h+var_870], ecx
0x1400ff23a  lea     rcx, [rbp+7B0h+OutputString]; Buffer
0x1400ff23e  mov     [rsp+8B0h+var_878], edx
0x1400ff242  lea     rdx, a04u02u02u02u02; "%04u-%02u-%02u %02u:%02u:%02u.%03u T#%u"...
0x1400ff249  mov     [rsp+8B0h+var_880], r10d
0x1400ff24e  mov     dword ptr [rsp+8B0h+ArgList], r11d
0x1400ff253  mov     dword ptr [rsp+8B0h+Locale], ebx
0x1400ff257  call    ??$sprintf_s@$0IAA@@@YAHAEAY0IAA@DPEBDZZ; sprintf_s<2048>(char (&)[2048],char const *,...)
0x1400ff25c  movsxd  rdi, eax
0x1400ff25f  lea     rbx, [rbp+7B0h+OutputString]
0x1400ff263  sub     rsi, rdi
0x1400ff266  mov     [rsp+8B0h+var_850], 0
0x1400ff26f  add     rbx, rdi
0x1400ff272  lea     r14, [rbp+7B0h+arg_18]
0x1400ff279  call    __local_stdio_printf_options
0x1400ff27e  mov     r9, [rbp+7B0h+Format]; Format
0x1400ff285  mov     r8, rsi; BufferCount
0x1400ff288  mov     [rsp+8B0h+ArgList], r14; ArgList
0x1400ff28d  mov     rdx, rbx; Buffer
0x1400ff290  mov     [rsp+8B0h+Locale], 0; Locale
0x1400ff299  mov     rcx, [rax]; Options
0x1400ff29c  call    __stdio_common_vsprintf_s
0x1400ff2a1  or      ecx, 0FFFFFFFFh
0x1400ff2a4  test    eax, eax
0x1400ff2a6  cmovs   eax, ecx
0x1400ff2a9  mov     ecx, 7FEh
0x1400ff2ae  add     edi, eax
0x1400ff2b0  movsxd  rax, edi
0x1400ff2b3  cmp     rax, rcx
0x1400ff2b6  cmova   rax, rcx
0x1400ff2ba  mov     [rbp+rax+7B0h+OutputString], 0Ah
0x1400ff2bf  lea     eax, [rdi+1]
0x1400ff2c2  movsxd  rcx, eax
0x1400ff2c5  mov     eax, 7FFh
0x1400ff2ca  cmp     rcx, rax
0x1400ff2cd  cmova   rcx, rax
0x1400ff2d1  mov     [rbp+rcx+7B0h+OutputString], 0
0x1400ff2d6  lea     rcx, [rbp+7B0h+OutputString]; lpOutputString
0x1400ff2da  call    cs:__imp_OutputDebugStringA
0x1400ff2e0  mov     rcx, [rbp+7B0h+var_30]
0x1400ff2e7  xor     rcx, rsp; StackCookie
0x1400ff2ea  call    __security_check_cookie
0x1400ff2ef  add     rsp, 890h
0x1400ff2f6  pop     r14
0x1400ff2f8  pop     rdi
0x1400ff2f9  pop     rsi
0x1400ff2fa  pop     rbx
0x1400ff2fb  pop     rbp
0x1400ff2fc  retn
```
