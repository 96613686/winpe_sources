# _PROG_RESOURCES::Phase2Build(void *)

- ea: `0x180009c28`
- end: `0x180009ce1`
- name: `?Phase2Build@_PROG_RESOURCES@@QEAAHPEAX@Z`
- size: `185`
- prototype: `__int64 __fastcall(_PROG_RESOURCES *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800098a0`

## callees

- `0x180009c28`
- `0x18000b2b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009c3f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009c58`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009c79`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009c92`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009c3f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009c58`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009c79`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009c92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ca5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ca5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cc6`

## string_xrefs

- `0x180009c31`: `Global\WINMGMT_COREDLL_CANSHUTDOWN`

## pseudocode

```c
__int64 __fastcall _PROG_RESOURCES::Phase2Build(_PROG_RESOURCES *this, void *a2)
{
  HANDLE EventW; // rax
  HANDLE v4; // rax
  HANDLE v6; // rax
  HANDLE v7; // rax

  EventW = CreateEventW(0, 0, 0, L"Global\\WINMGMT_COREDLL_CANSHUTDOWN");
  *((_QWORD *)this + 9) = EventW;
  if ( !EventW )
  {
    v4 = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 9) = v4;
    if ( !v4 )
      return 0;
  }
  v6 = CreateEventW(0, 0, 0, L"Global\\WINMGMT_PROVIDER_CANSHUTDOWN");
  *((_QWORD *)this + 10) = v6;
  if ( !v6 )
  {
    v7 = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 10) = v7;
    if ( !v7 )
    {
LABEL_6:
      CloseHandle(*((HANDLE *)this + 9));
      *((_QWORD *)this + 9) = 0;
      return 0;
    }
  }
  if ( !(unsigned int)CMonitorEvents::Init((_PROG_RESOURCES *)((char *)this + 104)) )
  {
    CloseHandle(*((HANDLE *)this + 10));
    *((_QWORD *)this + 10) = 0;
    goto LABEL_6;
  }
  return 1;
}

```

## disassembly

```asm
0x180009c28  push    rbx
0x180009c2a  sub     rsp, 20h
0x180009c2e  mov     rbx, rcx
0x180009c31  lea     r9, Name; "Global\\WINMGMT_COREDLL_CANSHUTDOWN"
0x180009c38  xor     ecx, ecx; lpEventAttributes
0x180009c3a  xor     r8d, r8d; bInitialState
0x180009c3d  xor     edx, edx; bManualReset
0x180009c3f  call    cs:__imp_CreateEventW
0x180009c45  mov     [rbx+48h], rax
0x180009c49  test    rax, rax
0x180009c4c  jnz     short loc_180009C6B
0x180009c4e  xor     r9d, r9d; lpName
0x180009c51  xor     r8d, r8d; bInitialState
0x180009c54  xor     edx, edx; bManualReset
0x180009c56  xor     ecx, ecx; lpEventAttributes
0x180009c58  call    cs:__imp_CreateEventW
0x180009c5e  mov     [rbx+48h], rax
0x180009c62  test    rax, rax
0x180009c65  jnz     short loc_180009C6B
0x180009c67  xor     eax, eax
0x180009c69  jmp     short loc_180009CDB
0x180009c6b  lea     r9, aGlobalWinmgmtP; "Global\\WINMGMT_PROVIDER_CANSHUTDOWN"
0x180009c72  xor     r8d, r8d; bInitialState
0x180009c75  xor     edx, edx; bManualReset
0x180009c77  xor     ecx, ecx; lpEventAttributes
0x180009c79  call    cs:__imp_CreateEventW
0x180009c7f  mov     [rbx+50h], rax
0x180009c83  test    rax, rax
0x180009c86  jnz     short loc_180009CB5
0x180009c88  xor     r9d, r9d; lpName
0x180009c8b  xor     r8d, r8d; bInitialState
0x180009c8e  xor     edx, edx; bManualReset
0x180009c90  xor     ecx, ecx; lpEventAttributes
0x180009c92  call    cs:__imp_CreateEventW
0x180009c98  mov     [rbx+50h], rax
0x180009c9c  test    rax, rax
0x180009c9f  jnz     short loc_180009CB5
0x180009ca1  mov     rcx, [rbx+48h]; hObject
0x180009ca5  call    cs:__imp_CloseHandle
0x180009cab  mov     qword ptr [rbx+48h], 0
0x180009cb3  jmp     short loc_180009C67
0x180009cb5  lea     rcx, [rbx+68h]; this
0x180009cb9  call    ?Init@CMonitorEvents@@QEAAHXZ; CMonitorEvents::Init(void)
0x180009cbe  test    eax, eax
0x180009cc0  jnz     short loc_180009CD6
0x180009cc2  mov     rcx, [rbx+50h]; hObject
0x180009cc6  call    cs:__imp_CloseHandle
0x180009ccc  mov     qword ptr [rbx+50h], 0
0x180009cd4  jmp     short loc_180009CA1
0x180009cd6  mov     eax, 1
0x180009cdb  add     rsp, 20h
0x180009cdf  pop     rbx
0x180009ce0  retn
```
