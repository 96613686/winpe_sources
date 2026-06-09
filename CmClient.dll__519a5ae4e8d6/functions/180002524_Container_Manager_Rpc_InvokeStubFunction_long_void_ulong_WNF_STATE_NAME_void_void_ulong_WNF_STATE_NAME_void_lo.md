# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,ulong,_WNF_STATE_NAME *,void * *),void *,ulong &,_WNF_STATE_NAME *,void * *>(long (*)(void *,ulong,_WNF_STATE_NAME *,void * *),void * &&,ulong &,_WNF_STATE_NAME * &&,void * * &&)

- ea: `0x180002524`
- end: `0x180002597`
- name: `??$InvokeStubFunction@P6AJPEAXKPEAU_WNF_STATE_NAME@@PEAPEAX@ZPEAXAEAKPEAU1@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXKPEAU_WNF_STATE_NAME@@PEAPEAX@Z$$QEAPEAXAEAK$$QEAPEAU3@$$QEAPEAPEAX@Z`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008a90`

## callees

- `0x180002524`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e594`

## string_xrefs

- `0x180002557`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000257c`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,unsigned long,_WNF_STATE_NAME *,void * *),void *,unsigned long &,_WNF_STATE_NAME *,void * *>(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v5 = CmsRpcClt_OpenProcessInContainer(*a2, *a3, *a4, *a5);
  v6 = v5;
  if ( v5 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v5,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180002524  push    rbx; int
0x180002526  sub     rsp, 20h
0x18000252a  mov     rax, r9
0x18000252d  mov     r10, r8
0x180002530  mov     r11, rdx
0x180002533  mov     r9, [rsp+28h+arg_20]
0x180002538  mov     r9, [r9]
0x18000253b  mov     r8, [rax]
0x18000253e  mov     edx, [r10]
0x180002541  mov     rcx, [r11]
0x180002544  call    CmsRpcClt_OpenProcessInContainer
0x180002549  mov     ebx, eax
0x18000254b  test    eax, eax
0x18000254d  jns     short loc_18000256C
0x18000254f  mov     rcx, [rsp+28h]; this
0x180002554  mov     r9d, eax; char *
0x180002557  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000255e  mov     edx, 56h ; 'V'; void *
0x180002563  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002568  mov     eax, ebx
0x18000256a  jmp     short loc_180002591
0x18000256c  xor     eax, eax
0x18000256e  jmp     short loc_180002591
0x180002570  test    eax, eax
0x180002572  jz      short loc_18000258F
0x180002574  mov     rcx, [rsp+28h]; this
0x180002579  mov     r9d, eax; char *
0x18000257c  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002583  mov     edx, 5Ch ; '\'; void *
0x180002588  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000258d  jmp     short loc_180002591
0x18000258f  xor     eax, eax
0x180002591  add     rsp, 20h
0x180002595  pop     rbx
0x180002596  retn
```
