# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_ACTIVITY_ID,_WNF_STATE_NAME *,void * *),void *,_CMS_ACTIVITY_ID &,_WNF_STATE_NAME *,void * *>(long (*)(void *,_CMS_ACTIVITY_ID,_WNF_STATE_NAME *,void * *),void * &&,_CMS_ACTIVITY_ID &,_WNF_STATE_NAME * &&,void * * &&)

- ea: `0x180002d88`
- end: `0x180002dfb`
- name: `??$InvokeStubFunction@P6AJPEAXW4_CMS_ACTIVITY_ID@@PEAU_WNF_STATE_NAME@@PEAPEAX@ZPEAXAEAW41@PEAU2@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_ACTIVITY_ID@@PEAU_WNF_STATE_NAME@@PEAPEAX@Z$$QEAPEAXAEAW43@$$QEAPEAU4@$$QEAPEAPEAX@Z`
- size: `115`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007490`

## callees

- `0x180002d88`
- `0x1800066e4`
- `0x18000672c`
- `0x18000de10`

## string_xrefs

- `0x180002dbb`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002de0`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_ACTIVITY_ID,_WNF_STATE_NAME *,void * *),void *,enum _CMS_ACTIVITY_ID &,_WNF_STATE_NAME *,void * *>(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  int Activity; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Activity = CmsRpcClt_CreateActivity(*a2, *a3, *a4, *a5);
  v6 = Activity;
  if ( Activity >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)Activity,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180002d88  push    rbx; int
0x180002d8a  sub     rsp, 20h
0x180002d8e  mov     rax, r9
0x180002d91  mov     r10, r8
0x180002d94  mov     r11, rdx
0x180002d97  mov     r9, [rsp+28h+arg_20]
0x180002d9c  mov     r9, [r9]
0x180002d9f  mov     r8, [rax]
0x180002da2  mov     edx, [r10]
0x180002da5  mov     rcx, [r11]
0x180002da8  call    CmsRpcClt_CreateActivity
0x180002dad  mov     ebx, eax
0x180002daf  test    eax, eax
0x180002db1  jns     short loc_180002DD0
0x180002db3  mov     rcx, [rsp+28h]; this
0x180002db8  mov     r9d, eax; char *
0x180002dbb  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002dc2  mov     edx, 56h ; 'V'; void *
0x180002dc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002dcc  mov     eax, ebx
0x180002dce  jmp     short loc_180002DF5
0x180002dd0  xor     eax, eax
0x180002dd2  jmp     short loc_180002DF5
0x180002dd4  test    eax, eax
0x180002dd6  jz      short loc_180002DF3
0x180002dd8  mov     rcx, [rsp+28h]; this
0x180002ddd  mov     r9d, eax; char *
0x180002de0  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002de7  mov     edx, 5Ch ; '\'; void *
0x180002dec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002df1  jmp     short loc_180002DF5
0x180002df3  xor     eax, eax
0x180002df5  add     rsp, 20h
0x180002df9  pop     rbx
0x180002dfa  retn
```
