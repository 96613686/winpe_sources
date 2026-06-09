# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180002c08`
- end: `0x180002ca8`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `160`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002cb0`
- `0x18000afe0`

## callees

- `0x180002c08`
- `0x180002e54`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002c52`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002c52`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002c89`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002c89`

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
        ATL::_AtlRaiseException((unsigned int)this, a2);
        JUMPOUT(0x180002CA7LL);
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
0x180002c08  push    rbx
0x180002c0a  push    rsi
0x180002c0b  push    rdi
0x180002c0c  push    r14
0x180002c0e  push    r15
0x180002c10  sub     rsp, 20h
0x180002c14  mov     rdi, rcx
0x180002c17  lea     r14, [rcx+8]
0x180002c1b  cmp     dword ptr [r14], 0
0x180002c1f  jz      short loc_180002C96
0x180002c21  cmp     qword ptr [rcx+10h], 0
0x180002c26  jz      short loc_180002C70
0x180002c28  mov     rax, rcx
0x180002c2b  neg     rax
0x180002c2e  sbb     rsi, rsi
0x180002c31  and     rsi, r14
0x180002c34  jz      short loc_180002CA2
0x180002c36  mov     r15, [rsi+8]
0x180002c3a  test    r15, r15
0x180002c3d  jz      short loc_180002C60
0x180002c3f  mov     rcx, [r15+8]
0x180002c43  mov     rax, [r15]
0x180002c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c4b  mov     rbx, [r15+10h]
0x180002c4f  mov     rcx, r15
0x180002c52  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002c58  mov     r15, rbx
0x180002c5b  test    rbx, rbx
0x180002c5e  jnz     short loc_180002C3F
0x180002c60  mov     qword ptr [rsi+8], 0
0x180002c68  mov     qword ptr [rdi+10h], 0
0x180002c70  mov     rcx, [rdi+40h]
0x180002c74  test    rcx, rcx
0x180002c77  jz      short loc_180002C85
0x180002c79  mov     rax, [rcx]
0x180002c7c  mov     rax, [rax+10h]
0x180002c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c85  lea     rcx, [rdi+18h]; lpCriticalSection
0x180002c89  call    cs:__imp_DeleteCriticalSection
0x180002c8f  mov     dword ptr [r14], 0
0x180002c96  add     rsp, 20h
0x180002c9a  pop     r15
0x180002c9c  pop     r14
0x180002c9e  pop     rdi
0x180002c9f  pop     rsi
0x180002ca0  pop     rbx
0x180002ca1  retn
0x180002ca2  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
