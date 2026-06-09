# Comms::RpcClient::InitializeBinding(ushort const *,void * &)

- ea: `0x180003330`
- end: `0x1800033e2`
- name: `?InitializeBinding@RpcClient@Comms@@QEAAJPEBGAEAPEAX@Z`
- size: `178`
- prototype: `__int64 __fastcall(Comms::RpcClient *this, unsigned __int16 *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003224`
- `0x180003330`
- `0x180003738`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000338f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000338f`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000336e`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000336e`

## pseudocode

```c
__int64 __fastcall Comms::RpcClient::InitializeBinding(Comms::RpcClient *this, unsigned __int16 *a2, void **a3)
{
  RPC_STATUS v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  RPC_WSTR StringBinding[3]; // [rsp+30h] [rbp-18h] BYREF

  *(_OWORD *)StringBinding = 0;
  v5 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, a2, 0, StringBinding);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
  }
  else
  {
    v7 = RpcBindingFromStringBindingW(StringBinding[0], a3);
    if ( v7 )
    {
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      v6 = v7;
    }
    else
    {
      StringBinding[1] = (RPC_WSTR)a3;
      if ( (unsigned __int8)utl::vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>::push_back(
                              this,
                              StringBinding) )
        v6 = 0;
      else
        v6 = -2147024882;
    }
  }
  Comms::RpcClient::Binders::~Binders(StringBinding);
  return v6;
}

```

## disassembly

```asm
0x180003330  mov     r11, rsp
0x180003333  mov     [r11+8], rbx
0x180003337  mov     [r11+10h], rsi
0x18000333b  push    rdi
0x18000333c  sub     rsp, 40h
0x180003340  lea     rax, [r11-18h]
0x180003344  mov     rdi, r8
0x180003347  mov     rsi, rcx
0x18000334a  mov     [r11-20h], rax
0x18000334e  xorps   xmm0, xmm0
0x180003351  mov     qword ptr [r11-28h], 0
0x180003359  mov     r9, rdx; Endpoint
0x18000335c  xor     r8d, r8d; NetworkAddr
0x18000335f  lea     rdx, ProtSeq; "ncalrpc"
0x180003366  xor     ecx, ecx; ObjUuid
0x180003368  movdqu  xmmword ptr [rsp+48h+StringBinding], xmm0
0x18000336e  call    cs:__imp_RpcStringBindingComposeW
0x180003374  mov     ebx, eax
0x180003376  test    eax, eax
0x180003378  jz      short loc_180003387
0x18000337a  jle     short loc_1800033C6
0x18000337c  movzx   ebx, ax
0x18000337f  or      ebx, 80070000h
0x180003385  jmp     short loc_1800033C6
0x180003387  mov     rcx, [rsp+48h+StringBinding]; StringBinding
0x18000338c  mov     rdx, rdi; Binding
0x18000338f  call    cs:__imp_RpcBindingFromStringBindingW
0x180003395  test    eax, eax
0x180003397  jz      short loc_1800033A7
0x180003399  jle     short loc_1800033A3
0x18000339b  movzx   eax, ax
0x18000339e  or      eax, 80070000h
0x1800033a3  mov     ebx, eax
0x1800033a5  jmp     short loc_1800033C6
0x1800033a7  lea     rdx, [rsp+48h+StringBinding]
0x1800033ac  mov     [rsp+48h+StringBinding+8], rdi
0x1800033b1  mov     rcx, rsi
0x1800033b4  call    ?push_back@?$vector@UBinders@RpcClient@Comms@@V?$allocator@UBinders@RpcClient@Comms@@@utl@@@utl@@QEAA_N$$QEAUBinders@RpcClient@Comms@@@Z; utl::vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>::push_back(Comms::RpcClient::Binders &&)
0x1800033b9  test    al, al
0x1800033bb  jnz     short loc_1800033C4
0x1800033bd  mov     ebx, 8007000Eh
0x1800033c2  jmp     short loc_1800033C6
0x1800033c4  xor     ebx, ebx
0x1800033c6  lea     rcx, [rsp+48h+StringBinding]; String
0x1800033cb  call    ??1Binders@RpcClient@Comms@@QEAA@XZ; Comms::RpcClient::Binders::~Binders(void)
0x1800033d0  mov     rsi, [rsp+48h+arg_8]
0x1800033d5  mov     eax, ebx
0x1800033d7  mov     rbx, [rsp+48h+arg_0]
0x1800033dc  add     rsp, 40h
0x1800033e0  pop     rdi
0x1800033e1  retn
```
