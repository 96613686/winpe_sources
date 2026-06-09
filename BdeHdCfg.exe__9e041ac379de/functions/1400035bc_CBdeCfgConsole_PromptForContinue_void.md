# CBdeCfgConsole::PromptForContinue(void)

- ea: `0x1400035bc`
- end: `0x1400037fb`
- name: `?PromptForContinue@CBdeCfgConsole@@AEAAJXZ`
- size: `575`
- prototype: `__int64 __fastcall(CBdeCfgConsole *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140003554`
- `0x140003804`

## callees

- `0x140001008`
- `0x1400035bc`

## import_xrefs

- `KERNEL32!ReadConsoleW` at `0x140003728`
- `KERNEL32!ReadConsoleW` at `0x140003728`
- `KERNEL32!SetConsoleMode` at `0x1400036e4`
- `KERNEL32!SetConsoleMode` at `0x1400037e2`
- `KERNEL32!SetConsoleMode` at `0x1400047b9`
- `KERNEL32!SetConsoleMode` at `0x1400036e4`
- `KERNEL32!SetConsoleMode` at `0x1400037e2`
- `KERNEL32!SetConsoleMode` at `0x1400047b9`
- `KERNEL32!GetConsoleMode` at `0x1400036c9`
- `KERNEL32!GetConsoleMode` at `0x1400036c9`
- `KERNEL32!FormatMessageW` at `0x14000368f`
- `KERNEL32!FormatMessageW` at `0x14000368f`
- `KERNEL32!LocalFree` at `0x1400037c4`
- `KERNEL32!LocalFree` at `0x14000479b`
- `KERNEL32!LocalFree` at `0x1400037c4`
- `KERNEL32!LocalFree` at `0x14000479b`
- `KERNEL32!GetLastError` at `0x14000378c`
- `KERNEL32!GetLastError` at `0x14000378c`
- `KERNEL32!GetStdHandle` at `0x1400036a2`
- `KERNEL32!GetStdHandle` at `0x1400036a2`
- `msvcrt!towupper` at `0x14000373a`
- `msvcrt!towupper` at `0x14000373a`
- `msvcrt!wprintf` at `0x140003703`
- `msvcrt!wprintf` at `0x140003752`
- `msvcrt!wprintf` at `0x14000377f`
- `msvcrt!wprintf` at `0x140003703`
- `msvcrt!wprintf` at `0x140003752`
- `msvcrt!wprintf` at `0x14000377f`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003609`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003623`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x14000363d`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003609`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003623`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x14000363d`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::PromptForContinue(CBdeCfgConsole *this)
{
  signed int ResourceString; // ebx
  char *v2; // rdi
  char *StdHandle; // rax
  signed int LastError; // eax
  void *Block; // [rsp+40h] [rbp-48h] BYREF
  void *v7; // [rsp+48h] [rbp-40h] BYREF
  LPCVOID lpSource; // [rsp+50h] [rbp-38h] BYREF
  WCHAR Buffer[4]; // [rsp+58h] [rbp-30h] BYREF
  char *v10; // [rsp+60h] [rbp-28h]
  __int128 Arguments; // [rsp+68h] [rbp-20h] BYREF
  int v12; // [rsp+98h] [rbp+10h] BYREF
  DWORD Mode; // [rsp+A0h] [rbp+18h] BYREF
  DWORD NumberOfCharsRead; // [rsp+A8h] [rbp+20h] BYREF

  ResourceString = 0;
  lpSource = 0;
  *(_QWORD *)Buffer = 0;
  Block = 0;
  v7 = 0;
  v2 = 0;
  v10 = 0;
  Mode = 0;
  v12 = 0;
  NumberOfCharsRead = 0;
  Arguments = 0;
  if ( !*((_BYTE *)this + 1384) )
  {
    ResourceString = BdeCfgLoadResourceString(0xCFu, (unsigned __int16 **)&lpSource);
    if ( ResourceString >= 0 )
    {
      ResourceString = BdeCfgLoadResourceString(0xD0u, (unsigned __int16 **)&Block);
      if ( ResourceString >= 0 )
      {
        ResourceString = BdeCfgLoadResourceString(0xD1u, (unsigned __int16 **)&v7);
        if ( ResourceString >= 0 )
        {
          *(_QWORD *)&Arguments = *(unsigned __int16 *)Block;
          *((_QWORD *)&Arguments + 1) = *(unsigned __int16 *)v7;
          if ( FormatMessageW(0x2500u, lpSource, 0, 0, Buffer, 0, (va_list *)&Arguments) )
          {
            StdHandle = (char *)GetStdHandle(0xFFFFFFF6);
            v2 = StdHandle;
            v10 = StdHandle;
            if ( (unsigned __int64)(StdHandle - 1) <= 0xFFFFFFFFFFFFFFFDuLL
              && GetConsoleMode(StdHandle, &Mode)
              && SetConsoleMode(v2, Mode & 0xFFFFFFF9) )
            {
              ResourceString = 1;
              while ( 1 )
              {
                wprintf(L"\n%s", *(_QWORD *)Buffer);
                if ( !ReadConsoleW(v2, &v12, 1u, &NumberOfCharsRead, 0) )
                  break;
                LOWORD(v12) = towupper(v12);
                wprintf(L"%c");
                if ( (_WORD)v12 == *(_WORD *)Block )
                {
                  ResourceString = 0;
LABEL_14:
                  wprintf(L"\r\n\r\n");
                  goto LABEL_18;
                }
                if ( (_WORD)v12 == *(_WORD *)v7 )
                  goto LABEL_14;
              }
            }
          }
          LastError = GetLastError();
          ResourceString = LastError;
          if ( LastError > 0 )
            ResourceString = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
LABEL_18:
  operator delete((void *)lpSource);
  operator delete(Block);
  operator delete(v7);
  LocalFree(*(HLOCAL *)Buffer);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && Mode )
    SetConsoleMode(v2, Mode);
  return (unsigned int)ResourceString;
}

```

## disassembly

```asm
0x1400035bc  mov     rax, rsp
0x1400035bf  mov     [rax+8], rbx
0x1400035c3  push    rdi
0x1400035c4  sub     rsp, 80h
0x1400035cb  xor     ebx, ebx
0x1400035cd  mov     [rax-38h], rbx
0x1400035d1  mov     [rax-30h], rbx
0x1400035d5  mov     [rax-48h], rbx
0x1400035d9  mov     [rax-40h], rbx
0x1400035dd  xor     edi, edi
0x1400035df  mov     [rax-28h], rdi
0x1400035e3  mov     [rax+18h], ebx
0x1400035e6  mov     [rax+10h], ebx
0x1400035e9  mov     [rax+20h], ebx
0x1400035ec  xorps   xmm0, xmm0
0x1400035ef  movups  xmmword ptr [rax-20h], xmm0
0x1400035f3  cmp     [rcx+568h], dil
0x1400035fa  jnz     loc_1400037A1
0x140003600  lea     rdx, [rax-38h]
0x140003604  mov     ecx, 0CFh
0x140003609  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x14000360f  mov     ebx, eax
0x140003611  test    eax, eax
0x140003613  js      loc_1400037A1
0x140003619  lea     rdx, [rsp+88h+Block]
0x14000361e  mov     ecx, 0D0h
0x140003623  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x140003629  mov     ebx, eax
0x14000362b  test    eax, eax
0x14000362d  js      loc_1400037A1
0x140003633  lea     rdx, [rsp+88h+var_40]
0x140003638  mov     ecx, 0D1h
0x14000363d  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x140003643  mov     ebx, eax
0x140003645  test    eax, eax
0x140003647  js      loc_1400037A1
0x14000364d  mov     rax, [rsp+88h+Block]
0x140003652  movzx   ecx, word ptr [rax]
0x140003655  mov     [rsp+88h+var_20], rcx
0x14000365a  mov     rax, [rsp+88h+var_40]
0x14000365f  movzx   ecx, word ptr [rax]
0x140003662  mov     [rsp+88h+var_18], rcx
0x140003667  lea     rax, [rsp+88h+var_20]
0x14000366c  mov     [rsp+88h+Arguments], rax; Arguments
0x140003671  mov     [rsp+88h+nSize], edi; nSize
0x140003675  lea     rax, [rsp+88h+Buffer]
0x14000367a  mov     [rsp+88h+lpBuffer], rax; lpBuffer
0x14000367f  xor     r9d, r9d; dwLanguageId
0x140003682  xor     r8d, r8d; dwMessageId
0x140003685  mov     rdx, [rsp+88h+lpSource]; lpSource
0x14000368a  mov     ecx, 2500h; dwFlags
0x14000368f  call    cs:__imp_FormatMessageW
0x140003695  test    eax, eax
0x140003697  jz      loc_14000378C
0x14000369d  mov     ecx, 0FFFFFFF6h; nStdHandle
0x1400036a2  call    cs:__imp_GetStdHandle
0x1400036a8  mov     rdi, rax
0x1400036ab  mov     [rsp+88h+var_28], rax
0x1400036b0  lea     rcx, [rax-1]
0x1400036b4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1400036b8  ja      loc_14000378C
0x1400036be  lea     rdx, [rsp+88h+Mode]; lpMode
0x1400036c6  mov     rcx, rax; hConsoleHandle
0x1400036c9  call    cs:__imp_GetConsoleMode
0x1400036cf  test    eax, eax
0x1400036d1  jz      loc_14000378C
0x1400036d7  mov     edx, [rsp+88h+Mode]
0x1400036de  and     edx, 0FFFFFFF9h; dwMode
0x1400036e1  mov     rcx, rdi; hConsoleHandle
0x1400036e4  call    cs:__imp_SetConsoleMode
0x1400036ea  test    eax, eax
0x1400036ec  jz      loc_14000378C
0x1400036f2  mov     ebx, 1
0x1400036f7  mov     rdx, qword ptr [rsp+88h+Buffer]
0x1400036fc  lea     rcx, aS_0; "\n%s"
0x140003703  call    cs:__imp_wprintf
0x140003709  mov     [rsp+88h+lpBuffer], 0; pInputControl
0x140003712  lea     r9, [rsp+88h+NumberOfCharsRead]; lpNumberOfCharsRead
0x14000371a  mov     r8d, ebx; nNumberOfCharsToRead
0x14000371d  lea     rdx, [rsp+88h+arg_8]; lpBuffer
0x140003725  mov     rcx, rdi; hConsoleInput
0x140003728  call    cs:__imp_ReadConsoleW
0x14000372e  test    eax, eax
0x140003730  jz      short loc_14000378C
0x140003732  movzx   ecx, word ptr [rsp+88h+arg_8]; C
0x14000373a  call    cs:__imp_towupper
0x140003740  movzx   edx, ax
0x140003743  mov     word ptr [rsp+88h+arg_8], dx
0x14000374b  lea     rcx, aC; "%c"
0x140003752  call    cs:__imp_wprintf
0x140003758  movzx   ecx, word ptr [rsp+88h+arg_8]
0x140003760  mov     rax, [rsp+88h+Block]
0x140003765  cmp     cx, [rax]
0x140003768  jnz     short loc_14000376E
0x14000376a  xor     ebx, ebx
0x14000376c  jmp     short loc_140003778
0x14000376e  mov     rax, [rsp+88h+var_40]
0x140003773  cmp     cx, [rax]
0x140003776  jnz     short loc_140003787
0x140003778  lea     rcx, asc_1400067C8; "\r\n\r\n"
0x14000377f  call    cs:__imp_wprintf
0x140003785  jmp     short loc_1400037A1
0x140003787  jmp     loc_1400036F7
0x14000378c  call    cs:__imp_GetLastError
0x140003792  mov     ebx, eax
0x140003794  test    eax, eax
0x140003796  jle     short loc_1400037A1
0x140003798  movzx   ebx, ax
0x14000379b  or      ebx, 80070000h
0x1400037a1  mov     rcx, [rsp+88h+lpSource]; Block
0x1400037a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400037ab  mov     rcx, [rsp+88h+Block]; Block
0x1400037b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400037b5  mov     rcx, [rsp+88h+var_40]; Block
0x1400037ba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400037bf  mov     rcx, qword ptr [rsp+88h+Buffer]; hMem
0x1400037c4  call    cs:__imp_LocalFree
0x1400037ca  lea     rax, [rdi-1]
0x1400037ce  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400037d2  ja      short loc_1400037E8
0x1400037d4  mov     edx, [rsp+88h+Mode]; dwMode
0x1400037db  test    edx, edx
0x1400037dd  jz      short loc_1400037E8
0x1400037df  mov     rcx, rdi; hConsoleHandle
0x1400037e2  call    cs:__imp_SetConsoleMode
0x1400037e8  mov     eax, ebx
0x1400037ea  mov     rbx, [rsp+88h+arg_0]
0x1400037f2  add     rsp, 80h
0x1400037f9  pop     rdi
0x1400037fa  retn
0x140004773  push    rbp
0x140004775  sub     rsp, 40h
0x140004779  mov     rbp, rdx
0x14000477c  mov     rcx, [rbp+50h]; Block
0x140004780  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004785  mov     rcx, [rbp+40h]; Block
0x140004789  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000478e  mov     rcx, [rbp+48h]; Block
0x140004792  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004797  mov     rcx, [rbp+58h]; hMem
0x14000479b  call    cs:__imp_LocalFree
0x1400047a1  mov     rcx, [rbp+60h]; hConsoleHandle
0x1400047a5  lea     rax, [rcx-1]
0x1400047a9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400047ad  ja      short loc_1400047C0
0x1400047af  mov     edx, [rbp+0A0h]; dwMode
0x1400047b5  test    edx, edx
0x1400047b7  jz      short loc_1400047C0
0x1400047b9  call    cs:__imp_SetConsoleMode
0x1400047bf  nop
0x1400047c0  add     rsp, 40h
0x1400047c4  pop     rbp
0x1400047c5  retn
```
