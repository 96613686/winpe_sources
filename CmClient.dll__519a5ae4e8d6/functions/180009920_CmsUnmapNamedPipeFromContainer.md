# CmsUnmapNamedPipeFromContainer

- ea: `0x180009920`
- end: `0x180009973`
- name: `CmsUnmapNamedPipeFromContainer`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x180009920`

## string_xrefs

- `0x180009953`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsUnmapNamedPipeFromContainer(__int64 a1, __int64 a2)
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
         (__int64 (__fastcall *)(_QWORD, _QWORD))CmsRpcClt_UnmapNamedPipeFromContainer,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4D7,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x180009920  mov     r11, rsp
0x180009923  mov     [r11+10h], rdx
0x180009927  push    rbx; int
0x180009928  sub     rsp, 20h
0x18000992c  mov     rax, [rcx+8]
0x180009930  lea     r8, [r11+10h]
0x180009934  lea     rcx, CmsRpcClt_UnmapNamedPipeFromContainer
0x18000993b  mov     [r11+8], rax
0x18000993f  lea     rdx, [r11+8]
0x180009943  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x180009948  mov     ebx, eax
0x18000994a  test    eax, eax
0x18000994c  jns     short loc_18000996B
0x18000994e  mov     rcx, [rsp+28h]; this
0x180009953  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000995a  mov     r9d, eax; char *
0x18000995d  mov     edx, 4D7h; void *
0x180009962  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009967  mov     eax, ebx
0x180009969  jmp     short loc_18000996D
0x18000996b  xor     eax, eax
0x18000996d  add     rsp, 20h
0x180009971  pop     rbx
0x180009972  retn
```
