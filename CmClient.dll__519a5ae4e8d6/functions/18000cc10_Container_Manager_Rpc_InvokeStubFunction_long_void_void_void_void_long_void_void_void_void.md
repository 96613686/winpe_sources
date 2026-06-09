# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void * *),void *,void * * &>(long (*)(void *,void * *),void * &&,void * * &)

- ea: `0x18000cc10`
- end: `0x18000cc72`
- name: `??$InvokeStubFunction@P6AJPEAXPEAPEAX@ZPEAXAEAPEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXPEAPEAX@Z$$QEAPEAXAEAPEAPEAX@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000d830`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000cc10`
- `0x18000e8bc`

## string_xrefs

- `0x18000cc32`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000cc57`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void * *),void *,void * * &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = CmsRpcClt_SetupViewOfLayer(*a2, *a3);
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
0x18000cc10  push    rbx; int
0x18000cc12  sub     rsp, 20h
0x18000cc16  mov     rax, rdx
0x18000cc19  mov     rdx, [r8]
0x18000cc1c  mov     rcx, [rax]
0x18000cc1f  call    CmsRpcClt_SetupViewOfLayer
0x18000cc24  mov     ebx, eax
0x18000cc26  test    eax, eax
0x18000cc28  jns     short loc_18000CC47
0x18000cc2a  mov     rcx, [rsp+28h]; this
0x18000cc2f  mov     r9d, eax; char *
0x18000cc32  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000cc39  mov     edx, 56h ; 'V'; void *
0x18000cc3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc43  mov     eax, ebx
0x18000cc45  jmp     short loc_18000CC6C
0x18000cc47  xor     eax, eax
0x18000cc49  jmp     short loc_18000CC6C
0x18000cc4b  test    eax, eax
0x18000cc4d  jz      short loc_18000CC6A
0x18000cc4f  mov     rcx, [rsp+28h]; this
0x18000cc54  mov     r9d, eax; char *
0x18000cc57  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000cc5e  mov     edx, 5Ch ; '\'; void *
0x18000cc63  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000cc68  jmp     short loc_18000CC6C
0x18000cc6a  xor     eax, eax
0x18000cc6c  add     rsp, 20h
0x18000cc70  pop     rbx
0x18000cc71  retn
```
