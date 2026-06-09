# WindowsPerformanceRecorder::Impl::CAutoPrivilege::SetPrivilege(uchar)

- ea: `0x18005d6d8`
- end: `0x18005d70d`
- name: `?SetPrivilege@CAutoPrivilege@Impl@WindowsPerformanceRecorder@@QEAAXE@Z`
- size: `53`
- prototype: `void __fastcall(WindowsPerformanceRecorder::Impl::CAutoPrivilege *__hidden this, unsigned __int8)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180023b34`
- `0x18004a170`
- `0x18004b494`

## callees

- `0x18005d6d8`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18005d6eb`
- `ntdll!RtlAdjustPrivilege` at `0x18005d6eb`

## pseudocode

```c
void __fastcall WindowsPerformanceRecorder::Impl::CAutoPrivilege::SetPrivilege(
        WindowsPerformanceRecorder::Impl::CAutoPrivilege *this,
        BOOLEAN a2)
{
  NTSTATUS v3; // eax
  int v4; // eax

  v3 = RtlAdjustPrivilege(*((_DWORD *)this + 3), a2, 0, (PBOOLEAN)this + 16);
  if ( v3 < 0 || v3 == 262 )
    v4 = v3 | 0x10000000;
  else
    v4 = 0;
  *((_DWORD *)this + 2) = v4;
}

```

## disassembly

```asm
0x18005d6d8  push    rbx
0x18005d6da  sub     rsp, 20h
0x18005d6de  mov     rbx, rcx
0x18005d6e1  lea     r9, [rcx+10h]; OldValue
0x18005d6e5  mov     ecx, [rcx+0Ch]; Privilege
0x18005d6e8  xor     r8d, r8d; ForThread
0x18005d6eb  call    cs:__imp_RtlAdjustPrivilege
0x18005d6f1  test    eax, eax
0x18005d6f3  js      short loc_18005D700
0x18005d6f5  cmp     eax, 106h
0x18005d6fa  jz      short loc_18005D700
0x18005d6fc  xor     eax, eax
0x18005d6fe  jmp     short loc_18005D704
0x18005d700  bts     eax, 1Ch
0x18005d704  mov     [rbx+8], eax
0x18005d707  add     rsp, 20h
0x18005d70b  pop     rbx
0x18005d70c  retn
```
