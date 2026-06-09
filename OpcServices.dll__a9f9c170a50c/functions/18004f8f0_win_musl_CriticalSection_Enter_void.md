# win_musl::CriticalSection::Enter(void)

- ea: `0x18004f8f0`
- end: `0x18004f91b`
- name: `?Enter@CriticalSection@win_musl@@QEAAXXZ`
- size: `43`
- prototype: `void __fastcall(win_musl::CriticalSection *__hidden this)`
- caller_count: `64`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ce8`
- `0x180003f60`
- `0x180004584`
- `0x1800047b8`
- `0x180007d5c`
- `0x18000d6f0`
- `0x18000ecd8`
- `0x1800293a8`
- `0x18002a6a0`
- `0x18002ac3c`
- `0x18002b870`
- `0x18002f270`
- `0x18002f33c`
- `0x18002f3c8`
- `0x18002f48c`
- `0x1800303b0`
- `0x180031260`
- `0x180031310`
- `0x18003c040`
- `0x180042be8`
- `0x1800431f8`
- `0x1800449ec`
- `0x180044a4c`
- `0x180044cc0`
- `0x180044f48`
- `0x180045858`
- `0x180045d98`
- `0x18004cda0`
- `0x18004d364`
- `0x18004db08`
- `0x18004ed34`
- `0x18004f074`
- `0x18004f508`
- `0x18004f730`
- `0x1800505d4`
- `0x180051314`
- `0x180051b00`
- `0x18005593c`
- `0x18005bb04`
- `0x18006b3b8`
- `0x18006b6d0`
- `0x18006bed0`
- `0x18006cf6c`
- `0x1800790e0`
- `0x180079718`
- `0x18007a3d0`
- `0x18007ac6c`
- `0x18007ae64`
- `0x18007afd8`
- `0x18007b164`

## callees

- `0x18004f8f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f90c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f90c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f8f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f8f9`

## pseudocode

```c
void __fastcall win_musl::CriticalSection::Enter(struct _RTL_CRITICAL_SECTION *this)
{
  int DebugInfo_high; // edx

  EnterCriticalSection(this);
  DebugInfo_high = HIDWORD(this[1].DebugInfo);
  HIDWORD(this[1].DebugInfo) = DebugInfo_high + 1;
  if ( !DebugInfo_high )
    LODWORD(this[1].DebugInfo) = GetCurrentThreadId();
}

```

## disassembly

```asm
0x18004f8f0  push    rbx
0x18004f8f2  sub     rsp, 20h
0x18004f8f6  mov     rbx, rcx
0x18004f8f9  call    cs:__imp_EnterCriticalSection
0x18004f8ff  mov     edx, [rbx+2Ch]
0x18004f902  lea     eax, [rdx+1]
0x18004f905  mov     [rbx+2Ch], eax
0x18004f908  test    edx, edx
0x18004f90a  jnz     short loc_18004F915
0x18004f90c  call    cs:__imp_GetCurrentThreadId
0x18004f912  mov     [rbx+28h], eax
0x18004f915  add     rsp, 20h
0x18004f919  pop     rbx
0x18004f91a  retn
```
