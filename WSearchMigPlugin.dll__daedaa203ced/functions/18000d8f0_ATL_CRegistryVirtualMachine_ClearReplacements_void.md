# ATL::CRegistryVirtualMachine::ClearReplacements(void)

- ea: `0x18000d8f0`
- end: `0x18000d968`
- name: `?ClearReplacements@CRegistryVirtualMachine@ATL@@UEAAJXZ`
- size: `120`
- prototype: `__int64 __fastcall(ATL::CRegistryVirtualMachine *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18000ce80`
- `0x1800129f0`

## callees

- `0x180002b9c`
- `0x18000d8f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d932`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d948`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d932`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d948`

## pseudocode

```c
__int64 __fastcall ATL::CRegistryVirtualMachine::ClearReplacements(ATL::CRegistryVirtualMachine *this)
{
  int v1; // ebp
  void **i; // rsi
  void *v4; // rcx

  v1 = 0;
  for ( i = (void **)((char *)this + 8); v1 < *((_DWORD *)this + 6); ++v1 )
  {
    operator delete(*((void **)*i + v1));
    operator delete(*(void **)(*((_QWORD *)this + 2) + 8LL * v1));
  }
  if ( *i )
  {
    free(*i);
    *i = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 2) = 0;
  }
  *((_DWORD *)this + 6) = 0;
  return 0;
}

```

## disassembly

```asm
0x18000d8f0  push    rbx
0x18000d8f2  push    rbp
0x18000d8f3  push    rsi
0x18000d8f4  push    rdi
0x18000d8f5  sub     rsp, 28h
0x18000d8f9  xor     ebp, ebp
0x18000d8fb  lea     rsi, [rcx+8]
0x18000d8ff  mov     rdi, rcx
0x18000d902  cmp     [rcx+18h], ebp
0x18000d905  jle     short loc_18000D92A
0x18000d907  mov     rcx, [rsi]
0x18000d90a  movsxd  rbx, ebp
0x18000d90d  mov     rcx, [rcx+rbx*8]; Block
0x18000d911  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d916  mov     rcx, [rdi+10h]
0x18000d91a  mov     rcx, [rcx+rbx*8]; Block
0x18000d91e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d923  inc     ebp
0x18000d925  cmp     ebp, [rdi+18h]
0x18000d928  jl      short loc_18000D907
0x18000d92a  mov     rcx, [rsi]; Block
0x18000d92d  test    rcx, rcx
0x18000d930  jz      short loc_18000D93F
0x18000d932  call    cs:__imp_free
0x18000d938  mov     qword ptr [rsi], 0
0x18000d93f  mov     rcx, [rdi+10h]; Block
0x18000d943  test    rcx, rcx
0x18000d946  jz      short loc_18000D956
0x18000d948  call    cs:__imp_free
0x18000d94e  mov     qword ptr [rdi+10h], 0
0x18000d956  mov     dword ptr [rdi+18h], 0
0x18000d95d  xor     eax, eax
0x18000d95f  add     rsp, 28h
0x18000d963  pop     rdi
0x18000d964  pop     rsi
0x18000d965  pop     rbp
0x18000d966  pop     rbx
0x18000d967  retn
```
