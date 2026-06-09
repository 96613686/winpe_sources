# HamCreateExtendedExecution

- ea: `0x18000bed0`
- end: `0x18000bfd7`
- name: `HamCreateExtendedExecution`
- size: `263`
- prototype: `__int64 __fastcall(_QWORD *, __int64, int, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180004550`
- `0x180004a70`
- `0x180009d40`
- `0x18000bed0`
- `0x18000bfe0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000bf95`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000bf95`
- `RPCRT4!NdrClientCall3` at `0x18000bf3f`
- `RPCRT4!NdrClientCall3` at `0x18000bf3f`
- `RPCRT4!RpcExceptionFilter` at `0x18001b320`
- `RPCRT4!RpcExceptionFilter` at `0x18001b320`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000bf55`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000bf55`

## pseudocode

```c
__int64 __fastcall HamCreateExtendedExecution(_QWORD *a1, __int64 a2, int a3, __int64 a4, __int64 *a5)
{
  int Pointer; // ebx
  CLIENT_CALL_RETURN v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v13; // [rsp+48h] [rbp-40h] BYREF
  CLIENT_CALL_RETURN v14; // [rsp+50h] [rbp-38h]
  __int64 v15; // [rsp+90h] [rbp+8h] BYREF

  v15 = 0;
  v13 = -1;
  Pointer = HampConnectionObjectCreate(a2, a1, &v15);
  if ( Pointer >= 0 )
  {
    v14.Simple = 0;
    v9.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DF70, 3u, 0, *a1, a3, a4, &v13).Pointer;
    Pointer = (int)v9.Pointer;
    v14.Pointer = v9.Pointer;
    if ( SLODWORD(v9.Simple) >= 0 )
    {
      v10 = v15;
      *(_QWORD *)(v15 + 48) = v13;
      v11 = *(_QWORD *)(v10 + 40);
      HampIpcChannelAcquireLock(v11);
      HampIpcChannelAddCallbackUnsafe(v10);
      *(_DWORD *)(v11 + 16) = 0;
      RtlReleaseSRWLockExclusive(v11 + 8);
      v15 = 0;
      *a5 = v13;
      Pointer = 0;
    }
  }
  if ( v15 )
    HamFreeBuffer(v15);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000bed0  mov     r11, rsp
0x18000bed3  push    rbx
0x18000bed4  push    rsi
0x18000bed5  push    rdi
0x18000bed6  push    r14
0x18000bed8  sub     rsp, 68h
0x18000bedc  mov     rsi, r9
0x18000bedf  mov     r14d, r8d
0x18000bee2  mov     rax, rdx
0x18000bee5  mov     rdi, rcx
0x18000bee8  mov     qword ptr [r11+8], 0
0x18000bef0  mov     qword ptr [r11-40h], 0FFFFFFFFFFFFFFFFh
0x18000bef8  lea     r8, [r11+8]
0x18000befc  mov     rdx, rcx
0x18000beff  mov     rcx, rax
0x18000bf02  call    HampConnectionObjectCreate
0x18000bf07  mov     ebx, eax
0x18000bf09  test    eax, eax
0x18000bf0b  js      loc_18000BFB9
0x18000bf11  mov     [rsp+88h+var_38], 0
0x18000bf1a  lea     rax, [rsp+88h+var_40]
0x18000bf1f  mov     [rsp+88h+var_58], rax
0x18000bf24  mov     [rsp+88h+var_60], rsi
0x18000bf29  mov     [rsp+88h+var_68], r14d
0x18000bf2e  mov     r9, [rdi]
0x18000bf31  xor     r8d, r8d; pReturnValue
0x18000bf34  lea     edx, [r8+3]; nProcNum
0x18000bf38  lea     rcx, stru_18001DF70; pProxyInfo
0x18000bf3f  call    cs:__imp_NdrClientCall3
0x18000bf45  mov     rbx, rax
0x18000bf48  mov     [rsp+88h+var_38], rax
0x18000bf4d  mov     [rsp+88h+var_48], eax
0x18000bf51  jmp     short loc_18000BF61
0x18000bf53  mov     ecx, eax; Status
0x18000bf55  call    cs:__imp_I_RpcMapWin32Status
0x18000bf5b  mov     ebx, eax
0x18000bf5d  mov     [rsp+88h+var_48], eax
0x18000bf61  test    ebx, ebx
0x18000bf63  js      short loc_18000BFB9
0x18000bf65  mov     rdi, [rsp+88h+arg_0]
0x18000bf6d  mov     rax, [rsp+88h+var_40]
0x18000bf72  mov     [rdi+30h], rax
0x18000bf76  mov     rbx, [rdi+28h]
0x18000bf7a  mov     rcx, rbx
0x18000bf7d  call    HampIpcChannelAcquireLock
0x18000bf82  mov     rcx, rdi
0x18000bf85  call    HampIpcChannelAddCallbackUnsafe
0x18000bf8a  mov     dword ptr [rbx+10h], 0
0x18000bf91  lea     rcx, [rbx+8]
0x18000bf95  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000bf9b  mov     [rsp+88h+arg_0], 0
0x18000bfa7  mov     rcx, [rsp+88h+var_40]
0x18000bfac  mov     rax, [rsp+88h+arg_20]
0x18000bfb4  mov     [rax], rcx
0x18000bfb7  xor     ebx, ebx
0x18000bfb9  mov     rcx, [rsp+88h+arg_0]
0x18000bfc1  test    rcx, rcx
0x18000bfc4  jz      short loc_18000BFCB
0x18000bfc6  call    HamFreeBuffer
0x18000bfcb  mov     eax, ebx
0x18000bfcd  add     rsp, 68h
0x18000bfd1  pop     r14
0x18000bfd3  pop     rdi
0x18000bfd4  pop     rsi
0x18000bfd5  pop     rbx
0x18000bfd6  retn
0x18001b312  push    rbp
0x18001b314  sub     rsp, 40h
0x18001b318  mov     rbp, rdx
0x18001b31b  mov     rcx, [rcx]
0x18001b31e  mov     ecx, [rcx]; ExceptionCode
0x18001b320  call    cs:__imp_RpcExceptionFilter
0x18001b326  nop
0x18001b327  add     rsp, 40h
0x18001b32b  pop     rbp
0x18001b32c  retn
```
