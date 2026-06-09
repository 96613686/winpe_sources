# wil::com_ptr_t<Rdp::Avenc::IEncodingProcessor,wil::err_exception_policy>::copy_to<Rdp::Avenc::Umrdp::IUmrdpProcessorRailPrivate>(Rdp::Avenc::Umrdp::IUmrdpProcessorRailPrivate * *)

- ea: `0x1800138a8`
- end: `0x1800138f4`
- name: `??$copy_to@UIUmrdpProcessorRailPrivate@Umrdp@Avenc@Rdp@@@?$com_ptr_t@UIEncodingProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUIUmrdpProcessorRailPrivate@Umrdp@Avenc@Rdp@@@Z`
- size: `76`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017b74`
- `0x1800184b4`
- `0x18001a6bc`

## callees

- `0x1800138a8`
- `0x18001dd50`
- `0x18003f010`

## string_xrefs

- `0x1800138d2`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
void __fastcall wil::com_ptr_t<Rdp::Avenc::IEncodingProcessor,wil::err_exception_policy>::copy_to<Rdp::Avenc::Umrdp::IUmrdpProcessorRailPrivate>(
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
    v3 = (**v2)(v2, &GUID_6a7e7a85_be2f_4472_9749_22eac352fe86, a2);
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
0x1800138a8  sub     rsp, 28h
0x1800138ac  mov     rcx, [rcx]
0x1800138af  test    rcx, rcx
0x1800138b2  jz      short loc_1800138E7
0x1800138b4  mov     rax, [rcx]
0x1800138b7  mov     r8, rdx
0x1800138ba  lea     rdx, _GUID_6a7e7a85_be2f_4472_9749_22eac352fe86
0x1800138c1  mov     rax, [rax]
0x1800138c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138c9  test    eax, eax
0x1800138cb  jns     short loc_1800138EE
0x1800138cd  mov     rcx, [rsp+28h]; this
0x1800138d2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800138d9  mov     r9d, eax; char *
0x1800138dc  mov     edx, 1CBEh; void *
0x1800138e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800138e7  mov     qword ptr [rdx], 0
0x1800138ee  add     rsp, 28h
0x1800138f2  retn
```
