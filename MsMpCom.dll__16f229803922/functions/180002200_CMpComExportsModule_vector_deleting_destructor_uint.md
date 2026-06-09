# CMpComExportsModule::`vector deleting destructor'(uint)

- ea: `0x180002200`
- end: `0x180002272`
- name: `??_ECMpComExportsModule@@UEAAPEAXI@Z`
- size: `114`
- prototype: `void *__fastcall(CMpComExportsModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002200`
- `0x180002384`
- `0x18000a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002259`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002259`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CMpComExportsModule *__fastcall CMpComExportsModule::`vector deleting destructor'(CMpComExportsModule *this, char a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rbx
  __int64 *v5; // rax

  v4 = off_180012150;
  v5 = off_180012158;
  while ( v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v5 )
  {
    if ( *v4 )
    {
      (*((void (__fastcall **)(_QWORD))*v4 + 8))(0);
      v5 = off_180012158;
    }
    ++v4;
  }
  ATL::CAtlModule::Term(this, a2);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002200  mov     [rsp+arg_0], rbx
0x180002205  mov     [rsp+arg_8], rsi
0x18000220a  push    rdi
0x18000220b  sub     rsp, 20h
0x18000220f  mov     esi, edx
0x180002211  mov     rdi, rcx
0x180002214  mov     rbx, cs:off_180012150
0x18000221b  mov     rax, cs:off_180012158
0x180002222  jmp     short loc_180002242
0x180002224  mov     r8, [rbx]
0x180002227  test    r8, r8
0x18000222a  jz      short loc_18000223E
0x18000222c  xor     ecx, ecx
0x18000222e  mov     rax, [r8+40h]
0x180002232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002237  mov     rax, cs:off_180012158
0x18000223e  add     rbx, 8
0x180002242  cmp     rbx, rax
0x180002245  jb      short loc_180002224
0x180002247  mov     rcx, rdi; this
0x18000224a  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000224f  nop
0x180002250  test    sil, 1
0x180002254  jz      short loc_18000225F
0x180002256  mov     rcx, rdi
0x180002259  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000225f  mov     rax, rdi
0x180002262  mov     rbx, [rsp+28h+arg_0]
0x180002267  mov     rsi, [rsp+28h+arg_8]
0x18000226c  add     rsp, 20h
0x180002270  pop     rdi
0x180002271  retn
```
