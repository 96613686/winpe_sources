# WPP_SF_qDh_IPV6__IPV6_HHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_

- ea: `0x14002dab0`
- end: `0x14002dde5`
- name: `WPP_SF_qDh_IPV6__IPV6_HHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_`
- size: `821`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14002b95c`
- `0x14002ba44`
- `0x1400327f0`

## callees

- `0x14002dab0`
- `0x140077fa0`
- `0x140078080`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x14002dba1`
- `ntoskrnl!RtlLengthSid` at `0x14002dbc8`
- `ntoskrnl!RtlLengthSid` at `0x14002dba1`
- `ntoskrnl!RtlLengthSid` at `0x14002dbc8`

## pseudocode

```c
__int64 __fastcall WPP_SF_qDh_IPV6__IPV6_HHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_(
        __int64 a1,
        unsigned __int16 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        char a6,
        __int64 a7,
        __int64 a8,
        char a9,
        char a10,
        char a11,
        unsigned int *a12,
        __int64 *a13,
        char a14,
        __int64 *a15,
        const wchar_t *a16,
        char a17,
        unsigned int *a18)
{
  __int64 *v18; // r15
  unsigned int *v19; // r13
  __int64 *v20; // rsi
  __int64 *v21; // rdi
  const wchar_t *v22; // rbx
  bool v23; // zf
  unsigned int *v24; // r12
  __int64 v25; // rax
  __int64 v26; // r14
  __int64 *v27; // rcx
  ULONG v28; // eax
  __int64 *v29; // rcx
  ULONG v30; // ebp
  ULONG v31; // eax
  __int64 v32; // r8
  __int64 *v35; // [rsp+148h] [rbp-70h]
  __int64 v36; // [rsp+150h] [rbp-68h]
  __int64 v37; // [rsp+158h] [rbp-60h]
  __int64 v39; // [rsp+168h] [rbp-50h] BYREF

  v18 = &qword_14009AA40;
  v19 = a18;
  v20 = a13;
  v21 = a15;
  v22 = a16;
  v23 = *a18 == 0;
  v24 = a12;
  v37 = a7;
  v39 = a4;
  v36 = a8;
  if ( v23 )
    v35 = &qword_14009AA40;
  else
    v35 = (__int64 *)*((_QWORD *)a18 + 1);
  if ( a16 )
  {
    v25 = -1;
    do
      v23 = a16[++v25] == 0;
    while ( !v23 );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v26 = 10;
  }
  v27 = a15;
  if ( !a16 )
    v22 = L"NULL";
  if ( !a15 )
    v27 = qword_1400881B0;
  v28 = RtlLengthSid(v27);
  v29 = v20;
  v30 = v28;
  if ( !v21 )
    v21 = qword_1400881B0;
  if ( !v20 )
    v29 = qword_1400881B0;
  v31 = RtlLengthSid(v29);
  v32 = *v24;
  if ( !v20 )
    v20 = qword_1400881B0;
  if ( (_DWORD)v32 )
    v18 = (__int64 *)*((_QWORD *)v24 + 1);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, __int64 *, __int64, char *, __int64, char *, __int64, __int64, __int64, __int64, __int64, char *, __int64, char *, __int64, char *, __int64, unsigned int *, __int64, __int64 *, __int64, __int64 *, _QWORD, char *, __int64, __int64 *, _QWORD, const wchar_t *, __int64, char *, __int64, unsigned int *, __int64, __int64 *, _QWORD, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_bdeae4f755aa39549b4065b41625a3d6_Traceguids,
           a2,
           &v39,
           8,
           &a5,
           4,
           &a6,
           2,
           v37,
           16,
           v36,
           16,
           &a9,
           2,
           &a10,
           2,
           &a11,
           4,
           v24,
           2,
           v18,
           v32,
           v20,
           v31,
           &a14,
           4,
           v21,
           v30,
           v22,
           v26,
           &a17,
           8,
           v19,
           2,
           v35,
           *v19,
           0);
}

```

## disassembly

