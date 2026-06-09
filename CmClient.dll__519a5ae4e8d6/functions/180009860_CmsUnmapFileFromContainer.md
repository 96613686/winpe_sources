# CmsUnmapFileFromContainer

- ea: `0x180009860`
- end: `0x1800098b3`
- name: `CmsUnmapFileFromContainer`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x180009860`

## string_xrefs

- `0x180009893`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsUnmapFileFromContainer(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 8);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
         (__int64 (__fastcall *)(_QWORD, _QWORD))CmsRpcClt_UnmapFileFromContainer,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x41D,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x180009860  mov     r11, rsp
0x180009863  mov     [r11+10h], rdx
0x180009867  push    rbx; int
0x180009868  sub     rsp, 20h
0x18000986c  mov     rax, [rcx+8]
0x180009870  lea     r8, [r11+10h]
0x180009874  lea     rcx, CmsRpcClt_UnmapFileFromContainer
0x18000987b  mov     [r11+8], rax
0x18000987f  lea     rdx, [r11+8]
0x180009883  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x180009888  mov     ebx, eax
0x18000988a  test    eax, eax
0x18000988c  jns     short loc_1800098AB
0x18000988e  mov     rcx, [rsp+28h]; this
0x180009893  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000989a  mov     r9d, eax; char *
0x18000989d  mov     edx, 41Dh; void *
0x1800098a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800098a7  mov     eax, ebx
0x1800098a9  jmp     short loc_1800098AD
0x1800098ab  xor     eax, eax
0x1800098ad  add     rsp, 20h
0x1800098b1  pop     rbx
0x1800098b2  retn
```
