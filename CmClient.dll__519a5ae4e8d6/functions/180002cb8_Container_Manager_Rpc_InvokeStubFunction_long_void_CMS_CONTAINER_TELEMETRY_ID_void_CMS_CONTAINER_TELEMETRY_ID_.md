# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CONTAINER_TELEMETRY_ID *),void *,_CMS_CONTAINER_TELEMETRY_ID * &>(long (*)(void *,_CMS_CONTAINER_TELEMETRY_ID *),void * &&,_CMS_CONTAINER_TELEMETRY_ID * &)

- ea: `0x180002cb8`
- end: `0x180002d1a`
- name: `??$InvokeStubFunction@P6AJPEAXPEAW4_CMS_CONTAINER_TELEMETRY_ID@@@ZPEAXAEAPEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXPEAW4_CMS_CONTAINER_TELEMETRY_ID@@@Z$$QEAPEAXAEAPEAW43@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008150`

## callees

- `0x180002cb8`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e21c`

## string_xrefs

- `0x180002cda`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002cff`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CONTAINER_TELEMETRY_ID *),void *,enum _CMS_CONTAINER_TELEMETRY_ID * &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  int ContainerTelemetryId; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  ContainerTelemetryId = CmsRpcClt_GetContainerTelemetryId(*a2, *a3);
  v4 = ContainerTelemetryId;
  if ( ContainerTelemetryId >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)ContainerTelemetryId,
    v6);
  return v4;
}

```

## disassembly

```asm
0x180002cb8  push    rbx; int
0x180002cba  sub     rsp, 20h
0x180002cbe  mov     rax, rdx
0x180002cc1  mov     rdx, [r8]
0x180002cc4  mov     rcx, [rax]
0x180002cc7  call    CmsRpcClt_GetContainerTelemetryId
0x180002ccc  mov     ebx, eax
0x180002cce  test    eax, eax
0x180002cd0  jns     short loc_180002CEF
0x180002cd2  mov     rcx, [rsp+28h]; this
0x180002cd7  mov     r9d, eax; char *
0x180002cda  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002ce1  mov     edx, 56h ; 'V'; void *
0x180002ce6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002ceb  mov     eax, ebx
0x180002ced  jmp     short loc_180002D14
0x180002cef  xor     eax, eax
0x180002cf1  jmp     short loc_180002D14
0x180002cf3  test    eax, eax
0x180002cf5  jz      short loc_180002D12
0x180002cf7  mov     rcx, [rsp+28h]; this
0x180002cfc  mov     r9d, eax; char *
0x180002cff  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002d06  mov     edx, 5Ch ; '\'; void *
0x180002d0b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002d10  jmp     short loc_180002D14
0x180002d12  xor     eax, eax
0x180002d14  add     rsp, 20h
0x180002d18  pop     rbx
0x180002d19  retn
```
