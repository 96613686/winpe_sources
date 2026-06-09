# GetAEBBindingHandle(void * *)

- ea: `0x18004d818`
- end: `0x18004d8ef`
- name: `?GetAEBBindingHandle@@YAJPEAPEAX@Z`
- size: `215`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003984c`

## callees

- `0x180010da8`
- `0x180033464`
- `0x18004d818`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18004d8b3`
- `RPCRT4!RpcStringFreeW` at `0x18004d8e1`
- `RPCRT4!RpcStringFreeW` at `0x18004d8b3`
- `RPCRT4!RpcStringFreeW` at `0x18004d8e1`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18004d8c3`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18004d8c3`
- `RPCRT4!RpcStringBindingComposeW` at `0x18004d881`
- `RPCRT4!RpcStringBindingComposeW` at `0x18004d881`

## string_xrefs

- `0x18004d82b`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18004d895`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
__int64 __fastcall GetAEBBindingHandle(RPC_BINDING_HANDLE *Binding)
{
  unsigned int v2; // ebx
  unsigned int v4; // eax
  __int64 v5; // rdx
  int Options; // [rsp+20h] [rbp-18h]
  unsigned int Optionsa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  RPC_WSTR String; // [rsp+40h] [rbp+8h] BYREF

  if ( !Binding )
  {
    v2 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F7,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)0x80070057LL,
      Options);
    return v2;
  }
  *Binding = 0;
  String = 0;
  v4 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"AudioEndpointBuilderClientRpc", 0, &String);
  if ( v4 )
  {
    v5 = 1283;
    goto LABEL_6;
  }
  v4 = RpcBindingFromStringBindingW(String, Binding);
  if ( v4 )
  {
    v5 = 1284;
LABEL_6:
    v2 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v5,
           (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
           (const char *)v4,
           Optionsa);
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
0x18004d818  push    rbx
0x18004d81a  sub     rsp, 30h
0x18004d81e  mov     rbx, rcx
0x18004d821  test    rcx, rcx
0x18004d824  jnz     short loc_18004D84B
0x18004d826  mov     rcx, [rsp+38h]; this
0x18004d82b  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18004d832  mov     ebx, 80070057h
0x18004d837  mov     edx, 4F7h; void *
0x18004d83c  mov     r9d, ebx; char *
0x18004d83f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d844  mov     eax, ebx
0x18004d846  jmp     loc_18004D8E9
0x18004d84b  lea     rax, [rsp+38h+String]
0x18004d850  mov     qword ptr [rcx], 0
0x18004d857  mov     [rsp+38h+StringBinding], rax; StringBinding
0x18004d85c  lea     r9, Endpoint; "AudioEndpointBuilderClientRpc"
0x18004d863  xor     r8d, r8d; NetworkAddr
0x18004d866  mov     [rsp+38h+Options], 0; unsigned int
0x18004d86f  lea     rdx, Protseq; "ncalrpc"
0x18004d876  mov     [rsp+38h+String], 0
0x18004d87f  xor     ecx, ecx; ObjUuid
0x18004d881  call    cs:__imp_RpcStringBindingComposeW
0x18004d887  test    eax, eax
0x18004d889  jz      short loc_18004D8BB
0x18004d88b  mov     edx, 503h; void *
0x18004d890  mov     rcx, [rsp+38h]; this
0x18004d895  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18004d89c  mov     r9d, eax; char *
0x18004d89f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004d8a4  cmp     [rsp+38h+String], 0
0x18004d8aa  mov     ebx, eax
0x18004d8ac  jz      short loc_18004D844
0x18004d8ae  lea     rcx, [rsp+38h+String]; String
0x18004d8b3  call    cs:__imp_RpcStringFreeW
0x18004d8b9  jmp     short loc_18004D844
0x18004d8bb  mov     rcx, [rsp+38h+String]; StringBinding
0x18004d8c0  mov     rdx, rbx; Binding
0x18004d8c3  call    cs:__imp_RpcBindingFromStringBindingW
0x18004d8c9  test    eax, eax
0x18004d8cb  jz      short loc_18004D8D4
0x18004d8cd  mov     edx, 504h
0x18004d8d2  jmp     short loc_18004D890
0x18004d8d4  cmp     [rsp+38h+String], 0
0x18004d8da  jz      short loc_18004D8E7
0x18004d8dc  lea     rcx, [rsp+38h+String]; String
0x18004d8e1  call    cs:__imp_RpcStringFreeW
0x18004d8e7  xor     eax, eax
0x18004d8e9  add     rsp, 30h
0x18004d8ed  pop     rbx
0x18004d8ee  retn
```
