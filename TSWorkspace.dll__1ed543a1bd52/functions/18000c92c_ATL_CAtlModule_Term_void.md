# ATL::CAtlModule::Term(void)

- ea: `0x18000c92c`
- end: `0x18000c9e8`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `188`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800049f4`
- `0x1800055e0`
- `0x18000c9f0`

## callees

- `0x18000c92c`
- `0x1800a3010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c998`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c998`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c9cf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c9cf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c975`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c975`

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
0x18000c92c  push    rbx
0x18000c92e  push    rsi
0x18000c92f  push    rdi
0x18000c930  push    r14
0x18000c932  push    r15
0x18000c934  sub     rsp, 30h
0x18000c938  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18000c941  mov     rdi, rcx
0x18000c944  lea     r14, [rcx+8]
0x18000c948  cmp     dword ptr [r14], 0
0x18000c94c  jz      loc_18000C9DC
0x18000c952  cmp     qword ptr [rcx+10h], 0
0x18000c957  jz      short loc_18000C9B6
0x18000c959  mov     rax, rcx
0x18000c95c  neg     rax
0x18000c95f  sbb     rsi, rsi
0x18000c962  and     rsi, r14
0x18000c965  jnz     short loc_18000C97C
0x18000c967  xor     r9d, r9d; lpArguments
0x18000c96a  xor     r8d, r8d; nNumberOfArguments
0x18000c96d  lea     edx, [rsi+1]; dwExceptionFlags
0x18000c970  mov     ecx, 0C0000005h; dwExceptionCode
0x18000c975  call    cs:__imp_RaiseException
0x18000c97b  int     3; Trap to Debugger
0x18000c97c  mov     r15, [rsi+8]
0x18000c980  test    r15, r15
0x18000c983  jz      short loc_18000C9A6
0x18000c985  mov     rcx, [r15+8]
0x18000c989  mov     rax, [r15]
0x18000c98c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c991  mov     rbx, [r15+10h]
0x18000c995  mov     rcx, r15
0x18000c998  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c99e  mov     r15, rbx
0x18000c9a1  test    rbx, rbx
0x18000c9a4  jnz     short loc_18000C985
0x18000c9a6  mov     qword ptr [rsi+8], 0
0x18000c9ae  mov     qword ptr [rdi+10h], 0
0x18000c9b6  mov     rcx, [rdi+40h]
0x18000c9ba  test    rcx, rcx
0x18000c9bd  jz      short loc_18000C9CB
0x18000c9bf  mov     rax, [rcx]
0x18000c9c2  mov     rax, [rax+10h]
0x18000c9c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9cb  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000c9cf  call    cs:__imp_DeleteCriticalSection
0x18000c9d5  mov     dword ptr [r14], 0
0x18000c9dc  add     rsp, 30h
0x18000c9e0  pop     r15
0x18000c9e2  pop     r14
0x18000c9e4  pop     rdi
0x18000c9e5  pop     rsi
0x18000c9e6  pop     rbx
0x18000c9e7  retn
```
