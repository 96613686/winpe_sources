# _dynamic_initializer_for__g_wpnUserService__

- ea: `0x180002760`
- end: `0x1800027c2`
- name: `_dynamic_initializer_for__g_wpnUserService__`
- size: `98`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180002770`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180002770`

## pseudocode

```c
int dynamic_initializer_for__g_wpnUserService__()
{
  InitializeCriticalSectionEx(&stru_180019218, 0, 0);
  g_wpnUserService = &WpnUserService::`vftable';
  xmmword_180019240 = 0;
  qword_180019250 = 0;
  qword_180019258 = 0;
  xmmword_180019260 = 0;
  xmmword_180019270 = 0;
  return atexit(dynamic_atexit_destructor_for__g_wpnUserService__);
}

```

## disassembly

```asm
0x180002760  sub     rsp, 28h
0x180002764  xor     r8d, r8d; Flags
0x180002767  lea     rcx, stru_180019218; lpCriticalSection
0x18000276e  xor     edx, edx; dwSpinCount
0x180002770  call    cs:__imp_InitializeCriticalSectionEx
0x180002776  xorps   xmm0, xmm0
0x180002779  lea     rax, ??_7WpnUserService@@6B@; const WpnUserService::`vftable'
0x180002780  mov     cs:?g_wpnUserService@@3V?$object_without_destructor_on_shutdown@VWpnUserService@@@wil@@A, rax; wil::object_without_destructor_on_shutdown<WpnUserService> g_wpnUserService
0x180002787  lea     rcx, _dynamic_atexit_destructor_for__g_wpnUserService__
0x18000278e  xor     eax, eax
0x180002790  movdqa  cs:xmmword_180019240, xmm0
0x180002798  xorps   xmm1, xmm1
0x18000279b  mov     cs:qword_180019250, rax
0x1800027a2  mov     cs:qword_180019258, rax
0x1800027a9  movdqa  cs:xmmword_180019260, xmm0
0x1800027b1  movdqa  cs:xmmword_180019270, xmm1
0x1800027b9  add     rsp, 28h
0x1800027bd  jmp     atexit
```
