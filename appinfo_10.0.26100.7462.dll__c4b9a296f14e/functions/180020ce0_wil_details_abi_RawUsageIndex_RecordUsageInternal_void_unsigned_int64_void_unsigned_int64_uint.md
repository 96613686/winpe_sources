# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180020ce0`
- end: `0x180020ecd`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `493`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180020bdc`

## callees

- `0x1800123a0`
- `0x1800192b4`
- `0x18001eaec`
- `0x18001ef94`
- `0x180020ce0`
- `0x180021d58`
- `0x1800226ec`
- `0x180022a08`

## import_xrefs

- `msvcrt!memmove_s` at `0x180020e50`
- `msvcrt!memmove_s` at `0x180020e50`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        unsigned __int64 a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  __int64 v6; // rdi
  unsigned __int8 *v11; // rdi
  char v12; // si
  int v13; // eax
  __int16 v15; // cx
  unsigned __int64 Size; // rax
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // r9
  __int64 v19; // r8
  __int64 v20; // r14
  unsigned __int8 *v21; // r8
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+30h] [rbp-50h] BYREF
  __int16 v23; // [rsp+38h] [rbp-48h] BYREF
  char v24; // [rsp+3Ah] [rbp-46h]
  int v25; // [rsp+3Ch] [rbp-44h]
  __int16 v26; // [rsp+40h] [rbp-40h]
  __int128 v27; // [rsp+48h] [rbp-38h]
  __int16 v28; // [rsp+58h] [rbp-28h] BYREF
  char v29; // [rsp+5Ah] [rbp-26h]
  unsigned int v30; // [rsp+5Ch] [rbp-24h]
  __int16 v31; // [rsp+60h] [rbp-20h]
  __int64 v32; // [rsp+68h] [rbp-18h]
  void *v33; // [rsp+70h] [rbp-10h]

  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v11 = (unsigned __int8 *)(v6 + 10);
    v23 = *((_WORD *)this + 1);
    v12 = 0;
    v24 = *((_BYTE *)this + 4);
    InsertionPointOrIncrement = v11;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    while ( 1 )
    {
      if ( !wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v23,
              &InsertionPointOrIncrement,
              *((unsigned __int8 **)this + 4)) )
      {
        v11 = InsertionPointOrIncrement;
        *((_QWORD *)this + 4) = InsertionPointOrIncrement;
        goto LABEL_14;
      }
      v13 = wil::details_abi::UsageIndexProperty::Compare((wil::details_abi::UsageIndexProperty *)&v23, a2, a3);
      if ( v13 < 0 )
      {
        InsertionPointOrIncrement = v11;
        goto LABEL_11;
      }
      if ( !v13 )
        break;
      v11 = wil::details_abi::RawUsageIndex::SkipValues(
              this,
              (struct wil::details_abi::UsageIndexProperty *)&v23,
              InsertionPointOrIncrement);
      InsertionPointOrIncrement = v11;
    }
    InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                  this,
                                  (struct wil::details_abi::UsageIndexProperty *)&v23,
                                  InsertionPointOrIncrement,
                                  a4,
                                  a5,
                                  a6);
    v11 = InsertionPointOrIncrement;
    if ( !InsertionPointOrIncrement )
      return 1;
    v12 = 1;
LABEL_11:
    if ( v12 )
      goto LABEL_15;
LABEL_14:
    *(_QWORD *)&v27 = 0;
    v25 = 1;
    v26 = a3;
    *((_QWORD *)&v27 + 1) = a2;
    wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v23);
LABEL_15:
    v15 = *((_WORD *)this + 3);
    v32 = 0;
    v28 = v15;
    v29 = *((_BYTE *)this + 8);
    v30 = a6;
    v31 = a5;
    v33 = a4;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v28);
    v17 = *((_QWORD *)this + 5);
    v18 = *((_QWORD *)this + 4);
    v20 = v19 + Size;
    if ( ((v17 - v18) & -(__int64)(v18 < v17)) >= v19 + Size )
    {
      memmove_s(&v11[v20], v17 - v20 - (_QWORD)v11, v11, v18 - (_QWORD)v11);
      v21 = (unsigned __int8 *)(v20 + *((_QWORD *)this + 4));
      *((_QWORD *)this + 4) = v21;
      if ( v12 )
      {
        if ( v24 )
          wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v23, v25 + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v23,
          &InsertionPointOrIncrement,
          v21);
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v28,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
      *((_BYTE *)this + 56) = 1;
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180020ce0  mov     [rsp-28h+arg_8], rbx
0x180020ce5  mov     [rsp-28h+arg_10], rsi
0x180020cea  mov     [rsp-28h+arg_18], rdi
0x180020cef  push    rbp
0x180020cf0  push    r12
0x180020cf2  push    r13
0x180020cf4  push    r14
0x180020cf6  push    r15
0x180020cf8  mov     rbp, rsp
0x180020cfb  sub     rsp, 80h
0x180020d02  mov     rdi, [rcx+18h]
0x180020d06  mov     rbx, rcx
0x180020d09  xor     ecx, ecx
0x180020d0b  mov     r12, r9
0x180020d0e  mov     r14, r8
0x180020d11  mov     r15, rdx
0x180020d14  test    rdi, rdi
0x180020d17  jz      loc_180020EA9
0x180020d1d  movzx   eax, word ptr [rbx+2]
0x180020d21  add     rdi, 0Ah
0x180020d25  mov     [rbp+var_48], ax
0x180020d29  xorps   xmm0, xmm0
0x180020d2c  mov     al, [rbx+4]
0x180020d2f  mov     sil, cl
0x180020d32  mov     [rbp+var_46], al
0x180020d35  mov     [rbp+var_50], rdi
0x180020d39  mov     [rbp+var_44], ecx
0x180020d3c  mov     [rbp+var_40], cx
0x180020d40  movdqu  [rbp+var_38], xmm0
0x180020d45  mov     r8, [rbx+20h]; unsigned __int8 *
0x180020d49  lea     rdx, [rbp+var_50]; unsigned __int8 **
0x180020d4d  lea     rcx, [rbp+var_48]; this
0x180020d51  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180020d56  mov     r13d, [rbp+arg_28]
0x180020d5a  test    al, al
0x180020d5c  jz      short loc_180020DCB
0x180020d5e  mov     r8, r14; unsigned __int64
0x180020d61  lea     rcx, [rbp+var_48]; this
0x180020d65  mov     rdx, r15; void *
0x180020d68  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180020d6d  test    eax, eax
0x180020d6f  js      short loc_180020DBD
0x180020d71  mov     r8, [rbp+var_50]; unsigned __int8 *
0x180020d75  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180020d79  jz      short loc_180020D8C
0x180020d7b  mov     rcx, rbx; this
0x180020d7e  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180020d83  mov     rdi, rax
0x180020d86  mov     [rbp+var_50], rax
0x180020d8a  jmp     short loc_180020D45
0x180020d8c  mov     rcx, [rbp+arg_20]
0x180020d90  mov     r9, r12; void *
0x180020d93  mov     [rsp+80h+var_58], r13d; unsigned int
0x180020d98  mov     [rsp+80h+var_60], rcx; unsigned __int64
0x180020d9d  mov     rcx, rbx; this
0x180020da0  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180020da5  mov     [rbp+var_50], rax
0x180020da9  mov     rdi, rax
0x180020dac  test    rax, rax
0x180020daf  jnz     short loc_180020DB8
0x180020db1  mov     al, 1
0x180020db3  jmp     loc_180020EAB
0x180020db8  mov     sil, 1
0x180020dbb  jmp     short loc_180020DC1
0x180020dbd  mov     [rbp+var_50], rdi
0x180020dc1  xor     r8d, r8d
0x180020dc4  test    sil, sil
0x180020dc7  jnz     short loc_180020DF4
0x180020dc9  jmp     short loc_180020DD3
0x180020dcb  mov     rdi, [rbp+var_50]
0x180020dcf  mov     [rbx+20h], rdi
0x180020dd3  and     qword ptr [rbp+var_38], 0
0x180020dd8  lea     rcx, [rbp+var_48]; this
0x180020ddc  mov     [rbp+var_44], 1
0x180020de3  mov     [rbp+var_40], r14w
0x180020de8  mov     qword ptr [rbp+var_38+8], r15
0x180020dec  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180020df1  mov     r8, rax
0x180020df4  movzx   ecx, word ptr [rbx+6]
0x180020df8  mov     rax, [rbp+arg_20]
0x180020dfc  and     [rbp+var_18], 0
0x180020e01  mov     [rbp+var_28], cx
0x180020e05  mov     cl, [rbx+8]
0x180020e08  mov     [rbp+var_26], cl
0x180020e0b  lea     rcx, [rbp+var_28]; this
0x180020e0f  mov     [rbp+var_24], r13d
0x180020e13  mov     [rbp+var_20], ax
0x180020e17  mov     [rbp+var_10], r12
0x180020e1b  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180020e20  mov     rdx, [rbx+28h]
0x180020e24  mov     r9, [rbx+20h]
0x180020e28  mov     r10, rdx
0x180020e2b  sub     r10, r9
0x180020e2e  cmp     r9, rdx
0x180020e31  lea     r14, [r8+rax]
0x180020e35  sbb     rcx, rcx
0x180020e38  and     rcx, r10
0x180020e3b  cmp     rcx, r14
0x180020e3e  jb      short loc_180020EA9
0x180020e40  sub     rdx, r14
0x180020e43  lea     rcx, [r14+rdi]; Destination
0x180020e47  sub     rdx, rdi; DestinationSize
0x180020e4a  sub     r9, rdi; SourceSize
0x180020e4d  mov     r8, rdi; Source
0x180020e50  call    cs:__imp_memmove_s
0x180020e57  nop     dword ptr [rax+rax+00h]
0x180020e5c  mov     r8, [rbx+20h]
0x180020e60  add     r8, r14; unsigned __int8 *
0x180020e63  mov     [rbx+20h], r8
0x180020e67  test    sil, sil
0x180020e6a  jnz     short loc_180020E7B
0x180020e6c  lea     rdx, [rbp+var_50]; unsigned __int8 **
0x180020e70  lea     rcx, [rbp+var_48]; this
0x180020e74  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180020e79  jmp     short loc_180020E8F
0x180020e7b  cmp     [rbp+var_46], 0
0x180020e7f  jz      short loc_180020E8F
0x180020e81  mov     edx, [rbp+var_44]
0x180020e84  lea     rcx, [rbp+var_48]; this
0x180020e88  inc     edx; unsigned int
0x180020e8a  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180020e8f  mov     r8, [rbx+20h]; unsigned __int8 *
0x180020e93  lea     rdx, [rbp+var_50]; unsigned __int8 **
0x180020e97  lea     rcx, [rbp+var_28]; this
0x180020e9b  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180020ea0  mov     byte ptr [rbx+38h], 1
0x180020ea4  jmp     loc_180020DB1
0x180020ea9  xor     al, al
0x180020eab  lea     r11, [rsp+80h+var_s0]
0x180020eb3  mov     rbx, [r11+38h]
0x180020eb7  mov     rsi, [r11+40h]
0x180020ebb  mov     rdi, [r11+48h]
0x180020ebf  mov     rsp, r11
0x180020ec2  pop     r15
0x180020ec4  pop     r14
0x180020ec6  pop     r13
0x180020ec8  pop     r12
0x180020eca  pop     rbp
0x180020ecb  retn
```
