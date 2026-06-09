# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_ACTIVITY_ID),void *,_CMS_ACTIVITY_ID &>(long (*)(void *,_CMS_ACTIVITY_ID),void * &&,_CMS_ACTIVITY_ID &)

- ea: `0x180002d20`
- end: `0x180002d82`
- name: `??$InvokeStubFunction@P6AJPEAXW4_CMS_ACTIVITY_ID@@@ZPEAXAEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_ACTIVITY_ID@@@Z$$QEAPEAXAEAW43@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800082c0`

## callees

- `0x180002d20`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e2ac`

## string_xrefs

- `0x180002d42`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002d67`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_ACTIVITY_ID),void *,enum _CMS_ACTIVITY_ID &>(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = CmsRpcClt_InitiateShutdownContainer(*a2, *a3);
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
0x180002d20  push    rbx; int
0x180002d22  sub     rsp, 20h
0x180002d26  mov     rax, rdx
0x180002d29  mov     edx, [r8]
0x180002d2c  mov     rcx, [rax]
0x180002d2f  call    CmsRpcClt_InitiateShutdownContainer
0x180002d34  mov     ebx, eax
0x180002d36  test    eax, eax
0x180002d38  jns     short loc_180002D57
0x180002d3a  mov     rcx, [rsp+28h]; this
0x180002d3f  mov     r9d, eax; char *
0x180002d42  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002d49  mov     edx, 56h ; 'V'; void *
0x180002d4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002d53  mov     eax, ebx
0x180002d55  jmp     short loc_180002D7C
0x180002d57  xor     eax, eax
0x180002d59  jmp     short loc_180002D7C
0x180002d5b  test    eax, eax
0x180002d5d  jz      short loc_180002D7A
0x180002d5f  mov     rcx, [rsp+28h]; this
0x180002d64  mov     r9d, eax; char *
0x180002d67  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002d6e  mov     edx, 5Ch ; '\'; void *
0x180002d73  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002d78  jmp     short loc_180002D7C
0x180002d7a  xor     eax, eax
0x180002d7c  add     rsp, 20h
0x180002d80  pop     rbx
0x180002d81  retn
```
