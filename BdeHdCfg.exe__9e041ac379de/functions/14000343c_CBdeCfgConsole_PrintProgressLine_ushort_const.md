# CBdeCfgConsole::PrintProgressLine(ushort const *)

- ea: `0x14000343c`
- end: `0x14000350c`
- name: `?PrintProgressLine@CBdeCfgConsole@@AEAAXPEBG@Z`
- size: `208`
- prototype: `void __fastcall(CBdeCfgConsole *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002a00`
- `0x140004010`

## callees

- `0x14000343c`
- `0x140004460`

## import_xrefs

- `KERNEL32!SetConsoleCursorPosition` at `0x1400034d9`
- `KERNEL32!SetConsoleCursorPosition` at `0x1400034d9`
- `KERNEL32!FillConsoleOutputCharacterW` at `0x1400034c8`
- `KERNEL32!FillConsoleOutputCharacterW` at `0x1400034c8`
- `KERNEL32!GetConsoleScreenBufferInfo` at `0x140003494`
- `KERNEL32!GetConsoleScreenBufferInfo` at `0x140003494`
- `KERNEL32!GetStdHandle` at `0x14000347d`
- `KERNEL32!GetStdHandle` at `0x14000347d`
- `msvcrt!wprintf` at `0x1400034ed`
- `msvcrt!wprintf` at `0x1400034ed`

## pseudocode

```c
void __fastcall CBdeCfgConsole::PrintProgressLine(CBdeCfgConsole *this, const unsigned __int16 *a2)
{
  HANDLE StdHandle; // rax
  void *v4; // rbx
  COORD dwWriteCoord; // [rsp+30h] [rbp-38h]
  DWORD NumberOfCharsWritten; // [rsp+34h] [rbp-34h] BYREF
  _CONSOLE_SCREEN_BUFFER_INFO ConsoleScreenBufferInfo; // [rsp+38h] [rbp-30h] BYREF

  NumberOfCharsWritten = 0;
  memset(&ConsoleScreenBufferInfo, 0, sizeof(ConsoleScreenBufferInfo));
  if ( *((_BYTE *)this + 1384) != 1 )
  {
    StdHandle = GetStdHandle(0xFFFFFFF5);
    v4 = StdHandle;
    if ( StdHandle != (HANDLE)-1LL )
    {
      if ( GetConsoleScreenBufferInfo(StdHandle, &ConsoleScreenBufferInfo) )
      {
        dwWriteCoord.Y = ConsoleScreenBufferInfo.dwCursorPosition.Y;
        dwWriteCoord.X = 0;
        if ( FillConsoleOutputCharacterW(
               v4,
               0x20u,
               ConsoleScreenBufferInfo.dwSize.X,
               dwWriteCoord,
               &NumberOfCharsWritten) )
        {
          if ( SetConsoleCursorPosition(v4, dwWriteCoord) )
            wprintf(L"%s", a2);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14000343c  mov     [rsp+arg_0], rbx
0x140003441  push    rdi
0x140003442  sub     rsp, 60h
0x140003446  mov     rax, cs:__security_cookie
0x14000344d  xor     rax, rsp
0x140003450  mov     [rsp+68h+var_18], rax
0x140003455  mov     rdi, rdx
0x140003458  mov     [rsp+68h+NumberOfCharsWritten], 0
0x140003460  xorps   xmm0, xmm0
0x140003463  xor     eax, eax
0x140003465  movups  xmmword ptr [rsp+68h+ConsoleScreenBufferInfo.dwSize.X], xmm0
0x14000346a  mov     qword ptr [rsp+68h+ConsoleScreenBufferInfo.srWindow.Right], rax
0x14000346f  cmp     byte ptr [rcx+568h], 1
0x140003476  jz      short loc_1400034F4
0x140003478  mov     ecx, 0FFFFFFF5h; nStdHandle
0x14000347d  call    cs:__imp_GetStdHandle
0x140003483  mov     rbx, rax
0x140003486  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000348a  jz      short loc_1400034F4
0x14000348c  lea     rdx, [rsp+68h+ConsoleScreenBufferInfo]; lpConsoleScreenBufferInfo
0x140003491  mov     rcx, rax; hConsoleOutput
0x140003494  call    cs:__imp_GetConsoleScreenBufferInfo
0x14000349a  test    eax, eax
0x14000349c  jz      short loc_1400034F4
0x14000349e  mov     ecx, dword ptr [rsp+68h+ConsoleScreenBufferInfo.dwCursorPosition.X]
0x1400034a2  mov     dword ptr [rsp+68h+dwWriteCoord.X], ecx
0x1400034a6  movsx   r8d, [rsp+68h+ConsoleScreenBufferInfo.dwSize.X]; nLength
0x1400034ac  xor     ecx, ecx
0x1400034ae  mov     [rsp+68h+dwWriteCoord.X], cx
0x1400034b3  lea     edx, [rcx+20h]; cCharacter
0x1400034b6  lea     rax, [rsp+68h+NumberOfCharsWritten]
0x1400034bb  mov     [rsp+68h+lpNumberOfCharsWritten], rax; lpNumberOfCharsWritten
0x1400034c0  mov     r9d, dword ptr [rsp+68h+dwWriteCoord.X]; dwWriteCoord
0x1400034c5  mov     rcx, rbx; hConsoleOutput
0x1400034c8  call    cs:__imp_FillConsoleOutputCharacterW
0x1400034ce  test    eax, eax
0x1400034d0  jz      short loc_1400034F4
0x1400034d2  mov     edx, dword ptr [rsp+68h+dwWriteCoord.X]; dwCursorPosition
0x1400034d6  mov     rcx, rbx; hConsoleOutput
0x1400034d9  call    cs:__imp_SetConsoleCursorPosition
0x1400034df  test    eax, eax
0x1400034e1  jz      short loc_1400034F4
0x1400034e3  mov     rdx, rdi
0x1400034e6  lea     rcx, aS; "%s"
0x1400034ed  call    cs:__imp_wprintf
0x1400034f3  nop
0x1400034f4  mov     rcx, [rsp+68h+var_18]
0x1400034f9  xor     rcx, rsp; StackCookie
0x1400034fc  call    __security_check_cookie
0x140003501  mov     rbx, [rsp+68h+arg_0]
0x140003506  add     rsp, 60h
0x14000350a  pop     rdi
0x14000350b  retn
0x140004650  push    rbp
0x140004652  sub     rsp, 30h
0x140004656  mov     rbp, rdx
0x140004659  add     rsp, 30h
0x14000465d  pop     rbp
0x14000465e  retn
```
