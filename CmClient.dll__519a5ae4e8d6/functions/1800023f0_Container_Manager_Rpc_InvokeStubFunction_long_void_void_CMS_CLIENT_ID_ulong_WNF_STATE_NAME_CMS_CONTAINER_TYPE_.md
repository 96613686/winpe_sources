# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *,_CMS_CLIENT_ID,ulong,_WNF_STATE_NAME *,_CMS_CONTAINER_TYPE *,_GUID *,void * *),void *,void * &,_CMS_CLIENT_ID &,ulong &,_WNF_STATE_NAME *,_CMS_CONTAINER_TYPE *,_GUID *,void * *>(long (*)(void *,void *,_CMS_CLIENT_ID,ulong,_WNF_STATE_NAME *,_CMS_CONTAINER_TYPE *,_GUID *,void * *),void * &&,void * &,_CMS_CLIENT_ID &,ulong &,_WNF_STATE_NAME * &&,_CMS_CONTAINER_TYPE * &&,_GUID * &&,void * * &&)

- ea: `0x1800023f0`
- end: `0x1800024a0`
- name: `??$InvokeStubFunction@P6AJPEAX0W4_CMS_CLIENT_ID@@KPEAU_WNF_STATE_NAME@@PEAW4_CMS_CONTAINER_TYPE@@PEAU_GUID@@PEAPEAX@ZPEAXAEAPEAXAEAW41@AEAKPEAU2@PEAW43@PEAU4@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX0W4_CMS_CLIENT_ID@@KPEAU_WNF_STATE_NAME@@PEAW4_CMS_CONTAINER_TYPE@@PEAU_GUID@@PEAPEAX@Z$$QEAPEAXAEAPEAXAEAW43@AEAK$$QEAPEAU4@$$QEAPEAW45@$$QEAPEAU6@$$QEAPEAPEAX@Z`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009a94`

## callees

- `0x1800023f0`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e48c`

## string_xrefs

- `0x180002460`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002485`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *,enum _CMS_CLIENT_ID,unsigned long,_WNF_STATE_NAME *,enum _CMS_CONTAINER_TYPE *,_GUID *,void * *),void *,void * &,enum _CMS_CLIENT_ID &,unsigned long &,_WNF_STATE_NAME *,enum _CMS_CONTAINER_TYPE *,_GUID *,void * *>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _DWORD *a4,
        _DWORD *a5,
        __int64 *a6,
        __int64 *a7,
        __int64 *a8,
        __int64 *a9)
{
  int v9; // eax
  unsigned int v10; // ebx
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v9 = CmsRpcClt_OpenContainerByMemoryHostingProcess(*a2, *a3, *a4, *a5, *a6, *a7, *a8, *a9);
  v10 = v9;
  if ( v9 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v9,
    v12);
  return v10;
}

```

## disassembly

```asm
0x1800023f0  push    rbx
0x1800023f2  sub     rsp, 40h
0x1800023f6  mov     r10, r9
0x1800023f9  mov     r11, r8
0x1800023fc  mov     rbx, rdx
0x1800023ff  mov     rax, [rsp+48h+arg_40]
0x180002407  mov     rcx, [rax]
0x18000240a  mov     [rsp+48h+var_10], rcx
0x18000240f  mov     rax, [rsp+48h+arg_38]
0x180002417  mov     rcx, [rax]
0x18000241a  mov     [rsp+48h+var_18], rcx
0x18000241f  mov     rax, [rsp+48h+arg_30]
0x180002427  mov     rcx, [rax]
0x18000242a  mov     [rsp+48h+var_20], rcx
0x18000242f  mov     rax, [rsp+48h+arg_28]
0x180002434  mov     rcx, [rax]
0x180002437  mov     qword ptr [rsp+48h+var_28], rcx; int
0x18000243c  mov     r9, [rsp+48h+arg_20]
0x180002441  mov     r9d, [r9]
0x180002444  mov     r8d, [r10]
0x180002447  mov     rdx, [r11]
0x18000244a  mov     rcx, [rbx]
0x18000244d  call    CmsRpcClt_OpenContainerByMemoryHostingProcess
0x180002452  mov     ebx, eax
0x180002454  test    eax, eax
0x180002456  jns     short loc_180002475
0x180002458  mov     rcx, [rsp+48h]; this
0x18000245d  mov     r9d, eax; char *
0x180002460  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002467  mov     edx, 56h ; 'V'; void *
0x18000246c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002471  mov     eax, ebx
0x180002473  jmp     short loc_18000249A
0x180002475  xor     eax, eax
0x180002477  jmp     short loc_18000249A
0x180002479  test    eax, eax
0x18000247b  jz      short loc_180002498
0x18000247d  mov     rcx, [rsp+48h]; this
0x180002482  mov     r9d, eax; char *
0x180002485  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000248c  mov     edx, 5Ch ; '\'; void *
0x180002491  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002496  jmp     short loc_18000249A
0x180002498  xor     eax, eax
0x18000249a  add     rsp, 40h
0x18000249e  pop     rbx
0x18000249f  retn
```
