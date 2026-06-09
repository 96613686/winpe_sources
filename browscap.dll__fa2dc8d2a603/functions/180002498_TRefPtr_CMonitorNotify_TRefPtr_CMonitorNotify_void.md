# TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)

- ea: `0x180002498`
- end: `0x1800024c6`
- name: `??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ`
- size: `46`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `30`
- callee_count: `2`
- tags: ``

## callers

- `0x1800024cc`
- `0x18000656c`
- `0x1800073d8`
- `0x18000742c`
- `0x180007454`
- `0x180007570`
- `0x1800076e8`
- `0x180007a70`
- `0x1800081b0`
- `0x18000888c`
- `0x180008940`
- `0x180008bc4`
- `0x180008db8`
- `0x180008fa8`
- `0x180009530`
- `0x180009f38`
- `0x180009f84`
- `0x18000a02c`
- `0x18000a0ec`
- `0x18000a1ac`
- `0x18000a2e4`
- `0x18000a750`
- `0x18000a920`
- `0x18000ad2c`
- `0x18000ae60`
- `0x18000c088`
- `0x18000c0c2`
- `0x18000c1a0`
- `0x18000c1c0`
- `0x18000c230`

## callees

- `0x180002498`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
  {
    result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 8), 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
      return (**(__int64 (__fastcall ***)(__int64, __int64))v1)(v1, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180002498  sub     rsp, 28h
0x18000249c  mov     rcx, [rcx]
0x18000249f  test    rcx, rcx
0x1800024a2  jz      short loc_1800024C1
0x1800024a4  or      eax, 0FFFFFFFFh
0x1800024a7  lock xadd [rcx+8], eax
0x1800024ac  cmp     eax, 1
0x1800024af  jnz     short loc_1800024C1
0x1800024b1  mov     rax, [rcx]
0x1800024b4  mov     edx, 1
0x1800024b9  mov     rax, [rax]
0x1800024bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024c1  add     rsp, 28h
0x1800024c5  retn
```
