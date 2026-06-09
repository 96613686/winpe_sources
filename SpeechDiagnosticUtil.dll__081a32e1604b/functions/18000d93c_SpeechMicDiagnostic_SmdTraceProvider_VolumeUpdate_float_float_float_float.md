# SpeechMicDiagnostic::SmdTraceProvider::VolumeUpdate<float &,float &>(float &,float &)

- ea: `0x18000d93c`
- end: `0x18000d9ea`
- name: `??$VolumeUpdate@AEAMAEAM@SmdTraceProvider@SpeechMicDiagnostic@@SAXAEAM0@Z`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000fba4`

## callees

- `0x180001640`
- `0x180002910`
- `0x1800068cc`
- `0x18000d93c`

## pseudocode

```c
ULONG __fastcall SpeechMicDiagnostic::SmdTraceProvider::VolumeUpdate<float &,float &>(int *a1, int *a2)
{
  ULONG *v4; // rcx
  ULONG result; // eax
  int v6; // xmm0_4
  int v7; // xmm1_4
  int v8; // [rsp+30h] [rbp-68h] BYREF
  int v9; // [rsp+34h] [rbp-64h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+40h] [rbp-58h] BYREF
  int *v11; // [rsp+60h] [rbp-38h]
  __int64 v12; // [rsp+68h] [rbp-30h]
  int *v13; // [rsp+70h] [rbp-28h]
  __int64 v14; // [rsp+78h] [rbp-20h]

  v4 = (ULONG *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
  result = *v4;
  if ( *v4 > 5 )
  {
    v6 = *a2;
    v7 = *a1;
    v13 = &v8;
    v14 = 4;
    v11 = &v9;
    v12 = 4;
    v8 = v6;
    v9 = v7;
    return tlgWriteTransfer_EventWriteTransfer((__int64)v4, (unsigned __int8 *)&dword_180015C64, 0, 0, 4u, &v10);
  }
  return result;
}

```

## disassembly

```asm
0x18000d93c  mov     [rsp+arg_0], rbx
0x18000d941  push    rdi
0x18000d942  sub     rsp, 90h
0x18000d949  mov     rax, cs:__security_cookie
0x18000d950  xor     rax, rsp
0x18000d953  mov     [rsp+98h+var_18], rax
0x18000d95b  mov     rbx, rdx
0x18000d95e  mov     rdi, rcx
0x18000d961  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000d966  mov     rcx, [rax+8]
0x18000d96a  mov     eax, [rcx]
0x18000d96c  cmp     eax, 5
0x18000d96f  jbe     short loc_18000D9C8
0x18000d971  movss   xmm0, dword ptr [rbx]
0x18000d975  lea     rax, [rsp+98h+var_68]
0x18000d97a  movss   xmm1, dword ptr [rdi]
0x18000d97e  mov     edx, 4
0x18000d983  mov     [rsp+98h+var_28], rax
0x18000d988  xor     r9d, r9d
0x18000d98b  lea     rax, [rsp+98h+var_64]
0x18000d990  mov     [rsp+98h+var_20], rdx
0x18000d995  mov     [rsp+98h+var_38], rax
0x18000d99a  xor     r8d, r8d
0x18000d99d  lea     rax, [rsp+98h+var_58]
0x18000d9a2  mov     [rsp+98h+var_30], rdx
0x18000d9a7  mov     [rsp+98h+var_70], rax
0x18000d9ac  mov     [rsp+98h+var_78], edx
0x18000d9b0  lea     rdx, dword_180015C64
0x18000d9b7  movss   [rsp+98h+var_68], xmm0
0x18000d9bd  movss   [rsp+98h+var_64], xmm1
0x18000d9c3  call    _tlgWriteTransfer_EventWriteTransfer
0x18000d9c8  mov     rcx, [rsp+98h+var_18]
0x18000d9d0  xor     rcx, rsp; StackCookie
0x18000d9d3  call    __security_check_cookie
0x18000d9d8  mov     rbx, [rsp+98h+arg_0]
0x18000d9e0  add     rsp, 90h
0x18000d9e7  pop     rdi
0x18000d9e8  retn
```
