# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180056650`
- end: `0x18005683b`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `491`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, size_t, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005655c`

## callees

- `0x180053418`
- `0x180053974`
- `0x180054758`
- `0x180056008`
- `0x180056650`
- `0x1800573b4`
- `0x180057984`
- `0x180057d4c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180056792`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180056792`

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
  char *v11; // rdi
  unsigned __int8 *v12; // r8
  char v13; // r14
  int v14; // eax
  unsigned __int8 *v15; // rax
  char v17; // cl
  __int64 Size; // rax
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // rsi
  const void *v24; // [rsp+30h] [rbp-48h] BYREF
  __int16 v25; // [rsp+38h] [rbp-40h]
  __int128 v26; // [rsp+40h] [rbp-38h]
  __int16 v27; // [rsp+50h] [rbp-28h] BYREF
  char v28; // [rsp+52h] [rbp-26h]
  unsigned int v29; // [rsp+54h] [rbp-24h]
  __int16 v30; // [rsp+58h] [rbp-20h]
  __int64 v31; // [rsp+60h] [rbp-18h]
  void *v32; // [rsp+68h] [rbp-10h]
  void *Source; // [rsp+C0h] [rbp+48h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v11 = (char *)(v6 + 10);
    v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
    LOWORD(v24) = *((_WORD *)this + 1);
    BYTE2(v24) = *((_BYTE *)this + 4);
    v25 = 0;
    v13 = 0;
    Source = v11;
    HIDWORD(v24) = 0;
    v26 = 0;
    while ( 1 )
    {
      if ( !wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v24,
              (unsigned __int8 **)&Source,
              v12) )
      {
        v11 = (char *)Source;
        *((_QWORD *)this + 4) = Source;
        goto LABEL_8;
      }
      v14 = wil::details_abi::UsageIndexProperty::Compare(&v24, a2, a3);
      if ( v14 < 0 )
      {
        Source = v11;
        goto LABEL_8;
      }
      if ( !v14 )
        break;
      v15 = wil::details_abi::RawUsageIndex::SkipValues(
              this,
              (struct wil::details_abi::UsageIndexProperty *)&v24,
              (unsigned __int8 *)Source);
      v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
      v11 = (char *)v15;
      Source = v15;
    }
    Source = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
               this,
               (struct wil::details_abi::UsageIndexProperty *)&v24,
               (unsigned __int8 *)Source,
               a4,
               a5,
               a6);
    v11 = (char *)Source;
    if ( !Source )
      return 1;
    v13 = 1;
