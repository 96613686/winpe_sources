# WPP_RECORDER_SF_sDsZZZd

- ea: `0x1400036f0`
- end: `0x140003aac`
- name: `WPP_RECORDER_SF_sDsZZZd`
- size: `956`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400157a0`

## callees

- `0x1400036f0`
- `0x140004c70`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140003a8b`
- `WppRecorder!WppAutoLogTrace` at `0x140003a8b`

## string_xrefs

- `0x1400038fe`: `onecore\base\fs\wci\bindflt\filter\create.c`
- `0x140003a6f`: `onecore\base\fs\wci\bindflt\filter\create.c`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_sDsZZZd(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        const char *a8,
        const wchar_t *a9,
        const wchar_t *a10,
        unsigned __int16 *a11)
{
  const wchar_t *v11; // r14
  const wchar_t *v12; // rbx
  __int64 v15; // r10
  __int64 v17; // r11
  __int64 v18; // rbp
  __int64 v19; // rdx
  const wchar_t *v20; // rax
  __int64 v21; // r8
  const wchar_t *v22; // r12
  __int64 v23; // r9
  const wchar_t *v24; // r13
  const wchar_t *v25; // r11
  __int64 v26; // rax
  __int64 v27; // r10
  const char *v28; // rcx
  __int64 v29; // rax
  const wchar_t *v30; // r9
  __int64 v31; // rcx
  const wchar_t *v32; // r8
  bool v33; // zf
  __int64 v34; // rdx
  int v36; // [rsp+20h] [rbp-108h]
  int v37; // [rsp+D0h] [rbp-58h] BYREF
  _DWORD v38[20]; // [rsp+D8h] [rbp-50h] BYREF
  const wchar_t *v40; // [rsp+168h] [rbp+40h]
  const wchar_t *v41; // [rsp+170h] [rbp+48h]
  const wchar_t *v42; // [rsp+178h] [rbp+50h]

  v11 = L"NULL";
  v12 = a11;
  v15 = -1;
  v17 = a1;
  v37 = -1073741192;
  v38[0] = 1698;
  v18 = 8;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    goto LABEL_32;
  if ( a11 )
  {
    v19 = *a11;
    if ( *a11 )
    {
      v42 = (const wchar_t *)*((_QWORD *)a11 + 1);
      goto LABEL_8;
    }
  }
  else
  {
    v19 = 8;
  }
  v42 = L"NULL";
LABEL_8:
  v20 = a11;
  if ( !a11 )
    v20 = L"\b";
  v40 = v20;
  if ( a10 )
  {
    v21 = *a10;
    if ( *a10 )
    {
      v41 = (const wchar_t *)*((_QWORD *)a10 + 1);
      goto LABEL_15;
    }
  }
  else
  {
    v21 = 8;
  }
  v41 = L"NULL";
LABEL_15:
  v22 = a10;
  if ( !a10 )
    v22 = L"\b";
  if ( !a9 )
  {
    v23 = 8;
    goto LABEL_21;
  }
  v23 = *a9;
  if ( !*a9 )
  {
LABEL_21:
    v24 = L"NULL";
    goto LABEL_22;
  }
  v24 = (const wchar_t *)*((_QWORD *)a9 + 1);
LABEL_22:
  v25 = a9;
  if ( !a9 )
    v25 = L"\b";
  if ( a8 )
  {
    v26 = -1;
    do
      ++v26;
    while ( a8[v26] );
    v27 = v26 + 1;
  }
  else
  {
    v27 = 5;
  }
  v28 = a8;
  if ( !a8 )
    v28 = "NULL";
  ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, const char *, __int64, _DWORD *, __int64, const char *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, int *, __int64, _QWORD))pfnWppTraceMessage)(
    WPP_GLOBAL_Control->AttachedDevice,
    43,
    WPP_48a527b79fd4344d8b4157379f595642_Traceguids,
    30,
    "onecore\\base\\fs\\wci\\bindflt\\filter\\create.c",
    44,
    v38,
    4,
    v28,
    v27,
    v25,
    2,
    v24,
    v23,
    v22,
    2,
    v41,
    v21,
    v40,
    2,
    v42,
    v19,
    &v37,
    4,
    0);
  v12 = a11;
  v17 = a1;
  v15 = -1;
