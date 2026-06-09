# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,_CMS_CLIENT_ID,ulong,_WNF_STATE_NAME *,_CMS_CONTAINER_TYPE *,void * *),void *,_GUID * &,_CMS_CLIENT_ID &,ulong &,_WNF_STATE_NAME *,_CMS_CONTAINER_TYPE *,void * *>(long (*)(void *,_GUID *,_CMS_CLIENT_ID,ulong,_WNF_STATE_NAME *,_CMS_CONTAINER_TYPE *,void * *),void * &&,_GUID * &,_CMS_CLIENT_ID &,ulong &,_WNF_STATE_NAME * &&,_CMS_CONTAINER_TYPE * &&,void * * &&)

- ea: `0x180002970`
- end: `0x180002a10`
- name: `??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@KPEAU_WNF_STATE_NAME@@PEAW4_CMS_CONTAINER_TYPE@@PEAPEAX@ZPEAXAEAPEAU1@AEAW42@AEAKPEAU3@PEAW44@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@KPEAU_WNF_STATE_NAME@@PEAW4_CMS_CONTAINER_TYPE@@PEAPEAX@Z$$QEAPEAXAEAPEAU3@AEAW44@AEAK$$QEAPEAU5@$$QEAPEAW46@$$QEAPEAPEAX@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009a94`

## callees

- `0x180002970`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e430`

## string_xrefs

- `0x1800029d0`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1800029f5`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,enum _CMS_CLIENT_ID,unsigned long,_WNF_STATE_NAME *,enum _CMS_CONTAINER_TYPE *,void * *),void *,_GUID * &,enum _CMS_CLIENT_ID &,unsigned long &,_WNF_STATE_NAME *,enum _CMS_CONTAINER_TYPE *,void * *>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _DWORD *a4,
        _DWORD *a5,
        __int64 *a6,
        __int64 *a7,
        __int64 *a8)
{
  int v8; // eax
  unsigned int v9; // ebx
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v8 = CmsRpcClt_OpenContainer(*a2, *a3, *a4, *a5, *a6, *a7, *a8);
  v9 = v8;
  if ( v8 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v8,
    v11);
  return v9;
}

```

## disassembly

```asm
0x180002970  push    rbx
0x180002972  sub     rsp, 40h
0x180002976  mov     r10, r9
0x180002979  mov     r11, r8
0x18000297c  mov     rbx, rdx
0x18000297f  mov     rax, [rsp+48h+arg_38]
0x180002987  mov     rcx, [rax]
0x18000298a  mov     [rsp+48h+var_18], rcx
0x18000298f  mov     rax, [rsp+48h+arg_30]
0x180002997  mov     rcx, [rax]
0x18000299a  mov     [rsp+48h+var_20], rcx
0x18000299f  mov     rax, [rsp+48h+arg_28]
0x1800029a4  mov     rcx, [rax]
0x1800029a7  mov     qword ptr [rsp+48h+var_28], rcx; int
0x1800029ac  mov     r9, [rsp+48h+arg_20]
0x1800029b1  mov     r9d, [r9]
0x1800029b4  mov     r8d, [r10]
0x1800029b7  mov     rdx, [r11]
0x1800029ba  mov     rcx, [rbx]
0x1800029bd  call    CmsRpcClt_OpenContainer
0x1800029c2  mov     ebx, eax
0x1800029c4  test    eax, eax
0x1800029c6  jns     short loc_1800029E5
0x1800029c8  mov     rcx, [rsp+48h]; this
0x1800029cd  mov     r9d, eax; char *
0x1800029d0  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1800029d7  mov     edx, 56h ; 'V'; void *
0x1800029dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800029e1  mov     eax, ebx
0x1800029e3  jmp     short loc_180002A0A
0x1800029e5  xor     eax, eax
0x1800029e7  jmp     short loc_180002A0A
0x1800029e9  test    eax, eax
0x1800029eb  jz      short loc_180002A08
0x1800029ed  mov     rcx, [rsp+48h]; this
0x1800029f2  mov     r9d, eax; char *
0x1800029f5  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1800029fc  mov     edx, 5Ch ; '\'; void *
0x180002a01  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002a06  jmp     short loc_180002A0A
0x180002a08  xor     eax, eax
0x180002a0a  add     rsp, 40h
0x180002a0e  pop     rbx
0x180002a0f  retn
```
