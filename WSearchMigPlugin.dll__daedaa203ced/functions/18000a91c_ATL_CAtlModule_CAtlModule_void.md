# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18000a91c`
- end: `0x18000a9ce`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `178`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18000aa00`
- `0x180017d70`

## callees

- `0x180002b9c`
- `0x18000a91c`
- `0x18000bf58`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a9aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a9aa`

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
        JUMPOUT(0x18000A9CDLL);
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
0x18000a91c  push    rbx
0x18000a91e  push    rsi
0x18000a91f  push    rdi
0x18000a920  push    r14
0x18000a922  push    r15
0x18000a924  sub     rsp, 30h
0x18000a928  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18000a931  mov     rdi, rcx
0x18000a934  lea     r14, [rcx+8]
0x18000a938  cmp     dword ptr [r14], 0
0x18000a93c  jz      short loc_18000A9B7
0x18000a93e  cmp     qword ptr [rcx+10h], 0
0x18000a943  jz      short loc_18000A991
0x18000a945  mov     rax, rcx
0x18000a948  neg     rax
0x18000a94b  sbb     rsi, rsi
0x18000a94e  and     rsi, r14
0x18000a951  jz      short loc_18000A9C3
0x18000a953  mov     r15, [rsi+8]
0x18000a957  test    r15, r15
0x18000a95a  jz      short loc_18000A981
0x18000a95c  mov     rcx, [r15+8]
0x18000a960  mov     rax, [r15]
0x18000a963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a968  mov     rbx, [r15+10h]
0x18000a96c  mov     edx, 18h
0x18000a971  mov     rcx, r15; Block
0x18000a974  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a979  mov     r15, rbx
0x18000a97c  test    rbx, rbx
0x18000a97f  jnz     short loc_18000A95C
0x18000a981  mov     qword ptr [rsi+8], 0
0x18000a989  mov     qword ptr [rdi+10h], 0
0x18000a991  mov     rcx, [rdi+40h]
0x18000a995  test    rcx, rcx
0x18000a998  jz      short loc_18000A9A6
0x18000a99a  mov     rax, [rcx]
0x18000a99d  mov     rax, [rax+10h]
0x18000a9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9a6  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000a9aa  call    cs:__imp_DeleteCriticalSection
0x18000a9b0  mov     dword ptr [r14], 0
0x18000a9b7  add     rsp, 30h
0x18000a9bb  pop     r15
0x18000a9bd  pop     r14
0x18000a9bf  pop     rdi
0x18000a9c0  pop     rsi
0x18000a9c1  pop     rbx
0x18000a9c2  retn
0x18000a9c3  mov     ecx, 0C0000005h; unsigned int
0x18000a9c8  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
