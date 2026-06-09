# ATL::CAtlModule::Term(void)

- ea: `0x1800029f4`
- end: `0x180002aa6`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `178`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800027f0`

## callees

- `0x1800012f0`
- `0x1800029f4`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002a8d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002a8d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002a34`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002a34`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v1; // r14
  __int64 v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v1 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = v1 & -(__int64)(this != 0);
      if ( !v3 )
      {
        RaiseException(0xC0000005, 1u, 0, 0);
        __debugbreak();
      }
      v4 = *(_QWORD **)((v1 & -(__int64)(this != 0)) + 8);
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
    *(_DWORD *)v1 = 0;
  }
}

```

## disassembly

```asm
0x1800029f4  push    rbx
0x1800029f6  push    rsi
0x1800029f7  push    rdi
0x1800029f8  push    r14
0x1800029fa  push    r15
0x1800029fc  sub     rsp, 20h
0x180002a00  lea     r14, [rcx+8]
0x180002a04  mov     rdi, rcx
0x180002a07  cmp     dword ptr [r14], 0
0x180002a0b  jz      loc_180002A9A
0x180002a11  cmp     qword ptr [rcx+10h], 0
0x180002a16  jz      short loc_180002A74
0x180002a18  mov     rax, rcx
0x180002a1b  neg     rax
0x180002a1e  sbb     rsi, rsi
0x180002a21  and     rsi, r14
0x180002a24  jnz     short loc_180002A3B
0x180002a26  xor     r9d, r9d; lpArguments
0x180002a29  lea     edx, [rsi+1]; dwExceptionFlags
0x180002a2c  xor     r8d, r8d; nNumberOfArguments
0x180002a2f  mov     ecx, 0C0000005h; dwExceptionCode
0x180002a34  call    cs:__imp_RaiseException
0x180002a3a  int     3; Trap to Debugger
0x180002a3b  mov     r15, [rsi+8]
0x180002a3f  test    r15, r15
0x180002a42  jz      short loc_180002A64
0x180002a44  mov     rcx, [r15+8]
0x180002a48  mov     rax, [r15]
0x180002a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a50  mov     rbx, [r15+10h]
0x180002a54  mov     rcx, r15; Block
0x180002a57  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002a5c  mov     r15, rbx
0x180002a5f  test    rbx, rbx
0x180002a62  jnz     short loc_180002A44
0x180002a64  mov     qword ptr [rsi+8], 0
0x180002a6c  mov     qword ptr [rdi+10h], 0
0x180002a74  mov     rcx, [rdi+40h]
0x180002a78  test    rcx, rcx
0x180002a7b  jz      short loc_180002A89
0x180002a7d  mov     rax, [rcx]
0x180002a80  mov     rax, [rax+10h]
0x180002a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a89  lea     rcx, [rdi+18h]; lpCriticalSection
0x180002a8d  call    cs:__imp_DeleteCriticalSection
0x180002a93  mov     dword ptr [r14], 0
0x180002a9a  add     rsp, 20h
0x180002a9e  pop     r15
0x180002aa0  pop     r14
0x180002aa2  pop     rdi
0x180002aa3  pop     rsi
0x180002aa4  pop     rbx
0x180002aa5  retn
```
