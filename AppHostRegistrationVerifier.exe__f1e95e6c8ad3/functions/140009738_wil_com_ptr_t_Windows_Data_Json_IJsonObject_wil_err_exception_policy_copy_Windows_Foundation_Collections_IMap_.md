# wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::copy<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(void)

- ea: `0x140009738`
- end: `0x14000978c`
- name: `??$copy@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@1@XZ`
- size: `84`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000ed9c`

## callees

- `0x140009738`
- `0x14000fbb0`
- `0x140012010`

## string_xrefs

- `0x14000976e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::copy<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  if ( v2 )
  {
    v4 = (**v2)(v2, &GUID_c9d9a725_786b_5113_b4b7_9b61764c220b, a2);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v4,
        v6);
  }
  return a2;
}

```

## disassembly

```asm
0x140009738  push    rbx
0x14000973a  sub     rsp, 30h
0x14000973e  mov     rcx, [rcx]
0x140009741  mov     rbx, rdx
0x140009744  mov     qword ptr [rdx], 0
0x14000974b  test    rcx, rcx
0x14000974e  jz      short loc_140009783
0x140009750  mov     rax, [rcx]
0x140009753  mov     r8, rdx
0x140009756  lea     rdx, _GUID_c9d9a725_786b_5113_b4b7_9b61764c220b
0x14000975d  mov     rax, [rax]
0x140009760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009765  test    eax, eax
0x140009767  jns     short loc_140009783
0x140009769  mov     rcx, [rsp+38h]; this
0x14000976e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140009775  mov     r9d, eax; char *
0x140009778  mov     edx, 1CBEh; void *
0x14000977d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009783  mov     rax, rbx
0x140009786  add     rsp, 30h
0x14000978a  pop     rbx
0x14000978b  retn
```
