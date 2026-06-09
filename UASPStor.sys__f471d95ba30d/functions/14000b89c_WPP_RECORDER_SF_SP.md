# WPP_RECORDER_SF_SP

- ea: `0x14000b89c`
- end: `0x14000b977`
- name: `WPP_RECORDER_SF_SP`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002320`

## callees

- `0x14000b89c`
- `0x14000d830`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000b959`
- `WppRecorder!WppAutoLogTrace` at `0x14000b959`

## string_xrefs

- `0x14000b8bb`: `PnPRemove`

## pseudocode

```c
__int64 WPP_RECORDER_SF_SP(__int64 a1, _DWORD a2, _DWORD a3, unsigned __int16 a4, __int64 a5, __int64 a6, ...)
{
  int v9; // [rsp+20h] [rbp-38h]
  va_list va; // [rsp+90h] [rbp+38h] BYREF

  va_start(va, a6);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64, _QWORD, const wchar_t *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      a5,
      a4,
      L"PnPRemove",
      20,
      va,
      8,
      0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(a1, 4, 3, a5, v9, L"PnPRemove", 20, va, 8, 0);
}

```

## disassembly

```asm
0x14000b89c  mov     r11, rsp
0x14000b89f  mov     [r11+8], rbx
0x14000b8a3  mov     [r11+10h], rdi
0x14000b8a7  push    r14
0x14000b8a9  sub     rsp, 50h
0x14000b8ad  mov     rdi, rcx
0x14000b8b0  movzx   ebx, r9w
0x14000b8b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b8bb  lea     r14, aPnpremove; "PnPRemove"
0x14000b8c2  mov     eax, [rcx+2Ch]
0x14000b8c5  test    al, 4
0x14000b8c7  jz      short loc_14000B913
0x14000b8c9  cmp     byte ptr [rcx+29h], 4
0x14000b8cd  jb      short loc_14000B913
0x14000b8cf  mov     rax, cs:pfnWppTraceMessage
0x14000b8d6  lea     rdx, [r11+38h]
0x14000b8da  mov     r8, [rsp+58h+arg_20]
0x14000b8e2  mov     r9d, ebx
0x14000b8e5  mov     rcx, [rcx+18h]
0x14000b8e9  mov     qword ptr [r11-18h], 0
0x14000b8f1  mov     qword ptr [r11-20h], 8
0x14000b8f9  mov     [r11-28h], rdx
0x14000b8fd  mov     edx, 2Bh ; '+'
0x14000b902  mov     qword ptr [r11-30h], 14h
0x14000b90a  mov     [r11-38h], r14
0x14000b90e  call    _guard_dispatch_icall
0x14000b913  mov     r9, [rsp+58h+arg_20]
0x14000b91b  lea     rax, [rsp+58h+arg_30]
0x14000b923  mov     [rsp+58h+var_10], 0
0x14000b92c  mov     edx, 4
0x14000b931  mov     [rsp+58h+var_18], 8
0x14000b93a  mov     rcx, rdi
0x14000b93d  mov     [rsp+58h+var_20], rax
0x14000b942  mov     [rsp+58h+var_28], 14h
0x14000b94b  lea     r8d, [rdx-1]
0x14000b94f  mov     [rsp+58h+var_30], r14
0x14000b954  mov     [rsp+58h+var_38], bx
0x14000b959  call    cs:__imp_WppAutoLogTrace
0x14000b960  nop     dword ptr [rax+rax+00h]
0x14000b965  mov     rbx, [rsp+58h+arg_0]
0x14000b96a  mov     rdi, [rsp+58h+arg_8]
0x14000b96f  add     rsp, 50h
0x14000b973  pop     r14
0x14000b975  retn
```
