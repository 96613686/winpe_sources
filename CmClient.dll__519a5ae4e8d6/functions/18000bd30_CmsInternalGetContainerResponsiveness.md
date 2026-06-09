# CmsInternalGetContainerResponsiveness

- ea: `0x18000bd30`
- end: `0x18000bd83`
- name: `CmsInternalGetContainerResponsiveness`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x18000bd30`

## string_xrefs

- `0x18000bd63`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalGetContainerResponsiveness(__int64 a1, __int64 a2)
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
         (__int64 (__fastcall *)(_QWORD, _QWORD))CmsRpcClt_GetContainerResponsiveness,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x138,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000bd30  mov     r11, rsp
0x18000bd33  mov     [r11+10h], rdx
0x18000bd37  push    rbx; int
0x18000bd38  sub     rsp, 20h
0x18000bd3c  mov     rax, [rcx+18h]
0x18000bd40  lea     r8, [r11+10h]
0x18000bd44  lea     rcx, CmsRpcClt_GetContainerResponsiveness
0x18000bd4b  mov     [r11+8], rax
0x18000bd4f  lea     rdx, [r11+8]
0x18000bd53  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x18000bd58  mov     ebx, eax
0x18000bd5a  test    eax, eax
0x18000bd5c  jns     short loc_18000BD7B
0x18000bd5e  mov     rcx, [rsp+28h]; this
0x18000bd63  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000bd6a  mov     r9d, eax; char *
0x18000bd6d  mov     edx, 138h; void *
0x18000bd72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd77  mov     eax, ebx
0x18000bd79  jmp     short loc_18000BD7D
0x18000bd7b  xor     eax, eax
0x18000bd7d  add     rsp, 20h
0x18000bd81  pop     rbx
0x18000bd82  retn
```
