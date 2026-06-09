# wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogInternal>(void)

- ea: `0x140008a8c`
- end: `0x140008adb`
- name: `??$query@UIFileDialogInternal@@@?$com_ptr_t@UIFileSaveDialog@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFileDialogInternal@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b480`
- `0x14000b4e0`
- `0x14000b540`
- `0x14000b5a0`

## callees

- `0x140007df4`
- `0x140008a8c`
- `0x140014010`

## string_xrefs

- `0x140008abd`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogInternal>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_e98f4700_8f03_4b3c_a697_d4f89448fbb6, a2);
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
0x140008a8c  push    rbx
0x140008a8e  sub     rsp, 30h
0x140008a92  mov     rcx, [rcx]
0x140008a95  mov     rbx, rdx
0x140008a98  mov     qword ptr [rdx], 0
0x140008a9f  mov     r8, rdx
0x140008aa2  lea     rdx, _GUID_e98f4700_8f03_4b3c_a697_d4f89448fbb6
0x140008aa9  mov     rax, [rcx]
0x140008aac  mov     rax, [rax]
0x140008aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008ab4  test    eax, eax
0x140008ab6  jns     short loc_140008AD2
0x140008ab8  mov     rcx, [rsp+38h]; this
0x140008abd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140008ac4  mov     r9d, eax; char *
0x140008ac7  mov     edx, 1CBEh; void *
0x140008acc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140008ad2  mov     rax, rbx
0x140008ad5  add     rsp, 30h
0x140008ad9  pop     rbx
0x140008ada  retn
```
