# ATL::CAtlModule::Term(void)

- ea: `0x18001a228`
- end: `0x18001a2db`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180017810`
- `0x180043f80`

## callees

- `0x18001a228`
- `0x180045010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001a28b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a28b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a2c2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a2c2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001a268`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001a268`

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
0x18001a228  push    rbx
0x18001a22a  push    rsi
0x18001a22b  push    rdi
0x18001a22c  push    r14
0x18001a22e  push    r15
0x18001a230  sub     rsp, 20h
0x18001a234  lea     r14, [rcx+8]
0x18001a238  mov     rdi, rcx
0x18001a23b  cmp     dword ptr [r14], 0
0x18001a23f  jz      loc_18001A2CF
0x18001a245  cmp     qword ptr [rcx+10h], 0
0x18001a24a  jz      short loc_18001A2A9
0x18001a24c  mov     rax, rcx
0x18001a24f  neg     rax
0x18001a252  sbb     rsi, rsi
0x18001a255  and     rsi, r14
0x18001a258  jnz     short loc_18001A26F
0x18001a25a  xor     r9d, r9d; lpArguments
0x18001a25d  lea     edx, [rsi+1]; dwExceptionFlags
0x18001a260  xor     r8d, r8d; nNumberOfArguments
0x18001a263  mov     ecx, 0C0000005h; dwExceptionCode
0x18001a268  call    cs:__imp_RaiseException
0x18001a26e  int     3; Trap to Debugger
0x18001a26f  mov     r15, [rsi+8]
0x18001a273  test    r15, r15
0x18001a276  jz      short loc_18001A299
0x18001a278  mov     rcx, [r15+8]
0x18001a27c  mov     rax, [r15]
0x18001a27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a284  mov     rbx, [r15+10h]
0x18001a288  mov     rcx, r15
0x18001a28b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a291  mov     r15, rbx
0x18001a294  test    rbx, rbx
0x18001a297  jnz     short loc_18001A278
0x18001a299  mov     qword ptr [rsi+8], 0
0x18001a2a1  mov     qword ptr [rdi+10h], 0
0x18001a2a9  mov     rcx, [rdi+40h]
0x18001a2ad  test    rcx, rcx
0x18001a2b0  jz      short loc_18001A2BE
0x18001a2b2  mov     rax, [rcx]
0x18001a2b5  mov     rax, [rax+10h]
0x18001a2b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2be  lea     rcx, [rdi+18h]; lpCriticalSection
0x18001a2c2  call    cs:__imp_DeleteCriticalSection
0x18001a2c8  mov     dword ptr [r14], 0
0x18001a2cf  add     rsp, 20h
0x18001a2d3  pop     r15
0x18001a2d5  pop     r14
0x18001a2d7  pop     rdi
0x18001a2d8  pop     rsi
0x18001a2d9  pop     rbx
0x18001a2da  retn
```
