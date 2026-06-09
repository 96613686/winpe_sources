# CWMVideoDecMediaObject::DeinitDecoder(void)

- ea: `0x180003c70`
- end: `0x180003cdf`
- name: `?DeinitDecoder@CWMVideoDecMediaObject@@IEAAJXZ`
- size: `111`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002858`
- `0x180003d80`
- `0x180003e70`
- `0x1800078c0`

## callees

- `0x180003c70`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003cc1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003cc1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c91`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::DeinitDecoder(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  void (__fastcall ***DebugInfo)(_QWORD, _QWORD); // rcx

  if ( this[24].DebugInfo )
  {
    v2 = this + 23;
    EnterCriticalSection(this + 23);
    DebugInfo = (void (__fastcall ***)(_QWORD, _QWORD))this[24].DebugInfo;
    if ( DebugInfo )
      (**DebugInfo)(DebugInfo, 1);
    this[24].DebugInfo = 0;
    LeaveCriticalSection(v2);
    *(_QWORD *)&this[24].LockCount = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180003c70  mov     [rsp+arg_0], rbx
0x180003c75  push    rdi
0x180003c76  sub     rsp, 20h
0x180003c7a  cmp     qword ptr [rcx+3C0h], 0
0x180003c82  mov     rbx, rcx
0x180003c85  jz      short loc_180003CD2
0x180003c87  lea     rdi, [rcx+398h]
0x180003c8e  mov     rcx, rdi; lpCriticalSection
0x180003c91  call    cs:__imp_EnterCriticalSection
0x180003c97  mov     rcx, [rbx+3C0h]
0x180003c9e  test    rcx, rcx
0x180003ca1  jz      short loc_180003CB3
0x180003ca3  mov     rax, [rcx]
0x180003ca6  mov     edx, 1
0x180003cab  mov     rax, [rax]
0x180003cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cb3  mov     rcx, rdi; lpCriticalSection
0x180003cb6  mov     qword ptr [rbx+3C0h], 0
0x180003cc1  call    cs:__imp_LeaveCriticalSection
0x180003cc7  mov     qword ptr [rbx+3C8h], 0
0x180003cd2  mov     rbx, [rsp+28h+arg_0]
0x180003cd7  xor     eax, eax
0x180003cd9  add     rsp, 20h
0x180003cdd  pop     rdi
0x180003cde  retn
```
