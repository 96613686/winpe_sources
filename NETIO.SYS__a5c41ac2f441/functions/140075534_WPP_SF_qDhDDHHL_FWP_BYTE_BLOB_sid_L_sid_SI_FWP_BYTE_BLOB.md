# WPP_SF_qDhDDHHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_

- ea: `0x140075534`
- end: `0x1400757b1`
- name: `WPP_SF_qDhDDHHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_`
- size: `637`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14002b7b4`
- `0x14002b9d0`
- `0x1400327f0`

## callees

- `0x140075534`
- `0x140077fa0`
- `0x140078080`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x1400755dc`
- `ntoskrnl!RtlLengthSid` at `0x140075604`
- `ntoskrnl!RtlLengthSid` at `0x1400755dc`
- `ntoskrnl!RtlLengthSid` at `0x140075604`

## pseudocode

```c
__int64 __fastcall WPP_SF_qDhDDHHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_(
        __int64 a1,
        unsigned __int16 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        char a6,
        char a7,
        char a8,
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
  __int64 *v18; // r14
  __int64 *v19; // rsi
  __int64 *v20; // rdi
  const wchar_t *v21; // rbx
  unsigned int *v22; // r12
  __int64 v23; // rax
  __int64 v24; // r13
  __int64 *v25; // rcx
  ULONG v26; // eax
  __int64 *v27; // rcx
  ULONG v28; // r15d
  ULONG v29; // eax
  __int64 v30; // r8
  __int64 *v33; // [rsp+148h] [rbp-78h]
  unsigned int *v34; // [rsp+150h] [rbp-70h]
  __int64 v36; // [rsp+160h] [rbp-60h] BYREF

  v18 = &qword_14009AA40;
  v19 = a13;
  v20 = a15;
  v21 = a16;
  v22 = a12;
  v34 = a18;
  v36 = a4;
  if ( *a18 )
    v33 = (__int64 *)*((_QWORD *)a18 + 1);
  else
    v33 = &qword_14009AA40;
  if ( a16 )
  {
    v23 = -1;
    do
      ++v23;
    while ( a16[v23] );
    v24 = 2 * v23 + 2;
  }
  else
  {
    v24 = 10;
  }
  v25 = a15;
  if ( !a16 )
    v21 = L"NULL";
  if ( !a15 )
    v25 = qword_1400881B0;
  v26 = RtlLengthSid(v25);
  v27 = v19;
  v28 = v26;
  if ( !v20 )
    v20 = qword_1400881B0;
  if ( !v19 )
    v27 = qword_1400881B0;
  v29 = RtlLengthSid(v27);
  v30 = *v22;
  if ( !v19 )
    v19 = qword_1400881B0;
  if ( (_DWORD)v30 )
    v18 = (__int64 *)*((_QWORD *)v22 + 1);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, __int64 *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, unsigned int *, __int64, __int64 *, __int64, __int64 *, _QWORD, char *, __int64, __int64 *, _QWORD, const wchar_t *, __int64, char *, __int64, unsigned int *, __int64, __int64 *, _QWORD, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_bdeae4f755aa39549b4065b41625a3d6_Traceguids,
           a2,
           &v36,
           8,
           &a5,
           4,
           &a6,
           2,
           &a7,
           4,
           &a8,
           4,
           &a9,
           2,
           &a10,
           2,
           &a11,
           4,
           v22,
           2,
           v18,
           v30,
           v19,
           v29,
           &a14,
           4,
           v20,
           v28,
           v21,
           v24,
           &a17,
           8,
           v34,
           2,
           v33,
           *v34,
           0);
}

```

## disassembly

