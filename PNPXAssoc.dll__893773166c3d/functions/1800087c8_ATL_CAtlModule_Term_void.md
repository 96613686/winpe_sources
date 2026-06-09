# ATL::CAtlModule::Term(void)

- ea: `0x1800087c8`
- end: `0x18000886c`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180005650`
- `0x1800090c0`
- `0x1800132a0`

## callees

- `0x1800019b0`
- `0x1800087c8`
- `0x180008f7c`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008848`
- `KERNEL32!DeleteCriticalSection` at `0x180008848`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this, unsigned int a2)
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
        JUMPOUT(0x18000886BLL);
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
0x1800087c8  push    rbx
0x1800087ca  push    rsi
0x1800087cb  push    rdi
0x1800087cc  push    r14
0x1800087ce  push    r15
0x1800087d0  sub     rsp, 20h
0x1800087d4  lea     r14, [rcx+8]
0x1800087d8  mov     rdi, rcx
0x1800087db  cmp     dword ptr [r14], 0
0x1800087df  jz      short loc_180008855
0x1800087e1  cmp     qword ptr [rcx+10h], 0
0x1800087e6  jz      short loc_18000882F
0x1800087e8  mov     rax, rcx
0x1800087eb  neg     rax
0x1800087ee  sbb     rsi, rsi
0x1800087f1  and     rsi, r14
0x1800087f4  jz      short loc_180008861
0x1800087f6  mov     r15, [rsi+8]
0x1800087fa  test    r15, r15
0x1800087fd  jz      short loc_18000881F
0x1800087ff  mov     rcx, [r15+8]
0x180008803  mov     rax, [r15]
0x180008806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000880b  mov     rbx, [r15+10h]
0x18000880f  mov     rcx, r15; Block
0x180008812  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008817  mov     r15, rbx
0x18000881a  test    rbx, rbx
0x18000881d  jnz     short loc_1800087FF
0x18000881f  mov     qword ptr [rsi+8], 0
0x180008827  mov     qword ptr [rdi+10h], 0
0x18000882f  mov     rcx, [rdi+40h]
0x180008833  test    rcx, rcx
0x180008836  jz      short loc_180008844
0x180008838  mov     rax, [rcx]
0x18000883b  mov     rax, [rax+10h]
0x18000883f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008844  lea     rcx, [rdi+18h]; lpCriticalSection
0x180008848  call    cs:__imp_DeleteCriticalSection
0x18000884e  mov     dword ptr [r14], 0
0x180008855  add     rsp, 20h
0x180008859  pop     r15
0x18000885b  pop     r14
0x18000885d  pop     rdi
0x18000885e  pop     rsi
0x18000885f  pop     rbx
0x180008860  retn
0x180008861  mov     ecx, 0C0000005h; unsigned int
0x180008866  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
