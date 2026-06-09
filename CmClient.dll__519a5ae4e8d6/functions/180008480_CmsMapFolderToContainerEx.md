# CmsMapFolderToContainerEx

- ea: `0x180008480`
- end: `0x1800084cc`
- name: `CmsMapFolderToContainerEx`
- size: `76`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008440`

## callees

- `0x1800026e0`
- `0x1800066e4`
- `0x180008480`

## string_xrefs

- `0x1800084ac`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsMapFolderToContainerEx(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 8);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_MAPPED_FOLDER_PROPERTIES *),void *,_CMS_MAPPED_FOLDER_PROPERTIES * &>(
         a1,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3F7,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x180008480  mov     r11, rsp
0x180008483  mov     [r11+10h], rdx
0x180008487  push    rbx; int
0x180008488  sub     rsp, 20h
0x18000848c  mov     rax, [rcx+8]
0x180008490  lea     r8, [r11+10h]
0x180008494  lea     rdx, [r11+8]
0x180008498  mov     [r11+8], rax
0x18000849c  call    ??$InvokeStubFunction@P6AJPEAXPEAU_CMS_MAPPED_FOLDER_PROPERTIES@@@ZPEAXAEAPEAU1@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_CMS_MAPPED_FOLDER_PROPERTIES@@@Z$$QEAPEAXAEAPEAU3@@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_MAPPED_FOLDER_PROPERTIES *),void *,_CMS_MAPPED_FOLDER_PROPERTIES * &>(long (*)(void *,_CMS_MAPPED_FOLDER_PROPERTIES *),void * &&,_CMS_MAPPED_FOLDER_PROPERTIES * &)
0x1800084a1  mov     ebx, eax
0x1800084a3  test    eax, eax
0x1800084a5  jns     short loc_1800084C4
0x1800084a7  mov     rcx, [rsp+28h]; this
0x1800084ac  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800084b3  mov     r9d, eax; char *
0x1800084b6  mov     edx, 3F7h; void *
0x1800084bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800084c0  mov     eax, ebx
0x1800084c2  jmp     short loc_1800084C6
0x1800084c4  xor     eax, eax
0x1800084c6  add     rsp, 20h
0x1800084ca  pop     rbx
0x1800084cb  retn
```
