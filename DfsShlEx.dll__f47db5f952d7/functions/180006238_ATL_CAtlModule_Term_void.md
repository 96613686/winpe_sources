# ATL::CAtlModule::Term(void)

- ea: `0x180006238`
- end: `0x1800062dd`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002e20`
- `0x1800069f0`
- `0x18000b2a0`

## callees

- `0x180006238`
- `0x1800068ac`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006282`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006282`
- `KERNEL32!DeleteCriticalSection` at `0x1800062b9`
- `KERNEL32!DeleteCriticalSection` at `0x1800062b9`

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
        JUMPOUT(0x1800062DCLL);
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
0x180006238  push    rbx
0x18000623a  push    rsi
0x18000623b  push    rdi
0x18000623c  push    r14
0x18000623e  push    r15
0x180006240  sub     rsp, 20h
0x180006244  mov     rdi, rcx
0x180006247  lea     r14, [rcx+8]
0x18000624b  cmp     dword ptr [r14], 0
0x18000624f  jz      short loc_1800062C6
0x180006251  cmp     qword ptr [rcx+10h], 0
0x180006256  jz      short loc_1800062A0
0x180006258  mov     rax, rcx
0x18000625b  neg     rax
0x18000625e  sbb     rsi, rsi
0x180006261  and     rsi, r14
0x180006264  jz      short loc_1800062D2
0x180006266  mov     r15, [rsi+8]
0x18000626a  test    r15, r15
0x18000626d  jz      short loc_180006290
0x18000626f  mov     rcx, [r15+8]
0x180006273  mov     rax, [r15]
0x180006276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000627b  mov     rbx, [r15+10h]
0x18000627f  mov     rcx, r15
0x180006282  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006288  mov     r15, rbx
0x18000628b  test    rbx, rbx
0x18000628e  jnz     short loc_18000626F
0x180006290  mov     qword ptr [rsi+8], 0
0x180006298  mov     qword ptr [rdi+10h], 0
0x1800062a0  mov     rcx, [rdi+40h]
0x1800062a4  test    rcx, rcx
0x1800062a7  jz      short loc_1800062B5
0x1800062a9  mov     rax, [rcx]
0x1800062ac  mov     rax, [rax+10h]
0x1800062b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062b5  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800062b9  call    cs:__imp_DeleteCriticalSection
0x1800062bf  mov     dword ptr [r14], 0
0x1800062c6  add     rsp, 20h
0x1800062ca  pop     r15
0x1800062cc  pop     r14
0x1800062ce  pop     rdi
0x1800062cf  pop     rsi
0x1800062d0  pop     rbx
0x1800062d1  retn
0x1800062d2  mov     ecx, 0C0000005h; unsigned int
0x1800062d7  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
