# __abi_WinRTraiseException(long)

- ea: `0x1400086b0`
- end: `0x140008790`
- name: `?__abi_WinRTraiseException@@YAXJ@Z`
- size: `224`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `180`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004518`
- `0x140004970`
- `0x1400049dc`
- `0x140005944`
- `0x140005bb0`
- `0x140005d24`
- `0x140005fa4`
- `0x1400061e0`
- `0x140006240`
- `0x1400062a0`
- `0x140006300`
- `0x140006360`
- `0x1400063c0`
- `0x140006420`
- `0x140006480`
- `0x140007a90`
- `0x140007b20`
- `0x140007bb0`
- `0x140007c40`
- `0x140007cd0`
- `0x140007d60`
- `0x140007df0`
- `0x140007e80`
- `0x140008470`
- `0x14000883c`
- `0x140008900`
- `0x14000b3b0`
- `0x14000b5cc`
- `0x14000b750`
- `0x14000b8f8`
- `0x14000b9ec`
- `0x14000bbc8`
- `0x14000bc58`
- `0x14000bfd8`
- `0x14000c11c`
- `0x14000c1e0`
- `0x14000c280`
- `0x14000c4e0`
- `0x14000c5a0`
- `0x14000c5f0`
- `0x14000c640`
- `0x14000c784`
- `0x14000d0c0`
- `0x14000d180`
- `0x14000d240`
- `0x14000d300`
- `0x14000d3c0`
- `0x14000daf8`
- `0x14000dbb0`
- `0x14000dc70`

## callees

- `0x1400086b0`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseNotImplementedException@@YAXXZ` at `0x14000870c`
- `wincorlib!?__abi_WinRTraiseNotImplementedException@@YAXXZ` at `0x14000870c`
- `wincorlib!?__abi_WinRTraiseInvalidCastException@@YAXXZ` at `0x140008705`
- `wincorlib!?__abi_WinRTraiseInvalidCastException@@YAXXZ` at `0x140008705`
- `wincorlib!?__abi_WinRTraiseNullReferenceException@@YAXXZ` at `0x1400086fe`
- `wincorlib!?__abi_WinRTraiseNullReferenceException@@YAXXZ` at `0x1400086fe`
- `wincorlib!?__abi_WinRTraiseOperationCanceledException@@YAXXZ` at `0x1400086f7`
- `wincorlib!?__abi_WinRTraiseOperationCanceledException@@YAXXZ` at `0x1400086f7`
- `wincorlib!?__abi_WinRTraiseFailureException@@YAXXZ` at `0x140008728`
- `wincorlib!?__abi_WinRTraiseFailureException@@YAXXZ` at `0x140008728`
- `wincorlib!?__abi_WinRTraiseAccessDeniedException@@YAXXZ` at `0x140008774`
- `wincorlib!?__abi_WinRTraiseAccessDeniedException@@YAXXZ` at `0x140008774`
- `wincorlib!?__abi_WinRTraiseOutOfMemoryException@@YAXXZ` at `0x14000876d`
- `wincorlib!?__abi_WinRTraiseOutOfMemoryException@@YAXXZ` at `0x14000876d`
- `wincorlib!?__abi_WinRTraiseInvalidArgumentException@@YAXXZ` at `0x140008766`
- `wincorlib!?__abi_WinRTraiseInvalidArgumentException@@YAXXZ` at `0x140008766`
- `wincorlib!?__abi_WinRTraiseOutOfBoundsException@@YAXXZ` at `0x140008721`
- `wincorlib!?__abi_WinRTraiseOutOfBoundsException@@YAXXZ` at `0x140008721`
- `wincorlib!?__abi_WinRTraiseChangedStateException@@YAXXZ` at `0x14000871a`
- `wincorlib!?__abi_WinRTraiseChangedStateException@@YAXXZ` at `0x14000871a`
- `wincorlib!?__abi_WinRTraiseClassNotRegisteredException@@YAXXZ` at `0x14000877b`
- `wincorlib!?__abi_WinRTraiseClassNotRegisteredException@@YAXXZ` at `0x14000877b`
- `wincorlib!?__abi_WinRTraiseWrongThreadException@@YAXXZ` at `0x140008782`
- `wincorlib!?__abi_WinRTraiseWrongThreadException@@YAXXZ` at `0x140008782`
- `wincorlib!?__abi_WinRTraiseDisconnectedException@@YAXXZ` at `0x140008789`
- `wincorlib!?__abi_WinRTraiseDisconnectedException@@YAXXZ` at `0x140008789`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140008713`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140008713`
- `wincorlib!?__abi_WinRTraiseCOMException@@YAXJ@Z` at `0x14000875f`
- `wincorlib!?__abi_WinRTraiseCOMException@@YAXJ@Z` at `0x14000875f`

## pseudocode

