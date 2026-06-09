# TimerCallback

- ea: `0x18002b130`
- end: `0x18002b155`
- name: `TimerCallback`
- size: `37`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002b130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002b14a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002b14a`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002b13c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002b13c`

## pseudocode

```c
void __fastcall TimerCallback(PTP_CALLBACK_INSTANCE Instance, const WCHAR *Context, PTP_TIMER Timer)
{
  HANDLE v3; // rax

  v3 = OpenEventW(2u, 0, Context);
  if ( v3 )
    SetEvent(v3);
}

```

## disassembly

```asm
0x18002b130  sub     rsp, 28h
0x18002b134  mov     r8, rdx; lpName
0x18002b137  xor     edx, edx; bInheritHandle
0x18002b139  lea     ecx, [rdx+2]; dwDesiredAccess
0x18002b13c  call    cs:__imp_OpenEventW
0x18002b142  test    rax, rax
0x18002b145  jz      short loc_18002B150
0x18002b147  mov     rcx, rax; hEvent
0x18002b14a  call    cs:__imp_SetEvent
0x18002b150  add     rsp, 28h
0x18002b154  retn
```
