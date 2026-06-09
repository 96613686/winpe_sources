# CmsUnmapStorageFromContainer

- ea: `0x180009980`
- end: `0x1800099d6`
- name: `CmsUnmapStorageFromContainer`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x180009980`

## string_xrefs

- `0x1800099b6`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsUnmapStorageFromContainer(__int64 a1, __int64 *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v7 = *a2;
  v8 = *(_QWORD *)(a1 + 8);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
         (__int64 (__fastcall *)(_QWORD, _QWORD))CmsRpcClt_UnmapStorageFromContainer,
         &v8,
         &v7);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5F8,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x180009980  mov     r11, rsp
0x180009983  push    rbx; int
0x180009984  sub     rsp, 20h
0x180009988  mov     rax, [rdx]
0x18000998b  lea     r8, [r11+8]
0x18000998f  mov     [r11+8], rax
0x180009993  lea     rdx, [r11+10h]
0x180009997  mov     rax, [rcx+8]
0x18000999b  lea     rcx, CmsRpcClt_UnmapStorageFromContainer
0x1800099a2  mov     [r11+10h], rax
0x1800099a6  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x1800099ab  mov     ebx, eax
0x1800099ad  test    eax, eax
0x1800099af  jns     short loc_1800099CE
0x1800099b1  mov     rcx, [rsp+28h]; this
0x1800099b6  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800099bd  mov     r9d, eax; char *
0x1800099c0  mov     edx, 5F8h; void *
0x1800099c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800099ca  mov     eax, ebx
0x1800099cc  jmp     short loc_1800099D0
0x1800099ce  xor     eax, eax
0x1800099d0  add     rsp, 20h
0x1800099d4  pop     rbx
0x1800099d5  retn
```
