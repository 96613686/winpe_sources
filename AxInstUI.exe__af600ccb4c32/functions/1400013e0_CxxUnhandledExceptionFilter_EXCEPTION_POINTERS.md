# __CxxUnhandledExceptionFilter(_EXCEPTION_POINTERS *)

- ea: `0x1400013e0`
- end: `0x140001419`
- name: `?__CxxUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z`
- size: `57`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400013e0`

## import_xrefs

- `msvcrt!?terminate@@YAXXZ` at `0x14000140b`
- `msvcrt!?terminate@@YAXXZ` at `0x14000140b`

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
0x1400013e0  sub     rsp, 28h
0x1400013e4  mov     rax, [rcx]
0x1400013e7  cmp     dword ptr [rax], 0E06D7363h
0x1400013ed  jnz     short loc_140001412
0x1400013ef  cmp     dword ptr [rax+18h], 4
0x1400013f3  jnz     short loc_140001412
0x1400013f5  mov     ecx, [rax+20h]
0x1400013f8  lea     eax, [rcx-19930520h]
0x1400013fe  cmp     eax, 2
0x140001401  jbe     short loc_14000140B
0x140001403  cmp     ecx, 1994000h
0x140001409  jnz     short loc_140001412
0x14000140b  call    cs:__imp_?terminate@@YAXXZ; terminate(void)
0x140001412  xor     eax, eax
0x140001414  add     rsp, 28h
0x140001418  retn
```
