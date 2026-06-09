# WPP_RECORDER_SF_DDL

- ea: `0x140017fb4`
- end: `0x140018099`
- name: `WPP_RECORDER_SF_DDL`
- size: `229`
- prototype: `__int64(_DWORD, _DWORD, _DWORD, _DWORD, __int64, char, char, ...)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fa30`
- `0x140012a2c`
- `0x140012c90`
- `0x140026698`
- `0x140026e44`
- `0x1400287b0`
- `0x140028cb8`
- `0x1400291c0`
- `0x1400296d0`
- `0x140031e20`
- `0x140033970`
- `0x140035080`
- `0x140035530`

## callees

- `0x140017fb4`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140018083`
- `WppRecorder!WppAutoLogTrace` at `0x140018083`

## pseudocode

```c
__int64 WPP_RECORDER_SF_DDL(__int64 a1, unsigned __int8 a2, _DWORD a3, unsigned __int16 a4, __int64 a5, char a6, ...)
{
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-68h]
  __int64 v11; // [rsp+C0h] [rbp+38h] BYREF
  va_list va; // [rsp+C0h] [rbp+38h]
  va_list va1; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va1, a6);
  va_start(va, a6);
  v11 = va_arg(va1, _QWORD);
  v8 = a2;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= a2 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64, _QWORD, char *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
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
  LOWORD(v10) = a4;
  return WppAutoLogTrace(a1, v8, 3, a5, v10, &a6, 4, (__int64 *)va, 4, va1);
}

```

## disassembly

```asm
0x140017fb4  mov     r11, rsp
0x140017fb7  push    rbx
0x140017fb8  push    rbp
0x140017fb9  push    rsi
0x140017fba  push    rdi
0x140017fbb  sub     rsp, 68h
0x140017fbf  mov     rsi, rcx
0x140017fc2  movzx   edi, r9w
0x140017fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x140017fcd  mov     ebp, 4
0x140017fd2  movzx   ebx, dl
0x140017fd5  mov     eax, [rcx+2Ch]
0x140017fd8  test    bpl, al
0x140017fdb  jz      short loc_14001802C
0x140017fdd  cmp     [rcx+29h], bl
0x140017fe0  jb      short loc_14001802C
0x140017fe2  mov     rax, cs:pfnWppTraceMessage
0x140017fe9  lea     rdx, [r11+40h]
0x140017fed  mov     r8, [rsp+88h+arg_20]
0x140017ff5  mov     r9d, edi
0x140017ff8  mov     rcx, [rcx+18h]
0x140017ffc  mov     qword ptr [r11-38h], 0
0x140018004  mov     [r11-40h], rbp
0x140018008  mov     [r11-48h], rdx
0x14001800c  lea     rdx, [r11+38h]
0x140018010  mov     [r11-50h], rbp
0x140018014  mov     [r11-58h], rdx
0x140018018  lea     rdx, [r11+30h]
0x14001801c  mov     [r11-60h], rbp
0x140018020  mov     [r11-68h], rdx
0x140018024  lea     edx, [rbp+27h]
0x140018027  call    _guard_dispatch_icall
0x14001802c  mov     r9, [rsp+88h+arg_20]
0x140018034  lea     rax, [rsp+88h+arg_38]
0x14001803c  mov     [rsp+88h+var_30], 0
0x140018045  mov     r8d, 3
0x14001804b  mov     [rsp+88h+var_38], rbp
0x140018050  mov     edx, ebx
0x140018052  mov     [rsp+88h+var_40], rax
0x140018057  mov     rcx, rsi
0x14001805a  mov     [rsp+88h+var_48], rbp
0x14001805f  lea     rax, [rsp+88h+arg_30]
0x140018067  mov     [rsp+88h+var_50], rax
0x14001806c  lea     rax, [rsp+88h+arg_28]
0x140018074  mov     [rsp+88h+var_58], rbp
0x140018079  mov     [rsp+88h+var_60], rax
0x14001807e  mov     [rsp+88h+var_68], di
0x140018083  call    cs:__imp_WppAutoLogTrace
0x14001808a  nop     dword ptr [rax+rax+00h]
0x14001808f  add     rsp, 68h
0x140018093  pop     rdi
0x140018094  pop     rsi
0x140018095  pop     rbp
0x140018096  pop     rbx
0x140018097  retn
```
