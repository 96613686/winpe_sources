# wil::com_ptr_t<IFileDialog,wil::err_exception_policy>::query<IFileOpenDialog>(void)

- ea: `0x140008b3c`
- end: `0x140008b8b`
- name: `??$query@UIFileOpenDialog@@@?$com_ptr_t@UIFileDialog@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFileOpenDialog@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000bf60`

## callees

- `0x140007df4`
- `0x140008b3c`
- `0x140014010`

## string_xrefs

- `0x140008b6d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<IFileDialog,wil::err_exception_policy>::query<IFileOpenDialog>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_d57c7288_d4ad_4768_be02_9d969532d960, a2);
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
0x140008b3c  push    rbx
0x140008b3e  sub     rsp, 30h
0x140008b42  mov     rcx, [rcx]
0x140008b45  mov     rbx, rdx
0x140008b48  mov     qword ptr [rdx], 0
0x140008b4f  mov     r8, rdx
0x140008b52  lea     rdx, _GUID_d57c7288_d4ad_4768_be02_9d969532d960
0x140008b59  mov     rax, [rcx]
0x140008b5c  mov     rax, [rax]
0x140008b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008b64  test    eax, eax
0x140008b66  jns     short loc_140008B82
0x140008b68  mov     rcx, [rsp+38h]; this
0x140008b6d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140008b74  mov     r9d, eax; char *
0x140008b77  mov     edx, 1CBEh; void *
0x140008b7c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140008b82  mov     rax, rbx
0x140008b85  add     rsp, 30h
0x140008b89  pop     rbx
0x140008b8a  retn
```
