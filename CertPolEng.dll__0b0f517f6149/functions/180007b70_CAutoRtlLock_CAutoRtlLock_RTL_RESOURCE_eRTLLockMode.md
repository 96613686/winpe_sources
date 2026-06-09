# CAutoRtlLock::CAutoRtlLock(_RTL_RESOURCE *,eRTLLockMode)

- ea: `0x180007b70`
- end: `0x180007bb5`
- name: `??0CAutoRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eRTLLockMode@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(__int64, struct _RTL_RESOURCE *, int)`
- caller_count: `11`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002560`
- `0x180003fb0`
- `0x1800066f0`
- `0x18000bee0`
- `0x18000d51c`
- `0x180014750`
- `0x180014c2c`
- `0x1800157d4`
- `0x180015c94`
- `0x18001640c`
- `0x1800167c8`

## callees

- `0x180007b70`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180007b8d`
- `ntdll!RtlAcquireResourceShared` at `0x180007b8d`
- `ntdll!RtlAcquireResourceExclusive` at `0x180007bad`
- `ntdll!RtlAcquireResourceExclusive` at `0x180007bad`

## pseudocode

```c
__int64 __fastcall CAutoRtlLock::CAutoRtlLock(__int64 a1, struct _RTL_RESOURCE *a2, int a3)
{
  *(_QWORD *)a1 = a2;
  *(_BYTE *)(a1 + 8) = 0;
  if ( a3 )
  {
    if ( a3 != 1 )
      return a1;
    RtlAcquireResourceExclusive(a2, 1u);
  }
  else
  {
    RtlAcquireResourceShared(a2, 1u);
  }
  *(_BYTE *)(a1 + 8) = 1;
  return a1;
}

```

## disassembly

```asm
0x180007b70  push    rbx
0x180007b72  sub     rsp, 20h
0x180007b76  mov     [rcx], rdx
0x180007b79  mov     rax, rdx
0x180007b7c  mov     byte ptr [rcx+8], 0
0x180007b80  mov     rbx, rcx
0x180007b83  test    r8d, r8d
0x180007b86  jnz     short loc_180007BA0
0x180007b88  mov     dl, 1; Wait
0x180007b8a  mov     rcx, rax; Resource
0x180007b8d  call    cs:__imp_RtlAcquireResourceShared
0x180007b93  mov     byte ptr [rbx+8], 1
0x180007b97  mov     rax, rbx
0x180007b9a  add     rsp, 20h
0x180007b9e  pop     rbx
0x180007b9f  retn
0x180007ba0  cmp     r8d, 1
0x180007ba4  jnz     short loc_180007B97
0x180007ba6  movzx   edx, r8b; Wait
0x180007baa  mov     rcx, rax; Resource
0x180007bad  call    cs:__imp_RtlAcquireResourceExclusive
0x180007bb3  jmp     short loc_180007B93
```
