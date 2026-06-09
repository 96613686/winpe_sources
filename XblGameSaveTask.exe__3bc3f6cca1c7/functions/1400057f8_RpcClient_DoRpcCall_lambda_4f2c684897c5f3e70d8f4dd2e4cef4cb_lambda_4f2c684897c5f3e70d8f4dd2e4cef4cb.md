# RpcClient::DoRpcCall<_lambda_4f2c684897c5f3e70d8f4dd2e4cef4cb_>(_lambda_4f2c684897c5f3e70d8f4dd2e4cef4cb_)

- ea: `0x1400057f8`
- end: `0x1400058ce`
- name: `??$DoRpcCall@V_lambda_4f2c684897c5f3e70d8f4dd2e4cef4cb_@@@RpcClient@@IEAAJV_lambda_4f2c684897c5f3e70d8f4dd2e4cef4cb_@@@Z`
- size: `214`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, RpcClient **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000607c`

## callees

- `0x140004704`
- `0x1400057f8`
- `0x140005ca0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005833`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000587f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005833`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000587f`
- `RPCRT4!NdrClientCall3` at `0x1400058a2`
- `RPCRT4!NdrClientCall3` at `0x1400058a2`
- `RPCRT4!I_RpcExceptionFilter` at `0x1400065dc`
- `RPCRT4!I_RpcExceptionFilter` at `0x1400065dc`

## string_xrefs

- `0x140005845`: `onecoreuap\xbox\ConnectedStorage\common\rpcclient.h`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall RpcClient::DoRpcCall<_lambda_4f2c684897c5f3e70d8f4dd2e4cef4cb_>(
        __int64 a1,
        RpcClient **a2)
{
  DWORD v3; // eax
  const char *v4; // r9
  RPC_BINDING_HANDLE v5; // rax
  RpcClient *v7; // rcx
  void **v8; // rbx
  DWORD BindingHandle; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( Binding
    || ((v3 = RpcClient::CreateBindingHandle((RpcClient *)&g_rpcClient, &Binding)) != 0
      ? (SetLastError(v3), v5 = 0)
      : (v5 = Binding),
        v5) )
  {
    v7 = *a2;
    v8 = (void **)((char *)*a2 + 8);
    if ( !*v8 )
    {
      BindingHandle = RpcClient::CreateBindingHandle(v7, v8);
      if ( BindingHandle )
        SetLastError(BindingHandle);
    }
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0);
  }
  else
  {
    return (CLIENT_CALL_RETURN)wil::details::in1diag3::Return_GetLastError(
                                 retaddr,
                                 (void *)0x31,
                                 (unsigned int)"onecoreuap\\xbox\\ConnectedStorage\\common\\rpcclient.h",
                                 v4);
  }
}

```

## disassembly

```asm
0x1400057f8  mov     [rsp+arg_8], rbx
0x1400057fd  push    rdi
0x1400057fe  sub     rsp, 40h
0x140005802  mov     rbx, rdx
0x140005805  mov     rax, cs:Binding
0x14000580c  test    rax, rax
0x14000580f  jnz     short loc_140005856
0x140005811  lea     rdx, Binding; void **
0x140005818  lea     rcx, ?g_rpcClient@@3VXblGameSaveRpc@@A; this
0x14000581f  call    ?CreateBindingHandle@RpcClient@@IEAAKPEAPEAX@Z; RpcClient::CreateBindingHandle(void * *)
0x140005824  test    eax, eax
0x140005826  jnz     short loc_140005831
0x140005828  mov     rax, cs:Binding
0x14000582f  jmp     short loc_14000583B
0x140005831  mov     ecx, eax; dwErrCode
0x140005833  call    cs:__imp_SetLastError
0x140005839  xor     eax, eax
0x14000583b  test    rax, rax
0x14000583e  jnz     short loc_140005856
0x140005840  mov     rcx, [rsp+48h]; this
0x140005845  lea     r8, aOnecoreuapXbox; "onecoreuap\\xbox\\ConnectedStorage\\com"...
0x14000584c  lea     edx, [rax+31h]; void *
0x14000584f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005854  jmp     short loc_1400058C3
0x140005856  mov     rax, [rbx+8]
0x14000585a  mov     rdi, [rax]
0x14000585d  mov     rcx, [rbx]; this
0x140005860  lea     rbx, [rcx+8]
0x140005864  mov     r9, [rbx]
0x140005867  test    r9, r9
0x14000586a  jnz     short loc_140005888
0x14000586c  mov     rdx, rbx; void **
0x14000586f  call    ?CreateBindingHandle@RpcClient@@IEAAKPEAPEAX@Z; RpcClient::CreateBindingHandle(void * *)
0x140005874  test    eax, eax
0x140005876  jnz     short loc_14000587D
0x140005878  mov     r9, [rbx]
0x14000587b  jmp     short loc_140005888
0x14000587d  mov     ecx, eax; dwErrCode
0x14000587f  call    cs:__imp_SetLastError
0x140005885  xor     r9d, r9d
0x140005888  mov     [rsp+48h+arg_0], 0
0x140005891  mov     [rsp+48h+var_28], rdi
0x140005896  xor     r8d, r8d; pReturnValue
0x140005899  xor     edx, edx; nProcNum
0x14000589b  lea     rcx, pProxyInfo; pProxyInfo
0x1400058a2  call    cs:__imp_NdrClientCall3
0x1400058a8  mov     [rsp+48h+arg_0], rax
0x1400058ad  mov     [rsp+48h+var_18], eax
0x1400058b1  jmp     short loc_1400058C3
0x1400058b3  test    eax, eax
0x1400058b5  jle     short loc_1400058BF
0x1400058b7  movzx   eax, ax
0x1400058ba  or      eax, 80070000h
0x1400058bf  mov     [rsp+48h+var_18], eax
0x1400058c3  mov     rbx, [rsp+48h+arg_8]
0x1400058c8  add     rsp, 40h
0x1400058cc  pop     rdi
0x1400058cd  retn
0x1400065ce  push    rbp
0x1400065d0  sub     rsp, 30h
0x1400065d4  mov     rbp, rdx
0x1400065d7  mov     rcx, [rcx]
0x1400065da  mov     ecx, [rcx]; ExceptionCode
0x1400065dc  call    cs:__imp_I_RpcExceptionFilter
0x1400065e2  nop
0x1400065e3  add     rsp, 30h
0x1400065e7  pop     rbp
0x1400065e8  retn
```
