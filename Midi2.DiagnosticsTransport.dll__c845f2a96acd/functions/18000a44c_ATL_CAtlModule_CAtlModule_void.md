# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18000a44c`
- end: `0x18000a4f5`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000a640`
- `0x180012550`

## callees

- `0x1800033f4`
- `0x18000a0ec`
- `0x18000a44c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a4d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a4d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
        JUMPOUT(0x18000A4F4LL);
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
0x18000a44c  push    rbx
0x18000a44e  push    rsi
0x18000a44f  push    rdi
0x18000a450  push    r14
0x18000a452  push    r15
0x18000a454  sub     rsp, 20h
0x18000a458  mov     rdi, rcx
0x18000a45b  lea     r14, [rcx+8]
0x18000a45f  cmp     dword ptr [r14], 0
0x18000a463  jz      short loc_18000A4DE
0x18000a465  cmp     qword ptr [rcx+10h], 0
0x18000a46a  jz      short loc_18000A4B8
0x18000a46c  mov     rax, rcx
0x18000a46f  neg     rax
0x18000a472  sbb     rsi, rsi
0x18000a475  and     rsi, r14
0x18000a478  jz      short loc_18000A4EA
0x18000a47a  mov     r15, [rsi+8]
0x18000a47e  test    r15, r15
0x18000a481  jz      short loc_18000A4A8
0x18000a483  mov     rcx, [r15+8]
0x18000a487  mov     rax, [r15]
0x18000a48a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a48f  mov     rbx, [r15+10h]
0x18000a493  mov     edx, 18h
0x18000a498  mov     rcx, r15; Block
0x18000a49b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a4a0  mov     r15, rbx
0x18000a4a3  test    rbx, rbx
0x18000a4a6  jnz     short loc_18000A483
0x18000a4a8  mov     qword ptr [rsi+8], 0
0x18000a4b0  mov     qword ptr [rdi+10h], 0
0x18000a4b8  mov     rcx, [rdi+40h]
0x18000a4bc  test    rcx, rcx
0x18000a4bf  jz      short loc_18000A4CD
0x18000a4c1  mov     rax, [rcx]
0x18000a4c4  mov     rax, [rax+10h]
0x18000a4c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4cd  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000a4d1  call    cs:__imp_DeleteCriticalSection
0x18000a4d7  mov     dword ptr [r14], 0
0x18000a4de  add     rsp, 20h
0x18000a4e2  pop     r15
0x18000a4e4  pop     r14
0x18000a4e6  pop     rdi
0x18000a4e7  pop     rsi
0x18000a4e8  pop     rbx
0x18000a4e9  retn
0x18000a4ea  mov     ecx, 0C0000005h; unsigned int
0x18000a4ef  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
