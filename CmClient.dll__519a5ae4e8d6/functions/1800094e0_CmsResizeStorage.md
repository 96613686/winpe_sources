# CmsResizeStorage

- ea: `0x1800094e0`
- end: `0x18000952b`
- name: `CmsResizeStorage`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180002efc`
- `0x1800066e4`
- `0x1800094e0`

## string_xrefs

- `0x18000950b`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsResizeStorage(__int64 *a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *a1;
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,unsigned __int64),void *,unsigned __int64 &>(
         (__int64)a1,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x662,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x1800094e0  mov     r11, rsp
0x1800094e3  mov     [r11+10h], rdx
0x1800094e7  push    rbx; int
0x1800094e8  sub     rsp, 20h
0x1800094ec  mov     rax, [rcx]
0x1800094ef  lea     r8, [r11+10h]
0x1800094f3  lea     rdx, [r11+8]
0x1800094f7  mov     [r11+8], rax
0x1800094fb  call    ??$InvokeStubFunction@P6AJPEAX_K@ZPEAXAEA_K@Rpc@Manager@Container@@YAJP6AJPEAX_K@Z$$QEAPEAXAEA_K@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,unsigned __int64),void *,unsigned __int64 &>(long (*)(void *,unsigned __int64),void * &&,unsigned __int64 &)
0x180009500  mov     ebx, eax
0x180009502  test    eax, eax
0x180009504  jns     short loc_180009523
0x180009506  mov     rcx, [rsp+28h]; this
0x18000950b  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180009512  mov     r9d, eax; char *
0x180009515  mov     edx, 662h; void *
0x18000951a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000951f  mov     eax, ebx
0x180009521  jmp     short loc_180009525
0x180009523  xor     eax, eax
0x180009525  add     rsp, 20h
0x180009529  pop     rbx
0x18000952a  retn
```
