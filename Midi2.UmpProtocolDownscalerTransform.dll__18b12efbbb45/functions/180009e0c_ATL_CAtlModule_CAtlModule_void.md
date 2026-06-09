# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180009e0c`
- end: `0x180009eb5`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000a000`
- `0x180012b80`

## callees

- `0x180002e94`
- `0x180009aac`
- `0x180009e0c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009e91`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009e91`

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
        JUMPOUT(0x180009EB4LL);
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
0x180009e0c  push    rbx
0x180009e0e  push    rsi
0x180009e0f  push    rdi
0x180009e10  push    r14
0x180009e12  push    r15
0x180009e14  sub     rsp, 20h
0x180009e18  mov     rdi, rcx
0x180009e1b  lea     r14, [rcx+8]
0x180009e1f  cmp     dword ptr [r14], 0
0x180009e23  jz      short loc_180009E9E
0x180009e25  cmp     qword ptr [rcx+10h], 0
0x180009e2a  jz      short loc_180009E78
0x180009e2c  mov     rax, rcx
0x180009e2f  neg     rax
0x180009e32  sbb     rsi, rsi
0x180009e35  and     rsi, r14
0x180009e38  jz      short loc_180009EAA
0x180009e3a  mov     r15, [rsi+8]
0x180009e3e  test    r15, r15
0x180009e41  jz      short loc_180009E68
0x180009e43  mov     rcx, [r15+8]
0x180009e47  mov     rax, [r15]
0x180009e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e4f  mov     rbx, [r15+10h]
0x180009e53  mov     edx, 18h
0x180009e58  mov     rcx, r15; Block
0x180009e5b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009e60  mov     r15, rbx
0x180009e63  test    rbx, rbx
0x180009e66  jnz     short loc_180009E43
0x180009e68  mov     qword ptr [rsi+8], 0
0x180009e70  mov     qword ptr [rdi+10h], 0
0x180009e78  mov     rcx, [rdi+40h]
0x180009e7c  test    rcx, rcx
0x180009e7f  jz      short loc_180009E8D
0x180009e81  mov     rax, [rcx]
0x180009e84  mov     rax, [rax+10h]
0x180009e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e8d  lea     rcx, [rdi+18h]; lpCriticalSection
0x180009e91  call    cs:__imp_DeleteCriticalSection
0x180009e97  mov     dword ptr [r14], 0
0x180009e9e  add     rsp, 20h
0x180009ea2  pop     r15
0x180009ea4  pop     r14
0x180009ea6  pop     rdi
0x180009ea7  pop     rsi
0x180009ea8  pop     rbx
0x180009ea9  retn
0x180009eaa  mov     ecx, 0C0000005h; unsigned int
0x180009eaf  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
