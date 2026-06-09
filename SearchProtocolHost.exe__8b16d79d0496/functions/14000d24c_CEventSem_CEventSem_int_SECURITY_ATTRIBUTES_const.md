# CEventSem::CEventSem(int,_SECURITY_ATTRIBUTES * const)

- ea: `0x14000d24c`
- end: `0x14000d28f`
- name: `??0CEventSem@@QEAA@HQEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `67`
- prototype: `CEventSem *__fastcall(CEventSem *__hidden this, int, struct _SECURITY_ATTRIBUTES *const)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002004c`
- `0x140020090`

## callees

- `0x14000d24c`
- `0x14003178c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000d261`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000d261`

## string_xrefs

- `0x14000d274`: `onecoreuap\base\appmodel\Search\common\include\eventsem_common.hxx`

## pseudocode

```c
CEventSem *__fastcall CEventSem::CEventSem(CEventSem *this, __int64 a2, struct _SECURITY_ATTRIBUTES *const a3)
{
  HANDLE EventW; // rax
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)this = EventW;
  if ( !EventW )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\eventsem_common.hxx",
      v5);
  return this;
}

```

## disassembly

```asm
0x14000d24c  push    rbx
0x14000d24e  sub     rsp, 20h
0x14000d252  xor     r9d, r9d; lpName
0x14000d255  mov     rbx, rcx
0x14000d258  xor     r8d, r8d; bInitialState
0x14000d25b  xor     ecx, ecx; lpEventAttributes
0x14000d25d  lea     edx, [r9+1]; bManualReset
0x14000d261  call    cs:__imp_CreateEventW
0x14000d267  mov     [rbx], rax
0x14000d26a  test    rax, rax
0x14000d26d  jnz     short loc_14000D286
0x14000d26f  mov     rcx, [rsp+28h]; this
0x14000d274  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14000d27b  mov     edx, 9Eh; void *
0x14000d280  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14000d286  mov     rax, rbx
0x14000d289  add     rsp, 20h
0x14000d28d  pop     rbx
0x14000d28e  retn
```
