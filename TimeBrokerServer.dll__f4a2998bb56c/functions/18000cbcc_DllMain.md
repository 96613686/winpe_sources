# DllMain

- ea: `0x18000cbcc`
- end: `0x18000cbfb`
- name: `DllMain`
- size: `47`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180012c44`

## callees

- `0x18000cbcc`
- `0x180010b94`
- `0x180010bcc`
- `0x180014068`
- `0x180019b74`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    McGenEventRegister_EventRegister(hinstDLL, fdwReason, lpvReserved);
    TlgRegisterAggregateProviderEx();
  }
  else if ( !fdwReason )
  {
    TlgUnregisterAggregateProvider(hinstDLL, fdwReason, lpvReserved);
    McGenEventUnregister_EventUnregister();
  }
  return 1;
}

```

## disassembly

```asm
0x18000cbcc  sub     rsp, 28h
0x18000cbd0  cmp     edx, 1
0x18000cbd3  jz      short loc_18000CBE3
0x18000cbd5  test    edx, edx
0x18000cbd7  jz      short loc_18000CBEF
0x18000cbd9  mov     eax, 1
0x18000cbde  add     rsp, 28h
0x18000cbe2  retn
0x18000cbe3  call    McGenEventRegister_EventRegister
0x18000cbe8  call    TlgRegisterAggregateProviderEx
0x18000cbed  jmp     short loc_18000CBD9
0x18000cbef  call    TlgUnregisterAggregateProvider
0x18000cbf4  call    McGenEventUnregister_EventUnregister
0x18000cbf9  jmp     short loc_18000CBD9
```
