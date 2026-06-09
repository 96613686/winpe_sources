# wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_exception_policy>::query<IMoUsoOrchestrator>(void)

- ea: `0x180018b0c`
- end: `0x180018b5b`
- name: `??$query@UIMoUsoOrchestrator@@@?$com_ptr_t@UIUpdateSessionOrchestrator@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIMoUsoOrchestrator@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x180018b0c`
- `0x180034a30`
- `0x18005c5e0`

## string_xrefs

- `0x180018b46`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_exception_policy>::query<IMoUsoOrchestrator>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_c57692f8_8f5f_47cb_9381_34329b40285a, a2);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v4,
      v6);
  return a2;
}

```

## disassembly

```asm
0x180018b0c  push    rbx
0x180018b0e  sub     rsp, 30h
0x180018b12  mov     rcx, [rcx]
0x180018b15  mov     rbx, rdx
0x180018b18  mov     qword ptr [rdx], 0
0x180018b1f  mov     r8, rdx
0x180018b22  lea     rdx, _GUID_c57692f8_8f5f_47cb_9381_34329b40285a
0x180018b29  mov     rax, [rcx]
0x180018b2c  mov     rax, [rax]
0x180018b2f  call    _guard_dispatch_icall
0x180018b34  test    eax, eax
0x180018b36  js      short loc_180018B41
0x180018b38  mov     rax, rbx
0x180018b3b  add     rsp, 30h
0x180018b3f  pop     rbx
0x180018b40  retn
0x180018b41  mov     rcx, [rsp+38h]; this
0x180018b46  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180018b4d  mov     r9d, eax; char *
0x180018b50  mov     edx, 1C96h; void *
0x180018b55  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
