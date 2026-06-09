# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_MANUAL_HOST_STATE_FLAGS),void *,_CMS_MANUAL_HOST_STATE_FLAGS &>(long (*)(void *,_CMS_MANUAL_HOST_STATE_FLAGS),void * &&,_CMS_MANUAL_HOST_STATE_FLAGS &)

- ea: `0x18000ba24`
- end: `0x18000ba86`
- name: `??$InvokeStubFunction@P6AJPEAXW4_CMS_MANUAL_HOST_STATE_FLAGS@@@ZPEAXAEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_MANUAL_HOST_STATE_FLAGS@@@Z$$QEAPEAXAEAW43@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000cac0`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000ba24`
- `0x18000ec6c`

## string_xrefs

- `0x18000ba46`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000ba6b`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_MANUAL_HOST_STATE_FLAGS),void *,enum _CMS_MANUAL_HOST_STATE_FLAGS &>(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = CmsRpcClt_SetManualHostStateFlags(*a2, *a3);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000ba24  push    rbx; int
0x18000ba26  sub     rsp, 20h
0x18000ba2a  mov     rax, rdx
0x18000ba2d  mov     edx, [r8]
0x18000ba30  mov     rcx, [rax]
0x18000ba33  call    CmsRpcClt_SetManualHostStateFlags
0x18000ba38  mov     ebx, eax
0x18000ba3a  test    eax, eax
0x18000ba3c  jns     short loc_18000BA5B
0x18000ba3e  mov     rcx, [rsp+28h]; this
0x18000ba43  mov     r9d, eax; char *
0x18000ba46  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000ba4d  mov     edx, 56h ; 'V'; void *
0x18000ba52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba57  mov     eax, ebx
0x18000ba59  jmp     short loc_18000BA80
0x18000ba5b  xor     eax, eax
0x18000ba5d  jmp     short loc_18000BA80
0x18000ba5f  test    eax, eax
0x18000ba61  jz      short loc_18000BA7E
0x18000ba63  mov     rcx, [rsp+28h]; this
0x18000ba68  mov     r9d, eax; char *
0x18000ba6b  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000ba72  mov     edx, 5Ch ; '\'; void *
0x18000ba77  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000ba7c  jmp     short loc_18000BA80
0x18000ba7e  xor     eax, eax
0x18000ba80  add     rsp, 20h
0x18000ba84  pop     rbx
0x18000ba85  retn
```
