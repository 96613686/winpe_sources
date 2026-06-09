# WPP_RECORDER_SF_DD

- ea: `0x14000b4d0`
- end: `0x14000b594`
- name: `WPP_RECORDER_SF_DD`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a450`
- `0x14000a7bc`

## callees

- `0x14000b4d0`
- `0x14000d830`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000b57e`
- `WppRecorder!WppAutoLogTrace` at `0x14000b57e`

## pseudocode

```c
__int64 WPP_RECORDER_SF_DD(__int64 a1, unsigned __int8 a2, _DWORD a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-58h]
  __int64 v10; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  va_list va1; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v10 = va_arg(va1, _QWORD);
  v7 = a2;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= a2 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids,
      a4,
      (__int64 *)va,
      4,
      va1,
      4,
      0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(a1, v7, 1, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, v9, (__int64 *)va);
}

```

## disassembly

```asm
0x14000b4d0  mov     r11, rsp
0x14000b4d3  push    rbx
0x14000b4d4  push    rbp
0x14000b4d5  push    rsi
0x14000b4d6  push    rdi
0x14000b4d7  sub     rsp, 58h
0x14000b4db  mov     rsi, rcx
0x14000b4de  movzx   edi, r9w
0x14000b4e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b4e9  mov     ebp, 4
0x14000b4ee  movzx   ebx, dl
0x14000b4f1  mov     eax, [rcx+2Ch]
0x14000b4f4  test    al, 1
0x14000b4f6  jz      short loc_14000B53A
0x14000b4f8  cmp     [rcx+29h], bl
0x14000b4fb  jb      short loc_14000B53A
0x14000b4fd  mov     rax, cs:pfnWppTraceMessage
0x14000b504  lea     rdx, [r11+38h]
0x14000b508  mov     rcx, [rcx+18h]
0x14000b50c  lea     r8, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x14000b513  mov     qword ptr [r11-38h], 0
0x14000b51b  mov     r9d, edi
0x14000b51e  mov     [r11-40h], rbp
0x14000b522  mov     [r11-48h], rdx
0x14000b526  lea     rdx, [r11+30h]
0x14000b52a  mov     [r11-50h], rbp
0x14000b52e  mov     [r11-58h], rdx
0x14000b532  lea     edx, [rbp+27h]
0x14000b535  call    _guard_dispatch_icall
0x14000b53a  mov     [rsp+78h+var_30], 0
0x14000b543  lea     rax, [rsp+78h+arg_30]
0x14000b54b  mov     [rsp+78h+var_38], rbp
0x14000b550  lea     r9, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x14000b557  mov     [rsp+78h+var_40], rax
0x14000b55c  mov     r8d, 1
0x14000b562  lea     rax, [rsp+78h+arg_28]
0x14000b56a  mov     [rsp+78h+var_48], rbp
0x14000b56f  mov     [rsp+78h+var_50], rax
0x14000b574  mov     edx, ebx
0x14000b576  mov     rcx, rsi
0x14000b579  mov     [rsp+78h+var_58], di
0x14000b57e  call    cs:__imp_WppAutoLogTrace
0x14000b585  nop     dword ptr [rax+rax+00h]
0x14000b58a  add     rsp, 58h
0x14000b58e  pop     rdi
0x14000b58f  pop     rsi
0x14000b590  pop     rbp
0x14000b591  pop     rbx
0x14000b592  retn
```
