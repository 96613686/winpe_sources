# CPersistStreamInit::WriteColumnMetaData(CRowInfo &,ushort)

- ea: `0x18001ce6c`
- end: `0x18001d15f`
- name: `?WriteColumnMetaData@CPersistStreamInit@@AEAAJAEAVCRowInfo@@G@Z`
- size: `755`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *, unsigned __int16)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18001ca70`

## callees

- `0x180002cd4`
- `0x180002d18`
- `0x180002d60`
- `0x180002da8`
- `0x180002df0`
- `0x180002e38`
- `0x180002e7c`
- `0x18001ac00`
- `0x18001c6a4`
- `0x18001c818`
- `0x18001ce6c`
- `0x18001e348`
- `0x18001f470`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteColumnMetaData(
        CPersistStreamInit *this,
        struct CRowInfo *a2,
        unsigned __int16 a3)
{
  __int64 v4; // rsi
  char *v6; // r14
  unsigned __int16 *BaseCatalogName; // rax
  bool v8; // r9
  int v9; // r10d
  unsigned __int16 *BaseSchemaName; // rax
  bool v11; // r9
  unsigned __int16 *BaseTableName; // rax
  bool v13; // r9
  bool v14; // r9
  unsigned __int16 *BaseColumnName; // rax
  bool v16; // r9
  __int64 v17; // rcx
  __int16 v18; // cx
  __int64 v19; // rax
  bool v20; // r9
  unsigned int CalculationInfoSize; // ebp
  unsigned __int8 *CalculationInfo; // rax
  unsigned int v24; // [rsp+78h] [rbp+10h] BYREF

  v4 = a3;
  v6 = (char *)this + 72;
  v24 = 0;
  if ( CMetaData::mdGetBaseCatalogName(a2, a3) )
  {
    BaseCatalogName = CMetaData::mdGetBaseCatalogName(a2, v4);
    v9 = CPersistStreamInit::WriteAttributeDefinition(
           this,
           *(void **)(*(_QWORD *)v6 + 1920LL),
           BaseCatalogName,
           v8,
           65,
           1);
    if ( v9 < 0 )
      return (unsigned int)v9;
  }
  if ( CMetaData::mdGetBaseSchemaName(a2, v4) )
  {
    BaseSchemaName = CMetaData::mdGetBaseSchemaName(a2, v4);
    v9 = CPersistStreamInit::WriteAttributeDefinition(
           this,
           *(void **)(*(_QWORD *)v6 + 1936LL),
           BaseSchemaName,
           v11,
           65,
           1);
    if ( v9 < 0 )
      return (unsigned int)v9;
  }
  if ( CMetaData::mdGetBaseTableName(a2, v4) )
  {
    BaseTableName = CMetaData::mdGetBaseTableName(a2, v4);
    v9 = CPersistStreamInit::WriteAttributeDefinition(
           this,
           *(void **)(*(_QWORD *)v6 + 1952LL),
           BaseTableName,
           v13,
           65,
           1);
    if ( v9 < 0 )
      return (unsigned int)v9;
  }
  if ( CMetaData::mdGetBaseColumnName(a2, v4) )
  {
    BaseColumnName = CMetaData::mdGetBaseColumnName(a2, v4);
    v9 = CPersistStreamInit::WriteAttributeDefinition(
           this,
           *(void **)(*(_QWORD *)v6 + 1968LL),
           BaseColumnName,
           v16,
           65,
           1);
    if ( v9 < 0 )
      return (unsigned int)v9;
  }
  v17 = *((_QWORD *)a2 + 1);
  if ( v17 )
  {
    v18 = *(_WORD *)(168 * v4 + v17 + 112);
LABEL_13:
    if ( v18 )
    {
      v9 = CPersistStreamInit::WriteAttributeDefinition(
             this,
             *(void **)(*((_QWORD *)this + 9) + 2128LL),
             *(unsigned __int16 **)(*((_QWORD *)this + 9) + 832LL),
             v14,
             65,
             0);
      if ( v9 < 0 )
        return (unsigned int)v9;
    }
    goto LABEL_15;
  }
  v19 = *((_QWORD *)a2 + 4);
  if ( !*(_DWORD *)(9648 * v4 + v19 + 9584) )
  {
    v18 = *(_WORD *)(9648 * v4 + v19 + 9580);
    goto LABEL_13;
  }
LABEL_15:
  if ( (unsigned __int16)v4 < *((_WORD *)a2 + 1)
    || (v9 = CPersistStreamInit::WriteAttributeDefinition(
               this,
               *(void **)(*((_QWORD *)this + 9) + 2144LL),
               *(unsigned __int16 **)(*((_QWORD *)this + 9) + 832LL),
               v14,
               65,
               0),
        v9 >= 0) )
  {
    if ( !CMetaData::mdGetAutoIncrement(a2, v4)
      || (v9 = CPersistStreamInit::WriteAttributeDefinition(
                 this,
                 *(void **)(*((_QWORD *)this + 9) + 2048LL),
                 *(unsigned __int16 **)(*((_QWORD *)this + 9) + 832LL),
                 v20,
                 65,
                 0),
          v9 >= 0) )
    {
      CalculationInfoSize = CMetaData::mdGetCalculationInfoSize(a2, v4);
      if ( CalculationInfoSize )
      {
        v9 = CPersistStreamInit::Write(
               this,
               *(_BYTE **)(*((_QWORD *)this + 9) + 704LL),
               *(unsigned __int8 *)(*((_QWORD *)this + 9) + 712LL),
               &v24,
               1);
        if ( v9 >= 0 )
        {
          v9 = CPersistStreamInit::WriteNamespace(this, 0x41u);
          if ( v9 >= 0 )
          {
            v9 = CPersistStreamInit::WriteTag(this, 0x8Fu, &v24);
            if ( v9 >= 0 )
            {
              v9 = CPersistStreamInit::WriteTag(this, 0x2Bu, &v24);
              if ( v9 >= 0 )
              {
                v9 = CPersistStreamInit::WriteTag(this, 0x29u, &v24);
                if ( v9 >= 0 )
                {
                  CalculationInfo = CMetaData::mdGetCalculationInfo(a2, v4);
                  v9 = CPersistStreamInit::BinaryOut(this, CalculationInfo, CalculationInfoSize);
                  if ( v9 >= 0 )
                    return (unsigned int)CPersistStreamInit::WriteTag(this, 0x29u, &v24);
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001ce6c  push    rbx
0x18001ce6e  push    rbp
0x18001ce6f  push    rsi
0x18001ce70  push    rdi
0x18001ce71  push    r14
0x18001ce73  push    r15
0x18001ce75  sub     rsp, 38h
0x18001ce79  mov     rdi, rdx
0x18001ce7c  movzx   esi, r8w
0x18001ce80  mov     rbx, rcx
0x18001ce83  lea     r14, [rcx+48h]
0x18001ce87  xor     r15d, r15d
0x18001ce8a  movzx   edx, si; unsigned __int16
0x18001ce8d  mov     rcx, rdi; this
0x18001ce90  mov     [rsp+68h+arg_8], r15d
0x18001ce95  mov     r10d, r15d
0x18001ce98  call    ?mdGetBaseCatalogName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseCatalogName(ushort)
0x18001ce9d  test    rax, rax
0x18001cea0  jz      short loc_18001CED7
0x18001cea2  movzx   edx, si; unsigned __int16
0x18001cea5  mov     rcx, rdi; this
0x18001cea8  call    ?mdGetBaseCatalogName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseCatalogName(ushort)
0x18001cead  mov     rdx, [r14]
0x18001ceb0  mov     r8, rax; unsigned __int16 *
0x18001ceb3  mov     [rsp+68h+var_40], 1; bool
0x18001ceb8  mov     rcx, rbx; this
0x18001cebb  mov     [rsp+68h+var_48], 41h ; 'A'; char
0x18001cec0  mov     rdx, [rdx+780h]; void *
0x18001cec7  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001cecc  mov     r10d, eax
0x18001cecf  test    eax, eax
0x18001ced1  js      loc_18001D14F
0x18001ced7  movzx   edx, si; unsigned __int16
0x18001ceda  mov     rcx, rdi; this
0x18001cedd  call    ?mdGetBaseSchemaName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseSchemaName(ushort)
0x18001cee2  test    rax, rax
0x18001cee5  jz      short loc_18001CF1C
0x18001cee7  movzx   edx, si; unsigned __int16
0x18001ceea  mov     rcx, rdi; this
0x18001ceed  call    ?mdGetBaseSchemaName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseSchemaName(ushort)
0x18001cef2  mov     rdx, [r14]
0x18001cef5  mov     r8, rax; unsigned __int16 *
0x18001cef8  mov     [rsp+68h+var_40], 1; bool
0x18001cefd  mov     rcx, rbx; this
0x18001cf00  mov     [rsp+68h+var_48], 41h ; 'A'; char
0x18001cf05  mov     rdx, [rdx+790h]; void *
0x18001cf0c  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001cf11  mov     r10d, eax
0x18001cf14  test    eax, eax
0x18001cf16  js      loc_18001D14F
0x18001cf1c  movzx   edx, si; unsigned __int16
0x18001cf1f  mov     rcx, rdi; this
0x18001cf22  call    ?mdGetBaseTableName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseTableName(ushort)
0x18001cf27  test    rax, rax
0x18001cf2a  jz      short loc_18001CF61
0x18001cf2c  movzx   edx, si; unsigned __int16
0x18001cf2f  mov     rcx, rdi; this
0x18001cf32  call    ?mdGetBaseTableName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseTableName(ushort)
0x18001cf37  mov     rdx, [r14]
0x18001cf3a  mov     r8, rax; unsigned __int16 *
0x18001cf3d  mov     [rsp+68h+var_40], 1; bool
0x18001cf42  mov     rcx, rbx; this
0x18001cf45  mov     [rsp+68h+var_48], 41h ; 'A'; char
0x18001cf4a  mov     rdx, [rdx+7A0h]; void *
0x18001cf51  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001cf56  mov     r10d, eax
0x18001cf59  test    eax, eax
0x18001cf5b  js      loc_18001D14F
0x18001cf61  movzx   edx, si; unsigned __int16
0x18001cf64  mov     rcx, rdi; this
0x18001cf67  call    ?mdGetBaseColumnName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseColumnName(ushort)
0x18001cf6c  test    rax, rax
0x18001cf6f  jz      short loc_18001CFA6
0x18001cf71  movzx   edx, si; unsigned __int16
0x18001cf74  mov     rcx, rdi; this
0x18001cf77  call    ?mdGetBaseColumnName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseColumnName(ushort)
0x18001cf7c  mov     rdx, [r14]
0x18001cf7f  mov     r8, rax; unsigned __int16 *
0x18001cf82  mov     [rsp+68h+var_40], 1; bool
0x18001cf87  mov     rcx, rbx; this
0x18001cf8a  mov     [rsp+68h+var_48], 41h ; 'A'; char
0x18001cf8f  mov     rdx, [rdx+7B0h]; void *
0x18001cf96  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001cf9b  mov     r10d, eax
0x18001cf9e  test    eax, eax
0x18001cfa0  js      loc_18001D14F
0x18001cfa6  mov     rcx, [rdi+8]
0x18001cfaa  mov     rax, rsi
0x18001cfad  test    rcx, rcx
0x18001cfb0  jz      short loc_18001CFC0
0x18001cfb2  imul    rax, 0A8h
0x18001cfb9  movzx   ecx, word ptr [rax+rcx+70h]
0x18001cfbe  jmp     short loc_18001CFDD
0x18001cfc0  imul    rcx, rax, 25B0h
0x18001cfc7  mov     rax, [rdi+20h]
0x18001cfcb  cmp     [rcx+rax+2570h], r15d
0x18001cfd3  jnz     short loc_18001D011
0x18001cfd5  movzx   ecx, word ptr [rcx+rax+256Ch]
0x18001cfdd  test    cx, cx
0x18001cfe0  jz      short loc_18001D011
0x18001cfe2  mov     rdx, [rbx+48h]
0x18001cfe6  mov     rcx, rbx; this
0x18001cfe9  mov     [rsp+68h+var_40], r15b; bool
0x18001cfee  mov     [rsp+68h+var_48], 41h ; 'A'; char
0x18001cff3  mov     r8, [rdx+340h]; unsigned __int16 *
0x18001cffa  mov     rdx, [rdx+850h]; void *
0x18001d001  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d006  mov     r10d, eax
0x18001d009  test    eax, eax
0x18001d00b  js      loc_18001D14F
0x18001d011  cmp     si, [rdi+2]
0x18001d015  jb      short loc_18001D046
0x18001d017  mov     rdx, [rbx+48h]
0x18001d01b  mov     rcx, rbx; this
0x18001d01e  mov     [rsp+68h+var_40], r15b; bool
0x18001d023  mov     [rsp+68h+var_48], 41h ; 'A'; char
0x18001d028  mov     r8, [rdx+340h]; unsigned __int16 *
0x18001d02f  mov     rdx, [rdx+860h]; void *
0x18001d036  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d03b  mov     r10d, eax
0x18001d03e  test    eax, eax
0x18001d040  js      loc_18001D14F
0x18001d046  movzx   edx, si; unsigned __int16
0x18001d049  mov     rcx, rdi; this
0x18001d04c  call    ?mdGetAutoIncrement@CMetaData@@QEAAFG@Z; CMetaData::mdGetAutoIncrement(ushort)
0x18001d051  test    ax, ax
0x18001d054  jz      short loc_18001D085
0x18001d056  mov     rdx, [rbx+48h]
0x18001d05a  mov     rcx, rbx; this
0x18001d05d  mov     [rsp+68h+var_40], r15b; bool
0x18001d062  mov     [rsp+68h+var_48], 41h ; 'A'; char
0x18001d067  mov     r8, [rdx+340h]; unsigned __int16 *
0x18001d06e  mov     rdx, [rdx+800h]; void *
0x18001d075  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d07a  mov     r10d, eax
0x18001d07d  test    eax, eax
0x18001d07f  js      loc_18001D14F
0x18001d085  movzx   edx, si; unsigned __int16
0x18001d088  mov     rcx, rdi; this
0x18001d08b  call    ?mdGetCalculationInfoSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetCalculationInfoSize(ushort)
0x18001d090  mov     ebp, eax
0x18001d092  test    eax, eax
0x18001d094  jz      loc_18001D14F
0x18001d09a  mov     rdx, [rbx+48h]
0x18001d09e  lea     r9, [rsp+68h+arg_8]; unsigned int *
0x18001d0a3  mov     rcx, rbx; this
0x18001d0a6  mov     [rsp+68h+var_48], 1; bool
0x18001d0ab  movzx   r8d, byte ptr [rdx+2C8h]; Size
0x18001d0b3  mov     rdx, [rdx+2C0h]; Src
0x18001d0ba  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001d0bf  mov     r10d, eax
0x18001d0c2  test    eax, eax
0x18001d0c4  js      loc_18001D14F
0x18001d0ca  mov     dl, 41h ; 'A'; unsigned __int8
0x18001d0cc  mov     rcx, rbx; this
0x18001d0cf  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001d0d4  mov     r10d, eax
0x18001d0d7  test    eax, eax
0x18001d0d9  js      short loc_18001D14F
0x18001d0db  lea     r8, [rsp+68h+arg_8]; unsigned int *
0x18001d0e0  mov     dl, 8Fh; unsigned __int8
0x18001d0e2  mov     rcx, rbx; this
0x18001d0e5  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d0ea  mov     r10d, eax
0x18001d0ed  test    eax, eax
0x18001d0ef  js      short loc_18001D14F
0x18001d0f1  lea     r8, [rsp+68h+arg_8]; unsigned int *
0x18001d0f6  mov     dl, 2Bh ; '+'; unsigned __int8
0x18001d0f8  mov     rcx, rbx; this
0x18001d0fb  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d100  mov     r10d, eax
0x18001d103  test    eax, eax
0x18001d105  js      short loc_18001D14F
0x18001d107  lea     r8, [rsp+68h+arg_8]; unsigned int *
0x18001d10c  mov     dl, 29h ; ')'; unsigned __int8
0x18001d10e  mov     rcx, rbx; this
0x18001d111  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d116  mov     r10d, eax
0x18001d119  test    eax, eax
0x18001d11b  js      short loc_18001D14F
0x18001d11d  movzx   edx, si; unsigned __int16
0x18001d120  mov     rcx, rdi; this
0x18001d123  call    ?mdGetCalculationInfo@CMetaData@@QEAAPEAEG@Z; CMetaData::mdGetCalculationInfo(ushort)
0x18001d128  mov     rdx, rax; unsigned __int8 *
0x18001d12b  mov     r8d, ebp; unsigned int
0x18001d12e  mov     rcx, rbx; this
0x18001d131  call    ?BinaryOut@CPersistStreamInit@@AEAAJPEAEK@Z; CPersistStreamInit::BinaryOut(uchar *,ulong)
0x18001d136  mov     r10d, eax
0x18001d139  test    eax, eax
0x18001d13b  js      short loc_18001D14F
0x18001d13d  lea     r8, [rsp+68h+arg_8]; unsigned int *
0x18001d142  mov     dl, 29h ; ')'; unsigned __int8
0x18001d144  mov     rcx, rbx; this
0x18001d147  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d14c  mov     r10d, eax
0x18001d14f  mov     eax, r10d
0x18001d152  add     rsp, 38h
0x18001d156  pop     r15
0x18001d158  pop     r14
0x18001d15a  pop     rdi
0x18001d15b  pop     rsi
0x18001d15c  pop     rbp
0x18001d15d  pop     rbx
0x18001d15e  retn
```
