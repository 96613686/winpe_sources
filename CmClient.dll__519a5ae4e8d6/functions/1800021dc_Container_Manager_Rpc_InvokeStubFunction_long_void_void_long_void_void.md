# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)

- ea: `0x1800021dc`
- end: `0x18000223b`
- name: `??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z`
- size: `95`
- prototype: ``
- caller_count: `18`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007100`
- `0x1800071d0`
- `0x1800072b0`
- `0x180007350`
- `0x180007400`
- `0x1800079d0`
- `0x180007ed0`
- `0x180008a90`
- `0x180009270`
- `0x1800095a0`
- `0x18000bc70`
- `0x18000c3c0`
- `0x18000cda0`
- `0x18000cec0`
- `0x18000cfc0`
- `0x18000d4a0`
- `0x18000d7e0`
- `0x18000d890`

## callees

- `0x1800021dc`
- `0x1800066e4`
- `0x18000672c`
- `0x180010010`

## string_xrefs

- `0x1800021fb`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002220`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(
        __int64 (__fastcall *a1)(_QWORD),
        _QWORD *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = a1(*a2);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x1800021dc  push    rbx; int
0x1800021de  sub     rsp, 20h
0x1800021e2  mov     rax, rcx
0x1800021e5  mov     rcx, [rdx]
0x1800021e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021ed  mov     ebx, eax
0x1800021ef  test    eax, eax
0x1800021f1  jns     short loc_180002210
0x1800021f3  mov     rcx, [rsp+28h]; this
0x1800021f8  mov     r9d, eax; char *
0x1800021fb  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002202  mov     edx, 56h ; 'V'; void *
0x180002207  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000220c  mov     eax, ebx
0x18000220e  jmp     short loc_180002235
0x180002210  xor     eax, eax
0x180002212  jmp     short loc_180002235
0x180002214  test    eax, eax
0x180002216  jz      short loc_180002233
0x180002218  mov     rcx, [rsp+28h]; this
0x18000221d  mov     r9d, eax; char *
0x180002220  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002227  mov     edx, 5Ch ; '\'; void *
0x18000222c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002231  jmp     short loc_180002235
0x180002233  xor     eax, eax
0x180002235  add     rsp, 20h
0x180002239  pop     rbx
0x18000223a  retn
```