LABEL_32:
  if ( v12 )
  {
    v29 = *v12;
    if ( *v12 )
    {
      v30 = (const wchar_t *)*((_QWORD *)v12 + 1);
      goto LABEL_37;
    }
  }
  else
  {
    v29 = 8;
  }
  v30 = L"NULL";
LABEL_37:
  if ( !v12 )
    v12 = L"\b";
  if ( a10 )
  {
    v31 = *a10;
    if ( *a10 )
    {
      v32 = (const wchar_t *)*((_QWORD *)a10 + 1);
      goto LABEL_44;
    }
  }
  else
  {
    v31 = 8;
  }
  v32 = L"NULL";
LABEL_44:
  if ( !a10 )
    a10 = L"\b";
  v33 = a9 == 0;
  if ( a9 )
  {
    v18 = *a9;
    if ( *a9 )
      v11 = (const wchar_t *)*((_QWORD *)a9 + 1);
    v33 = a9 == 0;
  }
  if ( v33 )
    a9 = L"\b";
  if ( a8 )
  {
    do
      ++v15;
    while ( a8[v15] );
    v34 = v15 + 1;
  }
  else
  {
    v34 = 5;
  }
  if ( !a8 )
    a8 = "NULL";
  LOWORD(v36) = 30;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64 *, int, const char *, __int64, _DWORD *, __int64, const char *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, int *, __int64, _QWORD))WppAutoLogTrace)(
           v17,
           3,
           5,
           WPP_48a527b79fd4344d8b4157379f595642_Traceguids,
           v36,
           "onecore\\base\\fs\\wci\\bindflt\\filter\\create.c",
           44,
           v38,
           4,
           a8,
           v34,
           a9,
           2,
           v11,
           v18,
           a10,
           2,
           v32,
           v31,
           v12,
           2,
           v30,
           v29,
           &v37,
           4,
           0);
}

