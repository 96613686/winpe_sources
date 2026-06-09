# CRemoveDeviceContextHandlerModule::`vector deleting destructor'(uint)

- ea: `0x18000c160`
- end: `0x18000c1d0`
- name: `??_ECRemoveDeviceContextHandlerModule@@UEAAPEAXI@Z`
- size: `112`
- prototype: `void *__fastcall(CRemoveDeviceContextHandlerModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x180001be0`
- `0x18000c0b0`
- `0x18000c160`
- `0x18000e010`

## pseudocode

```c
CRemoveDeviceContextHandlerModule *__fastcall CRemoveDeviceContextHandlerModule::`vector deleting destructor'(
        CRemoveDeviceContextHandlerModule *this,
        char a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v4; // rax

  v2 = off_180014160;
  v4 = off_180014168;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v4 )
  {
    if ( *v2 )
    {
      (*((void (__fastcall **)(_QWORD))*v2 + 8))(0);
      v4 = off_180014168;
    }
    ++v2;
  }
  ATL::CAtlModule::~CAtlModule(this, a2);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000c160  mov     [rsp+arg_0], rbx
0x18000c165  mov     [rsp+arg_8], rsi
0x18000c16a  push    rdi
0x18000c16b  sub     rsp, 20h
0x18000c16f  mov     rbx, cs:off_180014160
0x18000c176  mov     esi, edx
0x18000c178  mov     rax, cs:off_180014168
0x18000c17f  mov     rdi, rcx
0x18000c182  jmp     short loc_18000C1A2
0x18000c184  mov     r8, [rbx]
0x18000c187  test    r8, r8
0x18000c18a  jz      short loc_18000C19E
0x18000c18c  mov     rax, [r8+40h]
0x18000c190  xor     ecx, ecx
0x18000c192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c197  mov     rax, cs:off_180014168
0x18000c19e  add     rbx, 8
0x18000c1a2  cmp     rbx, rax
0x18000c1a5  jb      short loc_18000C184
0x18000c1a7  mov     rcx, rdi; this
0x18000c1aa  call    ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
0x18000c1af  test    sil, 1
0x18000c1b3  jz      short loc_18000C1BD
0x18000c1b5  mov     rcx, rdi; Block
0x18000c1b8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c1bd  mov     rbx, [rsp+28h+arg_0]
0x18000c1c2  mov     rax, rdi
0x18000c1c5  mov     rsi, [rsp+28h+arg_8]
0x18000c1ca  add     rsp, 20h
0x18000c1ce  pop     rdi
0x18000c1cf  retn
```
