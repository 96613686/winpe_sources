# CUICOMModule::`scalar deleting destructor'(uint)

- ea: `0x1800023d0`
- end: `0x180002440`
- name: `??_GCUICOMModule@@UEAAPEAXI@Z`
- size: `112`
- prototype: `void *__fastcall(CUICOMModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001170`
- `0x18000226c`
- `0x1800023d0`
- `0x180007010`

## pseudocode

```c
CUICOMModule *__fastcall CUICOMModule::`scalar deleting destructor'(CUICOMModule *this, char a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 *v2; // rbx
  __int64 *v4; // rax

  v2 = off_18000B0B0;
  v4 = (__int64 *)off_18000B0B8;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)v4 )
  {
    if ( *(_QWORD *)v2 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v2 + 64LL))(0);
      v4 = (__int64 *)off_18000B0B8;
    }
    v2 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v2 + 8);
  }
  ATL::CAtlModule::~CAtlModule(this, a2);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800023d0  mov     [rsp+arg_0], rbx
0x1800023d5  mov     [rsp+arg_8], rsi
0x1800023da  push    rdi
0x1800023db  sub     rsp, 20h
0x1800023df  mov     rbx, cs:off_18000B0B0
0x1800023e6  mov     esi, edx
0x1800023e8  mov     rax, cs:off_18000B0B8
0x1800023ef  mov     rdi, rcx
0x1800023f2  jmp     short loc_180002412
0x1800023f4  mov     r8, [rbx]
0x1800023f7  test    r8, r8
0x1800023fa  jz      short loc_18000240E
0x1800023fc  mov     rax, [r8+40h]
0x180002400  xor     ecx, ecx
0x180002402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002407  mov     rax, cs:off_18000B0B8
0x18000240e  add     rbx, 8
0x180002412  cmp     rbx, rax
0x180002415  jb      short loc_1800023F4
0x180002417  mov     rcx, rdi; this
0x18000241a  call    ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
0x18000241f  test    sil, 1
0x180002423  jz      short loc_18000242D
0x180002425  mov     rcx, rdi; Block
0x180002428  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000242d  mov     rbx, [rsp+28h+arg_0]
0x180002432  mov     rax, rdi
0x180002435  mov     rsi, [rsp+28h+arg_8]
0x18000243a  add     rsp, 20h
0x18000243e  pop     rdi
0x18000243f  retn
```
