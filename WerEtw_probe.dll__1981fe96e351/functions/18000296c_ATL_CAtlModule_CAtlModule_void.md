# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18000296c`
- end: `0x180002a15`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002ab0`
- `0x180028df0`

## callees

- `0x180001894`
- `0x18000296c`
- `0x1800036b4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800029f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800029f1`

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
        JUMPOUT(0x180002A14LL);
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
0x18000296c  push    rbx
0x18000296e  push    rsi
0x18000296f  push    rdi
0x180002970  push    r14
0x180002972  push    r15
0x180002974  sub     rsp, 20h
0x180002978  mov     rdi, rcx
0x18000297b  lea     r14, [rcx+8]
0x18000297f  cmp     dword ptr [r14], 0
0x180002983  jz      short loc_1800029FE
0x180002985  cmp     qword ptr [rcx+10h], 0
0x18000298a  jz      short loc_1800029D8
0x18000298c  mov     rax, rcx
0x18000298f  neg     rax
0x180002992  sbb     rsi, rsi
0x180002995  and     rsi, r14
0x180002998  jz      short loc_180002A0A
0x18000299a  mov     r15, [rsi+8]
0x18000299e  test    r15, r15
0x1800029a1  jz      short loc_1800029C8
0x1800029a3  mov     rcx, [r15+8]
0x1800029a7  mov     rax, [r15]
0x1800029aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029af  mov     rbx, [r15+10h]
0x1800029b3  mov     edx, 18h
0x1800029b8  mov     rcx, r15; Block
0x1800029bb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800029c0  mov     r15, rbx
0x1800029c3  test    rbx, rbx
0x1800029c6  jnz     short loc_1800029A3
0x1800029c8  mov     qword ptr [rsi+8], 0
0x1800029d0  mov     qword ptr [rdi+10h], 0
0x1800029d8  mov     rcx, [rdi+40h]
0x1800029dc  test    rcx, rcx
0x1800029df  jz      short loc_1800029ED
0x1800029e1  mov     rax, [rcx]
0x1800029e4  mov     rax, [rax+10h]
0x1800029e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ed  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800029f1  call    cs:__imp_DeleteCriticalSection
0x1800029f7  mov     dword ptr [r14], 0
0x1800029fe  add     rsp, 20h
0x180002a02  pop     r15
0x180002a04  pop     r14
0x180002a06  pop     rdi
0x180002a07  pop     rsi
0x180002a08  pop     rbx
0x180002a09  retn
0x180002a0a  mov     ecx, 0C0000005h; unsigned int
0x180002a0f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
