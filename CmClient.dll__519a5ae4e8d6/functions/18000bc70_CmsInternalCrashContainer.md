# CmsInternalCrashContainer

- ea: `0x18000bc70`
- end: `0x18000bcbb`
- name: `CmsInternalCrashContainer`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1800021dc`
- `0x1800066e4`
- `0x18000bc70`

## string_xrefs

- `0x18000bc9b`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalCrashContainer(__int64 a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = *(_QWORD *)(a1 + 8);
  v1 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(
         (__int64 (__fastcall *)(_QWORD))CmsRpcClt_CrashContainer,
         &v6);
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x209,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18000bc70  push    rbx; int
0x18000bc72  sub     rsp, 20h
0x18000bc76  mov     rax, [rcx+8]
0x18000bc7a  lea     rdx, [rsp+28h+arg_0]
0x18000bc7f  lea     rcx, CmsRpcClt_CrashContainer
0x18000bc86  mov     [rsp+28h+arg_0], rax
0x18000bc8b  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x18000bc90  mov     ebx, eax
0x18000bc92  test    eax, eax
0x18000bc94  jns     short loc_18000BCB3
0x18000bc96  mov     rcx, [rsp+28h]; this
0x18000bc9b  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000bca2  mov     r9d, eax; char *
0x18000bca5  mov     edx, 209h; void *
0x18000bcaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bcaf  mov     eax, ebx
0x18000bcb1  jmp     short loc_18000BCB5
0x18000bcb3  xor     eax, eax
0x18000bcb5  add     rsp, 20h
0x18000bcb9  pop     rbx
0x18000bcba  retn
```
