# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18000ac6c`
- end: `0x18000ad15`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000ae60`
- `0x180020d50`

## callees

- `0x180003914`
- `0x18000a90c`
- `0x18000ac6c`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000acf1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000acf1`

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
        JUMPOUT(0x18000AD14LL);
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
0x18000ac6c  push    rbx
0x18000ac6e  push    rsi
0x18000ac6f  push    rdi
0x18000ac70  push    r14
0x18000ac72  push    r15
0x18000ac74  sub     rsp, 20h
0x18000ac78  mov     rdi, rcx
0x18000ac7b  lea     r14, [rcx+8]
0x18000ac7f  cmp     dword ptr [r14], 0
0x18000ac83  jz      short loc_18000ACFE
0x18000ac85  cmp     qword ptr [rcx+10h], 0
0x18000ac8a  jz      short loc_18000ACD8
0x18000ac8c  mov     rax, rcx
0x18000ac8f  neg     rax
0x18000ac92  sbb     rsi, rsi
0x18000ac95  and     rsi, r14
0x18000ac98  jz      short loc_18000AD0A
0x18000ac9a  mov     r15, [rsi+8]
0x18000ac9e  test    r15, r15
0x18000aca1  jz      short loc_18000ACC8
0x18000aca3  mov     rcx, [r15+8]
0x18000aca7  mov     rax, [r15]
0x18000acaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acaf  mov     rbx, [r15+10h]
0x18000acb3  mov     edx, 18h
0x18000acb8  mov     rcx, r15; Block
0x18000acbb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000acc0  mov     r15, rbx
0x18000acc3  test    rbx, rbx
0x18000acc6  jnz     short loc_18000ACA3
0x18000acc8  mov     qword ptr [rsi+8], 0
0x18000acd0  mov     qword ptr [rdi+10h], 0
0x18000acd8  mov     rcx, [rdi+40h]
0x18000acdc  test    rcx, rcx
0x18000acdf  jz      short loc_18000ACED
0x18000ace1  mov     rax, [rcx]
0x18000ace4  mov     rax, [rax+10h]
0x18000ace8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aced  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000acf1  call    cs:__imp_DeleteCriticalSection
0x18000acf7  mov     dword ptr [r14], 0
0x18000acfe  add     rsp, 20h
0x18000ad02  pop     r15
0x18000ad04  pop     r14
0x18000ad06  pop     rdi
0x18000ad07  pop     rsi
0x18000ad08  pop     rbx
0x18000ad09  retn
0x18000ad0a  mov     ecx, 0C0000005h; unsigned int
0x18000ad0f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
