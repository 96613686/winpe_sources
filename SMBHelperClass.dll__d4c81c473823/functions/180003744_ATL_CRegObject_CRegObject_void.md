# ATL::CRegObject::~CRegObject(void)

- ea: `0x180003744`
- end: `0x1800037e0`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b70`
- `0x180008c84`

## callees

- `0x180003744`
- `0x180004770`

## import_xrefs

- `msvcrt!free` at `0x1800037a5`
- `msvcrt!free` at `0x1800037bb`
- `msvcrt!free` at `0x1800037a5`
- `msvcrt!free` at `0x1800037bb`
- `KERNEL32!LeaveCriticalSection` at `0x18000377c`
- `KERNEL32!LeaveCriticalSection` at `0x18000377c`
- `KERNEL32!EnterCriticalSection` at `0x180003767`
- `KERNEL32!EnterCriticalSection` at `0x180003767`
- `KERNEL32!DeleteCriticalSection` at `0x18000378f`
- `KERNEL32!DeleteCriticalSection` at `0x18000378f`

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
0x180003744  mov     [rsp+arg_0], rbx
0x180003749  mov     [rsp+arg_8], rsi
0x18000374e  push    rdi
0x18000374f  sub     rsp, 20h
0x180003753  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000375a  mov     rbx, rcx
0x18000375d  lea     rsi, [rcx+20h]
0x180003761  mov     [rcx], rax
0x180003764  mov     rcx, rsi; lpCriticalSection
0x180003767  call    cs:__imp_EnterCriticalSection
0x18000376d  lea     rdi, [rbx+8]
0x180003771  mov     rcx, rdi; this
0x180003774  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180003779  mov     rcx, rsi; lpCriticalSection
0x18000377c  call    cs:__imp_LeaveCriticalSection
0x180003782  cmp     byte ptr [rsi+28h], 0
0x180003786  jz      short loc_180003795
0x180003788  mov     rcx, rsi; lpCriticalSection
0x18000378b  mov     byte ptr [rsi+28h], 0
0x18000378f  call    cs:__imp_DeleteCriticalSection
0x180003795  mov     rcx, rdi; this
0x180003798  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000379d  mov     rcx, [rdi]; Block
0x1800037a0  test    rcx, rcx
0x1800037a3  jz      short loc_1800037B2
0x1800037a5  call    cs:__imp_free
0x1800037ab  mov     qword ptr [rdi], 0
0x1800037b2  mov     rcx, [rbx+10h]; Block
0x1800037b6  test    rcx, rcx
0x1800037b9  jz      short loc_1800037C9
0x1800037bb  call    cs:__imp_free
0x1800037c1  mov     qword ptr [rbx+10h], 0
0x1800037c9  mov     rsi, [rsp+28h+arg_8]
0x1800037ce  mov     dword ptr [rbx+18h], 0
0x1800037d5  mov     rbx, [rsp+28h+arg_0]
0x1800037da  add     rsp, 20h
0x1800037de  pop     rdi
0x1800037df  retn
```
