# RpcTeardown(void)

- ea: `0x1800031d0`
- end: `0x180003299`
- name: `?RpcTeardown@@YAJXZ`
- size: `201`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180008fe0`

## callees

- `0x180002c5c`
- `0x180002da8`
- `0x1800031d0`
- `0x1800032a0`

## import_xrefs

- `RPCRT4!RpcEpUnregister` at `0x180003256`
- `RPCRT4!RpcEpUnregister` at `0x180003256`
- `RPCRT4!RpcServerInqBindings` at `0x180003228`
- `RPCRT4!RpcServerInqBindings` at `0x180003228`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800031e3`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800031e3`

## string_xrefs

- `0x180003200`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\rpcsetup.cpp`
- `0x180003273`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\rpcsetup.cpp`

## pseudocode

```c
__int64 RpcTeardown(void)
{
  RPC_STATUS v0; // eax
  unsigned int v1; // ebx
  RPC_BINDING_VECTOR **v2; // rax
  RPC_STATUS v3; // eax
  __int64 v4; // r9
  RPC_STATUS v5; // eax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+40h] [rbp+8h] BYREF

  v0 = RpcServerUnregisterIfEx(qword_180024E00, 0, 1);
  v1 = v0;
  if ( !v0 )
  {
    BindingVector = 0;
    v2 = (RPC_BINDING_VECTOR **)tlx::replace<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&void _CloseBindingVector(_RPC_BINDING_VECTOR * &&),0>(&BindingVector);
    v3 = RpcServerInqBindings(v2);
    v1 = v3;
    if ( v3 )
    {
      if ( v3 > 0 )
        v1 = (unsigned __int16)v3 | 0x80070000;
      v4 = 167;
    }
    else
    {
      v5 = RpcEpUnregister(qword_180024E00, BindingVector, 0);
      v1 = v5;
      if ( !v5 )
      {
        v1 = 0;
        goto LABEL_15;
      }
      if ( v5 > 0 )
        v1 = (unsigned __int16)v5 | 0x80070000;
      v4 = 168;
    }
    Log_HREvent(
      v1,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\rpcsetup.cpp",
      v4);
LABEL_15:
    tlx::auto_xxx<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&void _CloseBindingVector(_RPC_BINDING_VECTOR * &&),0>::_Delete(&BindingVector);
    return v1;
  }
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  Log_HREvent(
    v1,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\rpcsetup.cpp",
    164);
  return v1;
}

```

## disassembly

```asm
0x1800031d0  push    rbx
0x1800031d2  sub     rsp, 30h
0x1800031d6  xor     edx, edx; MgrTypeUuid
0x1800031d8  lea     rcx, qword_180024E00; IfSpec
0x1800031df  lea     r8d, [rdx+1]; RundownContextHandles
0x1800031e3  call    cs:__imp_RpcServerUnregisterIfEx
0x1800031e9  mov     ebx, eax
0x1800031eb  test    eax, eax
0x1800031ed  jz      short loc_180003212
0x1800031ef  jle     short loc_1800031FA
0x1800031f1  movzx   ebx, ax
0x1800031f4  or      ebx, 80070000h
0x1800031fa  mov     r9d, 0A4h
0x180003200  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180003207  xor     edx, edx
0x180003209  mov     ecx, ebx
0x18000320b  call    Log_HREvent
0x180003210  jmp     short loc_180003291
0x180003212  lea     rcx, [rsp+38h+BindingVector]
0x180003217  mov     [rsp+38h+BindingVector], 0
0x180003220  call    ??$replace@PEAU_RPC_BINDING_VECTOR@@P6AX$$QEAPEAU1@@Z$1?_CloseBindingVector@@YAX0@Z$0A@@tlx@@YAPEAPEAU_RPC_BINDING_VECTOR@@AEAV?$auto_xxx@PEAU_RPC_BINDING_VECTOR@@P6AX$$QEAPEAU1@@Z$1?_CloseBindingVector@@YAX0@Z$0A@@0@@Z; tlx::replace<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&_CloseBindingVector(_RPC_BINDING_VECTOR * &&),0>(tlx::auto_xxx<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&_CloseBindingVector(_RPC_BINDING_VECTOR * &&),0> &)
0x180003225  mov     rcx, rax; BindingVector
0x180003228  call    cs:__imp_RpcServerInqBindings
0x18000322e  mov     ebx, eax
0x180003230  test    eax, eax
0x180003232  jz      short loc_180003247
0x180003234  jle     short loc_18000323F
0x180003236  movzx   ebx, ax
0x180003239  or      ebx, 80070000h
0x18000323f  mov     r9d, 0A7h
0x180003245  jmp     short loc_180003273
0x180003247  mov     rdx, [rsp+38h+BindingVector]; BindingVector
0x18000324c  lea     rcx, qword_180024E00; IfSpec
0x180003253  xor     r8d, r8d; UuidVector
0x180003256  call    cs:__imp_RpcEpUnregister
0x18000325c  mov     ebx, eax
0x18000325e  test    eax, eax
0x180003260  jz      short loc_180003285
0x180003262  jle     short loc_18000326D
0x180003264  movzx   ebx, ax
0x180003267  or      ebx, 80070000h
0x18000326d  mov     r9d, 0A8h
0x180003273  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000327a  xor     edx, edx
0x18000327c  mov     ecx, ebx
0x18000327e  call    Log_HREvent
0x180003283  jmp     short loc_180003287
0x180003285  xor     ebx, ebx
0x180003287  lea     rcx, [rsp+38h+BindingVector]
0x18000328c  call    ?_Delete@?$auto_xxx@PEAU_RPC_BINDING_VECTOR@@P6AX$$QEAPEAU1@@Z$1?_CloseBindingVector@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&_CloseBindingVector(_RPC_BINDING_VECTOR * &&),0>::_Delete(void)
0x180003291  mov     eax, ebx
0x180003293  add     rsp, 30h
0x180003297  pop     rbx
0x180003298  retn
```
