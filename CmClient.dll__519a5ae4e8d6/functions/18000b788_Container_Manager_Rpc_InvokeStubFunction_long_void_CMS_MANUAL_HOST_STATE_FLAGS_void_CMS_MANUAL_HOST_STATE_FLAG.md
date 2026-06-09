# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_MANUAL_HOST_STATE_FLAGS *),void *,_CMS_MANUAL_HOST_STATE_FLAGS * &>(long (*)(void *,_CMS_MANUAL_HOST_STATE_FLAGS *),void * &&,_CMS_MANUAL_HOST_STATE_FLAGS * &)

- ea: `0x18000b788`
- end: `0x18000b7ea`
- name: `??$InvokeStubFunction@P6AJPEAXPEAW4_CMS_MANUAL_HOST_STATE_FLAGS@@@ZPEAXAEAPEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXPEAW4_CMS_MANUAL_HOST_STATE_FLAGS@@@Z$$QEAPEAXAEAPEAW43@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c080`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000b788`
- `0x18000ebb0`

## string_xrefs

- `0x18000b7aa`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000b7cf`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_MANUAL_HOST_STATE_FLAGS *),void *,enum _CMS_MANUAL_HOST_STATE_FLAGS * &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  int ManualHostStateFlags; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  ManualHostStateFlags = CmsRpcClt_GetManualHostStateFlags(*a2, *a3);
  v4 = ManualHostStateFlags;
  if ( ManualHostStateFlags >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)ManualHostStateFlags,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000b788  push    rbx; int
0x18000b78a  sub     rsp, 20h
0x18000b78e  mov     rax, rdx
0x18000b791  mov     rdx, [r8]
0x18000b794  mov     rcx, [rax]
0x18000b797  call    CmsRpcClt_GetManualHostStateFlags
0x18000b79c  mov     ebx, eax
0x18000b79e  test    eax, eax
0x18000b7a0  jns     short loc_18000B7BF
0x18000b7a2  mov     rcx, [rsp+28h]; this
0x18000b7a7  mov     r9d, eax; char *
0x18000b7aa  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b7b1  mov     edx, 56h ; 'V'; void *
0x18000b7b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b7bb  mov     eax, ebx
0x18000b7bd  jmp     short loc_18000B7E4
0x18000b7bf  xor     eax, eax
0x18000b7c1  jmp     short loc_18000B7E4
0x18000b7c3  test    eax, eax
0x18000b7c5  jz      short loc_18000B7E2
0x18000b7c7  mov     rcx, [rsp+28h]; this
0x18000b7cc  mov     r9d, eax; char *
0x18000b7cf  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b7d6  mov     edx, 5Ch ; '\'; void *
0x18000b7db  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b7e0  jmp     short loc_18000B7E4
0x18000b7e2  xor     eax, eax
0x18000b7e4  add     rsp, 20h
0x18000b7e8  pop     rbx
0x18000b7e9  retn
```
