# Microsoft::Diagnostics::UtcDecoderHostApiManager::StopServer(void)

- ea: `0x140011194`
- end: `0x140011313`
- name: `?StopServer@UtcDecoderHostApiManager@Diagnostics@Microsoft@@QEAAJXZ`
- size: `383`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcDecoderHostApiManager *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000d958`
- `0x14000fa04`

## callees

- `0x14000c434`
- `0x140011194`
- `0x140011c80`

## import_xrefs

- `RPCRT4!RpcBindingVectorFree` at `0x14001125e`
- `RPCRT4!RpcBindingVectorFree` at `0x140011298`
- `RPCRT4!RpcBindingVectorFree` at `0x14001125e`
- `RPCRT4!RpcBindingVectorFree` at `0x140011298`
- `RPCRT4!RpcEpUnregister` at `0x140011218`
- `RPCRT4!RpcEpUnregister` at `0x140011218`
- `RPCRT4!RpcServerInqBindings` at `0x1400111c6`
- `RPCRT4!RpcServerInqBindings` at `0x1400111c6`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1400112ab`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1400112ab`

## string_xrefs

- `0x14001126c`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapimanager.cpp`
- `0x1400112e5`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapimanager.cpp`
- `0x1400111e7`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapiserver.cpp`
- `0x140011239`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapiserver.cpp`
- `0x1400112cc`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapiserver.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::UtcDecoderHostApiManager::StopServer(
        Microsoft::Diagnostics::UtcDecoderHostApiManager *this)
{
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  RPC_STATUS v4; // eax
  RPC_STATUS v5; // eax
  unsigned int v6; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RPC_BINDING_VECTOR *BindingVector; // [rsp+30h] [rbp+8h] BYREF
  RPC_BINDING_VECTOR *v9; // [rsp+38h] [rbp+10h] BYREF

  if ( !*((_QWORD *)this + 1) )
    gsl::details::terminate(this);
  if ( !*(_BYTE *)this )
    return 1;
  *(_BYTE *)this = 0;
  BindingVector = 0;
  v2 = RpcServerInqBindings(&BindingVector);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80010000;
  if ( (v3 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C,
      (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapiserver.cpp",
      (const char *)v3);
    if ( BindingVector )
    {
      v9 = BindingVector;
LABEL_14:
      RpcBindingVectorFree(&v9);
      goto LABEL_15;
    }
    goto LABEL_15;
  }
  v4 = RpcEpUnregister(qword_14001B150, BindingVector, 0);
  v3 = v4;
  if ( v4 > 0 )
    v3 = (unsigned __int16)v4 | 0x80010000;
  if ( (v3 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D,
      (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapiserver.cpp",
      (const char *)v3);
    if ( BindingVector )
    {
      v9 = BindingVector;
      goto LABEL_14;
    }
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapimanager.cpp",
      (const char *)v3);
    return v3;
  }
  if ( BindingVector )
  {
    v9 = BindingVector;
    RpcBindingVectorFree(&v9);
  }
  v5 = RpcServerUnregisterIfEx(qword_14001B150, 0, 1);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80010000;
  if ( (v6 & 0x80000000) == 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7E,
    (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapiserver.cpp",
    (const char *)v6);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x46,
    (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapimanager.cpp",
    (const char *)v6);
  return v6;
}

```

## disassembly

