# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180010f2c`
- end: `0x180010fd5`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180011040`
- `0x18005cea0`

## callees

- `0x180005044`
- `0x18000c65c`
- `0x180010f2c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010fb1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010fb1`

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
        JUMPOUT(0x180010FD4LL);
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
0x180010f2c  push    rbx
0x180010f2e  push    rsi
0x180010f2f  push    rdi
0x180010f30  push    r14
0x180010f32  push    r15
0x180010f34  sub     rsp, 20h
0x180010f38  mov     rdi, rcx
0x180010f3b  lea     r14, [rcx+8]
0x180010f3f  cmp     dword ptr [r14], 0
0x180010f43  jz      short loc_180010FBE
0x180010f45  cmp     qword ptr [rcx+10h], 0
0x180010f4a  jz      short loc_180010F98
0x180010f4c  mov     rax, rcx
0x180010f4f  neg     rax
0x180010f52  sbb     rsi, rsi
0x180010f55  and     rsi, r14
0x180010f58  jz      short loc_180010FCA
0x180010f5a  mov     r15, [rsi+8]
0x180010f5e  test    r15, r15
0x180010f61  jz      short loc_180010F88
0x180010f63  mov     rcx, [r15+8]
0x180010f67  mov     rax, [r15]
0x180010f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f6f  mov     rbx, [r15+10h]
0x180010f73  mov     edx, 18h
0x180010f78  mov     rcx, r15; Block
0x180010f7b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010f80  mov     r15, rbx
0x180010f83  test    rbx, rbx
0x180010f86  jnz     short loc_180010F63
0x180010f88  mov     qword ptr [rsi+8], 0
0x180010f90  mov     qword ptr [rdi+10h], 0
0x180010f98  mov     rcx, [rdi+40h]
0x180010f9c  test    rcx, rcx
0x180010f9f  jz      short loc_180010FAD
0x180010fa1  mov     rax, [rcx]
0x180010fa4  mov     rax, [rax+10h]
0x180010fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fad  lea     rcx, [rdi+18h]; lpCriticalSection
0x180010fb1  call    cs:__imp_DeleteCriticalSection
0x180010fb7  mov     dword ptr [r14], 0
0x180010fbe  add     rsp, 20h
0x180010fc2  pop     r15
0x180010fc4  pop     r14
0x180010fc6  pop     rdi
0x180010fc7  pop     rsi
0x180010fc8  pop     rbx
0x180010fc9  retn
0x180010fca  mov     ecx, 0C0000005h; unsigned int
0x180010fcf  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
