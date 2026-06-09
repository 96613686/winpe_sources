# __abi_WinRTraiseException(long)

- ea: `0x18000b6b8`
- end: `0x18000b798`
- name: `?__abi_WinRTraiseException@@YAXJ@Z`
- size: `224`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `177`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800022c0`
- `0x180005024`
- `0x18000b5cc`
- `0x18000b818`
- `0x18000b928`
- `0x18004c8d0`
- `0x18004e1a4`
- `0x18004fed4`
- `0x1800500c8`
- `0x1800501a8`
- `0x180050290`
- `0x1800502e0`
- `0x1800503f4`
- `0x1800504b4`
- `0x180051ac0`
- `0x180051d9c`
- `0x180051e34`
- `0x180051ec4`
- `0x180052e40`
- `0x180052e98`
- `0x180052f20`
- `0x180052fa4`
- `0x180053ee0`
- `0x180054480`
- `0x180054530`
- `0x1800545e0`
- `0x180054acc`
- `0x180054bec`
- `0x180054c74`
- `0x180054d14`
- `0x180054dd4`
- `0x180054e64`
- `0x180054ef4`
- `0x180054f84`
- `0x180055014`
- `0x1800550a4`
- `0x1800551d0`
- `0x180055240`
- `0x180060878`
- `0x180060904`
- `0x1800609c0`
- `0x180060a3c`
- `0x180060ab8`
- `0x180060b34`
- `0x180060b78`
- `0x180060bbc`
- `0x180060c00`
- `0x180060c44`
- `0x180061c00`
- `0x180061c90`

## callees

- `0x18000b6b8`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseWrongThreadException@@YAXXZ` at `0x18000b78a`
- `wincorlib!?__abi_WinRTraiseWrongThreadException@@YAXXZ` at `0x18000b78a`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x18000b71b`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x18000b71b`
- `wincorlib!?__abi_WinRTraiseInvalidCastException@@YAXXZ` at `0x18000b70d`
- `wincorlib!?__abi_WinRTraiseInvalidCastException@@YAXXZ` at `0x18000b70d`
- `wincorlib!?__abi_WinRTraiseNotImplementedException@@YAXXZ` at `0x18000b714`
- `wincorlib!?__abi_WinRTraiseNotImplementedException@@YAXXZ` at `0x18000b714`
- `wincorlib!?__abi_WinRTraiseDisconnectedException@@YAXXZ` at `0x18000b791`
- `wincorlib!?__abi_WinRTraiseDisconnectedException@@YAXXZ` at `0x18000b791`
- `wincorlib!?__abi_WinRTraiseFailureException@@YAXXZ` at `0x18000b730`
- `wincorlib!?__abi_WinRTraiseFailureException@@YAXXZ` at `0x18000b730`
- `wincorlib!?__abi_WinRTraiseOperationCanceledException@@YAXXZ` at `0x18000b6ff`
- `wincorlib!?__abi_WinRTraiseOperationCanceledException@@YAXXZ` at `0x18000b6ff`
- `wincorlib!?__abi_WinRTraiseAccessDeniedException@@YAXXZ` at `0x18000b77c`
- `wincorlib!?__abi_WinRTraiseAccessDeniedException@@YAXXZ` at `0x18000b77c`
- `wincorlib!?__abi_WinRTraiseInvalidArgumentException@@YAXXZ` at `0x18000b76e`
- `wincorlib!?__abi_WinRTraiseInvalidArgumentException@@YAXXZ` at `0x18000b76e`
- `wincorlib!?__abi_WinRTraiseClassNotRegisteredException@@YAXXZ` at `0x18000b783`
- `wincorlib!?__abi_WinRTraiseClassNotRegisteredException@@YAXXZ` at `0x18000b783`
- `wincorlib!?__abi_WinRTraiseCOMException@@YAXJ@Z` at `0x18000b767`
- `wincorlib!?__abi_WinRTraiseCOMException@@YAXJ@Z` at `0x18000b767`
- `wincorlib!?__abi_WinRTraiseNullReferenceException@@YAXXZ` at `0x18000b706`
- `wincorlib!?__abi_WinRTraiseNullReferenceException@@YAXXZ` at `0x18000b706`
- `wincorlib!?__abi_WinRTraiseChangedStateException@@YAXXZ` at `0x18000b722`
- `wincorlib!?__abi_WinRTraiseChangedStateException@@YAXXZ` at `0x18000b722`
- `wincorlib!?__abi_WinRTraiseOutOfBoundsException@@YAXXZ` at `0x18000b729`
- `wincorlib!?__abi_WinRTraiseOutOfBoundsException@@YAXXZ` at `0x18000b729`
- `wincorlib!?__abi_WinRTraiseOutOfMemoryException@@YAXXZ` at `0x18000b775`
- `wincorlib!?__abi_WinRTraiseOutOfMemoryException@@YAXXZ` at `0x18000b775`

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
        JUMPOUT(0x18000B797LL);
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
0x18000b6b8  sub     rsp, 28h
0x18000b6bc  mov     eax, 80004005h
0x18000b6c1  cmp     ecx, eax
0x18000b6c3  jg      short loc_18000B737
0x18000b6c5  jz      short loc_18000B730
0x18000b6c7  cmp     ecx, 8000000Bh
0x18000b6cd  jz      short loc_18000B729
0x18000b6cf  cmp     ecx, 8000000Ch
0x18000b6d5  jz      short loc_18000B722
0x18000b6d7  cmp     ecx, 80000013h
0x18000b6dd  jz      short loc_18000B71B
0x18000b6df  cmp     ecx, 80004001h
0x18000b6e5  jz      short loc_18000B714
0x18000b6e7  cmp     ecx, 80004002h
0x18000b6ed  jz      short loc_18000B70D
0x18000b6ef  cmp     ecx, 80004003h
0x18000b6f5  jz      short loc_18000B706
0x18000b6f7  cmp     ecx, 80004004h
0x18000b6fd  jnz     short loc_18000B767
0x18000b6ff  call    cs:__imp_?__abi_WinRTraiseOperationCanceledException@@YAXXZ; __abi_WinRTraiseOperationCanceledException(void)
0x18000b705  int     3; Trap to Debugger
0x18000b706  call    cs:__imp_?__abi_WinRTraiseNullReferenceException@@YAXXZ; __abi_WinRTraiseNullReferenceException(void)
0x18000b70c  int     3; Trap to Debugger
0x18000b70d  call    cs:__imp_?__abi_WinRTraiseInvalidCastException@@YAXXZ; __abi_WinRTraiseInvalidCastException(void)
0x18000b713  int     3; Trap to Debugger
0x18000b714  call    cs:__imp_?__abi_WinRTraiseNotImplementedException@@YAXXZ; __abi_WinRTraiseNotImplementedException(void)
0x18000b71a  int     3; Trap to Debugger
0x18000b71b  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x18000b721  int     3; Trap to Debugger
0x18000b722  call    cs:__imp_?__abi_WinRTraiseChangedStateException@@YAXXZ; __abi_WinRTraiseChangedStateException(void)
0x18000b728  int     3; Trap to Debugger
0x18000b729  call    cs:__imp_?__abi_WinRTraiseOutOfBoundsException@@YAXXZ; __abi_WinRTraiseOutOfBoundsException(void)
0x18000b72f  int     3; Trap to Debugger
0x18000b730  call    cs:__imp_?__abi_WinRTraiseFailureException@@YAXXZ; __abi_WinRTraiseFailureException(void)
0x18000b736  int     3; Trap to Debugger
0x18000b737  cmp     ecx, 80010108h
0x18000b73d  jz      short loc_18000B791
0x18000b73f  cmp     ecx, 8001010Eh
0x18000b745  jz      short loc_18000B78A
0x18000b747  cmp     ecx, 80040154h
0x18000b74d  jz      short loc_18000B783
0x18000b74f  cmp     ecx, 80070005h
0x18000b755  jz      short loc_18000B77C
0x18000b757  cmp     ecx, 8007000Eh
0x18000b75d  jz      short loc_18000B775
0x18000b75f  cmp     ecx, 80070057h
0x18000b765  jz      short loc_18000B76E
0x18000b767  call    cs:__imp_?__abi_WinRTraiseCOMException@@YAXJ@Z; __abi_WinRTraiseCOMException(long)
0x18000b76d  int     3; Trap to Debugger
0x18000b76e  call    cs:__imp_?__abi_WinRTraiseInvalidArgumentException@@YAXXZ; __abi_WinRTraiseInvalidArgumentException(void)
0x18000b774  int     3; Trap to Debugger
0x18000b775  call    cs:__imp_?__abi_WinRTraiseOutOfMemoryException@@YAXXZ; __abi_WinRTraiseOutOfMemoryException(void)
0x18000b77b  int     3; Trap to Debugger
0x18000b77c  call    cs:__imp_?__abi_WinRTraiseAccessDeniedException@@YAXXZ; __abi_WinRTraiseAccessDeniedException(void)
0x18000b782  int     3; Trap to Debugger
0x18000b783  call    cs:__imp_?__abi_WinRTraiseClassNotRegisteredException@@YAXXZ; __abi_WinRTraiseClassNotRegisteredException(void)
0x18000b789  int     3; Trap to Debugger
0x18000b78a  call    cs:__imp_?__abi_WinRTraiseWrongThreadException@@YAXXZ; __abi_WinRTraiseWrongThreadException(void)
0x18000b790  int     3; Trap to Debugger
0x18000b791  call    cs:__imp_?__abi_WinRTraiseDisconnectedException@@YAXXZ; __abi_WinRTraiseDisconnectedException(void)
```