```asm
0x140011194  push    rbx; int
0x140011196  sub     rsp, 20h
0x14001119a  cmp     qword ptr [rcx+8], 0
0x14001119f  jz      loc_14001130D
0x1400111a5  cmp     byte ptr [rcx], 0
0x1400111a8  jnz     short loc_1400111B5
0x1400111aa  mov     eax, 1
0x1400111af  add     rsp, 20h
0x1400111b3  pop     rbx
0x1400111b4  retn
0x1400111b5  mov     byte ptr [rcx], 0
0x1400111b8  mov     [rsp+28h+BindingVector], 0
0x1400111c1  lea     rcx, [rsp+28h+BindingVector]; BindingVector
0x1400111c6  call    cs:__imp_RpcServerInqBindings
0x1400111cc  mov     ebx, eax
0x1400111ce  test    eax, eax
0x1400111d0  jle     short loc_1400111DB
0x1400111d2  movzx   ebx, ax
0x1400111d5  or      ebx, 80010000h
0x1400111db  test    ebx, ebx
0x1400111dd  jns     short loc_140011209
0x1400111df  mov     rcx, [rsp+28h]; this
0x1400111e4  mov     r9d, ebx; char *
0x1400111e7  lea     r8, aOnecoreBaseTel_2; "onecore\\base\\telemetry\\utc\\service"...
0x1400111ee  mov     edx, 6Ch ; 'l'; void *
0x1400111f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400111f8  mov     rax, [rsp+28h+BindingVector]
0x1400111fd  test    rax, rax
0x140011200  jz      short loc_140011264
0x140011202  mov     [rsp+28h+arg_8], rax
0x140011207  jmp     short loc_140011259
0x140011209  xor     r8d, r8d; UuidVector
0x14001120c  mov     rdx, [rsp+28h+BindingVector]; BindingVector
0x140011211  lea     rcx, qword_14001B150; IfSpec
0x140011218  call    cs:__imp_RpcEpUnregister
0x14001121e  mov     ebx, eax
0x140011220  test    eax, eax
0x140011222  jle     short loc_14001122D
0x140011224  movzx   ebx, ax
0x140011227  or      ebx, 80010000h
0x14001122d  test    ebx, ebx
0x14001122f  jns     short loc_140011284
0x140011231  mov     rcx, [rsp+28h]; this
0x140011236  mov     r9d, ebx; char *
0x140011239  lea     r8, aOnecoreBaseTel_2; "onecore\\base\\telemetry\\utc\\service"...
0x140011240  mov     edx, 6Dh ; 'm'; void *
0x140011245  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001124a  mov     rcx, [rsp+28h+BindingVector]
0x14001124f  test    rcx, rcx
0x140011252  jz      short loc_140011264
0x140011254  mov     [rsp+28h+arg_8], rcx
0x140011259  lea     rcx, [rsp+28h+arg_8]; BindingVector
0x14001125e  call    cs:__imp_RpcBindingVectorFree
0x140011264  mov     rcx, [rsp+28h]; this
0x140011269  mov     r9d, ebx; char *
0x14001126c  lea     r8, aOnecoreBaseTel_1; "onecore\\base\\telemetry\\utc\\service"...
0x140011273  mov     edx, 45h ; 'E'; void *
0x140011278  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001127d  mov     eax, ebx
0x14001127f  jmp     loc_1400111AF
0x140011284  mov     rax, [rsp+28h+BindingVector]
0x140011289  test    rax, rax
0x14001128c  jz      short loc_14001129E
0x14001128e  mov     [rsp+28h+arg_8], rax
0x140011293  lea     rcx, [rsp+28h+arg_8]; BindingVector
0x140011298  call    cs:__imp_RpcBindingVectorFree
0x14001129e  xor     edx, edx; MgrTypeUuid
0x1400112a0  lea     r8d, [rdx+1]; RundownContextHandles
0x1400112a4  lea     rcx, qword_14001B150; IfSpec
0x1400112ab  call    cs:__imp_RpcServerUnregisterIfEx
0x1400112b1  mov     ebx, eax
0x1400112b3  test    eax, eax
0x1400112b5  jle     short loc_1400112C0
0x1400112b7  movzx   ebx, ax
0x1400112ba  or      ebx, 80010000h
0x1400112c0  test    ebx, ebx
0x1400112c2  jns     short loc_1400112FD
0x1400112c4  mov     rcx, [rsp+28h]; this
0x1400112c9  mov     r9d, ebx; char *
0x1400112cc  lea     r8, aOnecoreBaseTel_2; "onecore\\base\\telemetry\\utc\\service"...
0x1400112d3  mov     edx, 7Eh ; '~'; void *
0x1400112d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400112dd  mov     rcx, [rsp+28h]; this
0x1400112e2  mov     r9d, ebx; char *
0x1400112e5  lea     r8, aOnecoreBaseTel_1; "onecore\\base\\telemetry\\utc\\service"...
0x1400112ec  mov     edx, 46h ; 'F'; void *
0x1400112f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400112f6  mov     eax, ebx
0x1400112f8  jmp     loc_1400111AF
0x1400112fd  xor     eax, eax
0x1400112ff  jmp     loc_1400111AF
0x140011304  mov     eax, dword ptr [rsp+28h+BindingVector]
0x140011308  jmp     loc_1400111AF
0x14001130d  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
