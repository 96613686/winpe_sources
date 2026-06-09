# ATL::CAtlModule::Term(void)

- ea: `0x1400062a0`
- end: `0x140006344`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400059bc`

## callees

- `0x140001f64`
- `0x1400062a0`
- `0x14000655c`
- `0x140008010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140006325`
- `KERNEL32!DeleteCriticalSection` at `0x140006325`

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
        ATL::_AtlRaiseException((unsigned int)this, a2);
        JUMPOUT(0x140006343LL);
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
0x1400062a0  push    rbx
0x1400062a2  push    rsi
0x1400062a3  push    rdi
0x1400062a4  push    r14
0x1400062a6  push    r15
0x1400062a8  sub     rsp, 20h
0x1400062ac  lea     r14, [rcx+8]
0x1400062b0  mov     rdi, rcx
0x1400062b3  cmp     dword ptr [r14], 0
0x1400062b7  jz      short loc_140006332
0x1400062b9  cmp     qword ptr [rcx+10h], 0
0x1400062be  jz      short loc_14000630C
0x1400062c0  mov     rax, rcx
0x1400062c3  neg     rax
0x1400062c6  sbb     rsi, rsi
0x1400062c9  and     rsi, r14
0x1400062cc  jz      short loc_14000633E
0x1400062ce  mov     r15, [rsi+8]
0x1400062d2  test    r15, r15
0x1400062d5  jz      short loc_1400062FC
0x1400062d7  mov     rcx, [r15+8]
0x1400062db  mov     rax, [r15]
0x1400062de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062e3  mov     rbx, [r15+10h]
0x1400062e7  mov     edx, 18h
0x1400062ec  mov     rcx, r15; Block
0x1400062ef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400062f4  mov     r15, rbx
0x1400062f7  test    rbx, rbx
0x1400062fa  jnz     short loc_1400062D7
0x1400062fc  mov     qword ptr [rsi+8], 0
0x140006304  mov     qword ptr [rdi+10h], 0
0x14000630c  mov     rcx, [rdi+40h]
0x140006310  test    rcx, rcx
0x140006313  jz      short loc_140006321
0x140006315  mov     rax, [rcx]
0x140006318  mov     rax, [rax+10h]
0x14000631c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006321  lea     rcx, [rdi+18h]; lpCriticalSection
0x140006325  call    cs:__imp_DeleteCriticalSection
0x14000632b  mov     dword ptr [r14], 0
0x140006332  add     rsp, 20h
0x140006336  pop     r15
0x140006338  pop     r14
0x14000633a  pop     rdi
0x14000633b  pop     rsi
0x14000633c  pop     rbx
0x14000633d  retn
0x14000633e  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
