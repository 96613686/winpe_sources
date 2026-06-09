# CmsInternalSetContainerDebugPausePolicy

- ea: `0x18000c650`
- end: `0x18000c69c`
- name: `CmsInternalSetContainerDebugPausePolicy`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000b5e8`
- `0x18000c650`

## string_xrefs

- `0x18000c67c`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalSetContainerDebugPausePolicy(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 24);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_PAUSE_POLICY *),void *,_CMS_PAUSE_POLICY * &>(
         a1,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x15F,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000c650  mov     r11, rsp
0x18000c653  mov     [r11+10h], rdx
0x18000c657  push    rbx; int
0x18000c658  sub     rsp, 20h
0x18000c65c  mov     rax, [rcx+18h]
0x18000c660  lea     r8, [r11+10h]
0x18000c664  lea     rdx, [r11+8]
0x18000c668  mov     [r11+8], rax
0x18000c66c  call    ??$InvokeStubFunction@P6AJPEAXPEAU_CMS_PAUSE_POLICY@@@ZPEAXAEAPEAU1@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_CMS_PAUSE_POLICY@@@Z$$QEAPEAXAEAPEAU3@@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_PAUSE_POLICY *),void *,_CMS_PAUSE_POLICY * &>(long (*)(void *,_CMS_PAUSE_POLICY *),void * &&,_CMS_PAUSE_POLICY * &)
0x18000c671  mov     ebx, eax
0x18000c673  test    eax, eax
0x18000c675  jns     short loc_18000C694
0x18000c677  mov     rcx, [rsp+28h]; this
0x18000c67c  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c683  mov     r9d, eax; char *
0x18000c686  mov     edx, 15Fh; void *
0x18000c68b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c690  mov     eax, ebx
0x18000c692  jmp     short loc_18000C696
0x18000c694  xor     eax, eax
0x18000c696  add     rsp, 20h
0x18000c69a  pop     rbx
0x18000c69b  retn
```
