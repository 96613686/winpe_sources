# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180008d4c`
- end: `0x180008df5`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008f40`
- `0x18000d490`

## callees

- `0x180002024`
- `0x1800089ec`
- `0x180008d4c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008dd1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008dd1`

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
        JUMPOUT(0x180008DF4LL);
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
0x180008d4c  push    rbx
0x180008d4e  push    rsi
0x180008d4f  push    rdi
0x180008d50  push    r14
0x180008d52  push    r15
0x180008d54  sub     rsp, 20h
0x180008d58  mov     rdi, rcx
0x180008d5b  lea     r14, [rcx+8]
0x180008d5f  cmp     dword ptr [r14], 0
0x180008d63  jz      short loc_180008DDE
0x180008d65  cmp     qword ptr [rcx+10h], 0
0x180008d6a  jz      short loc_180008DB8
0x180008d6c  mov     rax, rcx
0x180008d6f  neg     rax
0x180008d72  sbb     rsi, rsi
0x180008d75  and     rsi, r14
0x180008d78  jz      short loc_180008DEA
0x180008d7a  mov     r15, [rsi+8]
0x180008d7e  test    r15, r15
0x180008d81  jz      short loc_180008DA8
0x180008d83  mov     rcx, [r15+8]
0x180008d87  mov     rax, [r15]
0x180008d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d8f  mov     rbx, [r15+10h]
0x180008d93  mov     edx, 18h
0x180008d98  mov     rcx, r15; Block
0x180008d9b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008da0  mov     r15, rbx
0x180008da3  test    rbx, rbx
0x180008da6  jnz     short loc_180008D83
0x180008da8  mov     qword ptr [rsi+8], 0
0x180008db0  mov     qword ptr [rdi+10h], 0
0x180008db8  mov     rcx, [rdi+40h]
0x180008dbc  test    rcx, rcx
0x180008dbf  jz      short loc_180008DCD
0x180008dc1  mov     rax, [rcx]
0x180008dc4  mov     rax, [rax+10h]
0x180008dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dcd  lea     rcx, [rdi+18h]; lpCriticalSection
0x180008dd1  call    cs:__imp_DeleteCriticalSection
0x180008dd7  mov     dword ptr [r14], 0
0x180008dde  add     rsp, 20h
0x180008de2  pop     r15
0x180008de4  pop     r14
0x180008de6  pop     rdi
0x180008de7  pop     rsi
0x180008de8  pop     rbx
0x180008de9  retn
0x180008dea  mov     ecx, 0C0000005h; unsigned int
0x180008def  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
