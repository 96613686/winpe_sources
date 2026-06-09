# RemoteOpenRPCDebugEndpointInfoEnumeration

- ea: `0x180007c50`
- end: `0x180007cde`
- name: `RemoteOpenRPCDebugEndpointInfoEnumeration`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180002a00`
- `0x180005f48`
- `0x180007c50`
- `0x1800098e4`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180007c7b`
- `RPCRT4!RpcRaiseException` at `0x180007c97`
- `RPCRT4!RpcRaiseException` at `0x180007cc7`
- `RPCRT4!RpcRaiseException` at `0x180007c7b`
- `RPCRT4!RpcRaiseException` at `0x180007c97`
- `RPCRT4!RpcRaiseException` at `0x180007cc7`

## pseudocode

```c
__int64 __fastcall RemoteOpenRPCDebugEndpointInfoEnumeration(__int64 a1, void *****a2, __int16 a3, char *a4)
{
  char *v5; // rdi
  void ****v7; // rax
  void ****v8; // rbx
  RPC_STATUS v9; // edi

  *a2 = 0;
  v5 = a4;
  if ( a4 && a4[a3 - 1] )
    RpcRaiseException(87);
  v7 = (void ****)operator new(0x10u);
  v8 = v7;
  if ( !v7 )
    RpcRaiseException(14);
  *(_DWORD *)v7 = 1;
  if ( a3 <= 0 )
    v5 = 0;
  v9 = OpenRPCDebugEndpointInfoEnumeration(v5, v7 + 1);
  if ( v9 )
  {
    operator delete(v8);
    RpcRaiseException(v9);
  }
  *a2 = v8;
  return 0;
}

```

## disassembly

```asm
0x180007c50  push    rbx
0x180007c52  push    rbp
0x180007c53  push    rsi
0x180007c54  push    rdi
0x180007c55  push    r14
0x180007c57  sub     rsp, 20h
0x180007c5b  xor     r14d, r14d
0x180007c5e  movsx   rbp, r8w
0x180007c62  mov     [rdx], r14
0x180007c65  mov     rdi, r9
0x180007c68  mov     rsi, rdx
0x180007c6b  test    r9, r9
0x180007c6e  jz      short loc_180007C82
0x180007c70  cmp     [rbp+r9-1], r14b
0x180007c75  jz      short loc_180007C82
0x180007c77  lea     ecx, [r14+57h]; exception
0x180007c7b  call    cs:__imp_RpcRaiseException
0x180007c81  int     3; Trap to Debugger
0x180007c82  mov     ecx, 10h; unsigned __int64
0x180007c87  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007c8c  mov     rbx, rax
0x180007c8f  test    rax, rax
0x180007c92  jnz     short loc_180007C9E
0x180007c94  lea     ecx, [rax+0Eh]; exception
0x180007c97  call    cs:__imp_RpcRaiseException
0x180007c9d  int     3; Trap to Debugger
0x180007c9e  test    bp, bp
0x180007ca1  mov     dword ptr [rax], 1
0x180007ca7  lea     rdx, [rax+8]; void **
0x180007cab  cmovle  rdi, r14
0x180007caf  mov     rcx, rdi; Src
0x180007cb2  call    ?OpenRPCDebugEndpointInfoEnumeration@@YAJPEADPEAPEAX@Z; OpenRPCDebugEndpointInfoEnumeration(char *,void * *)
0x180007cb7  mov     edi, eax
0x180007cb9  test    eax, eax
0x180007cbb  jz      short loc_180007CCE
0x180007cbd  mov     rcx, rbx; void *
0x180007cc0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007cc5  mov     ecx, edi; exception
0x180007cc7  call    cs:__imp_RpcRaiseException
0x180007ccd  int     3; Trap to Debugger
0x180007cce  mov     [rsi], rbx
0x180007cd1  xor     eax, eax
0x180007cd3  add     rsp, 20h
0x180007cd7  pop     r14
0x180007cd9  pop     rdi
0x180007cda  pop     rsi
0x180007cdb  pop     rbp
0x180007cdc  pop     rbx
0x180007cdd  retn
```
