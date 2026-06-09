# CDsmAdminControl::SetServicePaused(int)

- ea: `0x180009c80`
- end: `0x180009d19`
- name: `?SetServicePaused@CDsmAdminControl@@UEAAJH@Z`
- size: `153`
- prototype: `__int64 __fastcall(CDsmAdminControl *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180009c80`
- `0x180009d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180009cb0`
- `RPCRT4!NdrClientCall3` at `0x180009cb0`

## pseudocode

```c
__int64 __fastcall CDsmAdminControl::SetServicePaused(CDsmAdminControl *this, int a2)
{
  unsigned int Pointer; // eax
  unsigned int v3; // ebx

  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, DsmRpcAdmin_v1_0_c_ifspec, a2).Pointer;
  v3 = Pointer;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_0d5f4a92635133552c696894ac679e2a_Traceguids, Pointer);
  return v3;
}

```

## disassembly

```asm
0x180009c80  mov     rax, rsp
0x180009c83  mov     [rax+8], rbx
0x180009c87  push    rdi
0x180009c88  sub     rsp, 40h
0x180009c8c  mov     dword ptr [rax-18h], 80004005h
0x180009c93  xor     edi, edi
0x180009c95  mov     [rax+18h], rdi
0x180009c99  mov     [rax-28h], edx
0x180009c9c  mov     r9, cs:DsmRpcAdmin_v1_0_c_ifspec
0x180009ca3  xor     r8d, r8d; pReturnValue
0x180009ca6  lea     edx, [rdi+2]; nProcNum
0x180009ca9  lea     rcx, pProxyInfo; pProxyInfo
0x180009cb0  call    cs:__imp_NdrClientCall3
0x180009cb6  mov     rbx, rax
0x180009cb9  mov     [rsp+48h+arg_10], rax
0x180009cbe  mov     [rsp+48h+var_18], eax
0x180009cc2  jmp     short loc_180009CCA
0x180009cc4  mov     edi, eax
0x180009cc6  mov     ebx, [rsp+48h+var_18]
0x180009cca  test    edi, edi
0x180009ccc  jz      short loc_180009CDB
0x180009cce  jle     short loc_180009CD9
0x180009cd0  movzx   edi, di
0x180009cd3  or      edi, 80070000h
0x180009cd9  mov     ebx, edi
0x180009cdb  lea     rax, WPP_GLOBAL_Control
0x180009ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ce9  cmp     rcx, rax
0x180009cec  jz      short loc_180009D0C
0x180009cee  test    byte ptr [rcx+1Ch], 1
0x180009cf2  jz      short loc_180009D0C
0x180009cf4  mov     edx, 0Ch
0x180009cf9  mov     r9d, ebx
0x180009cfc  lea     r8, WPP_0d5f4a92635133552c696894ac679e2a_Traceguids
0x180009d03  mov     rcx, [rcx+10h]
0x180009d07  call    WPP_SF_D
0x180009d0c  mov     eax, ebx
0x180009d0e  mov     rbx, [rsp+48h+arg_0]
0x180009d13  add     rsp, 40h
0x180009d17  pop     rdi
0x180009d18  retn
```
