# TripleIterator<RangeSet::IteratorWithTripleCoreFragment,ulong,SharedRefPtr<IClockVector>,SharedRefPtr<IClockVector>>::UpdateIteratorState(void)

- ea: `0x180090970`
- end: `0x180090bb6`
- name: `?UpdateIteratorState@?$TripleIterator@VIteratorWithTripleCoreFragment@RangeSet@@KV?$SharedRefPtr@UIClockVector@@@@V3@@@AEAAXXZ`
- size: `582`
- prototype: `__int64 __fastcall(struct SyncId *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18008fd10`
- `0x1800904ec`

## callees

- `0x180005f20`
- `0x18000c270`
- `0x18008f9d8`
- `0x180090970`

## pseudocode

```c
__int64 __fastcall TripleIterator<RangeSet::IteratorWithTripleCoreFragment,unsigned long,SharedRefPtr<IClockVector>,SharedRefPtr<IClockVector>>::UpdateIteratorState(
        struct SyncId *a1)
{
  int v1; // r8d
  __int64 result; // rax
  int v4; // ecx
  int v5; // edi
  int v6; // esi
  BOOL v7; // ecx
  int *v8; // rsi
  int v9; // ebp
  int v10; // ecx
  int v11; // ecx
  int v12; // edx
  int Comparison23; // eax
  BOOL v14; // ecx

  v1 = *((_DWORD *)a1 + 25);
  result = (__int64)a1 + 108;
  *((_QWORD *)a1 + 11) = 0;
  *((_DWORD *)a1 + 24) = 0;
  if ( v1 )
    goto LABEL_38;
  if ( *((_DWORD *)a1 + 26) )
  {
    if ( !*(_DWORD *)result )
    {
      if ( *((_DWORD *)a1 + 30) )
        v11 = *((_DWORD *)a1 + 33);
      else
        v11 = SyncId::Compare(a1, (struct SyncId *)((char *)a1 + 32));
      *((_QWORD *)a1 + 14) = 0;
      *((_DWORD *)a1 + 30) = 0;
      result = v11 <= 0;
      *((_DWORD *)a1 + 22) = result;
      v7 = v11 >= 0;
      goto LABEL_37;
    }
LABEL_38:
    v12 = *((_DWORD *)a1 + 26);
    if ( !v12 && !*(_DWORD *)result )
    {
      Comparison23 = TripleIterator<RangeSet::IteratorWithTripleCoreFragment,unsigned long,SharedRefPtr<IClockVector>,SharedRefPtr<IClockVector>>::GetComparison23(a1);
      *((_QWORD *)a1 + 14) = 0;
      *((_DWORD *)a1 + 30) = 0;
      v14 = Comparison23 <= 0;
      result = Comparison23 >= 0;
      *((_DWORD *)a1 + 24) = result;
      *((_DWORD *)a1 + 23) = v14;
      goto LABEL_47;
    }
    if ( !v1 )
      goto LABEL_42;
    if ( !v12 )
    {
      *((_DWORD *)a1 + 23) = 1;
      goto LABEL_47;
    }
    if ( !*(_DWORD *)result )
      goto LABEL_46;
    goto LABEL_47;
  }
  v4 = *((_DWORD *)a1 + 28);
  if ( !*(_DWORD *)result )
  {
    if ( v4 )
    {
      v5 = *((_DWORD *)a1 + 31);
    }
    else
    {
      result = SyncId::Compare(a1, (struct SyncId *)((char *)a1 + 16));
      v5 = result;
    }
    if ( v5 <= 0 )
    {
      result = TripleIterator<RangeSet::IteratorWithTripleCoreFragment,unsigned long,SharedRefPtr<IClockVector>,SharedRefPtr<IClockVector>>::GetComparison23(a1);
      v6 = result;
      if ( (int)result <= 0 )
      {
        *((_QWORD *)a1 + 14) = 0;
        *((_DWORD *)a1 + 30) = 0;
        *((_DWORD *)a1 + 22) = 1;
        if ( !v5 )
        {
          *((_DWORD *)a1 + 23) = 1;
          v7 = result == 0;
LABEL_37:
          *((_DWORD *)a1 + 24) = v7;
          goto LABEL_47;
        }
LABEL_16:
        *((_DWORD *)a1 + 32) = v6;
        *((_DWORD *)a1 + 29) = 1;
        goto LABEL_47;
      }
      if ( *((_DWORD *)a1 + 30) )
        result = *((unsigned int *)a1 + 33);
      else
        result = SyncId::Compare(a1, (struct SyncId *)((char *)a1 + 32));
      *((_QWORD *)a1 + 14) = 0;
      *((_DWORD *)a1 + 30) = 0;
      if ( (int)result < 0 )
      {
        *((_DWORD *)a1 + 22) = 1;
        goto LABEL_16;
      }
      *((_DWORD *)a1 + 24) = 1;
      if ( (_DWORD)result )
      {
        *((_DWORD *)a1 + 31) = v5;
        *((_DWORD *)a1 + 28) = 1;
        goto LABEL_47;
      }
LABEL_42:
      *((_DWORD *)a1 + 22) = 1;
      goto LABEL_47;
    }
    v8 = (int *)((char *)a1 + 132);
    if ( *((_DWORD *)a1 + 30) )
    {
      v9 = *v8;
    }
    else
    {
      result = SyncId::Compare(a1, (struct SyncId *)((char *)a1 + 32));
      v9 = result;
    }
    if ( v9 <= 0 )
    {
      *((_QWORD *)a1 + 14) = 0;
      *((_DWORD *)a1 + 23) = 1;
LABEL_27:
      *v8 = v9;
      *((_DWORD *)a1 + 30) = 1;
      goto LABEL_47;
    }
    result = TripleIterator<RangeSet::IteratorWithTripleCoreFragment,unsigned long,SharedRefPtr<IClockVector>,SharedRefPtr<IClockVector>>::GetComparison23(a1);
    *((_QWORD *)a1 + 14) = 0;
    *((_DWORD *)a1 + 30) = 0;
    if ( (int)result <= 0 )
    {
      *((_DWORD *)a1 + 23) = 1;
      if ( (_DWORD)result )
        goto LABEL_27;
    }
    else
    {
      *((_DWORD *)a1 + 31) = v5;
      *((_DWORD *)a1 + 28) = 1;
    }
LABEL_46:
    *((_DWORD *)a1 + 24) = 1;
    goto LABEL_47;
  }
  if ( v4 )
    v10 = *((_DWORD *)a1 + 31);
  else
    v10 = SyncId::Compare(a1, (struct SyncId *)((char *)a1 + 16));
  *((_QWORD *)a1 + 14) = 0;
  *((_DWORD *)a1 + 30) = 0;
  result = v10 <= 0;
  *((_DWORD *)a1 + 23) = v10 >= 0;
  *((_DWORD *)a1 + 22) = result;
LABEL_47:
  if ( *((_DWORD *)a1 + 22) )
  {
    result = *((unsigned int *)a1 + 13);
    *((_DWORD *)a1 + 12) = result;
  }
  if ( *((_DWORD *)a1 + 23) )
    result = (__int64)SharedRefPtr<IClockVector>::operator=((__int64 *)a1 + 7, (__int64 *)a1 + 8);
  if ( *((_DWORD *)a1 + 24) )
    return (__int64)SharedRefPtr<IClockVector>::operator=((__int64 *)a1 + 9, (__int64 *)a1 + 10);
  return result;
}

```

