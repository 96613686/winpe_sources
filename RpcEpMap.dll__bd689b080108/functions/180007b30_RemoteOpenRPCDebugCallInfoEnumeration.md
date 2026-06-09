# RemoteOpenRPCDebugCallInfoEnumeration

- ea: `0x180007b30`
- end: `0x180007bb2`
- name: `RemoteOpenRPCDebugCallInfoEnumeration`
- size: `130`
- prototype: `__int64 __fastcall(__int64, void ***, int, int, int, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180002a00`
- `0x180005f48`
- `0x180007b30`
- `0x180009844`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180007b5e`
- `RPCRT4!RpcRaiseException` at `0x180007b9d`
- `RPCRT4!RpcRaiseException` at `0x180007b5e`
- `RPCRT4!RpcRaiseException` at `0x180007b9d`

## pseudocode

```c
__int64 __fastcall RemoteOpenRPCDebugCallInfoEnumeration(
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
  *(_DWORD *)v9 = 0;
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
0x180007b30  push    rbx
0x180007b32  push    rbp
0x180007b33  push    rsi
0x180007b34  push    rdi
0x180007b35  sub     rsp, 38h
0x180007b39  mov     ecx, 10h; unsigned __int64
0x180007b3e  mov     qword ptr [rdx], 0
0x180007b45  mov     esi, r9d
0x180007b48  mov     ebp, r8d
0x180007b4b  mov     rdi, rdx
0x180007b4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007b53  mov     rbx, rax
0x180007b56  test    rax, rax
0x180007b59  jnz     short loc_180007B65
0x180007b5b  lea     ecx, [rax+0Eh]; exception
0x180007b5e  call    cs:__imp_RpcRaiseException
0x180007b64  int     3; Trap to Debugger
0x180007b65  mov     r9d, [rsp+58h+arg_28]; unsigned int
0x180007b6d  mov     edx, esi; unsigned int
0x180007b6f  mov     r8d, [rsp+58h+arg_20]; int
0x180007b77  mov     ecx, ebp; unsigned int
0x180007b79  mov     dword ptr [rax], 0
0x180007b7f  add     rax, 8
0x180007b83  mov     [rsp+58h+var_38], rax; void **
0x180007b88  call    ?OpenRPCDebugClientCallInfoEnumeration@@YAJKKHKPEAPEAX@Z; OpenRPCDebugClientCallInfoEnumeration(ulong,ulong,int,ulong,void * *)
0x180007b8d  mov     esi, eax
0x180007b8f  test    eax, eax
0x180007b91  jz      short loc_180007BA4
0x180007b93  mov     rcx, rbx; void *
0x180007b96  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007b9b  mov     ecx, esi; exception
0x180007b9d  call    cs:__imp_RpcRaiseException
0x180007ba3  int     3; Trap to Debugger
0x180007ba4  mov     [rdi], rbx
0x180007ba7  xor     eax, eax
0x180007ba9  add     rsp, 38h
0x180007bad  pop     rdi
0x180007bae  pop     rsi
0x180007baf  pop     rbp
0x180007bb0  pop     rbx
0x180007bb1  retn
```
