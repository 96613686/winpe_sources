# HamTerminateApplicationHost

- ea: `0x180010190`
- end: `0x180010281`
- name: `HamTerminateApplicationHost`
- size: `241`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, __int64, void *, int, int, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180010190`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800101be`
- `ntdll!RtlLengthSid` at `0x180010247`
- `ntdll!RtlLengthSid` at `0x1800101be`
- `ntdll!RtlLengthSid` at `0x180010247`
- `RPCRT4!NdrClientCall3` at `0x180010207`
- `RPCRT4!NdrClientCall3` at `0x180010207`
- `RPCRT4!RpcExceptionFilter` at `0x18001b5d4`
- `RPCRT4!RpcExceptionFilter` at `0x18001b5d4`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001021d`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001021d`
- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcTerminateApplicationHost` at `0x180010279`
- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcTerminateApplicationHost` at `0x180010279`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HamTerminateApplicationHost(_QWORD *a1, __int64 a2, void *a3, int a4, int a5, __int64 a6)
{
  CLIENT_CALL_RETURN result; // rax
  ULONG v11; // eax
  ULONG v12; // [rsp+30h] [rbp-48h]

  if ( a1[1] )
  {
    v11 = RtlLengthSid(a3);
    result.Simple = HampInProcTerminateApplicationHost(a1[1], a2, a3, v11, a4, a5, a6);
  }
  else
  {
    v12 = RtlLengthSid(a3);
    result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x12u, 0, *a1, a2, a3, v12, a4, a5, a6).Pointer;
  }
  if ( SLODWORD(result.Simple) >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180010190  mov     [rsp+arg_8], rbx
0x180010195  mov     [rsp+arg_10], rsi
0x18001019a  push    rdi
0x18001019b  push    r14
0x18001019d  push    r15
0x18001019f  sub     rsp, 60h
0x1800101a3  mov     r14d, r9d
0x1800101a6  mov     rsi, r8
0x1800101a9  mov     r15, rdx
0x1800101ac  mov     rdi, rcx
0x1800101af  xor     ebx, ebx
0x1800101b1  cmp     [rcx+8], rbx
0x1800101b5  jnz     loc_180010244
0x1800101bb  mov     rcx, r8; Sid
0x1800101be  call    cs:__imp_RtlLengthSid
0x1800101c4  mov     [rsp+78h+arg_0], rbx
0x1800101cc  mov     rcx, [rsp+78h+arg_28]
0x1800101d4  mov     [rsp+78h+var_30], rcx
0x1800101d9  mov     ecx, [rsp+78h+arg_20]
0x1800101e0  mov     [rsp+78h+var_38], ecx
0x1800101e4  mov     [rsp+78h+var_40], r14d
0x1800101e9  mov     dword ptr [rsp+78h+var_48], eax
0x1800101ed  mov     [rsp+78h+var_50], rsi
0x1800101f2  mov     [rsp+78h+var_58], r15
0x1800101f7  mov     r9, [rdi]
0x1800101fa  xor     r8d, r8d; pReturnValue
0x1800101fd  lea     edx, [rbx+12h]; nProcNum
0x180010200  lea     rcx, pProxyInfo; pProxyInfo
0x180010207  call    cs:__imp_NdrClientCall3
0x18001020d  mov     [rsp+78h+arg_0], rax
0x180010215  mov     [rsp+78h+var_28], eax
0x180010219  jmp     short loc_180010229
0x18001021b  mov     ecx, eax; Status
0x18001021d  call    cs:__imp_I_RpcMapWin32Status
0x180010223  mov     [rsp+78h+var_28], eax
0x180010227  xor     ebx, ebx
0x180010229  test    eax, eax
0x18001022b  cmovns  eax, ebx
0x18001022e  lea     r11, [rsp+78h+var_18]
0x180010233  mov     rbx, [r11+28h]
0x180010237  mov     rsi, [r11+30h]
0x18001023b  mov     rsp, r11
0x18001023e  pop     r15
0x180010240  pop     r14
0x180010242  pop     rdi
0x180010243  retn
0x180010244  mov     rcx, rsi; Sid
0x180010247  call    cs:__imp_RtlLengthSid
0x18001024d  mov     r10, [rsp+78h+arg_28]
0x180010255  mov     [rsp+78h+var_48], r10
0x18001025a  mov     r9d, [rsp+78h+arg_20]
0x180010262  mov     dword ptr [rsp+78h+var_50], r9d
0x180010267  mov     dword ptr [rsp+78h+var_58], r14d
0x18001026c  mov     r9d, eax
0x18001026f  mov     r8, rsi
0x180010272  mov     rdx, r15
0x180010275  mov     rcx, [rdi+8]
0x180010279  call    cs:__imp_HampInProcTerminateApplicationHost
0x18001027f  jmp     short loc_180010229
0x18001b5c6  push    rbp
0x18001b5c8  sub     rsp, 50h
0x18001b5cc  mov     rbp, rdx
0x18001b5cf  mov     rcx, [rcx]
0x18001b5d2  mov     ecx, [rcx]; ExceptionCode
0x18001b5d4  call    cs:__imp_RpcExceptionFilter
0x18001b5da  nop
0x18001b5db  add     rsp, 50h
0x18001b5df  pop     rbp
0x18001b5e0  retn
```
