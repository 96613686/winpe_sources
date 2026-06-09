# CDsmDevice::_DsmOpenDevice(ushort const *)

- ea: `0x18000ca1c`
- end: `0x18000cb2a`
- name: `?_DsmOpenDevice@CDsmDevice@@AEAAJPEBG@Z`
- size: `270`
- prototype: `__int64 __fastcall(CDsmDevice *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000c070`

## callees

- `0x1800017c0`
- `0x18000ca1c`
- `0x18000ce68`
- `0x18000d524`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000caa9`
- `RPCRT4!NdrClientCall3` at `0x18000caa9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000ca50`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000ca50`

## pseudocode

```c
__int64 __fastcall CDsmDevice::_DsmOpenDevice(CDsmDevice *this, const unsigned __int16 *a2)
{
  HRESULT Pointer; // ebx
  _QWORD *v4; // rsi
  CLIENT_CALL_RETURN v5; // rdx
  CLIENT_CALL_RETURN v6; // r8
  int v8; // [rsp+30h] [rbp-38h]
  GUID pclsid; // [rsp+48h] [rbp-20h] BYREF

  pclsid = 0;
  Pointer = CLSIDFromString(a2, &pclsid);
  if ( Pointer >= 0 )
  {
    v4 = (_QWORD *)((char *)this + 104);
    if ( *v4 )
    {
      return (unsigned int)-2147467259;
    }
    else
    {
      v8 = 0;
      StartDsmService();
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&stru_1800117E0,
                                0,
                                0,
                                DsmRpcNotify_v1_0_c_ifspec,
                                &pclsid,
                                v4,
                                v8,
                                0,
                                v4).Pointer;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_iD)(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (CLIENT_CALL_RETURN)v5.Simple,
          (CLIENT_CALL_RETURN)v6.Simple,
          *v4,
          Pointer);
    }
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000ca1c  mov     [rsp+arg_10], rbx
0x18000ca21  mov     [rsp+arg_18], rsi
0x18000ca26  push    rdi
0x18000ca27  sub     rsp, 60h
0x18000ca2b  mov     rax, cs:__security_cookie
0x18000ca32  xor     rax, rsp
0x18000ca35  mov     [rsp+68h+var_10], rax
0x18000ca3a  mov     rax, rdx
0x18000ca3d  mov     rsi, rcx
0x18000ca40  xorps   xmm0, xmm0
0x18000ca43  movups  xmmword ptr [rsp+68h+pclsid.Data1], xmm0
0x18000ca48  lea     rdx, [rsp+68h+pclsid]; pclsid
0x18000ca4d  mov     rcx, rax; lpsz
0x18000ca50  call    cs:__imp_CLSIDFromString
0x18000ca56  mov     ebx, eax
0x18000ca58  test    eax, eax
0x18000ca5a  js      loc_18000CB09
0x18000ca60  add     rsi, 68h ; 'h'
0x18000ca64  mov     [rsp+68h+var_28], rsi
0x18000ca69  cmp     qword ptr [rsi], 0
0x18000ca6d  jnz     loc_18000CB04
0x18000ca73  mov     [rsp+68h+var_38], 0
0x18000ca7b  call    ?StartDsmService@@YAJXZ; StartDsmService(void)
0x18000ca80  xor     edi, edi
0x18000ca82  mov     [rsp+68h+var_30], rdi
0x18000ca87  mov     [rsp+68h+var_40], rsi
0x18000ca8c  lea     rax, [rsp+68h+pclsid]
0x18000ca91  mov     [rsp+68h+var_48], rax
0x18000ca96  mov     r9, cs:DsmRpcNotify_v1_0_c_ifspec
0x18000ca9d  xor     r8d, r8d; pReturnValue
0x18000caa0  xor     edx, edx; nProcNum
0x18000caa2  lea     rcx, stru_1800117E0; pProxyInfo
0x18000caa9  call    cs:__imp_NdrClientCall3
0x18000caaf  mov     rbx, rax
0x18000cab2  mov     [rsp+68h+var_30], rax
0x18000cab7  mov     [rsp+68h+var_38], eax
0x18000cabb  jmp     short loc_18000CAC8
0x18000cabd  mov     edi, eax
0x18000cabf  mov     ebx, [rsp+68h+var_38]
0x18000cac3  mov     rsi, [rsp+68h+var_28]
0x18000cac8  test    edi, edi
0x18000caca  jz      short loc_18000CAD9
0x18000cacc  jle     short loc_18000CAD7
0x18000cace  movzx   edi, di
0x18000cad1  or      edi, 80070000h
0x18000cad7  mov     ebx, edi
0x18000cad9  lea     rax, WPP_GLOBAL_Control
0x18000cae0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cae7  cmp     rcx, rax
0x18000caea  jz      short loc_18000CB09
0x18000caec  test    byte ptr [rcx+1Ch], 1
0x18000caf0  jz      short loc_18000CB09
0x18000caf2  mov     dword ptr [rsp+68h+var_48], ebx
0x18000caf6  mov     r9, [rsi]
0x18000caf9  mov     rcx, [rcx+10h]
0x18000cafd  call    WPP_SF_iD
0x18000cb02  jmp     short loc_18000CB09
0x18000cb04  mov     ebx, 80004005h
0x18000cb09  mov     eax, ebx
0x18000cb0b  mov     rcx, [rsp+68h+var_10]
0x18000cb10  xor     rcx, rsp; StackCookie
0x18000cb13  call    __security_check_cookie
0x18000cb18  lea     r11, [rsp+68h+var_8]
0x18000cb1d  mov     rbx, [r11+20h]
0x18000cb21  mov     rsi, [r11+28h]
0x18000cb25  mov     rsp, r11
0x18000cb28  pop     rdi
0x18000cb29  retn
```
