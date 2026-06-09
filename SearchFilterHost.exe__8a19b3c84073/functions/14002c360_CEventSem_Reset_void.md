# CEventSem::Reset(void)

- ea: `0x14002c360`
- end: `0x14002c38d`
- name: `?Reset@CEventSem@@QEAAXXZ`
- size: `45`
- prototype: `void __fastcall(CEventSem *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002c094`
- `0x14002c510`
- `0x14002c590`

## callees

- `0x140024944`
- `0x14002c360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14002c367`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14002c367`

## string_xrefs

- `0x14002c376`: `onecoreuap\base\appmodel\Search\common\include\eventsem_common.hxx`

## pseudocode

```c
void __fastcall CEventSem::Reset(HANDLE *this)
{
  const char *v1; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !ResetEvent(*this) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\eventsem_common.hxx",
      v1);
}

```

## disassembly

```asm
0x14002c360  sub     rsp, 28h
0x14002c364  mov     rcx, [rcx]; hEvent
0x14002c367  call    cs:__imp_ResetEvent
0x14002c36d  test    eax, eax
0x14002c36f  jnz     short loc_14002C388
0x14002c371  mov     rcx, [rsp+28h]; this
0x14002c376  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14002c37d  mov     edx, 11Ch; void *
0x14002c382  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14002c388  add     rsp, 28h
0x14002c38c  retn
```