```c
void __fastcall __noreturn __abi_WinRTraiseException(int a1)
{
  if ( a1 > -2147467259 )
  {
    switch ( a1 )
    {
      case -2147417848:
        __abi_WinRTraiseDisconnectedException();
        JUMPOUT(0x14000878FLL);
      case -2147417842:
        __abi_WinRTraiseWrongThreadException();
        __debugbreak();
      case -2147221164:
        __abi_WinRTraiseClassNotRegisteredException();
        __debugbreak();
      case -2147024891:
        __abi_WinRTraiseAccessDeniedException();
        __debugbreak();
      case -2147024882:
        __abi_WinRTraiseOutOfMemoryException();
        __debugbreak();
      case -2147024809:
        __abi_WinRTraiseInvalidArgumentException();
        __debugbreak();
    }
  }
  else
  {
    switch ( a1 )
    {
      case -2147467259:
        __abi_WinRTraiseFailureException();
        __debugbreak();
      case -2147483637:
        __abi_WinRTraiseOutOfBoundsException();
        __debugbreak();
      case -2147483636:
        __abi_WinRTraiseChangedStateException();
        __debugbreak();
      case -2147483629:
        __abi_WinRTraiseObjectDisposedException();
        __debugbreak();
      case -2147467263:
        __abi_WinRTraiseNotImplementedException();
        __debugbreak();
      case -2147467262:
        __abi_WinRTraiseInvalidCastException();
        __debugbreak();
      case -2147467261:
        __abi_WinRTraiseNullReferenceException();
        __debugbreak();
      case -2147467260:
        __abi_WinRTraiseOperationCanceledException();
        __debugbreak();
    }
  }
  __abi_WinRTraiseCOMException(a1);
  __debugbreak();
}

```

## disassembly

```asm
0x1400086b0  sub     rsp, 28h
0x1400086b4  mov     eax, 80004005h
0x1400086b9  cmp     ecx, eax
0x1400086bb  jg      short loc_14000872F
0x1400086bd  jz      short loc_140008728
0x1400086bf  cmp     ecx, 8000000Bh
0x1400086c5  jz      short loc_140008721
0x1400086c7  cmp     ecx, 8000000Ch
0x1400086cd  jz      short loc_14000871A
0x1400086cf  cmp     ecx, 80000013h
0x1400086d5  jz      short loc_140008713
0x1400086d7  cmp     ecx, 80004001h
0x1400086dd  jz      short loc_14000870C
0x1400086df  cmp     ecx, 80004002h
0x1400086e5  jz      short loc_140008705
0x1400086e7  cmp     ecx, 80004003h
0x1400086ed  jz      short loc_1400086FE
0x1400086ef  cmp     ecx, 80004004h
0x1400086f5  jnz     short loc_14000875F
0x1400086f7  call    cs:__imp_?__abi_WinRTraiseOperationCanceledException@@YAXXZ; __abi_WinRTraiseOperationCanceledException(void)
0x1400086fd  int     3; Trap to Debugger
0x1400086fe  call    cs:__imp_?__abi_WinRTraiseNullReferenceException@@YAXXZ; __abi_WinRTraiseNullReferenceException(void)
0x140008704  int     3; Trap to Debugger
0x140008705  call    cs:__imp_?__abi_WinRTraiseInvalidCastException@@YAXXZ; __abi_WinRTraiseInvalidCastException(void)
0x14000870b  int     3; Trap to Debugger
0x14000870c  call    cs:__imp_?__abi_WinRTraiseNotImplementedException@@YAXXZ; __abi_WinRTraiseNotImplementedException(void)
0x140008712  int     3; Trap to Debugger
0x140008713  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140008719  int     3; Trap to Debugger
0x14000871a  call    cs:__imp_?__abi_WinRTraiseChangedStateException@@YAXXZ; __abi_WinRTraiseChangedStateException(void)
0x140008720  int     3; Trap to Debugger
0x140008721  call    cs:__imp_?__abi_WinRTraiseOutOfBoundsException@@YAXXZ; __abi_WinRTraiseOutOfBoundsException(void)
0x140008727  int     3; Trap to Debugger
0x140008728  call    cs:__imp_?__abi_WinRTraiseFailureException@@YAXXZ; __abi_WinRTraiseFailureException(void)
0x14000872e  int     3; Trap to Debugger
0x14000872f  cmp     ecx, 80010108h
0x140008735  jz      short loc_140008789
0x140008737  cmp     ecx, 8001010Eh
0x14000873d  jz      short loc_140008782
0x14000873f  cmp     ecx, 80040154h
0x140008745  jz      short loc_14000877B
0x140008747  cmp     ecx, 80070005h
0x14000874d  jz      short loc_140008774
0x14000874f  cmp     ecx, 8007000Eh
0x140008755  jz      short loc_14000876D
0x140008757  cmp     ecx, 80070057h
0x14000875d  jz      short loc_140008766
0x14000875f  call    cs:__imp_?__abi_WinRTraiseCOMException@@YAXJ@Z; __abi_WinRTraiseCOMException(long)
0x140008765  int     3; Trap to Debugger
0x140008766  call    cs:__imp_?__abi_WinRTraiseInvalidArgumentException@@YAXXZ; __abi_WinRTraiseInvalidArgumentException(void)
0x14000876c  int     3; Trap to Debugger
0x14000876d  call    cs:__imp_?__abi_WinRTraiseOutOfMemoryException@@YAXXZ; __abi_WinRTraiseOutOfMemoryException(void)
0x140008773  int     3; Trap to Debugger
0x140008774  call    cs:__imp_?__abi_WinRTraiseAccessDeniedException@@YAXXZ; __abi_WinRTraiseAccessDeniedException(void)
0x14000877a  int     3; Trap to Debugger
0x14000877b  call    cs:__imp_?__abi_WinRTraiseClassNotRegisteredException@@YAXXZ; __abi_WinRTraiseClassNotRegisteredException(void)
0x140008781  int     3; Trap to Debugger
0x140008782  call    cs:__imp_?__abi_WinRTraiseWrongThreadException@@YAXXZ; __abi_WinRTraiseWrongThreadException(void)
0x140008788  int     3; Trap to Debugger
0x140008789  call    cs:__imp_?__abi_WinRTraiseDisconnectedException@@YAXXZ; __abi_WinRTraiseDisconnectedException(void)
```
