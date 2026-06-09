# SCEventsReleaseCriticalSections(void)

- ea: `0x180029950`
- end: `0x1800299b9`
- name: `?SCEventsReleaseCriticalSections@@YAXXZ`
- size: `105`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001527c`

## callees

- `0x180029950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029964`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029984`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800299a4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029964`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029984`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800299a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void SCEventsReleaseCriticalSections(void)
{
  if ( dword_18004BF08 )
  {
    DeleteCriticalSection(&CriticalSection);
    dword_18004BF08 = 0;
  }
  if ( dword_18004BEF0 )
  {
    DeleteCriticalSection(&stru_18004BAA8);
    dword_18004BEF0 = 0;
  }
  if ( dword_18004BF0C )
  {
    DeleteCriticalSection(&stru_18004BAD0);
    dword_18004BF0C = 0;
  }
}

```

## disassembly

```asm
0x180029950  sub     rsp, 28h
0x180029954  cmp     cs:dword_18004BF08, 0
0x18002995b  jz      short loc_180029974
0x18002995d  lea     rcx, CriticalSection; lpCriticalSection
0x180029964  call    cs:__imp_DeleteCriticalSection
0x18002996a  mov     cs:dword_18004BF08, 0
0x180029974  cmp     cs:dword_18004BEF0, 0
0x18002997b  jz      short loc_180029994
0x18002997d  lea     rcx, stru_18004BAA8; lpCriticalSection
0x180029984  call    cs:__imp_DeleteCriticalSection
0x18002998a  mov     cs:dword_18004BEF0, 0
0x180029994  cmp     cs:dword_18004BF0C, 0
0x18002999b  jz      short loc_1800299B4
0x18002999d  lea     rcx, stru_18004BAD0; lpCriticalSection
0x1800299a4  call    cs:__imp_DeleteCriticalSection
0x1800299aa  mov     cs:dword_18004BF0C, 0
0x1800299b4  add     rsp, 28h
0x1800299b8  retn
```
