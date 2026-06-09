# CodeIntegrity::make_unique_si_ptr<ushort * [0]>(unsigned __int64)

- ea: `0x18001b524`
- end: `0x18001b56d`
- name: `??$make_unique_si_ptr@$$BY0A@PEAG@CodeIntegrity@@YA?AV?$unique_ptr@$$BY0A@PEAGU?$function_deleter@P6AXPEAX@Z$1?SIPolicyFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `73`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c714`

## callees

- `0x1800082ac`
- `0x18001b524`
- `0x18001b5c4`

## string_xrefs

- `0x18001b551`: `onecore\base\ci\management\dll\smartsi.h`

## pseudocode

```c
_QWORD *__fastcall CodeIntegrity::make_unique_si_ptr<unsigned short * [0]>(_QWORD *a1)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  CodeIntegrity::make_unique_si_ptr_nothrow<unsigned short * [0]>(a1);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\base\\ci\\management\\dll\\smartsi.h",
      v2);
  return a1;
}

```

## disassembly

```asm
0x18001b524  mov     [rsp+arg_0], rcx
0x18001b529  push    rbx
0x18001b52a  sub     rsp, 30h
0x18001b52e  mov     rbx, rcx
0x18001b531  mov     [rsp+38h+var_18], 0
0x18001b539  call    ??$make_unique_si_ptr_nothrow@$$BY0A@PEAG@CodeIntegrity@@YA?AV?$unique_ptr@$$BY0A@PEAGU?$function_deleter@P6AXPEAX@Z$1?SIPolicyFree@@YAX0@Z@wil@@@wistd@@_K@Z; CodeIntegrity::make_unique_si_ptr_nothrow<ushort * [0]>(unsigned __int64)
0x18001b53e  mov     [rsp+38h+var_18], 1
0x18001b546  mov     rcx, [rsp+38h]; this
0x18001b54b  cmp     qword ptr [rbx], 0
0x18001b54f  jnz     short loc_18001B563
0x18001b551  lea     r8, aOnecoreBaseCiM_6; "onecore\\base\\ci\\management\\dll\\sma"...
0x18001b558  mov     edx, 53h ; 'S'; void *
0x18001b55d  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18001b563  mov     rax, rbx
0x18001b566  add     rsp, 30h
0x18001b56a  pop     rbx
0x18001b56b  retn
```
