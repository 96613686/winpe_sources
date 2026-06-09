# RetrieveFileInfoFromRpc(ushort const *,_FILE_INFO *)

- ea: `0x180027900`
- end: `0x180027bf8`
- name: `?RetrieveFileInfoFromRpc@@YAJPEBGPEAU_FILE_INFO@@@Z`
- size: `760`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180017fe0`

## callees

- `0x180005890`
- `0x180006938`
- `0x18000cb30`
- `0x180027900`
- `0x180029284`
- `0x1800295dc`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180027bc7`
- `RPCRT4!RpcBindingFree` at `0x180027bc7`
- `RPCRT4!RpcEpResolveBinding` at `0x180027a1f`
- `RPCRT4!RpcEpResolveBinding` at `0x180027a1f`
- `RPCRT4!RpcStringFreeW` at `0x1800279fa`
- `RPCRT4!RpcStringFreeW` at `0x1800279fa`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800279ed`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800279ed`
- `RPCRT4!RpcStringBindingComposeW` at `0x180027984`
- `RPCRT4!RpcStringBindingComposeW` at `0x180027984`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800e6463`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800e6463`
- `RPCRT4!NdrClientCall3` at `0x180027a99`
- `RPCRT4!NdrClientCall3` at `0x180027a99`

## string_xrefs

- `0x180027aeb`: `StringCchCopyW [%#x]`
- `0x180027b28`: `StringCchCopyW [%#x]`
- `0x180027990`: `RpcStringBindingCompose failed [%d]`

## pseudocode

