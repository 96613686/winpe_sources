# TRefPtr<StringBuffer>::Set(StringBuffer *)

- ea: `0x180009d8c`
- end: `0x180009dd8`
- name: `?Set@?$TRefPtr@VStringBuffer@@@@QEAAXPEAVStringBuffer@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180007a70`
- `0x180008bc4`
- `0x180008e40`
- `0x180009b10`
- `0x18000a750`

## callees

- `0x180009d8c`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall TRefPtr<StringBuffer>::Set(__int64 *a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 result; // rax

  v4 = *a1;
  if ( v4 )
  {
    result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 8), 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
      result = (**(__int64 (__fastcall ***)(__int64, __int64))v4)(v4, 1);
  }
  *a1 = a2;
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 8));
  return result;
}

```

## disassembly

```asm
0x180009d8c  mov     [rsp+arg_0], rbx
0x180009d91  push    rdi
0x180009d92  sub     rsp, 20h
0x180009d96  mov     rdi, rcx
0x180009d99  mov     rbx, rdx
0x180009d9c  mov     rcx, [rcx]
0x180009d9f  test    rcx, rcx
0x180009da2  jz      short loc_180009DC1
0x180009da4  or      eax, 0FFFFFFFFh
0x180009da7  lock xadd [rcx+8], eax
0x180009dac  cmp     eax, 1
0x180009daf  jnz     short loc_180009DC1
0x180009db1  mov     rax, [rcx]
0x180009db4  mov     edx, 1
0x180009db9  mov     rax, [rax]
0x180009dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dc1  mov     [rdi], rbx
0x180009dc4  test    rbx, rbx
0x180009dc7  jz      short loc_180009DCD
0x180009dc9  lock inc dword ptr [rbx+8]
0x180009dcd  mov     rbx, [rsp+28h+arg_0]
0x180009dd2  add     rsp, 20h
0x180009dd6  pop     rdi
0x180009dd7  retn
```
