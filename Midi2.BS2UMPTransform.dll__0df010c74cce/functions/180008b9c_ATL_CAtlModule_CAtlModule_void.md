# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180008b9c`
- end: `0x180008c45`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008d90`
- `0x18000b760`

## callees

- `0x180001e84`
- `0x18000883c`
- `0x180008b9c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008c21`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008c21`

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
        JUMPOUT(0x180008C44LL);
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
0x180008b9c  push    rbx
0x180008b9e  push    rsi
0x180008b9f  push    rdi
0x180008ba0  push    r14
0x180008ba2  push    r15
0x180008ba4  sub     rsp, 20h
0x180008ba8  mov     rdi, rcx
0x180008bab  lea     r14, [rcx+8]
0x180008baf  cmp     dword ptr [r14], 0
0x180008bb3  jz      short loc_180008C2E
0x180008bb5  cmp     qword ptr [rcx+10h], 0
0x180008bba  jz      short loc_180008C08
0x180008bbc  mov     rax, rcx
0x180008bbf  neg     rax
0x180008bc2  sbb     rsi, rsi
0x180008bc5  and     rsi, r14
0x180008bc8  jz      short loc_180008C3A
0x180008bca  mov     r15, [rsi+8]
0x180008bce  test    r15, r15
0x180008bd1  jz      short loc_180008BF8
0x180008bd3  mov     rcx, [r15+8]
0x180008bd7  mov     rax, [r15]
0x180008bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bdf  mov     rbx, [r15+10h]
0x180008be3  mov     edx, 18h
0x180008be8  mov     rcx, r15; Block
0x180008beb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008bf0  mov     r15, rbx
0x180008bf3  test    rbx, rbx
0x180008bf6  jnz     short loc_180008BD3
0x180008bf8  mov     qword ptr [rsi+8], 0
0x180008c00  mov     qword ptr [rdi+10h], 0
0x180008c08  mov     rcx, [rdi+40h]
0x180008c0c  test    rcx, rcx
0x180008c0f  jz      short loc_180008C1D
0x180008c11  mov     rax, [rcx]
0x180008c14  mov     rax, [rax+10h]
0x180008c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c1d  lea     rcx, [rdi+18h]; lpCriticalSection
0x180008c21  call    cs:__imp_DeleteCriticalSection
0x180008c27  mov     dword ptr [r14], 0
0x180008c2e  add     rsp, 20h
0x180008c32  pop     r15
0x180008c34  pop     r14
0x180008c36  pop     rdi
0x180008c37  pop     rsi
0x180008c38  pop     rbx
0x180008c39  retn
0x180008c3a  mov     ecx, 0C0000005h; unsigned int
0x180008c3f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
