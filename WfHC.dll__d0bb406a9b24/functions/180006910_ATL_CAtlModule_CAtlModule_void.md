# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180006910`
- end: `0x1800069bd`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `173`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800069d0`

## callees

- `0x180006910`
- `0x180006b90`
- `0x18000e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006963`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006963`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000699a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000699a`

## pseudocode

```c
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this, unsigned int a2)
{
  char *v3; // rbp
  _QWORD *v4; // rdi
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = (char *)this + 8;
      if ( !this )
        v3 = 0;
      if ( !v3 )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x1800069BCLL);
      }
      v4 = (_QWORD *)*((_QWORD *)v3 + 1);
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
      *((_QWORD *)v3 + 1) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v6 = *((_QWORD *)this + 8);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *((_DWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x180006910  push    rbx
0x180006912  push    rbp
0x180006913  push    rsi
0x180006914  push    rdi
0x180006915  push    r14
0x180006917  sub     rsp, 20h
0x18000691b  mov     rsi, rcx
0x18000691e  cmp     dword ptr [rcx+8], 0
0x180006922  jz      loc_1800069A7
0x180006928  cmp     qword ptr [rcx+10h], 0
0x18000692d  jz      short loc_180006981
0x18000692f  lea     rbp, [rcx+8]
0x180006933  xor     eax, eax
0x180006935  test    rcx, rcx
0x180006938  cmovz   rbp, rax
0x18000693c  test    rbp, rbp
0x18000693f  jz      short loc_1800069B2
0x180006941  mov     rdi, [rbp+8]
0x180006945  test    rdi, rdi
0x180006948  jz      short loc_180006971
0x18000694a  nop     word ptr [rax+rax+00h]
0x180006950  mov     rcx, [rdi+8]
0x180006954  mov     rax, [rdi]
0x180006957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000695c  mov     rbx, [rdi+10h]
0x180006960  mov     rcx, rdi
0x180006963  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006969  mov     rdi, rbx
0x18000696c  test    rbx, rbx
0x18000696f  jnz     short loc_180006950
0x180006971  mov     qword ptr [rbp+8], 0
0x180006979  mov     qword ptr [rsi+10h], 0
0x180006981  mov     rcx, [rsi+40h]
0x180006985  test    rcx, rcx
0x180006988  jz      short loc_180006996
0x18000698a  mov     rax, [rcx]
0x18000698d  mov     rax, [rax+10h]
0x180006991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006996  lea     rcx, [rsi+18h]; lpCriticalSection
0x18000699a  call    cs:__imp_DeleteCriticalSection
0x1800069a0  mov     dword ptr [rsi+8], 0
0x1800069a7  add     rsp, 20h
0x1800069ab  pop     r14
0x1800069ad  pop     rdi
0x1800069ae  pop     rsi
0x1800069af  pop     rbp
0x1800069b0  pop     rbx
0x1800069b1  retn
0x1800069b2  mov     ecx, 0C0000005h; unsigned int
0x1800069b7  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
