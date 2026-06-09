# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180003bfc`
- end: `0x180003ca0`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003d70`
- `0x18000a590`

## callees

- `0x180001160`
- `0x180003bfc`
- `0x180004874`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003c7c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003c7c`

## pseudocode

```c
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this, unsigned int a2)
{
  unsigned __int64 v2; // r14
  __int64 v4; // rsi
  _QWORD *v5; // r15
  _QWORD *v6; // rbx
  __int64 v7; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v4 = v2 & -(__int64)(this != 0);
      if ( !v4 )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x180003C9FLL);
      }
      v5 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
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
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x180003bfc  push    rbx
0x180003bfe  push    rsi
0x180003bff  push    rdi
0x180003c00  push    r14
0x180003c02  push    r15
0x180003c04  sub     rsp, 20h
0x180003c08  lea     r14, [rcx+8]
0x180003c0c  mov     rdi, rcx
0x180003c0f  cmp     dword ptr [r14], 0
0x180003c13  jz      short loc_180003C89
0x180003c15  cmp     qword ptr [rcx+10h], 0
0x180003c1a  jz      short loc_180003C63
0x180003c1c  mov     rax, rcx
0x180003c1f  neg     rax
0x180003c22  sbb     rsi, rsi
0x180003c25  and     rsi, r14
0x180003c28  jz      short loc_180003C95
0x180003c2a  mov     r15, [rsi+8]
0x180003c2e  test    r15, r15
0x180003c31  jz      short loc_180003C53
0x180003c33  mov     rcx, [r15+8]
0x180003c37  mov     rax, [r15]
0x180003c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c3f  mov     rbx, [r15+10h]
0x180003c43  mov     rcx, r15; Block
0x180003c46  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003c4b  mov     r15, rbx
0x180003c4e  test    rbx, rbx
0x180003c51  jnz     short loc_180003C33
0x180003c53  mov     qword ptr [rsi+8], 0
0x180003c5b  mov     qword ptr [rdi+10h], 0
0x180003c63  mov     rcx, [rdi+40h]
0x180003c67  test    rcx, rcx
0x180003c6a  jz      short loc_180003C78
0x180003c6c  mov     rax, [rcx]
0x180003c6f  mov     rax, [rax+10h]
0x180003c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c78  lea     rcx, [rdi+18h]; lpCriticalSection
0x180003c7c  call    cs:__imp_DeleteCriticalSection
0x180003c82  mov     dword ptr [r14], 0
0x180003c89  add     rsp, 20h
0x180003c8d  pop     r15
0x180003c8f  pop     r14
0x180003c91  pop     rdi
0x180003c92  pop     rsi
0x180003c93  pop     rbx
0x180003c94  retn
0x180003c95  mov     ecx, 0C0000005h; unsigned int
0x180003c9a  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
