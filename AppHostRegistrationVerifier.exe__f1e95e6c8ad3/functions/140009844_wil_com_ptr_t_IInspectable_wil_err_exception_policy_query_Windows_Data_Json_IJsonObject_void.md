# wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Data::Json::IJsonObject>(void)

- ea: `0x140009844`
- end: `0x140009893`
- name: `??$query@UIJsonObject@Json@Data@Windows@@@?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008450`

## callees

- `0x140009844`
- `0x14000fbb0`
- `0x140012010`

## string_xrefs

- `0x140009875`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Data::Json::IJsonObject>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, a2);
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
0x140009844  push    rbx
0x140009846  sub     rsp, 30h
0x14000984a  mov     rcx, [rcx]
0x14000984d  mov     rbx, rdx
0x140009850  mov     qword ptr [rdx], 0
0x140009857  mov     r8, rdx
0x14000985a  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x140009861  mov     rax, [rcx]
0x140009864  mov     rax, [rax]
0x140009867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000986c  test    eax, eax
0x14000986e  jns     short loc_14000988A
0x140009870  mov     rcx, [rsp+38h]; this
0x140009875  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000987c  mov     r9d, eax; char *
0x14000987f  mov     edx, 1CBEh; void *
0x140009884  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000988a  mov     rax, rbx
0x14000988d  add     rsp, 30h
0x140009891  pop     rbx
0x140009892  retn
```
