# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18000c34c`
- end: `0x18000c3f5`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000c540`
- `0x180031e20`

## callees

- `0x1800041a4`
- `0x18000b1ac`
- `0x18000c34c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c3d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c3d1`

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
        JUMPOUT(0x18000C3F4LL);
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
0x18000c34c  push    rbx
0x18000c34e  push    rsi
0x18000c34f  push    rdi
0x18000c350  push    r14
0x18000c352  push    r15
0x18000c354  sub     rsp, 20h
0x18000c358  mov     rdi, rcx
0x18000c35b  lea     r14, [rcx+8]
0x18000c35f  cmp     dword ptr [r14], 0
0x18000c363  jz      short loc_18000C3DE
0x18000c365  cmp     qword ptr [rcx+10h], 0
0x18000c36a  jz      short loc_18000C3B8
0x18000c36c  mov     rax, rcx
0x18000c36f  neg     rax
0x18000c372  sbb     rsi, rsi
0x18000c375  and     rsi, r14
0x18000c378  jz      short loc_18000C3EA
0x18000c37a  mov     r15, [rsi+8]
0x18000c37e  test    r15, r15
0x18000c381  jz      short loc_18000C3A8
0x18000c383  mov     rcx, [r15+8]
0x18000c387  mov     rax, [r15]
0x18000c38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c38f  mov     rbx, [r15+10h]
0x18000c393  mov     edx, 18h
0x18000c398  mov     rcx, r15; Block
0x18000c39b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c3a0  mov     r15, rbx
0x18000c3a3  test    rbx, rbx
0x18000c3a6  jnz     short loc_18000C383
0x18000c3a8  mov     qword ptr [rsi+8], 0
0x18000c3b0  mov     qword ptr [rdi+10h], 0
0x18000c3b8  mov     rcx, [rdi+40h]
0x18000c3bc  test    rcx, rcx
0x18000c3bf  jz      short loc_18000C3CD
0x18000c3c1  mov     rax, [rcx]
0x18000c3c4  mov     rax, [rax+10h]
0x18000c3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3cd  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000c3d1  call    cs:__imp_DeleteCriticalSection
0x18000c3d7  mov     dword ptr [r14], 0
0x18000c3de  add     rsp, 20h
0x18000c3e2  pop     r15
0x18000c3e4  pop     r14
0x18000c3e6  pop     rdi
0x18000c3e7  pop     rsi
0x18000c3e8  pop     rbx
0x18000c3e9  retn
0x18000c3ea  mov     ecx, 0C0000005h; unsigned int
0x18000c3ef  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
