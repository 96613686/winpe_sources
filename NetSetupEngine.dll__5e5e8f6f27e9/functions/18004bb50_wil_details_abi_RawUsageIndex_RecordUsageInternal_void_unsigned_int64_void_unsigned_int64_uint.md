# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18004bb50`
- end: `0x18004bd99`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `585`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18004ba40`

## callees

- `0x18004bb50`
- `0x18004bda0`
- `0x18004beac`
- `0x18004c3d4`
- `0x180054bfc`
- `0x180070280`
- `0x180081096`
- `0x1800810d0`

## import_xrefs

- `msvcrt!memmove_s` at `0x18004bd1f`
- `msvcrt!memmove_s` at `0x18004bd1f`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *Buf1,
        size_t Size,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  __int64 v6; // rdi
  unsigned __int8 *v11; // rdi
  char v12; // r14
  int v13; // ecx
  __int64 v15; // rcx
  __int64 v16; // rax
  char v17; // dl
  unsigned __int64 v18; // rdx
  __int64 v19; // rsi
  unsigned __int64 v20; // r9
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v22; // [rsp+38h] [rbp-41h]
  unsigned __int16 v23; // [rsp+40h] [rbp-39h] BYREF
  char v24; // [rsp+42h] [rbp-37h]
  int v25; // [rsp+44h] [rbp-35h]
  unsigned __int16 v26; // [rsp+48h] [rbp-31h]
  void *Buf2[2]; // [rsp+50h] [rbp-29h]
  __int16 v28; // [rsp+60h] [rbp-19h] BYREF
  char v29; // [rsp+62h] [rbp-17h]
  unsigned int v30; // [rsp+64h] [rbp-15h]
  __int16 v31; // [rsp+68h] [rbp-11h]
  __int64 v32; // [rsp+70h] [rbp-9h]
  void *v33; // [rsp+78h] [rbp-1h]

  v6 = *((_QWORD *)this + 3);
  v22 = a6;
  if ( v6 )
  {
    v11 = (unsigned __int8 *)(v6 + 10);
    v23 = *((_WORD *)this + 1);
    v12 = 0;
    v24 = *((_BYTE *)this + 4);
    InsertionPointOrIncrement = v11;
    v25 = 0;
    v26 = 0;
    *(_OWORD *)Buf2 = 0;
    while ( 1 )
    {
      if ( !wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v23,
              &InsertionPointOrIncrement,
              *((unsigned __int8 **)this + 4)) )
      {
        v11 = InsertionPointOrIncrement;
        *((_QWORD *)this + 4) = InsertionPointOrIncrement;
        goto LABEL_17;
      }
      v13 = Size == v26 ? memcmp_0(Buf1, Buf2[1], Size) : Size - v26;
      if ( v13 < 0 )
        break;
      if ( !v13 )
      {
        InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                      this,
                                      (struct wil::details_abi::UsageIndexProperty *)&v23,
                                      InsertionPointOrIncrement,
                                      a4,
                                      a5,
                                      v22);
        v11 = InsertionPointOrIncrement;
        if ( InsertionPointOrIncrement )
        {
          v12 = 1;
          goto LABEL_14;
        }
        return 1;
      }
      v11 = wil::details_abi::RawUsageIndex::SkipValues(
              this,
              (struct wil::details_abi::UsageIndexProperty *)&v23,
              InsertionPointOrIncrement);
      InsertionPointOrIncrement = v11;
    }
    InsertionPointOrIncrement = v11;
LABEL_14:
    v15 = 0;
    if ( !v12 )
    {
LABEL_17:
      v25 = 1;
      v26 = Size;
      Buf2[0] = 0;
      Buf2[1] = Buf1;
      if ( v23 )
        v15 = v23;
      else
        v15 = (unsigned __int16)Size + 2LL;
      if ( v24 == 1 )
      {
        v15 += 2;
      }
      else if ( v24 == 2 )
      {
        v15 += 4;
      }
    }
    v16 = *((unsigned __int16 *)this + 3);
    v17 = *((_BYTE *)this + 8);
    v28 = v16;
    v29 = v17;
    v30 = v22;
    v31 = a5;
    v32 = 0;
    v33 = a4;
    if ( !(_WORD)v16 )
      v16 = (unsigned __int16)a5 + 2LL;
    if ( v17 == 1 )
    {
      v16 += 2;
    }
    else if ( v17 == 2 )
    {
      v16 += 4;
    }
    v18 = *((_QWORD *)this + 5);
    v19 = v16 + v15;
    v20 = *((_QWORD *)this + 4);
    if ( ((v18 - v20) & -(__int64)(v20 < v18)) >= v16 + v15 )
    {
      memmove_s(&v11[v19], v18 - v19 - (_QWORD)v11, v11, v20 - (_QWORD)v11);
      *((_QWORD *)this + 4) += v19;
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
          *((unsigned __int8 **)this + 4));
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
0x18004bb50  mov     [rsp-8+arg_8], rbx
0x18004bb55  push    rbp
0x18004bb56  push    rsi
0x18004bb57  push    rdi
0x18004bb58  push    r12
0x18004bb5a  push    r13
0x18004bb5c  push    r14
0x18004bb5e  push    r15
0x18004bb60  lea     rbp, [rsp-17h]
0x18004bb65  sub     rsp, 90h
0x18004bb6c  mov     rax, cs:__security_cookie
0x18004bb73  xor     rax, rsp
0x18004bb76  mov     [rbp+47h+var_40], rax
0x18004bb7a  mov     rdi, [rcx+18h]
0x18004bb7e  mov     rbx, rcx
0x18004bb81  mov     eax, [rbp+47h+arg_28]
0x18004bb84  xor     ecx, ecx
0x18004bb86  mov     r12, [rbp+47h+arg_20]
0x18004bb8a  mov     r13, r9
0x18004bb8d  mov     [rbp+47h+var_88], eax
0x18004bb90  mov     rsi, r8
0x18004bb93  mov     r15, rdx
0x18004bb96  test    rdi, rdi
0x18004bb99  jz      loc_18004BD70
0x18004bb9f  movzx   eax, word ptr [rbx+2]
0x18004bba3  add     rdi, 0Ah
0x18004bba7  mov     [rbp+47h+var_80], ax
0x18004bbab  xorps   xmm0, xmm0
0x18004bbae  mov     al, [rbx+4]
0x18004bbb1  mov     r14b, cl
0x18004bbb4  mov     [rbp+47h+var_7E], al
0x18004bbb7  mov     [rbp+47h+var_90], rdi
0x18004bbbb  mov     [rbp+47h+var_7C], ecx
0x18004bbbe  mov     [rbp+47h+var_78], cx
0x18004bbc2  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18004bbc7  mov     r8, [rbx+20h]; unsigned __int8 *
0x18004bbcb  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18004bbcf  lea     rcx, [rbp+47h+var_80]; this
0x18004bbd3  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18004bbd8  xor     r9d, r9d
0x18004bbdb  test    al, al
0x18004bbdd  jz      loc_18004BC66
0x18004bbe3  movzx   eax, [rbp+47h+var_78]
0x18004bbe7  cmp     rsi, rax
0x18004bbea  jnz     short loc_18004BC02
0x18004bbec  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18004bbf0  mov     r8, rsi; Size
0x18004bbf3  mov     rcx, r15; Buf1
0x18004bbf6  call    memcmp_0
0x18004bbfb  mov     ecx, eax
0x18004bbfd  xor     r9d, r9d
0x18004bc00  jmp     short loc_18004BC0A
0x18004bc02  movzx   eax, [rbp+47h+var_78]
0x18004bc06  mov     ecx, esi
0x18004bc08  sub     ecx, eax
0x18004bc0a  test    ecx, ecx
0x18004bc0c  js      short loc_18004BC58
0x18004bc0e  mov     r8, [rbp+47h+var_90]; unsigned __int8 *
0x18004bc12  lea     rdx, [rbp+47h+var_80]; struct wil::details_abi::UsageIndexProperty *
0x18004bc16  mov     rcx, rbx; this
0x18004bc19  jz      short loc_18004BC29
0x18004bc1b  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18004bc20  mov     rdi, rax
0x18004bc23  mov     [rbp+47h+var_90], rax
0x18004bc27  jmp     short loc_18004BBC7
0x18004bc29  mov     eax, [rbp+47h+var_88]
0x18004bc2c  mov     r9, r13; void *
0x18004bc2f  mov     [rsp+0C0h+var_98], eax; unsigned int
0x18004bc33  mov     [rsp+0C0h+var_A0], r12; unsigned __int64
0x18004bc38  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18004bc3d  xor     r9d, r9d
0x18004bc40  mov     [rbp+47h+var_90], rax
0x18004bc44  mov     rdi, rax
0x18004bc47  test    rax, rax
0x18004bc4a  jnz     short loc_18004BC53
0x18004bc4c  mov     al, 1
0x18004bc4e  jmp     loc_18004BD72
0x18004bc53  mov     r14b, 1
0x18004bc56  jmp     short loc_18004BC5C
0x18004bc58  mov     [rbp+47h+var_90], rdi
0x18004bc5c  mov     rcx, r9
0x18004bc5f  test    r14b, r14b
0x18004bc62  jnz     short loc_18004BCAB
0x18004bc64  jmp     short loc_18004BC6E
0x18004bc66  mov     rdi, [rbp+47h+var_90]
0x18004bc6a  mov     [rbx+20h], rdi
0x18004bc6e  movzx   eax, [rbp+47h+var_80]
0x18004bc72  mov     [rbp+47h+var_7C], 1
0x18004bc79  mov     [rbp+47h+var_78], si
0x18004bc7d  mov     [rbp+47h+Buf2], r9
0x18004bc81  mov     [rbp+47h+Buf2+8], r15
0x18004bc85  test    ax, ax
0x18004bc88  jnz     short loc_18004BC93
0x18004bc8a  movzx   ecx, si
0x18004bc8d  add     rcx, 2
0x18004bc91  jmp     short loc_18004BC96
0x18004bc93  mov     rcx, rax
0x18004bc96  mov     al, [rbp+47h+var_7E]
0x18004bc99  cmp     al, 1
0x18004bc9b  jnz     short loc_18004BCA3
0x18004bc9d  add     rcx, 2
0x18004bca1  jmp     short loc_18004BCAB
0x18004bca3  cmp     al, 2
0x18004bca5  jnz     short loc_18004BCAB
0x18004bca7  add     rcx, 4
0x18004bcab  movzx   eax, word ptr [rbx+6]
0x18004bcaf  mov     dl, [rbx+8]
0x18004bcb2  mov     r8d, [rbp+47h+var_88]
0x18004bcb6  mov     [rbp+47h+var_60], ax
0x18004bcba  mov     [rbp+47h+var_5E], dl
0x18004bcbd  mov     [rbp+47h+var_5C], r8d
0x18004bcc1  mov     [rbp+47h+var_58], r12w
0x18004bcc6  mov     [rbp+47h+var_50], r9
0x18004bcca  mov     [rbp+47h+var_48], r13
0x18004bcce  test    ax, ax
0x18004bcd1  jnz     short loc_18004BCDB
0x18004bcd3  movzx   eax, r12w
0x18004bcd7  add     rax, 2
0x18004bcdb  cmp     dl, 1
0x18004bcde  jnz     short loc_18004BCE6
0x18004bce0  add     rax, 2
0x18004bce4  jmp     short loc_18004BCEF
0x18004bce6  cmp     dl, 2
0x18004bce9  jnz     short loc_18004BCEF
0x18004bceb  add     rax, 4
0x18004bcef  mov     rdx, [rbx+28h]
0x18004bcf3  lea     rsi, [rax+rcx]
0x18004bcf7  mov     r9, [rbx+20h]
0x18004bcfb  mov     rcx, rdx
0x18004bcfe  sub     rcx, r9
0x18004bd01  cmp     r9, rdx
0x18004bd04  sbb     rax, rax
0x18004bd07  and     rax, rcx
0x18004bd0a  cmp     rax, rsi
0x18004bd0d  jb      short loc_18004BD70
0x18004bd0f  sub     rdx, rsi
0x18004bd12  lea     rcx, [rsi+rdi]; Destination
0x18004bd16  sub     rdx, rdi; DestinationSize
0x18004bd19  sub     r9, rdi; SourceSize
0x18004bd1c  mov     r8, rdi; Source
0x18004bd1f  call    cs:__imp_memmove_s
0x18004bd25  add     [rbx+20h], rsi
0x18004bd29  xor     ecx, ecx
0x18004bd2b  test    r14b, r14b
0x18004bd2e  jnz     short loc_18004BD43
0x18004bd30  mov     r8, [rbx+20h]; unsigned __int8 *
0x18004bd34  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18004bd38  lea     rcx, [rbp+47h+var_80]; this
0x18004bd3c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18004bd41  jmp     short loc_18004BD56
0x18004bd43  cmp     [rbp+47h+var_7E], cl
0x18004bd46  jz      short loc_18004BD56
0x18004bd48  mov     edx, [rbp+47h+var_7C]
0x18004bd4b  lea     rcx, [rbp+47h+var_80]; this
0x18004bd4f  inc     edx; unsigned int
0x18004bd51  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18004bd56  mov     r8, [rbx+20h]; unsigned __int8 *
0x18004bd5a  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18004bd5e  lea     rcx, [rbp+47h+var_60]; this
0x18004bd62  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18004bd67  mov     byte ptr [rbx+38h], 1
0x18004bd6b  jmp     loc_18004BC4C
0x18004bd70  xor     al, al
0x18004bd72  mov     rcx, [rbp+47h+var_40]
0x18004bd76  xor     rcx, rsp; StackCookie
0x18004bd79  call    __security_check_cookie
0x18004bd7e  mov     rbx, [rsp+0C0h+arg_8]
0x18004bd86  add     rsp, 90h
0x18004bd8d  pop     r15
0x18004bd8f  pop     r14
0x18004bd91  pop     r13
0x18004bd93  pop     r12
0x18004bd95  pop     rdi
0x18004bd96  pop     rsi
0x18004bd97  pop     rbp
0x18004bd98  retn
```
