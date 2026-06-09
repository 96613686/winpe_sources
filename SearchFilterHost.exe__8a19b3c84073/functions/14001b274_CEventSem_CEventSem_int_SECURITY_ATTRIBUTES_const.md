# CEventSem::CEventSem(int,_SECURITY_ATTRIBUTES * const)

- ea: `0x14001b274`
- end: `0x14001b2b7`
- name: `??0CEventSem@@QEAA@HQEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `67`
- prototype: `CEventSem *__fastcall(CEventSem *this, __int64, struct _SECURITY_ATTRIBUTES *const)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140021bdc`
- `0x140021c20`

## callees

- `0x14001b274`
- `0x140024944`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001b289`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001b289`

## string_xrefs

- `0x14001b29c`: `onecoreuap\base\appmodel\Search\common\include\eventsem_common.hxx`

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
0x14001b274  push    rbx
0x14001b276  sub     rsp, 20h
0x14001b27a  xor     r9d, r9d; lpName
0x14001b27d  mov     rbx, rcx
0x14001b280  xor     r8d, r8d; bInitialState
0x14001b283  xor     ecx, ecx; lpEventAttributes
0x14001b285  lea     edx, [r9+1]; bManualReset
0x14001b289  call    cs:__imp_CreateEventW
0x14001b28f  mov     [rbx], rax
0x14001b292  test    rax, rax
0x14001b295  jnz     short loc_14001B2AE
0x14001b297  mov     rcx, [rsp+28h]; this
0x14001b29c  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14001b2a3  mov     edx, 9Eh; void *
0x14001b2a8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14001b2ae  mov     rax, rbx
0x14001b2b1  add     rsp, 20h
0x14001b2b5  pop     rbx
0x14001b2b6  retn
```
