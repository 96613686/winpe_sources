# CDsmAdminControl::Install(ushort const *)

- ea: `0x180009810`
- end: `0x1800098e8`
- name: `?Install@CDsmAdminControl@@UEAAJPEBG@Z`
- size: `216`
- prototype: `__int64 __fastcall(CDsmAdminControl *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800017c0`
- `0x180009810`
- `0x180009d20`
- `0x18000d524`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180009872`
- `RPCRT4!NdrClientCall3` at `0x180009872`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180009839`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180009839`

## pseudocode

```c
__int64 __fastcall CDsmAdminControl::Install(CDsmAdminControl *this, const unsigned __int16 *a2)
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
                              0,
                              0,
                              DsmRpcAdmin_v1_0_c_ifspec,
                              &pclsid).Pointer;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_0d5f4a92635133552c696894ac679e2a_Traceguids,
      (unsigned int)Pointer);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180009810  mov     [rsp+arg_0], rbx
0x180009815  push    rdi
0x180009816  sub     rsp, 60h
0x18000981a  mov     rax, cs:__security_cookie
0x180009821  xor     rax, rsp
0x180009824  mov     [rsp+68h+var_18], rax
0x180009829  mov     rcx, rdx; lpsz
0x18000982c  xorps   xmm0, xmm0
0x18000982f  movups  xmmword ptr [rsp+68h+pclsid.Data1], xmm0
0x180009834  lea     rdx, [rsp+68h+pclsid]; pclsid
0x180009839  call    cs:__imp_CLSIDFromString
0x18000983f  mov     ebx, eax
0x180009841  mov     [rsp+68h+var_38], eax
0x180009845  test    eax, eax
0x180009847  js      short loc_18000989D
0x180009849  call    ?StartDsmService@@YAJXZ; StartDsmService(void)
0x18000984e  xor     edi, edi
0x180009850  mov     [rsp+68h+var_30], rdi
0x180009855  lea     rax, [rsp+68h+pclsid]
0x18000985a  mov     [rsp+68h+var_48], rax
0x18000985f  mov     r9, cs:DsmRpcAdmin_v1_0_c_ifspec
0x180009866  xor     r8d, r8d; pReturnValue
0x180009869  xor     edx, edx; nProcNum
0x18000986b  lea     rcx, pProxyInfo; pProxyInfo
0x180009872  call    cs:__imp_NdrClientCall3
0x180009878  mov     rbx, rax
0x18000987b  mov     [rsp+68h+var_30], rax
0x180009880  mov     [rsp+68h+var_38], eax
0x180009884  jmp     short loc_18000988C
0x180009886  mov     edi, eax
0x180009888  mov     ebx, [rsp+68h+var_38]
0x18000988c  test    edi, edi
0x18000988e  jz      short loc_18000989D
0x180009890  jle     short loc_18000989B
0x180009892  movzx   edi, di
0x180009895  or      edi, 80070000h
0x18000989b  mov     ebx, edi
0x18000989d  lea     rax, WPP_GLOBAL_Control
0x1800098a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098ab  cmp     rcx, rax
0x1800098ae  jz      short loc_1800098CE
0x1800098b0  test    byte ptr [rcx+1Ch], 1
0x1800098b4  jz      short loc_1800098CE
0x1800098b6  mov     edx, 0Ah
0x1800098bb  mov     r9d, ebx
0x1800098be  lea     r8, WPP_0d5f4a92635133552c696894ac679e2a_Traceguids
0x1800098c5  mov     rcx, [rcx+10h]
0x1800098c9  call    WPP_SF_D
0x1800098ce  mov     eax, ebx
0x1800098d0  mov     rcx, [rsp+68h+var_18]
0x1800098d5  xor     rcx, rsp; StackCookie
0x1800098d8  call    __security_check_cookie
0x1800098dd  mov     rbx, [rsp+68h+arg_0]
0x1800098e2  add     rsp, 60h
0x1800098e6  pop     rdi
0x1800098e7  retn
```
