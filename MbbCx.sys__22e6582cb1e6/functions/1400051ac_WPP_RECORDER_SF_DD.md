# WPP_RECORDER_SF_DD

- ea: `0x1400051ac`
- end: `0x1400052b6`
- name: `WPP_RECORDER_SF_DD`
- size: `266`
- prototype: ``
- caller_count: `156`
- callee_count: `2`
- tags: ``

## callers

- `0x1400026f0`
- `0x140002840`
- `0x140002960`
- `0x140002a40`
- `0x140002bb0`
- `0x140002c90`
- `0x140002d70`
- `0x140002edc`
- `0x140003310`
- `0x140008ff0`
- `0x14000a910`
- `0x14000aed0`
- `0x14000efa4`
- `0x14000f6c0`
- `0x14000fa30`
- `0x14000fe90`
- `0x14000ff80`
- `0x1400101d0`
- `0x140010600`
- `0x1400108b0`
- `0x140011070`
- `0x140011b10`
- `0x140011d10`
- `0x1400124a0`
- `0x140012c90`
- `0x140013220`
- `0x140013590`
- `0x140013c08`
- `0x1400140c0`
- `0x140014540`
- `0x140014730`
- `0x140014b10`
- `0x140015290`
- `0x1400153a0`
- `0x140016200`
- `0x140016ab0`
- `0x140016c90`
- `0x140016fd0`
- `0x140017110`
- `0x140017230`
- `0x1400178e0`
- `0x1400196ac`
- `0x14001a2a4`
- `0x14001a9ec`
- `0x14001b1c0`
- `0x14001b348`
- `0x14001b818`
- `0x14001c400`
- `0x14001c834`
- `0x14001cd78`

## callees

- `0x1400051ac`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000529c`
- `WppRecorder!WppAutoLogTrace` at `0x14000529c`

## pseudocode

```c
__int64 WPP_RECORDER_SF_DD(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-68h]
  __int64 v13; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  va_list va1; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v13 = va_arg(va1, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, a3 - 1) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      4,
      va1,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v12, (__int64 *)va, 4, va1, 4, 0);
}

```

## disassembly

```asm
0x1400051ac  push    rbx
0x1400051ae  push    rbp
0x1400051af  push    rsi
0x1400051b0  push    rdi
0x1400051b1  push    r14
0x1400051b3  push    r15
0x1400051b5  sub     rsp, 58h
0x1400051b9  mov     ebp, r8d
0x1400051bc  mov     r14, rcx
0x1400051bf  mov     ebx, r8d
0x1400051c2  mov     r15d, 4
0x1400051c8  shr     rbx, 10h
0x1400051cc  movzx   esi, r9w
0x1400051d0  lea     r11d, [rbp-1]
0x1400051d4  movzx   edi, dl
0x1400051d7  mov     r10d, r11d
0x1400051da  shr     r10, 5
0x1400051de  lea     rax, [rbx+rbx*4]
0x1400051e2  and     r10d, 7FFh
0x1400051e9  lea     rax, [r10+rax*4]
0x1400051ed  mov     r10, cs:WPP_GLOBAL_Control
0x1400051f4  mov     eax, [r10+rax*4+2Ch]
0x1400051f9  bt      eax, r11d
0x1400051fd  jnb     short loc_14000525A
0x1400051ff  lea     rcx, [rbx+rbx*4]
0x140005203  add     rcx, rcx
0x140005206  cmp     [r10+rcx*8+29h], dil
0x14000520b  jb      short loc_14000525A
0x14000520d  mov     rax, cs:pfnWppTraceMessage
0x140005214  lea     rdx, [rsp+88h+arg_30]
0x14000521c  mov     r8, [rsp+88h+arg_20]
0x140005224  mov     r9d, esi
0x140005227  mov     rcx, [r10+rcx*8+18h]
0x14000522c  mov     [rsp+88h+var_48], 0
0x140005235  mov     [rsp+88h+var_50], r15
0x14000523a  mov     [rsp+88h+var_58], rdx
0x14000523f  lea     rdx, [rsp+88h+arg_28]
0x140005247  mov     [rsp+88h+var_60], r15
0x14000524c  mov     [rsp+88h+var_68], rdx
0x140005251  lea     edx, [r15+27h]
0x140005255  call    _guard_dispatch_icall
0x14000525a  mov     r9, [rsp+88h+arg_20]
0x140005262  lea     rax, [rsp+88h+arg_30]
0x14000526a  mov     [rsp+88h+var_40], 0
0x140005273  mov     r8d, ebp
0x140005276  mov     [rsp+88h+var_48], r15
0x14000527b  mov     edx, edi
0x14000527d  mov     [rsp+88h+var_50], rax
0x140005282  mov     rcx, r14
0x140005285  lea     rax, [rsp+88h+arg_28]
0x14000528d  mov     [rsp+88h+var_58], r15
0x140005292  mov     [rsp+88h+var_60], rax
0x140005297  mov     word ptr [rsp+88h+var_68], si
0x14000529c  call    cs:__imp_WppAutoLogTrace
0x1400052a3  nop     dword ptr [rax+rax+00h]
0x1400052a8  add     rsp, 58h
0x1400052ac  pop     r15
0x1400052ae  pop     r14
0x1400052b0  pop     rdi
0x1400052b1  pop     rsi
0x1400052b2  pop     rbp
0x1400052b3  pop     rbx
0x1400052b4  retn
```
