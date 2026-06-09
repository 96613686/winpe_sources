# wil::make_unique_cotaskmem<CREDUI_ADDITIONAL_INFO,>(void)

- ea: `0x18005d0ac`
- end: `0x18005d113`
- name: `??$make_unique_cotaskmem@UCREDUI_ADDITIONAL_INFO@@$$V@wil@@YA?AV?$unique_ptr@UCREDUI_ADDITIONAL_INFO@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ`
- size: `103`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005d1b8`

## callees

- `0x180023814`
- `0x18005d0ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005d0c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005d0c6`

## string_xrefs

- `0x18005d0f7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem<CREDUI_ADDITIONAL_INFO,>(_QWORD *a1)
{
  _OWORD *v2; // rax
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = CoTaskMemAlloc(0x20u);
  *a1 = v2;
  if ( v2 )
  {
    *v2 = 0;
    v2[1] = 0;
  }
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x1841,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v3);
  return a1;
}

```

## disassembly

```asm
0x18005d0ac  mov     [rsp+arg_0], rcx
0x18005d0b1  push    rbx
0x18005d0b2  sub     rsp, 30h
0x18005d0b6  mov     rbx, rcx
0x18005d0b9  mov     [rsp+38h+var_18], 0
0x18005d0c1  mov     ecx, 20h ; ' '; cb
0x18005d0c6  call    cs:__imp_CoTaskMemAlloc
0x18005d0cd  nop     dword ptr [rax+rax+00h]
0x18005d0d2  mov     [rbx], rax
0x18005d0d5  test    rax, rax
0x18005d0d8  jz      short loc_18005D0E4
0x18005d0da  xorps   xmm0, xmm0
0x18005d0dd  movups  xmmword ptr [rax], xmm0
0x18005d0e0  movups  xmmword ptr [rax+10h], xmm0
0x18005d0e4  mov     [rsp+38h+var_18], 1
0x18005d0ec  mov     rcx, [rsp+38h]; this
0x18005d0f1  cmp     qword ptr [rbx], 0
0x18005d0f5  jnz     short loc_18005D109
0x18005d0f7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005d0fe  mov     edx, 1841h; void *
0x18005d103  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18005d109  mov     rax, rbx
0x18005d10c  add     rsp, 30h
0x18005d110  pop     rbx
0x18005d111  retn
```
