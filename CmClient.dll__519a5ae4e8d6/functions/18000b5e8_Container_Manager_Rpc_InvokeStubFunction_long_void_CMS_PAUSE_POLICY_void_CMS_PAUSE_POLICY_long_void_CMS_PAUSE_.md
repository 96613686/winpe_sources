# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_PAUSE_POLICY *),void *,_CMS_PAUSE_POLICY * &>(long (*)(void *,_CMS_PAUSE_POLICY *),void * &&,_CMS_PAUSE_POLICY * &)

- ea: `0x18000b5e8`
- end: `0x18000b64a`
- name: `??$InvokeStubFunction@P6AJPEAXPEAU_CMS_PAUSE_POLICY@@@ZPEAXAEAPEAU1@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_CMS_PAUSE_POLICY@@@Z$$QEAPEAXAEAPEAU3@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c650`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000b5e8`
- `0x18000e7d4`

## string_xrefs

- `0x18000b60a`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000b62f`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_PAUSE_POLICY *),void *,_CMS_PAUSE_POLICY * &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = CmsRpcClt_SetContainerDebugPausePolicy(*a2, *a3);
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
0x18000b5e8  push    rbx; int
0x18000b5ea  sub     rsp, 20h
0x18000b5ee  mov     rax, rdx
0x18000b5f1  mov     rdx, [r8]
0x18000b5f4  mov     rcx, [rax]
0x18000b5f7  call    CmsRpcClt_SetContainerDebugPausePolicy
0x18000b5fc  mov     ebx, eax
0x18000b5fe  test    eax, eax
0x18000b600  jns     short loc_18000B61F
0x18000b602  mov     rcx, [rsp+28h]; this
0x18000b607  mov     r9d, eax; char *
0x18000b60a  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b611  mov     edx, 56h ; 'V'; void *
0x18000b616  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b61b  mov     eax, ebx
0x18000b61d  jmp     short loc_18000B644
0x18000b61f  xor     eax, eax
0x18000b621  jmp     short loc_18000B644
0x18000b623  test    eax, eax
0x18000b625  jz      short loc_18000B642
0x18000b627  mov     rcx, [rsp+28h]; this
0x18000b62c  mov     r9d, eax; char *
0x18000b62f  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b636  mov     edx, 5Ch ; '\'; void *
0x18000b63b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b640  jmp     short loc_18000B644
0x18000b642  xor     eax, eax
0x18000b644  add     rsp, 20h
0x18000b648  pop     rbx
0x18000b649  retn
```
