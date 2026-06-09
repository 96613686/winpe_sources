# vt::CTaskStatusEvent::Create(void)

- ea: `0x1800b8240`
- end: `0x1800b8287`
- name: `?Create@CTaskStatusEvent@vt@@UEAAJXZ`
- size: `71`
- prototype: `__int64 __fastcall(vt::CTaskStatusEvent *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800b8240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b825c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b825c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b826b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b826b`

## pseudocode

```c
signed int __fastcall vt::CTaskStatusEvent::Create(vt::CTaskStatusEvent *this)
{
  HANDLE EventW; // rax
  signed int result; // eax

  if ( *((_QWORD *)this + 4) )
    return 0;
  EventW = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)this + 4) = EventW;
  if ( EventW )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800b8240  push    rbx
0x1800b8242  sub     rsp, 20h
0x1800b8246  cmp     qword ptr [rcx+20h], 0
0x1800b824b  mov     rbx, rcx
0x1800b824e  jnz     short loc_1800B827F
0x1800b8250  xor     r9d, r9d; lpName
0x1800b8253  xor     ecx, ecx; lpEventAttributes
0x1800b8255  lea     edx, [r9+1]; bManualReset
0x1800b8259  mov     r8d, edx; bInitialState
0x1800b825c  call    cs:__imp_CreateEventW
0x1800b8262  mov     [rbx+20h], rax
0x1800b8266  test    rax, rax
0x1800b8269  jnz     short loc_1800B827F
0x1800b826b  call    cs:__imp_GetLastError
0x1800b8271  test    eax, eax
0x1800b8273  jle     short loc_1800B8281
0x1800b8275  movzx   eax, ax
0x1800b8278  or      eax, 80070000h
0x1800b827d  jmp     short loc_1800B8281
0x1800b827f  xor     eax, eax
0x1800b8281  add     rsp, 20h
0x1800b8285  pop     rbx
0x1800b8286  retn
```
