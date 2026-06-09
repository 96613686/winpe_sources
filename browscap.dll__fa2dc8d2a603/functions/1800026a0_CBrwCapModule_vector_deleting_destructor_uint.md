# CBrwCapModule::`vector deleting destructor'(uint)

- ea: `0x1800026a0`
- end: `0x1800026e7`
- name: `??_ECBrwCapModule@@UEAAPEAXI@Z`
- size: `71`
- prototype: `void *__fastcall(CBrwCapModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800026a0`
- `0x1800064c0`

## import_xrefs

- `msvcrt!free` at `0x1800026d3`
- `msvcrt!free` at `0x1800026d3`
- `KERNEL32!DeleteCriticalSection` at `0x1800026b3`
- `KERNEL32!DeleteCriticalSection` at `0x1800026b3`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall CBrwCapModule::`vector deleting destructor'(
        struct _RTL_CRITICAL_SECTION *this,
        char a2)
{
  unsigned int v4; // edx

  DeleteCriticalSection(this + 2);
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComModule::`vftable';
  ATL::CAtlModule::Term((ATL::CAtlModule *)this, v4);
  if ( (a2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x1800026a0  mov     [rsp+arg_0], rbx
0x1800026a5  push    rdi
0x1800026a6  sub     rsp, 20h
0x1800026aa  mov     rdi, rcx
0x1800026ad  mov     ebx, edx
0x1800026af  add     rcx, 50h ; 'P'; lpCriticalSection
0x1800026b3  call    cs:__imp_DeleteCriticalSection
0x1800026b9  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x1800026c0  mov     rcx, rdi; this
0x1800026c3  mov     [rdi], rax
0x1800026c6  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x1800026cb  test    bl, 1
0x1800026ce  jz      short loc_1800026D9
0x1800026d0  mov     rcx, rdi; Block
0x1800026d3  call    cs:__imp_free
0x1800026d9  mov     rbx, [rsp+28h+arg_0]
0x1800026de  mov     rax, rdi
0x1800026e1  add     rsp, 20h
0x1800026e5  pop     rdi
0x1800026e6  retn
```
