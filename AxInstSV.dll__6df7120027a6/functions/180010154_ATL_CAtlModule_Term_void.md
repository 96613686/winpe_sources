# ATL::CAtlModule::Term(void)

- ea: `0x180010154`
- end: `0x18001020b`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001250`
- `0x180008838`
- `0x18000889c`
- `0x180008e30`

## callees

- `0x180001744`
- `0x180010154`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010194`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010194`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800101f2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800101f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180010154  push    rbx
0x180010156  push    rsi
0x180010157  push    rdi
0x180010158  push    r14
0x18001015a  push    r15
0x18001015c  sub     rsp, 20h
0x180010160  mov     rdi, rcx
0x180010163  lea     r14, [rcx+8]
0x180010167  cmp     dword ptr [r14], 0
0x18001016b  jz      loc_1800101FF
0x180010171  cmp     qword ptr [rcx+10h], 0
0x180010176  jz      short loc_1800101D9
0x180010178  mov     rax, rcx
0x18001017b  neg     rax
0x18001017e  sbb     rsi, rsi
0x180010181  and     rsi, r14
0x180010184  jnz     short loc_18001019B
0x180010186  xor     r9d, r9d; lpArguments
0x180010189  xor     r8d, r8d; nNumberOfArguments
0x18001018c  lea     edx, [rsi+1]; dwExceptionFlags
0x18001018f  mov     ecx, 0C0000005h; dwExceptionCode
0x180010194  call    cs:__imp_RaiseException
0x18001019a  int     3; Trap to Debugger
0x18001019b  mov     r15, [rsi+8]
0x18001019f  test    r15, r15
0x1800101a2  jz      short loc_1800101C9
0x1800101a4  mov     rcx, [r15+8]
0x1800101a8  mov     rax, [r15]
0x1800101ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101b0  mov     rbx, [r15+10h]
0x1800101b4  mov     edx, 18h
0x1800101b9  mov     rcx, r15; Block
0x1800101bc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800101c1  mov     r15, rbx
0x1800101c4  test    rbx, rbx
0x1800101c7  jnz     short loc_1800101A4
0x1800101c9  mov     qword ptr [rsi+8], 0
0x1800101d1  mov     qword ptr [rdi+10h], 0
0x1800101d9  mov     rcx, [rdi+40h]
0x1800101dd  test    rcx, rcx
0x1800101e0  jz      short loc_1800101EE
0x1800101e2  mov     rax, [rcx]
0x1800101e5  mov     rax, [rax+10h]
0x1800101e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101ee  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800101f2  call    cs:__imp_DeleteCriticalSection
0x1800101f8  mov     dword ptr [r14], 0
0x1800101ff  add     rsp, 20h
0x180010203  pop     r15
0x180010205  pop     r14
0x180010207  pop     rdi
0x180010208  pop     rsi
0x180010209  pop     rbx
0x18001020a  retn
```
