# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CONTAINER_DEBUG_FLAGS *),void *,_CMS_CONTAINER_DEBUG_FLAGS * &>(long (*)(void *,_CMS_CONTAINER_DEBUG_FLAGS *),void * &&,_CMS_CONTAINER_DEBUG_FLAGS * &)

- ea: `0x18000b650`
- end: `0x18000b6b2`
- name: `??$InvokeStubFunction@P6AJPEAXPEAW4_CMS_CONTAINER_DEBUG_FLAGS@@@ZPEAXAEAPEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXPEAW4_CMS_CONTAINER_DEBUG_FLAGS@@@Z$$QEAPEAXAEAPEAW43@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bcd0`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000b650`
- `0x18000e130`

## string_xrefs

- `0x18000b672`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000b697`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CONTAINER_DEBUG_FLAGS *),void *,enum _CMS_CONTAINER_DEBUG_FLAGS * &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  int ContainerDebugFlags; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  ContainerDebugFlags = CmsRpcClt_GetContainerDebugFlags(*a2, *a3);
  v4 = ContainerDebugFlags;
  if ( ContainerDebugFlags >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)ContainerDebugFlags,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000b650  push    rbx; int
0x18000b652  sub     rsp, 20h
0x18000b656  mov     rax, rdx
0x18000b659  mov     rdx, [r8]
0x18000b65c  mov     rcx, [rax]
0x18000b65f  call    CmsRpcClt_GetContainerDebugFlags
0x18000b664  mov     ebx, eax
0x18000b666  test    eax, eax
0x18000b668  jns     short loc_18000B687
0x18000b66a  mov     rcx, [rsp+28h]; this
0x18000b66f  mov     r9d, eax; char *
0x18000b672  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b679  mov     edx, 56h ; 'V'; void *
0x18000b67e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b683  mov     eax, ebx
0x18000b685  jmp     short loc_18000B6AC
0x18000b687  xor     eax, eax
0x18000b689  jmp     short loc_18000B6AC
0x18000b68b  test    eax, eax
0x18000b68d  jz      short loc_18000B6AA
0x18000b68f  mov     rcx, [rsp+28h]; this
0x18000b694  mov     r9d, eax; char *
0x18000b697  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b69e  mov     edx, 5Ch ; '\'; void *
0x18000b6a3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b6a8  jmp     short loc_18000B6AC
0x18000b6aa  xor     eax, eax
0x18000b6ac  add     rsp, 20h
0x18000b6b0  pop     rbx
0x18000b6b1  retn
```
