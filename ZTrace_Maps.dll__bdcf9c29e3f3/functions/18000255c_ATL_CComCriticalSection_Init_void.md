# ATL::CComCriticalSection::Init(void)

- ea: `0x18000255c`
- end: `0x180002583`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800012f0`

## callees

- `0x18000255c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002567`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002567`

## pseudocode

```c
__int64 __fastcall ATL::CComCriticalSection::Init(ATL::CComCriticalSection *this)
{
  InitializeCriticalSection(&g_ZTraceContext);
  return 0;
}

```

## disassembly

```asm
0x18000255c  sub     rsp, 38h
0x180002560  lea     rcx, ?g_ZTraceContext@@3VZTraceContext@@A; lpCriticalSection
0x180002567  call    cs:__imp_InitializeCriticalSection
0x18000256d  xor     eax, eax
0x18000256f  mov     [rsp+38h+var_18], eax
0x180002573  jmp     short loc_18000257E
0x180002575  mov     eax, 8007000Eh
0x18000257a  mov     [rsp+38h+var_18], eax
0x18000257e  add     rsp, 38h
0x180002582  retn
0x180003c56  push    rbp
0x180003c58  sub     rsp, 20h
0x180003c5c  mov     rbp, rdx
0x180003c5f  mov     rax, [rcx]
0x180003c62  xor     ecx, ecx
0x180003c64  cmp     dword ptr [rax], 0C0000017h
0x180003c6a  setz    cl
0x180003c6d  mov     eax, ecx
0x180003c6f  add     rsp, 20h
0x180003c73  pop     rbp
0x180003c74  retn
```
