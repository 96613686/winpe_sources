# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18000226c`
- end: `0x180002310`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800023d0`
- `0x180006370`

## callees

- `0x180001170`
- `0x18000226c`
- `0x180004e44`
- `0x180007010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800022ec`
- `KERNEL32!DeleteCriticalSection` at `0x1800022ec`

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
        JUMPOUT(0x18000230FLL);
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
0x18000226c  push    rbx
0x18000226e  push    rsi
0x18000226f  push    rdi
0x180002270  push    r14
0x180002272  push    r15
0x180002274  sub     rsp, 20h
0x180002278  lea     r14, [rcx+8]
0x18000227c  mov     rdi, rcx
0x18000227f  cmp     dword ptr [r14], 0
0x180002283  jz      short loc_1800022F9
0x180002285  cmp     qword ptr [rcx+10h], 0
0x18000228a  jz      short loc_1800022D3
0x18000228c  mov     rax, rcx
0x18000228f  neg     rax
0x180002292  sbb     rsi, rsi
0x180002295  and     rsi, r14
0x180002298  jz      short loc_180002305
0x18000229a  mov     r15, [rsi+8]
0x18000229e  test    r15, r15
0x1800022a1  jz      short loc_1800022C3
0x1800022a3  mov     rcx, [r15+8]
0x1800022a7  mov     rax, [r15]
0x1800022aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022af  mov     rbx, [r15+10h]
0x1800022b3  mov     rcx, r15; Block
0x1800022b6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800022bb  mov     r15, rbx
0x1800022be  test    rbx, rbx
0x1800022c1  jnz     short loc_1800022A3
0x1800022c3  mov     qword ptr [rsi+8], 0
0x1800022cb  mov     qword ptr [rdi+10h], 0
0x1800022d3  mov     rcx, [rdi+40h]
0x1800022d7  test    rcx, rcx
0x1800022da  jz      short loc_1800022E8
0x1800022dc  mov     rax, [rcx]
0x1800022df  mov     rax, [rax+10h]
0x1800022e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022e8  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800022ec  call    cs:__imp_DeleteCriticalSection
0x1800022f2  mov     dword ptr [r14], 0
0x1800022f9  add     rsp, 20h
0x1800022fd  pop     r15
0x1800022ff  pop     r14
0x180002301  pop     rdi
0x180002302  pop     rsi
0x180002303  pop     rbx
0x180002304  retn
0x180002305  mov     ecx, 0C0000005h; unsigned int
0x18000230a  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
