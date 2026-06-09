# WPP_RECORDER_SF_PDDDDDDDDDDD

- ea: `0x140002dd8`
- end: `0x140003016`
- name: `WPP_RECORDER_SF_PDDDDDDDDDDD`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002320`

## callees

- `0x140002dd8`
- `0x14000d830`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002ffc`
- `WppRecorder!WppAutoLogTrace` at `0x140002ffc`

## pseudocode

```c
__int64 WPP_RECORDER_SF_PDDDDDDDDDDD(__int64 a1, _DWORD a2, _DWORD a3, _DWORD a4, __int64 a5, ...)
{
  int v7; // [rsp+28h] [rbp-D1h]
  __int64 v8; // [rsp+150h] [rbp+57h] BYREF
  va_list va; // [rsp+150h] [rbp+57h]
  __int64 v10; // [rsp+158h] [rbp+5Fh] BYREF
  va_list va1; // [rsp+158h] [rbp+5Fh]
  __int64 v12; // [rsp+160h] [rbp+67h] BYREF
  va_list va2; // [rsp+160h] [rbp+67h]
  __int64 v14; // [rsp+168h] [rbp+6Fh] BYREF
  va_list va3; // [rsp+168h] [rbp+6Fh]
  __int64 v16; // [rsp+170h] [rbp+77h] BYREF
  va_list va4; // [rsp+170h] [rbp+77h]
  __int64 v18; // [rsp+178h] [rbp+7Fh] BYREF
  va_list va5; // [rsp+178h] [rbp+7Fh]
  __int64 v20; // [rsp+180h] [rbp+87h] BYREF
  va_list va6; // [rsp+180h] [rbp+87h]
  __int64 v22; // [rsp+188h] [rbp+8Fh] BYREF
  va_list va7; // [rsp+188h] [rbp+8Fh]
  __int64 v24; // [rsp+190h] [rbp+97h] BYREF
  va_list va8; // [rsp+190h] [rbp+97h]
  __int64 v26; // [rsp+198h] [rbp+9Fh] BYREF
  va_list va9; // [rsp+198h] [rbp+9Fh]
  __int64 v28; // [rsp+1A0h] [rbp+A7h] BYREF
  va_list va10; // [rsp+1A0h] [rbp+A7h]
  va_list va11; // [rsp+1A8h] [rbp+AFh] BYREF

  va_start(va11, a5);
  va_start(va10, a5);
  va_start(va9, a5);
  va_start(va8, a5);
  va_start(va7, a5);
  va_start(va6, a5);
  va_start(va5, a5);
  va_start(va4, a5);
  va_start(va3, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v8 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v10 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v12 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v14 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v16 = va_arg(va5, _QWORD);
  va_copy(va6, va5);
  v18 = va_arg(va6, _QWORD);
  va_copy(va7, va6);
  v20 = va_arg(va7, _QWORD);
  va_copy(va8, va7);
  v22 = va_arg(va8, _QWORD);
  va_copy(va9, va8);
  v24 = va_arg(va9, _QWORD);
  va_copy(va10, va9);
  v26 = va_arg(va10, _QWORD);
  va_copy(va11, va10);
  v28 = va_arg(va11, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_dd684dc3739b34a5bf4807a1c7087b9b_Traceguids,
      10,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      4,
      (__int64 *)va2,
      4,
      (__int64 *)va3,
      4,
      (__int64 *)va4,
      4,
      (__int64 *)va5,
      4,
      (__int64 *)va6,
      4,
      (__int64 *)va7,
      4,
      (__int64 *)va8,
      4,
      (__int64 *)va9,
      4,
      (__int64 *)va10,
      4,
      va11,
      4,
      0);
  LOWORD(v7) = 10;
  return WppAutoLogTrace(a1, 4, 5, WPP_dd684dc3739b34a5bf4807a1c7087b9b_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140002dd8  mov     r11, rsp
0x140002ddb  push    rbp
0x140002ddc  push    rbx
0x140002ddd  push    rdi
0x140002dde  push    r14
0x140002de0  lea     rbp, [r11-27h]
0x140002de4  sub     rsp, 0F8h
0x140002deb  mov     rbx, rcx
0x140002dee  mov     edi, 4
0x140002df3  mov     rcx, cs:WPP_GLOBAL_Control
0x140002dfa  lea     r14d, [rdi+6]
0x140002dfe  mov     eax, [rcx+2Ch]
0x140002e01  test    al, 10h
0x140002e03  jz      loc_140002EF3
0x140002e09  cmp     [rcx+29h], dil
0x140002e0d  jb      loc_140002EF3
0x140002e13  mov     rax, cs:pfnWppTraceMessage
0x140002e1a  lea     rdx, [rbp+1Fh+arg_80]
0x140002e21  mov     rcx, [rcx+18h]
0x140002e25  lea     r8, WPP_dd684dc3739b34a5bf4807a1c7087b9b_Traceguids
0x140002e2c  mov     qword ptr [r11-38h], 0
0x140002e34  mov     r9d, r14d
0x140002e37  mov     [r11-40h], rdi
0x140002e3b  mov     [r11-48h], rdx
0x140002e3f  lea     rdx, [rbp+1Fh+arg_78]
0x140002e46  mov     [r11-50h], rdi
0x140002e4a  mov     [r11-58h], rdx
0x140002e4e  lea     rdx, [rbp+1Fh+arg_70]
0x140002e55  mov     [r11-60h], rdi
0x140002e59  mov     [r11-68h], rdx
0x140002e5d  lea     rdx, [rbp+1Fh+arg_68]
0x140002e64  mov     [r11-70h], rdi
0x140002e68  mov     [r11-78h], rdx
0x140002e6c  lea     rdx, [rbp+1Fh+arg_60]
0x140002e73  mov     [r11-80h], rdi
0x140002e77  mov     [r11-88h], rdx
0x140002e7e  lea     rdx, [rbp+1Fh+arg_58]
0x140002e85  mov     [r11-90h], rdi
0x140002e8c  mov     [r11-98h], rdx
0x140002e93  lea     rdx, [rbp+1Fh+arg_50]
0x140002e97  mov     [rsp+110h+var_98], rdi
0x140002e9c  mov     [rsp+110h+var_A0], rdx
0x140002ea1  lea     rdx, [rbp+1Fh+arg_48]
0x140002ea5  mov     [rsp+110h+var_A8], rdi
0x140002eaa  mov     [rsp+110h+var_B0], rdx
0x140002eaf  lea     rdx, [rbp+1Fh+arg_40]
0x140002eb3  mov     [rsp+110h+var_B8], rdi
0x140002eb8  mov     [rsp+110h+var_C0], rdx
0x140002ebd  lea     rdx, [rbp+1Fh+arg_38]
0x140002ec1  mov     [rsp+110h+var_C8], rdi
0x140002ec6  mov     [rsp+110h+var_D0], rdx
0x140002ecb  lea     rdx, [rbp+1Fh+arg_30]
0x140002ecf  mov     [rsp+110h+var_D8], rdi
0x140002ed4  mov     [rsp+110h+var_E0], rdx
0x140002ed9  lea     rdx, [rbp+1Fh+arg_28]
0x140002edd  mov     [rsp+110h+var_E8], 8
0x140002ee6  mov     [rsp+110h+var_F0], rdx
0x140002eeb  lea     edx, [rdi+27h]
0x140002eee  call    _guard_dispatch_icall
0x140002ef3  mov     qword ptr [rsp+0E8h], 0
0x140002eff  lea     rax, [rbp+1Fh+arg_80]
0x140002f06  mov     [rsp+110h+var_30], rdi
0x140002f0e  lea     r9, WPP_dd684dc3739b34a5bf4807a1c7087b9b_Traceguids
0x140002f15  mov     [rsp+110h+var_38], rax
0x140002f1d  mov     r8d, 5
0x140002f23  mov     [rsp+110h+var_40], rdi
0x140002f2b  lea     rax, [rbp+1Fh+arg_78]
0x140002f32  mov     [rsp+110h+var_48], rax
0x140002f3a  mov     edx, edi
0x140002f3c  mov     [rsp+110h+var_50], rdi
0x140002f44  lea     rax, [rbp+1Fh+arg_70]
0x140002f4b  mov     [rsp+110h+var_58], rax
0x140002f53  mov     rcx, rbx
0x140002f56  mov     [rsp+110h+var_60], rdi
0x140002f5e  lea     rax, [rbp+1Fh+arg_68]
0x140002f65  mov     [rsp+110h+var_68], rax
0x140002f6d  lea     rax, [rbp+1Fh+arg_60]
0x140002f74  mov     [rsp+110h+var_70], rdi
0x140002f7c  mov     [rsp+110h+var_78], rax
0x140002f84  lea     rax, [rbp+1Fh+arg_58]
0x140002f8b  mov     [rsp+110h+var_80], rdi
0x140002f93  mov     [rsp+110h+var_88], rax
0x140002f9b  lea     rax, [rbp+1Fh+arg_50]
0x140002f9f  mov     [rsp+110h+var_90], rdi
0x140002fa7  mov     [rsp+110h+var_98], rax
0x140002fac  lea     rax, [rbp+1Fh+arg_48]
0x140002fb0  mov     [rsp+110h+var_A0], rdi
0x140002fb5  mov     [rsp+110h+var_A8], rax
0x140002fba  lea     rax, [rbp+1Fh+arg_40]
0x140002fbe  mov     [rsp+110h+var_B0], rdi
0x140002fc3  mov     [rsp+110h+var_B8], rax
0x140002fc8  lea     rax, [rbp+1Fh+arg_38]
0x140002fcc  mov     [rsp+110h+var_C0], rdi
0x140002fd1  mov     [rsp+110h+var_C8], rax
0x140002fd6  lea     rax, [rbp+1Fh+arg_30]
0x140002fda  mov     [rsp+110h+var_D0], rdi
0x140002fdf  mov     [rsp+110h+var_D8], rax
0x140002fe4  lea     rax, [rbp+1Fh+arg_28]
0x140002fe8  mov     [rsp+110h+var_E0], 8
0x140002ff1  mov     [rsp+110h+var_E8], rax
0x140002ff6  mov     word ptr [rsp+110h+var_F0], r14w
0x140002ffc  call    cs:__imp_WppAutoLogTrace
0x140003003  nop     dword ptr [rax+rax+00h]
0x140003008  add     rsp, 0F8h
0x14000300f  pop     r14
0x140003011  pop     rdi
0x140003012  pop     rbx
0x140003013  pop     rbp
0x140003014  retn
```
