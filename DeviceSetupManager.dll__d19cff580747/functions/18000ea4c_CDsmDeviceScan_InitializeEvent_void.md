# CDsmDeviceScan::_InitializeEvent(void)

- ea: `0x18000ea4c`
- end: `0x18000ea92`
- name: `?_InitializeEvent@CDsmDeviceScan@@AEAAJXZ`
- size: `70`
- prototype: `__int64 __fastcall(CDsmDeviceScan *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ed44`

## callees

- `0x18000ea4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ea67`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ea67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea7a`

## pseudocode

```c
signed int __fastcall CDsmDeviceScan::_InitializeEvent(CDsmDeviceScan *this)
{
  signed int result; // eax
  HANDLE EventW; // rax

  result = 0;
  if ( !*((_QWORD *)this + 2) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 2) = EventW;
    if ( EventW )
    {
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ea4c  push    rbx
0x18000ea4e  sub     rsp, 20h
0x18000ea52  xor     eax, eax
0x18000ea54  mov     rbx, rcx
0x18000ea57  cmp     [rcx+10h], rax
0x18000ea5b  jnz     short loc_18000EA8C
0x18000ea5d  xor     r9d, r9d; lpName
0x18000ea60  xor     r8d, r8d; bInitialState
0x18000ea63  xor     edx, edx; bManualReset
0x18000ea65  xor     ecx, ecx; lpEventAttributes
0x18000ea67  call    cs:__imp_CreateEventW
0x18000ea6d  mov     [rbx+10h], rax
0x18000ea71  test    rax, rax
0x18000ea74  jz      short loc_18000EA7A
0x18000ea76  xor     eax, eax
0x18000ea78  jmp     short loc_18000EA8C
0x18000ea7a  call    cs:__imp_GetLastError
0x18000ea80  test    eax, eax
0x18000ea82  jle     short loc_18000EA8C
0x18000ea84  movzx   eax, ax
0x18000ea87  or      eax, 80070000h
0x18000ea8c  add     rsp, 20h
0x18000ea90  pop     rbx
0x18000ea91  retn
```
