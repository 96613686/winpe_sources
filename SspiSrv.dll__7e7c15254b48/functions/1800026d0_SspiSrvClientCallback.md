# SspiSrvClientCallback

- ea: `0x1800026d0`
- end: `0x1800027b5`
- name: `SspiSrvClientCallback`
- size: `229`
- prototype: `CLIENT_CALL_RETURN __fastcall(unsigned int, __int64, __int64, __int64, __int64, _OWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800026d0`
- `0x180003340`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18000346a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000346a`
- `RPCRT4!NdrClientCall3` at `0x18000275c`
- `RPCRT4!NdrClientCall3` at `0x18000275c`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000276f`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000276f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall SspiSrvClientCallback(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _OWORD *a6)
{
  CLIENT_CALL_RETURN result; // rax
  __int128 v7; // [rsp+70h] [rbp-48h] BYREF
  _DWORD v8[2]; // [rsp+80h] [rbp-38h] BYREF
  __int64 v9; // [rsp+88h] [rbp-30h]

  v7 = 0;
  v8[0] = *(_DWORD *)a5;
  v8[1] = *(_DWORD *)(a5 + 4);
  v9 = *(_QWORD *)(a5 + 8);
  result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, a1, a2, a3, a4, v8, &v7).Pointer;
  if ( SLODWORD(result.Simple) >= 0 )
    *a6 = v7;
  return result;
}

```

## disassembly

```asm
0x1800026d0  mov     r11, rsp
0x1800026d3  push    rbx
0x1800026d4  push    rdi
0x1800026d5  sub     rsp, 0A8h
0x1800026dc  mov     rax, cs:__security_cookie
0x1800026e3  xor     rax, rsp
0x1800026e6  mov     [rsp+0B8h+var_28], rax
0x1800026ee  mov     r10, r9
0x1800026f1  mov     r9d, ecx
0x1800026f4  mov     rdi, [rsp+0B8h+arg_28]
0x1800026fc  mov     rcx, [rsp+0B8h+arg_20]
0x180002704  mov     rbx, rdi
0x180002707  mov     [rsp+0B8h+var_58], rbx
0x18000270c  xorps   xmm0, xmm0
0x18000270f  movups  [rsp+0B8h+var_48], xmm0
0x180002714  mov     eax, [rcx]
0x180002716  mov     [r11-38h], eax
0x18000271a  mov     eax, [rcx+4]
0x18000271d  mov     [r11-34h], eax
0x180002721  mov     rax, [rcx+8]
0x180002725  mov     [r11-30h], rax
0x180002729  mov     qword ptr [r11-60h], 0
0x180002731  lea     rax, [r11-48h]
0x180002735  mov     [r11-78h], rax
0x180002739  lea     rax, [r11-38h]
0x18000273d  mov     [r11-80h], rax
0x180002741  mov     [rsp+0B8h+var_88], r10
0x180002746  mov     [rsp+0B8h+var_90], r8
0x18000274b  mov     [rsp+0B8h+var_98], rdx
0x180002750  xor     r8d, r8d; pReturnValue
0x180002753  xor     edx, edx; nProcNum
0x180002755  lea     rcx, pProxyInfo; pProxyInfo
0x18000275c  call    cs:__imp_NdrClientCall3
0x180002762  mov     [rsp+0B8h+var_60], rax
0x180002767  mov     [rsp+0B8h+var_68], eax
0x18000276b  jmp     short loc_180002781
0x18000276d  mov     ecx, eax; Status
0x18000276f  call    cs:__imp_I_RpcMapWin32Status
0x180002775  mov     [rsp+0B8h+var_68], eax
0x180002779  mov     rbx, [rsp+0B8h+var_58]
0x18000277e  mov     rdi, rbx
0x180002781  test    eax, eax
0x180002783  js      short loc_18000279B
0x180002785  mov     ecx, dword ptr [rsp+0B8h+var_48]
0x180002789  mov     [rdi], ecx
0x18000278b  mov     ecx, dword ptr [rsp+0B8h+var_48+4]
0x18000278f  mov     [rbx+4], ecx
0x180002792  mov     rcx, qword ptr [rsp+0B8h+var_48+8]
0x180002797  mov     [rbx+8], rcx
0x18000279b  mov     rcx, [rsp+0B8h+var_28]
0x1800027a3  xor     rcx, rsp; StackCookie
0x1800027a6  call    __security_check_cookie
0x1800027ab  add     rsp, 0A8h
0x1800027b2  pop     rdi
0x1800027b3  pop     rbx
0x1800027b4  retn
0x18000345c  push    rbp
0x18000345e  sub     rsp, 50h
0x180003462  mov     rbp, rdx
0x180003465  mov     rcx, [rcx]
0x180003468  mov     ecx, [rcx]; ExceptionCode
0x18000346a  call    cs:__imp_I_RpcExceptionFilter
0x180003470  nop
0x180003471  add     rsp, 50h
0x180003475  pop     rbp
0x180003476  retn
```
