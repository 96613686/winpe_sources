# CMidi2DiagnosticsMidiConfigurationManager::`scalar deleting destructor'(uint)

- ea: `0x18000b930`
- end: `0x18000b97d`
- name: `??_GCMidi2DiagnosticsMidiConfigurationManager@@UEAAPEAXI@Z`
- size: `77`
- prototype: `void *__fastcall(CMidi2DiagnosticsMidiConfigurationManager *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x1800033f4`
- `0x18000b930`
- `0x180013010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CMidi2DiagnosticsMidiConfigurationManager *__fastcall CMidi2DiagnosticsMidiConfigurationManager::`scalar deleting destructor'(
        CMidi2DiagnosticsMidiConfigurationManager *this,
        char a2)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *((_DWORD *)this + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000b930  mov     [rsp+arg_0], rbx
0x18000b935  push    rdi
0x18000b936  sub     rsp, 20h
0x18000b93a  mov     edi, edx
0x18000b93c  mov     rbx, rcx
0x18000b93f  mov     rcx, [rcx+10h]
0x18000b943  test    rcx, rcx
0x18000b946  jz      short loc_18000B955
0x18000b948  mov     rax, [rcx]
0x18000b94b  mov     rax, [rax+10h]
0x18000b94f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b954  nop
0x18000b955  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18000b95c  test    dil, 1
0x18000b960  jz      short loc_18000B96F
0x18000b962  mov     edx, 18h
0x18000b967  mov     rcx, rbx; Block
0x18000b96a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b96f  mov     rax, rbx
0x18000b972  mov     rbx, [rsp+28h+arg_0]
0x18000b977  add     rsp, 20h
0x18000b97b  pop     rdi
0x18000b97c  retn
```
