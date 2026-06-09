# _CMidi2MidiSrv::UpdateClientSessionName_::_26_::_lambda_1_::operator()

- ea: `0x180012064`
- end: `0x18001211c`
- name: `_CMidi2MidiSrv::UpdateClientSessionName_::_26_::_lambda_1_::operator()`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180013a3c`

## callees

- `0x180007e24`
- `0x180012064`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800120b3`
- `RPCRT4!NdrClientCall3` at `0x1800120b3`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrv::UpdateClientSessionName_::_26_::_lambda_1_::operator()(_QWORD **a1)
{
  int Pointer; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = *a1[1];
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&MidiSrvRPC_ProxyInfo, 4u, 0, **a1).Pointer;
  v2 = Pointer;
  if ( Pointer >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x163,
    (unsigned int)"avcore\\midi2\\libs\\midisrvtransportlib\\midisrvtransport.cpp",
    (const char *)(unsigned int)Pointer,
    v4);
  return v2;
}

```

## disassembly

```asm
0x180012064  mov     r11, rsp
0x180012067  push    rbx
0x180012068  sub     rsp, 50h
0x18001206c  mov     rax, [rcx+18h]
0x180012070  mov     r8, [rax]
0x180012073  mov     rdx, [rcx+10h]
0x180012077  mov     rax, [rcx+8]
0x18001207b  mov     r9, [rax]
0x18001207e  mov     rax, [rcx]
0x180012081  mov     qword ptr [r11+10h], 0
0x180012089  movups  xmm0, xmmword ptr [rdx]
0x18001208c  movdqu  [rsp+58h+var_18], xmm0
0x180012092  mov     [r11-28h], r8
0x180012096  lea     rcx, [r11-18h]
0x18001209a  mov     [r11-30h], rcx
0x18001209e  mov     [r11-38h], r9
0x1800120a2  mov     r9, [rax]
0x1800120a5  xor     r8d, r8d; pReturnValue
0x1800120a8  lea     edx, [r8+4]; nProcNum
0x1800120ac  lea     rcx, ?MidiSrvRPC_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800120b3  call    cs:__imp_NdrClientCall3
0x1800120b9  mov     rbx, rax
0x1800120bc  mov     [rsp+58h+arg_8], rax
0x1800120c1  test    eax, eax
0x1800120c3  jns     short loc_1800120E2
0x1800120c5  mov     rcx, [rsp+58h]; this
0x1800120ca  mov     r9d, ebx; char *
0x1800120cd  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x1800120d4  mov     edx, 163h; void *
0x1800120d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800120de  mov     eax, ebx
0x1800120e0  jmp     short loc_180012116
0x1800120e2  jmp     short loc_180012114
0x1800120e4  mov     ebx, eax
0x1800120e6  test    eax, eax
0x1800120e8  jle     short loc_1800120F3
0x1800120ea  movzx   ebx, ax
0x1800120ed  or      ebx, 80070000h
0x1800120f3  test    ebx, ebx
0x1800120f5  jns     short loc_180012114
0x1800120f7  mov     rcx, [rsp+58h]; this
0x1800120fc  mov     r9d, ebx; char *
0x1800120ff  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x180012106  mov     edx, 163h; void *
0x18001210b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012110  mov     eax, ebx
0x180012112  jmp     short loc_180012116
0x180012114  xor     eax, eax
0x180012116  add     rsp, 50h
0x18001211a  pop     rbx
0x18001211b  retn
0x180014372  push    rbp
0x180014374  sub     rsp, 40h
0x180014378  mov     rbp, rdx
0x18001437b  mov     rcx, [rcx]
0x18001437e  mov     ecx, [rcx]; ExceptionCode
0x180014380  call    cs:__imp_I_RpcExceptionFilter
0x180014386  nop
0x180014387  add     rsp, 40h
0x18001438b  pop     rbp
0x18001438c  retn
```
