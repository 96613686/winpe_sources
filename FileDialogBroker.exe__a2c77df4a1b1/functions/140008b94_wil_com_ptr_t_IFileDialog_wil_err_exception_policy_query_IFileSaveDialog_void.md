# wil::com_ptr_t<IFileDialog,wil::err_exception_policy>::query<IFileSaveDialog>(void)

- ea: `0x140008b94`
- end: `0x140008be3`
- name: `??$query@UIFileSaveDialog@@@?$com_ptr_t@UIFileDialog@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFileSaveDialog@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c500`

## callees

- `0x140007df4`
- `0x140008b94`
- `0x140014010`

## string_xrefs

- `0x140008bc5`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<IFileDialog,wil::err_exception_policy>::query<IFileSaveDialog>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_84bccd23_5fde_4cdb_aea4_af64b83d78ab, a2);
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
0x140008b94  push    rbx
0x140008b96  sub     rsp, 30h
0x140008b9a  mov     rcx, [rcx]
0x140008b9d  mov     rbx, rdx
0x140008ba0  mov     qword ptr [rdx], 0
0x140008ba7  mov     r8, rdx
0x140008baa  lea     rdx, _GUID_84bccd23_5fde_4cdb_aea4_af64b83d78ab
0x140008bb1  mov     rax, [rcx]
0x140008bb4  mov     rax, [rax]
0x140008bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008bbc  test    eax, eax
0x140008bbe  jns     short loc_140008BDA
0x140008bc0  mov     rcx, [rsp+38h]; this
0x140008bc5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140008bcc  mov     r9d, eax; char *
0x140008bcf  mov     edx, 1CBEh; void *
0x140008bd4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140008bda  mov     rax, rbx
0x140008bdd  add     rsp, 30h
0x140008be1  pop     rbx
0x140008be2  retn
```
