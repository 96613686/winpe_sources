# CmsUnmapVirtualDiskFromContainer

- ea: `0x1800099e0`
- end: `0x180009a33`
- name: `CmsUnmapVirtualDiskFromContainer`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x1800099e0`

## string_xrefs

- `0x180009a13`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsUnmapVirtualDiskFromContainer(__int64 a1, __int64 a2)
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
         (__int64 (__fastcall *)(_QWORD, _QWORD))CmsRpcClt_UnmapVirtualDiskFromContainer,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4FF,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x1800099e0  mov     r11, rsp
0x1800099e3  mov     [r11+10h], rdx
0x1800099e7  push    rbx; int
0x1800099e8  sub     rsp, 20h
0x1800099ec  mov     rax, [rcx+8]
0x1800099f0  lea     r8, [r11+10h]
0x1800099f4  lea     rcx, CmsRpcClt_UnmapVirtualDiskFromContainer
0x1800099fb  mov     [r11+8], rax
0x1800099ff  lea     rdx, [r11+8]
0x180009a03  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x180009a08  mov     ebx, eax
0x180009a0a  test    eax, eax
0x180009a0c  jns     short loc_180009A2B
0x180009a0e  mov     rcx, [rsp+28h]; this
0x180009a13  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180009a1a  mov     r9d, eax; char *
0x180009a1d  mov     edx, 4FFh; void *
0x180009a22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a27  mov     eax, ebx
0x180009a29  jmp     short loc_180009A2D
0x180009a2b  xor     eax, eax
0x180009a2d  add     rsp, 20h
0x180009a31  pop     rbx
0x180009a32  retn
```
