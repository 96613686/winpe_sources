# SRCache_DuplicateString

- ea: `0x18000de40`
- end: `0x18000de76`
- name: `SRCache_DuplicateString`
- size: `54`
- prototype: `__int64 __fastcall(wil *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000940c`
- `0x18000dc7c`
- `0x18000de40`

## string_xrefs

- `0x18000de56`: `onecore\base\appmodel\staterepository\core\lib\srcache.cpp`

## pseudocode

```c
__int64 __fastcall SRCache_DuplicateString(wil *a1, unsigned __int16 *a2, unsigned __int16 **a3)
{
  int nullable_string_nothrow; // eax
  unsigned int v4; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  nullable_string_nothrow = wil::make_nullable_string_nothrow(a1, a2, a3);
  v4 = nullable_string_nothrow;
  if ( nullable_string_nothrow >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x63,
    (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcache.cpp",
    (const char *)(unsigned int)nullable_string_nothrow);
  return v4;
}

```

## disassembly

```asm
0x18000de40  push    rbx; int
0x18000de42  sub     rsp, 20h
0x18000de46  call    ?make_nullable_string_nothrow@wil@@YAJPEBGPEAPEAG@Z; wil::make_nullable_string_nothrow(ushort const *,ushort * *)
0x18000de4b  mov     ebx, eax
0x18000de4d  test    eax, eax
0x18000de4f  jns     short loc_18000DE6E
0x18000de51  mov     rcx, [rsp+28h]; this
0x18000de56  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x18000de5d  mov     r9d, eax; char *
0x18000de60  mov     edx, 63h ; 'c'; void *
0x18000de65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de6a  mov     eax, ebx
0x18000de6c  jmp     short loc_18000DE70
0x18000de6e  xor     eax, eax
0x18000de70  add     rsp, 20h
0x18000de74  pop     rbx
0x18000de75  retn
```
