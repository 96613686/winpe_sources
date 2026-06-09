# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x1800136b8`
- end: `0x180013761`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180013770`
- `0x180036e00`

## callees

- `0x180001bc8`
- `0x1800073e0`
- `0x1800136b8`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001373d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001373d`

## pseudocode

```c
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
        JUMPOUT(0x180013760LL);
      }
      v5 = *(_QWORD **)((v3 & -(__int64)(this != 0)) + 8);
      if ( v5 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
          v6 = (_QWORD *)v5[2];
          operator delete(v5, 0x18u);
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
0x1800136b8  push    rbx
0x1800136ba  push    rsi
0x1800136bb  push    rdi
0x1800136bc  push    r14
0x1800136be  push    r15
0x1800136c0  sub     rsp, 20h
0x1800136c4  mov     rdi, rcx
0x1800136c7  lea     r14, [rcx+8]
0x1800136cb  cmp     dword ptr [r14], 0
0x1800136cf  jz      short loc_18001374A
0x1800136d1  cmp     qword ptr [rcx+10h], 0
0x1800136d6  jz      short loc_180013724
0x1800136d8  mov     rax, rcx
0x1800136db  neg     rax
0x1800136de  sbb     rsi, rsi
0x1800136e1  and     rsi, r14
0x1800136e4  jz      short loc_180013756
0x1800136e6  mov     r15, [rsi+8]
0x1800136ea  test    r15, r15
0x1800136ed  jz      short loc_180013714
0x1800136ef  mov     rcx, [r15+8]
0x1800136f3  mov     rax, [r15]
0x1800136f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136fb  mov     rbx, [r15+10h]
0x1800136ff  mov     edx, 18h; unsigned __int64
0x180013704  mov     rcx, r15; void *
0x180013707  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001370c  mov     r15, rbx
0x18001370f  test    rbx, rbx
0x180013712  jnz     short loc_1800136EF
0x180013714  mov     qword ptr [rsi+8], 0
0x18001371c  mov     qword ptr [rdi+10h], 0
0x180013724  mov     rcx, [rdi+40h]
0x180013728  test    rcx, rcx
0x18001372b  jz      short loc_180013739
0x18001372d  mov     rax, [rcx]
0x180013730  mov     rax, [rax+10h]
0x180013734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013739  lea     rcx, [rdi+18h]; lpCriticalSection
0x18001373d  call    cs:__imp_DeleteCriticalSection
0x180013743  mov     dword ptr [r14], 0
0x18001374a  add     rsp, 20h
0x18001374e  pop     r15
0x180013750  pop     r14
0x180013752  pop     rdi
0x180013753  pop     rsi
0x180013754  pop     rbx
0x180013755  retn
0x180013756  mov     ecx, 0C0000005h; unsigned int
0x18001375b  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
