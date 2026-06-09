# _CMidi2MidiSrv::UpdateConfiguration_::_36_::_lambda_1_::operator()

- ea: `0x1800121c4`
- end: `0x18001237e`
- name: `_CMidi2MidiSrv::UpdateConfiguration_::_36_::_lambda_1_::operator()`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013bf4`

## callees

- `0x18000163c`
- `0x180002470`
- `0x180007e24`
- `0x180009bf8`
- `0x1800121c4`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18001435e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001435e`
- `RPCRT4!NdrClientCall3` at `0x18001221e`
- `RPCRT4!NdrClientCall3` at `0x18001221e`

## string_xrefs

- `0x1800122f5`: `Completed RPC call`
- `0x180012323`: `CMidi2MidiSrv::UpdateConfiguration::<lambda_1>::operator ()`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrv::UpdateConfiguration_::_36_::_lambda_1_::operator()(__int64 a1)
{
  __int64 v2; // rdx
  _QWORD *v3; // rax
  int v4; // r14d
  CLIENT_CALL_RETURN v5; // rax
  unsigned int Pointer; // ebx
  _DWORD *v8; // r10
  __int64 *v9; // rcx
  __int64 v10; // rax
  int v11; // [rsp+20h] [rbp-B8h]
  __int64 v12; // [rsp+30h] [rbp-A8h] BYREF
  CLIENT_CALL_RETURN v13; // [rsp+38h] [rbp-A0h]
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+40h] [rbp-98h] BYREF
  const char *v15; // [rsp+60h] [rbp-78h]
  __int64 v16; // [rsp+68h] [rbp-70h]
  __int64 *v17; // [rsp+70h] [rbp-68h]
  __int64 v18; // [rsp+78h] [rbp-60h]
  const wchar_t *v19; // [rsp+80h] [rbp-58h]
  __int64 v20; // [rsp+88h] [rbp-50h]
  __int64 *v21; // [rsp+90h] [rbp-48h]
  int v22; // [rsp+98h] [rbp-40h]
  int v23; // [rsp+9Ch] [rbp-3Ch]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v12 = a1;
  v2 = **(_QWORD **)(a1 + 8);
  v3 = *(_QWORD **)a1;
  v13.Simple = 0;
  v11 = v2;
  v4 = 2;
  v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&MidiSrvRPC_ProxyInfo, 2u, 0, *v3).Pointer;
  Pointer = (unsigned int)v5.Pointer;
  v13.Pointer = v5.Pointer;
  if ( SLODWORD(v5.Simple) >= 0 )
  {
    v8 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
    if ( *v8 > 4u )
    {
      v9 = **(__int64 ***)(a1 + 8);
      v12 = *(_QWORD *)(a1 + 24);
      if ( v9 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *((_WORD *)v9 + v10) );
        v4 = 2 * v10 + 2;
      }
      else
      {
        v9 = qword_180017FF0;
      }
      v21 = v9;
      v22 = v4;
      v23 = 0;
      v19 = L"Completed RPC call";
      v20 = 38;
      v17 = &v12;
      v18 = 8;
      v15 = "CMidi2MidiSrv::UpdateConfiguration::<lambda_1>::operator ()";
      v16 = 60;
      tlgWriteTransfer_EventWriteTransfer((__int64)v8, (unsigned __int8 *)byte_18001AA4D, 0, 0, 6u, &v14);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x229,
      (unsigned int)"avcore\\midi2\\libs\\midisrvtransportlib\\midisrvtransport.cpp",
      (const char *)LODWORD(v5.Pointer),
      v11);
    return Pointer;
  }
}

