# WPP_RECORDER_SF_

- ea: `0x140002964`
- end: `0x140002a1d`
- name: `WPP_RECORDER_SF_`
- size: `185`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x1400015cc`
- `0x1400031f0`
- `0x140003618`
- `0x140003e70`
- `0x140004070`
- `0x140004120`
- `0x140004f40`
- `0x140005040`
- `0x1400062d0`
- `0x140007010`
- `0x1400072c0`
- `0x14000785c`
- `0x140007cc0`
- `0x140008430`
- `0x140008720`
- `0x140008e00`
- `0x14000a450`
- `0x14000a7bc`

## callees

- `0x140002964`
- `0x14000d830`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002a05`
- `WppRecorder!WppAutoLogTrace` at `0x140002a05`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5)
{
  unsigned __int64 v7; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-38h]

  v7 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, a3 - 1) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v12, 0);
}

```

## disassembly

```asm
0x140002964  push    rbx
0x140002966  push    rbp
0x140002967  push    rsi
0x140002968  push    rdi
0x140002969  push    r14
0x14000296b  sub     rsp, 30h
0x14000296f  mov     ebp, r8d
0x140002972  mov     r14, rcx
0x140002975  mov     ebx, r8d
0x140002978  shr     rbx, 10h
0x14000297c  movzx   esi, r9w
0x140002980  lea     r11d, [rbp-1]
0x140002984  movzx   edi, dl
0x140002987  mov     r10d, r11d
0x14000298a  shr     r10, 5
0x14000298e  lea     rax, [rbx+rbx*4]
0x140002992  and     r10d, 7FFh
0x140002999  lea     rax, [r10+rax*4]
0x14000299d  mov     r10, cs:WPP_GLOBAL_Control
0x1400029a4  mov     eax, [r10+rax*4+2Ch]
0x1400029a9  bt      eax, r11d
0x1400029ad  jnb     short loc_1400029E7
0x1400029af  lea     rcx, [rbx+rbx*4]
0x1400029b3  add     rcx, rcx
0x1400029b6  cmp     [r10+rcx*8+29h], dil
0x1400029bb  jb      short loc_1400029E7
0x1400029bd  mov     rax, cs:pfnWppTraceMessage
0x1400029c4  mov     r9d, esi
0x1400029c7  mov     r8, [rsp+58h+arg_20]
0x1400029cf  mov     edx, 2Bh ; '+'
0x1400029d4  mov     rcx, [r10+rcx*8+18h]
0x1400029d9  mov     [rsp+58h+var_38], 0
0x1400029e2  call    _guard_dispatch_icall
0x1400029e7  mov     r9, [rsp+58h+arg_20]
0x1400029ef  mov     r8d, ebp
0x1400029f2  mov     [rsp+58h+var_30], 0
0x1400029fb  mov     edx, edi
0x1400029fd  mov     rcx, r14
0x140002a00  mov     word ptr [rsp+58h+var_38], si
0x140002a05  call    cs:__imp_WppAutoLogTrace
0x140002a0c  nop     dword ptr [rax+rax+00h]
0x140002a11  add     rsp, 30h
0x140002a15  pop     r14
0x140002a17  pop     rdi
0x140002a18  pop     rsi
0x140002a19  pop     rbp
0x140002a1a  pop     rbx
0x140002a1b  retn
```
