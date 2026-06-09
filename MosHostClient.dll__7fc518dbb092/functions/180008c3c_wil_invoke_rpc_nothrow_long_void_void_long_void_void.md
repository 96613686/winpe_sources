# wil::invoke_rpc_nothrow<long (*&)(void * *),void * *>(long (*&)(void * *),void * * &&)

- ea: `0x180008c3c`
- end: `0x180008cad`
- name: `??$invoke_rpc_nothrow@AEAP6AJPEAPEAX@ZPEAPEAX@wil@@YAJAEAP6AJPEAPEAX@Z$$QEAPEAPEAX@Z`
- size: `113`
- prototype: `__int64 __fastcall(__int64 (__fastcall **)(_QWORD), _QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a760`
- `0x18000d1d0`
- `0x18000eca0`
- `0x18000fa20`

## callees

- `0x180006214`
- `0x180008c3c`
- `0x180012010`

## string_xrefs

- `0x180008c5e`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x180008c94`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::invoke_rpc_nothrow<long (*&)(void * *),void * *>(__int64 (__fastcall **a1)(_QWORD), _QWORD *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (*a1)(*a2);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\rpc_helpers.h",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x180008c3c  push    rbx; int
0x180008c3e  sub     rsp, 20h
0x180008c42  mov     rax, rcx
0x180008c45  mov     rcx, [rdx]
0x180008c48  mov     rax, [rax]
0x180008c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c50  mov     ebx, eax
0x180008c52  test    eax, eax
0x180008c54  jns     short loc_180008C73
0x180008c56  mov     rcx, [rsp+28h]; this
0x180008c5b  mov     r9d, eax; char *
0x180008c5e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008c65  mov     edx, 5Eh ; '^'; void *
0x180008c6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c6f  mov     eax, ebx
0x180008c71  jmp     short loc_180008CA7
0x180008c73  xor     eax, eax
0x180008c75  jmp     short loc_180008CA7
0x180008c77  mov     ebx, eax
0x180008c79  test    eax, eax
0x180008c7b  js      short loc_180008C88
0x180008c7d  jle     short loc_180008C88
0x180008c7f  movzx   ebx, ax
0x180008c82  or      ebx, 80070000h
0x180008c88  test    ebx, ebx
0x180008c8a  jns     short loc_180008CA5
0x180008c8c  mov     rcx, [rsp+28h]; this
0x180008c91  mov     r9d, ebx; char *
0x180008c94  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008c9b  mov     edx, 63h ; 'c'; void *
0x180008ca0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ca5  mov     eax, ebx
0x180008ca7  add     rsp, 20h
0x180008cab  pop     rbx
0x180008cac  retn
```