```c
__int64 __fastcall RetrieveFileInfoFromRpc(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  int started; // eax
  int Pointer; // ebx
  const char *v6; // r9
  __int64 v7; // r8
  CLIENT_CALL_RETURN v8; // rax
  int v9; // eax
  unsigned __int64 v10; // r11
  int v11; // eax
  RPC_WSTR Options; // [rsp+20h] [rbp-128h]
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp-100h] BYREF
  RPC_WSTR String; // [rsp+50h] [rbp-F8h] BYREF
  CLIENT_CALL_RETURN v16; // [rsp+58h] [rbp-F0h]
  unsigned __int16 v17[48]; // [rsp+60h] [rbp-E8h] BYREF
  unsigned __int16 v18[48]; // [rsp+C0h] [rbp-88h] BYREF

  String = 0;
  Binding = 0;
  started = Windows::Compat::Inventory::RpcHelper::StartInventorySvc();
  if ( started < 0 )
    AslLogCallPrintf(3, "RetrieveFileInfoFromRpc", 445, "StartInventorySvc failed %#x", started);
  Pointer = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
  if ( Pointer )
  {
    v6 = "RpcStringBindingCompose failed [%d]";
    v7 = 456;
    goto LABEL_5;
  }
  Pointer = RpcBindingFromStringBindingW(String, &Binding);
  RpcStringFreeW(&String);
  if ( Pointer )
  {
    v6 = "RpcBindingFromStringBinding failed: [%d]";
    v7 = 465;
    goto LABEL_5;
  }
  Pointer = RpcEpResolveBinding(Binding, qword_1800EE790);
  if ( Pointer )
  {
    v6 = "RpcEpResolveBinding failed: %d";
    v7 = 473;
LABEL_5:
    LODWORD(Options) = Pointer;
    AslLogCallPrintf(1, "RetrieveFileInfoFromRpc", v7, v6, Options);
    if ( Pointer > 0 )
      Pointer = (unsigned __int16)Pointer | 0x80070000;
    goto LABEL_20;
  }
  memset_0(v17, 0, 0x5Au);
  memset_0(v18, 0, 0x5Au);
  v16.Simple = 0;
  v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&InvSvcAppInv_ProxyInfo, 1u, 0, Binding, a1, v17, v18).Pointer;
  Pointer = (int)v8.Pointer;
  v16.Pointer = v8.Pointer;
  if ( SLODWORD(v8.Simple) < 0 )
  {
    AslLogCallPrintf(
      1,
      "RetrieveFileInfoFromRpc",
      508,
      "RAiPicRetrieveFileSimpleInfo failed: [%#x]",
      LODWORD(v8.Pointer));
  }
  else if ( v17[0] && v18[0] )
  {
    v9 = StringCchCopyW(a2[1], 0x2Du, v17);
    Pointer = v9;
    if ( v9 >= 0 )
    {
      v11 = StringCchCopyW(*a2, v10, v18);
      Pointer = v11;
      if ( v11 < 0 )
        AslLogCallPrintf(1, "RetrieveFileInfoFromRpc", 502, "StringCchCopyW [%#x]", v11);
    }
    else
    {
      AslLogCallPrintf(1, "RetrieveFileInfoFromRpc", 496, "StringCchCopyW [%#x]", v9);
    }
  }
  else
  {
    Pointer = -2147467259;
    AslLogCallPrintf(
      1,
      "RetrieveFileInfoFromRpc",
      489,
      "RAiPicRetrieveFileSimpleInfo returned empty ID: [%#x]",
      -2147467259);
  }
LABEL_20:
  if ( Binding )
    RpcBindingFree(&Binding);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180027900  mov     [rsp+arg_10], rbx
0x180027905  mov     [rsp+arg_18], rsi
0x18002790a  push    rdi
0x18002790b  push    r14
0x18002790d  push    r15
0x18002790f  sub     rsp, 130h
0x180027916  mov     rax, cs:__security_cookie
0x18002791d  xor     rax, rsp
0x180027920  mov     [rsp+148h+var_28], rax
0x180027928  mov     r15, rdx
0x18002792b  mov     rsi, rcx
0x18002792e  xor     edi, edi
0x180027930  mov     [rsp+148h+String], rdi
0x180027935  mov     [rsp+148h+Binding], rdi
0x18002793a  call    ?StartInventorySvc@RpcHelper@Inventory@Compat@Windows@@SAJXZ; Windows::Compat::Inventory::RpcHelper::StartInventorySvc(void)
0x18002793f  lea     r14, aRetrievefilein_0; "RetrieveFileInfoFromRpc"
0x180027946  test    eax, eax
0x180027948  jns     short loc_180027966
0x18002794a  mov     dword ptr [rsp+148h+Options], eax
0x18002794e  lea     r9, aStartinventory; "StartInventorySvc failed %#x"
0x180027955  mov     r8d, 1BDh
0x18002795b  mov     rdx, r14
0x18002795e  lea     ecx, [rdi+3]
0x180027961  call    AslLogCallPrintf
0x180027966  lea     rax, [rsp+148h+String]
0x18002796b  mov     [rsp+148h+StringBinding], rax; StringBinding
0x180027970  mov     [rsp+148h+Options], rdi; Options
0x180027975  xor     r9d, r9d; Endpoint
0x180027978  xor     r8d, r8d; NetworkAddr
0x18002797b  lea     rdx, ProtSeq; "ncalrpc"
0x180027982  xor     ecx, ecx; ObjUuid
0x180027984  call    cs:__imp_RpcStringBindingComposeW
0x18002798a  mov     ebx, eax
0x18002798c  test    eax, eax
0x18002798e  jz      short loc_1800279E3
0x180027990  lea     r9, aRpcstringbindi_0; "RpcStringBindingCompose failed [%d]"
0x180027997  mov     r8d, 1C8h
0x18002799d  mov     dword ptr [rsp+148h+Options], ebx
0x1800279a1  mov     rdx, r14
0x1800279a4  mov     ecx, 1
0x1800279a9  call    AslLogCallPrintf
0x1800279ae  movzx   ecx, bx
0x1800279b1  test    ebx, ebx
0x1800279b3  jg      short loc_1800279B9
0x1800279b5  mov     eax, ebx
0x1800279b7  jmp     short loc_1800279C0
0x1800279b9  mov     eax, ecx
0x1800279bb  or      eax, 80070000h
0x1800279c0  test    eax, eax
0x1800279c2  jns     short loc_1800279D9
0x1800279c4  test    ebx, ebx
0x1800279c6  jle     loc_180027BBB
0x1800279cc  mov     ebx, ecx
0x1800279ce  or      ebx, 80070000h
0x1800279d4  jmp     loc_180027BBB
0x1800279d9  mov     ebx, 80004005h
0x1800279de  jmp     loc_180027BBB
0x1800279e3  lea     rdx, [rsp+148h+Binding]; Binding
0x1800279e8  mov     rcx, [rsp+148h+String]; StringBinding
0x1800279ed  call    cs:__imp_RpcBindingFromStringBindingW
0x1800279f3  mov     ebx, eax
0x1800279f5  lea     rcx, [rsp+148h+String]; String
0x1800279fa  call    cs:__imp_RpcStringFreeW
0x180027a00  test    ebx, ebx
0x180027a02  jz      short loc_180027A13
0x180027a04  lea     r9, aRpcbindingfrom_0; "RpcBindingFromStringBinding failed: [%d"...
0x180027a0b  mov     r8d, 1D1h
0x180027a11  jmp     short loc_18002799D
0x180027a13  lea     rdx, qword_1800EE790; IfSpec
0x180027a1a  mov     rcx, [rsp+148h+Binding]; Binding
0x180027a1f  call    cs:__imp_RpcEpResolveBinding
0x180027a25  mov     ebx, eax
0x180027a27  test    eax, eax
0x180027a29  jz      short loc_180027A3D
0x180027a2b  lea     r9, aRpcepresolvebi_0; "RpcEpResolveBinding failed: %d"
0x180027a32  mov     r8d, 1D9h
0x180027a38  jmp     loc_18002799D
0x180027a3d  mov     ebx, 5Ah ; 'Z'
0x180027a42  mov     r8d, ebx; Size
0x180027a45  xor     edx, edx; Val
0x180027a47  lea     rcx, [rsp+148h+var_E8]; void *
0x180027a4c  call    memset_0
0x180027a51  mov     r8d, ebx; Size
0x180027a54  xor     edx, edx; Val
0x180027a56  lea     rcx, [rsp+148h+var_88]; void *
0x180027a5e  call    memset_0
0x180027a63  nop
0x180027a64  mov     [rsp+148h+var_F0], rdi
0x180027a69  lea     rax, [rsp+148h+var_88]
0x180027a71  mov     [rsp+148h+var_118], rax
0x180027a76  lea     rax, [rsp+148h+var_E8]
0x180027a7b  mov     [rsp+148h+StringBinding], rax
0x180027a80  mov     [rsp+148h+Options], rsi
0x180027a85  mov     r9, [rsp+148h+Binding]
0x180027a8a  xor     r8d, r8d; pReturnValue
0x180027a8d  lea     esi, [rbx-59h]
0x180027a90  mov     edx, esi; nProcNum
0x180027a92  lea     rcx, ?InvSvcAppInv_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180027a99  call    cs:__imp_NdrClientCall3
0x180027a9f  mov     rbx, rax
0x180027aa2  mov     [rsp+148h+var_F0], rax
0x180027aa7  mov     [rsp+148h+var_108], eax
0x180027aab  test    eax, eax
0x180027aad  js      loc_180027B67
0x180027ab3  cmp     [rsp+148h+var_E8], di
0x180027ab8  jz      loc_180027B41
0x180027abe  cmp     [rsp+148h+var_88], di
0x180027ac6  jz      short loc_180027B41
0x180027ac8  lea     r8, [rsp+148h+var_E8]; unsigned __int16 *
0x180027acd  lea     r11d, [rsi+2Ch]
0x180027ad1  mov     edx, r11d; unsigned __int64
0x180027ad4  mov     rcx, [r15+8]; unsigned __int16 *
0x180027ad8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027add  mov     ebx, eax
0x180027adf  mov     [rsp+148h+var_108], eax
0x180027ae3  test    eax, eax
0x180027ae5  jns     short loc_180027B07
0x180027ae7  mov     dword ptr [rsp+148h+Options], eax
0x180027aeb  lea     r9, aStringcchcopyw_0; "StringCchCopyW [%#x]"
0x180027af2  mov     r8d, 1F0h
0x180027af8  mov     rdx, r14
0x180027afb  mov     ecx, esi
0x180027afd  call    AslLogCallPrintf
0x180027b02  jmp     loc_180027BBB
0x180027b07  lea     r8, [rsp+148h+var_88]; unsigned __int16 *
0x180027b0f  mov     rdx, r11; unsigned __int64
0x180027b12  mov     rcx, [r15]; unsigned __int16 *
0x180027b15  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027b1a  mov     ebx, eax
0x180027b1c  mov     [rsp+148h+var_108], eax
0x180027b20  test    eax, eax
0x180027b22  jns     short loc_180027B82
0x180027b24  mov     dword ptr [rsp+148h+Options], eax
0x180027b28  lea     r9, aStringcchcopyw_0; "StringCchCopyW [%#x]"
0x180027b2f  mov     r8d, 1F6h
0x180027b35  mov     rdx, r14
0x180027b38  mov     ecx, esi
0x180027b3a  call    AslLogCallPrintf
0x180027b3f  jmp     short loc_180027BBB
0x180027b41  mov     ebx, 80004005h
0x180027b46  mov     [rsp+148h+var_108], ebx
0x180027b4a  mov     dword ptr [rsp+148h+Options], ebx
0x180027b4e  lea     r9, aRaipicretrieve_0; "RAiPicRetrieveFileSimpleInfo returned e"...
0x180027b55  mov     r8d, 1E9h
0x180027b5b  mov     rdx, r14
0x180027b5e  mov     ecx, esi
0x180027b60  call    AslLogCallPrintf
0x180027b65  jmp     short loc_180027BBB
0x180027b67  mov     dword ptr [rsp+148h+Options], eax
0x180027b6b  lea     r9, aRaipicretrieve; "RAiPicRetrieveFileSimpleInfo failed: [%"...
0x180027b72  mov     r8d, 1FCh
0x180027b78  mov     rdx, r14
0x180027b7b  mov     ecx, esi
0x180027b7d  call    AslLogCallPrintf
0x180027b82  jmp     short loc_180027BBB
0x180027b84  mov     ebx, eax
0x180027b86  mov     dword ptr [rsp+148h+Options], eax
0x180027b8a  lea     r9, aRpcexceptionD; "RpcException [%d]"
0x180027b91  mov     r8d, 201h
0x180027b97  lea     rdx, aRetrievefilein_0; "RetrieveFileInfoFromRpc"
0x180027b9e  mov     ecx, 1
0x180027ba3  call    AslLogCallPrintf
0x180027ba8  test    ebx, ebx
0x180027baa  jle     short loc_180027BB5
0x180027bac  movzx   ebx, bx
0x180027baf  or      ebx, 80070000h
0x180027bb5  mov     [rsp+148h+var_108], ebx
0x180027bb9  xor     edi, edi
0x180027bbb  cmp     [rsp+148h+Binding], rdi
0x180027bc0  jz      short loc_180027BCD
0x180027bc2  lea     rcx, [rsp+148h+Binding]; Binding
0x180027bc7  call    cs:__imp_RpcBindingFree
0x180027bcd  mov     eax, ebx
0x180027bcf  mov     rcx, [rsp+148h+var_28]
0x180027bd7  xor     rcx, rsp; StackCookie
0x180027bda  call    __security_check_cookie
0x180027bdf  lea     r11, [rsp+148h+var_18]
0x180027be7  mov     rbx, [r11+30h]
0x180027beb  mov     rsi, [r11+38h]
0x180027bef  mov     rsp, r11
0x180027bf2  pop     r15
0x180027bf4  pop     r14
0x180027bf6  pop     rdi
0x180027bf7  retn
0x1800e6455  push    rbp
0x1800e6457  sub     rsp, 40h
0x1800e645b  mov     rbp, rdx
0x1800e645e  mov     rcx, [rcx]
0x1800e6461  mov     ecx, [rcx]; ExceptionCode
0x1800e6463  call    cs:__imp_I_RpcExceptionFilter
0x1800e6469  nop
0x1800e646a  add     rsp, 40h
0x1800e646e  pop     rbp
0x1800e646f  retn
```
