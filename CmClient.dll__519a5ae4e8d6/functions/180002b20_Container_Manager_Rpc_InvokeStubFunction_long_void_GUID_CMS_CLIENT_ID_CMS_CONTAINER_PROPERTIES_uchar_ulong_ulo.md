# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,_CMS_CLIENT_ID,_CMS_CONTAINER_PROPERTIES *,uchar *,ulong,ulong,_WNF_STATE_NAME *,void * *),void *,_GUID * &,_CMS_CLIENT_ID &,_CMS_CONTAINER_PROPERTIES * &,uchar *,ulong &,ulong &,_WNF_STATE_NAME *,void * *>(long (*)(void *,_GUID *,_CMS_CLIENT_ID,_CMS_CONTAINER_PROPERTIES *,uchar *,ulong,ulong,_WNF_STATE_NAME *,void * *),void * &&,_GUID * &,_CMS_CLIENT_ID &,_CMS_CONTAINER_PROPERTIES * &,uchar * &&,ulong &,ulong &,_WNF_STATE_NAME * &&,void * * &&)

- ea: `0x180002b20`
- end: `0x180002be2`
- name: `??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAU_CMS_CONTAINER_PROPERTIES@@PEAEKKPEAU_WNF_STATE_NAME@@PEAPEAX@ZPEAXAEAPEAU1@AEAW42@AEAPEAU3@PEAEAEAKAEAKPEAU4@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAU_CMS_CONTAINER_PROPERTIES@@PEAEKKPEAU_WNF_STATE_NAME@@PEAPEAX@Z$$QEAPEAXAEAPEAU3@AEAW44@AEAPEAU5@$$QEAPEAEAEAKAEAK$$QEAPEAU6@$$QEAPEAPEAX@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007610`

## callees

- `0x180002b20`
- `0x1800066e4`
- `0x18000672c`
- `0x18000de44`

## string_xrefs

- `0x180002ba2`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002bc7`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,enum _CMS_CLIENT_ID,_CMS_CONTAINER_PROPERTIES *,unsigned char *,unsigned long,unsigned long,_WNF_STATE_NAME *,void * *),void *,_GUID * &,enum _CMS_CLIENT_ID &,_CMS_CONTAINER_PROPERTIES * &,unsigned char *,unsigned long &,unsigned long &,_WNF_STATE_NAME *,void * *>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _DWORD *a4,
        _QWORD *a5,
        __int64 *a6,
        _DWORD *a7,
        _DWORD *a8,
        __int64 *a9,
        __int64 *a10)
{
  int Container; // eax
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Container = CmsRpcClt_CreateContainer(*a2, *a3, *a4, *a5, *a6, *a7, *a8, *a9, *a10);
  v11 = Container;
  if ( Container >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)Container,
    v13);
  return v11;
}

```

## disassembly

```asm
0x180002b20  push    rbx
0x180002b22  sub     rsp, 50h
0x180002b26  mov     r10, r9
0x180002b29  mov     r11, r8
0x180002b2c  mov     rbx, rdx
0x180002b2f  mov     rax, [rsp+58h+arg_48]
0x180002b37  mov     rcx, [rax]
0x180002b3a  mov     [rsp+58h+var_18], rcx
0x180002b3f  mov     rax, [rsp+58h+arg_40]
0x180002b47  mov     rcx, [rax]
0x180002b4a  mov     [rsp+58h+var_20], rcx
0x180002b4f  mov     rax, [rsp+58h+arg_38]
0x180002b57  mov     ecx, [rax]
0x180002b59  mov     [rsp+58h+var_28], ecx
0x180002b5d  mov     rax, [rsp+58h+arg_30]
0x180002b65  mov     ecx, [rax]
0x180002b67  mov     [rsp+58h+var_30], ecx
0x180002b6b  mov     rax, [rsp+58h+arg_28]
0x180002b73  mov     rcx, [rax]
0x180002b76  mov     qword ptr [rsp+58h+var_38], rcx; int
0x180002b7b  mov     r9, [rsp+58h+arg_20]
0x180002b83  mov     r9, [r9]
0x180002b86  mov     r8d, [r10]
0x180002b89  mov     rdx, [r11]
0x180002b8c  mov     rcx, [rbx]
0x180002b8f  call    CmsRpcClt_CreateContainer
0x180002b94  mov     ebx, eax
0x180002b96  test    eax, eax
0x180002b98  jns     short loc_180002BB7
0x180002b9a  mov     rcx, [rsp+58h]; this
0x180002b9f  mov     r9d, eax; char *
0x180002ba2  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002ba9  mov     edx, 56h ; 'V'; void *
0x180002bae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002bb3  mov     eax, ebx
0x180002bb5  jmp     short loc_180002BDC
0x180002bb7  xor     eax, eax
0x180002bb9  jmp     short loc_180002BDC
0x180002bbb  test    eax, eax
0x180002bbd  jz      short loc_180002BDA
0x180002bbf  mov     rcx, [rsp+58h]; this
0x180002bc4  mov     r9d, eax; char *
0x180002bc7  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002bce  mov     edx, 5Ch ; '\'; void *
0x180002bd3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002bd8  jmp     short loc_180002BDC
0x180002bda  xor     eax, eax
0x180002bdc  add     rsp, 50h
0x180002be0  pop     rbx
0x180002be1  retn
```
