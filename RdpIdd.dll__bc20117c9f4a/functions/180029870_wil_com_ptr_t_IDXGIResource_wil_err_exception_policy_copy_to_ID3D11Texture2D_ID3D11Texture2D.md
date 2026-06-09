# wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::copy_to<ID3D11Texture2D>(ID3D11Texture2D * *)

- ea: `0x180029870`
- end: `0x1800298bc`
- name: `??$copy_to@UID3D11Texture2D@@@?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUID3D11Texture2D@@@Z`
- size: `76`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800299ac`
- `0x180029c18`
- `0x18002f0b0`

## callees

- `0x18001dd50`
- `0x180029870`
- `0x18003f010`

## string_xrefs

- `0x18002989a`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
void __fastcall wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::copy_to<ID3D11Texture2D>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v3; // eax
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *a1;
  if ( v2 )
  {
    v3 = (**v2)(v2, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, a2);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
        (const char *)(unsigned int)v3,
        v4);
  }
  else
  {
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x180029870  sub     rsp, 28h
0x180029874  mov     rcx, [rcx]
0x180029877  test    rcx, rcx
0x18002987a  jz      short loc_1800298AF
0x18002987c  mov     rax, [rcx]
0x18002987f  mov     r8, rdx
0x180029882  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x180029889  mov     rax, [rax]
0x18002988c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029891  test    eax, eax
0x180029893  jns     short loc_1800298B6
0x180029895  mov     rcx, [rsp+28h]; this
0x18002989a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800298a1  mov     r9d, eax; char *
0x1800298a4  mov     edx, 1CBEh; void *
0x1800298a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800298af  mov     qword ptr [rdx], 0
0x1800298b6  add     rsp, 28h
0x1800298ba  retn
```
