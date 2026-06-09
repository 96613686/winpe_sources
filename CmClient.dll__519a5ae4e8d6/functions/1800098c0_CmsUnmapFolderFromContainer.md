# CmsUnmapFolderFromContainer

- ea: `0x1800098c0`
- end: `0x180009913`
- name: `CmsUnmapFolderFromContainer`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000aa50`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x1800098c0`

## string_xrefs

- `0x1800098f3`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsUnmapFolderFromContainer(__int64 a1, __int64 a2)
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
         (__int64 (__fastcall *)(_QWORD, _QWORD))CmsRpcClt_UnmapFolderFromContainer,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x40A,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x1800098c0  mov     r11, rsp
0x1800098c3  mov     [r11+10h], rdx
0x1800098c7  push    rbx; int
0x1800098c8  sub     rsp, 20h
0x1800098cc  mov     rax, [rcx+8]
0x1800098d0  lea     r8, [r11+10h]
0x1800098d4  lea     rcx, CmsRpcClt_UnmapFolderFromContainer
0x1800098db  mov     [r11+8], rax
0x1800098df  lea     rdx, [r11+8]
0x1800098e3  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x1800098e8  mov     ebx, eax
0x1800098ea  test    eax, eax
0x1800098ec  jns     short loc_18000990B
0x1800098ee  mov     rcx, [rsp+28h]; this
0x1800098f3  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800098fa  mov     r9d, eax; char *
0x1800098fd  mov     edx, 40Ah; void *
0x180009902  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009907  mov     eax, ebx
0x180009909  jmp     short loc_18000990D
0x18000990b  xor     eax, eax
0x18000990d  add     rsp, 20h
0x180009911  pop     rbx
0x180009912  retn
```
