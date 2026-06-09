# AddNgcReader(ushort const *,ulong)

- ea: `0x18002bc50`
- end: `0x18002bdd8`
- name: `?AddNgcReader@@YAKPEBGK@Z`
- size: `392`
- prototype: `__int64 __fastcall(const unsigned __int8 *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180010670`
- `0x180019bc4`
- `0x18001c330`
- `0x180029f78`
- `0x18002b43c`
- `0x18002b600`
- `0x18002b844`
- `0x18002bc50`
- `0x18003261b`
- `0x1800326d0`
- `0x180037010`

## string_xrefs

- `0x18002bc84`: `AddNgcReader`

## pseudocode

```c
__int64 __fastcall AddNgcReader(const unsigned __int8 *a1)
{
  CNgcReader *v2; // rax
  const unsigned __int8 *v3; // rcx
  const unsigned __int16 *v4; // r9
  CNgcReader *v5; // rbx
  const unsigned __int8 *v6; // rcx
  const unsigned __int16 *v7; // r9
  __int64 v8; // rdx
  const unsigned __int8 *v9; // r8
  const unsigned __int8 *v10; // r9
  ulong v11; // eax
  ulong v12; // ebx
  const unsigned __int16 *v14; // [rsp+20h] [rbp-78h]
  ulong v15; // [rsp+30h] [rbp-68h] BYREF
  int v16; // [rsp+34h] [rbp-64h] BYREF
  CNgcReader *v17; // [rsp+38h] [rbp-60h]
  ulong pExceptionObject; // [rsp+40h] [rbp-58h] BYREF
  ulong v19; // [rsp+44h] [rbp-54h] BYREF
  ulong v20; // [rsp+48h] [rbp-50h] BYREF
  ulong v21; // [rsp+4Ch] [rbp-4Ch] BYREF
  _QWORD *v22; // [rsp+50h] [rbp-48h] BYREF
  _QWORD v23[4]; // [rsp+58h] [rbp-40h] BYREF
  char v24[16]; // [rsp+78h] [rbp-20h] BYREF

  v15 = 0;
  v16 = 0;
  strcpy(v24, "AddNgcReader");
  v23[0] = v24;
  v23[1] = &v16;
  v23[2] = &v15;
  lambda_1df4b5a13cd76cbb13cdbd91888a67f5_::operator()(v23);
  v16 = 1;
  v22 = v23;
  v17 = 0;
  try
  {
    v2 = (CNgcReader *)operator new(0x378u);
    v23[3] = v2;
    if ( v2 )
      v5 = CNgcReader::CNgcReader(v2, a1);
    else
      v5 = 0;
    v17 = v5;
    if ( !v5 )
    {
      CalaisError(v3, 0x25Bu, (const unsigned __int16 *)a1, v4, v14);
      pExceptionObject = -2146435066;
      throw &pExceptionObject;
    }
    if ( (unsigned int)CReader::InitFailed(v5) )
    {
      CalaisError(v6, 0x263u, 0, v7, v14);
      v19 = -2146435066;
      throw &v19;
    }
    (*(void (__fastcall **)(CNgcReader *))(*(_QWORD *)v5 + 8LL))(v5);
    v11 = CalaisAddReader(v5, v8, v9, v10);
    if ( v11 )
    {
      v20 = v11;
      throw &v20;
    }
    v17 = 0;
  }
  catch ( ulong v21 )
  {
    v15 = v21;
  }
  catch ( ... )
  {
    v15 = -2146435052;
  }
  v12 = v15;
  WppTraceUnwinder__lambda_1df4b5a13cd76cbb13cdbd91888a67f5____::_WppTraceUnwinder__lambda_1df4b5a13cd76cbb13cdbd91888a67f5____(&v22);
  return v12;
}

```

## disassembly

