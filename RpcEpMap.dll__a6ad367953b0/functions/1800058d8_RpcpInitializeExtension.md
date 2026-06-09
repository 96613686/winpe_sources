# RpcpInitializeExtension

- ea: `0x1800058d8`
- end: `0x18000598e`
- name: `RpcpInitializeExtension`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800080f8`

## callees

- `0x180002a00`
- `0x1800058d8`
- `0x180005994`
- `0x180005f48`
- `0x18000a750`

## string_xrefs

- `0x180005923`: `RemoteRpcDll`

## pseudocode

```c
__int64 __fastcall RpcpInitializeExtension(__int64 a1, _QWORD *a2)
{
  bool v2; // zf
  void *v4; // rax
  __int64 v5; // rcx
  void *v6; // rbx
  unsigned int v8; // edx
  unsigned int v9; // esi
  DLL *v10; // [rsp+38h] [rbp+10h] BYREF

  v2 = qword_180013BE8 == 0;
  v10 = 0;
  *a2 = 0;
  if ( v2 )
  {
    v4 = operator new(0x28u);
    v6 = v4;
    if ( !v4 )
      return 14;
    v9 = RpcpLoadExtensionDll(v5, L"RemoteRpcDll", (__int64)v4, &v10);
    if ( v9 )
    {
      operator delete(v6);
      return v9;
    }
    if ( _InterlockedCompareExchange64(&qword_180013BE0, (signed __int64)v10, 0) && v10 )
      DLL::`scalar deleting destructor'(v10, v8);
    if ( _InterlockedCompareExchange64(&qword_180013BE8, (signed __int64)v6, 0) )
      operator delete(v6);
  }
  *a2 = qword_180013BE8;
  return 0;
}

```

## disassembly

```asm
0x1800058d8  mov     [rsp+arg_0], rbx
0x1800058dd  mov     [rsp+arg_10], rsi
0x1800058e2  push    rdi
0x1800058e3  sub     rsp, 20h
0x1800058e7  cmp     cs:qword_180013BE8, 0
0x1800058ef  mov     rdi, rdx
0x1800058f2  mov     [rsp+28h+arg_8], 0
0x1800058fb  mov     qword ptr [rdx], 0
0x180005902  jnz     short loc_180005972
0x180005904  mov     ecx, 28h ; '('; unsigned __int64
0x180005909  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000590e  mov     rbx, rax
0x180005911  test    rax, rax
0x180005914  jnz     short loc_18000591B
0x180005916  lea     eax, [rbx+0Eh]
0x180005919  jmp     short loc_18000597E
0x18000591b  lea     r9, [rsp+28h+arg_8]
0x180005920  mov     r8, rbx
0x180005923  lea     rdx, aRemoterpcdll; "RemoteRpcDll"
0x18000592a  call    ?RpcpLoadExtensionDll@@YAJW4RPC_EXTENSION_POINT_TYPE@@PEBGPEAXPEAPEAVDLL@@@Z; RpcpLoadExtensionDll(RPC_EXTENSION_POINT_TYPE,ushort const *,void *,DLL * *)
0x18000592f  mov     esi, eax
0x180005931  test    eax, eax
0x180005933  jz      short loc_180005941
0x180005935  mov     rcx, rbx; void *
0x180005938  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000593d  mov     eax, esi
0x18000593f  jmp     short loc_18000597E
0x180005941  mov     rcx, [rsp+28h+arg_8]; this
0x180005946  xor     eax, eax
0x180005948  lock cmpxchg cs:qword_180013BE0, rcx
0x180005951  jz      short loc_18000595D
0x180005953  test    rcx, rcx
0x180005956  jz      short loc_18000595D
0x180005958  call    ??_GDLL@@QEAAPEAXI@Z; DLL::`scalar deleting destructor'(uint)
0x18000595d  xor     eax, eax
0x18000595f  lock cmpxchg cs:qword_180013BE8, rbx
0x180005968  jz      short loc_180005972
0x18000596a  mov     rcx, rbx; void *
0x18000596d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005972  mov     rax, cs:qword_180013BE8
0x180005979  mov     [rdi], rax
0x18000597c  xor     eax, eax
0x18000597e  mov     rbx, [rsp+28h+arg_0]
0x180005983  mov     rsi, [rsp+28h+arg_10]
0x180005988  add     rsp, 20h
0x18000598c  pop     rdi
0x18000598d  retn
```
