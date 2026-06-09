# wil::details::CloseHandle(void *)

- ea: `0x180009738`
- end: `0x18000975b`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800069b4`
- `0x180007ab4`
- `0x180007cb8`

## callees

- `0x180009738`
- `0x180009764`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000973c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000973c`

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
0x180009738  sub     rsp, 28h
0x18000973c  call    cs:__imp_CloseHandle
0x180009742  test    eax, eax
0x180009744  jnz     short loc_180009756
0x180009746  mov     rcx, [rsp+28h]; this
0x18000974b  mov     edx, 0A0Bh; void *
0x180009750  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009756  add     rsp, 28h
0x18000975a  retn
```
