# AiUpdatePerfTime

- ea: `0x140001590`
- end: `0x1400015ee`
- name: `AiUpdatePerfTime`
- size: `94`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400333b0`
- `0x140034550`
- `0x140036f60`
- `0x1400373b0`

## callees

- `0x140001590`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x1400015b3`
- `HAL!KeQueryPerformanceCounter` at `0x1400015b3`

## pseudocode

```c
LONGLONG __fastcall AiUpdatePerfTime(volatile signed __int64 *a1, __int64 a2, char a3)
{
  LONGLONG result; // rax
  __int128 v5; // rtt
  _LARGE_INTEGER PerformanceFrequency; // [rsp+48h] [rbp+20h] BYREF

  if ( !a3 )
    return 0;
  PerformanceFrequency.QuadPart = 0;
  v5 = 1000000 * (*(_QWORD *)&KeQueryPerformanceCounter(&PerformanceFrequency) - a2);
  result = v5 / PerformanceFrequency.QuadPart;
  if ( a1 )
  {
    _InterlockedAdd64(a1, result);
    _InterlockedIncrement64(a1 + 1);
  }
  return result;
}

```

## disassembly

```asm
0x140001590  mov     [rsp+arg_0], rbx
0x140001595  push    rdi
0x140001596  sub     rsp, 20h
0x14000159a  mov     rbx, rdx
0x14000159d  mov     rdi, rcx
0x1400015a0  test    r8b, r8b
0x1400015a3  jz      short loc_1400015EA
0x1400015a5  lea     rcx, [rsp+28h+PerformanceFrequency]; PerformanceFrequency
0x1400015aa  mov     qword ptr [rsp+28h+PerformanceFrequency], 0
0x1400015b3  call    cs:__imp_KeQueryPerformanceCounter
0x1400015ba  nop     dword ptr [rax+rax+00h]
0x1400015bf  sub     rax, rbx
0x1400015c2  imul    rax, 0F4240h
0x1400015c9  cqo
0x1400015cb  idiv    qword ptr [rsp+28h+PerformanceFrequency]
0x1400015d0  test    rdi, rdi
0x1400015d3  jz      short loc_1400015DE
0x1400015d5  lock add [rdi], rax
0x1400015d9  lock inc qword ptr [rdi+8]
0x1400015de  mov     rbx, [rsp+28h+arg_0]
0x1400015e3  add     rsp, 20h
0x1400015e7  pop     rdi
0x1400015e8  retn
0x1400015ea  xor     eax, eax
0x1400015ec  jmp     short loc_1400015DE
```
