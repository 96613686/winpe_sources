# CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState(void)

- ea: `0x180026070`
- end: `0x1800260ae`
- name: `??1CPrivilegeState@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAA@XZ`
- size: `62`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180027a90`
- `0x18002acf8`

## callees

- `0x180026070`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180026096`
- `ntdll!RtlAdjustPrivilege` at `0x180026096`

## pseudocode

```c
NTSTATUS __fastcall CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState(__int64 a1)
{
  unsigned __int8 *v2; // rdi
  NTSTATUS result; // eax

  if ( *(_BYTE *)(a1 + 4) )
  {
    v2 = (unsigned __int8 *)(a1 + 5);
    if ( !*(_BYTE *)(a1 + 5) )
    {
      result = RtlAdjustPrivilege(*(_DWORD *)a1, 0, 0, v2);
      *(_BYTE *)(a1 + 4) = 0;
      *v2 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180026070  mov     [rsp+arg_0], rbx
0x180026075  push    rdi
0x180026076  sub     rsp, 20h
0x18002607a  cmp     byte ptr [rcx+4], 0
0x18002607e  mov     rbx, rcx
0x180026081  jz      short loc_1800260A3
0x180026083  lea     rdi, [rcx+5]
0x180026087  cmp     byte ptr [rdi], 0
0x18002608a  jnz     short loc_1800260A3
0x18002608c  mov     ecx, [rcx]; Privilege
0x18002608e  mov     r9, rdi; OldValue
0x180026091  xor     r8d, r8d; ForThread
0x180026094  xor     edx, edx; NewValue
0x180026096  call    cs:__imp_RtlAdjustPrivilege
0x18002609c  mov     byte ptr [rbx+4], 0
0x1800260a0  mov     byte ptr [rdi], 0
0x1800260a3  mov     rbx, [rsp+28h+arg_0]
0x1800260a8  add     rsp, 20h
0x1800260ac  pop     rdi
0x1800260ad  retn
```
