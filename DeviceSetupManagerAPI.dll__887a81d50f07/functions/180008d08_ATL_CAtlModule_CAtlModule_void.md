# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180008d08`
- end: `0x180008dac`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008dc0`
- `0x18000e8f0`

## callees

- `0x180001c6c`
- `0x180008d08`
- `0x180008f64`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d8d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d8d`

## pseudocode

```c
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
        ATL::_AtlRaiseException((unsigned int)this, a2);
        JUMPOUT(0x180008DABLL);
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
0x180008d08  push    rbx
0x180008d0a  push    rsi
0x180008d0b  push    rdi
0x180008d0c  push    r14
0x180008d0e  push    r15
0x180008d10  sub     rsp, 20h
0x180008d14  mov     rdi, rcx
0x180008d17  lea     r14, [rcx+8]
0x180008d1b  cmp     dword ptr [r14], 0
0x180008d1f  jz      short loc_180008D9A
0x180008d21  cmp     qword ptr [rcx+10h], 0
0x180008d26  jz      short loc_180008D74
0x180008d28  mov     rax, rcx
0x180008d2b  neg     rax
0x180008d2e  sbb     rsi, rsi
0x180008d31  and     rsi, r14
0x180008d34  jz      short loc_180008DA6
0x180008d36  mov     r15, [rsi+8]
0x180008d3a  test    r15, r15
0x180008d3d  jz      short loc_180008D64
0x180008d3f  mov     rcx, [r15+8]
0x180008d43  mov     rax, [r15]
0x180008d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d4b  mov     rbx, [r15+10h]
0x180008d4f  mov     edx, 18h
0x180008d54  mov     rcx, r15; Block
0x180008d57  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008d5c  mov     r15, rbx
0x180008d5f  test    rbx, rbx
0x180008d62  jnz     short loc_180008D3F
0x180008d64  mov     qword ptr [rsi+8], 0
0x180008d6c  mov     qword ptr [rdi+10h], 0
0x180008d74  mov     rcx, [rdi+40h]
0x180008d78  test    rcx, rcx
0x180008d7b  jz      short loc_180008D89
0x180008d7d  mov     rax, [rcx]
0x180008d80  mov     rax, [rax+10h]
0x180008d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d89  lea     rcx, [rdi+18h]; lpCriticalSection
0x180008d8d  call    cs:__imp_DeleteCriticalSection
0x180008d93  mov     dword ptr [r14], 0
0x180008d9a  add     rsp, 20h
0x180008d9e  pop     r15
0x180008da0  pop     r14
0x180008da2  pop     rdi
0x180008da3  pop     rsi
0x180008da4  pop     rbx
0x180008da5  retn
0x180008da6  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
