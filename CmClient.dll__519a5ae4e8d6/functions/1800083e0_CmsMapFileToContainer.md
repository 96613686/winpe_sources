# CmsMapFileToContainer

- ea: `0x1800083e0`
- end: `0x180008434`
- name: `CmsMapFileToContainer`
- size: `84`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180002670`
- `0x1800066e4`
- `0x1800083e0`

## string_xrefs

- `0x180008414`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsMapFileToContainer(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF
  __int64 v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = a3;
  v9 = a2;
  v8 = *(_QWORD *)(a1 + 8);
  v3 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_MAPPED_FILE_PROPERTIES *,unsigned short const *),void *,_CMS_MAPPED_FILE_PROPERTIES * &,unsigned short const * &>(
         a1,
         &v8,
         &v10,
         &v9);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3E4,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x1800083e0  mov     r11, rsp
0x1800083e3  mov     [r11+18h], r8
0x1800083e7  mov     [r11+10h], rdx
0x1800083eb  push    rbx; int
0x1800083ec  sub     rsp, 20h
0x1800083f0  mov     rax, [rcx+8]
0x1800083f4  lea     r9, [r11+10h]
0x1800083f8  lea     r8, [r11+18h]
0x1800083fc  mov     [r11+8], rax
0x180008400  lea     rdx, [r11+8]
0x180008404  call    ??$InvokeStubFunction@P6AJPEAXPEAU_CMS_MAPPED_FILE_PROPERTIES@@PEBG@ZPEAXAEAPEAU1@AEAPEBG@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_CMS_MAPPED_FILE_PROPERTIES@@PEBG@Z$$QEAPEAXAEAPEAU3@AEAPEBG@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_MAPPED_FILE_PROPERTIES *,ushort const *),void *,_CMS_MAPPED_FILE_PROPERTIES * &,ushort const * &>(long (*)(void *,_CMS_MAPPED_FILE_PROPERTIES *,ushort const *),void * &&,_CMS_MAPPED_FILE_PROPERTIES * &,ushort const * &)
0x180008409  mov     ebx, eax
0x18000840b  test    eax, eax
0x18000840d  jns     short loc_18000842C
0x18000840f  mov     rcx, [rsp+28h]; this
0x180008414  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000841b  mov     r9d, eax; char *
0x18000841e  mov     edx, 3E4h; void *
0x180008423  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008428  mov     eax, ebx
0x18000842a  jmp     short loc_18000842E
0x18000842c  xor     eax, eax
0x18000842e  add     rsp, 20h
0x180008432  pop     rbx
0x180008433  retn
```
