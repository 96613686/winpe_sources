# Apx::ApfRpc::CreateDevice_Rpc(APF_DEVICE_RPC_CONFIG *,void * *)

- ea: `0x18000bf24`
- end: `0x18000c196`
- name: `?CreateDevice_Rpc@ApfRpc@Apx@@SAJPEAUAPF_DEVICE_RPC_CONFIG@@PEAPEAX@Z`
- size: `626`
- prototype: `__int64 __fastcall(struct APF_DEVICE_RPC_CONFIG *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f664`

## callees

- `0x18000a12c`
- `0x18000a1b4`
- `0x18000bf24`
- `0x18000c29c`
- `0x18000c2e4`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000c149`
- `RPCRT4!RpcBindingFree` at `0x18000c149`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000bfd6`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000bfd6`
- `RPCRT4!NdrClientCall3` at `0x18000c0c4`
- `RPCRT4!NdrClientCall3` at `0x18000c0c4`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000c016`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000c016`
- `RPCRT4!RpcStringFreeW` at `0x18000c023`
- `RPCRT4!RpcStringFreeW` at `0x18000c023`

## pseudocode

```c
__int64 __fastcall Apx::ApfRpc::CreateDevice_Rpc(struct APF_DEVICE_RPC_CONFIG *a1, void **a2)
{
  _QWORD *v4; // rcx
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  int Pointer; // ebx
  _QWORD *v9; // rcx
  int v10; // edx
  int v11; // r8d
  bool v12; // sf
  CLIENT_CALL_RETURN v13; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+70h] [rbp+18h] BYREF
  RPC_WSTR String; // [rsp+78h] [rbp+20h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_035003ffd5543b5c3de6eea8533c511b_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  Binding = 0;
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_(v4[2], 10, &WPP_035003ffd5543b5c3de6eea8533c511b_Traceguids);
  String = 0;
  Binding = 0;
  v5 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
  Pointer = v5;
  if ( v5 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_24;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_20;
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, v5);
    goto LABEL_19;
  }
  Pointer = RpcBindingFromStringBindingW(String, &Binding);
  RpcStringFreeW(&String);
  if ( !Pointer )
  {
LABEL_19:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_20;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_24;
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, (_DWORD)String, Pointer);
    goto LABEL_19;
  }
