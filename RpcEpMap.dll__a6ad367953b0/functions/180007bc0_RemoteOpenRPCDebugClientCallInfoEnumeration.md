# RemoteOpenRPCDebugClientCallInfoEnumeration

- ea: `0x180007bc0`
- end: `0x180007c42`
- name: `RemoteOpenRPCDebugClientCallInfoEnumeration`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180002a00`
- `0x180005f48`
- `0x180007bc0`
- `0x180009844`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180007bee`
- `RPCRT4!RpcRaiseException` at `0x180007c2d`
- `RPCRT4!RpcRaiseException` at `0x180007bee`
- `RPCRT4!RpcRaiseException` at `0x180007c2d`

## pseudocode

```c
__int64 __fastcall RemoteOpenRPCDebugClientCallInfoEnumeration(
        __int64 a1,
        void ***a2,
        int a3,
        int a4,
        int a5,
        unsigned int a6)
{
  void **v9; // rax
  void **v10; // rbx
  RPC_STATUS v11; // esi

  *a2 = 0;
  v9 = (void **)operator new(0x10u);
  v10 = v9;
  if ( !v9 )
    RpcRaiseException(14);
  *(_DWORD *)v9 = 3;
  v11 = OpenRPCDebugClientCallInfoEnumeration(a3, a4, a5, a6, v9 + 1);
  if ( v11 )
  {
    operator delete(v10);
    RpcRaiseException(v11);
  }
  *a2 = v10;
  return 0;
}

```

## disassembly

```asm
0x180007bc0  push    rbx
0x180007bc2  push    rbp
0x180007bc3  push    rsi
0x180007bc4  push    rdi
0x180007bc5  sub     rsp, 38h
0x180007bc9  mov     ecx, 10h; unsigned __int64
0x180007bce  mov     qword ptr [rdx], 0
0x180007bd5  mov     esi, r9d
0x180007bd8  mov     ebp, r8d
0x180007bdb  mov     rdi, rdx
0x180007bde  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007be3  mov     rbx, rax
0x180007be6  test    rax, rax
0x180007be9  jnz     short loc_180007BF5
0x180007beb  lea     ecx, [rax+0Eh]; exception
0x180007bee  call    cs:__imp_RpcRaiseException
0x180007bf4  int     3; Trap to Debugger
0x180007bf5  mov     r9d, [rsp+58h+arg_28]; unsigned int
0x180007bfd  mov     edx, esi; unsigned int
0x180007bff  mov     r8d, [rsp+58h+arg_20]; int
0x180007c07  mov     ecx, ebp; unsigned int
0x180007c09  mov     dword ptr [rax], 3
0x180007c0f  add     rax, 8
0x180007c13  mov     [rsp+58h+var_38], rax; void **
0x180007c18  call    ?OpenRPCDebugClientCallInfoEnumeration@@YAJKKHKPEAPEAX@Z; OpenRPCDebugClientCallInfoEnumeration(ulong,ulong,int,ulong,void * *)
0x180007c1d  mov     esi, eax
0x180007c1f  test    eax, eax
0x180007c21  jz      short loc_180007C34
0x180007c23  mov     rcx, rbx; void *
0x180007c26  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007c2b  mov     ecx, esi; exception
0x180007c2d  call    cs:__imp_RpcRaiseException
0x180007c33  int     3; Trap to Debugger
0x180007c34  mov     [rdi], rbx
0x180007c37  xor     eax, eax
0x180007c39  add     rsp, 38h
0x180007c3d  pop     rdi
0x180007c3e  pop     rsi
0x180007c3f  pop     rbp
0x180007c40  pop     rbx
0x180007c41  retn
```
