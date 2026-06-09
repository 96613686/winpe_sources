# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18000c0b0`
- end: `0x18000c154`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000c160`
- `0x18000cfa0`

## callees

- `0x180001be0`
- `0x18000b5c4`
- `0x18000c0b0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c130`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c130`

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
        JUMPOUT(0x18000C153LL);
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
0x18000c0b0  push    rbx
0x18000c0b2  push    rsi
0x18000c0b3  push    rdi
0x18000c0b4  push    r14
0x18000c0b6  push    r15
0x18000c0b8  sub     rsp, 20h
0x18000c0bc  lea     r14, [rcx+8]
0x18000c0c0  mov     rdi, rcx
0x18000c0c3  cmp     dword ptr [r14], 0
0x18000c0c7  jz      short loc_18000C13D
0x18000c0c9  cmp     qword ptr [rcx+10h], 0
0x18000c0ce  jz      short loc_18000C117
0x18000c0d0  mov     rax, rcx
0x18000c0d3  neg     rax
0x18000c0d6  sbb     rsi, rsi
0x18000c0d9  and     rsi, r14
0x18000c0dc  jz      short loc_18000C149
0x18000c0de  mov     r15, [rsi+8]
0x18000c0e2  test    r15, r15
0x18000c0e5  jz      short loc_18000C107
0x18000c0e7  mov     rcx, [r15+8]
0x18000c0eb  mov     rax, [r15]
0x18000c0ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0f3  mov     rbx, [r15+10h]
0x18000c0f7  mov     rcx, r15; Block
0x18000c0fa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c0ff  mov     r15, rbx
0x18000c102  test    rbx, rbx
0x18000c105  jnz     short loc_18000C0E7
0x18000c107  mov     qword ptr [rsi+8], 0
0x18000c10f  mov     qword ptr [rdi+10h], 0
0x18000c117  mov     rcx, [rdi+40h]
0x18000c11b  test    rcx, rcx
0x18000c11e  jz      short loc_18000C12C
0x18000c120  mov     rax, [rcx]
0x18000c123  mov     rax, [rax+10h]
0x18000c127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c12c  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000c130  call    cs:__imp_DeleteCriticalSection
0x18000c136  mov     dword ptr [r14], 0
0x18000c13d  add     rsp, 20h
0x18000c141  pop     r15
0x18000c143  pop     r14
0x18000c145  pop     rdi
0x18000c146  pop     rsi
0x18000c147  pop     rbx
0x18000c148  retn
0x18000c149  mov     ecx, 0C0000005h; unsigned int
0x18000c14e  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
