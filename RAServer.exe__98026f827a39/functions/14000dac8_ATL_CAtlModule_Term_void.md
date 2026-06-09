# ATL::CAtlModule::Term(void)

- ea: `0x14000dac8`
- end: `0x14000db7b`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000cb68`

## callees

- `0x14000dac8`
- `0x140017010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x14000db08`
- `KERNEL32!RaiseException` at `0x14000db08`
- `KERNEL32!DeleteCriticalSection` at `0x14000db62`
- `KERNEL32!DeleteCriticalSection` at `0x14000db62`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000db2b`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000db2b`

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
        RaiseException(0xC0000005, 1u, 0, 0);
        __debugbreak();
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
0x14000dac8  push    rbx
0x14000daca  push    rsi
0x14000dacb  push    rdi
0x14000dacc  push    r14
0x14000dace  push    r15
0x14000dad0  sub     rsp, 20h
0x14000dad4  mov     rdi, rcx
0x14000dad7  lea     r14, [rcx+8]
0x14000dadb  cmp     dword ptr [r14], 0
0x14000dadf  jz      loc_14000DB6F
0x14000dae5  cmp     qword ptr [rcx+10h], 0
0x14000daea  jz      short loc_14000DB49
0x14000daec  mov     rax, rcx
0x14000daef  neg     rax
0x14000daf2  sbb     rsi, rsi
0x14000daf5  and     rsi, r14
0x14000daf8  jnz     short loc_14000DB0F
0x14000dafa  xor     r9d, r9d; lpArguments
0x14000dafd  xor     r8d, r8d; nNumberOfArguments
0x14000db00  lea     edx, [rsi+1]; dwExceptionFlags
0x14000db03  mov     ecx, 0C0000005h; dwExceptionCode
0x14000db08  call    cs:__imp_RaiseException
0x14000db0e  int     3; Trap to Debugger
0x14000db0f  mov     r15, [rsi+8]
0x14000db13  test    r15, r15
0x14000db16  jz      short loc_14000DB39
0x14000db18  mov     rcx, [r15+8]
0x14000db1c  mov     rax, [r15]
0x14000db1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db24  mov     rbx, [r15+10h]
0x14000db28  mov     rcx, r15
0x14000db2b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000db31  mov     r15, rbx
0x14000db34  test    rbx, rbx
0x14000db37  jnz     short loc_14000DB18
0x14000db39  mov     qword ptr [rsi+8], 0
0x14000db41  mov     qword ptr [rdi+10h], 0
0x14000db49  mov     rcx, [rdi+40h]
0x14000db4d  test    rcx, rcx
0x14000db50  jz      short loc_14000DB5E
0x14000db52  mov     rax, [rcx]
0x14000db55  mov     rax, [rax+10h]
0x14000db59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db5e  lea     rcx, [rdi+18h]; lpCriticalSection
0x14000db62  call    cs:__imp_DeleteCriticalSection
0x14000db68  mov     dword ptr [r14], 0
0x14000db6f  add     rsp, 20h
0x14000db73  pop     r15
0x14000db75  pop     r14
0x14000db77  pop     rdi
0x14000db78  pop     rsi
0x14000db79  pop     rbx
0x14000db7a  retn
```
