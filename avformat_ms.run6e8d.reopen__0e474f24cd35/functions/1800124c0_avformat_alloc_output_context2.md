# avformat_alloc_output_context2

- ea: `0x1800124c0`
- end: `0x180012605`
- name: `avformat_alloc_output_context2`
- size: `325`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180001810`
- `0x18000fa10`
- `0x1800124c0`
- `0x180019290`
- `0x18001bb58`
- `0x18001bb94`
- `0x18001bbac`
- `0x18001bbfa`

## string_xrefs

- `0x180012550`: `Unable to choose an output format for '%s'; use a standard extension for the filename or specify the format manually.\n`

## pseudocode

```c
__int64 __fastcall avformat_alloc_output_context2(_QWORD *a1, __int64 a2, const char *a3, const char *a4)
{
  __int64 v8; // rax
  _QWORD *v9; // rbx
  unsigned int v10; // edi
  _QWORD *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax

  v8 = avformat_alloc_context();
  *a1 = 0;
  v9 = (_QWORD *)v8;
  if ( !v8 )
    goto LABEL_16;
  if ( a2 )
    goto LABEL_8;
  if ( !a3 )
  {
    a2 = av_guess_format(0, a4, 0);
    if ( !a2 )
    {
      v10 = -22;
      av_log(
        v9,
        16,
        "Unable to choose an output format for '%s'; use a standard extension for the filename or specify the format manually.\n",
        a4);
      goto LABEL_17;
    }
    goto LABEL_8;
  }
  a2 = av_guess_format(a3, 0, 0);
  if ( a2 )
  {
LABEL_8:
    v9[2] = a2;
    if ( *(int *)(a2 + 64) <= 0 )
    {
      v9[3] = 0;
      goto LABEL_13;
    }
    _mm_lfence();
    v11 = (_QWORD *)av_mallocz(*(int *)(a2 + 64));
    v9[3] = v11;
    if ( v11 )
    {
      v12 = *(_QWORD *)(v9[2] + 56LL);
      if ( v12 )
      {
        *v11 = v12;
        av_opt_set_defaults(v9[3]);
      }
LABEL_13:
      if ( !a4 || (v13 = av_strdup(a4), (v9[11] = v13) != 0) )
      {
        *a1 = v9;
        return 0;
      }
    }
LABEL_16:
    av_log(v9, 16, "Out of memory\n");
    v10 = -12;
    goto LABEL_17;
  }
  av_log(v9, 16, "Requested output format '%s' is not known.\n", a3);
  v10 = -22;
LABEL_17:
  avformat_free_context(v9);
  return v10;
}

```

## disassembly

```asm
0x1800124c0  mov     rax, rsp
0x1800124c3  mov     [rax+8], rbx
0x1800124c7  mov     [rax+10h], rbp
0x1800124cb  mov     [rax+18h], rsi
0x1800124cf  mov     [rax+20h], rdi
0x1800124d3  push    r14
0x1800124d5  sub     rsp, 20h
0x1800124d9  mov     rsi, r9
0x1800124dc  mov     rbp, r8
0x1800124df  mov     rdi, rdx
0x1800124e2  mov     r14, rcx
0x1800124e5  call    avformat_alloc_context
0x1800124ea  mov     qword ptr [r14], 0
0x1800124f1  mov     rbx, rax
0x1800124f4  test    rax, rax
0x1800124f7  jz      loc_1800125C7
0x1800124fd  test    rdi, rdi
0x180012500  jnz     short loc_180012567
0x180012502  xor     r8d, r8d
0x180012505  test    rbp, rbp
0x180012508  jz      short loc_18001253B
0x18001250a  xor     edx, edx
0x18001250c  mov     rcx, rbp
0x18001250f  call    av_guess_format
0x180012514  mov     rdi, rax
0x180012517  test    rax, rax
0x18001251a  jnz     short loc_180012567
0x18001251c  mov     r9, rbp
0x18001251f  lea     r8, aRequestedOutpu; "Requested output format '%s' is not kno"...
0x180012526  lea     edx, [rax+10h]
0x180012529  mov     rcx, rbx
0x18001252c  call    av_log
0x180012531  mov     edi, 0FFFFFFEAh
0x180012536  jmp     loc_1800125E0
0x18001253b  mov     rdx, rsi
0x18001253e  xor     ecx, ecx
0x180012540  call    av_guess_format
0x180012545  mov     rdi, rax
0x180012548  test    rax, rax
0x18001254b  jnz     short loc_180012567
0x18001254d  mov     r9, rsi
0x180012550  lea     r8, aUnableToChoose; "Unable to choose an output format for '"...
0x180012557  lea     edx, [rax+10h]
0x18001255a  mov     rcx, rbx
0x18001255d  lea     edi, [rax-16h]
0x180012560  call    av_log
0x180012565  jmp     short loc_1800125E0
0x180012567  mov     [rbx+10h], rdi
0x18001256b  movsxd  rax, dword ptr [rdi+40h]
0x18001256f  test    eax, eax
0x180012571  jle     short loc_1800125A2
0x180012573  lfence
0x180012576  mov     rcx, rax
0x180012579  call    av_mallocz
0x18001257e  mov     [rbx+18h], rax
0x180012582  test    rax, rax
0x180012585  jz      short loc_1800125C7
0x180012587  mov     rcx, [rbx+10h]
0x18001258b  mov     rdx, [rcx+38h]
0x18001258f  test    rdx, rdx
0x180012592  jz      short loc_1800125AA
0x180012594  mov     [rax], rdx
0x180012597  mov     rcx, [rbx+18h]
0x18001259b  call    av_opt_set_defaults
0x1800125a0  jmp     short loc_1800125AA
0x1800125a2  mov     qword ptr [rbx+18h], 0
0x1800125aa  test    rsi, rsi
0x1800125ad  jz      short loc_1800125C0
0x1800125af  mov     rcx, rsi
0x1800125b2  call    av_strdup
0x1800125b7  mov     [rbx+58h], rax
0x1800125bb  test    rax, rax
0x1800125be  jz      short loc_1800125C7
0x1800125c0  mov     [r14], rbx
0x1800125c3  xor     eax, eax
0x1800125c5  jmp     short loc_1800125EA
0x1800125c7  lea     r8, aOutOfMemory; "Out of memory\n"
0x1800125ce  mov     edx, 10h
0x1800125d3  mov     rcx, rbx
0x1800125d6  call    av_log
0x1800125db  mov     edi, 0FFFFFFF4h
0x1800125e0  mov     rcx, rbx
0x1800125e3  call    avformat_free_context
0x1800125e8  mov     eax, edi
0x1800125ea  mov     rbx, [rsp+28h+arg_0]
0x1800125ef  mov     rbp, [rsp+28h+arg_8]
0x1800125f4  mov     rsi, [rsp+28h+arg_10]
0x1800125f9  mov     rdi, [rsp+28h+arg_18]
0x1800125fe  add     rsp, 20h
0x180012602  pop     r14
0x180012604  retn
```
