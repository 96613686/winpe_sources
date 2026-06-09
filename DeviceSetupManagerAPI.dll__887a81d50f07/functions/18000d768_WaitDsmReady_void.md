# WaitDsmReady(void)

- ea: `0x18000d768`
- end: `0x18000d82a`
- name: `?WaitDsmReady@@YAJXZ`
- size: `194`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d524`

## callees

- `0x1800092c0`
- `0x180009d20`
- `0x18000d768`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x18000d7d4`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000d7d4`
- `RPCRT4!NdrClientCall3` at `0x18000d7be`
- `RPCRT4!NdrClientCall3` at `0x18000d7be`

## pseudocode

```c
__int64 WaitDsmReady(void)
{
  unsigned int Pointer; // eax
  unsigned int v1; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b8e3509543d83c1db711f9919e1dba96_Traceguids);
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&stru_1800116C0,
                            5u,
                            0,
                            DsmRpcControl_v1_0_c_ifspec).Pointer;
  v1 = Pointer;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b8e3509543d83c1db711f9919e1dba96_Traceguids, Pointer);
  return v1;
}

```

## disassembly

```asm
0x18000d768  mov     [rsp+arg_8], rbx
0x18000d76d  push    rdi
0x18000d76e  sub     rsp, 30h
0x18000d772  lea     rdi, WPP_GLOBAL_Control
0x18000d779  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d780  cmp     rcx, rdi
0x18000d783  jz      short loc_18000D7A0
0x18000d785  test    byte ptr [rcx+1Ch], 1
0x18000d789  jz      short loc_18000D7A0
0x18000d78b  mov     edx, 0Ch
0x18000d790  lea     r8, WPP_b8e3509543d83c1db711f9919e1dba96_Traceguids
0x18000d797  mov     rcx, [rcx+10h]
0x18000d79b  call    WPP_SF_
0x18000d7a0  mov     [rsp+38h+arg_0], 0
0x18000d7a9  mov     r9, cs:DsmRpcControl_v1_0_c_ifspec
0x18000d7b0  xor     r8d, r8d; pReturnValue
0x18000d7b3  lea     edx, [r8+5]; nProcNum
0x18000d7b7  lea     rcx, stru_1800116C0; pProxyInfo
0x18000d7be  call    cs:__imp_NdrClientCall3
0x18000d7c4  mov     rbx, rax
0x18000d7c7  mov     [rsp+38h+arg_0], rax
0x18000d7cc  mov     [rsp+38h+var_18], eax
0x18000d7d0  jmp     short loc_18000D7F3
0x18000d7d2  mov     ecx, eax; Status
0x18000d7d4  call    cs:__imp_I_RpcMapWin32Status
0x18000d7da  test    eax, eax
0x18000d7dc  jle     short loc_18000D7E6
0x18000d7de  movzx   eax, ax
0x18000d7e1  or      eax, 80070000h
0x18000d7e6  mov     ebx, eax
0x18000d7e8  mov     [rsp+38h+var_18], eax
0x18000d7ec  lea     rdi, WPP_GLOBAL_Control
0x18000d7f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7fa  cmp     rcx, rdi
0x18000d7fd  jz      short loc_18000D81D
0x18000d7ff  test    byte ptr [rcx+1Ch], 1
0x18000d803  jz      short loc_18000D81D
0x18000d805  mov     edx, 0Dh
0x18000d80a  mov     r9d, ebx
0x18000d80d  lea     r8, WPP_b8e3509543d83c1db711f9919e1dba96_Traceguids
0x18000d814  mov     rcx, [rcx+10h]
0x18000d818  call    WPP_SF_D
0x18000d81d  mov     eax, ebx
0x18000d81f  mov     rbx, [rsp+38h+arg_8]
0x18000d824  add     rsp, 30h
0x18000d828  pop     rdi
0x18000d829  retn
```
