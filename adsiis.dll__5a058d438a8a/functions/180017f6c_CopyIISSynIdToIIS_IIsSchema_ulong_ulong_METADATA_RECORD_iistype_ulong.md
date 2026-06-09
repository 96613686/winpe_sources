# CopyIISSynIdToIIS(IIsSchema *,ulong,ulong,_METADATA_RECORD *,_iistype *,ulong)

- ea: `0x180017f6c`
- end: `0x180018147`
- name: `?CopyIISSynIdToIIS@@YAPEAU_METADATA_RECORD@@PEAVIIsSchema@@KKPEAU1@PEAU_iistype@@K@Z`
- size: `475`
- prototype: `struct _METADATA_RECORD *(struct IIsSchema *, unsigned int, unsigned int, struct _METADATA_RECORD *, struct _iistype *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180010714`

## callees

- `0x180017d90`
- `0x180017e2c`
- `0x180017f6c`
- `0x18001b444`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsStr` at `0x180018019`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18001808d`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180018019`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18001808d`

## pseudocode

```c
struct _METADATA_RECORD *__fastcall CopyIISSynIdToIIS(
        struct IIsSchema *a1,
        unsigned int a2,
        unsigned int a3,
        struct _METADATA_RECORD *a4,
        struct _iistype *a5,
        unsigned int a6)
{
  struct _METADATA_RECORD *v6; // rbx
  unsigned int v8; // edx
  unsigned int v9; // edx
  unsigned int v10; // edx
  unsigned int v11; // edx
  struct _iistype *v13; // rcx
  LPWSTR v14; // rcx
  __int64 v15; // rax
  struct _iistype *v16; // rcx
  unsigned int v17; // edx
  unsigned int v18; // edx
  struct _iistype *v19; // rax
  unsigned int v21; // [rsp+58h] [rbp+28h] BYREF
  unsigned int v22; // [rsp+68h] [rbp+38h] BYREF

  v6 = a4;
  if ( a2 > 6 )
  {
    v17 = a2 - 7;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        v11 = v18 - 1;
        if ( !v11 )
          return CopyIISSynIdBINARY_To_IISBINARY(a1, a3, a4, a5);
LABEL_7:
        if ( v11 != 1 )
          return v6;
        return CopyIISSynIdBINARY_To_IISBINARY(a1, a3, a4, a5);
      }
      return CopyIISSynIdMULTISZ_To_IISMULTISZ(a1, a3, a4, a5, a6);
    }
    goto LABEL_26;
  }
  if ( a2 == 6 || (v8 = a2 - 1) == 0 )
  {
LABEL_26:
    v21 = 0;
    v22 = 0;
    IIsSchema::LookupMDFlags(a1, a3, &v21, &v22);
    v6->dwMDAttributes = v21;
    v6->dwMDUserType = v22;
    v19 = a5;
    v6->pbMDData = 0;
    *(_QWORD *)&v6->dwMDDataType = 1;
    v6->dwMDIdentifier = a3;
    if ( v19 )
    {
      v6->dwMDDataLen = 4;
      v6->pbMDData = (unsigned __int8 *)v19 + 8;
    }
    return v6;
  }
  v9 = v8 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
        goto LABEL_7;
      return CopyIISSynIdMULTISZ_To_IISMULTISZ(a1, a3, a4, a5, a6);
    }
    v21 = 0;
    v22 = 0;
    IIsSchema::LookupMDFlags(a1, a3, &v21, &v22);
    v13 = a5;
    v6->dwMDAttributes = v21;
    v6->dwMDUserType = v22;
    v6->dwMDIdentifier = a3;
    *(_QWORD *)&v6->dwMDDataType = 4;
    v6->pbMDData = 0;
    if ( v13 )
    {
      v14 = AllocADsStr(*((LPCWSTR *)v13 + 1));
      if ( v14 )
      {
        v15 = -1;
        do
          ++v15;
        while ( v14[v15] );
LABEL_15:
        v6->pbMDData = (unsigned __int8 *)v14;
        v6->dwMDDataLen = 2 * v15 + 2;
      }
    }
  }
  else
  {
    v21 = 0;
    v22 = 0;
    IIsSchema::LookupMDFlags(a1, a3, &v21, &v22);
    v16 = a5;
    v6->dwMDAttributes = v21;
    v6->dwMDUserType = v22;
    v6->dwMDIdentifier = a3;
    *(_QWORD *)&v6->dwMDDataType = 2;
    v6->pbMDData = 0;
    if ( v16 )
    {
      v14 = AllocADsStr(*((LPCWSTR *)v16 + 1));
      if ( v14 )
      {
        v15 = -1;
        do
          ++v15;
        while ( v14[v15] );
        goto LABEL_15;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180017f6c  mov     [rsp-18h+arg_0], rbx
0x180017f71  push    rbp
0x180017f72  push    rsi
0x180017f73  push    rdi
0x180017f74  mov     rbp, rsp
0x180017f77  sub     rsp, 30h
0x180017f7b  mov     rbx, r9
0x180017f7e  mov     esi, r8d
0x180017f81  cmp     edx, 6
0x180017f84  ja      loc_1800180AE
0x180017f8a  jz      loc_1800180EE
0x180017f90  sub     edx, 1
0x180017f93  jz      loc_1800180EE
0x180017f99  sub     edx, 1
0x180017f9c  jz      loc_18001804B
0x180017fa2  sub     edx, 1
0x180017fa5  jz      short loc_180017FD7
0x180017fa7  sub     edx, 1
0x180017faa  jz      short loc_180017FBA
0x180017fac  cmp     edx, 1
0x180017faf  jz      loc_1800180C1
0x180017fb5  jmp     loc_180018137
0x180017fba  mov     eax, [rbp+arg_28]
0x180017fbd  mov     r8, rbx; struct _METADATA_RECORD *
0x180017fc0  mov     r9, [rbp+arg_20]; struct _iistype *
0x180017fc4  mov     edx, esi; unsigned int
0x180017fc6  mov     [rsp+30h+var_10], eax; unsigned int
0x180017fca  call    ?CopyIISSynIdMULTISZ_To_IISMULTISZ@@YAPEAU_METADATA_RECORD@@PEAVIIsSchema@@KPEAU1@PEAU_iistype@@K@Z; CopyIISSynIdMULTISZ_To_IISMULTISZ(IIsSchema *,ulong,_METADATA_RECORD *,_iistype *,ulong)
0x180017fcf  mov     rbx, rax
0x180017fd2  jmp     loc_180018137
0x180017fd7  xor     edi, edi
0x180017fd9  lea     r9, [rbp+arg_18]; unsigned int *
0x180017fdd  lea     r8, [rbp+arg_8]; unsigned int *
0x180017fe1  mov     [rbp+arg_8], edi
0x180017fe4  mov     edx, esi; unsigned int
0x180017fe6  mov     [rbp+arg_18], edi
0x180017fe9  call    ?LookupMDFlags@IIsSchema@@QEAAJKPEAK0@Z; IIsSchema::LookupMDFlags(ulong,ulong *,ulong *)
0x180017fee  mov     eax, [rbp+arg_8]
0x180017ff1  mov     rcx, [rbp+arg_20]
0x180017ff5  mov     [rbx+4], eax
0x180017ff8  mov     eax, [rbp+arg_18]
0x180017ffb  mov     [rbx+8], eax
0x180017ffe  mov     [rbx], esi
0x180018000  mov     qword ptr [rbx+0Ch], 4
0x180018008  mov     [rbx+18h], rdi
0x18001800c  test    rcx, rcx
0x18001800f  jz      loc_180018137
0x180018015  mov     rcx, [rcx+8]; pStr
0x180018019  call    cs:__imp_AllocADsStr
0x18001801f  mov     rcx, rax; this
0x180018022  test    rax, rax
0x180018025  jz      loc_180018137
0x18001802b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001802f  inc     rax
0x180018032  cmp     [rcx+rax*2], di
0x180018036  jnz     short loc_18001802F
0x180018038  lea     eax, ds:2[rax*2]
0x18001803f  mov     [rbx+18h], rcx
0x180018043  mov     [rbx+10h], eax
0x180018046  jmp     loc_180018137
0x18001804b  xor     edi, edi
0x18001804d  lea     r9, [rbp+arg_18]; unsigned int *
0x180018051  lea     r8, [rbp+arg_8]; unsigned int *
0x180018055  mov     [rbp+arg_8], edi
0x180018058  mov     edx, esi; unsigned int
0x18001805a  mov     [rbp+arg_18], edi
0x18001805d  call    ?LookupMDFlags@IIsSchema@@QEAAJKPEAK0@Z; IIsSchema::LookupMDFlags(ulong,ulong *,ulong *)
0x180018062  mov     eax, [rbp+arg_8]
0x180018065  mov     rcx, [rbp+arg_20]
0x180018069  mov     [rbx+4], eax
0x18001806c  mov     eax, [rbp+arg_18]
0x18001806f  mov     [rbx+8], eax
0x180018072  mov     [rbx], esi
0x180018074  mov     qword ptr [rbx+0Ch], 2
0x18001807c  mov     [rbx+18h], rdi
0x180018080  test    rcx, rcx
0x180018083  jz      loc_180018137
0x180018089  mov     rcx, [rcx+8]; pStr
0x18001808d  call    cs:__imp_AllocADsStr
0x180018093  mov     rcx, rax; struct IIsSchema *
0x180018096  test    rax, rax
0x180018099  jz      loc_180018137
0x18001809f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800180a3  inc     rax
0x1800180a6  cmp     [rcx+rax*2], di
0x1800180aa  jnz     short loc_1800180A3
0x1800180ac  jmp     short loc_180018038
0x1800180ae  sub     edx, 7
0x1800180b1  jz      short loc_1800180EE
0x1800180b3  sub     edx, 1
0x1800180b6  jz      short loc_1800180D4
0x1800180b8  sub     edx, 1
0x1800180bb  jnz     loc_180017FAC
0x1800180c1  mov     r9, [rbp+arg_20]; struct _iistype *
0x1800180c5  mov     r8, rbx; struct _METADATA_RECORD *
0x1800180c8  mov     edx, esi; unsigned int
0x1800180ca  call    ?CopyIISSynIdBINARY_To_IISBINARY@@YAPEAU_METADATA_RECORD@@PEAVIIsSchema@@KPEAU1@PEAU_iistype@@@Z; CopyIISSynIdBINARY_To_IISBINARY(IIsSchema *,ulong,_METADATA_RECORD *,_iistype *)
0x1800180cf  jmp     loc_180017FCF
0x1800180d4  mov     eax, [rbp+arg_28]
0x1800180d7  mov     r8, rbx; struct _METADATA_RECORD *
0x1800180da  mov     r9, [rbp+arg_20]; struct _iistype *
0x1800180de  mov     edx, esi; unsigned int
0x1800180e0  mov     [rsp+30h+var_10], eax; unsigned int
0x1800180e4  call    ?CopyIISSynIdMULTISZ_To_IISMULTISZ@@YAPEAU_METADATA_RECORD@@PEAVIIsSchema@@KPEAU1@PEAU_iistype@@K@Z; CopyIISSynIdMULTISZ_To_IISMULTISZ(IIsSchema *,ulong,_METADATA_RECORD *,_iistype *,ulong)
0x1800180e9  jmp     loc_180017FCF
0x1800180ee  xor     edi, edi
0x1800180f0  lea     r9, [rbp+arg_18]; unsigned int *
0x1800180f4  lea     r8, [rbp+arg_8]; unsigned int *
0x1800180f8  mov     [rbp+arg_8], edi
0x1800180fb  mov     edx, esi; unsigned int
0x1800180fd  mov     [rbp+arg_18], edi
0x180018100  call    ?LookupMDFlags@IIsSchema@@QEAAJKPEAK0@Z; IIsSchema::LookupMDFlags(ulong,ulong *,ulong *)
0x180018105  mov     eax, [rbp+arg_8]
0x180018108  mov     [rbx+4], eax
0x18001810b  mov     eax, [rbp+arg_18]
0x18001810e  mov     [rbx+8], eax
0x180018111  mov     rax, [rbp+arg_20]
0x180018115  mov     [rbx+18h], rdi
0x180018119  mov     qword ptr [rbx+0Ch], 1
0x180018121  mov     [rbx], esi
0x180018123  test    rax, rax
0x180018126  jz      short loc_180018137
0x180018128  add     rax, 8
0x18001812c  mov     dword ptr [rbx+10h], 4
0x180018133  mov     [rbx+18h], rax
0x180018137  mov     rax, rbx
0x18001813a  mov     rbx, [rsp+30h+arg_0]
0x18001813f  add     rsp, 30h
0x180018143  pop     rdi
0x180018144  pop     rsi
0x180018145  pop     rbp
0x180018146  retn
```