```asm
0x140075534  mov     [rsp-8+arg_10], rbx
0x140075539  push    rbp
0x14007553a  push    rsi
0x14007553b  push    rdi
0x14007553c  push    r12
0x14007553e  push    r13
0x140075540  push    r14
0x140075542  push    r15
0x140075544  lea     rbp, [rsp+50h]
0x140075549  sub     rsp, 170h
0x140075550  mov     rax, cs:__security_cookie
0x140075557  xor     rax, rsp
0x14007555a  mov     [rbp-20h+var_38], rax
0x14007555e  mov     rax, [rbp-20h+arg_88]
0x140075562  lea     r14, qword_14009AA40
0x140075569  mov     rsi, [rbp-20h+arg_60]
0x14007556d  mov     rdi, [rbp-20h+arg_70]
0x140075571  mov     rbx, [rbp-20h+arg_78]
0x140075575  mov     r12, [rbp-20h+arg_58]
0x140075579  mov     [rbp-20h+var_48], rcx
0x14007557d  xor     ecx, ecx
0x14007557f  mov     [rbp-20h+var_60], dx
0x140075583  mov     [rbp-20h+var_50], rax
0x140075587  mov     [rbp-20h+var_40], r9
0x14007558b  cmp     [rax], ecx
0x14007558d  jz      short loc_140075599
0x14007558f  mov     rax, [rax+8]
0x140075593  mov     [rbp-20h+var_58], rax
0x140075597  jmp     short loc_14007559D
0x140075599  mov     [rbp-20h+var_58], r14
0x14007559d  test    rbx, rbx
0x1400755a0  jz      short loc_1400755B9
0x1400755a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400755a6  inc     rax
0x1400755a9  cmp     [rbx+rax*2], cx
0x1400755ad  jnz     short loc_1400755A6
0x1400755af  lea     r13, ds:2[rax*2]
0x1400755b7  jmp     short loc_1400755BF
0x1400755b9  mov     r13d, 0Ah
0x1400755bf  test    rbx, rbx
0x1400755c2  lea     rax, aNull_0; "NULL"
0x1400755c9  mov     rcx, rdi
0x1400755cc  cmovz   rbx, rax
0x1400755d0  test    rdi, rdi
0x1400755d3  jnz     short loc_1400755DC
0x1400755d5  lea     rcx, qword_1400881B0; Sid
0x1400755dc  call    cs:__imp_RtlLengthSid
0x1400755e3  nop     dword ptr [rax+rax+00h]
0x1400755e8  test    rdi, rdi
0x1400755eb  mov     rcx, rsi
0x1400755ee  mov     r15d, eax
0x1400755f1  lea     rax, qword_1400881B0
0x1400755f8  cmovz   rdi, rax
0x1400755fc  test    rsi, rsi
0x1400755ff  jnz     short loc_140075604
0x140075601  mov     rcx, rax; Sid
0x140075604  call    cs:__imp_RtlLengthSid
0x14007560b  nop     dword ptr [rax+rax+00h]
0x140075610  mov     r8d, [r12]
0x140075614  test    rsi, rsi
0x140075617  mov     edx, eax
0x140075619  lea     rax, qword_1400881B0
0x140075620  cmovz   rsi, rax
0x140075624  test    r8d, r8d
0x140075627  jz      short loc_14007562E
0x140075629  mov     r14, [r12+8]
0x14007562e  mov     r9, [rbp-20h+var_50]
0x140075632  mov     r11d, 2
0x140075638  mov     [rsp+1A0h+var_70], 0
0x140075644  mov     ecx, r15d
0x140075647  mov     eax, [r9]
0x14007564a  mov     [rsp+1A0h+var_78], rax
0x140075652  mov     rax, [rbp-20h+var_58]
0x140075656  mov     [rsp+1A0h+var_80], rax
0x14007565e  lea     rax, [rbp-20h+arg_80]
0x140075662  mov     [rsp+1A0h+var_88], r11
0x14007566a  mov     [rsp+1A0h+var_90], r9
0x140075672  lea     r9d, [r11+6]
0x140075676  mov     [rsp+1A0h+var_98], r9
0x14007567e  mov     [rsp+1A0h+var_A0], rax
0x140075686  lea     rax, [rbp-20h+arg_68]
0x14007568a  mov     [rsp+1A0h+var_A8], r13
0x140075692  mov     [rsp+1A0h+var_B0], rbx
0x14007569a  mov     [rsp+1A0h+var_B8], rcx
0x1400756a2  lea     ecx, [r11+2]
0x1400756a6  mov     [rsp+1A0h+var_C0], rdi
0x1400756ae  mov     [rsp+1A0h+var_C8], rcx
0x1400756b6  mov     [rsp+1A0h+var_D0], rax
0x1400756be  lea     rax, [rbp-20h+arg_50]
0x1400756c2  mov     [rsp+1A0h+var_D8], rdx
0x1400756ca  lea     edx, [rcx+27h]
0x1400756cd  mov     [rsp+1A0h+var_E0], rsi
0x1400756d5  mov     [rsp+1A0h+var_E8], r8
0x1400756dd  lea     r8, WPP_bdeae4f755aa39549b4065b41625a3d6_Traceguids
0x1400756e4  mov     [rsp+1A0h+var_F0], r14
0x1400756ec  mov     [rsp+1A0h+var_F8], r11
0x1400756f4  mov     [rsp+1A0h+var_100], r12
0x1400756fc  mov     [rsp+1A0h+var_108], rcx
0x140075704  mov     [rsp+1A0h+var_110], rax
0x14007570c  lea     rax, [rbp-20h+arg_48]
0x140075710  mov     [rsp+1A0h+var_118], r11
0x140075718  mov     [rsp+1A0h+var_120], rax
0x140075720  lea     rax, [rbp-20h+arg_40]
0x140075724  mov     [rsp+1A0h+var_128], r11
0x140075729  mov     [rsp+1A0h+var_130], rax
0x14007572e  lea     rax, [rbp-20h+arg_38]
0x140075732  mov     [rsp+1A0h+var_138], rcx
0x140075737  mov     [rsp+1A0h+var_140], rax
0x14007573c  lea     rax, [rbp-20h+arg_30]
0x140075740  mov     [rsp+1A0h+var_148], rcx
0x140075745  mov     [rsp+1A0h+var_150], rax
0x14007574a  lea     rax, [rbp-20h+arg_28]
0x14007574e  mov     [rsp+1A0h+var_158], r11
0x140075753  mov     [rsp+1A0h+var_160], rax
0x140075758  lea     rax, [rbp-20h+arg_20]
0x14007575c  mov     [rsp+1A0h+var_168], rcx
0x140075761  mov     rcx, [rbp-20h+var_48]
0x140075765  mov     [rsp+1A0h+var_170], rax
0x14007576a  lea     rax, [rbp-20h+var_40]
0x14007576e  mov     [rsp+1A0h+var_178], r9
0x140075773  movzx   r9d, [rbp-20h+var_60]
0x140075778  mov     [rsp+1A0h+var_180], rax
0x14007577d  mov     rax, cs:pfnWppTraceMessage
0x140075784  call    _guard_dispatch_icall
0x140075789  mov     rcx, [rbp-20h+var_38]
0x14007578d  xor     rcx, rsp; StackCookie
0x140075790  call    __security_check_cookie
0x140075795  mov     rbx, [rsp+1A0h+arg_10]
0x14007579d  add     rsp, 170h
0x1400757a4  pop     r15
0x1400757a6  pop     r14
0x1400757a8  pop     r13
0x1400757aa  pop     r12
0x1400757ac  pop     rdi
0x1400757ad  pop     rsi
0x1400757ae  pop     rbp
0x1400757af  retn
```
