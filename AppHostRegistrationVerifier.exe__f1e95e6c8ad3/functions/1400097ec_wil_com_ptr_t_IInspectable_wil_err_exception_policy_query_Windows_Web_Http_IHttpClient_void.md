# wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Web::Http::IHttpClient>(void)

- ea: `0x1400097ec`
- end: `0x14000983b`
- name: `??$query@UIHttpClient@Http@Web@Windows@@@?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIHttpClient@Http@Web@Windows@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400083ac`

## callees

- `0x1400097ec`
- `0x14000fbb0`
- `0x140012010`

## string_xrefs

- `0x14000981d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Web::Http::IHttpClient>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_7fda1151_3574_4880_a8ba_e6b1e0061f3d, a2);
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
0x1400097ec  push    rbx
0x1400097ee  sub     rsp, 30h
0x1400097f2  mov     rcx, [rcx]
0x1400097f5  mov     rbx, rdx
0x1400097f8  mov     qword ptr [rdx], 0
0x1400097ff  mov     r8, rdx
0x140009802  lea     rdx, _GUID_7fda1151_3574_4880_a8ba_e6b1e0061f3d
0x140009809  mov     rax, [rcx]
0x14000980c  mov     rax, [rax]
0x14000980f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009814  test    eax, eax
0x140009816  jns     short loc_140009832
0x140009818  mov     rcx, [rsp+38h]; this
0x14000981d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140009824  mov     r9d, eax; char *
0x140009827  mov     edx, 1CBEh; void *
0x14000982c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009832  mov     rax, rbx
0x140009835  add     rsp, 30h
0x140009839  pop     rbx
0x14000983a  retn
```
