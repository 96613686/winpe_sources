# CmsRemoveHostNetworkFromContainer

- ea: `0x180009480`
- end: `0x1800094d3`
- name: `CmsRemoveHostNetworkFromContainer`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x180009480`

## string_xrefs

- `0x1800094b3`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsRemoveHostNetworkFromContainer(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 8);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
         (__int64 (__fastcall *)(_QWORD, _QWORD))CmsRpcClt_RemoveHostNetworkFromContainer,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x45C,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x180009480  mov     r11, rsp
0x180009483  mov     [r11+10h], rdx
0x180009487  push    rbx; int
0x180009488  sub     rsp, 20h
0x18000948c  mov     rax, [rcx+8]
0x180009490  lea     r8, [r11+10h]
0x180009494  lea     rcx, CmsRpcClt_RemoveHostNetworkFromContainer
0x18000949b  mov     [r11+8], rax
0x18000949f  lea     rdx, [r11+8]
0x1800094a3  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x1800094a8  mov     ebx, eax
0x1800094aa  test    eax, eax
0x1800094ac  jns     short loc_1800094CB
0x1800094ae  mov     rcx, [rsp+28h]; this
0x1800094b3  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800094ba  mov     r9d, eax; char *
0x1800094bd  mov     edx, 45Ch; void *
0x1800094c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094c7  mov     eax, ebx
0x1800094c9  jmp     short loc_1800094CD
0x1800094cb  xor     eax, eax
0x1800094cd  add     rsp, 20h
0x1800094d1  pop     rbx
0x1800094d2  retn
```
