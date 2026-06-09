# ATL::CAtlModule::Term(void)

- ea: `0x180021e9c`
- end: `0x180021f45`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001f030`
- `0x1800227f0`
- `0x180023190`

## callees

- `0x180001914`
- `0x180021e9c`
- `0x18002262c`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021f21`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021f21`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this, unsigned int a2)
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
        JUMPOUT(0x180021F44LL);
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
0x180021e9c  push    rbx
0x180021e9e  push    rsi
0x180021e9f  push    rdi
0x180021ea0  push    r14
0x180021ea2  push    r15
0x180021ea4  sub     rsp, 20h
0x180021ea8  mov     rdi, rcx
0x180021eab  lea     r14, [rcx+8]
0x180021eaf  cmp     dword ptr [r14], 0
0x180021eb3  jz      short loc_180021F2E
0x180021eb5  cmp     qword ptr [rcx+10h], 0
0x180021eba  jz      short loc_180021F08
0x180021ebc  mov     rax, rcx
0x180021ebf  neg     rax
0x180021ec2  sbb     rsi, rsi
0x180021ec5  and     rsi, r14
0x180021ec8  jz      short loc_180021F3A
0x180021eca  mov     r15, [rsi+8]
0x180021ece  test    r15, r15
0x180021ed1  jz      short loc_180021EF8
0x180021ed3  mov     rcx, [r15+8]
0x180021ed7  mov     rax, [r15]
0x180021eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021edf  mov     rbx, [r15+10h]
0x180021ee3  mov     edx, 18h
0x180021ee8  mov     rcx, r15; Block
0x180021eeb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021ef0  mov     r15, rbx
0x180021ef3  test    rbx, rbx
0x180021ef6  jnz     short loc_180021ED3
0x180021ef8  mov     qword ptr [rsi+8], 0
0x180021f00  mov     qword ptr [rdi+10h], 0
0x180021f08  mov     rcx, [rdi+40h]
0x180021f0c  test    rcx, rcx
0x180021f0f  jz      short loc_180021F1D
0x180021f11  mov     rax, [rcx]
0x180021f14  mov     rax, [rax+10h]
0x180021f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f1d  lea     rcx, [rdi+18h]; lpCriticalSection
0x180021f21  call    cs:__imp_DeleteCriticalSection
0x180021f27  mov     dword ptr [r14], 0
0x180021f2e  add     rsp, 20h
0x180021f32  pop     r15
0x180021f34  pop     r14
0x180021f36  pop     rdi
0x180021f37  pop     rsi
0x180021f38  pop     rbx
0x180021f39  retn
0x180021f3a  mov     ecx, 0C0000005h; unsigned int
0x180021f3f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
