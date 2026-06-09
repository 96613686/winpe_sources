# CmsInternalContainerSimulateUnresponsive

- ea: `0x18000bac0`
- end: `0x18000bb0c`
- name: `CmsInternalContainerSimulateUnresponsive`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000b494`
- `0x18000bac0`

## string_xrefs

- `0x18000baec`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalContainerSimulateUnresponsive(__int64 a1, unsigned int a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 24);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int),void *,int &>(a1, &v7, &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x123,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000bac0  mov     [rsp+arg_8], edx
0x18000bac4  push    rbx; int
0x18000bac5  sub     rsp, 20h
0x18000bac9  mov     rax, [rcx+18h]
0x18000bacd  lea     r8, [rsp+28h+arg_8]
0x18000bad2  lea     rdx, [rsp+28h+arg_0]
0x18000bad7  mov     [rsp+28h+arg_0], rax
0x18000badc  call    ??$InvokeStubFunction@P6AJPEAXH@ZPEAXAEAH@Rpc@Manager@Container@@YAJP6AJPEAXH@Z$$QEAPEAXAEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int),void *,int &>(long (*)(void *,int),void * &&,int &)
0x18000bae1  mov     ebx, eax
0x18000bae3  test    eax, eax
0x18000bae5  jns     short loc_18000BB04
0x18000bae7  mov     rcx, [rsp+28h]; this
0x18000baec  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000baf3  mov     r9d, eax; char *
0x18000baf6  mov     edx, 123h; void *
0x18000bafb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bb00  mov     eax, ebx
0x18000bb02  jmp     short loc_18000BB06
0x18000bb04  xor     eax, eax
0x18000bb06  add     rsp, 20h
0x18000bb0a  pop     rbx
0x18000bb0b  retn
```
