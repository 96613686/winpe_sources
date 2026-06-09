# CmsDiagCollectContainerMemoryState

- ea: `0x18000ab40`
- end: `0x18000ab8c`
- name: `CmsDiagCollectContainerMemoryState`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800066e4`
- `0x18000aa64`
- `0x18000ab40`

## string_xrefs

- `0x18000ab6c`: `onecore\base\gendrv\silos\clem\client\dll\diagapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsDiagCollectContainerMemoryState(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 24);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *),void *,void * &>(a1, &v7, &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x62,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\diagapi.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000ab40  mov     r11, rsp
0x18000ab43  mov     [r11+10h], rdx
0x18000ab47  push    rbx; int
0x18000ab48  sub     rsp, 20h
0x18000ab4c  mov     rax, [rcx+18h]
0x18000ab50  lea     r8, [r11+10h]
0x18000ab54  lea     rdx, [r11+8]
0x18000ab58  mov     [r11+8], rax
0x18000ab5c  call    ??$InvokeStubFunction@P6AJPEAX0@ZPEAXAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX0@Z$$QEAPEAXAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *),void *,void * &>(long (*)(void *,void *),void * &&,void * &)
0x18000ab61  mov     ebx, eax
0x18000ab63  test    eax, eax
0x18000ab65  jns     short loc_18000AB84
0x18000ab67  mov     rcx, [rsp+28h]; this
0x18000ab6c  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000ab73  mov     r9d, eax; char *
0x18000ab76  mov     edx, 62h ; 'b'; void *
0x18000ab7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ab80  mov     eax, ebx
0x18000ab82  jmp     short loc_18000AB86
0x18000ab84  xor     eax, eax
0x18000ab86  add     rsp, 20h
0x18000ab8a  pop     rbx
0x18000ab8b  retn
```
