# ATL::CAtlModule::Term(void)

- ea: `0x140005c54`
- end: `0x140005cf9`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1400025d4`

## callees

- `0x140005c54`
- `0x1400062fc`
- `0x140013010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140005c9e`
- `msvcrt!??3@YAXPEAX@Z` at `0x140005c9e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005cd5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005cd5`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v2; // r14
  __int64 v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = v2 & -(__int64)(this != 0);
      if ( !v3 )
      {
        ATL::_AtlRaiseException(0xC0000005);
        JUMPOUT(0x140005CF8LL);
      }
      v4 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
      if ( v4 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v4)(v4[1]);
          v5 = (_QWORD *)v4[2];
          operator delete(v4);
          v4 = v5;
        }
        while ( v5 );
      }
      *(_QWORD *)(v3 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v6 = *((_QWORD *)this + 8);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x140005c54  push    rbx
0x140005c56  push    rsi
0x140005c57  push    rdi
0x140005c58  push    r14
0x140005c5a  push    r15
0x140005c5c  sub     rsp, 20h
0x140005c60  mov     rdi, rcx
0x140005c63  lea     r14, [rcx+8]
0x140005c67  cmp     dword ptr [r14], 0
0x140005c6b  jz      short loc_140005CE2
0x140005c6d  cmp     qword ptr [rcx+10h], 0
0x140005c72  jz      short loc_140005CBC
0x140005c74  mov     rax, rcx
0x140005c77  neg     rax
0x140005c7a  sbb     rsi, rsi
0x140005c7d  and     rsi, r14
0x140005c80  jz      short loc_140005CEE
0x140005c82  mov     r15, [rsi+8]
0x140005c86  test    r15, r15
0x140005c89  jz      short loc_140005CAC
0x140005c8b  mov     rcx, [r15+8]
0x140005c8f  mov     rax, [r15]
0x140005c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c97  mov     rbx, [r15+10h]
0x140005c9b  mov     rcx, r15
0x140005c9e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140005ca4  mov     r15, rbx
0x140005ca7  test    rbx, rbx
0x140005caa  jnz     short loc_140005C8B
0x140005cac  mov     qword ptr [rsi+8], 0
0x140005cb4  mov     qword ptr [rdi+10h], 0
0x140005cbc  mov     rcx, [rdi+40h]
0x140005cc0  test    rcx, rcx
0x140005cc3  jz      short loc_140005CD1
0x140005cc5  mov     rax, [rcx]
0x140005cc8  mov     rax, [rax+10h]
0x140005ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cd1  lea     rcx, [rdi+18h]; lpCriticalSection
0x140005cd5  call    cs:__imp_DeleteCriticalSection
0x140005cdb  mov     dword ptr [r14], 0
0x140005ce2  add     rsp, 20h
0x140005ce6  pop     r15
0x140005ce8  pop     r14
0x140005cea  pop     rdi
0x140005ceb  pop     rsi
0x140005cec  pop     rbx
0x140005ced  retn
0x140005cee  mov     ecx, 0C0000005h; unsigned int
0x140005cf3  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
