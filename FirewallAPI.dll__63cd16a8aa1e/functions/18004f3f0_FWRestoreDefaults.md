# FWRestoreDefaults

- ea: `0x18004f3f0`
- end: `0x18004f6d9`
- name: `FWRestoreDefaults`
- size: `745`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180037490`
- `0x180037660`

## callees

- `0x180005954`
- `0x18000e6c0`
- `0x18000ebe0`
- `0x18002514c`
- `0x1800277b0`
- `0x1800284c4`
- `0x18003104c`
- `0x18004f3f0`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005c1d8`
- `RPCRT4!RpcExceptionFilter` at `0x18005c1f4`
- `RPCRT4!RpcExceptionFilter` at `0x18005c1d8`
- `RPCRT4!RpcExceptionFilter` at `0x18005c1f4`
- `RPCRT4!NdrClientCall3` at `0x18004f50f`
- `RPCRT4!NdrClientCall3` at `0x18004f5d4`
- `RPCRT4!NdrClientCall3` at `0x18004f50f`
- `RPCRT4!NdrClientCall3` at `0x18004f5d4`
- `ntdll!EtwEventWrite` at `0x18004f42b`
- `ntdll!EtwEventWrite` at `0x18004f6b0`
- `ntdll!EtwEventWrite` at `0x18004f42b`
- `ntdll!EtwEventWrite` at `0x18004f6b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004f46f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004f46f`

## pseudocode

```c
__int64 __fastcall FWRestoreDefaults(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int Pointer; // eax
  _BYTE v8[4]; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v9; // [rsp+44h] [rbp-64h]
  __int64 v10; // [rsp+60h] [rbp-48h]

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_RestoreDefaults, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  memset_0(v8, 0, 0x50u);
  GetTickCount64();
  v2 = Int_FWCreateConnectionHandle(512, a1, 2, 2, 0, v8);
  v3 = v2;
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v2);
  }
  else
  {
    v4 = v9;
    if ( v9 > 1 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v4 = v9;
    }
    if ( v4 )
    {
      if ( v4 == 1 )
      {
        Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&RemoteFW_ProxyInfo, 2u, 0, v10).Pointer;
        v3 = Pointer;
        if ( Pointer )
        {
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, Pointer);
        }
      }
    }
    else
    {
      v5 = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&FW_ProxyInfo, 2u, 0, v10).Pointer;
      v3 = v5;
      if ( v5
        && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v5);
      }
    }
  }
  Int_FWClientHandleCleanup(v8);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_RestoreDefaults, 0, 0);
  return v3;
}

```

## disassembly

