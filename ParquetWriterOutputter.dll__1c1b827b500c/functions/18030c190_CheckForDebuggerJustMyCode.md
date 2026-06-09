# __CheckForDebuggerJustMyCode

- ea: `0x18030c190`
- end: `0x18030c1cc`
- name: `__CheckForDebuggerJustMyCode`
- size: `60`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `443`
- callee_count: `1`
- tags: ``

## callers

- `0x180001000`
- `0x180001020`
- `0x180001ac0`
- `0x180001ae0`
- `0x180001b00`
- `0x180001b20`
- `0x180001b40`
- `0x180001b60`
- `0x180001b80`
- `0x180001ba0`
- `0x180001bc0`
- `0x180001be0`
- `0x180001c00`
- `0x180001c20`
- `0x180001c40`
- `0x180001c60`
- `0x180001c80`
- `0x180001ca0`
- `0x180001cc0`
- `0x180001ce0`
- `0x180001d00`
- `0x18000f1f0`
- `0x18000f260`
- `0x18000f2c0`
- `0x18000f3a0`
- `0x18000f4c0`
- `0x18000f550`
- `0x18000f5c0`
- `0x18000f610`
- `0x18000f6b0`
- `0x18000f720`
- `0x18000f740`
- `0x18000f850`
- `0x18000f870`
- `0x18000f8d0`
- `0x18000f960`
- `0x18000f9e0`
- `0x18000fa50`
- `0x18000fb90`
- `0x18000fd10`
- `0x18000fde0`
- `0x18000fee0`
- `0x18000ff30`
- `0x18000ff60`
- `0x18000ffa0`
- `0x18000fff0`
- `0x180010030`
- `0x180010080`
- `0x1800100c0`
- `0x180010330`

## callees

- `0x18030c190`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18030c1b8`
- `KERNEL32!GetCurrentThreadId` at `0x18030c1b8`

## pseudocode

```c
DWORD __fastcall _CheckForDebuggerJustMyCode(_BYTE *a1)
{
  DWORD result; // eax

  result = (unsigned __int8)*a1;
  if ( *a1 )
  {
    if ( _DebuggerCurrentSteppingThreadId )
      return GetCurrentThreadId();
  }
  return result;
}

```

## disassembly

```asm
0x18030c190  mov     [rsp+arg_0], rcx
0x18030c195  sub     rsp, 38h
0x18030c199  mov     rax, [rsp+38h+arg_0]
0x18030c19e  mov     [rsp+38h+var_18], rax
0x18030c1a3  mov     rax, [rsp+38h+arg_0]
0x18030c1a8  movzx   eax, byte ptr [rax]
0x18030c1ab  test    eax, eax
0x18030c1ad  jz      short loc_18030C1C7
0x18030c1af  cmp     cs:__DebuggerCurrentSteppingThreadId, 0
0x18030c1b6  jz      short loc_18030C1C7
0x18030c1b8  call    cs:__imp_GetCurrentThreadId
0x18030c1be  cmp     cs:__DebuggerCurrentSteppingThreadId, eax
0x18030c1c4  jnz     short loc_18030C1C7
0x18030c1c6  nop
0x18030c1c7  add     rsp, 38h
0x18030c1cb  retn
```