```

## disassembly

```asm
0x1800121c4  push    rbx
0x1800121c6  push    rsi
0x1800121c7  push    rdi
0x1800121c8  push    r14
0x1800121ca  sub     rsp, 0B8h
0x1800121d1  mov     rax, cs:__security_cookie
0x1800121d8  xor     rax, rsp
0x1800121db  mov     [rsp+0D8h+var_38], rax
0x1800121e3  mov     rdi, rcx
0x1800121e6  mov     [rsp+0D8h+var_A8], rcx
0x1800121eb  mov     r8, [rcx+10h]
0x1800121ef  mov     rax, [rcx+8]
0x1800121f3  mov     rdx, [rax]
0x1800121f6  mov     rax, [rcx]
0x1800121f9  xor     esi, esi
0x1800121fb  mov     [rsp+0D8h+var_A0], rsi
0x180012200  mov     [rsp+0D8h+var_B0], r8
0x180012205  mov     qword ptr [rsp+0D8h+var_B8], rdx; int
0x18001220a  mov     r9, [rax]
0x18001220d  xor     r8d, r8d; pReturnValue
0x180012210  lea     r14d, [rsi+2]
0x180012214  mov     edx, r14d; nProcNum
0x180012217  lea     rcx, ?MidiSrvRPC_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001221e  call    cs:__imp_NdrClientCall3
0x180012224  mov     rbx, rax
0x180012227  mov     [rsp+0D8h+var_A0], rax
0x18001222c  test    eax, eax
0x18001222e  jns     short loc_180012253
0x180012230  mov     rcx, [rsp+0D8h]; this
0x180012238  mov     r9d, ebx; char *
0x18001223b  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x180012242  mov     edx, 229h; void *
0x180012247  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001224c  mov     eax, ebx
0x18001224e  jmp     loc_180012361
0x180012253  jmp     short loc_180012296
0x180012255  mov     ebx, eax
0x180012257  test    eax, eax
0x180012259  jle     short loc_180012264
0x18001225b  movzx   ebx, ax
0x18001225e  or      ebx, 80070000h
0x180012264  test    ebx, ebx
0x180012266  jns     short loc_18001228B
0x180012268  mov     rcx, [rsp+0D8h]; this
0x180012270  mov     r9d, ebx; char *
0x180012273  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x18001227a  mov     edx, 229h; void *
0x18001227f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012284  mov     eax, ebx
0x180012286  jmp     loc_180012361
0x18001228b  xor     esi, esi
0x18001228d  lea     r14d, [rsi+2]
0x180012291  mov     rdi, [rsp+0D8h+var_A8]
0x180012296  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18001229b  mov     r10, [rax+8]
0x18001229f  mov     eax, [r10]
0x1800122a2  cmp     eax, 4
0x1800122a5  jbe     loc_18001235F
0x1800122ab  mov     rax, [rdi+8]
0x1800122af  mov     rcx, [rax]
0x1800122b2  mov     rax, [rdi+18h]
0x1800122b6  mov     [rsp+0D8h+var_A8], rax
0x1800122bb  test    rcx, rcx
0x1800122be  jz      short loc_1800122D7
0x1800122c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800122c4  inc     rax
0x1800122c7  cmp     [rcx+rax*2], si
0x1800122cb  jnz     short loc_1800122C4
0x1800122cd  lea     r14d, ds:2[rax*2]
0x1800122d5  jmp     short loc_1800122DE
0x1800122d7  lea     rcx, qword_180017FF0
0x1800122de  mov     [rsp+0D8h+var_48], rcx
0x1800122e6  mov     [rsp+0D8h+var_40], r14d
0x1800122ee  mov     [rsp+0D8h+var_3C], esi
0x1800122f5  lea     rax, aCompletedRpcCa; "Completed RPC call"
0x1800122fc  mov     [rsp+0D8h+var_58], rax
0x180012304  mov     [rsp+0D8h+var_50], 26h ; '&'
0x180012310  lea     rax, [rsp+0D8h+var_A8]
0x180012315  mov     [rsp+0D8h+var_68], rax
0x18001231a  mov     [rsp+0D8h+var_60], 8
0x180012323  lea     rax, aCmidi2midisrvU_0; "CMidi2MidiSrv::UpdateConfiguration::<la"...
0x18001232a  mov     [rsp+0D8h+var_78], rax
0x18001232f  mov     [rsp+0D8h+var_70], 3Ch ; '<'
0x180012338  lea     rax, [rsp+0D8h+var_98]
0x18001233d  mov     [rsp+0D8h+var_B0], rax
0x180012342  mov     [rsp+0D8h+var_B8], 6
0x18001234a  xor     r9d, r9d
0x18001234d  xor     r8d, r8d
0x180012350  lea     rdx, byte_18001AA4D
0x180012357  mov     rcx, r10
0x18001235a  call    _tlgWriteTransfer_EventWriteTransfer
0x18001235f  xor     eax, eax
0x180012361  mov     rcx, [rsp+0D8h+var_38]
0x180012369  xor     rcx, rsp; StackCookie
0x18001236c  call    __security_check_cookie
0x180012371  add     rsp, 0B8h
0x180012378  pop     r14
0x18001237a  pop     rdi
0x18001237b  pop     rsi
0x18001237c  pop     rbx
0x18001237d  retn
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
