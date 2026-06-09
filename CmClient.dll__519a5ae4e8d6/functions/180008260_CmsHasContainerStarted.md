# CmsHasContainerStarted

- ea: `0x180008260`
- end: `0x1800082b3`
- name: `CmsHasContainerStarted`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x180008260`

## string_xrefs

- `0x180008293`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsHasContainerStarted(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 24);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
         (__int64 (__fastcall *)(_QWORD, _QWORD))CmsRpcClt_HasContainerStarted,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1ED,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x180008260  mov     r11, rsp
0x180008263  mov     [r11+10h], rdx
0x180008267  push    rbx; int
0x180008268  sub     rsp, 20h
0x18000826c  mov     rax, [rcx+18h]
0x180008270  lea     r8, [r11+10h]
0x180008274  lea     rcx, CmsRpcClt_HasContainerStarted
0x18000827b  mov     [r11+8], rax
0x18000827f  lea     rdx, [r11+8]
0x180008283  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x180008288  mov     ebx, eax
0x18000828a  test    eax, eax
0x18000828c  jns     short loc_1800082AB
0x18000828e  mov     rcx, [rsp+28h]; this
0x180008293  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000829a  mov     r9d, eax; char *
0x18000829d  mov     edx, 1EDh; void *
0x1800082a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082a7  mov     eax, ebx
0x1800082a9  jmp     short loc_1800082AD
0x1800082ab  xor     eax, eax
0x1800082ad  add     rsp, 20h
0x1800082b1  pop     rbx
0x1800082b2  retn
```
