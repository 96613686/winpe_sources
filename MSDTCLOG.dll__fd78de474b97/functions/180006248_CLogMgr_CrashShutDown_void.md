# CLogMgr::CrashShutDown(void)

- ea: `0x180006248`
- end: `0x18000628f`
- name: `?CrashShutDown@CLogMgr@@QEAAJXZ`
- size: `71`
- prototype: `__int64 __fastcall(CLogMgr *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800047b0`
- `0x180004a00`
- `0x180004cf0`
- `0x18000699c`
- `0x180006ca0`

## callees

- `0x180006248`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006276`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006267`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006267`

## pseudocode

```c
DWORD __fastcall CLogMgr::CrashShutDown(CLogMgr *this)
{
  void *v2; // rcx

  *((_DWORD *)this + 145) = 1;
  v2 = (void *)*((_QWORD *)this + 70);
  if ( v2 && !SetEvent(v2) )
    return GetLastError();
  *((_DWORD *)this + 72) = 0;
  return 0;
}

```

## disassembly

```asm
0x180006248  push    rbx
0x18000624a  sub     rsp, 20h
0x18000624e  mov     rbx, rcx
0x180006251  mov     dword ptr [rcx+244h], 1
0x18000625b  mov     rcx, [rcx+230h]; hEvent
0x180006262  test    rcx, rcx
0x180006265  jz      short loc_18000627D
0x180006267  call    cs:__imp_SetEvent
0x18000626d  test    eax, eax
0x18000626f  jnz     short loc_18000627D
0x180006271  add     rsp, 20h
0x180006275  pop     rbx
0x180006276  jmp     cs:__imp_GetLastError
0x18000627d  mov     dword ptr [rbx+120h], 0
0x180006287  xor     eax, eax
0x180006289  add     rsp, 20h
0x18000628d  pop     rbx
0x18000628e  retn
```
