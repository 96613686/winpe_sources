# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,ulong,void * *),void *,ulong &,void * * &>(long (*)(void *,ulong,void * *),void * &&,ulong &,void * * &)

- ea: `0x18000b578`
- end: `0x18000b5df`
- name: `??$InvokeStubFunction@P6AJPEAXKPEAPEAX@ZPEAXAEAKAEAPEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXKPEAPEAX@Z$$QEAPEAXAEAKAEAPEAPEAX@Z`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c360`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000b578`
- `0x18000e4f4`

## string_xrefs

- `0x18000b59f`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000b5c4`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,unsigned long,void * *),void *,unsigned long &,void * * &>(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3,
        _QWORD *a4)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = CmsRpcClt_OpenContainerMemoryHostingProcess(*a2, *a3, *a4);
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
0x18000b578  push    rbx; int
0x18000b57a  sub     rsp, 20h
0x18000b57e  mov     rax, r8
0x18000b581  mov     r10, rdx
0x18000b584  mov     r8, [r9]
0x18000b587  mov     edx, [rax]
0x18000b589  mov     rcx, [r10]
0x18000b58c  call    CmsRpcClt_OpenContainerMemoryHostingProcess
0x18000b591  mov     ebx, eax
0x18000b593  test    eax, eax
0x18000b595  jns     short loc_18000B5B4
0x18000b597  mov     rcx, [rsp+28h]; this
0x18000b59c  mov     r9d, eax; char *
0x18000b59f  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b5a6  mov     edx, 56h ; 'V'; void *
0x18000b5ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b5b0  mov     eax, ebx
0x18000b5b2  jmp     short loc_18000B5D9
0x18000b5b4  xor     eax, eax
0x18000b5b6  jmp     short loc_18000B5D9
0x18000b5b8  test    eax, eax
0x18000b5ba  jz      short loc_18000B5D7
0x18000b5bc  mov     rcx, [rsp+28h]; this
0x18000b5c1  mov     r9d, eax; char *
0x18000b5c4  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b5cb  mov     edx, 5Ch ; '\'; void *
0x18000b5d0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b5d5  jmp     short loc_18000B5D9
0x18000b5d7  xor     eax, eax
0x18000b5d9  add     rsp, 20h
0x18000b5dd  pop     rbx
0x18000b5de  retn
```