```

## disassembly

```asm
0x1400036f0  mov     rax, rsp
0x1400036f3  mov     [rax+8], rcx
0x1400036f7  push    rbx
0x1400036f8  push    rbp
0x1400036f9  push    rsi
0x1400036fa  push    rdi
0x1400036fb  push    r12
0x1400036fd  push    r13
0x1400036ff  push    r14
0x140003701  push    r15
0x140003703  sub     rsp, 0E8h
0x14000370a  mov     rdx, cs:WPP_GLOBAL_Control
0x140003711  lea     r14, aNull_0; "NULL"
0x140003718  mov     rbx, [rsp+128h+arg_50]
0x140003720  lea     r12, asc_140008A70; "\b"
0x140003727  mov     rdi, [rsp+128h+arg_48]
0x14000372f  xor     r13d, r13d
0x140003732  mov     rsi, [rsp+128h+arg_40]
0x14000373a  or      r10, 0FFFFFFFFFFFFFFFFh
0x14000373e  mov     r15, [rsp+128h+arg_38]
0x140003746  mov     r11, rcx
0x140003749  mov     dword ptr [rax-58h], 0C0000278h
0x140003750  mov     dword ptr [rax-50h], 6A2h
0x140003757  lea     ebp, [r13+8]
0x14000375b  mov     eax, [rdx+2Ch]
0x14000375e  test    al, 10h
0x140003760  jz      loc_140003941
0x140003766  cmp     byte ptr [rdx+29h], 3
0x14000376a  jb      loc_140003941
0x140003770  test    rbx, rbx
0x140003773  jz      short loc_14000378C
0x140003775  movzx   edx, word ptr [rbx]
0x140003778  cmp     [rbx], r13w
0x14000377c  jz      short loc_14000378F
0x14000377e  mov     rcx, [rbx+8]
0x140003782  mov     [rsp+128h+arg_48], rcx
0x14000378a  jmp     short loc_140003797
0x14000378c  mov     rdx, rbp
0x14000378f  mov     [rsp+128h+arg_48], r14
0x140003797  test    rbx, rbx
0x14000379a  mov     rax, rbx
0x14000379d  cmovz   rax, r12
0x1400037a1  mov     [rsp+128h+arg_38], rax
0x1400037a9  test    rdi, rdi
0x1400037ac  jz      short loc_1400037C6
0x1400037ae  movzx   r8d, word ptr [rdi]
0x1400037b2  cmp     [rdi], r13w
0x1400037b6  jz      short loc_1400037C9
0x1400037b8  mov     rax, [rdi+8]
0x1400037bc  mov     [rsp+128h+arg_40], rax
0x1400037c4  jmp     short loc_1400037D1
0x1400037c6  mov     r8, rbp
0x1400037c9  mov     [rsp+128h+arg_40], r14
0x1400037d1  test    rdi, rdi
0x1400037d4  lea     rax, asc_140008A70; "\b"
0x1400037db  mov     r12, rdi
0x1400037de  cmovz   r12, rax
0x1400037e2  test    rsi, rsi
0x1400037e5  jz      short loc_1400037F7
0x1400037e7  movzx   r9d, word ptr [rsi]
0x1400037eb  cmp     [rsi], r13w
0x1400037ef  jz      short loc_1400037FA
0x1400037f1  mov     r13, [rsi+8]
0x1400037f5  jmp     short loc_1400037FD
0x1400037f7  mov     r9, rbp
0x1400037fa  mov     r13, r14
0x1400037fd  test    rsi, rsi
0x140003800  mov     r11, rsi
0x140003803  cmovz   r11, rax
0x140003807  test    r15, r15
0x14000380a  jz      short loc_14000381F
0x14000380c  mov     rax, r10
0x14000380f  inc     rax
0x140003812  cmp     byte ptr [r15+rax], 0
0x140003817  jnz     short loc_14000380F
0x140003819  lea     r10, [rax+1]
0x14000381d  jmp     short loc_140003825
0x14000381f  mov     r10d, 5
0x140003825  mov     [rsp+128h+var_68], 0
0x140003831  lea     rbx, [rsp+128h+var_58]
0x140003839  mov     [rsp+128h+var_70], 4
0x140003845  lea     rax, aNull; "NULL"
0x14000384c  mov     [rsp+128h+var_78], rbx
0x140003854  test    r15, r15
0x140003857  mov     [rsp+128h+var_80], rdx
0x14000385f  mov     ebx, 2
0x140003864  mov     rdx, [rsp+128h+arg_48]
0x14000386c  mov     rcx, r15
0x14000386f  mov     [rsp+128h+var_88], rdx
0x140003877  cmovz   rcx, rax
0x14000387b  mov     rdx, [rsp+128h+arg_38]
0x140003883  mov     rax, cs:pfnWppTraceMessage
0x14000388a  mov     [rsp+128h+var_90], rbx
0x140003892  mov     [rsp+128h+var_98], rdx
0x14000389a  mov     rdx, [rsp+128h+arg_40]
0x1400038a2  mov     [rsp+128h+var_A0], r8
0x1400038aa  lea     r8, WPP_48a527b79fd4344d8b4157379f595642_Traceguids
0x1400038b1  mov     [rsp+128h+var_A8], rdx
0x1400038b9  lea     edx, [rbx+29h]
0x1400038bc  mov     [rsp+128h+var_B0], rbx
0x1400038c1  mov     [rsp+128h+var_B8], r12
0x1400038c6  mov     [rsp+128h+var_C0], r9
0x1400038cb  lea     r9d, [rbx+1Ch]
0x1400038cf  mov     [rsp+128h+var_C8], r13
0x1400038d4  mov     [rsp+128h+var_D0], rbx
0x1400038d9  mov     [rsp+128h+var_D8], r11
0x1400038de  mov     [rsp+128h+var_E0], r10
0x1400038e3  mov     [rsp+128h+var_E8], rcx
0x1400038e8  lea     rcx, [rsp+128h+var_50]
0x1400038f0  mov     [rsp+128h+var_F0], 4
0x1400038f9  mov     [rsp+128h+var_F8], rcx
0x1400038fe  lea     rcx, aOnecoreBaseFsW_6; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140003905  mov     [rsp+128h+var_100], 2Ch ; ','
0x14000390e  mov     [rsp+128h+var_108], rcx
0x140003913  mov     rcx, cs:WPP_GLOBAL_Control
0x14000391a  mov     rcx, [rcx+18h]
0x14000391e  call    _guard_dispatch_icall
0x140003923  mov     rbx, [rsp+128h+arg_50]
0x14000392b  lea     r12, asc_140008A70; "\b"
0x140003932  mov     r11, [rsp+128h+arg_0]
0x14000393a  or      r10, 0FFFFFFFFFFFFFFFFh
0x14000393e  xor     r13d, r13d
0x140003941  test    rbx, rbx
0x140003944  jz      short loc_140003955
0x140003946  movzx   eax, word ptr [rbx]
0x140003949  cmp     [rbx], r13w
0x14000394d  jz      short loc_140003958
0x14000394f  mov     r9, [rbx+8]
0x140003953  jmp     short loc_14000395B
0x140003955  mov     rax, rbp
0x140003958  mov     r9, r14
0x14000395b  test    rbx, rbx
0x14000395e  cmovz   rbx, r12
0x140003962  test    rdi, rdi
0x140003965  jz      short loc_140003976
0x140003967  movzx   ecx, word ptr [rdi]
0x14000396a  cmp     [rdi], r13w
0x14000396e  jz      short loc_140003979
0x140003970  mov     r8, [rdi+8]
0x140003974  jmp     short loc_14000397C
0x140003976  mov     rcx, rbp
0x140003979  mov     r8, r14
0x14000397c  test    rdi, rdi
0x14000397f  cmovz   rdi, r12
0x140003983  test    rsi, rsi
0x140003986  jz      short loc_140003998
0x140003988  movzx   ebp, word ptr [rsi]
0x14000398b  cmp     [rsi], r13w
0x14000398f  jz      short loc_140003995
0x140003991  mov     r14, [rsi+8]
0x140003995  test    rsi, rsi
0x140003998  cmovz   rsi, r12
0x14000399c  test    r15, r15
0x14000399f  jz      short loc_1400039B0
0x1400039a1  inc     r10
0x1400039a4  cmp     [r15+r10], r13b
0x1400039a8  jnz     short loc_1400039A1
0x1400039aa  lea     rdx, [r10+1]
0x1400039ae  jmp     short loc_1400039B5
0x1400039b0  mov     edx, 5
0x1400039b5  mov     [rsp+128h+var_60], r13
0x1400039bd  lea     r10, aNull; "NULL"
0x1400039c4  mov     r12d, 4
0x1400039ca  test    r15, r15
0x1400039cd  mov     [rsp+128h+var_68], r12
0x1400039d5  cmovz   r15, r10
0x1400039d9  lea     r10, [rsp+128h+var_58]
0x1400039e1  mov     [rsp+128h+var_70], r10
0x1400039e9  mov     [rsp+128h+var_78], rax
0x1400039f1  lea     eax, [r12-2]
0x1400039f6  mov     [rsp+128h+var_80], r9
0x1400039fe  lea     r9, WPP_48a527b79fd4344d8b4157379f595642_Traceguids
0x140003a05  mov     [rsp+128h+var_88], rax
0x140003a0d  mov     [rsp+128h+var_90], rbx
0x140003a15  mov     [rsp+128h+var_98], rcx
0x140003a1d  mov     rcx, r11
0x140003a20  mov     [rsp+128h+var_A0], r8
0x140003a28  lea     r8d, [r12+1]
0x140003a2d  mov     [rsp+128h+var_A8], rax
0x140003a35  mov     [rsp+128h+var_B0], rdi
0x140003a3a  mov     [rsp+128h+var_B8], rbp
0x140003a3f  mov     [rsp+128h+var_C0], r14
0x140003a44  mov     [rsp+128h+var_C8], rax
0x140003a49  lea     rax, [rsp+128h+var_50]
0x140003a51  mov     [rsp+128h+var_D0], rsi
0x140003a56  mov     [rsp+128h+var_D8], rdx
0x140003a5b  lea     edx, [r12-1]
0x140003a60  mov     [rsp+128h+var_E0], r15
0x140003a65  mov     [rsp+128h+var_E8], r12
0x140003a6a  mov     [rsp+128h+var_F0], rax
0x140003a6f  lea     rax, aOnecoreBaseFsW_6; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140003a76  mov     [rsp+128h+var_F8], 2Ch ; ','
0x140003a7f  mov     [rsp+128h+var_100], rax
0x140003a84  mov     word ptr [rsp+128h+var_108], 1Eh
0x140003a8b  call    cs:__imp_WppAutoLogTrace
0x140003a92  nop     dword ptr [rax+rax+00h]
0x140003a97  add     rsp, 0E8h
0x140003a9e  pop     r15
0x140003aa0  pop     r14
0x140003aa2  pop     r13
0x140003aa4  pop     r12
0x140003aa6  pop     rdi
0x140003aa7  pop     rsi
0x140003aa8  pop     rbp
0x140003aa9  pop     rbx
0x140003aaa  retn
```
