# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180004c5c`
- end: `0x180004eaa`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `590`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004b60`
- `0x1800095a8`

## callees

- `0x180004c5c`
- `0x180004eb0`
- `0x180008784`
- `0x1800087d4`
- `0x180008ea0`
- `0x18000c80c`
- `0x18000d2b6`

## import_xrefs

- `msvcrt!memmove_s` at `0x180004e09`
- `msvcrt!memmove_s` at `0x180004e09`
- `msvcrt!memcpy_s` at `0x180004e6d`
- `msvcrt!memcpy_s` at `0x180004e6d`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        size_t a3,
        void *a4,
        size_t a5,
        unsigned int a6)
{
  __int64 v6; // rdi
  unsigned __int8 *v10; // rdi
  char v11; // r14
  bool v12; // al
  unsigned int v13; // r12d
  __int64 v14; // r9
  size_t Size; // r15
  int v16; // ecx
  unsigned __int8 *InsertionPointOrIncrement; // rax
  unsigned __int64 v19; // r8
  __int64 v20; // rdx
  char v21; // cl
  __int64 v22; // rax
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rsi
  unsigned __int64 v25; // r9
  __int16 v26; // r8
  rsize_t v27; // r9
  int *p_Source; // r8
  rsize_t v29; // rdx
  unsigned __int8 *v30; // [rsp+30h] [rbp-50h] BYREF
  __int16 v31; // [rsp+38h] [rbp-48h] BYREF
  char v32; // [rsp+3Ah] [rbp-46h]
  int Source; // [rsp+3Ch] [rbp-44h] BYREF
  unsigned __int16 v34; // [rsp+40h] [rbp-40h]
  void *Buf2[2]; // [rsp+48h] [rbp-38h]
  __int16 v36; // [rsp+58h] [rbp-28h] BYREF
  char v37; // [rsp+5Ah] [rbp-26h]
  unsigned int v38; // [rsp+5Ch] [rbp-24h]
  __int16 v39; // [rsp+60h] [rbp-20h]
  __int64 v40; // [rsp+68h] [rbp-18h]
  void *v41; // [rsp+70h] [rbp-10h]
  __int16 v42; // [rsp+C0h] [rbp+40h] BYREF
  void *Buf1; // [rsp+C8h] [rbp+48h]

  Buf1 = a2;
  v6 = *((_QWORD *)this + 3);
  if ( !v6 )
    return 0;
  v10 = (unsigned __int8 *)(v6 + 10);
  v31 = *((_WORD *)this + 1);
  v11 = 0;
  v32 = *((_BYTE *)this + 4);
  v30 = v10;
  Source = 0;
  v34 = 0;
  *(_OWORD *)Buf2 = 0;
  while ( 1 )
  {
    v12 = wil::details_abi::UsageIndexProperty::Read(
            (wil::details_abi::UsageIndexProperty *)&v31,
            &v30,
            *((unsigned __int8 **)this + 4));
    v13 = a6;
    v14 = 0;
    Size = a5;
    if ( !v12 )
    {
      v10 = v30;
      *((_QWORD *)this + 4) = v30;
LABEL_17:
      Buf2[1] = Buf1;
      Source = 1;
      v34 = a3;
      Buf2[0] = 0;
      v19 = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v31);
      goto LABEL_18;
    }
    if ( a3 == v34 )
    {
      v16 = memcmp_0(Buf1, Buf2[1], a3);
      v14 = 0;
    }
    else
    {
      v16 = a3 - v34;
    }
    if ( v16 < 0 )
      break;
    if ( !v16 )
    {
      InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                    this,
                                    (struct wil::details_abi::UsageIndexProperty *)&v31,
                                    v30,
                                    a4,
                                    Size,
                                    v13);
      v14 = 0;
      v30 = InsertionPointOrIncrement;
      v10 = InsertionPointOrIncrement;
      if ( InsertionPointOrIncrement )
      {
        v11 = 1;
        goto LABEL_14;
      }
      return 1;
    }
    v10 = wil::details_abi::RawUsageIndex::SkipValues(this, (struct wil::details_abi::UsageIndexProperty *)&v31, v30);
    v30 = v10;
  }
  v30 = v10;
LABEL_14:
  v19 = 0;
  if ( !v11 )
    goto LABEL_17;
LABEL_18:
  v20 = *((unsigned __int16 *)this + 3);
  v21 = *((_BYTE *)this + 8);
  v38 = v13;
  v36 = v20;
  v37 = v21;
  v39 = Size;
  v40 = v14;
  v41 = a4;
  if ( (_WORD)v20 )
    v22 = v20;
  else
    v22 = (unsigned __int16)Size + 2LL;
  if ( v21 == 1 )
  {
    v22 += 2;
  }
  else if ( v21 == 2 )
  {
    v22 += 4;
  }
  v23 = *((_QWORD *)this + 5);
  v24 = v22 + v19;
  v25 = *((_QWORD *)this + 4);
  if ( ((v23 - v25) & -(__int64)(v25 < v23)) >= v22 + v19 )
  {
    memmove_s(&v10[v24], v23 - v24 - (_QWORD)v10, v10, v25 - (_QWORD)v10);
    *((_QWORD *)this + 4) += v24;
    if ( !v11 )
    {
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v31,
        &v30,
        *((unsigned __int8 **)this + 4));
      goto LABEL_35;
    }
    if ( v32 )
    {
      v26 = Source + 1;
      if ( Source != Source + 1 )
      {
        ++Source;
        if ( v32 == 1 )
        {
          v42 = v26;
          v27 = 2;
          p_Source = (int *)&v42;
          v29 = 2;
          goto LABEL_34;
        }
        if ( v32 == 2 )
        {
          v29 = 4;
          p_Source = &Source;
          v27 = 4;
LABEL_34:
          memcpy_s(Buf2[0], v29, p_Source, v27);
        }
      }
    }
LABEL_35:
    wil::details_abi::UsageIndexProperty::Write(
      (wil::details_abi::UsageIndexProperty *)&v36,
      &v30,
      *((unsigned __int8 **)this + 4));
    *((_BYTE *)this + 56) = 1;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180004c5c  mov     [rsp-38h+arg_10], rbx
0x180004c61  mov     [rsp-38h+Buf1], rdx
0x180004c66  push    rbp
0x180004c67  push    rsi
0x180004c68  push    rdi
0x180004c69  push    r12
0x180004c6b  push    r13
0x180004c6d  push    r14
0x180004c6f  push    r15
0x180004c71  mov     rbp, rsp
0x180004c74  sub     rsp, 80h
0x180004c7b  mov     rdi, [rcx+18h]
0x180004c7f  mov     rbx, rcx
0x180004c82  xor     ecx, ecx
0x180004c84  mov     r13, r9
0x180004c87  mov     rsi, r8
0x180004c8a  test    rdi, rdi
0x180004c8d  jz      loc_180004E8D
0x180004c93  movzx   eax, word ptr [rbx+2]
0x180004c97  add     rdi, 0Ah
0x180004c9b  mov     [rbp+var_48], ax
0x180004c9f  xorps   xmm0, xmm0
0x180004ca2  mov     al, [rbx+4]
0x180004ca5  mov     r14b, cl
0x180004ca8  mov     [rbp+var_46], al
0x180004cab  mov     [rbp+var_50], rdi
0x180004caf  mov     [rbp+Source], ecx
0x180004cb2  mov     [rbp+var_40], cx
0x180004cb6  movdqu  xmmword ptr [rbp+Buf2], xmm0
0x180004cbb  mov     r8, [rbx+20h]; unsigned __int8 *
0x180004cbf  lea     rdx, [rbp+var_50]; unsigned __int8 **
0x180004cc3  lea     rcx, [rbp+var_48]; this
0x180004cc7  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180004ccc  mov     r12d, [rbp+arg_28]
0x180004cd0  xor     r9d, r9d
0x180004cd3  mov     r15, [rbp+arg_20]
0x180004cd7  test    al, al
0x180004cd9  jz      loc_180004D61
0x180004cdf  movzx   eax, [rbp+var_40]
0x180004ce3  cmp     rsi, rax
0x180004ce6  jnz     short loc_180004CFF
0x180004ce8  mov     rdx, [rbp+Buf2+8]; Buf2
0x180004cec  mov     r8, rsi; Size
0x180004cef  mov     rcx, [rbp+Buf1]; Buf1
0x180004cf3  call    memcmp_0
0x180004cf8  mov     ecx, eax
0x180004cfa  xor     r9d, r9d
0x180004cfd  jmp     short loc_180004D07
0x180004cff  movzx   eax, [rbp+var_40]
0x180004d03  mov     ecx, esi
0x180004d05  sub     ecx, eax
0x180004d07  test    ecx, ecx
0x180004d09  js      short loc_180004D53
0x180004d0b  mov     r8, [rbp+var_50]; unsigned __int8 *
0x180004d0f  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180004d13  mov     rcx, rbx; this
0x180004d16  jz      short loc_180004D26
0x180004d18  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180004d1d  mov     rdi, rax
0x180004d20  mov     [rbp+var_50], rax
0x180004d24  jmp     short loc_180004CBB
0x180004d26  mov     [rsp+80h+var_58], r12d; unsigned int
0x180004d2b  mov     r9, r13; void *
0x180004d2e  mov     [rsp+80h+Size], r15; Size
0x180004d33  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180004d38  xor     r9d, r9d
0x180004d3b  mov     [rbp+var_50], rax
0x180004d3f  mov     rdi, rax
0x180004d42  test    rax, rax
0x180004d45  jnz     short loc_180004D4E
0x180004d47  mov     al, 1
0x180004d49  jmp     loc_180004E8F
0x180004d4e  mov     r14b, 1
0x180004d51  jmp     short loc_180004D57
0x180004d53  mov     [rbp+var_50], rdi
0x180004d57  mov     r8, r9
0x180004d5a  test    r14b, r14b
0x180004d5d  jz      short loc_180004D69
0x180004d5f  jmp     short loc_180004D8C
0x180004d61  mov     rdi, [rbp+var_50]
0x180004d65  mov     [rbx+20h], rdi
0x180004d69  mov     rax, [rbp+Buf1]
0x180004d6d  lea     rcx, [rbp+var_48]; this
0x180004d71  mov     [rbp+Buf2+8], rax
0x180004d75  mov     [rbp+Source], 1
0x180004d7c  mov     [rbp+var_40], si
0x180004d80  mov     [rbp+Buf2], r9
0x180004d84  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180004d89  mov     r8, rax
0x180004d8c  movzx   edx, word ptr [rbx+6]
0x180004d90  mov     cl, [rbx+8]
0x180004d93  mov     [rbp+var_24], r12d
0x180004d97  mov     r12d, 2
0x180004d9d  mov     [rbp+var_28], dx
0x180004da1  mov     [rbp+var_26], cl
0x180004da4  mov     [rbp+var_20], r15w
0x180004da9  mov     [rbp+var_18], r9
0x180004dad  mov     [rbp+var_10], r13
0x180004db1  test    dx, dx
0x180004db4  jnz     short loc_180004DBF
0x180004db6  movzx   eax, r15w
0x180004dba  add     rax, r12
0x180004dbd  jmp     short loc_180004DC2
0x180004dbf  mov     rax, rdx
0x180004dc2  cmp     cl, 1
0x180004dc5  jnz     short loc_180004DCC
0x180004dc7  add     rax, r12
0x180004dca  jmp     short loc_180004DD5
0x180004dcc  cmp     cl, r12b
0x180004dcf  jnz     short loc_180004DD5
0x180004dd1  add     rax, 4
0x180004dd5  mov     rdx, [rbx+28h]
0x180004dd9  lea     rsi, [rax+r8]
0x180004ddd  mov     r9, [rbx+20h]
0x180004de1  mov     rcx, rdx
0x180004de4  sub     rcx, r9
0x180004de7  cmp     r9, rdx
0x180004dea  sbb     rax, rax
0x180004ded  and     rax, rcx
0x180004df0  cmp     rax, rsi
0x180004df3  jb      loc_180004E8D
0x180004df9  sub     rdx, rsi
0x180004dfc  lea     rcx, [rsi+rdi]; Destination
0x180004e00  sub     rdx, rdi; DestinationSize
0x180004e03  sub     r9, rdi; SourceSize
0x180004e06  mov     r8, rdi; Source
0x180004e09  call    cs:__imp_memmove_s
0x180004e0f  add     [rbx+20h], rsi
0x180004e13  test    r14b, r14b
0x180004e16  jnz     short loc_180004E2B
0x180004e18  mov     r8, [rbx+20h]; unsigned __int8 *
0x180004e1c  lea     rdx, [rbp+var_50]; unsigned __int8 **
0x180004e20  lea     rcx, [rbp+var_48]; this
0x180004e24  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180004e29  jmp     short loc_180004E73
0x180004e2b  mov     cl, [rbp+var_46]
0x180004e2e  test    cl, cl
0x180004e30  jz      short loc_180004E73
0x180004e32  mov     eax, [rbp+Source]
0x180004e35  lea     r8d, [rax+1]
0x180004e39  cmp     eax, r8d
0x180004e3c  jz      short loc_180004E73
0x180004e3e  mov     [rbp+Source], r8d
0x180004e42  cmp     cl, 1
0x180004e45  jnz     short loc_180004E58
0x180004e47  mov     [rbp+arg_0], r8w
0x180004e4c  mov     r9, r12
0x180004e4f  lea     r8, [rbp+arg_0]
0x180004e53  mov     rdx, r12
0x180004e56  jmp     short loc_180004E69
0x180004e58  cmp     cl, r12b
0x180004e5b  jnz     short loc_180004E73
0x180004e5d  mov     edx, 4; DestinationSize
0x180004e62  lea     r8, [rbp+Source]; Source
0x180004e66  mov     r9d, edx; SourceSize
0x180004e69  mov     rcx, [rbp+Buf2]; Destination
0x180004e6d  call    cs:__imp_memcpy_s
0x180004e73  mov     r8, [rbx+20h]; unsigned __int8 *
0x180004e77  lea     rdx, [rbp+var_50]; unsigned __int8 **
0x180004e7b  lea     rcx, [rbp+var_28]; this
0x180004e7f  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180004e84  mov     byte ptr [rbx+38h], 1
0x180004e88  jmp     loc_180004D47
0x180004e8d  xor     al, al
0x180004e8f  mov     rbx, [rsp+80h+arg_10]
0x180004e97  add     rsp, 80h
0x180004e9e  pop     r15
0x180004ea0  pop     r14
0x180004ea2  pop     r13
0x180004ea4  pop     r12
0x180004ea6  pop     rdi
0x180004ea7  pop     rsi
0x180004ea8  pop     rbp
0x180004ea9  retn
```
