# _CMidi2MidiSrv::RemoveClientSession_::_16_::_lambda_1_::operator()

- ea: `0x180011d1c`
- end: `0x180011dc9`
- name: `_CMidi2MidiSrv::RemoveClientSession_::_16_::_lambda_1_::operator()`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013730`

## callees

- `0x180007e24`
- `0x180011d1c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180011d60`
- `RPCRT4!NdrClientCall3` at `0x180011d60`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrv::RemoveClientSession_::_16_::_lambda_1_::operator()(_QWORD **a1)
{
  int Pointer; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = *a1[1];
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&MidiSrvRPC_ProxyInfo, 5u, 0, **a1).Pointer;
  v2 = Pointer;
  if ( Pointer >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x186,
    (unsigned int)"avcore\\midi2\\libs\\midisrvtransportlib\\midisrvtransport.cpp",
    (const char *)(unsigned int)Pointer,
    v4);
  return v2;
}

```

## disassembly

```asm
0x180011d1c  mov     r11, rsp
0x180011d1f  push    rbx
0x180011d20  sub     rsp, 40h
0x180011d24  mov     rdx, [rcx+10h]
0x180011d28  mov     rax, [rcx+8]
0x180011d2c  mov     r8, [rax]
0x180011d2f  mov     rax, [rcx]
0x180011d32  mov     qword ptr [r11+10h], 0
0x180011d3a  movups  xmm0, xmmword ptr [rdx]
0x180011d3d  movdqu  [rsp+48h+var_18], xmm0
0x180011d43  lea     rcx, [r11-18h]
0x180011d47  mov     [r11-20h], rcx
0x180011d4b  mov     [r11-28h], r8
0x180011d4f  mov     r9, [rax]
0x180011d52  xor     r8d, r8d; pReturnValue
0x180011d55  lea     edx, [r8+5]; nProcNum
0x180011d59  lea     rcx, ?MidiSrvRPC_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180011d60  call    cs:__imp_NdrClientCall3
0x180011d66  mov     rbx, rax
0x180011d69  mov     [rsp+48h+arg_8], rax
0x180011d6e  test    eax, eax
0x180011d70  jns     short loc_180011D8F
0x180011d72  mov     rcx, [rsp+48h]; this
0x180011d77  mov     r9d, ebx; char *
0x180011d7a  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x180011d81  mov     edx, 186h; void *
0x180011d86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011d8b  mov     eax, ebx
0x180011d8d  jmp     short loc_180011DC3
0x180011d8f  jmp     short loc_180011DC1
0x180011d91  mov     ebx, eax
0x180011d93  test    eax, eax
0x180011d95  jle     short loc_180011DA0
0x180011d97  movzx   ebx, ax
0x180011d9a  or      ebx, 80070000h
0x180011da0  test    ebx, ebx
0x180011da2  jns     short loc_180011DC1
0x180011da4  mov     rcx, [rsp+48h]; this
0x180011da9  mov     r9d, ebx; char *
0x180011dac  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x180011db3  mov     edx, 186h; void *
0x180011db8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011dbd  mov     eax, ebx
0x180011dbf  jmp     short loc_180011DC3
0x180011dc1  xor     eax, eax
0x180011dc3  add     rsp, 40h
0x180011dc7  pop     rbx
0x180011dc8  retn
0x180014350  push    rbp
0x180014352  sub     rsp, 30h
0x180014356  mov     rbp, rdx
0x180014359  mov     rcx, [rcx]
0x18001435c  mov     ecx, [rcx]; ExceptionCode
0x18001435e  call    cs:__imp_I_RpcExceptionFilter
0x180014364  nop
0x180014365  add     rsp, 30h
0x180014369  pop     rbp
0x18001436a  retn
```
