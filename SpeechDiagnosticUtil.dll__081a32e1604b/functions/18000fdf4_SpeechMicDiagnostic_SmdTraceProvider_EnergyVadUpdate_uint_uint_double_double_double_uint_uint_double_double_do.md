# SpeechMicDiagnostic::SmdTraceProvider::EnergyVadUpdate<uint &,uint &,double &,double &,double &>(uint &,uint &,double &,double &,double &)

- ea: `0x18000fdf4`
- end: `0x18000feed`
- name: `??$EnergyVadUpdate@AEAIAEAIAEANAEANAEAN@SmdTraceProvider@SpeechMicDiagnostic@@SAXAEAI0AEAN11@Z`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ff2c`

## callees

- `0x180001640`
- `0x180002910`
- `0x1800068cc`
- `0x18000fdf4`

## pseudocode

```c
ULONG __fastcall SpeechMicDiagnostic::SmdTraceProvider::EnergyVadUpdate<unsigned int &,unsigned int &,double &,double &,double &>(
        int *a1,
        int *a2,
        __int64 *a3,
        __int64 *a4,
        __int64 *a5)
{
  ULONG *v9; // rcx
  ULONG result; // eax
  __int64 v11; // xmm0_8
  int v12; // [rsp+30h] [rbp-71h] BYREF
  int v13; // [rsp+34h] [rbp-6Dh] BYREF
  __int64 v14; // [rsp+38h] [rbp-69h] BYREF
  __int64 v15; // [rsp+40h] [rbp-61h] BYREF
  __int64 v16; // [rsp+48h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+50h] [rbp-51h] BYREF
  int *v18; // [rsp+70h] [rbp-31h]
  __int64 v19; // [rsp+78h] [rbp-29h]
  int *v20; // [rsp+80h] [rbp-21h]
  __int64 v21; // [rsp+88h] [rbp-19h]
  __int64 *v22; // [rsp+90h] [rbp-11h]
  __int64 v23; // [rsp+98h] [rbp-9h]
  __int64 *v24; // [rsp+A0h] [rbp-1h]
  __int64 v25; // [rsp+A8h] [rbp+7h]
  __int64 *v26; // [rsp+B0h] [rbp+Fh]
  __int64 v27; // [rsp+B8h] [rbp+17h]

  v9 = (ULONG *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
  result = *v9;
  if ( *v9 > 5 )
  {
    v15 = *a4;
    v27 = 8;
    v11 = *a5;
    v12 = *a2;
    v13 = *a1;
    v26 = &v14;
    v24 = &v15;
    v22 = &v16;
    v20 = &v12;
    v18 = &v13;
    v14 = v11;
    v16 = *a3;
    v25 = 8;
    v23 = 8;
    v21 = 4;
    v19 = 4;
    return tlgWriteTransfer_EventWriteTransfer((__int64)v9, (unsigned __int8 *)byte_180015D45, 0, 0, 7u, &v17);
  }
  return result;
}

```

## disassembly

```asm
0x18000fdf4  push    rbp
0x18000fdf6  push    rbx
0x18000fdf7  push    rsi
0x18000fdf8  push    rdi
0x18000fdf9  push    r14
0x18000fdfb  lea     rbp, [rsp-2Fh]
0x18000fe00  sub     rsp, 0D0h
0x18000fe07  mov     rax, cs:__security_cookie
0x18000fe0e  xor     rax, rsp
0x18000fe11  mov     [rbp+4Fh+var_30], rax
0x18000fe15  mov     rbx, r9
0x18000fe18  mov     rdi, r8
0x18000fe1b  mov     rsi, rdx
0x18000fe1e  mov     r14, rcx
0x18000fe21  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000fe26  mov     rcx, [rax+8]
0x18000fe2a  mov     eax, [rcx]
0x18000fe2c  cmp     eax, 5
0x18000fe2f  jbe     loc_18000FED2
0x18000fe35  mov     rax, [rbp+4Fh+arg_20]
0x18000fe39  lea     rdx, byte_180015D45
0x18000fe40  movsd   xmm1, qword ptr [rbx]
0x18000fe44  xor     r9d, r9d
0x18000fe47  xor     r8d, r8d
0x18000fe4a  movsd   [rbp+4Fh+var_B0], xmm1
0x18000fe4f  mov     [rbp+4Fh+var_38], 8
0x18000fe57  movsd   xmm0, qword ptr [rax]
0x18000fe5b  mov     eax, [rsi]
0x18000fe5d  mov     [rbp+4Fh+var_C0], eax
0x18000fe60  mov     eax, [r14]
0x18000fe63  mov     [rbp+4Fh+var_BC], eax
0x18000fe66  lea     rax, [rbp+4Fh+var_B8]
0x18000fe6a  mov     [rbp+4Fh+var_40], rax
0x18000fe6e  lea     rax, [rbp+4Fh+var_B0]
0x18000fe72  mov     [rbp+4Fh+var_50], rax
0x18000fe76  lea     rax, [rbp+4Fh+var_A8]
0x18000fe7a  mov     [rbp+4Fh+var_60], rax
0x18000fe7e  lea     rax, [rbp+4Fh+var_C0]
0x18000fe82  mov     [rbp+4Fh+var_70], rax
0x18000fe86  lea     rax, [rbp+4Fh+var_BC]
0x18000fe8a  mov     [rbp+4Fh+var_80], rax
0x18000fe8e  lea     rax, [rbp+4Fh+var_A0]
0x18000fe92  movsd   [rbp+4Fh+var_B8], xmm0
0x18000fe97  movsd   xmm0, qword ptr [rdi]
0x18000fe9b  mov     [rsp+0F0h+var_C8], rax
0x18000fea0  mov     [rsp+0F0h+var_D0], 7
0x18000fea8  movsd   [rbp+4Fh+var_A8], xmm0
0x18000fead  mov     [rbp+4Fh+var_48], 8
0x18000feb5  mov     [rbp+4Fh+var_58], 8
0x18000febd  mov     [rbp+4Fh+var_68], 4
0x18000fec5  mov     [rbp+4Fh+var_78], 4
0x18000fecd  call    _tlgWriteTransfer_EventWriteTransfer
0x18000fed2  mov     rcx, [rbp+4Fh+var_30]
0x18000fed6  xor     rcx, rsp; StackCookie
0x18000fed9  call    __security_check_cookie
0x18000fede  add     rsp, 0D0h
0x18000fee5  pop     r14
0x18000fee7  pop     rdi
0x18000fee8  pop     rsi
0x18000fee9  pop     rbx
0x18000feea  pop     rbp
0x18000feeb  retn
```
