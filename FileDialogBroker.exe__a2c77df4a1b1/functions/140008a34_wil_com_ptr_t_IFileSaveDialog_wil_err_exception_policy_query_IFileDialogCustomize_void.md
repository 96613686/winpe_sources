# wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogCustomize>(void)

- ea: `0x140008a34`
- end: `0x140008a83`
- name: `??$query@UIFileDialogCustomize@@@?$com_ptr_t@UIFileSaveDialog@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFileDialogCustomize@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ae40`
- `0x14000aea0`
- `0x14000af00`
- `0x14000af60`

## callees

- `0x140007df4`
- `0x140008a34`
- `0x140014010`

## string_xrefs

- `0x140008a65`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogCustomize>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_e6fdd21a_163f_4975_9c8c_a69f1ba37034, a2);
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
0x140008a34  push    rbx
0x140008a36  sub     rsp, 30h
0x140008a3a  mov     rcx, [rcx]
0x140008a3d  mov     rbx, rdx
0x140008a40  mov     qword ptr [rdx], 0
0x140008a47  mov     r8, rdx
0x140008a4a  lea     rdx, _GUID_e6fdd21a_163f_4975_9c8c_a69f1ba37034
0x140008a51  mov     rax, [rcx]
0x140008a54  mov     rax, [rax]
0x140008a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a5c  test    eax, eax
0x140008a5e  jns     short loc_140008A7A
0x140008a60  mov     rcx, [rsp+38h]; this
0x140008a65  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140008a6c  mov     r9d, eax; char *
0x140008a6f  mov     edx, 1CBEh; void *
0x140008a74  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140008a7a  mov     rax, rbx
0x140008a7d  add     rsp, 30h
0x140008a81  pop     rbx
0x140008a82  retn
```
