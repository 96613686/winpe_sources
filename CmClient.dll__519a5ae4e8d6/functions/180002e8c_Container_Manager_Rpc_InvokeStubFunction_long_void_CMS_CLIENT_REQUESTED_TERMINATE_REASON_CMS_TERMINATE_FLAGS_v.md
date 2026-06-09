# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CLIENT_REQUESTED_TERMINATE_REASON,_CMS_TERMINATE_FLAGS),void *,_CMS_CLIENT_REQUESTED_TERMINATE_REASON &,_CMS_TERMINATE_FLAGS &>(long (*)(void *,_CMS_CLIENT_REQUESTED_TERMINATE_REASON,_CMS_TERMINATE_FLAGS),void * &&,_CMS_CLIENT_REQUESTED_TERMINATE_REASON &,_CMS_TERMINATE_FLAGS &)

- ea: `0x180002e8c`
- end: `0x180002ef3`
- name: `??$InvokeStubFunction@P6AJPEAXW4_CMS_CLIENT_REQUESTED_TERMINATE_REASON@@W4_CMS_TERMINATE_FLAGS@@@ZPEAXAEAW41@AEAW42@@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_CLIENT_REQUESTED_TERMINATE_REASON@@W4_CMS_TERMINATE_FLAGS@@@Z$$QEAPEAXAEAW43@AEAW44@@Z`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800097a0`

## callees

- `0x180002e8c`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e940`

## string_xrefs

- `0x180002eb3`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002ed8`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CLIENT_REQUESTED_TERMINATE_REASON,enum _CMS_TERMINATE_FLAGS),void *,enum _CMS_CLIENT_REQUESTED_TERMINATE_REASON &,enum _CMS_TERMINATE_FLAGS &>(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = CmsRpcClt_TerminateContainer(*a2, *a3, *a4);
  v5 = v4;
  if ( v4 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v4,
    v7);
  return v5;
}

```

## disassembly

```asm
0x180002e8c  push    rbx; int
0x180002e8e  sub     rsp, 20h
0x180002e92  mov     rax, r8
0x180002e95  mov     r10, rdx
0x180002e98  mov     r8d, [r9]
0x180002e9b  mov     edx, [rax]
0x180002e9d  mov     rcx, [r10]
0x180002ea0  call    CmsRpcClt_TerminateContainer
0x180002ea5  mov     ebx, eax
0x180002ea7  test    eax, eax
0x180002ea9  jns     short loc_180002EC8
0x180002eab  mov     rcx, [rsp+28h]; this
0x180002eb0  mov     r9d, eax; char *
0x180002eb3  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002eba  mov     edx, 56h ; 'V'; void *
0x180002ebf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002ec4  mov     eax, ebx
0x180002ec6  jmp     short loc_180002EED
0x180002ec8  xor     eax, eax
0x180002eca  jmp     short loc_180002EED
0x180002ecc  test    eax, eax
0x180002ece  jz      short loc_180002EEB
0x180002ed0  mov     rcx, [rsp+28h]; this
0x180002ed5  mov     r9d, eax; char *
0x180002ed8  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002edf  mov     edx, 5Ch ; '\'; void *
0x180002ee4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002ee9  jmp     short loc_180002EED
0x180002eeb  xor     eax, eax
0x180002eed  add     rsp, 20h
0x180002ef1  pop     rbx
0x180002ef2  retn
```
