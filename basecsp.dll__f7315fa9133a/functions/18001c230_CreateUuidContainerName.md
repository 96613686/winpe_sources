# CreateUuidContainerName

- ea: `0x18001c230`
- end: `0x18001c2cc`
- name: `CreateUuidContainerName`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010760`

## callees

- `0x18001c230`
- `0x18002cfa0`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18001c278`
- `RPCRT4!UuidToStringW` at `0x18001c278`
- `RPCRT4!UuidCreate` at `0x18001c262`
- `RPCRT4!UuidCreate` at `0x18001c262`
- `RPCRT4!RpcStringFreeW` at `0x18001c2ac`
- `RPCRT4!RpcStringFreeW` at `0x18001c2ac`

## pseudocode

```c
__int64 __fastcall CreateUuidContainerName(__int64 a1)
{
  unsigned int v2; // ebx
  RPC_WSTR v3; // rax
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+28h] [rbp-20h] BYREF

  StringUuid = 0;
  Uuid = 0;
  v2 = UuidCreate(&Uuid);
  if ( v2 || (v2 = UuidToStringW(&Uuid, &StringUuid)) != 0 )
  {
    v3 = StringUuid;
  }
  else
  {
    *(_QWORD *)(a1 + 16) = StringUuid;
    v3 = 0;
    StringUuid = 0;
    *(_DWORD *)(a1 + 24) = 1;
  }
  if ( v3 )
    RpcStringFreeW(&StringUuid);
  return v2;
}

```

## disassembly

```asm
0x18001c230  mov     [rsp+arg_8], rbx
0x18001c235  push    rdi
0x18001c236  sub     rsp, 40h
0x18001c23a  mov     rax, cs:__security_cookie
0x18001c241  xor     rax, rsp
0x18001c244  mov     [rsp+48h+var_10], rax
0x18001c249  mov     rdi, rcx
0x18001c24c  mov     [rsp+48h+StringUuid], 0
0x18001c255  xorps   xmm0, xmm0
0x18001c258  lea     rcx, [rsp+48h+Uuid]; Uuid
0x18001c25d  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18001c262  call    cs:__imp_UuidCreate
0x18001c268  mov     ebx, eax
0x18001c26a  test    eax, eax
0x18001c26c  jnz     short loc_18001C29D
0x18001c26e  lea     rdx, [rsp+48h+StringUuid]; StringUuid
0x18001c273  lea     rcx, [rsp+48h+Uuid]; Uuid
0x18001c278  call    cs:__imp_UuidToStringW
0x18001c27e  mov     ebx, eax
0x18001c280  test    eax, eax
0x18001c282  jnz     short loc_18001C29D
0x18001c284  mov     rax, [rsp+48h+StringUuid]
0x18001c289  mov     [rdi+10h], rax
0x18001c28d  xor     eax, eax
0x18001c28f  mov     [rsp+48h+StringUuid], rax
0x18001c294  mov     dword ptr [rdi+18h], 1
0x18001c29b  jmp     short loc_18001C2A2
0x18001c29d  mov     rax, [rsp+48h+StringUuid]
0x18001c2a2  test    rax, rax
0x18001c2a5  jz      short loc_18001C2B2
0x18001c2a7  lea     rcx, [rsp+48h+StringUuid]; String
0x18001c2ac  call    cs:__imp_RpcStringFreeW
0x18001c2b2  mov     eax, ebx
0x18001c2b4  mov     rcx, [rsp+48h+var_10]
0x18001c2b9  xor     rcx, rsp; StackCookie
0x18001c2bc  call    __security_check_cookie
0x18001c2c1  mov     rbx, [rsp+48h+arg_8]
0x18001c2c6  add     rsp, 40h
0x18001c2ca  pop     rdi
0x18001c2cb  retn
```
