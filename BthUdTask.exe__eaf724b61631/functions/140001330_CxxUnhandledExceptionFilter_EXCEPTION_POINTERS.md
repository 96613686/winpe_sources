# __CxxUnhandledExceptionFilter(_EXCEPTION_POINTERS *)

- ea: `0x140001330`
- end: `0x140001369`
- name: `?__CxxUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z`
- size: `57`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001330`

## import_xrefs

- `msvcrt!?terminate@@YAXXZ` at `0x14000135b`
- `msvcrt!?terminate@@YAXXZ` at `0x14000135b`

## pseudocode

```c
__int64 __fastcall __CxxUnhandledExceptionFilter(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  PEXCEPTION_RECORD ExceptionRecord; // rax
  int v2; // ecx

  ExceptionRecord = ExceptionInfo->ExceptionRecord;
  if ( ExceptionInfo->ExceptionRecord->ExceptionCode == -529697949 && ExceptionRecord->NumberParameters == 4 )
  {
    v2 = ExceptionRecord->ExceptionInformation[0];
    if ( (unsigned int)(v2 - 429065504) <= 2 || v2 == 26820608 )
      terminate();
  }
  return 0;
}

```

## disassembly

```asm
0x140001330  sub     rsp, 28h
0x140001334  mov     rax, [rcx]
0x140001337  cmp     dword ptr [rax], 0E06D7363h
0x14000133d  jnz     short loc_140001362
0x14000133f  cmp     dword ptr [rax+18h], 4
0x140001343  jnz     short loc_140001362
0x140001345  mov     ecx, [rax+20h]
0x140001348  lea     eax, [rcx-19930520h]
0x14000134e  cmp     eax, 2
0x140001351  jbe     short loc_14000135B
0x140001353  cmp     ecx, 1994000h
0x140001359  jnz     short loc_140001362
0x14000135b  call    cs:__imp_?terminate@@YAXXZ; terminate(void)
0x140001362  xor     eax, eax
0x140001364  add     rsp, 28h
0x140001368  retn
```
