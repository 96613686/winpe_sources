# WPP_RECORDER_AND_TRACE_SF_DDLLLL

- ea: `0x14000638c`
- end: `0x1400064bb`
- name: `WPP_RECORDER_AND_TRACE_SF_DDLLLL`
- size: `303`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400030e0`

## callees

- `0x14000638c`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400064a2`
- `WppRecorder!WppAutoLogTrace` at `0x1400064a2`

## pseudocode

```c
__int64 WPP_RECORDER_AND_TRACE_SF_DDLLLL(
        __int64 a1,
        char a2,
        _DWORD a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        ...)
{
  int v10; // [rsp+28h] [rbp-71h]
  __int64 v11; // [rsp+108h] [rbp+6Fh] BYREF
  va_list va; // [rsp+108h] [rbp+6Fh]
  __int64 v13; // [rsp+110h] [rbp+77h] BYREF
  va_list va1; // [rsp+110h] [rbp+77h]
  __int64 v15; // [rsp+118h] [rbp+7Fh] BYREF
  va_list va2; // [rsp+118h] [rbp+7Fh]
  __int64 v17; // [rsp+120h] [rbp+87h] BYREF
  va_list va3; // [rsp+120h] [rbp+87h]
  __int64 v19; // [rsp+128h] [rbp+8Fh] BYREF
  va_list va4; // [rsp+128h] [rbp+8Fh]
  va_list va5; // [rsp+130h] [rbp+97h] BYREF

  va_start(va5, a8);
  va_start(va4, a8);
  va_start(va3, a8);
  va_start(va2, a8);
  va_start(va1, a8);
  va_start(va, a8);
  v11 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v13 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v15 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v17 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v19 = va_arg(va5, _QWORD);
  if ( a2 )
    ((void (__fastcall *)(__int64, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))WPP_MAIN_CB.Queue.Wcb.DeviceObject)(
      a1,
      43,
      WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
      57,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      (__int64 *)va2,
      4,
      (__int64 *)va3,
      4,
      (__int64 *)va4,
      4,
      va5,
      4,
      0);
  LOWORD(v10) = 57;
  return WppAutoLogTrace(
           a4,
           4,
           4,
           WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
           v10,
           (__int64 *)va,
           4,
           (__int64 *)va1,
           4,
           (__int64 *)va2,
           4,
           (__int64 *)va3,
           4,
           (__int64 *)va4,
           4,
           va5,
           4,
           0);
}

```

## disassembly

```asm
0x14000638c  mov     r11, rsp
0x14000638f  push    rbp
0x140006390  push    rbx
0x140006391  push    rsi
0x140006392  push    rdi
0x140006393  lea     rbp, [r11-27h]
0x140006397  sub     rsp, 98h
0x14000639e  mov     esi, 39h ; '9'
0x1400063a3  mov     rbx, r9
0x1400063a6  lea     edi, [rsi-35h]
0x1400063a9  test    dl, dl
0x1400063ab  jz      short loc_140006422
0x1400063ad  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x1400063b4  lea     rdx, [rbp+1Fh+arg_68]
0x1400063bb  mov     qword ptr [r11-38h], 0
0x1400063c3  lea     r8, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x1400063ca  mov     [r11-40h], rdi
0x1400063ce  mov     r9d, esi
0x1400063d1  mov     [r11-48h], rdx
0x1400063d5  lea     rdx, [rbp+1Fh+arg_60]
0x1400063dc  mov     [r11-50h], rdi
0x1400063e0  mov     [r11-58h], rdx
0x1400063e4  lea     rdx, [rbp+1Fh+arg_58]
0x1400063eb  mov     [r11-60h], rdi
0x1400063ef  mov     [r11-68h], rdx
0x1400063f3  lea     rdx, [rbp+1Fh+arg_50]
0x1400063f7  mov     [r11-70h], rdi
0x1400063fb  mov     [r11-78h], rdx
0x1400063ff  lea     rdx, [rbp+1Fh+arg_48]
0x140006403  mov     [r11-80h], rdi
0x140006407  mov     [rsp+0B0h+var_80], rdx
0x14000640c  lea     rdx, [rbp+1Fh+arg_40]
0x140006410  mov     [rsp+0B0h+var_88], rdi
0x140006415  mov     [rsp+0B0h+var_90], rdx
0x14000641a  lea     edx, [rsi-0Eh]
0x14000641d  call    _guard_dispatch_icall
0x140006422  mov     qword ptr [rsp+88h], 0
0x14000642e  lea     rax, [rbp+1Fh+arg_68]
0x140006435  mov     [rsp+0B0h+var_30], rdi
0x14000643d  lea     r9, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140006444  mov     [rsp+0B0h+var_38], rax
0x140006449  mov     r8d, edi
0x14000644c  mov     [rsp+0B0h+var_40], rdi
0x140006451  lea     rax, [rbp+1Fh+arg_60]
0x140006458  mov     [rsp+0B0h+var_48], rax
0x14000645d  mov     edx, edi
0x14000645f  mov     [rsp+0B0h+var_50], rdi
0x140006464  lea     rax, [rbp+1Fh+arg_58]
0x14000646b  mov     [rsp+0B0h+var_58], rax
0x140006470  mov     rcx, rbx
0x140006473  mov     [rsp+0B0h+var_60], rdi
0x140006478  lea     rax, [rbp+1Fh+arg_50]
0x14000647c  mov     [rsp+0B0h+var_68], rax
0x140006481  lea     rax, [rbp+1Fh+arg_48]
0x140006485  mov     [rsp+0B0h+var_70], rdi
0x14000648a  mov     [rsp+0B0h+var_78], rax
0x14000648f  lea     rax, [rbp+1Fh+arg_40]
0x140006493  mov     [rsp+0B0h+var_80], rdi
0x140006498  mov     [rsp+0B0h+var_88], rax
0x14000649d  mov     word ptr [rsp+0B0h+var_90], si
0x1400064a2  call    cs:__imp_WppAutoLogTrace
0x1400064a9  nop     dword ptr [rax+rax+00h]
0x1400064ae  add     rsp, 98h
0x1400064b5  pop     rdi
0x1400064b6  pop     rsi
0x1400064b7  pop     rbx
0x1400064b8  pop     rbp
0x1400064b9  retn
```
