# CBdeCfgConsole::PrintConsoleMessage(long,...)

- ea: `0x1400031c4`
- end: `0x1400032aa`
- name: `?PrintConsoleMessage@CBdeCfgConsole@@AEAAJJZZ`
- size: `230`
- prototype: `__int64(CBdeCfgConsole *this, unsigned int, ...)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140001dbc`
- `0x140001fac`
- `0x140002898`
- `0x140002bc4`
- `0x1400031c4`
- `0x140003340`
- `0x140003884`

## callees

- `0x140001008`
- `0x1400031c4`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x14000324b`
- `KERNEL32!FormatMessageW` at `0x14000324b`
- `KERNEL32!LocalFree` at `0x140003292`
- `KERNEL32!LocalFree` at `0x140004737`
- `KERNEL32!LocalFree` at `0x140003292`
- `KERNEL32!LocalFree` at `0x140004737`
- `msvcrt!wprintf` at `0x140003264`
- `msvcrt!wprintf` at `0x140003264`
- `BDEHDCFGLIB!BdeCfgLoadErrorString` at `0x140003208`
- `BDEHDCFGLIB!BdeCfgLoadErrorString` at `0x140003208`

## pseudocode

```c
__int64 CBdeCfgConsole::PrintConsoleMessage(CBdeCfgConsole *this, unsigned int a2, ...)
{
  WCHAR Buffer[4]; // [rsp+40h] [rbp-28h] BYREF
  LPCVOID lpSource; // [rsp+48h] [rbp-20h] BYREF
  va_list Arguments; // [rsp+50h] [rbp-18h] BYREF
  va_list va; // [rsp+80h] [rbp+18h] BYREF

  va_start(va, a2);
  lpSource = 0;
  *(_QWORD *)Buffer = 0;
  Arguments = 0;
  if ( !*((_BYTE *)this + 1384) && (int)BdeCfgLoadErrorString(a2, (unsigned __int16 **)&lpSource) >= 0 )
  {
    va_copy(Arguments, va);
    FormatMessageW(0x500u, lpSource, 0, 0, Buffer, 0, &Arguments);
    Arguments = 0;
    if ( *(_QWORD *)Buffer )
    {
      wprintf(*(const wchar_t *const *)Buffer);
    }
    else if ( a2 != -1063256018 )
    {
      CBdeCfgConsole::PrintConsoleMessage(this, -1063256018);
    }
  }
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  operator delete((void *)lpSource);
  return 0;
}

```

## disassembly

```asm
0x1400031c4  mov     [rsp+arg_8], edx
0x1400031c8  mov     r11, rsp
0x1400031cb  mov     [r11+18h], r8
0x1400031cf  mov     [r11+20h], r9
0x1400031d3  push    rbx
0x1400031d4  sub     rsp, 60h
0x1400031d8  mov     eax, edx
0x1400031da  mov     rbx, rcx
0x1400031dd  mov     qword ptr [r11-20h], 0
0x1400031e5  mov     qword ptr [r11-28h], 0
0x1400031ed  mov     qword ptr [r11-18h], 0
0x1400031f5  cmp     byte ptr [rcx+568h], 0
0x1400031fc  jnz     loc_140003288
0x140003202  lea     rdx, [r11-20h]
0x140003206  mov     ecx, eax
0x140003208  call    cs:__imp_?BdeCfgLoadErrorString@@YAJKPEAPEAG@Z; BdeCfgLoadErrorString(ulong,ushort * *)
0x14000320e  test    eax, eax
0x140003210  js      short loc_140003288
0x140003212  lea     rax, [rsp+68h+arg_10]
0x14000321a  mov     [rsp+68h+var_18], rax
0x14000321f  lea     rax, [rsp+68h+var_18]
0x140003224  mov     [rsp+68h+Arguments], rax; Arguments
0x140003229  mov     [rsp+68h+nSize], 0; nSize
0x140003231  lea     rax, [rsp+68h+Buffer]
0x140003236  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x14000323b  xor     r9d, r9d; dwLanguageId
0x14000323e  xor     r8d, r8d; dwMessageId
0x140003241  mov     rdx, [rsp+68h+lpSource]; lpSource
0x140003246  mov     ecx, 500h; dwFlags
0x14000324b  call    cs:__imp_FormatMessageW
0x140003251  mov     [rsp+68h+var_18], 0
0x14000325a  mov     rcx, qword ptr [rsp+68h+Buffer]; Format
0x14000325f  test    rcx, rcx
0x140003262  jz      short loc_14000326C
0x140003264  call    cs:__imp_wprintf
0x14000326a  jmp     short loc_140003288
0x14000326c  mov     r8d, [rsp+68h+arg_8]
0x140003271  cmp     r8d, 0C0A0002Eh
0x140003278  jz      short loc_140003288
0x14000327a  mov     edx, 0C0A0002Eh; int
0x14000327f  mov     rcx, rbx; this
0x140003282  call    ?PrintConsoleMessage@CBdeCfgConsole@@AEAAJJZZ; CBdeCfgConsole::PrintConsoleMessage(long,...)
0x140003287  nop
0x140003288  mov     rcx, qword ptr [rsp+68h+Buffer]; hMem
0x14000328d  test    rcx, rcx
0x140003290  jz      short loc_140003298
0x140003292  call    cs:__imp_LocalFree
0x140003298  mov     rcx, [rsp+68h+lpSource]; Block
0x14000329d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400032a2  xor     eax, eax
0x1400032a4  add     rsp, 60h
0x1400032a8  pop     rbx
0x1400032a9  retn
0x140004725  push    rbp
0x140004727  sub     rsp, 40h
0x14000472b  mov     rbp, rdx
0x14000472e  mov     rcx, [rbp+40h]; hMem
0x140004732  test    rcx, rcx
0x140004735  jz      short loc_14000473E
0x140004737  call    cs:__imp_LocalFree
0x14000473d  nop
0x14000473e  mov     rcx, [rbp+48h]; Block
0x140004742  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004747  nop
0x140004748  add     rsp, 40h
0x14000474c  pop     rbp
0x14000474d  retn
```