```asm
0x18004f3f0  mov     [rsp+arg_8], rbx
0x18004f3f5  push    rdi
0x18004f3f6  sub     rsp, 0A0h
0x18004f3fd  mov     rax, cs:__security_cookie
0x18004f404  xor     rax, rsp
0x18004f407  mov     [rsp+0A8h+var_18], rax
0x18004f40f  mov     rbx, rcx
0x18004f412  mov     rcx, cs:g_Provider
0x18004f419  test    rcx, rcx
0x18004f41c  jz      short loc_18004F431
0x18004f41e  xor     r9d, r9d
0x18004f421  xor     r8d, r8d
0x18004f424  lea     rdx, MPS_CLNT_API_Enter_RestoreDefaults
0x18004f42b  call    cs:__imp_EtwEventWrite
0x18004f431  lea     rdi, WPP_GLOBAL_Control
0x18004f438  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f43f  cmp     rcx, rdi
0x18004f442  jz      short loc_18004F45F
0x18004f444  test    byte ptr [rcx+1Ch], 8
0x18004f448  jz      short loc_18004F45F
0x18004f44a  mov     edx, 47h ; 'G'
0x18004f44f  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18004f456  mov     rcx, [rcx+10h]
0x18004f45a  call    WPP_SF_
0x18004f45f  xor     edx, edx; Val
0x18004f461  lea     r8d, [rdx+50h]; Size
0x18004f465  lea     rcx, [rsp+0A8h+var_68]; void *
0x18004f46a  call    memset_0
0x18004f46f  call    cs:__imp_GetTickCount64
0x18004f475  mov     ecx, 200h
0x18004f47a  lea     rax, [rsp+0A8h+var_68]
0x18004f47f  mov     [rsp+0A8h+var_80], rax
0x18004f484  mov     [rsp+0A8h+var_88], 0
0x18004f48c  mov     r9d, 2
0x18004f492  mov     r8d, r9d
0x18004f495  mov     rdx, rbx
0x18004f498  call    Int_FWCreateConnectionHandle
0x18004f49d  mov     ebx, eax
0x18004f49f  test    eax, eax
0x18004f4a1  jz      short loc_18004F4DA
0x18004f4a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f4aa  cmp     rcx, rdi
0x18004f4ad  jz      loc_18004F666
0x18004f4b3  test    byte ptr [rcx+1Ch], 1
0x18004f4b7  jz      loc_18004F666
0x18004f4bd  mov     edx, 48h ; 'H'
0x18004f4c2  mov     r9d, eax
0x18004f4c5  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18004f4cc  mov     rcx, [rcx+10h]
0x18004f4d0  call    WPP_SF_d
0x18004f4d5  jmp     loc_18004F666
0x18004f4da  mov     eax, [rsp+0A8h+var_64]
0x18004f4de  cmp     eax, 1
0x18004f4e1  jbe     short loc_18004F4EC
0x18004f4e3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004f4e8  mov     eax, [rsp+0A8h+var_64]
0x18004f4ec  test    eax, eax
0x18004f4ee  jnz     loc_18004F5B0
0x18004f4f4  mov     [rsp+0A8h+var_70], 0
0x18004f4fd  mov     r9, [rsp+0A8h+var_48]
0x18004f502  xor     r8d, r8d; pReturnValue
0x18004f505  lea     edx, [rax+2]; nProcNum
0x18004f508  lea     rcx, ?FW_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004f50f  call    cs:__imp_NdrClientCall3
0x18004f515  mov     rbx, rax
0x18004f518  mov     [rsp+0A8h+var_70], rax
0x18004f51d  mov     [rsp+0A8h+var_78], eax
0x18004f521  mov     [rsp+0A8h+var_78], eax
0x18004f525  test    eax, eax
0x18004f527  jz      short loc_18004F558
0x18004f529  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f530  cmp     rcx, rdi
0x18004f533  jz      short loc_18004F553
0x18004f535  test    byte ptr [rcx+1Ch], 1
0x18004f539  jz      short loc_18004F553
0x18004f53b  mov     edx, 49h ; 'I'
0x18004f540  mov     r9d, eax
0x18004f543  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18004f54a  mov     rcx, [rcx+10h]
0x18004f54e  call    WPP_SF_d
0x18004f553  jmp     loc_18004F666
0x18004f558  jmp     loc_18004F666
0x18004f55d  mov     ebx, eax
0x18004f55f  mov     [rsp+0A8h+var_78], eax
0x18004f563  test    eax, eax
0x18004f565  jz      short loc_18004F5A4
0x18004f567  lea     rdx, WPP_GLOBAL_Control
0x18004f56e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f575  cmp     rcx, rdx
0x18004f578  jz      short loc_18004F598
0x18004f57a  test    byte ptr [rcx+1Ch], 1
0x18004f57e  jz      short loc_18004F598
0x18004f580  mov     edx, 4Ah ; 'J'
0x18004f585  mov     r9d, eax
0x18004f588  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18004f58f  mov     rcx, [rcx+10h]
0x18004f593  call    WPP_SF_d
0x18004f598  lea     rdi, WPP_GLOBAL_Control
0x18004f59f  jmp     loc_18004F666
0x18004f5a4  lea     rdi, WPP_GLOBAL_Control
0x18004f5ab  jmp     loc_18004F666
0x18004f5b0  cmp     eax, 1
0x18004f5b3  jnz     loc_18004F666
0x18004f5b9  mov     [rsp+0A8h+var_70], 0
0x18004f5c2  mov     r9, [rsp+0A8h+var_48]
0x18004f5c7  xor     r8d, r8d; pReturnValue
0x18004f5ca  lea     edx, [rax+1]; nProcNum
0x18004f5cd  lea     rcx, ?RemoteFW_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004f5d4  call    cs:__imp_NdrClientCall3
0x18004f5da  mov     [rsp+0A8h+var_70], rax
0x18004f5df  mov     [rsp+0A8h+var_78], eax
0x18004f5e3  mov     ebx, eax
0x18004f5e5  mov     [rsp+0A8h+var_78], eax
0x18004f5e9  test    eax, eax
0x18004f5eb  jz      short loc_18004F619
0x18004f5ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f5f4  cmp     rcx, rdi
0x18004f5f7  jz      short loc_18004F617
0x18004f5f9  test    byte ptr [rcx+1Ch], 1
0x18004f5fd  jz      short loc_18004F617
0x18004f5ff  mov     edx, 4Bh ; 'K'
0x18004f604  mov     r9d, eax
0x18004f607  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18004f60e  mov     rcx, [rcx+10h]
0x18004f612  call    WPP_SF_d
0x18004f617  jmp     short loc_18004F666
0x18004f619  jmp     short loc_18004F666
0x18004f61b  mov     ebx, eax
0x18004f61d  mov     [rsp+0A8h+var_78], eax
0x18004f621  test    eax, eax
0x18004f623  jz      short loc_18004F65F
0x18004f625  lea     rdx, WPP_GLOBAL_Control
0x18004f62c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f633  cmp     rcx, rdx
0x18004f636  jz      short loc_18004F656
0x18004f638  test    byte ptr [rcx+1Ch], 1
0x18004f63c  jz      short loc_18004F656
0x18004f63e  mov     edx, 4Ch ; 'L'
0x18004f643  mov     r9d, eax
0x18004f646  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18004f64d  mov     rcx, [rcx+10h]
0x18004f651  call    WPP_SF_d
0x18004f656  lea     rdi, WPP_GLOBAL_Control
0x18004f65d  jmp     short loc_18004F666
0x18004f65f  lea     rdi, WPP_GLOBAL_Control
0x18004f666  lea     rcx, [rsp+0A8h+var_68]
0x18004f66b  call    Int_FWClientHandleCleanup
0x18004f670  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f677  cmp     rcx, rdi
0x18004f67a  jz      short loc_18004F697
0x18004f67c  test    byte ptr [rcx+1Ch], 8
0x18004f680  jz      short loc_18004F697
0x18004f682  mov     edx, 4Dh ; 'M'
0x18004f687  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18004f68e  mov     rcx, [rcx+10h]
0x18004f692  call    WPP_SF_
0x18004f697  mov     rcx, cs:g_Provider
0x18004f69e  test    rcx, rcx
0x18004f6a1  jz      short loc_18004F6B6
0x18004f6a3  xor     r9d, r9d
0x18004f6a6  xor     r8d, r8d
0x18004f6a9  lea     rdx, MPS_CLNT_API_Exit_RestoreDefaults
0x18004f6b0  call    cs:__imp_EtwEventWrite
0x18004f6b6  mov     eax, ebx
0x18004f6b8  mov     rcx, [rsp+0A8h+var_18]
0x18004f6c0  xor     rcx, rsp; StackCookie
0x18004f6c3  call    __security_check_cookie
0x18004f6c8  mov     rbx, [rsp+0A8h+arg_8]
0x18004f6d0  add     rsp, 0A0h
0x18004f6d7  pop     rdi
0x18004f6d8  retn
0x18005c1ca  push    rbp
0x18005c1cc  sub     rsp, 30h
0x18005c1d0  mov     rbp, rdx
0x18005c1d3  mov     rcx, [rcx]
0x18005c1d6  mov     ecx, [rcx]; ExceptionCode
0x18005c1d8  call    cs:__imp_RpcExceptionFilter
0x18005c1de  nop
0x18005c1df  add     rsp, 30h
0x18005c1e3  pop     rbp
0x18005c1e4  retn
0x18005c1e6  push    rbp
0x18005c1e8  sub     rsp, 30h
0x18005c1ec  mov     rbp, rdx
0x18005c1ef  mov     rcx, [rcx]
0x18005c1f2  mov     ecx, [rcx]; ExceptionCode
0x18005c1f4  call    cs:__imp_RpcExceptionFilter
0x18005c1fa  nop
0x18005c1fb  add     rsp, 30h
0x18005c1ff  pop     rbp
0x18005c200  retn
```
