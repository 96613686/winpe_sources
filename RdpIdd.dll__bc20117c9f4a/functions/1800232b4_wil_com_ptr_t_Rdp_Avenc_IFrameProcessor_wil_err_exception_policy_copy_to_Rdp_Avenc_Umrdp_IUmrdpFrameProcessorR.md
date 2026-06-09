# wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy>::copy_to<Rdp::Avenc::Umrdp::IUmrdpFrameProcessorRailPrivate>(Rdp::Avenc::Umrdp::IUmrdpFrameProcessorRailPrivate * *)

- ea: `0x1800232b4`
- end: `0x180023300`
- name: `??$copy_to@UIUmrdpFrameProcessorRailPrivate@Umrdp@Avenc@Rdp@@@?$com_ptr_t@UIFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUIUmrdpFrameProcessorRailPrivate@Umrdp@Avenc@Rdp@@@Z`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025c90`

## callees

- `0x18001dd50`
- `0x1800232b4`
- `0x18003f010`

## string_xrefs

- `0x1800232de`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
void __fastcall wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy>::copy_to<Rdp::Avenc::Umrdp::IUmrdpFrameProcessorRailPrivate>(
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
    v3 = (**v2)(v2, &GUID_c9c525cc_0524_4b8b_9399_4e3a9b49467e, a2);
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
0x1800232b4  sub     rsp, 28h
0x1800232b8  mov     rcx, [rcx]
0x1800232bb  test    rcx, rcx
0x1800232be  jz      short loc_1800232F3
0x1800232c0  mov     rax, [rcx]
0x1800232c3  mov     r8, rdx
0x1800232c6  lea     rdx, _GUID_c9c525cc_0524_4b8b_9399_4e3a9b49467e
0x1800232cd  mov     rax, [rax]
0x1800232d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232d5  test    eax, eax
0x1800232d7  jns     short loc_1800232FA
0x1800232d9  mov     rcx, [rsp+28h]; this
0x1800232de  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800232e5  mov     r9d, eax; char *
0x1800232e8  mov     edx, 1CBEh; void *
0x1800232ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800232f3  mov     qword ptr [rdx], 0
0x1800232fa  add     rsp, 28h
0x1800232fe  retn
```
