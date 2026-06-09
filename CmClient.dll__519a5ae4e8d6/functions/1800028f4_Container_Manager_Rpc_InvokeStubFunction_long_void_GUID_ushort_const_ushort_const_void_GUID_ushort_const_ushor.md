# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,ushort const *,ushort const *),void *,_GUID * &,ushort const * &,ushort const * &>(long (*)(void *,_GUID *,ushort const *,ushort const *),void * &&,_GUID * &,ushort const * &,ushort const * &)

- ea: `0x1800028f4`
- end: `0x180002967`
- name: `??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@PEBG2@ZPEAXAEAPEAU1@AEAPEBGAEAPEBG@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@PEBG2@Z$$QEAPEAXAEAPEAU3@AEAPEBG6@Z`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007090`

## callees

- `0x1800028f4`
- `0x1800066e4`
- `0x18000672c`
- `0x18000dba0`

## string_xrefs

- `0x180002927`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000294c`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,unsigned short const *,unsigned short const *),void *,_GUID * &,unsigned short const * &,unsigned short const * &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v5 = CmsRpcClt_AddHostNetworkToContainer(*a2, *a3, *a4, *a5);
  v6 = v5;
  if ( v5 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v5,
    v8);
  return v6;
}

```

## disassembly

```asm
0x1800028f4  push    rbx; int
0x1800028f6  sub     rsp, 20h
0x1800028fa  mov     rax, r9
0x1800028fd  mov     r10, r8
0x180002900  mov     r11, rdx
0x180002903  mov     r9, [rsp+28h+arg_20]
0x180002908  mov     r9, [r9]
0x18000290b  mov     r8, [rax]
0x18000290e  mov     rdx, [r10]
0x180002911  mov     rcx, [r11]
0x180002914  call    CmsRpcClt_AddHostNetworkToContainer
0x180002919  mov     ebx, eax
0x18000291b  test    eax, eax
0x18000291d  jns     short loc_18000293C
0x18000291f  mov     rcx, [rsp+28h]; this
0x180002924  mov     r9d, eax; char *
0x180002927  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000292e  mov     edx, 56h ; 'V'; void *
0x180002933  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002938  mov     eax, ebx
0x18000293a  jmp     short loc_180002961
0x18000293c  xor     eax, eax
0x18000293e  jmp     short loc_180002961
0x180002940  test    eax, eax
0x180002942  jz      short loc_18000295F
0x180002944  mov     rcx, [rsp+28h]; this
0x180002949  mov     r9d, eax; char *
0x18000294c  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002953  mov     edx, 5Ch ; '\'; void *
0x180002958  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000295d  jmp     short loc_180002961
0x18000295f  xor     eax, eax
0x180002961  add     rsp, 20h
0x180002965  pop     rbx
0x180002966  retn
```
