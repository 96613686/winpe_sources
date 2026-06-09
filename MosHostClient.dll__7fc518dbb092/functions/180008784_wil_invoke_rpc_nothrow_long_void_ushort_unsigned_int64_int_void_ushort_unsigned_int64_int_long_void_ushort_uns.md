# wil::invoke_rpc_nothrow<long (&)(void *,ushort,unsigned __int64,int *),void * &,ushort &,unsigned __int64 &,int * &>(long (&)(void *,ushort,unsigned __int64,int *),void * &,ushort &,unsigned __int64 &,int * &)

- ea: `0x180008784`
- end: `0x1800087fd`
- name: `??$invoke_rpc_nothrow@A6AJPEAXG_KPEAH@ZAEAPEAXAEAGAEA_KAEAPEAH@wil@@YAJA6AJPEAXG_KPEAH@ZAEAPEAXAEAGAEA_KAEAPEAH@Z`
- size: `121`
- prototype: `__int64 __fastcall(__int64, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009eb0`

## callees

- `0x180006214`
- `0x180008420`
- `0x180008784`

## string_xrefs

- `0x1800087ae`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x1800087e4`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::invoke_rpc_nothrow<long (&)(void *,unsigned short,unsigned __int64,int *),void * &,unsigned short &,unsigned __int64 &,int * &>(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        __int64 a5)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = wistd::__invoke<long (&)(void *,unsigned short,unsigned __int64,int *),void * &,unsigned short &,unsigned __int64 &,int * &>(
         (unsigned int)MosHostCacheStateUseSlot,
         a2,
         a3,
         a4,
         a5);
  v6 = v5;
  if ( v5 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\rpc_helpers.h",
    (const char *)(unsigned int)v5,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180008784  push    rbx
0x180008786  sub     rsp, 30h
0x18000878a  mov     rax, qword ptr [rsp+38h+arg_20]
0x18000878f  mov     qword ptr [rsp+38h+var_18], rax; int
0x180008794  lea     rcx, MosHostCacheStateUseSlot
0x18000879b  call    ??$__invoke@A6AJPEAXG_KPEAH@ZAEAPEAXAEAGAEA_KAEAPEAH@wistd@@YAJA6AJPEAXG_KPEAH@ZAEAPEAXAEAGAEA_KAEAPEAH@Z; wistd::__invoke<long (&)(void *,ushort,unsigned __int64,int *),void * &,ushort &,unsigned __int64 &,int * &>(long (&)(void *,ushort,unsigned __int64,int *),void * &,ushort &,unsigned __int64 &,int * &)
0x1800087a0  mov     ebx, eax
0x1800087a2  test    eax, eax
0x1800087a4  jns     short loc_1800087C3
0x1800087a6  mov     rcx, [rsp+38h]; this
0x1800087ab  mov     r9d, eax; char *
0x1800087ae  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800087b5  mov     edx, 5Eh ; '^'; void *
0x1800087ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800087bf  mov     eax, ebx
0x1800087c1  jmp     short loc_1800087F7
0x1800087c3  xor     eax, eax
0x1800087c5  jmp     short loc_1800087F7
0x1800087c7  mov     ebx, eax
0x1800087c9  test    eax, eax
0x1800087cb  js      short loc_1800087D8
0x1800087cd  jle     short loc_1800087D8
0x1800087cf  movzx   ebx, ax
0x1800087d2  or      ebx, 80070000h
0x1800087d8  test    ebx, ebx
0x1800087da  jns     short loc_1800087F5
0x1800087dc  mov     rcx, [rsp+38h]; this
0x1800087e1  mov     r9d, ebx; char *
0x1800087e4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800087eb  mov     edx, 63h ; 'c'; void *
0x1800087f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800087f5  mov     eax, ebx
0x1800087f7  add     rsp, 30h
0x1800087fb  pop     rbx
0x1800087fc  retn
```
