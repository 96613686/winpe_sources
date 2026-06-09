# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_PROCESS_PROPERTIES *,_CMS_PROCESS_CREATION_FLAGS,_WNF_STATE_NAME *,void * *,void * *,void * *,ulong *,void * *),void *,_CMS_PROCESS_PROPERTIES * &,_CMS_PROCESS_CREATION_FLAGS &,_WNF_STATE_NAME *,void * *,void * *,void * *,ulong *,void * *>(long (*)(void *,_CMS_PROCESS_PROPERTIES *,_CMS_PROCESS_CREATION_FLAGS,_WNF_STATE_NAME *,void * *,void * *,void * *,ulong *,void * *),void * &&,_CMS_PROCESS_PROPERTIES * &,_CMS_PROCESS_CREATION_FLAGS &,_WNF_STATE_NAME * &&,void * * &&,void * * &&,void * * &&,ulong * &&,void * * &&)

- ea: `0x180002748`
- end: `0x18000280e`
- name: `??$InvokeStubFunction@P6AJPEAXPEAU_CMS_PROCESS_PROPERTIES@@W4_CMS_PROCESS_CREATION_FLAGS@@PEAU_WNF_STATE_NAME@@PEAPEAX44PEAK4@ZPEAXAEAPEAU1@AEAW42@PEAU3@PEAPEAXPEAPEAXPEAPEAXPEAKPEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_CMS_PROCESS_PROPERTIES@@W4_CMS_PROCESS_CREATION_FLAGS@@PEAU_WNF_STATE_NAME@@PEAPEAX44PEAK4@Z$$QEAPEAXAEAPEAU3@AEAW44@$$QEAPEAU5@$$QEAPEAPEAX$$QEAPEAPEAX$$QEAPEAPEAX$$QEAPEAK$$QEAPEAPEAX@Z`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800079d0`

## callees

- `0x180002748`
- `0x1800066e4`
- `0x18000672c`
- `0x18000df74`

## string_xrefs

- `0x1800027ce`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1800027f3`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_PROCESS_PROPERTIES *,enum _CMS_PROCESS_CREATION_FLAGS,_WNF_STATE_NAME *,void * *,void * *,void * *,unsigned long *,void * *),void *,_CMS_PROCESS_PROPERTIES * &,enum _CMS_PROCESS_CREATION_FLAGS &,_WNF_STATE_NAME *,void * *,void * *,void * *,unsigned long *,void * *>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _DWORD *a4,
        _QWORD *a5,
        __int64 *a6,
        __int64 *a7,
        __int64 *a8,
        __int64 *a9,
        __int64 *a10)
{
  int ProcessInContainer; // eax
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  ProcessInContainer = CmsRpcClt_CreateProcessInContainer(*a2, *a3, *a4, *a5, *a6, *a7, *a8, *a9, *a10);
  v11 = ProcessInContainer;
  if ( ProcessInContainer >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)ProcessInContainer,
    v13);
  return v11;
}

```

## disassembly

```asm
0x180002748  push    rbx
0x18000274a  sub     rsp, 50h
0x18000274e  mov     r10, r9
0x180002751  mov     r11, r8
0x180002754  mov     rbx, rdx
0x180002757  mov     rax, [rsp+58h+arg_48]
0x18000275f  mov     rcx, [rax]
0x180002762  mov     [rsp+58h+var_18], rcx
0x180002767  mov     rax, [rsp+58h+arg_40]
0x18000276f  mov     rcx, [rax]
0x180002772  mov     [rsp+58h+var_20], rcx
0x180002777  mov     rax, [rsp+58h+arg_38]
0x18000277f  mov     rcx, [rax]
0x180002782  mov     [rsp+58h+var_28], rcx
0x180002787  mov     rax, [rsp+58h+arg_30]
0x18000278f  mov     rcx, [rax]
0x180002792  mov     [rsp+58h+var_30], rcx
0x180002797  mov     rax, [rsp+58h+arg_28]
0x18000279f  mov     rcx, [rax]
0x1800027a2  mov     qword ptr [rsp+58h+var_38], rcx; int
0x1800027a7  mov     r9, [rsp+58h+arg_20]
0x1800027af  mov     r9, [r9]
0x1800027b2  mov     r8d, [r10]
0x1800027b5  mov     rdx, [r11]
0x1800027b8  mov     rcx, [rbx]
0x1800027bb  call    CmsRpcClt_CreateProcessInContainer
0x1800027c0  mov     ebx, eax
0x1800027c2  test    eax, eax
0x1800027c4  jns     short loc_1800027E3
0x1800027c6  mov     rcx, [rsp+58h]; this
0x1800027cb  mov     r9d, eax; char *
0x1800027ce  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1800027d5  mov     edx, 56h ; 'V'; void *
0x1800027da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800027df  mov     eax, ebx
0x1800027e1  jmp     short loc_180002808
0x1800027e3  xor     eax, eax
0x1800027e5  jmp     short loc_180002808
0x1800027e7  test    eax, eax
0x1800027e9  jz      short loc_180002806
0x1800027eb  mov     rcx, [rsp+58h]; this
0x1800027f0  mov     r9d, eax; char *
0x1800027f3  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1800027fa  mov     edx, 5Ch ; '\'; void *
0x1800027ff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002804  jmp     short loc_180002808
0x180002806  xor     eax, eax
0x180002808  add     rsp, 50h
0x18000280c  pop     rbx
0x18000280d  retn
```
