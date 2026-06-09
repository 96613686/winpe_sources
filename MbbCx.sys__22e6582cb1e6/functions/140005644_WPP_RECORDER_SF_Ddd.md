# WPP_RECORDER_SF_Ddd

- ea: `0x140005644`
- end: `0x140005772`
- name: `WPP_RECORDER_SF_Ddd`
- size: `302`
- prototype: `__int64(_DWORD, _DWORD, _DWORD, _DWORD, __int64, char, char, ...)`
- caller_count: `86`
- callee_count: `2`
- tags: ``

## callers

- `0x140003310`
- `0x14000fa30`
- `0x14000ff80`
- `0x1400101d0`
- `0x140012c90`
- `0x140013590`
- `0x1400138d0`
- `0x1400140c0`
- `0x140014730`
- `0x140014ea0`
- `0x140015710`
- `0x140016c90`
- `0x1400193bc`
- `0x14001e7b8`
- `0x140026698`
- `0x140026e44`
- `0x1400275f0`
- `0x140027a54`
- `0x140027eb8`
- `0x1400280f8`
- `0x140028340`
- `0x1400287b0`
- `0x140028cb8`
- `0x1400291c0`
- `0x1400296d0`
- `0x1400298a0`
- `0x140029b20`
- `0x140029d80`
- `0x140029fe0`
- `0x14002a240`
- `0x14002ae5c`
- `0x14002b930`
- `0x14002be90`
- `0x14002c394`
- `0x14002c9e0`
- `0x14002d18c`
- `0x14002d460`
- `0x14002e2b0`
- `0x14002e780`
- `0x14002f8e0`
- `0x14002fb40`
- `0x140030100`
- `0x140030590`
- `0x140030830`
- `0x140030bc0`
- `0x140030f80`
- `0x140031550`
- `0x140031a40`
- `0x140031e20`
- `0x140032280`

## callees

- `0x140005644`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140005758`
- `WppRecorder!WppAutoLogTrace` at `0x140005758`

## pseudocode

```c
__int64 WPP_RECORDER_SF_Ddd(
        __int64 a1,
        unsigned __int8 a2,
        unsigned int a3,
        unsigned __int16 a4,
        __int64 a5,
        char a6,
        ...)
{
  unsigned __int64 v8; // rbx
  unsigned int v10; // edi
  int v11; // eax
  int v13; // [rsp+20h] [rbp-78h]
  __int64 v14; // [rsp+D0h] [rbp+38h] BYREF
  va_list va; // [rsp+D0h] [rbp+38h]
  va_list va1; // [rsp+D8h] [rbp+40h] BYREF

  va_start(va1, a6);
  va_start(va, a6);
  v14 = va_arg(va1, _QWORD);
  v8 = (unsigned __int64)a3 >> 16;
  v10 = a2;
  v11 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v8 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v11, a3 - 1) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v8 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, char *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v8),
      43,
      a5,
      a4,
      &a6,
      4,
      (__int64 *)va,
      4,
      va1,
      4,
      0);
  LOWORD(v13) = a4;
  return WppAutoLogTrace(a1, v10, a3, a5, v13, &a6, 4, (__int64 *)va, 4, va1);
}

```

## disassembly

```asm
0x140005644  push    rbx
0x140005646  push    rbp
0x140005647  push    rsi
0x140005648  push    rdi
0x140005649  push    r14
0x14000564b  push    r15
0x14000564d  sub     rsp, 68h
0x140005651  mov     ebp, r8d
0x140005654  mov     r14, rcx
0x140005657  mov     ebx, r8d
0x14000565a  mov     r15d, 4
0x140005660  shr     rbx, 10h
0x140005664  movzx   esi, r9w
0x140005668  lea     r11d, [rbp-1]
0x14000566c  movzx   edi, dl
0x14000566f  mov     r10d, r11d
0x140005672  shr     r10, 5
0x140005676  lea     rax, [rbx+rbx*4]
0x14000567a  and     r10d, 7FFh
0x140005681  lea     rax, [r10+rax*4]
0x140005685  mov     r10, cs:WPP_GLOBAL_Control
0x14000568c  mov     eax, [r10+rax*4+2Ch]
0x140005691  bt      eax, r11d
0x140005695  jnb     short loc_140005704
0x140005697  lea     rcx, [rbx+rbx*4]
0x14000569b  add     rcx, rcx
0x14000569e  cmp     [r10+rcx*8+29h], dil
0x1400056a3  jb      short loc_140005704
0x1400056a5  mov     rax, cs:pfnWppTraceMessage
0x1400056ac  lea     rdx, [rsp+98h+arg_38]
0x1400056b4  mov     r8, [rsp+98h+arg_20]
0x1400056bc  mov     r9d, esi
0x1400056bf  mov     rcx, [r10+rcx*8+18h]
0x1400056c4  mov     [rsp+98h+var_48], 0
0x1400056cd  mov     [rsp+98h+var_50], r15
0x1400056d2  mov     [rsp+98h+var_58], rdx
0x1400056d7  lea     rdx, [rsp+98h+arg_30]
0x1400056df  mov     [rsp+98h+var_60], r15
0x1400056e4  mov     [rsp+98h+var_68], rdx
0x1400056e9  lea     rdx, [rsp+98h+arg_28]
0x1400056f1  mov     [rsp+98h+var_70], r15
0x1400056f6  mov     [rsp+98h+var_78], rdx
0x1400056fb  lea     edx, [r15+27h]
0x1400056ff  call    _guard_dispatch_icall
0x140005704  mov     r9, [rsp+98h+arg_20]
0x14000570c  lea     rax, [rsp+98h+arg_38]
0x140005714  mov     [rsp+98h+var_40], 0
0x14000571d  mov     r8d, ebp
0x140005720  mov     [rsp+98h+var_48], r15
0x140005725  mov     edx, edi
0x140005727  mov     [rsp+98h+var_50], rax
0x14000572c  mov     rcx, r14
0x14000572f  mov     [rsp+98h+var_58], r15
0x140005734  lea     rax, [rsp+98h+arg_30]
0x14000573c  mov     [rsp+98h+var_60], rax
0x140005741  lea     rax, [rsp+98h+arg_28]
0x140005749  mov     [rsp+98h+var_68], r15
0x14000574e  mov     [rsp+98h+var_70], rax
0x140005753  mov     word ptr [rsp+98h+var_78], si
0x140005758  call    cs:__imp_WppAutoLogTrace
0x14000575f  nop     dword ptr [rax+rax+00h]
0x140005764  add     rsp, 68h
0x140005768  pop     r15
0x14000576a  pop     r14
0x14000576c  pop     rdi
0x14000576d  pop     rsi
0x14000576e  pop     rbp
0x14000576f  pop     rbx
0x140005770  retn
```
