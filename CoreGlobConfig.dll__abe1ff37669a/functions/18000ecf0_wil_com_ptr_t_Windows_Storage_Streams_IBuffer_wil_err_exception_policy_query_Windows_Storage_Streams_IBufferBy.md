# wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::query<Windows::Storage::Streams::IBufferByteAccess>(void)

- ea: `0x18000ecf0`
- end: `0x18000ed3f`
- name: `??$query@UIBufferByteAccess@Streams@Storage@Windows@@@?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIBufferByteAccess@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e11c`

## callees

- `0x18000ecf0`
- `0x18001b4e4`
- `0x180025010`

## string_xrefs

- `0x18000ed21`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

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
0x18000ecf0  push    rbx
0x18000ecf2  sub     rsp, 30h
0x18000ecf6  mov     rcx, [rcx]
0x18000ecf9  mov     rbx, rdx
0x18000ecfc  mov     qword ptr [rdx], 0
0x18000ed03  mov     r8, rdx
0x18000ed06  lea     rdx, _GUID_905a0fef_bc53_11df_8c49_001e4fc686da
0x18000ed0d  mov     rax, [rcx]
0x18000ed10  mov     rax, [rax]
0x18000ed13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed18  test    eax, eax
0x18000ed1a  jns     short loc_18000ED36
0x18000ed1c  mov     rcx, [rsp+38h]; this
0x18000ed21  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ed28  mov     r9d, eax; char *
0x18000ed2b  mov     edx, 1CBEh; void *
0x18000ed30  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000ed36  mov     rax, rbx
0x18000ed39  add     rsp, 30h
0x18000ed3d  pop     rbx
0x18000ed3e  retn
```
