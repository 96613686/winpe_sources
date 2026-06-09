# DllRelease(void)

- ea: `0x180015de8`
- end: `0x180015e52`
- name: `?DllRelease@@YAXXZ`
- size: `106`
- prototype: `void(void)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180014410`
- `0x180014df4`
- `0x180015318`
- `0x180015af0`
- `0x180015da0`
- `0x180015ed8`
- `0x180019e90`
- `0x1800415c0`
- `0x18004a510`
- `0x18005afa4`

## callees

- `0x180015de8`
- `0x180032170`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015e39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void DllRelease(void)
{
  if ( _InterlockedExchangeAdd(&dword_1800FB700, 0xFFFFFFFF) == 1 )
  {
    EnterCriticalSection(&stru_1800FB908);
    if ( !dword_1800FB700 )
    {
      if ( qword_1800FB400[0] )
        FreeGlobalObjects();
    }
    LeaveCriticalSection(&stru_1800FB908);
  }
}

```

## disassembly

```asm
0x180015de8  sub     rsp, 38h
0x180015dec  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180015df5  or      eax, 0FFFFFFFFh
0x180015df8  lock xadd cs:dword_1800FB700, eax
0x180015e00  cmp     eax, 1
0x180015e03  jz      short loc_180015E0A
0x180015e05  add     rsp, 38h
0x180015e09  retn
0x180015e0a  lea     rax, byte_1800FB900
0x180015e11  mov     [rsp+38h+arg_0], rax
0x180015e16  lea     rcx, stru_1800FB908; lpCriticalSection
0x180015e1d  call    cs:__imp_EnterCriticalSection
0x180015e23  nop
0x180015e24  mov     eax, cs:dword_1800FB700
0x180015e2a  test    eax, eax
0x180015e2c  jz      short loc_180015E40
0x180015e2e  lea     rcx, stru_1800FB908
0x180015e35  add     rsp, 38h
0x180015e39  jmp     cs:__imp_LeaveCriticalSection
0x180015e40  cmp     cs:qword_1800FB400, 0
0x180015e48  jz      short loc_180015E2E
0x180015e4a  call    FreeGlobalObjects
0x180015e4f  jmp     short loc_180015E2E
```
