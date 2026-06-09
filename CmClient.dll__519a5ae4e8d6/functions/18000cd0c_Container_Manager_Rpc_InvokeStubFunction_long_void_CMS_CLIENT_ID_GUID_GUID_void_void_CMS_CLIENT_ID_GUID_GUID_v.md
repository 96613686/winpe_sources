# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CLIENT_ID,_GUID *,_GUID *,void * *),void * &,_CMS_CLIENT_ID &,_GUID * &,_GUID *,void * *>(long (*)(void *,_CMS_CLIENT_ID,_GUID *,_GUID *,void * *),void * &,_CMS_CLIENT_ID &,_GUID * &,_GUID * &&,void * * &&)

- ea: `0x18000cd0c`
- end: `0x18000cd8c`
- name: `??$InvokeStubFunction@P6AJPEAXW4_CMS_CLIENT_ID@@PEAU_GUID@@2PEAPEAX@ZAEAPEAXAEAW41@AEAPEAU2@PEAU2@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_CLIENT_ID@@PEAU_GUID@@2PEAPEAX@ZAEAPEAXAEAW43@AEAPEAU4@$$QEAPEAU4@$$QEAPEAPEAX@Z`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d260`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000cd0c`
- `0x18000e028`

## string_xrefs

- `0x18000cd4c`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000cd71`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CLIENT_ID,_GUID *,_GUID *,void * *),void * &,enum _CMS_CLIENT_ID &,_GUID * &,_GUID *,void * *>(
        __int64 a1,
        _QWORD *a2,
        _DWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 *a6)
{
  int StorageTransacted; // eax
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  StorageTransacted = CmsRpcClt_CreateStorageTransacted(*a2, *a3, *a4, *a5, *a6);
  v7 = StorageTransacted;
  if ( StorageTransacted >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)StorageTransacted,
    v9);
  return v7;
}

```

## disassembly

```asm
0x18000cd0c  push    rbx
0x18000cd0e  sub     rsp, 30h
0x18000cd12  mov     r10, r9
0x18000cd15  mov     r11, r8
0x18000cd18  mov     rbx, rdx
0x18000cd1b  mov     rax, [rsp+38h+arg_28]
0x18000cd20  mov     rcx, [rax]
0x18000cd23  mov     qword ptr [rsp+38h+var_18], rcx; int
0x18000cd28  mov     r9, [rsp+38h+arg_20]
0x18000cd2d  mov     r9, [r9]
0x18000cd30  mov     r8, [r10]
0x18000cd33  mov     edx, [r11]
0x18000cd36  mov     rcx, [rbx]
0x18000cd39  call    CmsRpcClt_CreateStorageTransacted
0x18000cd3e  mov     ebx, eax
0x18000cd40  test    eax, eax
0x18000cd42  jns     short loc_18000CD61
0x18000cd44  mov     rcx, [rsp+38h]; this
0x18000cd49  mov     r9d, eax; char *
0x18000cd4c  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000cd53  mov     edx, 56h ; 'V'; void *
0x18000cd58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd5d  mov     eax, ebx
0x18000cd5f  jmp     short loc_18000CD86
0x18000cd61  xor     eax, eax
0x18000cd63  jmp     short loc_18000CD86
0x18000cd65  test    eax, eax
0x18000cd67  jz      short loc_18000CD84
0x18000cd69  mov     rcx, [rsp+38h]; this
0x18000cd6e  mov     r9d, eax; char *
0x18000cd71  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000cd78  mov     edx, 5Ch ; '\'; void *
0x18000cd7d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000cd82  jmp     short loc_18000CD86
0x18000cd84  xor     eax, eax
0x18000cd86  add     rsp, 30h
0x18000cd8a  pop     rbx
0x18000cd8b  retn
```
