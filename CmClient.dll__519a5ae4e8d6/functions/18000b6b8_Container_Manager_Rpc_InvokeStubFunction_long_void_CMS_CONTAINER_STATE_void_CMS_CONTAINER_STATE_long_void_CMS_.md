# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CONTAINER_STATE *),void *,_CMS_CONTAINER_STATE * &>(long (*)(void *,_CMS_CONTAINER_STATE *),void * &&,_CMS_CONTAINER_STATE * &)

- ea: `0x18000b6b8`
- end: `0x18000b71a`
- name: `??$InvokeStubFunction@P6AJPEAXPEAW4_CMS_CONTAINER_STATE@@@ZPEAXAEAPEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXPEAW4_CMS_CONTAINER_STATE@@@Z$$QEAPEAXAEAPEAW43@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bd90`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000b6b8`
- `0x18000e1f0`

## string_xrefs

- `0x18000b6da`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000b6ff`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CONTAINER_STATE *),void *,enum _CMS_CONTAINER_STATE * &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  int ContainerState; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  ContainerState = CmsRpcClt_GetContainerState(*a2, *a3);
  v4 = ContainerState;
  if ( ContainerState >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)ContainerState,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000b6b8  push    rbx; int
0x18000b6ba  sub     rsp, 20h
0x18000b6be  mov     rax, rdx
0x18000b6c1  mov     rdx, [r8]
0x18000b6c4  mov     rcx, [rax]
0x18000b6c7  call    CmsRpcClt_GetContainerState
0x18000b6cc  mov     ebx, eax
0x18000b6ce  test    eax, eax
0x18000b6d0  jns     short loc_18000B6EF
0x18000b6d2  mov     rcx, [rsp+28h]; this
0x18000b6d7  mov     r9d, eax; char *
0x18000b6da  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b6e1  mov     edx, 56h ; 'V'; void *
0x18000b6e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b6eb  mov     eax, ebx
0x18000b6ed  jmp     short loc_18000B714
0x18000b6ef  xor     eax, eax
0x18000b6f1  jmp     short loc_18000B714
0x18000b6f3  test    eax, eax
0x18000b6f5  jz      short loc_18000B712
0x18000b6f7  mov     rcx, [rsp+28h]; this
0x18000b6fc  mov     r9d, eax; char *
0x18000b6ff  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b706  mov     edx, 5Ch ; '\'; void *
0x18000b70b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b710  jmp     short loc_18000B714
0x18000b712  xor     eax, eax
0x18000b714  add     rsp, 20h
0x18000b718  pop     rbx
0x18000b719  retn
```
