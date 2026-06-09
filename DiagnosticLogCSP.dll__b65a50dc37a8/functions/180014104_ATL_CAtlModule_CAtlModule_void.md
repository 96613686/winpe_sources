# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180014104`
- end: `0x1800141b4`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `176`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800141c0`
- `0x1800385d0`

## callees

- `0x180001bf8`
- `0x180007530`
- `0x180014104`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014189`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014189`

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
        JUMPOUT(0x1800141B3LL);
      }
      v5 = *(_QWORD **)((v3 & -(__int64)(this != 0)) + 8);
      if ( v5 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
          v6 = (_QWORD *)v5[2];
          operator delete(v5, 0x18u);
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
0x180014104  push    rbx
0x180014106  push    rsi
0x180014107  push    rdi
0x180014108  push    r14
0x18001410a  push    r15
0x18001410c  sub     rsp, 20h
0x180014110  mov     rdi, rcx
0x180014113  lea     r14, [rcx+8]
0x180014117  cmp     dword ptr [r14], 0
0x18001411b  jz      short loc_18001419C
0x18001411d  cmp     qword ptr [rcx+10h], 0
0x180014122  jz      short loc_180014170
0x180014124  mov     rax, rcx
0x180014127  neg     rax
0x18001412a  sbb     rsi, rsi
0x18001412d  and     rsi, r14
0x180014130  jz      short loc_1800141A9
0x180014132  mov     r15, [rsi+8]
0x180014136  test    r15, r15
0x180014139  jz      short loc_180014160
0x18001413b  mov     rcx, [r15+8]
0x18001413f  mov     rax, [r15]
0x180014142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014147  mov     rbx, [r15+10h]
0x18001414b  mov     edx, 18h; unsigned __int64
0x180014150  mov     rcx, r15; void *
0x180014153  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014158  mov     r15, rbx
0x18001415b  test    rbx, rbx
0x18001415e  jnz     short loc_18001413B
0x180014160  mov     qword ptr [rsi+8], 0
0x180014168  mov     qword ptr [rdi+10h], 0
0x180014170  mov     rcx, [rdi+40h]
0x180014174  test    rcx, rcx
0x180014177  jz      short loc_180014185
0x180014179  mov     rax, [rcx]
0x18001417c  mov     rax, [rax+10h]
0x180014180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014185  lea     rcx, [rdi+18h]; lpCriticalSection
0x180014189  call    cs:__imp_DeleteCriticalSection
0x180014190  nop     dword ptr [rax+rax+00h]
0x180014195  mov     dword ptr [r14], 0
0x18001419c  add     rsp, 20h
0x1800141a0  pop     r15
0x1800141a2  pop     r14
0x1800141a4  pop     rdi
0x1800141a5  pop     rsi
0x1800141a6  pop     rbx
0x1800141a7  retn
0x1800141a9  mov     ecx, 0C0000005h; unsigned int
0x1800141ae  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
