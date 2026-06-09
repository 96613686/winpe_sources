# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18000d26c`
- end: `0x18000d315`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000d380`
- `0x1800408b0`

## callees

- `0x180004434`
- `0x18000badc`
- `0x18000d26c`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d2f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d2f1`

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
        JUMPOUT(0x18000D314LL);
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
0x18000d26c  push    rbx
0x18000d26e  push    rsi
0x18000d26f  push    rdi
0x18000d270  push    r14
0x18000d272  push    r15
0x18000d274  sub     rsp, 20h
0x18000d278  mov     rdi, rcx
0x18000d27b  lea     r14, [rcx+8]
0x18000d27f  cmp     dword ptr [r14], 0
0x18000d283  jz      short loc_18000D2FE
0x18000d285  cmp     qword ptr [rcx+10h], 0
0x18000d28a  jz      short loc_18000D2D8
0x18000d28c  mov     rax, rcx
0x18000d28f  neg     rax
0x18000d292  sbb     rsi, rsi
0x18000d295  and     rsi, r14
0x18000d298  jz      short loc_18000D30A
0x18000d29a  mov     r15, [rsi+8]
0x18000d29e  test    r15, r15
0x18000d2a1  jz      short loc_18000D2C8
0x18000d2a3  mov     rcx, [r15+8]
0x18000d2a7  mov     rax, [r15]
0x18000d2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2af  mov     rbx, [r15+10h]
0x18000d2b3  mov     edx, 18h
0x18000d2b8  mov     rcx, r15; Block
0x18000d2bb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d2c0  mov     r15, rbx
0x18000d2c3  test    rbx, rbx
0x18000d2c6  jnz     short loc_18000D2A3
0x18000d2c8  mov     qword ptr [rsi+8], 0
0x18000d2d0  mov     qword ptr [rdi+10h], 0
0x18000d2d8  mov     rcx, [rdi+40h]
0x18000d2dc  test    rcx, rcx
0x18000d2df  jz      short loc_18000D2ED
0x18000d2e1  mov     rax, [rcx]
0x18000d2e4  mov     rax, [rax+10h]
0x18000d2e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2ed  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000d2f1  call    cs:__imp_DeleteCriticalSection
0x18000d2f7  mov     dword ptr [r14], 0
0x18000d2fe  add     rsp, 20h
0x18000d302  pop     r15
0x18000d304  pop     r14
0x18000d306  pop     rdi
0x18000d307  pop     rsi
0x18000d308  pop     rbx
0x18000d309  retn
0x18000d30a  mov     ecx, 0C0000005h; unsigned int
0x18000d30f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
