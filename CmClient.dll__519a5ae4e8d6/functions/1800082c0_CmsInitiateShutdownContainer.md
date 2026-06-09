# CmsInitiateShutdownContainer

- ea: `0x1800082c0`
- end: `0x18000830c`
- name: `CmsInitiateShutdownContainer`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180002d20`
- `0x1800066e4`
- `0x1800082c0`

## string_xrefs

- `0x1800082ec`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsInitiateShutdownContainer(__int64 a1, unsigned int a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 24);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_ACTIVITY_ID),void *,enum _CMS_ACTIVITY_ID &>(
         a1,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x25E,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x1800082c0  mov     [rsp+arg_8], edx
0x1800082c4  push    rbx; int
0x1800082c5  sub     rsp, 20h
0x1800082c9  mov     rax, [rcx+18h]
0x1800082cd  lea     r8, [rsp+28h+arg_8]
0x1800082d2  lea     rdx, [rsp+28h+arg_0]
0x1800082d7  mov     [rsp+28h+arg_0], rax
0x1800082dc  call    ??$InvokeStubFunction@P6AJPEAXW4_CMS_ACTIVITY_ID@@@ZPEAXAEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_ACTIVITY_ID@@@Z$$QEAPEAXAEAW43@@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_ACTIVITY_ID),void *,_CMS_ACTIVITY_ID &>(long (*)(void *,_CMS_ACTIVITY_ID),void * &&,_CMS_ACTIVITY_ID &)
0x1800082e1  mov     ebx, eax
0x1800082e3  test    eax, eax
0x1800082e5  jns     short loc_180008304
0x1800082e7  mov     rcx, [rsp+28h]; this
0x1800082ec  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800082f3  mov     r9d, eax; char *
0x1800082f6  mov     edx, 25Eh; void *
0x1800082fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008300  mov     eax, ebx
0x180008302  jmp     short loc_180008306
0x180008304  xor     eax, eax
0x180008306  add     rsp, 20h
0x18000830a  pop     rbx
0x18000830b  retn
```
