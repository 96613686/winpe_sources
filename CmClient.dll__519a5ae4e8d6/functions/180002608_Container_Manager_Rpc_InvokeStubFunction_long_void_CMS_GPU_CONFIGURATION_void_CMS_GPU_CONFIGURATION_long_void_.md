# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_GPU_CONFIGURATION *),void *,_CMS_GPU_CONFIGURATION * &>(long (*)(void *,_CMS_GPU_CONFIGURATION *),void * &&,_CMS_GPU_CONFIGURATION * &)

- ea: `0x180002608`
- end: `0x18000266a`
- name: `??$InvokeStubFunction@P6AJPEAXPEAU_CMS_GPU_CONFIGURATION@@@ZPEAXAEAPEAU1@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_CMS_GPU_CONFIGURATION@@@Z$$QEAPEAXAEAPEAU3@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180009a40`

## callees

- `0x180002608`
- `0x1800066e4`
- `0x18000672c`
- `0x18000ea8c`

## string_xrefs

- `0x18000262a`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000264f`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_GPU_CONFIGURATION *),void *,_CMS_GPU_CONFIGURATION * &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  int updated; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  updated = CmsRpcClt_UpdateContainerGpuConfiguration(*a2, *a3);
  v4 = updated;
  if ( updated >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)updated,
    v6);
  return v4;
}

```

## disassembly

```asm
0x180002608  push    rbx; int
0x18000260a  sub     rsp, 20h
0x18000260e  mov     rax, rdx
0x180002611  mov     rdx, [r8]
0x180002614  mov     rcx, [rax]
0x180002617  call    CmsRpcClt_UpdateContainerGpuConfiguration
0x18000261c  mov     ebx, eax
0x18000261e  test    eax, eax
0x180002620  jns     short loc_18000263F
0x180002622  mov     rcx, [rsp+28h]; this
0x180002627  mov     r9d, eax; char *
0x18000262a  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002631  mov     edx, 56h ; 'V'; void *
0x180002636  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000263b  mov     eax, ebx
0x18000263d  jmp     short loc_180002664
0x18000263f  xor     eax, eax
0x180002641  jmp     short loc_180002664
0x180002643  test    eax, eax
0x180002645  jz      short loc_180002662
0x180002647  mov     rcx, [rsp+28h]; this
0x18000264c  mov     r9d, eax; char *
0x18000264f  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002656  mov     edx, 5Ch ; '\'; void *
0x18000265b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002660  jmp     short loc_180002664
0x180002662  xor     eax, eax
0x180002664  add     rsp, 20h
0x180002668  pop     rbx
0x180002669  retn
```
