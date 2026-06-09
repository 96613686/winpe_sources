# CPersistStreamInit::WriteData(CRowInfo &,unsigned __int64)

- ea: `0x18001d9f4`
- end: `0x18001dff8`
- name: `?WriteData@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_K@Z`
- size: `1540`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x18001ba50`
- `0x18001e44c`

## callees

- `0x180001dd8`
- `0x18001b85c`
- `0x18001b9ec`
- `0x18001d9f4`
- `0x18001e348`
- `0x18001e44c`
- `0x18001f2c8`
- `0x18001f470`
- `0x18002e012`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001dd3e`
- `ole32!CoTaskMemFree` at `0x18001de06`
- `ole32!CoTaskMemFree` at `0x18001de11`
- `ole32!CoTaskMemFree` at `0x18001dea1`
- `ole32!CoTaskMemFree` at `0x18001debb`
- `ole32!CoTaskMemFree` at `0x18001dec6`
- `ole32!CoTaskMemFree` at `0x18001dee2`
- `ole32!CoTaskMemFree` at `0x18001df60`
- `ole32!CoTaskMemFree` at `0x18001df6b`
- `ole32!CoTaskMemFree` at `0x18001dd3e`
- `ole32!CoTaskMemFree` at `0x18001de06`
- `ole32!CoTaskMemFree` at `0x18001de11`
- `ole32!CoTaskMemFree` at `0x18001dea1`
- `ole32!CoTaskMemFree` at `0x18001debb`
- `ole32!CoTaskMemFree` at `0x18001dec6`
- `ole32!CoTaskMemFree` at `0x18001dee2`
- `ole32!CoTaskMemFree` at `0x18001df60`
- `ole32!CoTaskMemFree` at `0x18001df6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPersistStreamInit::WriteData(CPersistStreamInit *this, struct CRowInfo *a2, void *a3)
{
  LPVOID v3; // r14
  unsigned int v6; // r15d
  int v7; // ebx
  int v8; // edx
  struct CBitMap *BitMap; // rax
  _QWORD *v10; // r13
  _QWORD *v11; // r12
  _QWORD *v12; // r14
  _DWORD *v13; // r15
  int v14; // edx
  struct CBitMap *v15; // rbx
  unsigned __int64 *v16; // rcx
  struct CBitMap *v17; // rax
  unsigned int *v18; // rdx
  unsigned int v19; // ecx
  void *v20; // rcx
  __int64 v21; // rcx
  _QWORD *v22; // r14
  unsigned __int64 v23; // rdx
  int v24; // ecx
  __int64 v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  unsigned __int64 *v29; // [rsp+40h] [rbp-20h] BYREF
  LPVOID v30; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v31; // [rsp+50h] [rbp-10h] BYREF
  __int64 v32; // [rsp+58h] [rbp-8h] BYREF
  char v33; // [rsp+A8h] [rbp+48h]
  LPVOID pv; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v35; // [rsp+B8h] [rbp+58h] BYREF

  pv = a3;
  v3 = a3;
  v6 = 0;
  v7 = 0;
  v31 = 0;
  v32 = 0;
  v29 = (unsigned __int64 *)&v32;
  v35 = 0;
  if ( a3 && !*((_QWORD *)a2 + 30) && !CPersistStreamInit::IsTopLevel(this, a2) )
  {
    BitMap = MakeBitMap(1024, v8);
    *((_QWORD *)a2 + 30) = BitMap;
    if ( !BitMap )
    {
LABEL_5:
      v7 = -2147024882;
      goto LABEL_60;
    }
    *((_DWORD *)a2 + 62) = 1024;
  }
  if ( CPersistStreamInit::IsTopLevel(this, a2) )
  {
    v7 = CPersistStreamInit::WriteTag(this, 0x30u, &v35);
    if ( v7 < 0 )
      goto LABEL_60;
    v7 = CPersistStreamInit::WriteNamespace(this, 0x41u);
    if ( v7 < 0 )
      goto LABEL_60;
    v7 = CPersistStreamInit::WriteTag(this, 2u, &v35);
    if ( v7 < 0 )
      goto LABEL_60;
    v7 = CPersistStreamInit::WriteTag(this, 0x31u, &v35);
    if ( v7 < 0 )
      goto LABEL_60;
    v7 = CPersistStreamInit::WriteTag(this, 0x28u, &v35);
    if ( v7 < 0 )
      goto LABEL_60;
    ++*((_DWORD *)this + 12);
  }
  v33 = 0;
  v10 = (_QWORD *)((char *)a2 + 112);
  if ( !*((_QWORD *)a2 + 14) )
    (***((void (__fastcall ****)(_QWORD, GUID *, char *))a2 + 13))(
      *((_QWORD *)a2 + 13),
      &IID_IRowsetUpdate,
      (char *)a2 + 112);
  v11 = (_QWORD *)((char *)a2 + 120);
  if ( !*((_QWORD *)a2 + 15) )
    (***((void (__fastcall ****)(_QWORD, GUID *, char *))a2 + 13))(
      *((_QWORD *)a2 + 13),
      &IID_IUpdateInfo,
      (char *)a2 + 120);
  while ( v7 != 265926 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, _QWORD, __int64, unsigned __int64 *, unsigned __int64 **))(**((_QWORD **)a2 + 13) + 40LL))(
           *((_QWORD *)a2 + 13),
           v3,
           0,
           1,
           &v31,
           &v29);
    if ( v7 < 0 )
      goto LABEL_60;
    v12 = (_QWORD *)((char *)a2 + 208);
    *((_QWORD *)a2 + 26) = 0;
    if ( !v31 )
      goto LABEL_18;
    if ( !*v10 )
      goto LABEL_32;
    v13 = (_DWORD *)((char *)a2 + 196);
    v7 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, __int64, unsigned __int64 *, char *))(*(_QWORD *)*v10 + 64LL))(
           *v10,
           pv,
           1,
           v29,
           (char *)a2 + 196);
    if ( v7 < 0 )
      goto LABEL_60;
    if ( *v13 != 4 )
    {
      if ( *v13 == 2 )
      {
        v7 = CPersistStreamInit::WriteRow(this, a2, *v29);
        if ( v7 < 0 )
          goto LABEL_60;
        *v12 = *((unsigned int *)a2 + 21);
        if ( *v11 )
          (*(void (__fastcall **)(_QWORD, unsigned __int64, char *, char *))(*(_QWORD *)*v11 + 24LL))(
            *v11,
            *v29,
            (char *)a2 + 208,
            (char *)a2 + 216);
        *v13 = 8;
LABEL_31:
        v6 = 0;
      }
      else
      {
        if ( *v13 != 1 )
          goto LABEL_31;
        v33 = 1;
        *v12 = *((unsigned int *)a2 + 21);
        v6 = 0;
        if ( *v11 )
          (*(void (__fastcall **)(_QWORD, unsigned __int64, char *, char *))(*(_QWORD *)*v11 + 24LL))(
            *v11,
            *v29,
            (char *)a2 + 208,
            (char *)a2 + 216);
      }
LABEL_32:
      v7 = CPersistStreamInit::WriteRow(this, a2, *v29);
      if ( v7 < 0 )
        goto LABEL_60;
      v15 = (struct CBitMap *)*((_QWORD *)a2 + 30);
      if ( v15 )
      {
        v16 = v29;
        if ( *v29 >= *((unsigned int *)a2 + 62) )
        {
          v17 = MakeBitMap(*(_DWORD *)v29 + 1024, v14);
          v15 = v17;
          if ( !v17 )
            goto LABEL_5;
          v18 = (unsigned int *)*((_QWORD *)a2 + 30);
          v19 = *(_DWORD *)v17;
          if ( *(_DWORD *)v17 >= *v18 )
            v19 = *v18;
          memcpy_0((char *)v17 + 4, v18 + 1, v19);
          MMMFree(*((unsigned __int8 **)a2 + 30));
          *((_QWORD *)a2 + 30) = v15;
          v16 = v29;
          *((_DWORD *)a2 + 62) = *(_DWORD *)v29 + 1024;
        }
        *((_BYTE *)v15 + ((__int64)*(int *)v16 >> 3) + 4) |= *((_BYTE *)bits + (*(_DWORD *)v16 & 7));
      }
      goto LABEL_40;
    }
    *v13 = *((_DWORD *)a2 + 50);
    v6 = 0;
LABEL_40:
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int64 *))(**((_QWORD **)a2 + 13) + 48LL))(
           *((_QWORD *)a2 + 13),
           1,
           v29);
    if ( v7 < 0 )
      goto LABEL_60;
    *v12 = 0;
    v20 = (void *)*((_QWORD *)a2 + 27);
    if ( v20 )
    {
      CoTaskMemFree(v20);
      *((_QWORD *)a2 + 27) = 0;
    }
    *v29 = 0;
LABEL_18:
    v3 = pv;
  }
  CPersistStreamInit::WriteStatusFooter(this, *((_DWORD *)a2 + 49));
  v21 = *((_QWORD *)a2 + 14);
  if ( !v21 )
    goto LABEL_67;
  v30 = 0;
  pv = 0;
  *((_DWORD *)a2 + 50) = 8;
  v7 = (*(__int64 (__fastcall **)(__int64, LPVOID, _QWORD, unsigned __int64 *, LPVOID *, LPVOID *))(*(_QWORD *)v21 + 56LL))(
         v21,
         v3,
         5 - (unsigned int)(v33 != 0),
         &v31,
         &pv,
         &v30);
  if ( v7 < 0 )
    goto LABEL_59;
  v22 = (_QWORD *)((char *)a2 + 208);
  while ( 1 )
  {
    v23 = v31;
    if ( v6 >= v31 )
      break;
    v24 = *((_DWORD *)v30 + v6);
    *((_DWORD *)a2 + 49) = v24;
    if ( v24 == 1 )
    {
      *v22 = *((unsigned int *)a2 + 21);
      v25 = *((_QWORD *)a2 + 15);
      if ( v25 )
        (*(void (__fastcall **)(__int64, _QWORD, char *, char *))(*(_QWORD *)v25 + 24LL))(
          v25,
          *((_QWORD *)pv + v6),
          (char *)a2 + 208,
          (char *)a2 + 216);
    }
    v7 = CPersistStreamInit::WriteRow(this, a2, *((_QWORD *)pv + v6));
    if ( v7 < 0 )
      goto LABEL_59;
    *v22 = 0;
    v26 = (void *)*((_QWORD *)a2 + 27);
    if ( v26 )
    {
      CoTaskMemFree(v26);
      *((_QWORD *)a2 + 27) = 0;
    }
    ++v6;
  }
  if ( v31 )
  {
    CPersistStreamInit::WriteStatusFooter(this, *((_DWORD *)a2 + 49));
    v23 = v31;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, LPVOID, _QWORD, _QWORD, _QWORD))(**((_QWORD **)a2 + 13)
                                                                                           + 48LL))(
         *((_QWORD *)a2 + 13),
         v23,
         pv,
         0,
         0,
         0);
  if ( v7 < 0 )
  {
LABEL_59:
    CoTaskMemFree(pv);
    CoTaskMemFree(v30);
  }
  else
  {
    *((_DWORD *)a2 + 49) = 8;
    *((_DWORD *)a2 + 50) = 8;
    CoTaskMemFree(pv);
    CoTaskMemFree(v30);
LABEL_67:
    if ( CPersistStreamInit::IsTopLevel(this, a2) )
    {
      --*((_DWORD *)this + 12);
      v7 = CPersistStreamInit::WriteTag(this, 0x33u, &v35);
      if ( v7 >= 0 )
      {
        v7 = CPersistStreamInit::WriteNamespace(this, 0x41u);
        if ( v7 >= 0 )
        {
          v7 = CPersistStreamInit::WriteTag(this, 2u, &v35);
          if ( v7 >= 0 )
          {
            v7 = CPersistStreamInit::WriteTag(this, 0x31u, &v35);
            if ( v7 >= 0 )
              v7 = CPersistStreamInit::WriteTag(this, 0x28u, &v35);
          }
        }
      }
    }
  }
LABEL_60:
  *((_QWORD *)a2 + 26) = 0;
  v27 = (void *)*((_QWORD *)a2 + 27);
  if ( v27 )
  {
    CoTaskMemFree(v27);
    *((_QWORD *)a2 + 27) = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001d9f4  mov     [rsp-38h+arg_0], rbx
0x18001d9f9  mov     [rsp-38h+pv], r8
0x18001d9fe  push    rbp
0x18001d9ff  push    rsi
0x18001da00  push    rdi
0x18001da01  push    r12
0x18001da03  push    r13
0x18001da05  push    r14
0x18001da07  push    r15
0x18001da09  mov     rbp, rsp
0x18001da0c  sub     rsp, 60h
0x18001da10  mov     r14, r8
0x18001da13  mov     rdi, rdx
0x18001da16  mov     rsi, rcx
0x18001da19  xor     r15d, r15d
0x18001da1c  mov     ebx, r15d
0x18001da1f  mov     [rbp+var_10], r15
0x18001da23  mov     [rbp+var_8], r15
0x18001da27  lea     rax, [rbp+var_8]
0x18001da2b  mov     [rbp+var_20], rax
0x18001da2f  mov     [rbp+arg_18], r15d
0x18001da33  mov     r12d, 400h
0x18001da39  test    r8, r8
0x18001da3c  jz      short loc_18001DA75
0x18001da3e  cmp     [rdx+0F0h], r15
0x18001da45  jnz     short loc_18001DA75
0x18001da47  call    ?IsTopLevel@CPersistStreamInit@@AEAA_NAEAVCRowInfo@@@Z; CPersistStreamInit::IsTopLevel(CRowInfo &)
0x18001da4c  test    al, al
0x18001da4e  jnz     short loc_18001DA75
0x18001da50  mov     ecx, r12d; int
0x18001da53  call    ?MakeBitMap@@YAPEAVCBitMap@@JH@Z; MakeBitMap(long,int)
0x18001da58  mov     [rdi+0F0h], rax
0x18001da5f  test    rax, rax
0x18001da62  jnz     short loc_18001DA6E
0x18001da64  mov     ebx, 8007000Eh
0x18001da69  jmp     loc_18001DECF
0x18001da6e  mov     [rdi+0F8h], r12d
0x18001da75  mov     rdx, rdi; struct CRowInfo *
0x18001da78  mov     rcx, rsi; this
0x18001da7b  call    ?IsTopLevel@CPersistStreamInit@@AEAA_NAEAVCRowInfo@@@Z; CPersistStreamInit::IsTopLevel(CRowInfo &)
0x18001da80  test    al, al
0x18001da82  jz      short loc_18001DAFB
0x18001da84  lea     r8, [rbp+arg_18]; unsigned int *
0x18001da88  mov     dl, 30h ; '0'; unsigned __int8
0x18001da8a  mov     rcx, rsi; this
0x18001da8d  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001da92  mov     ebx, eax
0x18001da94  test    eax, eax
0x18001da96  js      loc_18001DECF
0x18001da9c  mov     dl, 41h ; 'A'; unsigned __int8
0x18001da9e  mov     rcx, rsi; this
0x18001daa1  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001daa6  mov     ebx, eax
0x18001daa8  test    eax, eax
0x18001daaa  js      loc_18001DECF
0x18001dab0  lea     r8, [rbp+arg_18]; unsigned int *
0x18001dab4  mov     dl, 2; unsigned __int8
0x18001dab6  mov     rcx, rsi; this
0x18001dab9  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001dabe  mov     ebx, eax
0x18001dac0  test    eax, eax
0x18001dac2  js      loc_18001DECF
0x18001dac8  lea     r8, [rbp+arg_18]; unsigned int *
0x18001dacc  mov     dl, 31h ; '1'; unsigned __int8
0x18001dace  mov     rcx, rsi; this
0x18001dad1  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001dad6  mov     ebx, eax
0x18001dad8  test    eax, eax
0x18001dada  js      loc_18001DECF
0x18001dae0  lea     r8, [rbp+arg_18]; unsigned int *
0x18001dae4  mov     dl, 28h ; '('; unsigned __int8
0x18001dae6  mov     rcx, rsi; this
0x18001dae9  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001daee  mov     ebx, eax
0x18001daf0  test    eax, eax
0x18001daf2  js      loc_18001DECF
0x18001daf8  inc     dword ptr [rsi+30h]
0x18001dafb  mov     [rbp+arg_8], r15b
0x18001daff  lea     r13, [rdi+70h]
0x18001db03  cmp     [r13+0], r15
0x18001db07  jnz     short loc_18001DB22
0x18001db09  mov     rcx, [rdi+68h]
0x18001db0d  mov     rax, [rcx]
0x18001db10  mov     r8, r13
0x18001db13  lea     rdx, IID_IRowsetUpdate
0x18001db1a  mov     rax, [rax]
0x18001db1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db22  lea     r12, [rdi+78h]
0x18001db26  cmp     [r12], r15
0x18001db2a  jnz     short loc_18001DB4B
0x18001db2c  mov     rcx, [rdi+68h]
0x18001db30  mov     rax, [rcx]
0x18001db33  mov     r8, r12
0x18001db36  lea     rdx, ?IID_IUpdateInfo@@3U_GUID@@B; _GUID const IID_IUpdateInfo
0x18001db3d  mov     rax, [rax]
0x18001db40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db45  jmp     short loc_18001DB4B
0x18001db47  mov     r14, [rbp+pv]
0x18001db4b  cmp     ebx, 40EC6h
0x18001db51  jz      loc_18001DD9D
0x18001db57  mov     rcx, [rdi+68h]
0x18001db5b  mov     rax, [rcx]
0x18001db5e  lea     rdx, [rbp+var_20]
0x18001db62  mov     [rsp+60h+var_38], rdx
0x18001db67  lea     rdx, [rbp+var_10]
0x18001db6b  mov     [rsp+60h+var_40], rdx
0x18001db70  mov     r9d, 1
0x18001db76  xor     r8d, r8d
0x18001db79  mov     rdx, r14
0x18001db7c  mov     rax, [rax+28h]
0x18001db80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db85  mov     ebx, eax
0x18001db87  test    eax, eax
0x18001db89  js      loc_18001DECF
0x18001db8f  lea     r14, [rdi+0D0h]
0x18001db96  mov     [r14], r15
0x18001db99  cmp     [rbp+var_10], r15
0x18001db9d  jz      short loc_18001DB47
0x18001db9f  mov     rcx, [r13+0]
0x18001dba3  test    rcx, rcx
0x18001dba6  jz      loc_18001DC4F
0x18001dbac  lea     r15, [rdi+0C4h]
0x18001dbb3  mov     rax, [rcx]
0x18001dbb6  mov     [rsp+60h+var_40], r15
0x18001dbbb  mov     r9, [rbp+var_20]
0x18001dbbf  mov     r8d, 1
0x18001dbc5  mov     rdx, [rbp+pv]
0x18001dbc9  mov     rax, [rax+40h]
0x18001dbcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbd2  mov     ebx, eax
0x18001dbd4  test    eax, eax
0x18001dbd6  js      loc_18001DECC
0x18001dbdc  cmp     dword ptr [r15], 4
0x18001dbe0  jnz     short loc_18001DBF3
0x18001dbe2  mov     eax, [rdi+0C8h]
0x18001dbe8  mov     [r15], eax
0x18001dbeb  xor     r15d, r15d
0x18001dbee  jmp     loc_18001DD00
0x18001dbf3  cmp     dword ptr [r15], 2
0x18001dbf7  jnz     loc_18001DD57
0x18001dbfd  mov     r8, [rbp+var_20]
0x18001dc01  mov     r8, [r8]; unsigned __int64
0x18001dc04  mov     rdx, rdi; struct CRowInfo *
0x18001dc07  mov     rcx, rsi; this
0x18001dc0a  call    ?WriteRow@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_K@Z; CPersistStreamInit::WriteRow(CRowInfo &,unsigned __int64)
0x18001dc0f  mov     ebx, eax
0x18001dc11  test    eax, eax
0x18001dc13  js      loc_18001DECC
0x18001dc19  mov     eax, [rdi+54h]
0x18001dc1c  mov     [r14], rax
0x18001dc1f  mov     rcx, [r12]
0x18001dc23  test    rcx, rcx
0x18001dc26  jz      short loc_18001DC45
0x18001dc28  mov     rax, [rcx]
0x18001dc2b  lea     r9, [rdi+0D8h]
0x18001dc32  mov     r8, r14
0x18001dc35  mov     rdx, [rbp+var_20]
0x18001dc39  mov     rdx, [rdx]
0x18001dc3c  mov     rax, [rax+18h]
0x18001dc40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc45  mov     dword ptr [r15], 8
0x18001dc4c  xor     r15d, r15d
0x18001dc4f  mov     r8, [rbp+var_20]
0x18001dc53  mov     r8, [r8]; unsigned __int64
0x18001dc56  mov     rdx, rdi; struct CRowInfo *
0x18001dc59  mov     rcx, rsi; this
0x18001dc5c  call    ?WriteRow@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_K@Z; CPersistStreamInit::WriteRow(CRowInfo &,unsigned __int64)
0x18001dc61  mov     ebx, eax
0x18001dc63  test    eax, eax
0x18001dc65  js      loc_18001DECF
0x18001dc6b  mov     rbx, [rdi+0F0h]
0x18001dc72  test    rbx, rbx
0x18001dc75  jz      loc_18001DD00
0x18001dc7b  mov     eax, [rdi+0F8h]
0x18001dc81  mov     rcx, [rbp+var_20]
0x18001dc85  cmp     [rcx], rax
0x18001dc88  jb      short loc_18001DCE5
0x18001dc8a  mov     ecx, [rcx]
0x18001dc8c  add     ecx, 400h; int
0x18001dc92  call    ?MakeBitMap@@YAPEAVCBitMap@@JH@Z; MakeBitMap(long,int)
0x18001dc97  mov     rbx, rax
0x18001dc9a  test    rax, rax
0x18001dc9d  jz      loc_18001DA64
0x18001dca3  mov     rdx, [rdi+0F0h]
0x18001dcaa  mov     ecx, [rax]
0x18001dcac  cmp     ecx, [rdx]
0x18001dcae  cmovnb  ecx, [rdx]
0x18001dcb1  mov     r8d, ecx; Size
0x18001dcb4  add     rdx, 4; Src
0x18001dcb8  lea     rcx, [rax+4]; void *
0x18001dcbc  call    memcpy_0
0x18001dcc1  mov     rcx, [rdi+0F0h]; unsigned __int8 *
0x18001dcc8  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001dccd  mov     [rdi+0F0h], rbx
0x18001dcd4  mov     rcx, [rbp+var_20]
0x18001dcd8  mov     eax, [rcx]
0x18001dcda  add     eax, 400h
0x18001dcdf  mov     [rdi+0F8h], eax
0x18001dce5  movsxd  rax, dword ptr [rcx]
0x18001dce8  mov     rcx, rax
0x18001dceb  sar     rcx, 3
0x18001dcef  and     eax, 7
0x18001dcf2  lea     rdx, bits
0x18001dcf9  mov     al, [rax+rdx]
0x18001dcfc  or      [rcx+rbx+4], al
0x18001dd00  mov     rcx, [rdi+68h]
0x18001dd04  mov     rax, [rcx]
0x18001dd07  mov     [rsp+60h+var_38], r15
0x18001dd0c  mov     [rsp+60h+var_40], r15
0x18001dd11  xor     r9d, r9d
0x18001dd14  mov     r8, [rbp+var_20]
0x18001dd18  lea     edx, [r9+1]
0x18001dd1c  mov     rax, [rax+30h]
0x18001dd20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd25  mov     ebx, eax
0x18001dd27  test    eax, eax
0x18001dd29  js      loc_18001DECF
0x18001dd2f  mov     [r14], r15
0x18001dd32  mov     rcx, [rdi+0D8h]; pv
0x18001dd39  test    rcx, rcx
0x18001dd3c  jz      short loc_18001DD4B
0x18001dd3e  call    cs:__imp_CoTaskMemFree
0x18001dd44  mov     [rdi+0D8h], r15
0x18001dd4b  mov     rax, [rbp+var_20]
0x18001dd4f  mov     [rax], r15
0x18001dd52  jmp     loc_18001DB47
0x18001dd57  cmp     dword ptr [r15], 1
0x18001dd5b  jnz     loc_18001DC4C
0x18001dd61  mov     [rbp+arg_8], 1
0x18001dd65  mov     eax, [rdi+54h]
0x18001dd68  mov     [r14], rax
0x18001dd6b  mov     rcx, [r12]
0x18001dd6f  xor     r15d, r15d
0x18001dd72  test    rcx, rcx
0x18001dd75  jz      loc_18001DC4F
0x18001dd7b  mov     rax, [rcx]
0x18001dd7e  lea     r9, [rdi+0D8h]
0x18001dd85  mov     r8, r14
0x18001dd88  mov     rdx, [rbp+var_20]
0x18001dd8c  mov     rdx, [rdx]
0x18001dd8f  mov     rax, [rax+18h]
0x18001dd93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd98  jmp     loc_18001DC4F
0x18001dd9d  mov     edx, [rdi+0C4h]; unsigned int
0x18001dda3  mov     rcx, rsi; this
0x18001dda6  call    ?WriteStatusFooter@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::WriteStatusFooter(ulong)
0x18001ddab  mov     rcx, [rdi+70h]
0x18001ddaf  test    rcx, rcx
0x18001ddb2  jz      loc_18001DF71
0x18001ddb8  mov     [rbp+var_18], r15
0x18001ddbc  mov     [rbp+pv], r15
0x18001ddc0  mov     r13d, 8
0x18001ddc6  mov     [rdi+0C8h], r13d
0x18001ddcd  mov     rax, [rcx]
0x18001ddd0  neg     [rbp+arg_8]
0x18001ddd3  sbb     r8d, r8d
0x18001ddd6  add     r8d, 5
0x18001ddda  lea     rdx, [rbp+var_18]
0x18001ddde  mov     [rsp+60h+var_38], rdx
0x18001dde3  lea     rdx, [rbp+pv]
0x18001dde7  mov     [rsp+60h+var_40], rdx
0x18001ddec  lea     r9, [rbp+var_10]
0x18001ddf0  mov     rdx, r14
0x18001ddf3  mov     rax, [rax+38h]
0x18001ddf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddfc  mov     ebx, eax
0x18001ddfe  test    eax, eax
0x18001de00  jns     short loc_18001DE1C
0x18001de02  mov     rcx, [rbp+pv]; pv
0x18001de06  call    cs:__imp_CoTaskMemFree
0x18001de0c  nop
0x18001de0d  mov     rcx, [rbp+var_18]; pv
0x18001de11  call    cs:__imp_CoTaskMemFree
0x18001de17  jmp     loc_18001DECF
0x18001de1c  lea     r12, [rdi+0D8h]
0x18001de23  lea     r14, [rdi+0D0h]
0x18001de2a  mov     ebx, r15d
0x18001de2d  mov     rdx, [rbp+var_10]
0x18001de31  cmp     rbx, rdx
0x18001de34  jnb     loc_18001DF09
0x18001de3a  mov     rax, [rbp+var_18]
0x18001de3e  mov     ecx, [rax+rbx*4]
0x18001de41  mov     [rdi+0C4h], ecx
0x18001de47  cmp     ecx, 1
0x18001de4a  jnz     short loc_18001DE75
0x18001de4c  mov     eax, [rdi+54h]
0x18001de4f  mov     [r14], rax
0x18001de52  mov     rcx, [rdi+78h]
0x18001de56  test    rcx, rcx
0x18001de59  jz      short loc_18001DE75
0x18001de5b  mov     rax, [rcx]
0x18001de5e  mov     r9, r12
0x18001de61  mov     r8, r14
0x18001de64  mov     rdx, [rbp+pv]
0x18001de68  mov     rdx, [rdx+rbx*8]
0x18001de6c  mov     rax, [rax+18h]
0x18001de70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de75  mov     r8, [rbp+pv]
0x18001de79  mov     r8, [r8+rbx*8]; unsigned __int64
0x18001de7d  mov     rdx, rdi; struct CRowInfo *
  ... truncated ...
```
