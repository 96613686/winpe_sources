# wil::com_ptr_t<Rdp::Avenc::IEncodingProcessor,wil::err_exception_policy>::copy_to<Rdp::Avenc::IFileIoControlEvents>(Rdp::Avenc::IFileIoControlEvents * *)

- ea: `0x180013854`
- end: `0x1800138a2`
- name: `??$copy_to@UIFileIoControlEvents@Avenc@Rdp@@@?$com_ptr_t@UIEncodingProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUIFileIoControlEvents@Avenc@Rdp@@@Z`
- size: `78`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017b74`
- `0x18001818c`
- `0x18001d938`

## callees

- `0x180013854`
- `0x18001dd50`
- `0x18003f010`

## string_xrefs

- `0x18001388d`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
void __fastcall wil::com_ptr_t<Rdp::Avenc::IEncodingProcessor,wil::err_exception_policy>::copy_to<Rdp::Avenc::IFileIoControlEvents>(
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
    v3 = (**v2)(v2, &GUID_919aab83_d30b_4d65_9465_eb7e9f74c123, a2);
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
0x180013854  sub     rsp, 28h
0x180013858  mov     rcx, [rcx]
0x18001385b  test    rcx, rcx
0x18001385e  jz      short loc_18001387B
0x180013860  mov     rax, [rcx]
0x180013863  mov     r8, rdx
0x180013866  lea     rdx, _GUID_919aab83_d30b_4d65_9465_eb7e9f74c123
0x18001386d  mov     rax, [rax]
0x180013870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013875  test    eax, eax
0x180013877  js      short loc_180013888
0x180013879  jmp     short loc_180013882
0x18001387b  mov     qword ptr [rdx], 0
0x180013882  add     rsp, 28h
0x180013886  retn
0x180013888  mov     rcx, [rsp+28h]; this
0x18001388d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180013894  mov     r9d, eax; char *
0x180013897  mov     edx, 1CBEh; void *
0x18001389c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
