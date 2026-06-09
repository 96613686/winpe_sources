# mkl_serv_lock

- ea: `0x180054080`
- end: `0x1800540c0`
- name: `mkl_serv_lock`
- size: `64`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bb30`
- `0x18000d570`
- `0x18003baf0`
- `0x18003bee0`
- `0x18003c000`
- `0x18003c0c0`
- `0x18003cec0`
- `0x18003d720`
- `0x18003df30`
- `0x18003eb20`
- `0x18003fa70`
- `0x180040370`
- `0x180040c20`
- `0x180053170`
- `0x180061260`
- `0x1800777c0`
- `0x1800779d0`
- `0x1800b4000`
- `0x1800b41b0`

## callees

- `0x180054080`
- `0x1800540c0`

## import_xrefs

- `KERNEL32!SwitchToThread` at `0x18005409a`
- `KERNEL32!SwitchToThread` at `0x18005409a`

## pseudocode

```c
__int64 __fastcall mkl_serv_lock(__int64 a1)
{
  int v2; // ebx
  __int64 result; // rax

  v2 = 0;
  result = ((__int64 (*)(void))mkl_serv_trylock)();
  if ( !(_DWORD)result )
  {
LABEL_2:
    ++v2;
    _mm_pause();
    while ( 1 )
    {
      result = mkl_serv_trylock(a1);
      if ( (_DWORD)result )
        break;
      if ( v2 < 5000 )
        goto LABEL_2;
      SwitchToThread();
    }
  }
  return result;
}

```

## disassembly

```asm
0x180054080  push    rbx
0x180054081  push    rsi
0x180054082  sub     rsp, 28h
0x180054086  mov     rsi, rcx
0x180054089  xor     ebx, ebx
0x18005408b  call    mkl_serv_trylock
0x180054090  test    eax, eax
0x180054092  jnz     short loc_1800540B6
0x180054094  inc     ebx
0x180054096  pause
0x180054098  jmp     short loc_1800540A0
0x18005409a  call    cs:__imp_SwitchToThread
0x1800540a0  mov     rcx, rsi
0x1800540a3  call    mkl_serv_trylock
0x1800540a8  test    eax, eax
0x1800540aa  jnz     short loc_1800540B6
0x1800540ac  cmp     ebx, 1388h
0x1800540b2  jl      short loc_180054094
0x1800540b4  jmp     short loc_18005409A
0x1800540b6  add     rsp, 28h
0x1800540ba  pop     rsi
0x1800540bb  pop     rbx
0x1800540bc  retn
```
