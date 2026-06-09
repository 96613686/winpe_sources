# ATL::CRegObject::~CRegObject(void)

- ea: `0x180003190`
- end: `0x18000322c`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800032c0`
- `0x18000637c`
- `0x18000669c`

## callees

- `0x180003190`
- `0x180004768`

## import_xrefs

- `msvcrt!free` at `0x1800031f1`
- `msvcrt!free` at `0x180003207`
- `msvcrt!free` at `0x1800031f1`
- `msvcrt!free` at `0x180003207`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800031db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800031db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800031c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800031c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800031b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800031b3`

## pseudocode

```c
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  void **v3; // rdi
  void *v4; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  *(_QWORD *)this = &ATL::CRegObject::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v3 = (void **)((char *)this + 8);
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  LeaveCriticalSection(v2);
  if ( LOBYTE(v2[1].DebugInfo) )
  {
    LOBYTE(v2[1].DebugInfo) = 0;
    DeleteCriticalSection(v2);
  }
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  if ( *v3 )
  {
    free(*v3);
    *v3 = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 2) = 0;
  }
  *((_DWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x180003190  mov     [rsp+arg_0], rbx
0x180003195  mov     [rsp+arg_8], rsi
0x18000319a  push    rdi
0x18000319b  sub     rsp, 20h
0x18000319f  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800031a6  mov     rbx, rcx
0x1800031a9  lea     rsi, [rcx+20h]
0x1800031ad  mov     [rcx], rax
0x1800031b0  mov     rcx, rsi; lpCriticalSection
0x1800031b3  call    cs:__imp_EnterCriticalSection
0x1800031b9  lea     rdi, [rbx+8]
0x1800031bd  mov     rcx, rdi; this
0x1800031c0  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x1800031c5  mov     rcx, rsi; lpCriticalSection
0x1800031c8  call    cs:__imp_LeaveCriticalSection
0x1800031ce  cmp     byte ptr [rsi+28h], 0
0x1800031d2  jz      short loc_1800031E1
0x1800031d4  mov     rcx, rsi; lpCriticalSection
0x1800031d7  mov     byte ptr [rsi+28h], 0
0x1800031db  call    cs:__imp_DeleteCriticalSection
0x1800031e1  mov     rcx, rdi; this
0x1800031e4  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x1800031e9  mov     rcx, [rdi]; Block
0x1800031ec  test    rcx, rcx
0x1800031ef  jz      short loc_1800031FE
0x1800031f1  call    cs:__imp_free
0x1800031f7  mov     qword ptr [rdi], 0
0x1800031fe  mov     rcx, [rbx+10h]; Block
0x180003202  test    rcx, rcx
0x180003205  jz      short loc_180003215
0x180003207  call    cs:__imp_free
0x18000320d  mov     qword ptr [rbx+10h], 0
0x180003215  mov     rsi, [rsp+28h+arg_8]
0x18000321a  mov     dword ptr [rbx+18h], 0
0x180003221  mov     rbx, [rsp+28h+arg_0]
0x180003226  add     rsp, 20h
0x18000322a  pop     rdi
0x18000322b  retn
```
