# CmsServicingActivateTransaction

- ea: `0x18000cda0`
- end: `0x18000cde7`
- name: `CmsServicingActivateTransaction`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1800021dc`
- `0x1800066e4`
- `0x18000cda0`

## string_xrefs

- `0x18000cdc7`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsServicingActivateTransaction(__int64 a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = a1;
  v1 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(
         (__int64 (__fastcall *)(_QWORD))CmsRpcClt_ActivateTransaction,
         &v6);
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12B,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18000cda0  push    rbx; int
0x18000cda2  sub     rsp, 20h
0x18000cda6  mov     [rsp+28h+arg_0], rcx
0x18000cdab  lea     rdx, [rsp+28h+arg_0]
0x18000cdb0  lea     rcx, CmsRpcClt_ActivateTransaction
0x18000cdb7  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x18000cdbc  mov     ebx, eax
0x18000cdbe  test    eax, eax
0x18000cdc0  jns     short loc_18000CDDF
0x18000cdc2  mov     rcx, [rsp+28h]; this
0x18000cdc7  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000cdce  mov     r9d, eax; char *
0x18000cdd1  mov     edx, 12Bh; void *
0x18000cdd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cddb  mov     eax, ebx
0x18000cddd  jmp     short loc_18000CDE1
0x18000cddf  xor     eax, eax
0x18000cde1  add     rsp, 20h
0x18000cde5  pop     rbx
0x18000cde6  retn
```