```asm
0x18002bc50  mov     r11, rsp
0x18002bc53  mov     [r11+10h], rbx
0x18002bc57  push    rdi
0x18002bc58  sub     rsp, 90h
0x18002bc5f  mov     rax, cs:__security_cookie
0x18002bc66  xor     rax, rsp
0x18002bc69  mov     [rsp+98h+var_10], rax
0x18002bc71  mov     rdi, rcx
0x18002bc74  mov     [rsp+98h+var_68], 0
0x18002bc7c  mov     [rsp+98h+var_64], 0
0x18002bc84  movsd   xmm0, qword ptr cs:aAddngcreader; "AddNgcReader"
0x18002bc8c  movsd   qword ptr [rsp+98h+var_20], xmm0
0x18002bc92  mov     eax, dword ptr cs:aAddngcreader+8; "ader"
0x18002bc98  mov     [r11-18h], eax
0x18002bc9c  mov     al, byte ptr cs:aAddngcreader+0Ch; ""
0x18002bca2  mov     [r11-14h], al
0x18002bca6  lea     rax, [r11-20h]
0x18002bcaa  mov     [r11-40h], rax
0x18002bcae  lea     rax, [r11-64h]
0x18002bcb2  mov     [r11-38h], rax
0x18002bcb6  lea     rax, [r11-68h]
0x18002bcba  mov     [r11-30h], rax
0x18002bcbe  lea     rcx, [r11-40h]
0x18002bcc2  call    _lambda_1df4b5a13cd76cbb13cdbd91888a67f5___operator__
0x18002bcc7  mov     [rsp+98h+var_64], 1
0x18002bccf  lea     rax, [rsp+98h+var_40]
0x18002bcd4  mov     [rsp+98h+var_48], rax
0x18002bcd9  mov     [rsp+98h+var_60], 0
0x18002bce2  mov     ecx, 378h; Size
0x18002bce7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bcec  mov     [rsp+98h+var_28], rax
0x18002bcf1  test    rax, rax
0x18002bcf4  jz      short loc_18002BD06
0x18002bcf6  mov     rdx, rdi; unsigned __int16 *
0x18002bcf9  mov     rcx, rax; this
0x18002bcfc  call    ??0CNgcReader@@QEAA@PEBG@Z; CNgcReader::CNgcReader(ushort const *)
0x18002bd01  mov     rbx, rax
0x18002bd04  jmp     short loc_18002BD08
0x18002bd06  xor     ebx, ebx
0x18002bd08  mov     [rsp+98h+var_60], rbx
0x18002bd0d  test    rbx, rbx
0x18002bd10  jnz     short loc_18002BD38
0x18002bd12  mov     r8, rdi; unsigned __int16 *
0x18002bd15  mov     edx, 25Bh; unsigned int
0x18002bd1a  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x18002bd1f  mov     [rsp+98h+pExceptionObject], 80100006h
0x18002bd27  lea     rdx, _TI1K; pThrowInfo
0x18002bd2e  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18002bd33  call    _CxxThrowException_0
0x18002bd38  mov     rcx, rbx; this
0x18002bd3b  call    ?InitFailed@CReader@@QEAAHXZ; CReader::InitFailed(void)
0x18002bd40  test    eax, eax
0x18002bd42  jz      short loc_18002BD6A
0x18002bd44  xor     r8d, r8d; unsigned __int16 *
0x18002bd47  mov     edx, 263h; unsigned int
0x18002bd4c  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x18002bd51  mov     [rsp+98h+var_54], 80100006h
0x18002bd59  lea     rdx, _TI1K; pThrowInfo
0x18002bd60  lea     rcx, [rsp+98h+var_54]; pExceptionObject
0x18002bd65  call    _CxxThrowException_0
0x18002bd6a  mov     rax, [rbx]
0x18002bd6d  mov     rcx, rbx
0x18002bd70  mov     rax, [rax+8]
0x18002bd74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd79  mov     rcx, rbx; struct CReader *
0x18002bd7c  call    ?CalaisAddReader@@YAKPEAVCReader@@@Z; CalaisAddReader(CReader *)
0x18002bd81  test    eax, eax
0x18002bd83  jz      short loc_18002BD9A
0x18002bd85  mov     [rsp+98h+var_50], eax
0x18002bd89  lea     rdx, _TI1K; pThrowInfo
0x18002bd90  lea     rcx, [rsp+98h+var_50]; pExceptionObject
0x18002bd95  call    _CxxThrowException_0
0x18002bd9a  mov     [rsp+98h+var_60], 0
0x18002bda3  jmp     short loc_18002BDA7
0x18002bda5  jmp     short $+2
0x18002bda7  mov     ebx, [rsp+98h+var_68]
0x18002bdab  lea     rcx, [rsp+98h+var_48]
0x18002bdb0  call    WppTraceUnwinder__lambda_1df4b5a13cd76cbb13cdbd91888a67f5_______WppTraceUnwinder__lambda_1df4b5a13cd76cbb13cdbd91888a67f5____
0x18002bdb5  mov     eax, ebx
0x18002bdb7  mov     rcx, [rsp+98h+var_10]
0x18002bdbf  xor     rcx, rsp; StackCookie
0x18002bdc2  call    __security_check_cookie
0x18002bdc7  mov     rbx, [rsp+98h+arg_8]
0x18002bdcf  add     rsp, 90h
0x18002bdd6  pop     rdi
0x18002bdd7  retn
```
