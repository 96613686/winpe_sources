# SpeechMicDiagnostic::SmdTraceProvider::DignosticCompletion<ulong &,double &,long &>(ulong &,double &,long &)

- ea: `0x18000713c`
- end: `0x1800071f3`
- name: `??$DignosticCompletion@AEAKAEANAEAJ@SmdTraceProvider@SpeechMicDiagnostic@@SAXAEAKAEANAEAJ@Z`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007c38`

## callees

- `0x180001640`
- `0x180002910`
- `0x1800068cc`
- `0x18000713c`

## pseudocode

```c
ULONG __fastcall SpeechMicDiagnostic::SmdTraceProvider::DignosticCompletion<unsigned long &,double &,long &>(
        int *a1,
        __int64 *a2,
        int *a3)
{
  ULONG *v6; // rcx
  ULONG result; // eax
  __int64 v8; // xmm0_8
  int v9; // [rsp+30h] [rbp-39h] BYREF
  int v10; // [rsp+34h] [rbp-35h] BYREF
  __int64 v11; // [rsp+38h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+40h] [rbp-29h] BYREF
  int *v13; // [rsp+60h] [rbp-9h]
  __int64 v14; // [rsp+68h] [rbp-1h]
  __int64 *v15; // [rsp+70h] [rbp+7h]
  __int64 v16; // [rsp+78h] [rbp+Fh]
  int *v17; // [rsp+80h] [rbp+17h]
  __int64 v18; // [rsp+88h] [rbp+1Fh]

  v6 = (ULONG *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
  result = *v6;
  if ( *v6 > 5 )
  {
    v8 = *a2;
    v9 = *a3;
    v10 = *a1;
    v17 = &v9;
    v15 = &v11;
    v13 = &v10;
    v11 = v8;
    v18 = 4;
    v16 = 8;
    v14 = 4;
    return tlgWriteTransfer_EventWriteTransfer((__int64)v6, (unsigned __int8 *)byte_180014133, 0, 0, 5u, &v12);
  }
  return result;
}

```

## disassembly

```asm
0x18000713c  push    rbp
0x18000713e  push    rbx
0x18000713f  push    rsi
0x180007140  push    rdi
0x180007141  lea     rbp, [rsp-3Fh]
0x180007146  sub     rsp, 0A8h
0x18000714d  mov     rax, cs:__security_cookie
0x180007154  xor     rax, rsp
0x180007157  mov     [rbp+57h+var_30], rax
0x18000715b  mov     rbx, r8
0x18000715e  mov     rdi, rdx
0x180007161  mov     rsi, rcx
0x180007164  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x180007169  mov     rcx, [rax+8]
0x18000716d  mov     eax, [rcx]
0x18000716f  cmp     eax, 5
0x180007172  jbe     short loc_1800071DA
0x180007174  mov     eax, [rbx]
0x180007176  lea     rdx, byte_180014133
0x18000717d  movsd   xmm0, qword ptr [rdi]
0x180007181  xor     r9d, r9d
0x180007184  mov     [rbp+57h+var_90], eax
0x180007187  xor     r8d, r8d
0x18000718a  mov     eax, [rsi]
0x18000718c  mov     [rbp+57h+var_8C], eax
0x18000718f  lea     rax, [rbp+57h+var_90]
0x180007193  mov     [rbp+57h+var_40], rax
0x180007197  lea     rax, [rbp+57h+var_88]
0x18000719b  mov     [rbp+57h+var_50], rax
0x18000719f  lea     rax, [rbp+57h+var_8C]
0x1800071a3  mov     [rbp+57h+var_60], rax
0x1800071a7  lea     rax, [rbp+57h+var_80]
0x1800071ab  mov     [rsp+0C0h+var_98], rax
0x1800071b0  mov     [rsp+0C0h+var_A0], 5
0x1800071b8  movsd   [rbp+57h+var_88], xmm0
0x1800071bd  mov     [rbp+57h+var_38], 4
0x1800071c5  mov     [rbp+57h+var_48], 8
0x1800071cd  mov     [rbp+57h+var_58], 4
0x1800071d5  call    _tlgWriteTransfer_EventWriteTransfer
0x1800071da  mov     rcx, [rbp+57h+var_30]
0x1800071de  xor     rcx, rsp; StackCookie
0x1800071e1  call    __security_check_cookie
0x1800071e6  add     rsp, 0A8h
0x1800071ed  pop     rdi
0x1800071ee  pop     rsi
0x1800071ef  pop     rbx
0x1800071f0  pop     rbp
0x1800071f1  retn
```
