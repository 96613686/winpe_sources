# Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)

- ea: `0x18001a120`
- end: `0x18001a1cc`
- name: `?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ`
- size: `172`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcWrapperBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019f6c`
- `0x1800e6bb8`

## callees

- `0x1800033d0`
- `0x18001a120`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001a149`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001a149`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001a178`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001a178`
- `RPCRT4!RpcStringFreeW` at `0x18001a1b1`
- `RPCRT4!RpcStringFreeW` at `0x18001a1b1`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001a197`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001a197`

## pseudocode

```c
int __fastcall Microsoft::Diagnostics::UtcWrapperBase::Initialize(RPC_BINDING_HANDLE *this)
{
  int result; // eax
  bool v3; // sf
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  RPC_WSTR String; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 ProtSeq[20]; // [rsp+38h] [rbp-40h] BYREF

  _o_wcscpy_s(ProtSeq, 20, L"ncalrpc");
  String = 0;
  result = RpcStringBindingComposeW(0, ProtSeq, 0, 0, 0, &String);
  v3 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v3 = result < 0;
  }
  if ( !v3 )
  {
    v4 = RpcBindingFromStringBindingW(String, this + 1);
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    RpcStringFreeW(&String);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18001a120  push    rbx
0x18001a122  sub     rsp, 70h
0x18001a126  mov     rax, cs:__security_cookie
0x18001a12d  xor     rax, rsp
0x18001a130  mov     [rsp+78h+var_18], rax
0x18001a135  mov     rbx, rcx
0x18001a138  lea     r8, aNcalrpc; "ncalrpc"
0x18001a13f  lea     rcx, [rsp+78h+ProtSeq]
0x18001a144  mov     edx, 14h
0x18001a149  call    cs:__imp__o_wcscpy_s
0x18001a14f  lea     rax, [rsp+78h+String]
0x18001a154  mov     [rsp+78h+String], 0
0x18001a15d  mov     [rsp+78h+StringBinding], rax; StringBinding
0x18001a162  lea     rdx, [rsp+78h+ProtSeq]; ProtSeq
0x18001a167  xor     r9d, r9d; Endpoint
0x18001a16a  mov     [rsp+78h+Options], 0; Options
0x18001a173  xor     r8d, r8d; NetworkAddr
0x18001a176  xor     ecx, ecx; ObjUuid
0x18001a178  call    cs:__imp_RpcStringBindingComposeW
0x18001a17e  test    eax, eax
0x18001a180  jle     short loc_18001A18C
0x18001a182  movzx   eax, ax
0x18001a185  or      eax, 80070000h
0x18001a18a  test    eax, eax
0x18001a18c  js      short loc_18001A1B9
0x18001a18e  mov     rcx, [rsp+78h+String]; StringBinding
0x18001a193  lea     rdx, [rbx+8]; Binding
0x18001a197  call    cs:__imp_RpcBindingFromStringBindingW
0x18001a19d  mov     ebx, eax
0x18001a19f  test    eax, eax
0x18001a1a1  jle     short loc_18001A1AC
0x18001a1a3  movzx   ebx, ax
0x18001a1a6  or      ebx, 80070000h
0x18001a1ac  lea     rcx, [rsp+78h+String]; String
0x18001a1b1  call    cs:__imp_RpcStringFreeW
0x18001a1b7  mov     eax, ebx
0x18001a1b9  mov     rcx, [rsp+78h+var_18]
0x18001a1be  xor     rcx, rsp; StackCookie
0x18001a1c1  call    __security_check_cookie
0x18001a1c6  add     rsp, 70h
0x18001a1ca  pop     rbx
0x18001a1cb  retn
```
