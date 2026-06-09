# ATL::CRegObject::~CRegObject(void)

- ea: `0x180002530`
- end: `0x1800025cc`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002730`
- `0x18000672c`
- `0x180006b14`

## callees

- `0x180002530`
- `0x180003898`

## import_xrefs

- `msvcrt!free` at `0x180002591`
- `msvcrt!free` at `0x1800025a7`
- `msvcrt!free` at `0x180002591`
- `msvcrt!free` at `0x1800025a7`
- `KERNEL32!LeaveCriticalSection` at `0x180002568`
- `KERNEL32!LeaveCriticalSection` at `0x180002568`
- `KERNEL32!EnterCriticalSection` at `0x180002553`
- `KERNEL32!EnterCriticalSection` at `0x180002553`
- `KERNEL32!DeleteCriticalSection` at `0x18000257b`
- `KERNEL32!DeleteCriticalSection` at `0x18000257b`

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
0x180002530  mov     [rsp+arg_0], rbx
0x180002535  mov     [rsp+arg_8], rsi
0x18000253a  push    rdi
0x18000253b  sub     rsp, 20h
0x18000253f  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180002546  mov     rbx, rcx
0x180002549  lea     rsi, [rcx+20h]
0x18000254d  mov     [rcx], rax
0x180002550  mov     rcx, rsi; lpCriticalSection
0x180002553  call    cs:__imp_EnterCriticalSection
0x180002559  lea     rdi, [rbx+8]
0x18000255d  mov     rcx, rdi; this
0x180002560  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002565  mov     rcx, rsi; lpCriticalSection
0x180002568  call    cs:__imp_LeaveCriticalSection
0x18000256e  cmp     byte ptr [rsi+28h], 0
0x180002572  jz      short loc_180002581
0x180002574  mov     rcx, rsi; lpCriticalSection
0x180002577  mov     byte ptr [rsi+28h], 0
0x18000257b  call    cs:__imp_DeleteCriticalSection
0x180002581  mov     rcx, rdi; this
0x180002584  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002589  mov     rcx, [rdi]; Block
0x18000258c  test    rcx, rcx
0x18000258f  jz      short loc_18000259E
0x180002591  call    cs:__imp_free
0x180002597  mov     qword ptr [rdi], 0
0x18000259e  mov     rcx, [rbx+10h]; Block
0x1800025a2  test    rcx, rcx
0x1800025a5  jz      short loc_1800025B5
0x1800025a7  call    cs:__imp_free
0x1800025ad  mov     qword ptr [rbx+10h], 0
0x1800025b5  mov     rsi, [rsp+28h+arg_8]
0x1800025ba  mov     dword ptr [rbx+18h], 0
0x1800025c1  mov     rbx, [rsp+28h+arg_0]
0x1800025c6  add     rsp, 20h
0x1800025ca  pop     rdi
0x1800025cb  retn
```
