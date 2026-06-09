# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x1800031a8`
- end: `0x18000324c`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003830`
- `0x1800167a0`

## callees

- `0x180001790`
- `0x1800031a8`
- `0x1800082ac`
- `0x180017010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180003228`
- `KERNEL32!DeleteCriticalSection` at `0x180003228`

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
        JUMPOUT(0x18000324BLL);
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
0x1800031a8  push    rbx
0x1800031aa  push    rsi
0x1800031ab  push    rdi
0x1800031ac  push    r14
0x1800031ae  push    r15
0x1800031b0  sub     rsp, 20h
0x1800031b4  lea     r14, [rcx+8]
0x1800031b8  mov     rdi, rcx
0x1800031bb  cmp     dword ptr [r14], 0
0x1800031bf  jz      short loc_180003235
0x1800031c1  cmp     qword ptr [rcx+10h], 0
0x1800031c6  jz      short loc_18000320F
0x1800031c8  mov     rax, rcx
0x1800031cb  neg     rax
0x1800031ce  sbb     rsi, rsi
0x1800031d1  and     rsi, r14
0x1800031d4  jz      short loc_180003241
0x1800031d6  mov     r15, [rsi+8]
0x1800031da  test    r15, r15
0x1800031dd  jz      short loc_1800031FF
0x1800031df  mov     rcx, [r15+8]
0x1800031e3  mov     rax, [r15]
0x1800031e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031eb  mov     rbx, [r15+10h]
0x1800031ef  mov     rcx, r15; Block
0x1800031f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800031f7  mov     r15, rbx
0x1800031fa  test    rbx, rbx
0x1800031fd  jnz     short loc_1800031DF
0x1800031ff  mov     qword ptr [rsi+8], 0
0x180003207  mov     qword ptr [rdi+10h], 0
0x18000320f  mov     rcx, [rdi+40h]
0x180003213  test    rcx, rcx
0x180003216  jz      short loc_180003224
0x180003218  mov     rax, [rcx]
0x18000321b  mov     rax, [rax+10h]
0x18000321f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003224  lea     rcx, [rdi+18h]; lpCriticalSection
0x180003228  call    cs:__imp_DeleteCriticalSection
0x18000322e  mov     dword ptr [r14], 0
0x180003235  add     rsp, 20h
0x180003239  pop     r15
0x18000323b  pop     r14
0x18000323d  pop     rdi
0x18000323e  pop     rsi
0x18000323f  pop     rbx
0x180003240  retn
0x180003241  mov     ecx, 0C0000005h; unsigned int
0x180003246  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
