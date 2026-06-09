# CMidi2UmpProtocolDownscalerTransformModule::`vector deleting destructor'(uint)

- ea: `0x18000a000`
- end: `0x18000a076`
- name: `??_ECMidi2UmpProtocolDownscalerTransformModule@@UEAAPEAXI@Z`
- size: `118`
- prototype: `void *__fastcall(CMidi2UmpProtocolDownscalerTransformModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002e94`
- `0x180009e0c`
- `0x18000a000`
- `0x180013010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CMidi2UmpProtocolDownscalerTransformModule *__fastcall CMidi2UmpProtocolDownscalerTransformModule::`vector deleting destructor'(
        CMidi2UmpProtocolDownscalerTransformModule *this,
        char a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rbx
  __int64 *v5; // rax

  v4 = off_18001B100;
  v5 = off_18001B108;
  while ( v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v5 )
  {
    if ( *v4 )
    {
      (*((void (__fastcall **)(_QWORD))*v4 + 8))(0);
      v5 = off_18001B108;
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
0x18000a000  mov     [rsp+arg_0], rbx
0x18000a005  mov     [rsp+arg_8], rsi
0x18000a00a  push    rdi
0x18000a00b  sub     rsp, 20h
0x18000a00f  mov     esi, edx
0x18000a011  mov     rdi, rcx
0x18000a014  mov     rbx, cs:off_18001B100
0x18000a01b  mov     rax, cs:off_18001B108
0x18000a022  jmp     short loc_18000A042
0x18000a024  mov     r8, [rbx]
0x18000a027  test    r8, r8
0x18000a02a  jz      short loc_18000A03E
0x18000a02c  xor     ecx, ecx
0x18000a02e  mov     rax, [r8+40h]
0x18000a032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a037  mov     rax, cs:off_18001B108
0x18000a03e  add     rbx, 8
0x18000a042  cmp     rbx, rax
0x18000a045  jb      short loc_18000A024
0x18000a047  mov     rcx, rdi; this
0x18000a04a  call    ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
0x18000a04f  nop
0x18000a050  test    sil, 1
0x18000a054  jz      short loc_18000A063
0x18000a056  mov     edx, 48h ; 'H'
0x18000a05b  mov     rcx, rdi; Block
0x18000a05e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a063  mov     rax, rdi
0x18000a066  mov     rbx, [rsp+28h+arg_0]
0x18000a06b  mov     rsi, [rsp+28h+arg_8]
0x18000a070  add     rsp, 20h
0x18000a074  pop     rdi
0x18000a075  retn
```
