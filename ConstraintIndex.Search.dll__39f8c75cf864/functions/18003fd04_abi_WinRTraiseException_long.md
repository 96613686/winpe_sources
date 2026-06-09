# __abi_WinRTraiseException(long)

- ea: `0x18003fd04`
- end: `0x18003fde4`
- name: `?__abi_WinRTraiseException@@YAXJ@Z`
- size: `224`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `148`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004140`
- `0x1800041c0`
- `0x1800395d0`
- `0x18003a5f4`
- `0x18003b2f4`
- `0x18003b624`
- `0x18003b6f8`
- `0x18003c088`
- `0x18003c9d8`
- `0x18003cd30`
- `0x18003f990`
- `0x18003fe64`
- `0x18003ff00`
- `0x18003ff8c`
- `0x18004086c`
- `0x180080fa4`
- `0x180081220`
- `0x180084140`
- `0x180084d0c`
- `0x18008500c`
- `0x180086610`
- `0x180086680`
- `0x1800869b0`
- `0x180086b30`
- `0x180086bdc`
- `0x180086ccc`
- `0x180086d3c`
- `0x180086dac`
- `0x180086f1c`
- `0x180086f8c`
- `0x180087340`
- `0x180087488`
- `0x1800875d0`
- `0x180087718`
- `0x180087860`
- `0x180087934`
- `0x180087a08`
- `0x180087a78`
- `0x180087acc`
- `0x180087d30`
- `0x1800880fc`
- `0x1800884b4`
- `0x18008892c`
- `0x180088cd0`
- `0x180092490`
- `0x180092be4`
- `0x180092c54`
- `0x180092d24`
- `0x180092d94`
- `0x180092dcc`

## callees

- `0x18003fd04`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseNotImplementedException@@YAXXZ` at `0x18003fd60`
- `wincorlib!?__abi_WinRTraiseNotImplementedException@@YAXXZ` at `0x18003fd60`
- `wincorlib!?__abi_WinRTraiseInvalidCastException@@YAXXZ` at `0x18003fd59`
- `wincorlib!?__abi_WinRTraiseInvalidCastException@@YAXXZ` at `0x18003fd59`
- `wincorlib!?__abi_WinRTraiseNullReferenceException@@YAXXZ` at `0x18003fd52`
- `wincorlib!?__abi_WinRTraiseNullReferenceException@@YAXXZ` at `0x18003fd52`
- `wincorlib!?__abi_WinRTraiseOperationCanceledException@@YAXXZ` at `0x18003fd4b`
- `wincorlib!?__abi_WinRTraiseOperationCanceledException@@YAXXZ` at `0x18003fd4b`
- `wincorlib!?__abi_WinRTraiseFailureException@@YAXXZ` at `0x18003fd7c`
- `wincorlib!?__abi_WinRTraiseFailureException@@YAXXZ` at `0x18003fd7c`
- `wincorlib!?__abi_WinRTraiseOutOfMemoryException@@YAXXZ` at `0x18003fdc1`
- `wincorlib!?__abi_WinRTraiseOutOfMemoryException@@YAXXZ` at `0x18003fdc1`
- `wincorlib!?__abi_WinRTraiseInvalidArgumentException@@YAXXZ` at `0x18003fdba`
- `wincorlib!?__abi_WinRTraiseInvalidArgumentException@@YAXXZ` at `0x18003fdba`
- `wincorlib!?__abi_WinRTraiseOutOfBoundsException@@YAXXZ` at `0x18003fd75`
- `wincorlib!?__abi_WinRTraiseOutOfBoundsException@@YAXXZ` at `0x18003fd75`
- `wincorlib!?__abi_WinRTraiseChangedStateException@@YAXXZ` at `0x18003fd6e`
- `wincorlib!?__abi_WinRTraiseChangedStateException@@YAXXZ` at `0x18003fd6e`
- `wincorlib!?__abi_WinRTraiseClassNotRegisteredException@@YAXXZ` at `0x18003fdcf`
- `wincorlib!?__abi_WinRTraiseClassNotRegisteredException@@YAXXZ` at `0x18003fdcf`
- `wincorlib!?__abi_WinRTraiseWrongThreadException@@YAXXZ` at `0x18003fdd6`
- `wincorlib!?__abi_WinRTraiseWrongThreadException@@YAXXZ` at `0x18003fdd6`
- `wincorlib!?__abi_WinRTraiseDisconnectedException@@YAXXZ` at `0x18003fddd`
- `wincorlib!?__abi_WinRTraiseDisconnectedException@@YAXXZ` at `0x18003fddd`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x18003fd67`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x18003fd67`
- `wincorlib!?__abi_WinRTraiseCOMException@@YAXJ@Z` at `0x18003fdb3`
- `wincorlib!?__abi_WinRTraiseCOMException@@YAXJ@Z` at `0x18003fdb3`
- `wincorlib!?__abi_WinRTraiseAccessDeniedException@@YAXXZ` at `0x18003fdc8`
- `wincorlib!?__abi_WinRTraiseAccessDeniedException@@YAXXZ` at `0x18003fdc8`

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
        JUMPOUT(0x18003FDE3LL);
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
0x18003fd04  sub     rsp, 28h
0x18003fd08  mov     eax, 80004005h
0x18003fd0d  cmp     ecx, eax
0x18003fd0f  jg      short loc_18003FD83
0x18003fd11  jz      short loc_18003FD7C
0x18003fd13  cmp     ecx, 8000000Bh
0x18003fd19  jz      short loc_18003FD75
0x18003fd1b  cmp     ecx, 8000000Ch
0x18003fd21  jz      short loc_18003FD6E
0x18003fd23  cmp     ecx, 80000013h
0x18003fd29  jz      short loc_18003FD67
0x18003fd2b  cmp     ecx, 80004001h
0x18003fd31  jz      short loc_18003FD60
0x18003fd33  cmp     ecx, 80004002h
0x18003fd39  jz      short loc_18003FD59
0x18003fd3b  cmp     ecx, 80004003h
0x18003fd41  jz      short loc_18003FD52
0x18003fd43  cmp     ecx, 80004004h
0x18003fd49  jnz     short loc_18003FDB3
0x18003fd4b  call    cs:__imp_?__abi_WinRTraiseOperationCanceledException@@YAXXZ; __abi_WinRTraiseOperationCanceledException(void)
0x18003fd51  int     3; Trap to Debugger
0x18003fd52  call    cs:__imp_?__abi_WinRTraiseNullReferenceException@@YAXXZ; __abi_WinRTraiseNullReferenceException(void)
0x18003fd58  int     3; Trap to Debugger
0x18003fd59  call    cs:__imp_?__abi_WinRTraiseInvalidCastException@@YAXXZ; __abi_WinRTraiseInvalidCastException(void)
0x18003fd5f  int     3; Trap to Debugger
0x18003fd60  call    cs:__imp_?__abi_WinRTraiseNotImplementedException@@YAXXZ; __abi_WinRTraiseNotImplementedException(void)
0x18003fd66  int     3; Trap to Debugger
0x18003fd67  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x18003fd6d  int     3; Trap to Debugger
0x18003fd6e  call    cs:__imp_?__abi_WinRTraiseChangedStateException@@YAXXZ; __abi_WinRTraiseChangedStateException(void)
0x18003fd74  int     3; Trap to Debugger
0x18003fd75  call    cs:__imp_?__abi_WinRTraiseOutOfBoundsException@@YAXXZ; __abi_WinRTraiseOutOfBoundsException(void)
0x18003fd7b  int     3; Trap to Debugger
0x18003fd7c  call    cs:__imp_?__abi_WinRTraiseFailureException@@YAXXZ; __abi_WinRTraiseFailureException(void)
0x18003fd82  int     3; Trap to Debugger
0x18003fd83  cmp     ecx, 80010108h
0x18003fd89  jz      short loc_18003FDDD
0x18003fd8b  cmp     ecx, 8001010Eh
0x18003fd91  jz      short loc_18003FDD6
0x18003fd93  cmp     ecx, 80040154h
0x18003fd99  jz      short loc_18003FDCF
0x18003fd9b  cmp     ecx, 80070005h
0x18003fda1  jz      short loc_18003FDC8
0x18003fda3  cmp     ecx, 8007000Eh
0x18003fda9  jz      short loc_18003FDC1
0x18003fdab  cmp     ecx, 80070057h
0x18003fdb1  jz      short loc_18003FDBA
0x18003fdb3  call    cs:__imp_?__abi_WinRTraiseCOMException@@YAXJ@Z; __abi_WinRTraiseCOMException(long)
0x18003fdb9  int     3; Trap to Debugger
0x18003fdba  call    cs:__imp_?__abi_WinRTraiseInvalidArgumentException@@YAXXZ; __abi_WinRTraiseInvalidArgumentException(void)
0x18003fdc0  int     3; Trap to Debugger
0x18003fdc1  call    cs:__imp_?__abi_WinRTraiseOutOfMemoryException@@YAXXZ; __abi_WinRTraiseOutOfMemoryException(void)
0x18003fdc7  int     3; Trap to Debugger
0x18003fdc8  call    cs:__imp_?__abi_WinRTraiseAccessDeniedException@@YAXXZ; __abi_WinRTraiseAccessDeniedException(void)
0x18003fdce  int     3; Trap to Debugger
0x18003fdcf  call    cs:__imp_?__abi_WinRTraiseClassNotRegisteredException@@YAXXZ; __abi_WinRTraiseClassNotRegisteredException(void)
0x18003fdd5  int     3; Trap to Debugger
0x18003fdd6  call    cs:__imp_?__abi_WinRTraiseWrongThreadException@@YAXXZ; __abi_WinRTraiseWrongThreadException(void)
0x18003fddc  int     3; Trap to Debugger
0x18003fddd  call    cs:__imp_?__abi_WinRTraiseDisconnectedException@@YAXXZ; __abi_WinRTraiseDisconnectedException(void)
```
