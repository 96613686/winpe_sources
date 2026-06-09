# CmsInternalGetContainerState

- ea: `0x18000bd90`
- end: `0x18000bddc`
- name: `CmsInternalGetContainerState`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000b6b8`
- `0x18000bd90`

## string_xrefs

- `0x18000bdbc`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalGetContainerState(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 24);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CONTAINER_STATE *),void *,enum _CMS_CONTAINER_STATE * &>(
         a1,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA3,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000bd90  mov     r11, rsp
0x18000bd93  mov     [r11+10h], rdx
0x18000bd97  push    rbx; int
0x18000bd98  sub     rsp, 20h
0x18000bd9c  mov     rax, [rcx+18h]
0x18000bda0  lea     r8, [r11+10h]
0x18000bda4  lea     rdx, [r11+8]
0x18000bda8  mov     [r11+8], rax
0x18000bdac  call    ??$InvokeStubFunction@P6AJPEAXPEAW4_CMS_CONTAINER_STATE@@@ZPEAXAEAPEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXPEAW4_CMS_CONTAINER_STATE@@@Z$$QEAPEAXAEAPEAW43@@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CONTAINER_STATE *),void *,_CMS_CONTAINER_STATE * &>(long (*)(void *,_CMS_CONTAINER_STATE *),void * &&,_CMS_CONTAINER_STATE * &)
0x18000bdb1  mov     ebx, eax
0x18000bdb3  test    eax, eax
0x18000bdb5  jns     short loc_18000BDD4
0x18000bdb7  mov     rcx, [rsp+28h]; this
0x18000bdbc  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000bdc3  mov     r9d, eax; char *
0x18000bdc6  mov     edx, 0A3h; void *
0x18000bdcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bdd0  mov     eax, ebx
0x18000bdd2  jmp     short loc_18000BDD6
0x18000bdd4  xor     eax, eax
0x18000bdd6  add     rsp, 20h
0x18000bdda  pop     rbx
0x18000bddb  retn
```