## disassembly

```asm
0x180090970  push    rbx
0x180090972  push    rbp
0x180090973  push    rsi
0x180090974  push    rdi
0x180090975  push    r14
0x180090977  push    r15
0x180090979  sub     rsp, 28h
0x18009097d  mov     r8d, [rcx+64h]
0x180090981  lea     rax, [rcx+6Ch]
0x180090985  xor     r14d, r14d
0x180090988  mov     rbx, rcx
0x18009098b  mov     [rcx+58h], r14
0x18009098f  mov     [rcx+60h], r14d
0x180090993  lea     r15d, [r14+1]
0x180090997  test    r8d, r8d
0x18009099a  jnz     loc_180090B2B
0x1800909a0  cmp     [rcx+68h], r14d
0x1800909a4  jnz     loc_180090AF0
0x1800909aa  mov     ecx, [rcx+70h]
0x1800909ad  cmp     [rax], r14d
0x1800909b0  jnz     loc_180090AB9
0x1800909b6  test    ecx, ecx
0x1800909b8  jnz     short loc_1800909CA
0x1800909ba  lea     rdx, [rbx+10h]; struct SyncId *
0x1800909be  mov     rcx, rbx; struct SyncId *
0x1800909c1  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x1800909c6  mov     edi, eax
0x1800909c8  jmp     short loc_1800909CD
0x1800909ca  mov     edi, [rbx+7Ch]
0x1800909cd  test    edi, edi
0x1800909cf  jg      loc_180090A55
0x1800909d5  mov     rcx, rbx
0x1800909d8  call    ?GetComparison23@?$TripleIterator@VIteratorWithTripleCoreFragment@RangeSet@@KV?$SharedRefPtr@UIClockVector@@@@V3@@@AEAAJXZ; TripleIterator<RangeSet::IteratorWithTripleCoreFragment,ulong,SharedRefPtr<IClockVector>,SharedRefPtr<IClockVector>>::GetComparison23(void)
0x1800909dd  mov     esi, eax
0x1800909df  test    eax, eax
0x1800909e1  jg      short loc_180090A04
0x1800909e3  mov     [rbx+70h], r14
0x1800909e7  mov     [rbx+78h], r14d
0x1800909eb  mov     [rbx+58h], r15d
0x1800909ef  test    edi, edi
0x1800909f1  jnz     short loc_180090A2E
0x1800909f3  test    eax, eax
0x1800909f5  mov     [rbx+5Ch], r15d
0x1800909f9  mov     ecx, r14d
0x1800909fc  setz    cl
0x1800909ff  jmp     loc_180090B26
0x180090a04  cmp     [rbx+78h], r14d
0x180090a08  jnz     short loc_180090A18
0x180090a0a  lea     rdx, [rbx+20h]; struct SyncId *
0x180090a0e  mov     rcx, rbx; struct SyncId *
0x180090a11  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x180090a16  jmp     short loc_180090A1E
0x180090a18  mov     eax, [rbx+84h]
0x180090a1e  mov     [rbx+70h], r14
0x180090a22  mov     [rbx+78h], r14d
0x180090a26  test    eax, eax
0x180090a28  jns     short loc_180090A3D
0x180090a2a  mov     [rbx+58h], r15d
0x180090a2e  mov     [rbx+80h], esi
0x180090a34  mov     [rbx+74h], r15d
0x180090a38  jmp     loc_180090B77
0x180090a3d  mov     [rbx+60h], r15d
0x180090a41  test    eax, eax
0x180090a43  jz      loc_180090B5E
0x180090a49  mov     [rbx+7Ch], edi
0x180090a4c  mov     [rbx+70h], r15d
0x180090a50  jmp     loc_180090B77
0x180090a55  lea     rsi, [rbx+84h]
0x180090a5c  cmp     [rbx+78h], r14d
0x180090a60  jnz     short loc_180090A72
0x180090a62  lea     rdx, [rbx+20h]; struct SyncId *
0x180090a66  mov     rcx, rbx; struct SyncId *
0x180090a69  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x180090a6e  mov     ebp, eax
0x180090a70  jmp     short loc_180090A74
0x180090a72  mov     ebp, [rsi]
0x180090a74  test    ebp, ebp
0x180090a76  jg      short loc_180090A82
0x180090a78  mov     [rbx+70h], r14
0x180090a7c  mov     [rbx+5Ch], r15d
0x180090a80  jmp     short loc_180090AAE
0x180090a82  mov     rcx, rbx
0x180090a85  call    ?GetComparison23@?$TripleIterator@VIteratorWithTripleCoreFragment@RangeSet@@KV?$SharedRefPtr@UIClockVector@@@@V3@@@AEAAJXZ; TripleIterator<RangeSet::IteratorWithTripleCoreFragment,ulong,SharedRefPtr<IClockVector>,SharedRefPtr<IClockVector>>::GetComparison23(void)
0x180090a8a  mov     [rbx+70h], r14
0x180090a8e  mov     [rbx+78h], r14d
0x180090a92  test    eax, eax
0x180090a94  jle     short loc_180090AA2
0x180090a96  mov     [rbx+7Ch], edi
0x180090a99  mov     [rbx+70h], r15d
0x180090a9d  jmp     loc_180090B73
0x180090aa2  mov     [rbx+5Ch], r15d
0x180090aa6  test    eax, eax
0x180090aa8  jz      loc_180090B73
0x180090aae  mov     [rsi], ebp
0x180090ab0  mov     [rbx+78h], r15d
0x180090ab4  jmp     loc_180090B77
0x180090ab9  test    ecx, ecx
0x180090abb  jnz     short loc_180090ACD
0x180090abd  lea     rdx, [rbx+10h]; struct SyncId *
0x180090ac1  mov     rcx, rbx; struct SyncId *
0x180090ac4  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x180090ac9  mov     ecx, eax
0x180090acb  jmp     short loc_180090AD0
0x180090acd  mov     ecx, [rbx+7Ch]
0x180090ad0  test    ecx, ecx
0x180090ad2  mov     [rbx+70h], r14
0x180090ad6  mov     eax, r14d
0x180090ad9  mov     [rbx+78h], r14d
0x180090add  setle   al
0x180090ae0  not     ecx
0x180090ae2  shr     ecx, 1Fh; struct SyncId *
0x180090ae5  mov     [rbx+5Ch], ecx
0x180090ae8  mov     [rbx+58h], eax
0x180090aeb  jmp     loc_180090B77
0x180090af0  cmp     [rax], r14d
0x180090af3  jnz     short loc_180090B2B
0x180090af5  cmp     [rcx+78h], r14d
0x180090af9  jnz     short loc_180090B08
0x180090afb  lea     rdx, [rcx+20h]; struct SyncId *
0x180090aff  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x180090b04  mov     ecx, eax
0x180090b06  jmp     short loc_180090B0E
0x180090b08  mov     ecx, [rcx+84h]
0x180090b0e  test    ecx, ecx
0x180090b10  mov     [rbx+70h], r14
0x180090b14  mov     eax, r14d
0x180090b17  mov     [rbx+78h], r14d
0x180090b1b  setle   al
0x180090b1e  not     ecx
0x180090b20  mov     [rbx+58h], eax
0x180090b23  shr     ecx, 1Fh
0x180090b26  mov     [rbx+60h], ecx
0x180090b29  jmp     short loc_180090B77
0x180090b2b  mov     edx, [rcx+68h]
0x180090b2e  test    edx, edx
0x180090b30  jnz     short loc_180090B59
0x180090b32  cmp     [rax], r14d
0x180090b35  jnz     short loc_180090B59
0x180090b37  call    ?GetComparison23@?$TripleIterator@VIteratorWithTripleCoreFragment@RangeSet@@KV?$SharedRefPtr@UIClockVector@@@@V3@@@AEAAJXZ; TripleIterator<RangeSet::IteratorWithTripleCoreFragment,ulong,SharedRefPtr<IClockVector>,SharedRefPtr<IClockVector>>::GetComparison23(void)
0x180090b3c  test    eax, eax
0x180090b3e  mov     [rbx+70h], r14
0x180090b42  mov     ecx, r14d
0x180090b45  mov     [rbx+78h], r14d
0x180090b49  setle   cl
0x180090b4c  not     eax
0x180090b4e  shr     eax, 1Fh
0x180090b51  mov     [rbx+60h], eax
0x180090b54  mov     [rbx+5Ch], ecx
0x180090b57  jmp     short loc_180090B77
0x180090b59  test    r8d, r8d
0x180090b5c  jnz     short loc_180090B64
0x180090b5e  mov     [rbx+58h], r15d
0x180090b62  jmp     short loc_180090B77
0x180090b64  test    edx, edx
0x180090b66  jnz     short loc_180090B6E
0x180090b68  mov     [rcx+5Ch], r15d
0x180090b6c  jmp     short loc_180090B77
0x180090b6e  cmp     [rax], r14d
0x180090b71  jnz     short loc_180090B77
0x180090b73  mov     [rbx+60h], r15d
0x180090b77  cmp     [rbx+58h], r14d
0x180090b7b  jz      short loc_180090B83
0x180090b7d  mov     eax, [rbx+34h]
0x180090b80  mov     [rbx+30h], eax
0x180090b83  cmp     [rbx+5Ch], r14d
0x180090b87  jz      short loc_180090B96
0x180090b89  lea     rdx, [rbx+40h]
0x180090b8d  lea     rcx, [rbx+38h]
0x180090b91  call    ??4?$SharedRefPtr@UIClockVector@@@@QEAAAEAV0@AEBV0@@Z; SharedRefPtr<IClockVector>::operator=(SharedRefPtr<IClockVector> const &)
0x180090b96  cmp     [rbx+60h], r14d
0x180090b9a  jz      short loc_180090BA9
0x180090b9c  lea     rdx, [rbx+50h]
0x180090ba0  lea     rcx, [rbx+48h]
0x180090ba4  call    ??4?$SharedRefPtr@UIClockVector@@@@QEAAAEAV0@AEBV0@@Z; SharedRefPtr<IClockVector>::operator=(SharedRefPtr<IClockVector> const &)
0x180090ba9  add     rsp, 28h
0x180090bad  pop     r15
0x180090baf  pop     r14
0x180090bb1  pop     rdi
0x180090bb2  pop     rsi
0x180090bb3  pop     rbp
0x180090bb4  pop     rbx
0x180090bb5  retn
```
