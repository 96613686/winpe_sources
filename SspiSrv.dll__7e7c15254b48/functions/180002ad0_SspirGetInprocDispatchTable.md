# SspirGetInprocDispatchTable

- ea: `0x180002ad0`
- end: `0x180002b80`
- name: `SspirGetInprocDispatchTable`
- size: `176`
- prototype: `int __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x180002ad0`
- `0x180003213`
- `0x180003340`

## import_xrefs

- `RPCRT4!RpcServerInqCallAttributesW` at `0x180002b2a`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180002b2a`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002b36`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002b36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002b42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002b42`

## pseudocode

```c
int __fastcall SspirGetInprocDispatchTable(__int64 a1, _QWORD *a2)
{
  RPC_STATUS v4; // eax
  int v5; // ebx
  _DWORD RpcCallAttributes[2]; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v7[56]; // [rsp+28h] [rbp-80h] BYREF
  int v8; // [rsp+60h] [rbp-48h]

  if ( !gLsapSspiExtension )
    return -1073741637;
  memset_0(v7, 0, 0x68u);
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 16;
  v4 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v4 )
    return I_RpcMapWin32Status(v4);
  v5 = v8;
  if ( v5 != GetCurrentProcessId() )
    return -1073741790;
  *a2 = &SspiInprocFunctions;
  return 0;
}

```

## disassembly

```asm
0x180002ad0  mov     [rsp+arg_0], rbx
0x180002ad5  push    rdi
0x180002ad6  sub     rsp, 0A0h
0x180002add  mov     rax, cs:__security_cookie
0x180002ae4  xor     rax, rsp
0x180002ae7  mov     [rsp+0A8h+var_18], rax
0x180002aef  cmp     cs:gLsapSspiExtension, 0
0x180002af7  mov     rdi, rdx
0x180002afa  jnz     short loc_180002B03
0x180002afc  mov     eax, 0C00000BBh
0x180002b01  jmp     short loc_180002B5F
0x180002b03  xor     edx, edx; Val
0x180002b05  lea     rcx, [rsp+0A8h+var_80]; void *
0x180002b0a  lea     r8d, [rdx+68h]; Size
0x180002b0e  call    memset_0
0x180002b13  lea     rdx, [rsp+0A8h+RpcCallAttributes]; RpcCallAttributes
0x180002b18  mov     [rsp+0A8h+RpcCallAttributes], 2
0x180002b20  xor     ecx, ecx; ClientBinding
0x180002b22  mov     [rsp+0A8h+var_84], 10h
0x180002b2a  call    cs:__imp_RpcServerInqCallAttributesW
0x180002b30  test    eax, eax
0x180002b32  jz      short loc_180002B3E
0x180002b34  mov     ecx, eax; Status
0x180002b36  call    cs:__imp_I_RpcMapWin32Status
0x180002b3c  jmp     short loc_180002B5F
0x180002b3e  mov     ebx, [rsp+0A8h+var_48]
0x180002b42  call    cs:__imp_GetCurrentProcessId
0x180002b48  cmp     ebx, eax
0x180002b4a  jz      short loc_180002B53
0x180002b4c  mov     eax, 0C0000022h
0x180002b51  jmp     short loc_180002B5F
0x180002b53  lea     rax, SspiInprocFunctions
0x180002b5a  mov     [rdi], rax
0x180002b5d  xor     eax, eax
0x180002b5f  mov     rcx, [rsp+0A8h+var_18]
0x180002b67  xor     rcx, rsp; StackCookie
0x180002b6a  call    __security_check_cookie
0x180002b6f  mov     rbx, [rsp+0A8h+arg_0]
0x180002b77  add     rsp, 0A0h
0x180002b7e  pop     rdi
0x180002b7f  retn
```
