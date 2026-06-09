# GetMidiSrvBindingHandle(void * *)

- ea: `0x180012610`
- end: `0x1800126dc`
- name: `?GetMidiSrvBindingHandle@@YAJPEAPEAX@Z`
- size: `204`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012448`
- `0x1800126e4`
- `0x180012830`
- `0x180012964`
- `0x180012b04`
- `0x180013730`
- `0x1800138f8`
- `0x180013a3c`
- `0x180013bf4`
- `0x180013d98`

## callees

- `0x180007e24`
- `0x180012610`
- `0x180013878`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800126b0`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800126b0`
- `RPCRT4!RpcStringFreeW` at `0x1800126a0`
- `RPCRT4!RpcStringFreeW` at `0x1800126ce`
- `RPCRT4!RpcStringFreeW` at `0x1800126a0`
- `RPCRT4!RpcStringFreeW` at `0x1800126ce`
- `RPCRT4!RpcStringBindingComposeW` at `0x180012675`
- `RPCRT4!RpcStringBindingComposeW` at `0x180012675`

## pseudocode

```c
__int64 __fastcall GetMidiSrvBindingHandle(RPC_BINDING_HANDLE *Binding)
{
  unsigned int v2; // ebx
  unsigned int v4; // eax
  unsigned int v5; // r8d
  __int64 v6; // rdx
  int Options; // [rsp+20h] [rbp-18h]
  unsigned int Optionsa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  RPC_WSTR String; // [rsp+40h] [rbp+8h] BYREF

  if ( !Binding )
  {
    v2 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"avcore\\midi2\\libs\\midisrvtransportlib\\midisrvtransport.cpp",
      (const char *)0x80070057LL,
      Options);
    return v2;
  }
  *Binding = 0;
  String = 0;
  v4 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
  if ( v4 )
  {
    v6 = 51;
    goto LABEL_6;
  }
  v4 = RpcBindingFromStringBindingW(String, Binding);
  if ( v4 )
  {
    v6 = 55;
LABEL_6:
    v2 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v6, v5, (const char *)v4, Optionsa);
    if ( String )
      RpcStringFreeW(&String);
    return v2;
  }
  if ( String )
    RpcStringFreeW(&String);
  return 0;
}

```

## disassembly

```asm
0x180012610  push    rbx
0x180012612  sub     rsp, 30h
0x180012616  mov     rbx, rcx
0x180012619  test    rcx, rcx
0x18001261c  jnz     short loc_180012643
0x18001261e  mov     rcx, [rsp+38h]; this
0x180012623  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x18001262a  mov     ebx, 80070057h
0x18001262f  mov     edx, 21h ; '!'; void *
0x180012634  mov     r9d, ebx; char *
0x180012637  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001263c  mov     eax, ebx
0x18001263e  jmp     loc_1800126D6
0x180012643  lea     rax, [rsp+38h+String]
0x180012648  mov     qword ptr [rcx], 0
0x18001264f  mov     [rsp+38h+StringBinding], rax; StringBinding
0x180012654  lea     rdx, ProtSeq; "ncalrpc"
0x18001265b  xor     r9d, r9d; Endpoint
0x18001265e  mov     [rsp+38h+Options], 0; unsigned int
0x180012667  xor     r8d, r8d; NetworkAddr
0x18001266a  mov     [rsp+38h+String], 0
0x180012673  xor     ecx, ecx; ObjUuid
0x180012675  call    cs:__imp_RpcStringBindingComposeW
0x18001267b  test    eax, eax
0x18001267d  jz      short loc_1800126A8
0x18001267f  mov     edx, 33h ; '3'; void *
0x180012684  mov     rcx, [rsp+38h]; this
0x180012689  mov     r9d, eax; char *
0x18001268c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012691  cmp     [rsp+38h+String], 0
0x180012697  mov     ebx, eax
0x180012699  jz      short loc_18001263C
0x18001269b  lea     rcx, [rsp+38h+String]; String
0x1800126a0  call    cs:__imp_RpcStringFreeW
0x1800126a6  jmp     short loc_18001263C
0x1800126a8  mov     rcx, [rsp+38h+String]; StringBinding
0x1800126ad  mov     rdx, rbx; Binding
0x1800126b0  call    cs:__imp_RpcBindingFromStringBindingW
0x1800126b6  test    eax, eax
0x1800126b8  jz      short loc_1800126C1
0x1800126ba  mov     edx, 37h ; '7'
0x1800126bf  jmp     short loc_180012684
0x1800126c1  cmp     [rsp+38h+String], 0
0x1800126c7  jz      short loc_1800126D4
0x1800126c9  lea     rcx, [rsp+38h+String]; String
0x1800126ce  call    cs:__imp_RpcStringFreeW
0x1800126d4  xor     eax, eax
0x1800126d6  add     rsp, 30h
0x1800126da  pop     rbx
0x1800126db  retn
```
