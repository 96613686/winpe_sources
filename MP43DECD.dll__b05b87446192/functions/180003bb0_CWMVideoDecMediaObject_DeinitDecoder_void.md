# CWMVideoDecMediaObject::DeinitDecoder(void)

- ea: `0x180003bb0`
- end: `0x180003c1f`
- name: `?DeinitDecoder@CWMVideoDecMediaObject@@IEAAJXZ`
- size: `111`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000279c`
- `0x180003cc0`
- `0x180003db0`
- `0x180007800`

## callees

- `0x180003bb0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c01`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003bd1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003bd1`

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
0x180003bb0  mov     [rsp+arg_0], rbx
0x180003bb5  push    rdi
0x180003bb6  sub     rsp, 20h
0x180003bba  cmp     qword ptr [rcx+3C0h], 0
0x180003bc2  mov     rbx, rcx
0x180003bc5  jz      short loc_180003C12
0x180003bc7  lea     rdi, [rcx+398h]
0x180003bce  mov     rcx, rdi; lpCriticalSection
0x180003bd1  call    cs:__imp_EnterCriticalSection
0x180003bd7  mov     rcx, [rbx+3C0h]
0x180003bde  test    rcx, rcx
0x180003be1  jz      short loc_180003BF3
0x180003be3  mov     rax, [rcx]
0x180003be6  mov     edx, 1
0x180003beb  mov     rax, [rax]
0x180003bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bf3  mov     rcx, rdi; lpCriticalSection
0x180003bf6  mov     qword ptr [rbx+3C0h], 0
0x180003c01  call    cs:__imp_LeaveCriticalSection
0x180003c07  mov     qword ptr [rbx+3C8h], 0
0x180003c12  mov     rbx, [rsp+28h+arg_0]
0x180003c17  xor     eax, eax
0x180003c19  add     rsp, 20h
0x180003c1d  pop     rdi
0x180003c1e  retn
```
