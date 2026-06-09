# Utility::IsAeInvAlreadyRunning(void * *)

- ea: `0x1800cdec0`
- end: `0x1800cdefe`
- name: `?IsAeInvAlreadyRunning@Utility@@SA_NPEAPEAX@Z`
- size: `62`
- prototype: `bool __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f378`
- `0x180021990`

## callees

- `0x1800cdec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cded7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cded7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdee5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdee5`

## pseudocode

```c
bool __fastcall Utility::IsAeInvAlreadyRunning(void **a1)
{
  HANDLE EventW; // rax

  EventW = CreateEventW(0, 0, 0, L"Global\\AeInvExclusiveEvent");
  *a1 = EventW;
  return !EventW || GetLastError() == 183;
}

```

## disassembly

```asm
0x1800cdec0  push    rbx
0x1800cdec2  sub     rsp, 20h
0x1800cdec6  mov     rbx, rcx
0x1800cdec9  lea     r9, Name; "Global\\AeInvExclusiveEvent"
0x1800cded0  xor     ecx, ecx; lpEventAttributes
0x1800cded2  xor     r8d, r8d; bInitialState
0x1800cded5  xor     edx, edx; bManualReset
0x1800cded7  call    cs:__imp_CreateEventW
0x1800cdedd  mov     [rbx], rax
0x1800cdee0  test    rax, rax
0x1800cdee3  jz      short loc_1800CDEF6
0x1800cdee5  call    cs:__imp_GetLastError
0x1800cdeeb  cmp     eax, 0B7h
0x1800cdef0  jz      short loc_1800CDEF6
0x1800cdef2  xor     al, al
0x1800cdef4  jmp     short loc_1800CDEF8
0x1800cdef6  mov     al, 1
0x1800cdef8  add     rsp, 20h
0x1800cdefc  pop     rbx
0x1800cdefd  retn
```
