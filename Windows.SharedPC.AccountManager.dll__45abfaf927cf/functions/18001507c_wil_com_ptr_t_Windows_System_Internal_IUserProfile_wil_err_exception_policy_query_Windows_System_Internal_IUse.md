# wil::com_ptr_t<Windows::System::Internal::IUserProfile,wil::err_exception_policy>::query<Windows::System::Internal::IUserProfile2>(void)

- ea: `0x18001507c`
- end: `0x1800150cb`
- name: `??$query@UIUserProfile2@Internal@System@Windows@@@?$com_ptr_t@UIUserProfile@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIUserProfile2@Internal@System@Windows@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015828`
- `0x180022f60`
- `0x1800230a8`

## callees

- `0x18000ccd4`
- `0x18001507c`
- `0x180026010`

## string_xrefs

- `0x1800150ad`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::com_ptr_t<Windows::System::Internal::IUserProfile,wil::err_exception_policy>::query<Windows::System::Internal::IUserProfile2>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_2a426936_3887_4e38_9b4b_6064463481b8, a2);
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
0x18001507c  push    rbx
0x18001507e  sub     rsp, 30h
0x180015082  mov     rcx, [rcx]
0x180015085  mov     rbx, rdx
0x180015088  mov     qword ptr [rdx], 0
0x18001508f  mov     r8, rdx
0x180015092  lea     rdx, _GUID_2a426936_3887_4e38_9b4b_6064463481b8
0x180015099  mov     rax, [rcx]
0x18001509c  mov     rax, [rax]
0x18001509f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150a4  test    eax, eax
0x1800150a6  jns     short loc_1800150C2
0x1800150a8  mov     rcx, [rsp+38h]; this
0x1800150ad  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800150b4  mov     r9d, eax; char *
0x1800150b7  mov     edx, 1CBEh; void *
0x1800150bc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800150c2  mov     rax, rbx
0x1800150c5  add     rsp, 30h
0x1800150c9  pop     rbx
0x1800150ca  retn
```
