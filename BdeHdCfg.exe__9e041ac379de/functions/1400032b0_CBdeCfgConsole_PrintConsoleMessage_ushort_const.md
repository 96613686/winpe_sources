# CBdeCfgConsole::PrintConsoleMessage(ushort const *,...)

- ea: `0x1400032b0`
- end: `0x140003338`
- name: `?PrintConsoleMessage@CBdeCfgConsole@@AEAAJPEBGZZ`
- size: `136`
- prototype: `__int64(CBdeCfgConsole *__hidden this, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140001dbc`
- `0x140001ecc`
- `0x1400029d0`
- `0x140002a00`
- `0x140003804`
- `0x140003884`

## callees

- `0x1400032b0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140003307`
- `KERNEL32!FormatMessageW` at `0x140003307`
- `KERNEL32!LocalFree` at `0x14000332b`
- `KERNEL32!LocalFree` at `0x14000332b`
- `msvcrt!wprintf` at `0x140003320`
- `msvcrt!wprintf` at `0x140003320`

## pseudocode

```c
__int64 CBdeCfgConsole::PrintConsoleMessage(CBdeCfgConsole *this, const unsigned __int16 *a2, ...)
{
  bool v2; // zf
  va_list v4; // [rsp+40h] [rbp-18h] BYREF
  wchar_t *Format; // [rsp+48h] [rbp-10h] BYREF
  va_list va; // [rsp+70h] [rbp+18h] BYREF

  va_start(va, a2);
  v2 = *((_BYTE *)this + 1384) == 0;
  v4 = 0;
  if ( v2 )
  {
    Format = 0;
    va_copy(v4, va);
    FormatMessageW(0x500u, a2, 0, 0, (LPWSTR)&Format, 0, &v4);
    v4 = 0;
    if ( Format )
    {
      wprintf(Format);
      LocalFree(Format);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400032b0  mov     r11, rsp
0x1400032b3  mov     [r11+10h], rdx
0x1400032b7  mov     [r11+18h], r8
0x1400032bb  mov     [r11+20h], r9
0x1400032bf  sub     rsp, 58h
0x1400032c3  cmp     byte ptr [rcx+568h], 0
0x1400032ca  mov     qword ptr [r11-18h], 0
0x1400032d2  jnz     short loc_140003331
0x1400032d4  lea     rax, [r11+18h]
0x1400032d8  mov     qword ptr [r11-10h], 0
0x1400032e0  mov     [r11-18h], rax
0x1400032e4  xor     r9d, r9d; dwLanguageId
0x1400032e7  lea     rax, [r11-18h]
0x1400032eb  xor     r8d, r8d; dwMessageId
0x1400032ee  mov     [r11-28h], rax
0x1400032f2  mov     ecx, 500h; dwFlags
0x1400032f7  lea     rax, [r11-10h]
0x1400032fb  mov     [rsp+58h+nSize], 0; nSize
0x140003303  mov     [r11-38h], rax
0x140003307  call    cs:__imp_FormatMessageW
0x14000330d  mov     rcx, [rsp+58h+Format]; Format
0x140003312  mov     [rsp+58h+var_18], 0
0x14000331b  test    rcx, rcx
0x14000331e  jz      short loc_140003331
0x140003320  call    cs:__imp_wprintf
0x140003326  mov     rcx, [rsp+58h+Format]; hMem
0x14000332b  call    cs:__imp_LocalFree
0x140003331  xor     eax, eax
0x140003333  add     rsp, 58h
0x140003337  retn
```
