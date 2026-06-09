# DmrcComServer::`scalar deleting destructor'(uint)

- ea: `0x180012b10`
- end: `0x180012b80`
- name: `??_GDmrcComServer@@UEAAPEAXI@Z`
- size: `112`
- prototype: `DmrcComServer *__fastcall(DmrcComServer *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001520`
- `0x180012a64`
- `0x180012b10`
- `0x180014010`

## pseudocode

```c
DmrcComServer *__fastcall DmrcComServer::`scalar deleting destructor'(DmrcComServer *this, char a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v4; // rax

  v2 = off_18001E320;
  v4 = off_18001E328;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v4 )
  {
    if ( *v2 )
    {
      (*((void (__fastcall **)(_QWORD))*v2 + 8))(0);
      v4 = off_18001E328;
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
0x180012b10  mov     [rsp+arg_0], rbx
0x180012b15  mov     [rsp+arg_8], rsi
0x180012b1a  push    rdi
0x180012b1b  sub     rsp, 20h
0x180012b1f  mov     rbx, cs:off_18001E320
0x180012b26  mov     esi, edx
0x180012b28  mov     rax, cs:off_18001E328
0x180012b2f  mov     rdi, rcx
0x180012b32  jmp     short loc_180012B52
0x180012b34  mov     r8, [rbx]
0x180012b37  test    r8, r8
0x180012b3a  jz      short loc_180012B4E
0x180012b3c  mov     rax, [r8+40h]
0x180012b40  xor     ecx, ecx
0x180012b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b47  mov     rax, cs:off_18001E328
0x180012b4e  add     rbx, 8
0x180012b52  cmp     rbx, rax
0x180012b55  jb      short loc_180012B34
0x180012b57  mov     rcx, rdi; this
0x180012b5a  call    ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
0x180012b5f  test    sil, 1
0x180012b63  jz      short loc_180012B6D
0x180012b65  mov     rcx, rdi; Block
0x180012b68  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012b6d  mov     rbx, [rsp+28h+arg_0]
0x180012b72  mov     rax, rdi
0x180012b75  mov     rsi, [rsp+28h+arg_8]
0x180012b7a  add     rsp, 20h
0x180012b7e  pop     rdi
0x180012b7f  retn
```
