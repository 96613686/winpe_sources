# Token::~Token(void)

- ea: `0x180006040`
- end: `0x18000605c`
- name: `??1Token@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(void **this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18002919f`
- `0x1800291c3`
- `0x180029201`
- `0x18002ad62`
- `0x18002ad86`
- `0x18002adbc`

## callees

- `0x180006040`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006051`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006051`

## pseudocode

```c
void __fastcall Token::~Token(void **this)
{
  char *v1; // rcx

  v1 = (char *)*this;
  if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v1);
}

```

## disassembly

```asm
0x180006040  sub     rsp, 28h
0x180006044  mov     rcx, [rcx]; hObject
0x180006047  lea     rax, [rcx-1]
0x18000604b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000604f  ja      short loc_180006057
0x180006051  call    cs:__imp_CloseHandle
0x180006057  add     rsp, 28h
0x18000605b  retn
```
