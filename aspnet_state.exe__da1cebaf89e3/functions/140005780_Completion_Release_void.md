# Completion::Release(void)

- ea: `0x140005780`
- end: `0x1400057af`
- name: `?Release@Completion@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(Completion *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140005780`
- `0x140006590`

## pseudocode

```c
__int64 __fastcall Completion::Release(Completion *this)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)this + 12);
  if ( !(_DWORD)result )
  {
    if ( this )
      (*(void (__fastcall **)(Completion *, __int64))(*(_QWORD *)this + 32LL))(this, 1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140005780  sub     rsp, 28h
0x140005784  or      eax, 0FFFFFFFFh
0x140005787  lock xadd [rcx+30h], eax
0x14000578c  sub     eax, 1
0x14000578f  jnz     short loc_1400057AA
0x140005791  test    rcx, rcx
0x140005794  jz      short loc_1400057A8
0x140005796  mov     rax, [rcx]
0x140005799  mov     edx, 1
0x14000579e  mov     rax, [rax+20h]
0x1400057a2  call    cs:__guard_dispatch_icall_fptr
0x1400057a8  xor     eax, eax
0x1400057aa  add     rsp, 28h
0x1400057ae  retn
```
