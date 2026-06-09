# CmsInternalSetContainerDebugFlags

- ea: `0x18000c5f0`
- end: `0x18000c63c`
- name: `CmsInternalSetContainerDebugFlags`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000b8ec`
- `0x18000c5f0`

## string_xrefs

- `0x18000c61c`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalSetContainerDebugFlags(__int64 a1, unsigned int a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 24);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CONTAINER_DEBUG_FLAGS),void *,enum _CMS_CONTAINER_DEBUG_FLAGS &>(
         a1,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x61,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000c5f0  mov     [rsp+arg_8], edx
0x18000c5f4  push    rbx; int
0x18000c5f5  sub     rsp, 20h
0x18000c5f9  mov     rax, [rcx+18h]
0x18000c5fd  lea     r8, [rsp+28h+arg_8]
0x18000c602  lea     rdx, [rsp+28h+arg_0]
0x18000c607  mov     [rsp+28h+arg_0], rax
0x18000c60c  call    ??$InvokeStubFunction@P6AJPEAXW4_CMS_CONTAINER_DEBUG_FLAGS@@@ZPEAXAEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_CONTAINER_DEBUG_FLAGS@@@Z$$QEAPEAXAEAW43@@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CONTAINER_DEBUG_FLAGS),void *,_CMS_CONTAINER_DEBUG_FLAGS &>(long (*)(void *,_CMS_CONTAINER_DEBUG_FLAGS),void * &&,_CMS_CONTAINER_DEBUG_FLAGS &)
0x18000c611  mov     ebx, eax
0x18000c613  test    eax, eax
0x18000c615  jns     short loc_18000C634
0x18000c617  mov     rcx, [rsp+28h]; this
0x18000c61c  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c623  mov     r9d, eax; char *
0x18000c626  mov     edx, 61h ; 'a'; void *
0x18000c62b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c630  mov     eax, ebx
0x18000c632  jmp     short loc_18000C636
0x18000c634  xor     eax, eax
0x18000c636  add     rsp, 20h
0x18000c63a  pop     rbx
0x18000c63b  retn
```
