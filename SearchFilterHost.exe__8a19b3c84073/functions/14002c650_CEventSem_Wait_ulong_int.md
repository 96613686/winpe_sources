# CEventSem::Wait(ulong,int)

- ea: `0x14002c650`
- end: `0x14002c684`
- name: `?Wait@CEventSem@@QEAAKKH@Z`
- size: `52`
- prototype: `unsigned int __fastcall(CEventSem *__hidden this, unsigned int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002c094`
- `0x14002c510`
- `0x14002c590`

## callees

- `0x140024944`
- `0x14002c650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14002c65d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14002c65d`

## string_xrefs

- `0x14002c66d`: `onecoreuap\base\appmodel\Search\common\include\eventsem_common.hxx`

## pseudocode

```c
DWORD __fastcall CEventSem::Wait(HANDLE *this)
{
  DWORD result; // eax
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  result = WaitForSingleObjectEx(*this, 0xFFFFFFFF, 0);
  if ( result == -1 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\eventsem_common.hxx",
      v2);
  return result;
}

```

## disassembly

```asm
0x14002c650  sub     rsp, 28h
0x14002c654  mov     rcx, [rcx]; hHandle
0x14002c657  xor     r8d, r8d; bAlertable
0x14002c65a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14002c65d  call    cs:__imp_WaitForSingleObjectEx
0x14002c663  cmp     eax, 0FFFFFFFFh
0x14002c666  jnz     short loc_14002C67F
0x14002c668  mov     rcx, [rsp+28h]; this
0x14002c66d  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14002c674  mov     edx, 130h; void *
0x14002c679  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14002c67f  add     rsp, 28h
0x14002c683  retn
```