LABEL_20:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 5u )
  {
    WPP_SF_(v9[2], 13, &WPP_035003ffd5543b5c3de6eea8533c511b_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
LABEL_24:
  v12 = Pointer < 0;
  if ( Pointer > 0 )
  {
    Pointer = (unsigned __int16)Pointer | 0x80070000;
    v12 = Pointer < 0;
  }
  if ( !v12 )
  {
    String = 0;
    v13.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, Binding, a1, a2).Pointer;
    Pointer = (int)v13.Pointer;
    String = (RPC_WSTR)v13.Simple;
    v9 = WPP_GLOBAL_Control;
    if ( SLODWORD(v13.Simple) >= 0 )
      Pointer = 0;
  }
  if ( Binding )
  {
    RpcBindingFree(&Binding);
    Binding = 0;
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_(v9[2], 16, &WPP_035003ffd5543b5c3de6eea8533c511b_Traceguids);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000bf24  mov     [rsp+arg_0], rbx
0x18000bf29  push    rsi
0x18000bf2a  push    r14
0x18000bf2c  push    r15
0x18000bf2e  sub     rsp, 40h
0x18000bf32  mov     r14, rdx
0x18000bf35  mov     r15, rcx
0x18000bf38  lea     rsi, WPP_GLOBAL_Control
0x18000bf3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf46  cmp     rcx, rsi
0x18000bf49  jz      short loc_18000BF73
0x18000bf4b  test    byte ptr [rcx+1Ch], 1
0x18000bf4f  jz      short loc_18000BF73
0x18000bf51  cmp     byte ptr [rcx+19h], 5
0x18000bf55  jb      short loc_18000BF73
0x18000bf57  mov     edx, 0Eh
0x18000bf5c  lea     r8, WPP_035003ffd5543b5c3de6eea8533c511b_Traceguids
0x18000bf63  mov     rcx, [rcx+10h]
0x18000bf67  call    WPP_SF_
0x18000bf6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf73  mov     [rsp+58h+Binding], 0
0x18000bf7c  cmp     rcx, rsi
0x18000bf7f  jz      short loc_18000BFA2
0x18000bf81  test    byte ptr [rcx+1Ch], 1
0x18000bf85  jz      short loc_18000BFA2
0x18000bf87  cmp     byte ptr [rcx+19h], 5
0x18000bf8b  jb      short loc_18000BFA2
0x18000bf8d  mov     edx, 0Ah
0x18000bf92  lea     r8, WPP_035003ffd5543b5c3de6eea8533c511b_Traceguids
0x18000bf99  mov     rcx, [rcx+10h]
0x18000bf9d  call    WPP_SF_
0x18000bfa2  mov     [rsp+58h+String], 0
0x18000bfab  mov     [rsp+58h+Binding], 0
0x18000bfb4  lea     rax, [rsp+58h+String]
0x18000bfb9  mov     [rsp+58h+StringBinding], rax; StringBinding
0x18000bfbe  mov     [rsp+58h+Options], 0; Options
0x18000bfc7  xor     r9d, r9d; Endpoint
0x18000bfca  xor     r8d, r8d; NetworkAddr
0x18000bfcd  lea     rdx, ProtSeq; "ncalrpc"
0x18000bfd4  xor     ecx, ecx; ObjUuid
0x18000bfd6  call    cs:__imp_RpcStringBindingComposeW
0x18000bfdc  mov     ebx, eax
0x18000bfde  test    eax, eax
0x18000bfe0  jz      short loc_18000C00C
0x18000bfe2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bfe9  cmp     rcx, rsi
0x18000bfec  jz      loc_18000C08B
0x18000bff2  test    byte ptr [rcx+1Ch], 80h
0x18000bff6  jz      short loc_18000C05E
0x18000bff8  cmp     byte ptr [rcx+19h], 2
0x18000bffc  jb      short loc_18000C05E
0x18000bffe  mov     r9d, eax
0x18000c001  mov     rcx, [rcx+10h]
0x18000c005  call    WPP_SF_D
0x18000c00a  jmp     short loc_18000C057
0x18000c00c  lea     rdx, [rsp+58h+Binding]; Binding
0x18000c011  mov     rcx, [rsp+58h+String]; StringBinding
0x18000c016  call    cs:__imp_RpcBindingFromStringBindingW
0x18000c01c  mov     ebx, eax
0x18000c01e  lea     rcx, [rsp+58h+String]; String
0x18000c023  call    cs:__imp_RpcStringFreeW
0x18000c029  test    ebx, ebx
0x18000c02b  jz      short loc_18000C057
0x18000c02d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c034  cmp     rcx, rsi
0x18000c037  jz      short loc_18000C08B
0x18000c039  test    byte ptr [rcx+1Ch], 80h
0x18000c03d  jz      short loc_18000C05E
0x18000c03f  cmp     byte ptr [rcx+19h], 2
0x18000c043  jb      short loc_18000C05E
0x18000c045  mov     dword ptr [rsp+58h+Options], ebx
0x18000c049  mov     r9, [rsp+58h+String]
0x18000c04e  mov     rcx, [rcx+10h]
0x18000c052  call    WPP_SF_SD
0x18000c057  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c05e  cmp     rcx, rsi
0x18000c061  jz      short loc_18000C08B
0x18000c063  test    byte ptr [rcx+1Ch], 1
0x18000c067  jz      short loc_18000C08B
0x18000c069  cmp     byte ptr [rcx+19h], 5
0x18000c06d  jb      short loc_18000C08B
0x18000c06f  mov     edx, 0Dh
0x18000c074  lea     r8, WPP_035003ffd5543b5c3de6eea8533c511b_Traceguids
0x18000c07b  mov     rcx, [rcx+10h]
0x18000c07f  call    WPP_SF_
0x18000c084  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c08b  test    ebx, ebx
0x18000c08d  jle     short loc_18000C09A
0x18000c08f  movzx   ebx, bx
0x18000c092  or      ebx, 80070000h
0x18000c098  test    ebx, ebx
0x18000c09a  js      loc_18000C13C
0x18000c0a0  mov     [rsp+58h+String], 0
0x18000c0a9  mov     [rsp+58h+StringBinding], r14
0x18000c0ae  mov     [rsp+58h+Options], r15
0x18000c0b3  mov     r9, [rsp+58h+Binding]
0x18000c0b8  xor     r8d, r8d; pReturnValue
0x18000c0bb  xor     edx, edx; nProcNum
0x18000c0bd  lea     rcx, pProxyInfo; pProxyInfo
0x18000c0c4  call    cs:__imp_NdrClientCall3
0x18000c0ca  mov     rbx, rax
0x18000c0cd  mov     [rsp+58h+String], rax
0x18000c0d2  mov     [rsp+58h+var_28], eax
0x18000c0d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0dd  jmp     short loc_18000C136
0x18000c0df  test    eax, eax
0x18000c0e1  jle     short loc_18000C0EB
0x18000c0e3  movzx   eax, ax
0x18000c0e6  or      eax, 80070000h
0x18000c0eb  mov     ebx, eax
0x18000c0ed  mov     [rsp+58h+var_28], eax
0x18000c0f1  lea     rdx, WPP_GLOBAL_Control
0x18000c0f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0ff  cmp     rcx, rdx
0x18000c102  jz      short loc_18000C12F
0x18000c104  test    byte ptr [rcx+1Ch], 80h
0x18000c108  jz      short loc_18000C12F
0x18000c10a  cmp     byte ptr [rcx+19h], 2
0x18000c10e  jb      short loc_18000C12F
0x18000c110  mov     edx, 0Fh
0x18000c115  mov     r9d, eax
0x18000c118  lea     r8, WPP_035003ffd5543b5c3de6eea8533c511b_Traceguids
0x18000c11f  mov     rcx, [rcx+10h]
0x18000c123  call    WPP_SF_d
0x18000c128  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c12f  lea     rsi, WPP_GLOBAL_Control
0x18000c136  test    ebx, ebx
0x18000c138  js      short loc_18000C13C
0x18000c13a  xor     ebx, ebx
0x18000c13c  cmp     [rsp+58h+Binding], 0
0x18000c142  jz      short loc_18000C15F
0x18000c144  lea     rcx, [rsp+58h+Binding]; Binding
0x18000c149  call    cs:__imp_RpcBindingFree
0x18000c14f  mov     [rsp+58h+Binding], 0
0x18000c158  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c15f  cmp     rcx, rsi
0x18000c162  jz      short loc_18000C185
0x18000c164  test    byte ptr [rcx+1Ch], 1
0x18000c168  jz      short loc_18000C185
0x18000c16a  cmp     byte ptr [rcx+19h], 5
0x18000c16e  jb      short loc_18000C185
0x18000c170  mov     edx, 10h
0x18000c175  lea     r8, WPP_035003ffd5543b5c3de6eea8533c511b_Traceguids
0x18000c17c  mov     rcx, [rcx+10h]
0x18000c180  call    WPP_SF_
0x18000c185  mov     eax, ebx
0x18000c187  mov     rbx, [rsp+58h+arg_0]
0x18000c18c  add     rsp, 40h
0x18000c190  pop     r15
0x18000c192  pop     r14
0x18000c194  pop     rsi
0x18000c195  retn
```
