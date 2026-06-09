# ATL::CAtlModule::Term(void)

- ea: `0x180023134`
- end: `0x1800231e7`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001ebc4`

## callees

- `0x180023134`
- `0x18005e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180023197`
- `msvcrt!??3@YAXPEAX@Z` at `0x180023197`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800231ce`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800231ce`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023174`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023174`

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
0x180023134  push    rbx
0x180023136  push    rsi
0x180023137  push    rdi
0x180023138  push    r14
0x18002313a  push    r15
0x18002313c  sub     rsp, 20h
0x180023140  mov     rdi, rcx
0x180023143  lea     r14, [rcx+8]
0x180023147  cmp     dword ptr [r14], 0
0x18002314b  jz      loc_1800231DB
0x180023151  cmp     qword ptr [rcx+10h], 0
0x180023156  jz      short loc_1800231B5
0x180023158  mov     rax, rcx
0x18002315b  neg     rax
0x18002315e  sbb     rsi, rsi
0x180023161  and     rsi, r14
0x180023164  jnz     short loc_18002317B
0x180023166  xor     r9d, r9d; lpArguments
0x180023169  xor     r8d, r8d; nNumberOfArguments
0x18002316c  lea     edx, [rsi+1]; dwExceptionFlags
0x18002316f  mov     ecx, 0C0000005h; dwExceptionCode
0x180023174  call    cs:__imp_RaiseException
0x18002317a  int     3; Trap to Debugger
0x18002317b  mov     r15, [rsi+8]
0x18002317f  test    r15, r15
0x180023182  jz      short loc_1800231A5
0x180023184  mov     rcx, [r15+8]
0x180023188  mov     rax, [r15]
0x18002318b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023190  mov     rbx, [r15+10h]
0x180023194  mov     rcx, r15
0x180023197  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002319d  mov     r15, rbx
0x1800231a0  test    rbx, rbx
0x1800231a3  jnz     short loc_180023184
0x1800231a5  mov     qword ptr [rsi+8], 0
0x1800231ad  mov     qword ptr [rdi+10h], 0
0x1800231b5  mov     rcx, [rdi+40h]
0x1800231b9  test    rcx, rcx
0x1800231bc  jz      short loc_1800231CA
0x1800231be  mov     rax, [rcx]
0x1800231c1  mov     rax, [rax+10h]
0x1800231c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231ca  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800231ce  call    cs:__imp_DeleteCriticalSection
0x1800231d4  mov     dword ptr [r14], 0
0x1800231db  add     rsp, 20h
0x1800231df  pop     r15
0x1800231e1  pop     r14
0x1800231e3  pop     rdi
0x1800231e4  pop     rsi
0x1800231e5  pop     rbx
0x1800231e6  retn
```
