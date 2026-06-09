# wil::make_unique_cotaskmem<SoftLockoutInfoMetadata,>(void)

- ea: `0x180017210`
- end: `0x180017278`
- name: `??$make_unique_cotaskmem@USoftLockoutInfoMetadata@@$$V@wil@@YA?AV?$unique_ptr@USoftLockoutInfoMetadata@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ`
- size: `104`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800112d0`

## callees

- `0x180017210`
- `0x180023814`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001722a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001722a`

## string_xrefs

- `0x18001725c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem<SoftLockoutInfoMetadata,>(_QWORD *a1)
{
  _DWORD *v2; // rax
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = CoTaskMemAlloc(0x14u);
  *a1 = v2;
  if ( v2 )
  {
    *(_OWORD *)v2 = 0;
    v2[4] = 0;
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
0x180017210  mov     [rsp+arg_0], rcx
0x180017215  push    rbx
0x180017216  sub     rsp, 30h
0x18001721a  mov     rbx, rcx
0x18001721d  mov     [rsp+38h+var_18], 0
0x180017225  mov     ecx, 14h; cb
0x18001722a  call    cs:__imp_CoTaskMemAlloc
0x180017231  nop     dword ptr [rax+rax+00h]
0x180017236  mov     [rbx], rax
0x180017239  test    rax, rax
0x18001723c  jz      short loc_180017249
0x18001723e  xorps   xmm0, xmm0
0x180017241  xor     ecx, ecx
0x180017243  movups  xmmword ptr [rax], xmm0
0x180017246  mov     [rax+10h], ecx
0x180017249  mov     [rsp+38h+var_18], 1
0x180017251  mov     rcx, [rsp+38h]; this
0x180017256  cmp     qword ptr [rbx], 0
0x18001725a  jnz     short loc_18001726E
0x18001725c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180017263  mov     edx, 1841h; void *
0x180017268  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18001726e  mov     rax, rbx
0x180017271  add     rsp, 30h
0x180017275  pop     rbx
0x180017276  retn
```
