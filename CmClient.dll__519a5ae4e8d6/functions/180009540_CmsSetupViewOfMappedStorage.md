# CmsSetupViewOfMappedStorage

- ea: `0x180009540`
- end: `0x180009596`
- name: `CmsSetupViewOfMappedStorage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x180009540`

## string_xrefs

- `0x180009576`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsSetupViewOfMappedStorage(__int64 a1, __int64 *a2)
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
         (__int64 (__fastcall *)(_QWORD, _QWORD))CmsRpcClt_SetupViewOfMappedStorage,
         &v8,
         &v7);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x60D,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x180009540  mov     r11, rsp
0x180009543  push    rbx; int
0x180009544  sub     rsp, 20h
0x180009548  mov     rax, [rdx]
0x18000954b  lea     r8, [r11+8]
0x18000954f  mov     [r11+8], rax
0x180009553  lea     rdx, [r11+10h]
0x180009557  mov     rax, [rcx+8]
0x18000955b  lea     rcx, CmsRpcClt_SetupViewOfMappedStorage
0x180009562  mov     [r11+10h], rax
0x180009566  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x18000956b  mov     ebx, eax
0x18000956d  test    eax, eax
0x18000956f  jns     short loc_18000958E
0x180009571  mov     rcx, [rsp+28h]; this
0x180009576  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000957d  mov     r9d, eax; char *
0x180009580  mov     edx, 60Dh; void *
0x180009585  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000958a  mov     eax, ebx
0x18000958c  jmp     short loc_180009590
0x18000958e  xor     eax, eax
0x180009590  add     rsp, 20h
0x180009594  pop     rbx
0x180009595  retn
```
