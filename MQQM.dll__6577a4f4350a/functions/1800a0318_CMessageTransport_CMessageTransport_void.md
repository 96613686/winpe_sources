# CMessageTransport::~CMessageTransport(void)

- ea: `0x1800a0318`
- end: `0x1800a046c`
- name: `??1CMessageTransport@@UEAA@XZ`
- size: `340`
- prototype: `void __fastcall(CMessageTransport *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800a04b0`

## callees

- `0x18000d1f0`
- `0x18000f430`
- `0x18000fa68`
- `0x180010b88`
- `0x180064f48`
- `0x1800a0318`
- `0x1800e4010`

## import_xrefs

- `msvcrt!free` at `0x1800a03c1`
- `msvcrt!free` at `0x1800a03fb`
- `msvcrt!free` at `0x1800a0409`
- `msvcrt!free` at `0x1800a0417`
- `msvcrt!free` at `0x1800a0425`
- `msvcrt!free` at `0x1800a03c1`
- `msvcrt!free` at `0x1800a03fb`
- `msvcrt!free` at `0x1800a0409`
- `msvcrt!free` at `0x1800a0417`
- `msvcrt!free` at `0x1800a0425`
- `KERNEL32!DeleteCriticalSection` at `0x1800a03b3`
- `KERNEL32!DeleteCriticalSection` at `0x1800a03cf`
- `KERNEL32!DeleteCriticalSection` at `0x1800a0430`
- `KERNEL32!DeleteCriticalSection` at `0x1800a0453`
- `KERNEL32!DeleteCriticalSection` at `0x1800a03b3`
- `KERNEL32!DeleteCriticalSection` at `0x1800a03cf`
- `KERNEL32!DeleteCriticalSection` at `0x1800a0430`
- `KERNEL32!DeleteCriticalSection` at `0x1800a0453`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CMessageTransport::~CMessageTransport(CMessageTransport *this)
{
  __int64 **v2; // rdi
  __int64 *v3; // rdx
  __int64 *v4; // rcx
  __int64 v5; // rax
  CReference *v6; // rcx
  CReference *v7; // rcx

  *(_QWORD *)this = &CMessageTransport::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, &WPP_28db9bc4cc773976798ea098a090597b_Traceguids);
  v2 = (__int64 **)((char *)this + 128);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == (__int64 *)v2 )
      break;
    v4 = (__int64 *)v3[1];
    v5 = *v3;
    *v4 = *v3;
    *(_QWORD *)(v5 + 8) = v4;
    v3[1] = 0;
    *v3 = 0;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 8LL))(*((_QWORD *)this + 10));
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 64LL))(*((_QWORD *)this + 10));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 912));
  free(*((void **)this + 113));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 816));
  v6 = (CReference *)*((_QWORD *)this + 101);
  if ( v6 )
    CReference::Release(v6);
  P<CInSeqLogContext>::~P<CInSeqLogContext>((char *)this + 800);
  free(*((void **)this + 98));
  free(*((void **)this + 97));
  free(*((void **)this + 96));
  free(*((void **)this + 24));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v7 = (CReference *)*((_QWORD *)this + 10);
  if ( v7 )
    CReference::Release(v7);
  SafeRelease<CSockTransport>(*((CReference **)this + 9));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  CTransport::~CTransport(this);
}

```

## disassembly

```asm
0x1800a0318  mov     [rsp+arg_0], rbx
0x1800a031d  push    rdi
0x1800a031e  sub     rsp, 20h
0x1800a0322  mov     rbx, rcx
0x1800a0325  lea     rax, ??_7CMessageTransport@@6B@; const CMessageTransport::`vftable'
0x1800a032c  mov     [rcx], rax
0x1800a032f  lea     rax, WPP_GLOBAL_Control
0x1800a0336  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a033d  cmp     rcx, rax
0x1800a0340  jz      short loc_1800A035D
0x1800a0342  test    byte ptr [rcx+6Ch], 4
0x1800a0346  jz      short loc_1800A035D
0x1800a0348  mov     edx, 0Ch
0x1800a034d  lea     r8, WPP_28db9bc4cc773976798ea098a090597b_Traceguids
0x1800a0354  mov     rcx, [rcx+60h]
0x1800a0358  call    WPP_SF_
0x1800a035d  lea     rdi, [rbx+80h]
0x1800a0364  mov     rdx, [rdi]
0x1800a0367  cmp     rdx, rdi
0x1800a036a  jz      short loc_1800A039B
0x1800a036c  mov     rcx, [rdx+8]
0x1800a0370  mov     rax, [rdx]
0x1800a0373  mov     [rcx], rax
0x1800a0376  mov     [rax+8], rcx
0x1800a037a  mov     qword ptr [rdx+8], 0
0x1800a0382  mov     qword ptr [rdx], 0
0x1800a0389  mov     rcx, [rbx+50h]
0x1800a038d  mov     rax, [rcx]
0x1800a0390  mov     rax, [rax+8]
0x1800a0394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0399  jmp     short loc_1800A0364
0x1800a039b  mov     rcx, [rbx+50h]
0x1800a039f  mov     rax, [rcx]
0x1800a03a2  mov     rax, [rax+40h]
0x1800a03a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a03ab  nop
0x1800a03ac  lea     rcx, [rbx+390h]; lpCriticalSection
0x1800a03b3  call    cs:__imp_DeleteCriticalSection
0x1800a03b9  nop
0x1800a03ba  mov     rcx, [rbx+388h]; Block
0x1800a03c1  call    cs:__imp_free
0x1800a03c7  nop
0x1800a03c8  lea     rcx, [rbx+330h]; lpCriticalSection
0x1800a03cf  call    cs:__imp_DeleteCriticalSection
0x1800a03d5  nop
0x1800a03d6  mov     rcx, [rbx+328h]; this
0x1800a03dd  test    rcx, rcx
0x1800a03e0  jz      short loc_1800A03E7
0x1800a03e2  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x1800a03e7  lea     rcx, [rbx+320h]
0x1800a03ee  call    ??1?$P@VCInSeqLogContext@@@@QEAA@XZ; P<CInSeqLogContext>::~P<CInSeqLogContext>(void)
0x1800a03f3  nop
0x1800a03f4  mov     rcx, [rbx+310h]; Block
0x1800a03fb  call    cs:__imp_free
0x1800a0401  nop
0x1800a0402  mov     rcx, [rbx+308h]; Block
0x1800a0409  call    cs:__imp_free
0x1800a040f  nop
0x1800a0410  mov     rcx, [rbx+300h]; Block
0x1800a0417  call    cs:__imp_free
0x1800a041d  nop
0x1800a041e  mov     rcx, [rbx+0C0h]; Block
0x1800a0425  call    cs:__imp_free
0x1800a042b  nop
0x1800a042c  lea     rcx, [rbx+58h]; lpCriticalSection
0x1800a0430  call    cs:__imp_DeleteCriticalSection
0x1800a0436  nop
0x1800a0437  mov     rcx, [rbx+50h]; this
0x1800a043b  test    rcx, rcx
0x1800a043e  jz      short loc_1800A0445
0x1800a0440  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x1800a0445  mov     rcx, [rbx+48h]
0x1800a0449  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x1800a044e  nop
0x1800a044f  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800a0453  call    cs:__imp_DeleteCriticalSection
0x1800a0459  nop
0x1800a045a  mov     rcx, rbx; this
0x1800a045d  mov     rbx, [rsp+28h+arg_0]
0x1800a0462  add     rsp, 20h
0x1800a0466  pop     rdi
0x1800a0467  jmp     ??1CTransport@@UEAA@XZ; CTransport::~CTransport(void)
```
