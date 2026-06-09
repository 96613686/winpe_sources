# CodeIntegrity::make_unique_si_ptr<_SIPOLICY_FILE_ITEM [0]>(unsigned __int64)

- ea: `0x18001b574`
- end: `0x18001b5bd`
- name: `??$make_unique_si_ptr@$$BY0A@U_SIPOLICY_FILE_ITEM@@@CodeIntegrity@@YA?AV?$unique_ptr@$$BY0A@U_SIPOLICY_FILE_ITEM@@U?$function_deleter@P6AXPEAX@Z$1?SIPolicyFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `73`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c714`

## callees

- `0x1800082ac`
- `0x18001b574`
- `0x18001b63c`

## string_xrefs

- `0x18001b5a1`: `onecore\base\ci\management\dll\smartsi.h`

## pseudocode

```c
_QWORD *__fastcall CodeIntegrity::make_unique_si_ptr<_SIPOLICY_FILE_ITEM [0]>(_QWORD *a1)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  CodeIntegrity::make_unique_si_ptr_nothrow<_SIPOLICY_FILE_ITEM [0]>(a1);
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
0x18001b574  mov     [rsp+arg_0], rcx
0x18001b579  push    rbx
0x18001b57a  sub     rsp, 30h
0x18001b57e  mov     rbx, rcx
0x18001b581  mov     [rsp+38h+var_18], 0
0x18001b589  call    ??$make_unique_si_ptr_nothrow@$$BY0A@U_SIPOLICY_FILE_ITEM@@@CodeIntegrity@@YA?AV?$unique_ptr@$$BY0A@U_SIPOLICY_FILE_ITEM@@U?$function_deleter@P6AXPEAX@Z$1?SIPolicyFree@@YAX0@Z@wil@@@wistd@@_K@Z; CodeIntegrity::make_unique_si_ptr_nothrow<_SIPOLICY_FILE_ITEM [0]>(unsigned __int64)
0x18001b58e  mov     [rsp+38h+var_18], 1
0x18001b596  mov     rcx, [rsp+38h]; this
0x18001b59b  cmp     qword ptr [rbx], 0
0x18001b59f  jnz     short loc_18001B5B3
0x18001b5a1  lea     r8, aOnecoreBaseCiM_6; "onecore\\base\\ci\\management\\dll\\sma"...
0x18001b5a8  mov     edx, 53h ; 'S'; void *
0x18001b5ad  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18001b5b3  mov     rax, rbx
0x18001b5b6  add     rsp, 30h
0x18001b5ba  pop     rbx
0x18001b5bb  retn
```
