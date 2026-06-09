# CWSMigPluginModule::`vector deleting destructor'(uint)

- ea: `0x18000aa00`
- end: `0x18000aa80`
- name: `??_ECWSMigPluginModule@@UEAAPEAXI@Z`
- size: `128`
- prototype: `CWSMigPluginModule *__fastcall(CWSMigPluginModule *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x180002b9c`
- `0x18000a91c`
- `0x18000aa00`
- `0x180018010`

## pseudocode

```c
CWSMigPluginModule *__fastcall CWSMigPluginModule::`vector deleting destructor'(CWSMigPluginModule *this, char a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rbx
  __int64 *v5; // rax

  v4 = off_180025520;
  v5 = off_180025528;
  while ( v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v5 )
  {
    if ( *v4 )
    {
      (*((void (__fastcall **)(_QWORD))*v4 + 8))(0);
      v5 = off_180025528;
    }
    ++v4;
  }
  ATL::CAtlModule::~CAtlModule(this, a2);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000aa00  push    rdi
0x18000aa02  sub     rsp, 30h
0x18000aa06  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000aa0f  mov     [rsp+38h+arg_0], rbx
0x18000aa14  mov     [rsp+38h+arg_8], rsi
0x18000aa19  mov     esi, edx
0x18000aa1b  mov     rdi, rcx
0x18000aa1e  mov     rbx, cs:off_180025520
0x18000aa25  mov     rax, cs:off_180025528
0x18000aa2c  jmp     short loc_18000AA4C
0x18000aa2e  mov     r8, [rbx]
0x18000aa31  test    r8, r8
0x18000aa34  jz      short loc_18000AA48
0x18000aa36  xor     ecx, ecx
0x18000aa38  mov     rax, [r8+40h]
0x18000aa3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa41  mov     rax, cs:off_180025528
0x18000aa48  add     rbx, 8
0x18000aa4c  cmp     rbx, rax
0x18000aa4f  jb      short loc_18000AA2E
0x18000aa51  mov     rcx, rdi; this
0x18000aa54  call    ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
0x18000aa59  nop
0x18000aa5a  test    sil, 1
0x18000aa5e  jz      short loc_18000AA6D
0x18000aa60  mov     edx, 48h ; 'H'
0x18000aa65  mov     rcx, rdi; Block
0x18000aa68  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000aa6d  mov     rax, rdi
0x18000aa70  mov     rbx, [rsp+38h+arg_0]
0x18000aa75  mov     rsi, [rsp+38h+arg_8]
0x18000aa7a  add     rsp, 30h
0x18000aa7e  pop     rdi
0x18000aa7f  retn
```
