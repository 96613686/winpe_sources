# CmsServicingAdjustMappedStorage

- ea: `0x18000ce50`
- end: `0x18000ceae`
- name: `CmsServicingAdjustMappedStorage`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x18000237c`
- `0x1800066e4`
- `0x18000ce50`

## string_xrefs

- `0x18000ce8e`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsServicingAdjustMappedStorage(__int64 a1, __int64 *a2, __int64 a3)
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
         (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))CmsRpcClt_AdjustMappedStorage,
         &v9,
         &v8,
         &v10);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x18D,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000ce50  mov     r11, rsp
0x18000ce53  mov     [r11+18h], r8
0x18000ce57  push    rbx; int
0x18000ce58  sub     rsp, 20h
0x18000ce5c  mov     rax, [rdx]
0x18000ce5f  lea     r9, [r11+18h]
0x18000ce63  mov     [r11+8], rax
0x18000ce67  lea     r8, [r11+8]
0x18000ce6b  mov     rax, [rcx+8]
0x18000ce6f  lea     rdx, [r11+10h]
0x18000ce73  lea     rcx, CmsRpcClt_AdjustMappedStorage
0x18000ce7a  mov     [r11+10h], rax
0x18000ce7e  call    ??$InvokeStubFunction@P6AJPEAX0PEBG@ZPEAXPEAXAEAPEBG@Rpc@Manager@Container@@YAJP6AJPEAX0PEBG@Z$$QEAPEAX3AEAPEBG@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *,ushort const *),void *,void *,ushort const * &>(long (*)(void *,void *,ushort const *),void * &&,void * &&,ushort const * &)
0x18000ce83  mov     ebx, eax
0x18000ce85  test    eax, eax
0x18000ce87  jns     short loc_18000CEA6
0x18000ce89  mov     rcx, [rsp+28h]; this
0x18000ce8e  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000ce95  mov     r9d, eax; char *
0x18000ce98  mov     edx, 18Dh; void *
0x18000ce9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cea2  mov     eax, ebx
0x18000cea4  jmp     short loc_18000CEA8
0x18000cea6  xor     eax, eax
0x18000cea8  add     rsp, 20h
0x18000ceac  pop     rbx
0x18000cead  retn
```
