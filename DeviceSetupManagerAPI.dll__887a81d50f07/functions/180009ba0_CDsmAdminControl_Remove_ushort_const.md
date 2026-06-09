# CDsmAdminControl::Remove(ushort const *)

- ea: `0x180009ba0`
- end: `0x180009c79`
- name: `?Remove@CDsmAdminControl@@UEAAJPEBG@Z`
- size: `217`
- prototype: `__int64 __fastcall(CDsmAdminControl *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800017c0`
- `0x180009ba0`
- `0x180009d20`
- `0x18000d524`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180009c03`
- `RPCRT4!NdrClientCall3` at `0x180009c03`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180009bc9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180009bc9`

## pseudocode

```c
__int64 __fastcall CDsmAdminControl::Remove(CDsmAdminControl *this, const unsigned __int16 *a2)
{
  HRESULT Pointer; // ebx
  GUID pclsid; // [rsp+40h] [rbp-28h] BYREF

  pclsid = 0;
  Pointer = CLSIDFromString(a2, &pclsid);
  if ( Pointer >= 0 )
  {
    StartDsmService();
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              1u,
                              0,
                              DsmRpcAdmin_v1_0_c_ifspec,
                              &pclsid).Pointer;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_0d5f4a92635133552c696894ac679e2a_Traceguids,
      (unsigned int)Pointer);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180009ba0  mov     [rsp+arg_0], rbx
0x180009ba5  push    rdi
0x180009ba6  sub     rsp, 60h
0x180009baa  mov     rax, cs:__security_cookie
0x180009bb1  xor     rax, rsp
0x180009bb4  mov     [rsp+68h+var_18], rax
0x180009bb9  mov     rcx, rdx; lpsz
0x180009bbc  xorps   xmm0, xmm0
0x180009bbf  movups  xmmword ptr [rsp+68h+pclsid.Data1], xmm0
0x180009bc4  lea     rdx, [rsp+68h+pclsid]; pclsid
0x180009bc9  call    cs:__imp_CLSIDFromString
0x180009bcf  mov     ebx, eax
0x180009bd1  mov     [rsp+68h+var_38], eax
0x180009bd5  test    eax, eax
0x180009bd7  js      short loc_180009C2E
0x180009bd9  call    ?StartDsmService@@YAJXZ; StartDsmService(void)
0x180009bde  xor     edi, edi
0x180009be0  mov     [rsp+68h+var_30], rdi
0x180009be5  lea     rax, [rsp+68h+pclsid]
0x180009bea  mov     [rsp+68h+var_48], rax
0x180009bef  mov     r9, cs:DsmRpcAdmin_v1_0_c_ifspec
0x180009bf6  xor     r8d, r8d; pReturnValue
0x180009bf9  lea     edx, [rdi+1]; nProcNum
0x180009bfc  lea     rcx, pProxyInfo; pProxyInfo
0x180009c03  call    cs:__imp_NdrClientCall3
0x180009c09  mov     rbx, rax
0x180009c0c  mov     [rsp+68h+var_30], rax
0x180009c11  mov     [rsp+68h+var_38], eax
0x180009c15  jmp     short loc_180009C1D
0x180009c17  mov     edi, eax
0x180009c19  mov     ebx, [rsp+68h+var_38]
0x180009c1d  test    edi, edi
0x180009c1f  jz      short loc_180009C2E
0x180009c21  jle     short loc_180009C2C
0x180009c23  movzx   edi, di
0x180009c26  or      edi, 80070000h
0x180009c2c  mov     ebx, edi
0x180009c2e  lea     rax, WPP_GLOBAL_Control
0x180009c35  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c3c  cmp     rcx, rax
0x180009c3f  jz      short loc_180009C5F
0x180009c41  test    byte ptr [rcx+1Ch], 1
0x180009c45  jz      short loc_180009C5F
0x180009c47  mov     edx, 0Bh
0x180009c4c  mov     r9d, ebx
0x180009c4f  lea     r8, WPP_0d5f4a92635133552c696894ac679e2a_Traceguids
0x180009c56  mov     rcx, [rcx+10h]
0x180009c5a  call    WPP_SF_D
0x180009c5f  mov     eax, ebx
0x180009c61  mov     rcx, [rsp+68h+var_18]
0x180009c66  xor     rcx, rsp; StackCookie
0x180009c69  call    __security_check_cookie
0x180009c6e  mov     rbx, [rsp+68h+arg_0]
0x180009c73  add     rsp, 60h
0x180009c77  pop     rdi
0x180009c78  retn
```
