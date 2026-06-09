# wil::invoke_rpc_nothrow<long (&)(void *,ushort,unsigned __int64 * const,char * const,unsigned __int64 * const,int * const),void * &,ushort &,unsigned __int64 * &,char * &,unsigned __int64 * &,int * &>(long (&)(void *,ushort,unsigned __int64 * const,char * const,unsigned __int64 * const,int * const),void * &,ushort &,unsigned __int64 * &,char * &,unsigned __int64 * &,int * &)

- ea: `0x1800086ec`
- end: `0x18000877c`
- name: `??$invoke_rpc_nothrow@A6AJPEAXGQEA_KQEAD1QEAH@ZAEAPEAXAEAGAEAQEA_KAEAQEADAEAQEA_KAEAQEAH@wil@@YAJA6AJPEAXGQEA_KQEAD1QEAH@ZAEAPEAXAEAGAEAQEA_KAEAQEAD7AEAQEAH@Z`
- size: `144`
- prototype: `__int64 __fastcall(__int64, int, int, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a920`

## callees

- `0x180006214`
- `0x1800083b8`
- `0x1800086ec`

## string_xrefs

- `0x18000872d`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x180008763`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::invoke_rpc_nothrow<long (&)(void *,unsigned short,unsigned __int64 * const,char * const,unsigned __int64 * const,int * const),void * &,unsigned short &,unsigned __int64 * &,char * &,unsigned __int64 * &,int * &>(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  int v7; // eax
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v7 = wistd::__invoke<long (&)(void *,unsigned short,unsigned __int64 * const,char * const,unsigned __int64 * const,int * const),void * &,unsigned short &,unsigned __int64 * &,char * &,unsigned __int64 * &,int * &>(
         (unsigned int)MosHostReportCacheMiss,
         a2,
         a3,
         a4,
         a5,
         a6,
         a7);
  v8 = v7;
  if ( v7 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\rpc_helpers.h",
    (const char *)(unsigned int)v7,
    v10);
  return v8;
}

```

## disassembly

```asm
0x1800086ec  push    rbx
0x1800086ee  sub     rsp, 40h
0x1800086f2  mov     rax, [rsp+48h+arg_30]
0x1800086fa  mov     [rsp+48h+var_18], rax
0x1800086ff  mov     rax, [rsp+48h+arg_28]
0x180008704  mov     [rsp+48h+var_20], rax
0x180008709  mov     rax, [rsp+48h+arg_20]
0x18000870e  mov     qword ptr [rsp+48h+var_28], rax; int
0x180008713  lea     rcx, MosHostReportCacheMiss
0x18000871a  call    ??$__invoke@A6AJPEAXGQEA_KQEAD1QEAH@ZAEAPEAXAEAGAEAQEA_KAEAQEADAEAQEA_KAEAQEAH@wistd@@YAJA6AJPEAXGQEA_KQEAD1QEAH@ZAEAPEAXAEAGAEAQEA_KAEAQEAD7AEAQEAH@Z; wistd::__invoke<long (&)(void *,ushort,unsigned __int64 * const,char * const,unsigned __int64 * const,int * const),void * &,ushort &,unsigned __int64 * &,char * &,unsigned __int64 * &,int * &>(long (&)(void *,ushort,unsigned __int64 * const,char * const,unsigned __int64 * const,int * const),void * &,ushort &,unsigned __int64 * &,char * &,unsigned __int64 * &,int * &)
0x18000871f  mov     ebx, eax
0x180008721  test    eax, eax
0x180008723  jns     short loc_180008742
0x180008725  mov     rcx, [rsp+48h]; this
0x18000872a  mov     r9d, eax; char *
0x18000872d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008734  mov     edx, 5Eh ; '^'; void *
0x180008739  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000873e  mov     eax, ebx
0x180008740  jmp     short loc_180008776
0x180008742  xor     eax, eax
0x180008744  jmp     short loc_180008776
0x180008746  mov     ebx, eax
0x180008748  test    eax, eax
0x18000874a  js      short loc_180008757
0x18000874c  jle     short loc_180008757
0x18000874e  movzx   ebx, ax
0x180008751  or      ebx, 80070000h
0x180008757  test    ebx, ebx
0x180008759  jns     short loc_180008774
0x18000875b  mov     rcx, [rsp+48h]; this
0x180008760  mov     r9d, ebx; char *
0x180008763  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000876a  mov     edx, 63h ; 'c'; void *
0x18000876f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008774  mov     eax, ebx
0x180008776  add     rsp, 40h
0x18000877a  pop     rbx
0x18000877b  retn
```
