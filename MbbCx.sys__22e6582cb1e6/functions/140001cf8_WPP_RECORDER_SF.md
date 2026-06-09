# WPP_RECORDER_SF_

- ea: `0x140001cf8`
- end: `0x140001db1`
- name: `WPP_RECORDER_SF_`
- size: `185`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, __int64)`
- caller_count: `100`
- callee_count: `2`
- tags: ``

## callers

- `0x140002024`
- `0x140002278`
- `0x140003534`
- `0x140003744`
- `0x140003ab0`
- `0x140004004`
- `0x14000431c`
- `0x14000459c`
- `0x140004844`
- `0x140006aa4`
- `0x140006b60`
- `0x140006d20`
- `0x140009720`
- `0x1400099cc`
- `0x14000a050`
- `0x14000a0a8`
- `0x14000a2d4`
- `0x14000a330`
- `0x14000a4f0`
- `0x14000a880`
- `0x14000a9d0`
- `0x14000ab20`
- `0x14000abe0`
- `0x14000aed0`
- `0x14000b670`
- `0x14000bb48`
- `0x14000c37c`
- `0x14000d3d0`
- `0x14000f478`
- `0x14000f6c0`
- `0x14000fca8`
- `0x140010540`
- `0x1400108b0`
- `0x140010d00`
- `0x140010e20`
- `0x140010e90`
- `0x140010f40`
- `0x140011000`
- `0x140011150`
- `0x1400111c0`
- `0x140011330`
- `0x1400114b0`
- `0x1400115c0`
- `0x1400117c0`
- `0x140011830`
- `0x140011910`
- `0x1400119c0`
- `0x140011a30`
- `0x140011b10`
- `0x140011c50`

## callees

- `0x140001cf8`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001d99`
- `WppRecorder!WppAutoLogTrace` at `0x140001d99`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5)
{
  unsigned __int64 v7; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-38h]
  __int64 v13; // [rsp+30h] [rbp-28h]
  __int64 v14; // [rsp+38h] [rbp-20h]
  __int64 v15; // [rsp+40h] [rbp-18h]
  __int64 v16; // [rsp+48h] [rbp-10h]

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
  return WppAutoLogTrace(a1, v9, a3, a5, v12, 0, v13, v14, v15, v16);
}

```

## disassembly

```asm
0x140001cf8  push    rbx
0x140001cfa  push    rbp
0x140001cfb  push    rsi
0x140001cfc  push    rdi
0x140001cfd  push    r14
0x140001cff  sub     rsp, 30h
0x140001d03  mov     ebp, r8d
0x140001d06  mov     r14, rcx
0x140001d09  mov     ebx, r8d
0x140001d0c  shr     rbx, 10h
0x140001d10  movzx   esi, r9w
0x140001d14  lea     r11d, [rbp-1]
0x140001d18  movzx   edi, dl
0x140001d1b  mov     r10d, r11d
0x140001d1e  shr     r10, 5
0x140001d22  lea     rax, [rbx+rbx*4]
0x140001d26  and     r10d, 7FFh
0x140001d2d  lea     rax, [r10+rax*4]
0x140001d31  mov     r10, cs:WPP_GLOBAL_Control
0x140001d38  mov     eax, [r10+rax*4+2Ch]
0x140001d3d  bt      eax, r11d
0x140001d41  jnb     short loc_140001D7B
0x140001d43  lea     rcx, [rbx+rbx*4]
0x140001d47  add     rcx, rcx
0x140001d4a  cmp     [r10+rcx*8+29h], dil
0x140001d4f  jb      short loc_140001D7B
0x140001d51  mov     rax, cs:pfnWppTraceMessage
0x140001d58  mov     r9d, esi
0x140001d5b  mov     r8, [rsp+58h+arg_20]
0x140001d63  mov     edx, 2Bh ; '+'
0x140001d68  mov     rcx, [r10+rcx*8+18h]
0x140001d6d  mov     [rsp+58h+var_38], 0
0x140001d76  call    _guard_dispatch_icall
0x140001d7b  mov     r9, [rsp+58h+arg_20]
0x140001d83  mov     r8d, ebp
0x140001d86  mov     [rsp+58h+var_30], 0
0x140001d8f  mov     edx, edi
0x140001d91  mov     rcx, r14
0x140001d94  mov     word ptr [rsp+58h+var_38], si
0x140001d99  call    cs:__imp_WppAutoLogTrace
0x140001da0  nop     dword ptr [rax+rax+00h]
0x140001da5  add     rsp, 30h
0x140001da9  pop     r14
0x140001dab  pop     rdi
0x140001dac  pop     rsi
0x140001dad  pop     rbp
0x140001dae  pop     rbx
0x140001daf  retn
```
