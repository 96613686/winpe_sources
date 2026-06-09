# CmsServicingCommitTransaction

- ea: `0x18000cfc0`
- end: `0x18000d007`
- name: `CmsServicingCommitTransaction`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800021dc`
- `0x1800066e4`
- `0x18000cfc0`

## string_xrefs

- `0x18000cfe7`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsServicingCommitTransaction(__int64 a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = a1;
  v1 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(
         (__int64 (__fastcall *)(_QWORD))CmsRpcClt_CommitTransaction,
         &v6);
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x13D,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18000cfc0  push    rbx; int
0x18000cfc2  sub     rsp, 20h
0x18000cfc6  mov     [rsp+28h+arg_0], rcx
0x18000cfcb  lea     rdx, [rsp+28h+arg_0]
0x18000cfd0  lea     rcx, CmsRpcClt_CommitTransaction
0x18000cfd7  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x18000cfdc  mov     ebx, eax
0x18000cfde  test    eax, eax
0x18000cfe0  jns     short loc_18000CFFF
0x18000cfe2  mov     rcx, [rsp+28h]; this
0x18000cfe7  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000cfee  mov     r9d, eax; char *
0x18000cff1  mov     edx, 13Dh; void *
0x18000cff6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cffb  mov     eax, ebx
0x18000cffd  jmp     short loc_18000D001
0x18000cfff  xor     eax, eax
0x18000d001  add     rsp, 20h
0x18000d005  pop     rbx
0x18000d006  retn
```
