# ETWClean

- ea: `0x1800378d0`
- end: `0x18003791a`
- name: `ETWClean`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002575c`

## callees

- `0x1800378d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800378e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800378e8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037913`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037900`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037900`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800378f7`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800378f7`

## pseudocode

```c
void ETWClean()
{
  _QWORD *v0; // rdi
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  v0 = g_petwPro;
  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)g_petwPro + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_petwPro + 16));
  if ( !*(_DWORD *)v0 )
    EventUnregister(v0[1]);
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
}

```

## disassembly

```asm
0x1800378d0  mov     [rsp+arg_0], rbx
0x1800378d5  push    rdi
0x1800378d6  sub     rsp, 20h
0x1800378da  mov     rdi, cs:g_petwPro
0x1800378e1  lea     rbx, [rdi+10h]
0x1800378e5  mov     rcx, rbx; lpCriticalSection
0x1800378e8  call    cs:__imp_EnterCriticalSection
0x1800378ee  cmp     dword ptr [rdi], 0
0x1800378f1  jnz     short loc_1800378FD
0x1800378f3  mov     rcx, [rdi+8]; RegHandle
0x1800378f7  call    cs:__imp_EventUnregister
0x1800378fd  mov     rcx, rbx; lpCriticalSection
0x180037900  call    cs:__imp_LeaveCriticalSection
0x180037906  mov     rcx, rbx
0x180037909  mov     rbx, [rsp+28h+arg_0]
0x18003790e  add     rsp, 20h
0x180037912  pop     rdi
0x180037913  jmp     cs:__imp_DeleteCriticalSection
```
