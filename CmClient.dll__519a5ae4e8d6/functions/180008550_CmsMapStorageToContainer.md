# CmsMapStorageToContainer

- ea: `0x180008550`
- end: `0x1800085ae`
- name: `CmsMapStorageToContainer`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000237c`
- `0x1800066e4`
- `0x180008550`

## string_xrefs

- `0x18000858e`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsMapStorageToContainer(__int64 a1, __int64 *a2, __int64 a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF
  __int64 v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = a3;
  v8 = *a2;
  v9 = *(_QWORD *)(a1 + 8);
  v3 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *,unsigned short const *),void *,void *,unsigned short const * &>(
         (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))CmsRpcClt_MapStorageToContainer,
         &v9,
         &v8,
         &v10);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E3,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x180008550  mov     r11, rsp
0x180008553  mov     [r11+18h], r8
0x180008557  push    rbx; int
0x180008558  sub     rsp, 20h
0x18000855c  mov     rax, [rdx]
0x18000855f  lea     r9, [r11+18h]
0x180008563  mov     [r11+8], rax
0x180008567  lea     r8, [r11+8]
0x18000856b  mov     rax, [rcx+8]
0x18000856f  lea     rdx, [r11+10h]
0x180008573  lea     rcx, CmsRpcClt_MapStorageToContainer
0x18000857a  mov     [r11+10h], rax
0x18000857e  call    ??$InvokeStubFunction@P6AJPEAX0PEBG@ZPEAXPEAXAEAPEBG@Rpc@Manager@Container@@YAJP6AJPEAX0PEBG@Z$$QEAPEAX3AEAPEBG@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *,ushort const *),void *,void *,ushort const * &>(long (*)(void *,void *,ushort const *),void * &&,void * &&,ushort const * &)
0x180008583  mov     ebx, eax
0x180008585  test    eax, eax
0x180008587  jns     short loc_1800085A6
0x180008589  mov     rcx, [rsp+28h]; this
0x18000858e  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008595  mov     r9d, eax; char *
0x180008598  mov     edx, 5E3h; void *
0x18000859d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800085a2  mov     eax, ebx
0x1800085a4  jmp     short loc_1800085A8
0x1800085a6  xor     eax, eax
0x1800085a8  add     rsp, 20h
0x1800085ac  pop     rbx
0x1800085ad  retn
```
