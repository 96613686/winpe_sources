# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180008c2c`
- end: `0x180008cd5`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008e20`
- `0x18000ec60`

## callees

- `0x180001f14`
- `0x1800088cc`
- `0x180008c2c`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008cb1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008cb1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this, unsigned int a2)
{
  unsigned __int64 v3; // r14
  __int64 v4; // rsi
  _QWORD *v5; // r15
  _QWORD *v6; // rbx
  __int64 v7; // rcx

  v3 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v4 = v3 & -(__int64)(this != 0);
      if ( !v4 )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x180008CD4LL);
      }
      v5 = *(_QWORD **)((v3 & -(__int64)(this != 0)) + 8);
      if ( v5 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
          v6 = (_QWORD *)v5[2];
          operator delete(v5);
          v5 = v6;
        }
        while ( v6 );
      }
      *(_QWORD *)(v4 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v7 = *((_QWORD *)this + 8);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v3 = 0;
  }
}

```

## disassembly

```asm
0x180008c2c  push    rbx
0x180008c2e  push    rsi
0x180008c2f  push    rdi
0x180008c30  push    r14
0x180008c32  push    r15
0x180008c34  sub     rsp, 20h
0x180008c38  mov     rdi, rcx
0x180008c3b  lea     r14, [rcx+8]
0x180008c3f  cmp     dword ptr [r14], 0
0x180008c43  jz      short loc_180008CBE
0x180008c45  cmp     qword ptr [rcx+10h], 0
0x180008c4a  jz      short loc_180008C98
0x180008c4c  mov     rax, rcx
0x180008c4f  neg     rax
0x180008c52  sbb     rsi, rsi
0x180008c55  and     rsi, r14
0x180008c58  jz      short loc_180008CCA
0x180008c5a  mov     r15, [rsi+8]
0x180008c5e  test    r15, r15
0x180008c61  jz      short loc_180008C88
0x180008c63  mov     rcx, [r15+8]
0x180008c67  mov     rax, [r15]
0x180008c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c6f  mov     rbx, [r15+10h]
0x180008c73  mov     edx, 18h
0x180008c78  mov     rcx, r15; Block
0x180008c7b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008c80  mov     r15, rbx
0x180008c83  test    rbx, rbx
0x180008c86  jnz     short loc_180008C63
0x180008c88  mov     qword ptr [rsi+8], 0
0x180008c90  mov     qword ptr [rdi+10h], 0
0x180008c98  mov     rcx, [rdi+40h]
0x180008c9c  test    rcx, rcx
0x180008c9f  jz      short loc_180008CAD
0x180008ca1  mov     rax, [rcx]
0x180008ca4  mov     rax, [rax+10h]
0x180008ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cad  lea     rcx, [rdi+18h]; lpCriticalSection
0x180008cb1  call    cs:__imp_DeleteCriticalSection
0x180008cb7  mov     dword ptr [r14], 0
0x180008cbe  add     rsp, 20h
0x180008cc2  pop     r15
0x180008cc4  pop     r14
0x180008cc6  pop     rdi
0x180008cc7  pop     rsi
0x180008cc8  pop     rbx
0x180008cc9  retn
0x180008cca  mov     ecx, 0C0000005h; unsigned int
0x180008ccf  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
