# OpenEndpointMapper

- ea: `0x180007170`
- end: `0x1800071ae`
- name: `OpenEndpointMapper`
- size: `62`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004dc0`
- `0x180007170`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18000718e`
- `RPCRT4!RpcRaiseException` at `0x18000718e`

## pseudocode

```c
__int64 __fastcall OpenEndpointMapper(__int64 a1, _QWORD *a2)
{
  _QWORD *v3; // rax

  v3 = MIDL_user_allocate(0x10u);
  if ( !v3 )
  {
    *a2 = 0;
    RpcRaiseException(14);
  }
  *(_DWORD *)v3 = -557122642;
  v3[1] = 0;
  *a2 = v3;
  return 0;
}

```

## disassembly

```asm
0x180007170  push    rbx
0x180007172  sub     rsp, 20h
0x180007176  mov     ecx, 10h; size
0x18000717b  mov     rbx, rdx
0x18000717e  call    MIDL_user_allocate
0x180007183  test    rax, rax
0x180007186  jnz     short loc_180007195
0x180007188  lea     ecx, [rax+0Eh]; exception
0x18000718b  mov     [rbx], rax
0x18000718e  call    cs:__imp_RpcRaiseException
0x180007194  int     3; Trap to Debugger
0x180007195  mov     dword ptr [rax], 0DECAFBAEh
0x18000719b  mov     qword ptr [rax+8], 0
0x1800071a3  mov     [rbx], rax
0x1800071a6  xor     eax, eax
0x1800071a8  add     rsp, 20h
0x1800071ac  pop     rbx
0x1800071ad  retn
```
