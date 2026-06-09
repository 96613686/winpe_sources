# std::shared_ptr<DiagHubCommon::FileLogWriter>::~shared_ptr<DiagHubCommon::FileLogWriter>(void)

- ea: `0x14000b6ec`
- end: `0x14000b73a`
- name: `??1?$shared_ptr@VFileLogWriter@DiagHubCommon@@@std@@QEAA@XZ`
- size: `78`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400153c5`
- `0x1400153d1`
- `0x1400153e9`
- `0x1400153f5`
- `0x1400154bb`
- `0x1400154c7`

## callees

- `0x14000b6ec`
- `0x140014c70`

## pseudocode

```c
__int64 __fastcall std::shared_ptr<DiagHubCommon::FileLogWriter>::~shared_ptr<DiagHubCommon::FileLogWriter>(__int64 a1)
{
  volatile signed __int32 *v1; // rbx
  __int64 result; // rax

  v1 = *(volatile signed __int32 **)(a1 + 8);
  if ( v1 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v1 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v1)(v1);
      result = (unsigned int)_InterlockedExchangeAdd(v1 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000b6ec  push    rbx
0x14000b6ee  sub     rsp, 20h
0x14000b6f2  mov     rbx, [rcx+8]
0x14000b6f6  test    rbx, rbx
0x14000b6f9  jz      short loc_14000B734
0x14000b6fb  or      eax, 0FFFFFFFFh
0x14000b6fe  lock xadd [rbx+8], eax
0x14000b703  cmp     eax, 1
0x14000b706  jnz     short loc_14000B734
0x14000b708  mov     rax, [rbx]
0x14000b70b  mov     rcx, rbx
0x14000b70e  mov     rax, [rax]
0x14000b711  call    cs:__guard_dispatch_icall_fptr
0x14000b717  or      eax, 0FFFFFFFFh
0x14000b71a  lock xadd [rbx+0Ch], eax
0x14000b71f  cmp     eax, 1
0x14000b722  jnz     short loc_14000B734
0x14000b724  mov     rax, [rbx]
0x14000b727  mov     rcx, rbx
0x14000b72a  mov     rax, [rax+8]
0x14000b72e  call    cs:__guard_dispatch_icall_fptr
0x14000b734  add     rsp, 20h
0x14000b738  pop     rbx
0x14000b739  retn
```
