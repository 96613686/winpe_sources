# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CLIENT_ID,_CMS_STORAGE_PROPERTIES *,_GUID *,void * *),void *,_CMS_CLIENT_ID &,_CMS_STORAGE_PROPERTIES * &,_GUID *,void * *>(long (*)(void *,_CMS_CLIENT_ID,_CMS_STORAGE_PROPERTIES *,_GUID *,void * *),void * &&,_CMS_CLIENT_ID &,_CMS_STORAGE_PROPERTIES * &,_GUID * &&,void * * &&)

- ea: `0x180002e04`
- end: `0x180002e84`
- name: `??$InvokeStubFunction@P6AJPEAXW4_CMS_CLIENT_ID@@PEAU_CMS_STORAGE_PROPERTIES@@PEAU_GUID@@PEAPEAX@ZPEAXAEAW41@AEAPEAU2@PEAU3@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_CLIENT_ID@@PEAU_CMS_STORAGE_PROPERTIES@@PEAU_GUID@@PEAPEAX@Z$$QEAPEAXAEAW43@AEAPEAU4@$$QEAPEAU5@$$QEAPEAPEAX@Z`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007d00`

## callees

- `0x180002e04`
- `0x1800066e4`
- `0x18000672c`
- `0x18000dfe8`

## string_xrefs

- `0x180002e44`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002e69`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CLIENT_ID,_CMS_STORAGE_PROPERTIES *,_GUID *,void * *),void *,enum _CMS_CLIENT_ID &,_CMS_STORAGE_PROPERTIES * &,_GUID *,void * *>(
        __int64 a1,
        _QWORD *a2,
        _DWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 *a6)
{
  int Storage; // eax
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  Storage = CmsRpcClt_CreateStorage(*a2, *a3, *a4, *a5, *a6);
  v7 = Storage;
  if ( Storage >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)Storage,
    v9);
  return v7;
}

```

## disassembly

```asm
0x180002e04  push    rbx
0x180002e06  sub     rsp, 30h
0x180002e0a  mov     r10, r9
0x180002e0d  mov     r11, r8
0x180002e10  mov     rbx, rdx
0x180002e13  mov     rax, [rsp+38h+arg_28]
0x180002e18  mov     rcx, [rax]
0x180002e1b  mov     qword ptr [rsp+38h+var_18], rcx; int
0x180002e20  mov     r9, [rsp+38h+arg_20]
0x180002e25  mov     r9, [r9]
0x180002e28  mov     r8, [r10]
0x180002e2b  mov     edx, [r11]
0x180002e2e  mov     rcx, [rbx]
0x180002e31  call    CmsRpcClt_CreateStorage
0x180002e36  mov     ebx, eax
0x180002e38  test    eax, eax
0x180002e3a  jns     short loc_180002E59
0x180002e3c  mov     rcx, [rsp+38h]; this
0x180002e41  mov     r9d, eax; char *
0x180002e44  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002e4b  mov     edx, 56h ; 'V'; void *
0x180002e50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002e55  mov     eax, ebx
0x180002e57  jmp     short loc_180002E7E
0x180002e59  xor     eax, eax
0x180002e5b  jmp     short loc_180002E7E
0x180002e5d  test    eax, eax
0x180002e5f  jz      short loc_180002E7C
0x180002e61  mov     rcx, [rsp+38h]; this
0x180002e66  mov     r9d, eax; char *
0x180002e69  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002e70  mov     edx, 5Ch ; '\'; void *
0x180002e75  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002e7a  jmp     short loc_180002E7E
0x180002e7c  xor     eax, eax
0x180002e7e  add     rsp, 30h
0x180002e82  pop     rbx
0x180002e83  retn
```
