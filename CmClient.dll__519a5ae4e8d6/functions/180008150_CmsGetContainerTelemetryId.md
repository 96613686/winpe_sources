# CmsGetContainerTelemetryId

- ea: `0x180008150`
- end: `0x18000819c`
- name: `CmsGetContainerTelemetryId`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180002cb8`
- `0x1800066e4`
- `0x180008150`

## string_xrefs

- `0x18000817c`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsGetContainerTelemetryId(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 24);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CONTAINER_TELEMETRY_ID *),void *,enum _CMS_CONTAINER_TELEMETRY_ID * &>(
         a1,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x202,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x180008150  mov     r11, rsp
0x180008153  mov     [r11+10h], rdx
0x180008157  push    rbx; int
0x180008158  sub     rsp, 20h
0x18000815c  mov     rax, [rcx+18h]
0x180008160  lea     r8, [r11+10h]
0x180008164  lea     rdx, [r11+8]
0x180008168  mov     [r11+8], rax
0x18000816c  call    ??$InvokeStubFunction@P6AJPEAXPEAW4_CMS_CONTAINER_TELEMETRY_ID@@@ZPEAXAEAPEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXPEAW4_CMS_CONTAINER_TELEMETRY_ID@@@Z$$QEAPEAXAEAPEAW43@@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CONTAINER_TELEMETRY_ID *),void *,_CMS_CONTAINER_TELEMETRY_ID * &>(long (*)(void *,_CMS_CONTAINER_TELEMETRY_ID *),void * &&,_CMS_CONTAINER_TELEMETRY_ID * &)
0x180008171  mov     ebx, eax
0x180008173  test    eax, eax
0x180008175  jns     short loc_180008194
0x180008177  mov     rcx, [rsp+28h]; this
0x18000817c  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008183  mov     r9d, eax; char *
0x180008186  mov     edx, 202h; void *
0x18000818b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008190  mov     eax, ebx
0x180008192  jmp     short loc_180008196
0x180008194  xor     eax, eax
0x180008196  add     rsp, 20h
0x18000819a  pop     rbx
0x18000819b  retn
```
