# Tracker::ProcessReading(long,int)

- ea: `0x140004410`
- end: `0x140004489`
- name: `?ProcessReading@Tracker@@AEAAJJH@Z`
- size: `121`
- prototype: `__int64 __fastcall(ReadBuffer **this, int, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140003a9c`
- `0x140004ba4`

## callees

- `0x1400017ac`
- `0x1400033ec`
- `0x140003f18`
- `0x140004410`
- `0x140004638`

## string_xrefs

- `0x140004461`: `ProcessReading`

## pseudocode

```c
__int64 __fastcall Tracker::ProcessReading(ReadBuffer **this, int a2, unsigned int a3)
{
  unsigned int Request; // ebx

  Request = a2;
  if ( !(unsigned int)Tracker::IsExpectedError((Tracker *)this, a2) && !Request )
  {
    Request = ReadBuffer::ReadRequest(this[26], a3);
    if ( Request )
    {
      if ( Request == 1 )
        Request = 0;
    }
    else
    {
      Request = Tracker::SubmitRequest((Tracker *)this);
    }
  }
  Tracker::RecordProcessError((Tracker *)this, Request, L"ProcessReading");
  return Request;
}

```

## disassembly

```asm
0x140004410  mov     [rsp+arg_0], rbx
0x140004415  mov     [rsp+arg_8], rbp
0x14000441a  mov     [rsp+arg_10], rsi
0x14000441f  push    rdi
0x140004420  sub     rsp, 20h
0x140004424  mov     esi, r8d
0x140004427  mov     ebx, edx
0x140004429  mov     rdi, rcx
0x14000442c  call    ?IsExpectedError@Tracker@@AEAAHJ@Z; Tracker::IsExpectedError(long)
0x140004431  xor     ebp, ebp
0x140004433  test    eax, eax
0x140004435  jnz     short loc_140004461
0x140004437  test    ebx, ebx
0x140004439  jnz     short loc_140004461
0x14000443b  mov     rcx, [rdi+0D0h]; this
0x140004442  mov     edx, esi; unsigned int
0x140004444  call    ?ReadRequest@ReadBuffer@@QEAAJK@Z; ReadBuffer::ReadRequest(ulong)
0x140004449  mov     ebx, eax
0x14000444b  test    eax, eax
0x14000444d  jnz     short loc_14000445B
0x14000444f  mov     rcx, rdi; this
0x140004452  call    ?SubmitRequest@Tracker@@AEAAJXZ; Tracker::SubmitRequest(void)
0x140004457  mov     ebx, eax
0x140004459  jmp     short loc_140004461
0x14000445b  cmp     ebx, 1
0x14000445e  cmovz   ebx, ebp
0x140004461  lea     r8, aProcessreading; "ProcessReading"
0x140004468  mov     edx, ebx; int
0x14000446a  mov     rcx, rdi; this
0x14000446d  call    ?RecordProcessError@Tracker@@AEAAXJPEBG@Z; Tracker::RecordProcessError(long,ushort const *)
0x140004472  mov     rbp, [rsp+28h+arg_8]
0x140004477  mov     eax, ebx
0x140004479  mov     rbx, [rsp+28h+arg_0]
0x14000447e  mov     rsi, [rsp+28h+arg_10]
0x140004483  add     rsp, 20h
0x140004487  pop     rdi
0x140004488  retn
```
