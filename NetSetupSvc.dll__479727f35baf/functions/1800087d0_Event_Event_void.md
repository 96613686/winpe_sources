# Event::Event(void)

- ea: `0x1800087d0`
- end: `0x180008826`
- name: `??0Event@@QEAA@XZ`
- size: `86`
- prototype: `Event *__fastcall(Event *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800088d4`
- `0x18000f8ac`

## callees

- `0x1800032e4`
- `0x1800087d0`
- `0x180008c78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800087ed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800087ed`

## pseudocode

```c
Event *__fastcall Event::Event(Event *this)
{
  HANDLE EventW; // rax
  _BYTE pExceptionObject[224]; // [rsp+28h] [rbp-E0h] BYREF

  EventW = CreateEventW(0, 1, 0, 0);
  if ( !EventW )
  {
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, 6);
    throw (Win32Exception *)pExceptionObject;
  }
  *(_QWORD *)this = EventW;
  return this;
}

```

## disassembly

```asm
0x1800087d0  push    rbx
0x1800087d2  sub     rsp, 100h
0x1800087d9  xor     r9d, r9d; lpName
0x1800087dc  mov     [rsp+108h+var_E8], rcx
0x1800087e1  mov     rbx, rcx
0x1800087e4  xor     r8d, r8d; bInitialState
0x1800087e7  xor     ecx, ecx; lpEventAttributes
0x1800087e9  lea     edx, [r9+1]; bManualReset
0x1800087ed  call    cs:__imp_CreateEventW
0x1800087f3  test    rax, rax
0x1800087f6  jnz     short loc_180008817
0x1800087f8  lea     edx, [rax+6]; int
0x1800087fb  lea     rcx, [rsp+108h+pExceptionObject]; this
0x180008800  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180008805  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18000880c  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180008811  call    _CxxThrowException_0
0x180008817  mov     [rbx], rax
0x18000881a  mov     rax, rbx
0x18000881d  add     rsp, 100h
0x180008824  pop     rbx
0x180008825  retn
```
