# wil::details::CloseHandle(void *)

- ea: `0x14000222c`
- end: `0x14000224f`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140001ad0`
- `0x140001d90`
- `0x140006f5c`
- `0x140007f1c`

## callees

- `0x14000222c`
- `0x14000cd84`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002230`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002230`

## pseudocode

```c
void __fastcall wil::details::CloseHandle(wil::details *this, void *a2)
{
  unsigned int v2; // r8d
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !CloseHandle(this) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v2, v3);
}

```

## disassembly

```asm
0x14000222c  sub     rsp, 28h
0x140002230  call    cs:__imp_CloseHandle
0x140002236  test    eax, eax
0x140002238  jz      short loc_14000223F
0x14000223a  add     rsp, 28h
0x14000223e  retn
0x14000223f  mov     rcx, [rsp+28h]; this
0x140002244  mov     edx, 0A0Bh; void *
0x140002249  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
