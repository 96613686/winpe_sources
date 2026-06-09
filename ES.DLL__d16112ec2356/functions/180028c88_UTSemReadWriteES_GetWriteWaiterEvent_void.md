# UTSemReadWriteES::GetWriteWaiterEvent(void)

- ea: `0x180028c88`
- end: `0x180028ce8`
- name: `?GetWriteWaiterEvent@UTSemReadWriteES@@AEAAPEAXXZ`
- size: `96`
- prototype: `void *__fastcall(UTSemReadWriteES *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d078`
- `0x18000d15c`
- `0x18000e050`
- `0x18001e970`

## callees

- `0x180009034`
- `0x180028c88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028ca2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028ca2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028cd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028cd8`

## string_xrefs

- `0x180028cc0`: `com\complus\src\events\shared\utsem.cpp`
- `0x180028cb9`: `CreateEvent`

## pseudocode

```c
void *__fastcall UTSemReadWriteES::GetWriteWaiterEvent(UTSemReadWriteES *this)
{
  HANDLE EventW; // rax

  if ( !*((_QWORD *)this + 2) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( EventW )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 2, (signed __int64)EventW, 0) )
        CloseHandle(EventW);
    }
    else
    {
      InternalError_Win32(L"com\\complus\\src\\events\\shared\\utsem.cpp", 0x265u, 0x10u, L"CreateEvent");
    }
  }
  return (void *)*((_QWORD *)this + 2);
}

```

## disassembly

```asm
0x180028c88  push    rbx
0x180028c8a  sub     rsp, 20h
0x180028c8e  cmp     qword ptr [rcx+10h], 0
0x180028c93  mov     rbx, rcx
0x180028c96  jnz     short loc_180028CDE
0x180028c98  xor     r9d, r9d; lpName
0x180028c9b  xor     r8d, r8d; bInitialState
0x180028c9e  xor     edx, edx; bManualReset
0x180028ca0  xor     ecx, ecx; lpEventAttributes
0x180028ca2  call    cs:__imp_CreateEventW
0x180028ca8  mov     rcx, rax; hObject
0x180028cab  test    rax, rax
0x180028cae  jnz     short loc_180028CCE
0x180028cb0  lea     r8d, [rax+10h]; unsigned __int16
0x180028cb4  mov     edx, 265h; unsigned int
0x180028cb9  lea     r9, aCreateevent; "CreateEvent"
0x180028cc0  lea     rcx, aComComplusSrcE_23; "com\\complus\\src\\events\\shared\\utse"...
0x180028cc7  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x180028ccc  jmp     short loc_180028CDE
0x180028cce  xor     eax, eax
0x180028cd0  lock cmpxchg [rbx+10h], rcx
0x180028cd6  jz      short loc_180028CDE
0x180028cd8  call    cs:__imp_CloseHandle
0x180028cde  mov     rax, [rbx+10h]
0x180028ce2  add     rsp, 20h
0x180028ce6  pop     rbx
0x180028ce7  retn
```