LABEL_8:
    if ( !v13 )
    {
      HIDWORD(v24) = 1;
      v25 = a3;
      *(_QWORD *)&v26 = 0;
      *((_QWORD *)&v26 + 1) = a2;
      wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v24);
    }
    v27 = *((_WORD *)this + 3);
    v17 = *((_BYTE *)this + 8);
    v29 = a6;
    v28 = v17;
    v30 = a5;
    v31 = 0;
    v32 = a4;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v27);
    v19 = *((_QWORD *)this + 5);
    v20 = *((_QWORD *)this + 4);
    v22 = Size + v21;
    if ( ((v19 - v20) & -(__int64)(v20 < v19)) >= Size + v21 )
    {
      memmove_s(&v11[v22], v19 - v22 - (_QWORD)v11, v11, v20 - (_QWORD)v11);
      *((_QWORD *)this + 4) += v22;
      if ( v13 )
      {
        if ( BYTE2(v24) )
          wil::details_abi::UsageIndexProperty::UpdateCount(
            (wil::details_abi::UsageIndexProperty *)&v24,
            HIDWORD(v24) + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v24,
          (char **)&Source,
          *((char **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v27,
        (char **)&Source,
        *((char **)this + 4));
      *((_BYTE *)this + 56) = 1;
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180056650  push    rbp
0x180056652  push    rbx
0x180056653  push    rsi
0x180056654  push    rdi
0x180056655  push    r12
0x180056657  push    r13
0x180056659  push    r14
0x18005665b  push    r15
0x18005665d  mov     rbp, rsp
0x180056660  sub     rsp, 78h
0x180056664  mov     rdi, [rcx+18h]
0x180056668  mov     r13, r9
0x18005666b  mov     r15, r8
0x18005666e  mov     r12, rdx
0x180056671  mov     rbx, rcx
0x180056674  test    rdi, rdi
0x180056677  jz      loc_180056827
0x18005667d  movzx   eax, word ptr [rcx+2]
0x180056681  add     rdi, 0Ah
0x180056685  mov     r8, [rcx+20h]
0x180056689  xorps   xmm0, xmm0
0x18005668c  mov     [rbp+var_48], ax
0x180056690  mov     al, [rcx+4]
0x180056693  mov     [rbp+var_46], al
0x180056696  xor     eax, eax
0x180056698  mov     [rbp+var_40], ax
0x18005669c  xor     r14b, r14b
0x18005669f  mov     [rbp+Source], rdi
0x1800566a3  mov     [rbp+var_44], 0
0x1800566aa  movdqu  [rbp+var_38], xmm0
0x1800566af  jmp     short loc_1800566E9
0x1800566b1  mov     r8, r15; unsigned __int64
0x1800566b4  lea     rcx, [rbp+var_48]; this
0x1800566b8  mov     rdx, r12; void *
0x1800566bb  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x1800566c0  test    eax, eax
0x1800566c2  js      loc_1800567EA
0x1800566c8  mov     r8, [rbp+Source]; unsigned __int8 *
0x1800566cc  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x1800566d0  jz      loc_1800567BA
0x1800566d6  mov     rcx, rbx; this
0x1800566d9  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800566de  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800566e2  mov     rdi, rax
0x1800566e5  mov     [rbp+Source], rax
0x1800566e9  lea     rdx, [rbp+Source]; unsigned __int8 **
0x1800566ed  lea     rcx, [rbp+var_48]; this
0x1800566f1  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800566f6  mov     sil, al
0x1800566f9  test    al, al
0x1800566fb  jnz     short loc_1800566B1
0x1800566fd  mov     rdi, [rbp+Source]
0x180056701  mov     [rbx+20h], rdi
0x180056705  xor     r8d, r8d
0x180056708  test    r14b, r14b
0x18005670b  jnz     short loc_18005672D
0x18005670d  lea     rcx, [rbp+var_48]; this
0x180056711  mov     [rbp+var_44], 1
0x180056718  mov     [rbp+var_40], r15w
0x18005671d  mov     qword ptr [rbp+var_38], r8
0x180056721  mov     qword ptr [rbp+var_38+8], r12
0x180056725  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18005672a  mov     r8, rax
0x18005672d  movzx   ecx, word ptr [rbx+6]
0x180056731  mov     eax, [rbp+arg_28]
0x180056734  mov     [rbp+var_28], cx
0x180056738  mov     cl, [rbx+8]
0x18005673b  mov     [rbp+var_24], eax
0x18005673e  mov     rax, [rbp+arg_20]
0x180056742  mov     [rbp+var_26], cl
0x180056745  lea     rcx, [rbp+var_28]; this
0x180056749  mov     [rbp+var_20], ax
0x18005674d  mov     [rbp+var_18], 0
0x180056755  mov     [rbp+var_10], r13
0x180056759  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18005675e  mov     rdx, [rbx+28h]
0x180056762  mov     r9, [rbx+20h]
0x180056766  mov     rcx, rdx
0x180056769  sub     rcx, r9
0x18005676c  lea     rsi, [rax+r8]
0x180056770  cmp     r9, rdx
0x180056773  sbb     rax, rax
0x180056776  and     rax, rcx
0x180056779  cmp     rax, rsi
0x18005677c  jb      loc_180056827
0x180056782  sub     rdx, rsi
0x180056785  lea     rcx, [rsi+rdi]; Destination
0x180056789  sub     rdx, rdi; DestinationSize
0x18005678c  sub     r9, rdi; SourceSize
0x18005678f  mov     r8, rdi; Source
0x180056792  call    cs:__imp_memmove_s
0x180056799  nop     dword ptr [rax+rax+00h]
0x18005679e  add     [rbx+20h], rsi
0x1800567a2  test    r14b, r14b
0x1800567a5  jnz     short loc_1800567FC
0x1800567a7  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800567ab  lea     rdx, [rbp+Source]; unsigned __int8 **
0x1800567af  lea     rcx, [rbp+var_48]; this
0x1800567b3  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800567b8  jmp     short loc_180056810
0x1800567ba  mov     ecx, [rbp+arg_28]
0x1800567bd  mov     r9, r13; void *
0x1800567c0  mov     [rsp+78h+var_50], ecx; unsigned int
0x1800567c4  mov     rcx, [rbp+arg_20]
0x1800567c8  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x1800567cd  mov     rcx, rbx; this
0x1800567d0  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800567d5  mov     [rbp+Source], rax
0x1800567d9  mov     rdi, rax
0x1800567dc  test    rax, rax
0x1800567df  jnz     short loc_1800567E5
0x1800567e1  mov     al, 1
0x1800567e3  jmp     short loc_180056829
0x1800567e5  mov     r14b, 1
0x1800567e8  jmp     short loc_1800567EE
0x1800567ea  mov     [rbp+Source], rdi
0x1800567ee  test    sil, sil
0x1800567f1  jnz     loc_180056705
0x1800567f7  jmp     loc_180056701
0x1800567fc  cmp     [rbp+var_46], 0
0x180056800  jz      short loc_180056810
0x180056802  mov     edx, [rbp+var_44]
0x180056805  lea     rcx, [rbp+var_48]; this
0x180056809  inc     edx; unsigned int
0x18005680b  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180056810  mov     r8, [rbx+20h]; unsigned __int8 *
0x180056814  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180056818  lea     rcx, [rbp+var_28]; this
0x18005681c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180056821  mov     byte ptr [rbx+38h], 1
0x180056825  jmp     short loc_1800567E1
0x180056827  xor     al, al
0x180056829  add     rsp, 78h
0x18005682d  pop     r15
0x18005682f  pop     r14
0x180056831  pop     r13
0x180056833  pop     r12
0x180056835  pop     rdi
0x180056836  pop     rsi
0x180056837  pop     rbx
0x180056838  pop     rbp
0x180056839  retn
```
