# sndOpenSound

- ea: `0x18001ccd0`
- end: `0x18001ce06`
- name: `sndOpenSound`
- size: `310`
- prototype: `LONG __stdcall(LPCWSTR EventName, LPCWSTR AppName, INT32 Flags, PHANDLE FileHandle)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001ccd0`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001cd4d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001cd4d`
- `RPCRT4!RpcBindingFree` at `0x18001cdd1`
- `RPCRT4!RpcBindingFree` at `0x18001cdd1`
- `RPCRT4!NdrClientCall3` at `0x18001cd96`
- `RPCRT4!NdrClientCall3` at `0x18001cd96`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001cd33`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001cd33`
- `RPCRT4!RpcStringFreeW` at `0x18001cde4`
- `RPCRT4!RpcStringFreeW` at `0x18001cde4`

## pseudocode

```c
LONG __stdcall sndOpenSound(LPCWSTR EventName, LPCWSTR AppName, INT32 Flags, PHANDLE FileHandle)
{
  RPC_STATUS Pointer; // ebx
  CLIENT_CALL_RETURN v9; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-40h] BYREF
  RPC_WSTR StringBinding; // [rsp+60h] [rbp-38h] BYREF
  void *v13; // [rsp+68h] [rbp-30h] BYREF
  CLIENT_CALL_RETURN v14; // [rsp+70h] [rbp-28h]

  StringBinding = 0;
  Binding = 0;
  v13 = 0;
  Pointer = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"Audiosrv", 0, &StringBinding);
  if ( !Pointer )
  {
    Pointer = RpcBindingFromStringBindingW(StringBinding, &Binding);
    if ( !Pointer )
    {
      v14.Simple = 0;
      v9.Pointer = NdrClientCall3(
                     (MIDL_STUBLESS_PROXY_INFO *)&AudioSrv_ProxyInfo,
                     8u,
                     0,
                     Binding,
                     EventName,
                     AppName,
                     Flags,
                     &v13,
                     0).Pointer;
      Pointer = (RPC_STATUS)v9.Pointer;
      v14.Pointer = v9.Pointer;
      if ( !LODWORD(v9.Pointer) )
        *FileHandle = v13;
    }
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return Pointer;
}

```

## disassembly

```asm
0x18001ccd0  mov     r11, rsp
0x18001ccd3  mov     [r11+8], rbx
0x18001ccd7  mov     [r11+10h], rsi
0x18001ccdb  mov     [r11+20h], r9
0x18001ccdf  push    r12
0x18001cce1  push    r14
0x18001cce3  push    r15
0x18001cce5  sub     rsp, 80h
0x18001ccec  mov     rsi, r9
0x18001ccef  mov     r14d, r8d
0x18001ccf2  mov     r15, rdx
0x18001ccf5  mov     r12, rcx
0x18001ccf8  mov     qword ptr [r11-38h], 0
0x18001cd00  mov     qword ptr [r11-40h], 0
0x18001cd08  mov     qword ptr [r11-30h], 0
0x18001cd10  lea     rax, [r11-38h]
0x18001cd14  mov     [r11-70h], rax
0x18001cd18  mov     qword ptr [r11-78h], 0
0x18001cd20  lea     r9, Endpoint; "Audiosrv"
0x18001cd27  xor     r8d, r8d; NetworkAddr
0x18001cd2a  lea     rdx, ProtSeq; "ncalrpc"
0x18001cd31  xor     ecx, ecx; ObjUuid
0x18001cd33  call    cs:__imp_RpcStringBindingComposeW
0x18001cd39  mov     ebx, eax
0x18001cd3b  test    eax, eax
0x18001cd3d  jnz     loc_18001CDC4
0x18001cd43  lea     rdx, [rsp+98h+Binding]; Binding
0x18001cd48  mov     rcx, [rsp+98h+StringBinding]; StringBinding
0x18001cd4d  call    cs:__imp_RpcBindingFromStringBindingW
0x18001cd53  mov     ebx, eax
0x18001cd55  test    eax, eax
0x18001cd57  jnz     short loc_18001CDC4
0x18001cd59  mov     [rsp+98h+var_28], 0
0x18001cd62  mov     [rsp+98h+var_58], 0
0x18001cd6b  lea     rax, [rsp+98h+var_30]
0x18001cd70  mov     [rsp+98h+var_60], rax
0x18001cd75  mov     [rsp+98h+var_68], r14d
0x18001cd7a  mov     [rsp+98h+var_70], r15
0x18001cd7f  mov     [rsp+98h+var_78], r12
0x18001cd84  mov     r9, [rsp+98h+Binding]
0x18001cd89  xor     r8d, r8d; pReturnValue
0x18001cd8c  lea     edx, [rbx+8]; nProcNum
0x18001cd8f  lea     rcx, ?AudioSrv_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001cd96  call    cs:__imp_NdrClientCall3
0x18001cd9c  mov     rbx, rax
0x18001cd9f  mov     [rsp+98h+var_28], rax
0x18001cda4  mov     [rsp+98h+var_48], eax
0x18001cda8  jmp     short loc_18001CDB8
0x18001cdaa  mov     ebx, eax
0x18001cdac  mov     [rsp+98h+var_48], eax
0x18001cdb0  mov     rsi, [rsp+98h+arg_18]
0x18001cdb8  test    ebx, ebx
0x18001cdba  jnz     short loc_18001CDC4
0x18001cdbc  mov     rax, [rsp+98h+var_30]
0x18001cdc1  mov     [rsi], rax
0x18001cdc4  cmp     [rsp+98h+Binding], 0
0x18001cdca  jz      short loc_18001CDD7
0x18001cdcc  lea     rcx, [rsp+98h+Binding]; Binding
0x18001cdd1  call    cs:__imp_RpcBindingFree
0x18001cdd7  cmp     [rsp+98h+StringBinding], 0
0x18001cddd  jz      short loc_18001CDEA
0x18001cddf  lea     rcx, [rsp+98h+StringBinding]; String
0x18001cde4  call    cs:__imp_RpcStringFreeW
0x18001cdea  mov     eax, ebx
0x18001cdec  lea     r11, [rsp+98h+var_18]
0x18001cdf4  mov     rbx, [r11+20h]
0x18001cdf8  mov     rsi, [r11+28h]
0x18001cdfc  mov     rsp, r11
0x18001cdff  pop     r15
0x18001ce01  pop     r14
0x18001ce03  pop     r12
0x18001ce05  retn
```
