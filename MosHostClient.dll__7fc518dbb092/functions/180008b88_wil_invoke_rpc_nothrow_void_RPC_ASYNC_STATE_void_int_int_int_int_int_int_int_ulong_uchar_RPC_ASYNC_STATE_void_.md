# wil::invoke_rpc_nothrow<void (&)(_RPC_ASYNC_STATE *,void *,int,int,int,int,int *,int *,int *,ulong *,uchar * *),_RPC_ASYNC_STATE * &,void * &,int &,int &,int &,int &,int *,int *,int *,ulong *,uchar * *>(void (&)(_RPC_ASYNC_STATE *,void *,int,int,int,int,int *,int *,int *,ulong *,uchar * *),_RPC_ASYNC_STATE * &,void * &,int &,int &,int &,int &,int * &&,int * &&,int * &&,ulong * &&,uchar * * &&)

- ea: `0x180008b88`
- end: `0x180008c36`
- name: `??$invoke_rpc_nothrow@A6AXPEAU_RPC_ASYNC_STATE@@PEAXHHHHPEAH22PEAKPEAPEAE@ZAEAPEAU1@AEAPEAXAEAHAEAHAEAHAEAHPEAHPEAHPEAHPEAKPEAPEAE@wil@@YAJA6AXPEAU_RPC_ASYNC_STATE@@PEAXHHHHPEAH22PEAKPEAPEAE@ZAEAPEAU1@AEAPEAXAEAH888$$QEAPEAH99$$QEAPEAK$$QEAPEAPEAE@Z`
- size: `174`
- prototype: `__int64 __fastcall(__int64, int, int, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800096d0`

## callees

- `0x180006214`
- `0x180008560`
- `0x180008b88`

## string_xrefs

- `0x180008c1d`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::invoke_rpc_nothrow<void (&)(_RPC_ASYNC_STATE *,void *,int,int,int,int,int *,int *,int *,unsigned long *,unsigned char * *),_RPC_ASYNC_STATE * &,void * &,int &,int &,int &,int &,int *,int *,int *,unsigned long *,unsigned char * *>(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  wistd::__invoke<void (&)(_RPC_ASYNC_STATE *,void *,int,int,int,int,int *,int *,int *,unsigned long *,unsigned char * *),_RPC_ASYNC_STATE * &,void * &,int &,int &,int &,int &,int *,int *,int *,unsigned long *,unsigned char * *>(
    (unsigned int)MosHostGetDataAsync,
    a2,
    a3,
    a4,
    a5,
    a6,
    a7,
    a8,
    a9,
    a10,
    a11,
    a12);
  return 0;
}

```

## disassembly

```asm
0x180008b88  mov     r11, rsp
0x180008b8b  push    rbx
0x180008b8c  sub     rsp, 60h
0x180008b90  mov     rax, [rsp+68h+arg_58]
0x180008b98  mov     [r11-10h], rax
0x180008b9c  mov     rax, [rsp+68h+arg_50]
0x180008ba4  mov     [r11-18h], rax
0x180008ba8  mov     rax, [rsp+68h+arg_48]
0x180008bb0  mov     [r11-20h], rax
0x180008bb4  mov     rax, [rsp+68h+arg_40]
0x180008bbc  mov     [r11-28h], rax
0x180008bc0  mov     rax, [rsp+68h+arg_38]
0x180008bc8  mov     [r11-30h], rax
0x180008bcc  mov     rax, [rsp+68h+arg_30]
0x180008bd4  mov     [r11-38h], rax
0x180008bd8  mov     rax, [rsp+68h+arg_28]
0x180008be0  mov     [r11-40h], rax
0x180008be4  mov     rax, [rsp+68h+arg_20]
0x180008bec  mov     [r11-48h], rax
0x180008bf0  lea     rcx, MosHostGetDataAsync
0x180008bf7  call    ??$__invoke@A6AXPEAU_RPC_ASYNC_STATE@@PEAXHHHHPEAH22PEAKPEAPEAE@ZAEAPEAU1@AEAPEAXAEAHAEAHAEAHAEAHPEAHPEAHPEAHPEAKPEAPEAE@wistd@@YAXA6AXPEAU_RPC_ASYNC_STATE@@PEAXHHHHPEAH22PEAKPEAPEAE@ZAEAPEAU1@AEAPEAXAEAH888$$QEAPEAH99$$QEAPEAK$$QEAPEAPEAE@Z; wistd::__invoke<void (&)(_RPC_ASYNC_STATE *,void *,int,int,int,int,int *,int *,int *,ulong *,uchar * *),_RPC_ASYNC_STATE * &,void * &,int &,int &,int &,int &,int *,int *,int *,ulong *,uchar * *>(void (&)(_RPC_ASYNC_STATE *,void *,int,int,int,int,int *,int *,int *,ulong *,uchar * *),_RPC_ASYNC_STATE * &,void * &,int &,int &,int &,int &,int * &&,int * &&,int * &&,ulong * &&,uchar * * &&)
0x180008bfc  xor     eax, eax
0x180008bfe  jmp     short loc_180008C30
0x180008c00  mov     ebx, eax
0x180008c02  test    eax, eax
0x180008c04  js      short loc_180008C11
0x180008c06  jle     short loc_180008C11
0x180008c08  movzx   ebx, ax
0x180008c0b  or      ebx, 80070000h
0x180008c11  test    ebx, ebx
0x180008c13  jns     short loc_180008C2E
0x180008c15  mov     rcx, [rsp+68h]; this
0x180008c1a  mov     r9d, ebx; char *
0x180008c1d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008c24  mov     edx, 63h ; 'c'; void *
0x180008c29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c2e  mov     eax, ebx
0x180008c30  add     rsp, 60h
0x180008c34  pop     rbx
0x180008c35  retn
```
