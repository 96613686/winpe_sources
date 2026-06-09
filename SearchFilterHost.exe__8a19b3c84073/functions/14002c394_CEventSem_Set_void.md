# CEventSem::Set(void)

- ea: `0x14002c394`
- end: `0x14002c3c1`
- name: `?Set@CEventSem@@QEAAXXZ`
- size: `45`
- prototype: `void __fastcall(CEventSem *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002c174`
- `0x14002c210`
- `0x14002c590`
- `0x14002c8dc`

## callees

- `0x140024944`
- `0x14002c394`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002c39b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002c39b`

## string_xrefs

- `0x14002c3aa`: `onecoreuap\base\appmodel\Search\common\include\eventsem_common.hxx`

## pseudocode

```c
void __fastcall CEventSem::Set(HANDLE *this)
{
  const char *v1; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !SetEvent(*this) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\eventsem_common.hxx",
      v1);
}

```

## disassembly

```asm
0x14002c394  sub     rsp, 28h
0x14002c398  mov     rcx, [rcx]; hEvent
0x14002c39b  call    cs:__imp_SetEvent
0x14002c3a1  test    eax, eax
0x14002c3a3  jnz     short loc_14002C3BC
0x14002c3a5  mov     rcx, [rsp+28h]; this
0x14002c3aa  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14002c3b1  mov     edx, 10Ah; void *
0x14002c3b6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14002c3bc  add     rsp, 28h
0x14002c3c0  retn
```
