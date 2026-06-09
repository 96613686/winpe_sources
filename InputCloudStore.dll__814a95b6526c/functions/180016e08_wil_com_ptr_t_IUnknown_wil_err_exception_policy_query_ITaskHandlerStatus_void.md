# wil::com_ptr_t<IUnknown,wil::err_exception_policy>::query<ITaskHandlerStatus>(void)

- ea: `0x180016e08`
- end: `0x180016e57`
- name: `??$query@UITaskHandlerStatus@@@?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UITaskHandlerStatus@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180022280`
- `0x1800282c0`

## callees

- `0x180016e08`
- `0x180022b80`
- `0x180031010`

## string_xrefs

- `0x180016e39`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<IUnknown,wil::err_exception_policy>::query<ITaskHandlerStatus>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a, a2);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
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
0x180016e08  push    rbx
0x180016e0a  sub     rsp, 30h
0x180016e0e  mov     rcx, [rcx]
0x180016e11  mov     rbx, rdx
0x180016e14  mov     qword ptr [rdx], 0
0x180016e1b  mov     r8, rdx
0x180016e1e  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180016e25  mov     rax, [rcx]
0x180016e28  mov     rax, [rax]
0x180016e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e30  test    eax, eax
0x180016e32  jns     short loc_180016E4E
0x180016e34  mov     rcx, [rsp+38h]; this
0x180016e39  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016e40  mov     r9d, eax; char *
0x180016e43  mov     edx, 1CBEh; void *
0x180016e48  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016e4e  mov     rax, rbx
0x180016e51  add     rsp, 30h
0x180016e55  pop     rbx
0x180016e56  retn
```
