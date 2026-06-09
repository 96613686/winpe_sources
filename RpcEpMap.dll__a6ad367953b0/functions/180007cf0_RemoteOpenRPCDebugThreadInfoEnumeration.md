# RemoteOpenRPCDebugThreadInfoEnumeration

- ea: `0x180007cf0`
- end: `0x180007da3`
- name: `RemoteOpenRPCDebugThreadInfoEnumeration`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180002a00`
- `0x180005f48`
- `0x180007cf0`
- `0x180009df8`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180007d22`
- `RPCRT4!RpcRaiseException` at `0x180007d88`
- `RPCRT4!RpcRaiseException` at `0x180007d22`
- `RPCRT4!RpcRaiseException` at `0x180007d88`

## pseudocode

```c
__int64 __fastcall RemoteOpenRPCDebugThreadInfoEnumeration(__int64 a1, _QWORD *a2, unsigned int a3, int a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rsi
  void **v9; // rax
  void **v10; // rdi
  RPC_STATUS v11; // ebx
  RPC_STATUS v12; // eax
  __int64 result; // rax

  *a2 = 0;
  v7 = operator new(0x10u);
  v8 = v7;
  if ( !v7 )
    RpcRaiseException(14);
  *(_DWORD *)v7 = 2;
  v7[1] = 0;
  v9 = (void **)operator new(0x10u);
  v10 = v9;
  if ( !v9 )
  {
    v11 = 14;
    goto LABEL_9;
  }
  *(_DWORD *)v9 = a3;
  *((_DWORD *)v9 + 1) = a4;
  v12 = OpenRPCServerDebugInfo(a3, v9 + 1);
  v11 = v12;
  if ( v12 == 2 )
  {
    operator delete(v10);
    v11 = 1;
    goto LABEL_9;
  }
  if ( v12 )
  {
    operator delete(v10);
LABEL_9:
    operator delete(v8);
    RpcRaiseException(v11);
  }
  v8[1] = v10;
  result = 0;
  *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x180007cf0  push    rbx
0x180007cf2  push    rbp
0x180007cf3  push    rsi
0x180007cf4  push    rdi
0x180007cf5  push    r14
0x180007cf7  sub     rsp, 20h
0x180007cfb  mov     edi, 10h
0x180007d00  mov     qword ptr [rdx], 0
0x180007d07  mov     ecx, edi; unsigned __int64
0x180007d09  mov     ebp, r9d
0x180007d0c  mov     ebx, r8d
0x180007d0f  mov     r14, rdx
0x180007d12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007d17  mov     rsi, rax
0x180007d1a  test    rax, rax
0x180007d1d  jnz     short loc_180007D29
0x180007d1f  lea     ecx, [rdi-2]; exception
0x180007d22  call    cs:__imp_RpcRaiseException
0x180007d28  int     3; Trap to Debugger
0x180007d29  mov     dword ptr [rax], 2
0x180007d2f  mov     rcx, rdi; unsigned __int64
0x180007d32  mov     qword ptr [rax+8], 0
0x180007d3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007d3f  mov     rdi, rax
0x180007d42  test    rax, rax
0x180007d45  jnz     short loc_180007D4C
0x180007d47  lea     ebx, [rax+0Eh]
0x180007d4a  jmp     short loc_180007D7E
0x180007d4c  lea     rdx, [rax+8]; void **
0x180007d50  mov     [rax], ebx
0x180007d52  mov     ecx, ebx; unsigned int
0x180007d54  mov     [rax+4], ebp
0x180007d57  call    ?OpenRPCServerDebugInfo@@YAJKPEAPEAX@Z; OpenRPCServerDebugInfo(ulong,void * *)
0x180007d5c  mov     ebx, eax
0x180007d5e  cmp     eax, 2
0x180007d61  jnz     short loc_180007D72
0x180007d63  mov     rcx, rdi; void *
0x180007d66  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007d6b  mov     ebx, 1
0x180007d70  jmp     short loc_180007D7E
0x180007d72  test    eax, eax
0x180007d74  jz      short loc_180007D8F
0x180007d76  mov     rcx, rdi; void *
0x180007d79  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007d7e  mov     rcx, rsi; void *
0x180007d81  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007d86  mov     ecx, ebx; exception
0x180007d88  call    cs:__imp_RpcRaiseException
0x180007d8e  int     3; Trap to Debugger
0x180007d8f  mov     [rsi+8], rdi
0x180007d93  xor     eax, eax
0x180007d95  mov     [r14], rsi
0x180007d98  add     rsp, 20h
0x180007d9c  pop     r14
0x180007d9e  pop     rdi
0x180007d9f  pop     rsi
0x180007da0  pop     rbp
0x180007da1  pop     rbx
0x180007da2  retn
```
