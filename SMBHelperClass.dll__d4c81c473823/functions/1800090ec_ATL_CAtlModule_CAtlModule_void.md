# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x1800090ec`
- end: `0x180009191`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800091a0`
- `0x180011510`

## callees

- `0x1800090c4`
- `0x1800090ec`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009136`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009136`
- `KERNEL32!DeleteCriticalSection` at `0x18000916d`
- `KERNEL32!DeleteCriticalSection` at `0x18000916d`

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
        JUMPOUT(0x180009190LL);
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
0x1800090ec  push    rbx
0x1800090ee  push    rsi
0x1800090ef  push    rdi
0x1800090f0  push    r14
0x1800090f2  push    r15
0x1800090f4  sub     rsp, 20h
0x1800090f8  mov     rdi, rcx
0x1800090fb  lea     r14, [rcx+8]
0x1800090ff  cmp     dword ptr [r14], 0
0x180009103  jz      short loc_18000917A
0x180009105  cmp     qword ptr [rcx+10h], 0
0x18000910a  jz      short loc_180009154
0x18000910c  mov     rax, rcx
0x18000910f  neg     rax
0x180009112  sbb     rsi, rsi
0x180009115  and     rsi, r14
0x180009118  jz      short loc_180009186
0x18000911a  mov     r15, [rsi+8]
0x18000911e  test    r15, r15
0x180009121  jz      short loc_180009144
0x180009123  mov     rcx, [r15+8]
0x180009127  mov     rax, [r15]
0x18000912a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000912f  mov     rbx, [r15+10h]
0x180009133  mov     rcx, r15
0x180009136  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000913c  mov     r15, rbx
0x18000913f  test    rbx, rbx
0x180009142  jnz     short loc_180009123
0x180009144  mov     qword ptr [rsi+8], 0
0x18000914c  mov     qword ptr [rdi+10h], 0
0x180009154  mov     rcx, [rdi+40h]
0x180009158  test    rcx, rcx
0x18000915b  jz      short loc_180009169
0x18000915d  mov     rax, [rcx]
0x180009160  mov     rax, [rax+10h]
0x180009164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009169  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000916d  call    cs:__imp_DeleteCriticalSection
0x180009173  mov     dword ptr [r14], 0
0x18000917a  add     rsp, 20h
0x18000917e  pop     r15
0x180009180  pop     r14
0x180009182  pop     rdi
0x180009183  pop     rsi
0x180009184  pop     rbx
0x180009185  retn
0x180009186  mov     ecx, 0C0000005h; unsigned int
0x18000918b  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
