# wil::safe_cast<ulong,__int64,0>(__int64)

- ea: `0x18000c710`
- end: `0x18000c769`
- name: `??$safe_cast@K_J$0A@@wil@@YAK_J@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b23c`

## callees

- `0x18000c710`
- `0x18000c770`
- `0x18000d2a0`
- `0x180010f80`

## string_xrefs

- `0x18000c73e`: `onecore\internal\sdk\inc\wil\opensource\wil\safecast.h`

## pseudocode

```c
__int64 __fastcall wil::safe_cast<unsigned long,__int64,0>(__int64 a1)
{
  int v1; // eax
  unsigned int v3; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = 0;
  v1 = LongLongToULong(a1, &v3);
  if ( v1 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\safecast.h",
      (const char *)(unsigned int)v1,
      v3);
  return v3;
}

```

## disassembly

```asm
0x18000c710  sub     rsp, 38h
0x18000c714  mov     rax, cs:__security_cookie
0x18000c71b  xor     rax, rsp
0x18000c71e  mov     [rsp+38h+var_10], rax
0x18000c723  lea     rdx, [rsp+38h+var_18]; unsigned int *
0x18000c728  mov     [rsp+38h+var_18], 0; int
0x18000c730  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x18000c735  test    eax, eax
0x18000c737  jns     short loc_18000C753
0x18000c739  mov     rcx, [rsp+38h]; this
0x18000c73e  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c745  mov     r9d, eax; char *
0x18000c748  mov     edx, 132h; void *
0x18000c74d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c753  mov     eax, [rsp+38h+var_18]
0x18000c757  mov     rcx, [rsp+38h+var_10]
0x18000c75c  xor     rcx, rsp; StackCookie
0x18000c75f  call    __security_check_cookie
0x18000c764  add     rsp, 38h
0x18000c768  retn
```
