# CreateResetEvent

- ea: `0x180007a60`
- end: `0x180007aaf`
- name: `CreateResetEvent`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007a60`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180007a87`
- `KERNEL32!CreateEventW` at `0x180007a87`

## pseudocode

```c
_BOOL8 __fastcall CreateResetEvent(_QWORD *a1)
{
  signed int v2; // eax
  HANDLE EventW; // rcx

  v2 = a1 == 0 ? 0x80070057 : 0;
  if ( a1 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    v2 = EventW == 0 ? 0x80000307 : 0;
    if ( EventW )
      *a1 = EventW;
  }
  return v2 >= 0;
}

```

## disassembly

```asm
0x180007a60  push    rbx
0x180007a62  sub     rsp, 20h
0x180007a66  mov     rax, rcx
0x180007a69  mov     rbx, rcx
0x180007a6c  neg     rax
0x180007a6f  sbb     eax, eax
0x180007a71  not     eax
0x180007a73  and     eax, 80070057h
0x180007a78  test    rcx, rcx
0x180007a7b  jz      short loc_180007AA4
0x180007a7d  xor     r9d, r9d; lpName
0x180007a80  xor     r8d, r8d; bInitialState
0x180007a83  xor     edx, edx; bManualReset
0x180007a85  xor     ecx, ecx; lpEventAttributes
0x180007a87  call    cs:__imp_CreateEventW
0x180007a8d  mov     rcx, rax
0x180007a90  neg     rax
0x180007a93  sbb     eax, eax
0x180007a95  not     eax
0x180007a97  and     eax, 80000307h
0x180007a9c  test    rcx, rcx
0x180007a9f  jz      short loc_180007AA4
0x180007aa1  mov     [rbx], rcx
0x180007aa4  not     eax
0x180007aa6  shr     eax, 1Fh
0x180007aa9  add     rsp, 20h
0x180007aad  pop     rbx
0x180007aae  retn
```
