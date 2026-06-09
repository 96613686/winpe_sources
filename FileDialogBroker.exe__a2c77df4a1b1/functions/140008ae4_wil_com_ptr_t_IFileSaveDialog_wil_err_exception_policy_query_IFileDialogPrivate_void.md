# wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogPrivate>(void)

- ea: `0x140008ae4`
- end: `0x140008b33`
- name: `??$query@UIFileDialogPrivate@@@?$com_ptr_t@UIFileSaveDialog@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFileDialogPrivate@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b600`
- `0x14000b660`
- `0x14000b6c0`
- `0x14000b720`

## callees

- `0x140007df4`
- `0x140008ae4`
- `0x140014010`

## string_xrefs

- `0x140008b15`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogPrivate>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_9ea5491c_89c8_4bef_93d3_7f665fb82a33, a2);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v4,
      v6);
  return a2;
}

```

## disassembly

```asm
0x140008ae4  push    rbx
0x140008ae6  sub     rsp, 30h
0x140008aea  mov     rcx, [rcx]
0x140008aed  mov     rbx, rdx
0x140008af0  mov     qword ptr [rdx], 0
0x140008af7  mov     r8, rdx
0x140008afa  lea     rdx, _GUID_9ea5491c_89c8_4bef_93d3_7f665fb82a33
0x140008b01  mov     rax, [rcx]
0x140008b04  mov     rax, [rax]
0x140008b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008b0c  test    eax, eax
0x140008b0e  jns     short loc_140008B2A
0x140008b10  mov     rcx, [rsp+38h]; this
0x140008b15  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140008b1c  mov     r9d, eax; char *
0x140008b1f  mov     edx, 1CBEh; void *
0x140008b24  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140008b2a  mov     rax, rbx
0x140008b2d  add     rsp, 30h
0x140008b31  pop     rbx
0x140008b32  retn
```
