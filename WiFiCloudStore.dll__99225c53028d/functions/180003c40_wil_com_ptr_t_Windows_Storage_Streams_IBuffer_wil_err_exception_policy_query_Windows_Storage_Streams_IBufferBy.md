# wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::query<Windows::Storage::Streams::IBufferByteAccess>(void)

- ea: `0x180003c40`
- end: `0x180003c8f`
- name: `??$query@UIBufferByteAccess@Streams@Storage@Windows@@@?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIBufferByteAccess@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800039e0`

## callees

- `0x180003c40`
- `0x18002e2d0`
- `0x180041010`

## string_xrefs

- `0x180003c7a`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

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
0x180003c40  push    rbx
0x180003c42  sub     rsp, 30h
0x180003c46  mov     rcx, [rcx]
0x180003c49  mov     rbx, rdx
0x180003c4c  mov     qword ptr [rdx], 0
0x180003c53  mov     r8, rdx
0x180003c56  lea     rdx, _GUID_905a0fef_bc53_11df_8c49_001e4fc686da
0x180003c5d  mov     rax, [rcx]
0x180003c60  mov     rax, [rax]
0x180003c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c68  test    eax, eax
0x180003c6a  js      short loc_180003C75
0x180003c6c  mov     rax, rbx
0x180003c6f  add     rsp, 30h
0x180003c73  pop     rbx
0x180003c74  retn
0x180003c75  mov     rcx, [rsp+38h]; this
0x180003c7a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003c81  mov     r9d, eax; char *
0x180003c84  mov     edx, 1CBEh; void *
0x180003c89  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