```asm
0x14002dab0  mov     [rsp+arg_10], rbx
0x14002dab5  push    rbp
0x14002dab6  push    rsi
0x14002dab7  push    rdi
0x14002dab8  push    r12
0x14002daba  push    r13
0x14002dabc  push    r14
0x14002dabe  push    r15
0x14002dac0  sub     rsp, 180h
0x14002dac7  mov     rax, cs:__security_cookie
0x14002dace  xor     rax, rsp
0x14002dad1  mov     [rsp+1B8h+var_48], rax
0x14002dad9  mov     rax, [rsp+1B8h+arg_30]
0x14002dae1  lea     r15, qword_14009AA40
0x14002dae8  mov     r13, [rsp+1B8h+arg_88]
0x14002daf0  mov     rsi, [rsp+1B8h+arg_60]
0x14002daf8  mov     rdi, [rsp+1B8h+arg_70]
0x14002db00  mov     rbx, [rsp+1B8h+arg_78]
0x14002db08  cmp     dword ptr [r13+0], 0
0x14002db0d  mov     r12, [rsp+1B8h+arg_58]
0x14002db15  mov     [rsp+1B8h+var_60], rax
0x14002db1d  mov     rax, [rsp+1B8h+arg_38]
0x14002db25  mov     [rsp+1B8h+var_78], dx
0x14002db2d  mov     [rsp+1B8h+var_58], rcx
0x14002db35  mov     [rsp+1B8h+var_50], r9
0x14002db3d  mov     [rsp+1B8h+var_68], rax
0x14002db45  jz      loc_14002DDD8
0x14002db4b  mov     rax, [r13+8]
0x14002db4f  mov     [rsp+1B8h+var_70], rax
0x14002db57  test    rbx, rbx
0x14002db5a  jz      loc_14002DDCD
0x14002db60  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14002db67  nop     word ptr [rax+rax+00000000h]
0x14002db70  cmp     word ptr [rbx+rax*2+2], 0
0x14002db76  lea     rax, [rax+1]
0x14002db7a  jnz     short loc_14002DB70
0x14002db7c  lea     r14, ds:2[rax*2]
0x14002db84  test    rbx, rbx
0x14002db87  lea     rax, aNull_0; "NULL"
0x14002db8e  mov     rcx, rdi
0x14002db91  cmovz   rbx, rax
0x14002db95  test    rdi, rdi
0x14002db98  jnz     short loc_14002DBA1
0x14002db9a  lea     rcx, qword_1400881B0; Sid
0x14002dba1  call    cs:__imp_RtlLengthSid
0x14002dba8  nop     dword ptr [rax+rax+00h]
0x14002dbad  test    rdi, rdi
0x14002dbb0  mov     rcx, rsi
0x14002dbb3  mov     ebp, eax
0x14002dbb5  lea     rax, qword_1400881B0
0x14002dbbc  cmovz   rdi, rax
0x14002dbc0  test    rsi, rsi
0x14002dbc3  jnz     short loc_14002DBC8
0x14002dbc5  mov     rcx, rax; Sid
0x14002dbc8  call    cs:__imp_RtlLengthSid
0x14002dbcf  nop     dword ptr [rax+rax+00h]
0x14002dbd4  mov     r8d, [r12]
0x14002dbd8  test    rsi, rsi
0x14002dbdb  mov     edx, eax
0x14002dbdd  lea     rax, qword_1400881B0
0x14002dbe4  cmovz   rsi, rax
0x14002dbe8  test    r8d, r8d
0x14002dbeb  jz      short loc_14002DBF2
0x14002dbed  mov     r15, [r12+8]
0x14002dbf2  mov     eax, [r13+0]
0x14002dbf6  mov     [rsp+1B8h+var_88], 0
0x14002dc02  mov     [rsp+1B8h+var_90], rax
0x14002dc0a  mov     rax, [rsp+1B8h+var_70]
0x14002dc12  mov     [rsp+1B8h+var_98], rax
0x14002dc1a  lea     rax, [rsp+1B8h+arg_80]
0x14002dc22  movzx   r9d, [rsp+1B8h+var_78]
0x14002dc2b  mov     [rsp+1B8h+var_A0], 2
0x14002dc37  mov     [rsp+1B8h+var_A8], r13
0x14002dc3f  mov     [rsp+1B8h+var_B0], 8
0x14002dc4b  mov     [rsp+1B8h+var_B8], rax
0x14002dc53  lea     rax, [rsp+1B8h+arg_68]
0x14002dc5b  mov     [rsp+1B8h+var_C0], r14
0x14002dc63  mov     [rsp+1B8h+var_C8], rbx
0x14002dc6b  mov     ecx, ebp
0x14002dc6d  mov     [rsp+1B8h+var_D0], rcx
0x14002dc75  mov     rcx, [rsp+1B8h+var_58]
0x14002dc7d  mov     [rsp+1B8h+var_D8], rdi
0x14002dc85  mov     [rsp+1B8h+var_E0], 4
0x14002dc91  mov     [rsp+1B8h+var_E8], rax
0x14002dc99  lea     rax, [rsp+1B8h+arg_50]
0x14002dca1  mov     [rsp+1B8h+var_F0], rdx
0x14002dca9  mov     edx, 2Bh ; '+'
0x14002dcae  mov     [rsp+1B8h+var_F8], rsi
0x14002dcb6  mov     [rsp+1B8h+var_100], r8
0x14002dcbe  lea     r8, WPP_bdeae4f755aa39549b4065b41625a3d6_Traceguids
0x14002dcc5  mov     [rsp+1B8h+var_108], r15
0x14002dccd  mov     [rsp+1B8h+var_110], 2
0x14002dcd9  mov     [rsp+1B8h+var_118], r12
0x14002dce1  mov     [rsp+1B8h+var_120], 4
0x14002dced  mov     [rsp+1B8h+var_128], rax
0x14002dcf5  lea     rax, [rsp+1B8h+arg_48]
0x14002dcfd  mov     [rsp+1B8h+var_130], 2
0x14002dd09  mov     [rsp+1B8h+var_138], rax
0x14002dd11  lea     rax, [rsp+1B8h+arg_40]
0x14002dd19  mov     [rsp+1B8h+var_140], 2
0x14002dd22  mov     [rsp+1B8h+var_148], rax
0x14002dd27  mov     rax, [rsp+1B8h+var_68]
0x14002dd2f  mov     [rsp+1B8h+var_150], 10h
0x14002dd38  mov     [rsp+1B8h+var_158], rax
0x14002dd3d  mov     rax, [rsp+1B8h+var_60]
0x14002dd45  mov     [rsp+1B8h+var_160], 10h
0x14002dd4e  mov     [rsp+1B8h+var_168], rax
0x14002dd53  lea     rax, [rsp+1B8h+arg_28]
0x14002dd5b  mov     [rsp+1B8h+var_170], 2
0x14002dd64  mov     [rsp+1B8h+var_178], rax
0x14002dd69  lea     rax, [rsp+1B8h+arg_20]
0x14002dd71  mov     [rsp+1B8h+var_180], 4
0x14002dd7a  mov     [rsp+1B8h+var_188], rax
0x14002dd7f  lea     rax, [rsp+1B8h+var_50]
0x14002dd87  mov     [rsp+1B8h+var_190], 8
0x14002dd90  mov     [rsp+1B8h+var_198], rax
0x14002dd95  mov     rax, cs:pfnWppTraceMessage
0x14002dd9c  call    _guard_dispatch_icall
0x14002dda1  mov     rcx, [rsp+1B8h+var_48]
0x14002dda9  xor     rcx, rsp; StackCookie
0x14002ddac  call    __security_check_cookie
0x14002ddb1  mov     rbx, [rsp+1B8h+arg_10]
0x14002ddb9  add     rsp, 180h
0x14002ddc0  pop     r15
0x14002ddc2  pop     r14
0x14002ddc4  pop     r13
0x14002ddc6  pop     r12
0x14002ddc8  pop     rdi
0x14002ddc9  pop     rsi
0x14002ddca  pop     rbp
0x14002ddcb  retn
0x14002ddcd  mov     r14d, 0Ah
0x14002ddd3  jmp     loc_14002DB84
0x14002ddd8  mov     [rsp+1B8h+var_70], r15
0x14002dde0  jmp     loc_14002DB57
```
