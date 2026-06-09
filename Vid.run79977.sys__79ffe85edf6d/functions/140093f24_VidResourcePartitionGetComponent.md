# VidResourcePartitionGetComponent

- ea: `0x140093f24`
- end: `0x140094637`
- name: `VidResourcePartitionGetComponent`
- size: `1811`
- prototype: `__int64 __fastcall(int, int, int, int, void *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140094640`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x140022340`
- `0x140093f24`
- `0x140095abc`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x140094223`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14009433a`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140094223`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14009433a`
- `ntoskrnl!PsJobType` at `0x14009420d`
- `ntoskrnl!PsJobType` at `0x140094324`

## string_xrefs

- `0x140093fab`: `VidResourcePartitionGetComponent`
- `0x1400940a8`: `VidResourcePartitionGetComponent`
- `0x14009414a`: `VidResourcePartitionGetComponent`
- `0x140094261`: `VidResourcePartitionGetComponent`
- `0x140094378`: `VidResourcePartitionGetComponent`
- `0x1400944a1`: `VidResourcePartitionGetComponent`
- `0x140094577`: `VidResourcePartitionGetComponent`

## pseudocode

```c
__int64 __fastcall VidResourcePartitionGetComponent(
        __int64 a1,
        unsigned __int64 a2,
        int *a3,
        unsigned __int64 a4,
        void *a5,
        _DWORD *a6)
{
  unsigned int MemoryPartitionComponent; // ebx
  __int64 v9; // r11
  void *v10; // rdx
  int v11; // r8d
  int *v12; // rax
  __int64 v13; // r10
  __int64 v14; // r8
  __int64 v15; // rdi
  int v16; // r8d
  void *v17; // rcx
  void *v18; // rcx
  void **p_Src; // rdx
  int v20; // r8d
  __int64 v21; // r10
  __int64 v22; // r9
  int v23; // r8d
  int ObjectType; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  void *Src; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v31; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v32[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v34[16]; // [rsp+A0h] [rbp-60h] BYREF
  int *v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  int *v37; // [rsp+C0h] [rbp-40h]
  __int64 v38; // [rsp+C8h] [rbp-38h]
  __int64 v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  int *v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  __int64 *v43; // [rsp+F0h] [rbp-10h]
  __int64 v44; // [rsp+F8h] [rbp-8h]
  __int128 *v45; // [rsp+100h] [rbp+0h]
  __int64 v46; // [rsp+108h] [rbp+8h]

  Src = 0;
  if ( a2 >= 4 )
  {
    v14 = *a3;
    if ( (unsigned int)v14 > 4 )
    {
      MemoryPartitionComponent = -1073741808;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        return MemoryPartitionComponent;
      tlgCreate1Sz_char(v33, "VidResourcePartitionGetComponent");
      tlgCreate1Sz_char(v34, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
      LODWORD(v29) = 812;
      v35 = (int *)&v29;
      v10 = &unk_140048D22;
      v27 = v23;
      v37 = &v27;
      v39 = a1 + 8;
      v26 = *a3;
      v12 = &v26;
LABEL_39:
      v42 = v9;
      goto LABEL_40;
    }
    v15 = 2 * v14;
    if ( a2 < qword_140065200[2 * v14] + 4LL || a4 < qword_140065200[2 * v14 + 1] )
    {
      MemoryPartitionComponent = -1073741820;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v33, "VidResourcePartitionGetComponent");
        tlgCreate1Sz_char(v34, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
        LODWORD(v29) = 829;
        v35 = (int *)&v29;
        v10 = &unk_140048C96;
        v27 = v20;
        v37 = &v27;
        v39 = a1 + 8;
        v26 = *a3;
        v41 = &v26;
        v43 = &v28;
        v45 = &v31;
        ObjectType = 10;
        v42 = v9;
        v28 = v21;
        v44 = 8;
        *(_QWORD *)&v31 = v22;
        v46 = 8;
LABEL_41:
        v38 = v9;
        v36 = v9;
        goto LABEL_42;
      }
      return MemoryPartitionComponent;
    }
    if ( (_DWORD)v14 )
    {
      if ( (_DWORD)v14 == 1 )
      {
        v18 = *(void **)(a1 + 80);
        if ( v18 )
        {
          MemoryPartitionComponent = ObOpenObjectByPointer(v18, 0, 0, a3[1], (POBJECT_TYPE)PsJobType, 1, &Src);
          if ( (MemoryPartitionComponent & 0x80000000) != 0 )
          {
            if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
              return MemoryPartitionComponent;
            tlgCreate1Sz_char(v33, "VidResourcePartitionGetComponent");
            tlgCreate1Sz_char(v34, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
            LODWORD(v29) = 874;
            v35 = (int *)&v29;
            v10 = &unk_140048C10;
            v36 = 4;
            v37 = &v27;
            v39 = a1 + 8;
            v26 = *a3;
            v41 = &v26;
            LODWORD(v28) = a3[1];
            v43 = &v28;
            ObjectType = 9;
            v27 = MemoryPartitionComponent;
            v38 = 4;
            v42 = 4;
            v44 = 4;
LABEL_42:
            v40 = 16;
            tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v10, 0, 0, ObjectType, v32);
            return MemoryPartitionComponent;
          }
LABEL_29:
          p_Src = &Src;
LABEL_30:
          memmove(a5, p_Src, qword_140065200[v15 + 1]);
          MemoryPartitionComponent = 0;
          *a6 = qword_140065200[v15 + 1];
          return MemoryPartitionComponent;
        }
      }
      else
      {
        if ( (_DWORD)v14 != 2 )
        {
          if ( (unsigned int)(v14 - 3) >= 2 )
          {
            *a6 = 0;
            MemoryPartitionComponent = -1073741808;
            if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
              return MemoryPartitionComponent;
            tlgCreate1Sz_char(v33, "VidResourcePartitionGetComponent");
            tlgCreate1Sz_char(v34, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
            v26 = 955;
            v35 = &v26;
            v10 = &unk_140048AA2;
            LODWORD(v28) = v16;
            v37 = (int *)&v28;
            v39 = a1 + 8;
            v27 = *a3;
            v12 = &v27;
            goto LABEL_39;
          }
          MemoryPartitionComponent = VidResourcePartitionpGetMemoryPartitionComponent(
                                       a1,
                                       (unsigned int)a3[1],
                                       v14,
                                       &Src);
          if ( (MemoryPartitionComponent & 0x80000000) != 0 )
          {
            if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
              return MemoryPartitionComponent;
            tlgCreate1Sz_char(v33, "VidResourcePartitionGetComponent");
            tlgCreate1Sz_char(v34, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
            v27 = 940;
            v35 = &v27;
            v10 = &unk_140048B04;
            v36 = 4;
            v37 = &v26;
            v39 = a1 + 8;
            LODWORD(v28) = *a3;
            v41 = (int *)&v28;
            LODWORD(v29) = a3[1];
            v43 = &v29;
            ObjectType = 9;
            v26 = MemoryPartitionComponent;
            v38 = 4;
            v42 = 4;
            v44 = 4;
            goto LABEL_42;
          }
          goto LABEL_29;
        }
        v17 = *(void **)(a1 + 88);
        if ( v17 )
        {
          MemoryPartitionComponent = ObOpenObjectByPointer(v17, 0, 0, a3[1], (POBJECT_TYPE)PsJobType, 1, &Src);
          if ( (MemoryPartitionComponent & 0x80000000) != 0 )
          {
            if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
              return MemoryPartitionComponent;
            tlgCreate1Sz_char(v33, "VidResourcePartitionGetComponent");
            tlgCreate1Sz_char(v34, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
            LODWORD(v29) = 909;
            v35 = (int *)&v29;
            v10 = &unk_140048B8A;
            v36 = 4;
            v37 = &v27;
            v39 = a1 + 8;
            v26 = *a3;
            v41 = &v26;
            LODWORD(v28) = a3[1];
            v43 = &v28;
            ObjectType = 9;
            v27 = MemoryPartitionComponent;
            v38 = 4;
            v42 = 4;
            v44 = 4;
            goto LABEL_42;
          }
          goto LABEL_29;
        }
      }
    }
    else
    {
      p_Src = (void **)(a1 + 60);
      v31 = 0;
      if ( *(_OWORD *)(a1 + 60) )
        goto LABEL_30;
    }
    return (unsigned int)-1073741275;
  }
  MemoryPartitionComponent = -1073741820;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v33, "VidResourcePartitionGetComponent");
    tlgCreate1Sz_char(v34, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
    LODWORD(v28) = 798;
    v35 = (int *)&v28;
    v10 = &unk_140048D84;
    v26 = v11;
    v37 = &v26;
    v39 = a1 + 8;
    v12 = (int *)&v29;
    v29 = v13;
    v42 = 8;
LABEL_40:
    v41 = v12;
    ObjectType = 8;
    goto LABEL_41;
  }
  return MemoryPartitionComponent;
}

```

## disassembly

```asm
0x140093f24  mov     [rsp-8+arg_8], rbx
0x140093f29  push    rbp
0x140093f2a  push    rsi
0x140093f2b  push    rdi
0x140093f2c  push    r12
0x140093f2e  push    r13
0x140093f30  push    r14
0x140093f32  push    r15
0x140093f34  lea     rbp, [rsp-20h]
0x140093f39  sub     rsp, 120h
0x140093f40  mov     rax, cs:__security_cookie
0x140093f47  xor     rax, rsp
0x140093f4a  mov     [rbp+50h+var_40], rax
0x140093f4e  mov     r12, [rbp+50h+arg_20]
0x140093f55  xor     r13d, r13d
0x140093f58  mov     r15, [rbp+50h+arg_28]
0x140093f5f  mov     r14, r8
0x140093f62  mov     r10, rdx
0x140093f65  mov     [rsp+150h+Src], r13
0x140093f6a  mov     rsi, rcx
0x140093f6d  lea     r11d, [r13+4]
0x140093f71  cmp     rdx, r11
0x140093f74  jnb     loc_140094010
0x140093f7a  mov     eax, cs:dword_140065110
0x140093f80  mov     r8d, 0C0000004h
0x140093f86  mov     ebx, r8d
0x140093f89  cmp     eax, 2
0x140093f8c  jbe     loc_14009460D
0x140093f92  mov     edx, 100h
0x140093f97  lea     rcx, dword_140065110
0x140093f9e  call    _tlgKeywordOn
0x140093fa3  test    al, al
0x140093fa5  jz      loc_14009460D
0x140093fab  lea     rdx, aVidresourcepar_6; "VidResourcePartitionGetComponent"
0x140093fb2  lea     rcx, [rbp+50h+var_C0]
0x140093fb6  call    _tlgCreate1Sz_char
0x140093fbb  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140093fc2  lea     rcx, [rbp+50h+var_B0]
0x140093fc6  call    _tlgCreate1Sz_char
0x140093fcb  lea     rax, [rsp+150h+var_108]
0x140093fd0  mov     dword ptr [rsp+150h+var_108], 31Eh
0x140093fd8  mov     [rbp+50h+var_A0], rax
0x140093fdc  lea     rdx, unk_140048D84
0x140093fe3  lea     rax, [rsp+150h+var_110]
0x140093fe8  mov     [rsp+150h+var_110], r8d
0x140093fed  mov     [rbp+50h+var_90], rax
0x140093ff1  lea     rax, [rsi+8]
0x140093ff5  mov     [rbp+50h+var_80], rax
0x140093ff9  lea     rax, [rsp+150h+var_100]
0x140093ffe  mov     [rsp+150h+var_100], r10
0x140094003  mov     [rbp+50h+var_68], 8
0x14009400b  jmp     loc_1400945D5
0x140094010  movsxd  r8, dword ptr [r8]
0x140094013  cmp     r8d, r11d
0x140094016  ja      loc_140094546
0x14009401c  mov     rdi, r8
0x14009401f  lea     rcx, qword_140065200
0x140094026  add     rdi, rdi
0x140094029  mov     rax, [rcx+rdi*8]
0x14009402d  add     rax, r11
0x140094030  cmp     r10, rax
0x140094033  jb      loc_140094470
0x140094039  cmp     r9, [rcx+rdi*8+8]
0x14009403e  jb      loc_140094470
0x140094044  mov     ecx, r8d
0x140094047  test    r8d, r8d
0x14009404a  jz      loc_140094445
0x140094050  sub     ecx, 1
0x140094053  jz      loc_140094306
0x140094059  sub     ecx, 1
0x14009405c  jz      loc_1400941EF
0x140094062  sub     ecx, 1
0x140094065  jz      loc_140094107
0x14009406b  cmp     ecx, 1
0x14009406e  jz      loc_140094107
0x140094074  mov     [r15], r13d
0x140094077  mov     r8d, 0C0000010h
0x14009407d  mov     eax, cs:dword_140065110
0x140094083  mov     ebx, r8d
0x140094086  cmp     eax, 2
0x140094089  jbe     loc_14009460D
0x14009408f  mov     edx, 100h
0x140094094  lea     rcx, dword_140065110
0x14009409b  call    _tlgKeywordOn
0x1400940a0  test    al, al
0x1400940a2  jz      loc_14009460D
0x1400940a8  lea     rdx, aVidresourcepar_6; "VidResourcePartitionGetComponent"
0x1400940af  lea     rcx, [rbp+50h+var_C0]
0x1400940b3  call    _tlgCreate1Sz_char
0x1400940b8  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x1400940bf  lea     rcx, [rbp+50h+var_B0]
0x1400940c3  call    _tlgCreate1Sz_char
0x1400940c8  lea     rax, [rsp+150h+var_110]
0x1400940cd  mov     [rsp+150h+var_110], 3BBh
0x1400940d5  mov     [rbp+50h+var_A0], rax
0x1400940d9  lea     rdx, unk_140048AA2
0x1400940e0  lea     rax, [rsp+150h+var_108]
0x1400940e5  mov     dword ptr [rsp+150h+var_108], r8d
0x1400940ea  mov     [rbp+50h+var_90], rax
0x1400940ee  lea     rax, [rsi+8]
0x1400940f2  mov     [rbp+50h+var_80], rax
0x1400940f6  mov     eax, [r14]
0x1400940f9  mov     [rsp+150h+var_10C], eax
0x1400940fd  lea     rax, [rsp+150h+var_10C]
0x140094102  jmp     loc_1400945D1
0x140094107  mov     edx, [r14+4]
0x14009410b  lea     r9, [rsp+150h+Src]
0x140094110  mov     rcx, rsi
0x140094113  call    VidResourcePartitionpGetMemoryPartitionComponent
0x140094118  mov     ebx, eax
0x14009411a  test    eax, eax
0x14009411c  jns     loc_14009441D
0x140094122  mov     ecx, cs:dword_140065110
0x140094128  cmp     ecx, 2
0x14009412b  jbe     loc_14009460D
0x140094131  mov     edx, 100h
0x140094136  lea     rcx, dword_140065110
0x14009413d  call    _tlgKeywordOn
0x140094142  test    al, al
0x140094144  jz      loc_14009460D
0x14009414a  lea     rdx, aVidresourcepar_6; "VidResourcePartitionGetComponent"
0x140094151  lea     rcx, [rbp+50h+var_C0]
0x140094155  call    _tlgCreate1Sz_char
0x14009415a  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140094161  lea     rcx, [rbp+50h+var_B0]
0x140094165  call    _tlgCreate1Sz_char
0x14009416a  lea     rax, [rsp+150h+var_10C]
0x14009416f  mov     [rsp+150h+var_10C], 3ACh
0x140094177  mov     [rbp+50h+var_A0], rax
0x14009417b  lea     rdx, unk_140048B04
0x140094182  lea     rax, [rsp+150h+var_110]
0x140094187  mov     [rbp+50h+var_98], 4
0x14009418f  mov     [rbp+50h+var_90], rax
0x140094193  lea     rax, [rsi+8]
0x140094197  mov     [rbp+50h+var_80], rax
0x14009419b  mov     eax, [r14]
0x14009419e  mov     dword ptr [rsp+150h+var_108], eax
0x1400941a2  lea     rax, [rsp+150h+var_108]
0x1400941a7  mov     [rbp+50h+var_70], rax
0x1400941ab  mov     eax, [r14+4]
0x1400941af  mov     dword ptr [rsp+150h+var_100], eax
0x1400941b3  lea     rax, [rsp+150h+var_100]
0x1400941b8  mov     [rbp+50h+var_60], rax
0x1400941bc  lea     rax, [rsp+150h+var_E0]
0x1400941c1  mov     qword ptr [rsp+150h+AccessMode], rax
0x1400941c6  mov     dword ptr [rsp+150h+ObjectType], 9
0x1400941ce  mov     [rsp+150h+var_110], ebx
0x1400941d2  mov     [rbp+50h+var_88], 4
0x1400941da  mov     [rbp+50h+var_68], 4
0x1400941e2  mov     [rbp+50h+var_58], 4
0x1400941ea  jmp     loc_1400945F3
0x1400941ef  mov     rcx, [rsi+58h]; Object
0x1400941f3  test    rcx, rcx
0x1400941f6  jz      loc_140094466
0x1400941fc  mov     r9d, [r14+4]; DesiredAccess
0x140094200  lea     rax, [rsp+150h+Src]
0x140094205  mov     [rsp+150h+Handle], rax; Handle
0x14009420a  xor     r8d, r8d; PassedAccessState
0x14009420d  mov     rax, cs:PsJobType
0x140094214  mov     [rsp+150h+AccessMode], 1; AccessMode
0x140094219  mov     rdx, [rax]
0x14009421c  mov     [rsp+150h+ObjectType], rdx; ObjectType
0x140094221  xor     edx, edx; HandleAttributes
0x140094223  call    cs:__imp_ObOpenObjectByPointer
0x14009422a  nop     dword ptr [rax+rax+00h]
0x14009422f  mov     ebx, eax
0x140094231  test    eax, eax
0x140094233  jns     loc_14009441D
0x140094239  mov     eax, cs:dword_140065110
0x14009423f  cmp     eax, 2
0x140094242  jbe     loc_14009460D
0x140094248  mov     edx, 100h
0x14009424d  lea     rcx, dword_140065110
0x140094254  call    _tlgKeywordOn
0x140094259  test    al, al
0x14009425b  jz      loc_14009460D
0x140094261  lea     rdx, aVidresourcepar_6; "VidResourcePartitionGetComponent"
0x140094268  lea     rcx, [rbp+50h+var_C0]
0x14009426c  call    _tlgCreate1Sz_char
0x140094271  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140094278  lea     rcx, [rbp+50h+var_B0]
0x14009427c  call    _tlgCreate1Sz_char
0x140094281  lea     rax, [rsp+150h+var_100]
0x140094286  mov     dword ptr [rsp+150h+var_100], 38Dh
0x14009428e  mov     [rbp+50h+var_A0], rax
0x140094292  lea     rdx, unk_140048B8A
0x140094299  lea     rax, [rsp+150h+var_10C]
0x14009429e  mov     [rbp+50h+var_98], 4
0x1400942a6  mov     [rbp+50h+var_90], rax
0x1400942aa  lea     rax, [rsi+8]
0x1400942ae  mov     [rbp+50h+var_80], rax
0x1400942b2  mov     eax, [r14]
0x1400942b5  mov     [rsp+150h+var_110], eax
0x1400942b9  lea     rax, [rsp+150h+var_110]
0x1400942be  mov     [rbp+50h+var_70], rax
0x1400942c2  mov     eax, [r14+4]
0x1400942c6  mov     dword ptr [rsp+150h+var_108], eax
0x1400942ca  lea     rax, [rsp+150h+var_108]
0x1400942cf  mov     [rbp+50h+var_60], rax
0x1400942d3  lea     rax, [rsp+150h+var_E0]
0x1400942d8  mov     qword ptr [rsp+150h+AccessMode], rax
0x1400942dd  mov     dword ptr [rsp+150h+ObjectType], 9
0x1400942e5  mov     [rsp+150h+var_10C], ebx
0x1400942e9  mov     [rbp+50h+var_88], 4
0x1400942f1  mov     [rbp+50h+var_68], 4
0x1400942f9  mov     [rbp+50h+var_58], 4
0x140094301  jmp     loc_1400945F3
0x140094306  mov     rcx, [rsi+50h]; Object
0x14009430a  test    rcx, rcx
0x14009430d  jz      loc_140094466
0x140094313  mov     r9d, [r14+4]; DesiredAccess
0x140094317  lea     rax, [rsp+150h+Src]
0x14009431c  mov     [rsp+150h+Handle], rax; Handle
0x140094321  xor     r8d, r8d; PassedAccessState
0x140094324  mov     rax, cs:PsJobType
0x14009432b  mov     [rsp+150h+AccessMode], 1; AccessMode
0x140094330  mov     rdx, [rax]
0x140094333  mov     [rsp+150h+ObjectType], rdx; ObjectType
0x140094338  xor     edx, edx; HandleAttributes
0x14009433a  call    cs:__imp_ObOpenObjectByPointer
0x140094341  nop     dword ptr [rax+rax+00h]
0x140094346  mov     ebx, eax
0x140094348  test    eax, eax
0x14009434a  jns     loc_14009441D
0x140094350  mov     eax, cs:dword_140065110
0x140094356  cmp     eax, 2
0x140094359  jbe     loc_14009460D
0x14009435f  mov     edx, 100h
0x140094364  lea     rcx, dword_140065110
0x14009436b  call    _tlgKeywordOn
0x140094370  test    al, al
0x140094372  jz      loc_14009460D
0x140094378  lea     rdx, aVidresourcepar_6; "VidResourcePartitionGetComponent"
0x14009437f  lea     rcx, [rbp+50h+var_C0]
0x140094383  call    _tlgCreate1Sz_char
0x140094388  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x14009438f  lea     rcx, [rbp+50h+var_B0]
0x140094393  call    _tlgCreate1Sz_char
0x140094398  lea     rax, [rsp+150h+var_100]
0x14009439d  mov     dword ptr [rsp+150h+var_100], 36Ah
0x1400943a5  mov     [rbp+50h+var_A0], rax
0x1400943a9  lea     rdx, unk_140048C10
0x1400943b0  lea     rax, [rsp+150h+var_10C]
0x1400943b5  mov     [rbp+50h+var_98], 4
0x1400943bd  mov     [rbp+50h+var_90], rax
0x1400943c1  lea     rax, [rsi+8]
0x1400943c5  mov     [rbp+50h+var_80], rax
0x1400943c9  mov     eax, [r14]
0x1400943cc  mov     [rsp+150h+var_110], eax
0x1400943d0  lea     rax, [rsp+150h+var_110]
0x1400943d5  mov     [rbp+50h+var_70], rax
0x1400943d9  mov     eax, [r14+4]
0x1400943dd  mov     dword ptr [rsp+150h+var_108], eax
0x1400943e1  lea     rax, [rsp+150h+var_108]
0x1400943e6  mov     [rbp+50h+var_60], rax
0x1400943ea  lea     rax, [rsp+150h+var_E0]
0x1400943ef  mov     qword ptr [rsp+150h+AccessMode], rax
0x1400943f4  mov     dword ptr [rsp+150h+ObjectType], 9
0x1400943fc  mov     [rsp+150h+var_10C], ebx
0x140094400  mov     [rbp+50h+var_88], 4
0x140094408  mov     [rbp+50h+var_68], 4
0x140094410  mov     [rbp+50h+var_58], 4
0x140094418  jmp     loc_1400945F3
0x14009441d  lea     rdx, [rsp+150h+Src]; Src
0x140094422  lea     rbx, qword_140065200
0x140094429  mov     rcx, r12; void *
0x14009442c  mov     r8, [rbx+rdi*8+8]; Size
0x140094431  call    memmove
0x140094436  mov     eax, [rbx+rdi*8+8]
0x14009443a  mov     ebx, r13d
0x14009443d  mov     [r15], eax
0x140094440  jmp     loc_14009460D
0x140094445  xorps   xmm0, xmm0
0x140094448  lea     rdx, [rsi+3Ch]
0x14009444c  movq    rax, xmm0
0x140094451  movups  [rsp+150h+var_F0], xmm0
0x140094456  cmp     [rdx], rax
0x140094459  jnz     short loc_140094422
0x14009445b  mov     rax, [rdx+8]
0x14009445f  cmp     rax, qword ptr [rsp+150h+var_F0+8]
0x140094464  jnz     short loc_140094422
0x140094466  mov     ebx, 0C0000225h
0x14009446b  jmp     loc_14009460D
0x140094470  mov     eax, cs:dword_140065110
0x140094476  mov     r8d, 0C0000004h
0x14009447c  mov     ebx, r8d
0x14009447f  cmp     eax, 2
0x140094482  jbe     loc_14009460D
0x140094488  mov     edx, 100h
0x14009448d  lea     rcx, dword_140065110
0x140094494  call    _tlgKeywordOn
0x140094499  test    al, al
0x14009449b  jz      loc_14009460D
0x1400944a1  lea     rdx, aVidresourcepar_6; "VidResourcePartitionGetComponent"
0x1400944a8  lea     rcx, [rbp+50h+var_C0]
0x1400944ac  call    _tlgCreate1Sz_char
0x1400944b1  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x1400944b8  lea     rcx, [rbp+50h+var_B0]
0x1400944bc  call    _tlgCreate1Sz_char
0x1400944c1  lea     rax, [rsp+150h+var_100]
  ... truncated ...
```
