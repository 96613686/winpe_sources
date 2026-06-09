# wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::query<Windows::Storage::Streams::IBufferByteAccess>(void)

- ea: `0x180016db0`
- end: `0x180016dff`
- name: `??$query@UIBufferByteAccess@Streams@Storage@Windows@@@?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIBufferByteAccess@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022e18`

## callees

- `0x180016db0`
- `0x180022b80`
- `0x180031010`

## string_xrefs

- `0x180016de1`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::query<Windows::Storage::Streams::IBufferByteAccess>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_905a0fef_bc53_11df_8c49_001e4fc686da, a2);
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
0x180016db0  push    rbx
0x180016db2  sub     rsp, 30h
0x180016db6  mov     rcx, [rcx]
0x180016db9  mov     rbx, rdx
0x180016dbc  mov     qword ptr [rdx], 0
0x180016dc3  mov     r8, rdx
0x180016dc6  lea     rdx, _GUID_905a0fef_bc53_11df_8c49_001e4fc686da
0x180016dcd  mov     rax, [rcx]
0x180016dd0  mov     rax, [rax]
0x180016dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dd8  test    eax, eax
0x180016dda  jns     short loc_180016DF6
0x180016ddc  mov     rcx, [rsp+38h]; this
0x180016de1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016de8  mov     r9d, eax; char *
0x180016deb  mov     edx, 1CBEh; void *
0x180016df0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016df6  mov     rax, rbx
0x180016df9  add     rsp, 30h
0x180016dfd  pop     rbx
0x180016dfe  retn
```
