# CmsAddHostNetworkToContainer

- ea: `0x180007090`
- end: `0x1800070f0`
- name: `CmsAddHostNetworkToContainer`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800028f4`
- `0x1800066e4`
- `0x180007090`

## string_xrefs

- `0x1800070d0`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 CmsAddHostNetworkToContainer(__int64 a1, ...)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF
  va_list va; // [rsp+48h] [rbp+10h]
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF
  va_list va1; // [rsp+50h] [rbp+18h]
  va_list va2; // [rsp+58h] [rbp+20h] BYREF

  va_start(va2, a1);
  va_start(va1, a1);
  va_start(va, a1);
  v7 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v9 = va_arg(va2, _QWORD);
  v6 = *(_QWORD *)(a1 + 8);
  v1 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,unsigned short const *,unsigned short const *),void *,_GUID * &,unsigned short const * &,unsigned short const * &>(
         a1,
         &v6,
         (__int64 *)va,
         (__int64 *)va1,
         (__int64 *)va2);
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x449,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x180007090  mov     r11, rsp
0x180007093  mov     [r11+20h], r9
0x180007097  mov     [r11+18h], r8
0x18000709b  mov     [r11+10h], rdx
0x18000709f  push    rbx
0x1800070a0  sub     rsp, 30h
0x1800070a4  mov     rax, [rcx+8]
0x1800070a8  lea     r9, [r11+18h]
0x1800070ac  mov     [r11+8], rax
0x1800070b0  lea     r8, [r11+10h]
0x1800070b4  lea     rax, [r11+20h]
0x1800070b8  lea     rdx, [r11+8]
0x1800070bc  mov     [r11-18h], rax
0x1800070c0  call    ??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@PEBG2@ZPEAXAEAPEAU1@AEAPEBGAEAPEBG@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@PEBG2@Z$$QEAPEAXAEAPEAU3@AEAPEBG6@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,ushort const *,ushort const *),void *,_GUID * &,ushort const * &,ushort const * &>(long (*)(void *,_GUID *,ushort const *,ushort const *),void * &&,_GUID * &,ushort const * &,ushort const * &)
0x1800070c5  mov     ebx, eax
0x1800070c7  test    eax, eax
0x1800070c9  jns     short loc_1800070E8
0x1800070cb  mov     rcx, [rsp+38h]; this
0x1800070d0  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800070d7  mov     r9d, eax; char *
0x1800070da  mov     edx, 449h; void *
0x1800070df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070e4  mov     eax, ebx
0x1800070e6  jmp     short loc_1800070EA
0x1800070e8  xor     eax, eax
0x1800070ea  add     rsp, 30h
0x1800070ee  pop     rbx
0x1800070ef  retn
```
