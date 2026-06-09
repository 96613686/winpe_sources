# ABO_NODE::GetInheritedData(ACCESS_GRANTED,ushort const *,_METADATA_RECORD *,ulong *)

- ea: `0x180008f28`
- end: `0x180009480`
- name: `?GetInheritedData@ABO_NODE@@QEAAJW4ACCESS_GRANTED@@PEBGPEAU_METADATA_RECORD@@PEAK@Z`
- size: `1368`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x18000dea0`
- `0x18001d9b0`

## callees

- `0x180003402`
- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x18000473c`
- `0x180005e94`
- `0x1800077dc`
- `0x180007a80`
- `0x180008f28`
- `0x18000a63c`
- `0x18000fc50`
- `0x18000fec4`
- `0x18000ffd8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800093da`
- `msvcrt!_wcsicmp` at `0x1800093da`
- `msvcrt!wcschr` at `0x1800090a9`
- `msvcrt!wcschr` at `0x1800090a9`
- `msvcrt!wcstoul` at `0x180009409`
- `msvcrt!wcstoul` at `0x180009409`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180009074`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800090f6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180009113`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800091c0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180009074`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800090f6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180009113`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800091c0`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800093ca`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800093f5`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800093ca`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800093f5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000926e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000926e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008fa0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008fc5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008fea`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008fa0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008fc5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008fea`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000916d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009177`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009181`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000916d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009177`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009181`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800091d4`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800091d4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000909b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800090bf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800090d2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009106`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800091b3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800091de`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000909b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800090bf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800090d2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009106`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800091b3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800091de`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180009256`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800092bb`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180009256`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800092bb`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800090e2`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800090e2`

## pseudocode

```c
__int64 __fastcall ABO_NODE::GetInheritedData(
        ABO_NODE *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct _METADATA_RECORD *a4,
        unsigned int *a5)
{
  PROPERTY_MAPPING *v7; // r13
  ABO_NODE *v9; // r12
  PROPERTY_MAPPING *v10; // r15
  HANDLE_ENTRY *v11; // rsi
  int v12; // ebx
  const unsigned __int16 *v13; // rdx
  const wchar_t *Str; // rax
  wchar_t *v15; // rax
  wchar_t *v16; // r13
  __int64 v17; // rbx
  const unsigned __int16 *v18; // rax
  const unsigned __int16 *v19; // rax
  const unsigned __int16 *v21; // rax
  const unsigned __int16 *v22; // rax
  int v23; // eax
  unsigned int dwMDIdentifier; // edx
  struct PROPERTY_ENTRY *v25; // rbx
  int Key; // eax
  const void *v27; // rdx
  unsigned int v28; // eax
  _DWORD *v29; // rcx
  int v30; // eax
  const wchar_t *v31; // rax
  __int64 v32; // rcx
  const wchar_t *v33; // rax
  __int64 v34; // rax
  unsigned __int8 *pbMDData; // rcx
  struct PROPERTY_ENTRY *v36; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+28h] [rbp-D8h]
  ABO_NODE *v39; // [rsp+30h] [rbp-D0h] BYREF
  struct PROPERTY_ENTRY *v40; // [rsp+38h] [rbp-C8h] BYREF
  DWORD dwMDAttributes; // [rsp+40h] [rbp-C0h]
  unsigned int *v42; // [rsp+48h] [rbp-B8h]
  __int64 v43; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *EndPtr; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD Src[2]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v46; // [rsp+80h] [rbp-80h]
  _BYTE v47[56]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v48[56]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v49[56]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 v50[256]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v51[256]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v52[256]; // [rsp+530h] [rbp+430h] BYREF

  v7 = 0;
  v42 = a5;
  v39 = 0;
  v9 = 0;
  memset_0(v50, 0, sizeof(v50));
  STRU::STRU((STRU *)v48, v50, 0x100u);
  memset_0(v51, 0, sizeof(v51));
  STRU::STRU((STRU *)v47, v51, 0x100u);
  memset_0(v52, 0, sizeof(v52));
  STRU::STRU((STRU *)v49, v52, 0x100u);
  v10 = 0;
  v43 = 0;
  v11 = 0;
  EndPtr = 0;
  v46 = aIiswebvirtuald[16];
  v36 = 0;
  v40 = 0;
  Src[0] = *(_OWORD *)L"IIsWebVirtualDir";
  Src[1] = *(_OWORD *)L"rtualDir";
  if ( !a4 || !a3 )
  {
    a1 = 0;
    v12 = -2147024809;
LABEL_14:
    if ( v9 )
      ABO_NODE::DereferenceAboNode(v9);
    if ( a1 )
      ABO_NODE::DereferenceAboNode(a1);
    if ( v10 )
      PROPERTY_MAPPING::DereferencePropertyMapping(v10);
    if ( v7 )
      PROPERTY_MAPPING::DereferencePropertyMapping(v7);
    if ( v11 )
      HANDLE_ENTRY::DereferenceHandleEntry(v11);
    goto LABEL_24;
  }
  if ( !(unsigned int)PROPERTY_ENTRY::IsReadAccessAllowed(a4->dwMDIdentifier, a2) )
  {
    v12 = -2147024891;
    goto LABEL_24;
  }
  v13 = a3 + 1;
  dwMDAttributes = a4->dwMDAttributes;
  if ( *a3 != 47 )
    v13 = a3;
  v12 = STRU::Copy((STRU *)v47, v13);
  if ( v12 >= 0 )
  {
    v12 = 0;
    v38 = 0;
    ABO_NODE::ReferenceAboNode(a1);
    while ( !STRU::IsEmpty((STRU *)v47) )
    {
      Str = STRU::QueryStr((STRU *)v47);
      v15 = wcschr(Str, 0x2Fu);
      v16 = v15;
      if ( v15 )
      {
        v17 = v15 - STRU::QueryStr((STRU *)v47);
        v18 = STRU::QueryStr((STRU *)v47);
        v12 = STRU::Copy((STRU *)v48, v18, v17);
        if ( v12 < 0 )
          goto LABEL_13;
        v12 = STRU::Copy((STRU *)v49, v16 + 1);
        if ( v12 < 0 )
          goto LABEL_13;
        v19 = STRU::QueryStr((STRU *)v49);
        v12 = STRU::Copy((STRU *)v47, v19);
        if ( v12 < 0 )
          goto LABEL_13;
      }
      else
      {
        v21 = STRU::QueryStr((STRU *)v47);
        v12 = STRU::Copy((STRU *)v48, v21);
        if ( v12 < 0 )
          goto LABEL_13;
        STRU::Reset((STRU *)v47);
      }
      v22 = STRU::QueryStr((STRU *)v48);
      v23 = ABO_NODE::QueryChildNodeByName(a1, v22, &v39);
      v12 = v23;
      if ( v23 >= 0 )
      {
        ABO_NODE::ReferenceAboNode(v39);
        LODWORD(v7) = 1;
        ABO_NODE::DereferenceAboNode(a1);
        a1 = v39;
        dwMDIdentifier = a4->dwMDIdentifier;
        v12 = 0;
        v9 = 0;
        v39 = 0;
        if ( (int)PROPERTY_BAG::FindEntry((ABO_NODE *)((char *)a1 + 184), dwMDIdentifier, &v40) < 0 )
        {
          v36 = v40;
        }
        else
        {
          if ( STRU::IsEmpty((STRU *)v47) )
          {
            v38 = 0;
            v25 = v40;
          }
          else
          {
            v25 = v40;
            v38 = 1;
            if ( (*((_BYTE *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v40 + 16)) + 4) & 1) == 0 )
            {
              PROPERTY_MAPPING::DereferencePropertyMapping(v25);
              v25 = 0;
            }
          }
          if ( v10 )
            PROPERTY_MAPPING::DereferencePropertyMapping(v10);
          v10 = v25;
          v12 = 0;
          v36 = 0;
          v40 = 0;
        }
      }
      else
      {
        v9 = v39;
        if ( v23 != -2147023483 )
          goto LABEL_13;
        v12 = 0;
        LODWORD(v7) = 0;
      }
    }
    if ( (dwMDAttributes & 2) == 0 && !(_DWORD)v7 )
    {
      v12 = -2147024893;
      goto LABEL_13;
    }
    if ( !v10 )
    {
      Key = CTypedHashTable<HANDLE_TABLE,HANDLE_ENTRY,unsigned long,CLKRHashTable>::FindKey(
              (char *)g_pPropertyIdTable + 8,
              a4->dwMDIdentifier,
              &v43);
      v11 = (HANDLE_ENTRY *)v43;
      if ( Key || (v27 = *(const void **)(v43 + 96)) == 0 )
      {
        if ( a4->dwMDIdentifier != 1002
          || !a1
          || (v31 = STRU::QueryStr((ABO_NODE *)((char *)a1 + 56)), _wcsicmp(v31, L"ROOT"))
          || (v32 = *((_QWORD *)a1 + 2)) == 0
          || (v33 = STRU::QueryStr((STRU *)(v32 + 56)), !wcstoul(v33, &EndPtr, 10))
          || *EndPtr )
        {
          v12 = -2146646015;
          goto LABEL_13;
        }
        v34 = -1;
        do
          ++v34;
        while ( *((_WORD *)Src + v34) );
        v28 = 2 * v34 + 2;
        if ( a4->dwMDDataLen >= v28 )
        {
          pbMDData = a4->pbMDData;
          *(_QWORD *)&a4->dwMDIdentifier = 1002;
          a4->dwMDUserType = 1;
          a4->dwMDDataType = 2;
          a4->dwMDDataLen = v28;
          memcpy_0(pbMDData, Src, v28);
          goto LABEL_13;
        }
      }
      else
      {
        v28 = *(_DWORD *)(v43 + 104);
        if ( a4->dwMDDataLen >= v28 )
        {
          memcpy_0(a4->pbMDData, v27, *(unsigned int *)(v43 + 104));
          a4->dwMDDataLen = *((_DWORD *)v11 + 26);
          if ( *((_DWORD *)v11 + 22) )
          {
            v29 = (_DWORD *)**((_QWORD **)v11 + 10);
            a4->dwMDDataType = v29[38];
            a4->dwMDUserType = v29[37];
            v30 = v29[39];
          }
          else
          {
            a4->dwMDDataType = *((_DWORD *)v11 + 27);
            a4->dwMDUserType = *((_DWORD *)v11 + 28);
            v30 = *((_DWORD *)v11 + 29);
          }
          a4->dwMDAttributes = v30 | 0x20;
          goto LABEL_13;
        }
      }
      v12 = -2147024774;
      *v42 = v28;
LABEL_13:
      v7 = v36;
      goto LABEL_14;
    }
    v12 = PROPERTY_ENTRY::CopyData(v10, a4, v42);
    if ( v12 < 0 )
      goto LABEL_13;
    v7 = v36;
    if ( v38 )
      a4->dwMDAttributes |= 0x20u;
    goto LABEL_14;
  }
LABEL_24:
  STRU::~STRU((STRU *)v49);
  STRU::~STRU((STRU *)v47);
  STRU::~STRU((STRU *)v48);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180008f28  mov     [rsp-8+arg_8], rbx
0x180008f2d  push    rbp
0x180008f2e  push    rsi
0x180008f2f  push    rdi
0x180008f30  push    r12
0x180008f32  push    r13
0x180008f34  push    r14
0x180008f36  push    r15
0x180008f38  lea     rbp, [rsp-640h]
0x180008f40  sub     rsp, 740h
0x180008f47  mov     rax, cs:__security_cookie
0x180008f4e  xor     rax, rsp
0x180008f51  mov     [rbp+670h+var_40], rax
0x180008f58  mov     rax, [rbp+670h+arg_20]
0x180008f5f  mov     rbx, r8
0x180008f62  mov     [rsp+770h+var_748], edx
0x180008f66  mov     r14, rcx
0x180008f69  xor     r13d, r13d
0x180008f6c  mov     [rsp+770h+var_728], rax
0x180008f71  mov     r15d, 200h
0x180008f77  mov     [rsp+770h+var_740], r13
0x180008f7c  mov     r8d, r15d; Size
0x180008f7f  lea     rcx, [rbp+670h+var_640]; void *
0x180008f83  xor     edx, edx; Val
0x180008f85  mov     rdi, r9
0x180008f88  mov     r12d, r13d
0x180008f8b  call    memset_0
0x180008f90  mov     esi, 100h
0x180008f95  lea     rdx, [rbp+670h+var_640]
0x180008f99  mov     r8d, esi
0x180008f9c  lea     rcx, [rbp+670h+var_6B0]
0x180008fa0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180008fa6  mov     r8d, r15d; Size
0x180008fa9  lea     rcx, [rbp+670h+var_440]; void *
0x180008fb0  xor     edx, edx; Val
0x180008fb2  call    memset_0
0x180008fb7  mov     r8d, esi
0x180008fba  lea     rdx, [rbp+670h+var_440]
0x180008fc1  lea     rcx, [rbp+670h+var_6E8]
0x180008fc5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180008fcb  mov     r8d, r15d; Size
0x180008fce  lea     rcx, [rbp+670h+var_240]; void *
0x180008fd5  xor     edx, edx; Val
0x180008fd7  call    memset_0
0x180008fdc  mov     r8d, esi
0x180008fdf  lea     rdx, [rbp+670h+var_240]
0x180008fe6  lea     rcx, [rbp+670h+var_678]
0x180008fea  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180008ff0  movups  xmm0, xmmword ptr cs:aIiswebvirtuald; "IIsWebVirtualDir"
0x180008ff7  xor     eax, eax
0x180008ff9  mov     r15d, r13d
0x180008ffc  mov     [rsp+770h+var_720], rax
0x180009001  mov     esi, eax
0x180009003  mov     [rsp+770h+EndPtr], rax
0x180009008  movzx   eax, word ptr cs:aIiswebvirtuald+20h; ""
0x18000900f  mov     [rbp+670h+var_6F0], ax
0x180009013  mov     [rsp+770h+var_750], r13
0x180009018  mov     [rsp+770h+var_738], r13
0x18000901d  movups  xmm1, xmmword ptr cs:aIiswebvirtuald+10h; "rtualDir"
0x180009024  movups  [rsp+770h+Src], xmm0
0x180009029  movups  [rsp+770h+var_700], xmm1
0x18000902e  test    rdi, rdi
0x180009031  jz      loc_180009473
0x180009037  test    rbx, rbx
0x18000903a  jz      loc_180009473
0x180009040  mov     edx, [rsp+770h+var_748]
0x180009044  mov     ecx, [rdi]
0x180009046  call    ?IsReadAccessAllowed@PROPERTY_ENTRY@@SAHKW4ACCESS_GRANTED@@@Z; PROPERTY_ENTRY::IsReadAccessAllowed(ulong,ACCESS_GRANTED)
0x18000904b  test    eax, eax
0x18000904d  jnz     short loc_180009059
0x18000904f  mov     ebx, 80070005h
0x180009054  jmp     loc_180009169
0x180009059  mov     eax, [rdi+4]
0x18000905c  lea     rdx, [rbx+2]
0x180009060  mov     [rsp+770h+var_730], eax
0x180009064  lea     rcx, [rbp+670h+var_6E8]
0x180009068  mov     eax, 2Fh ; '/'
0x18000906d  cmp     [rbx], ax
0x180009070  cmovnz  rdx, rbx
0x180009074  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000907a  mov     ebx, eax
0x18000907c  test    eax, eax
0x18000907e  js      loc_180009169
0x180009084  xor     ebx, ebx
0x180009086  mov     rcx, r14; this
0x180009089  mov     [rsp+770h+var_748], ebx
0x18000908d  call    ?ReferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::ReferenceAboNode(void)
0x180009092  jmp     loc_1800092B7
0x180009097  lea     rcx, [rbp+670h+var_6E8]
0x18000909b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800090a1  mov     rcx, rax; Str
0x1800090a4  mov     edx, 2Fh ; '/'; Ch
0x1800090a9  call    cs:__imp_wcschr
0x1800090af  lea     rcx, [rbp+670h+var_6E8]
0x1800090b3  mov     r13, rax
0x1800090b6  test    rax, rax
0x1800090b9  jz      loc_1800091B3
0x1800090bf  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800090c5  mov     rbx, r13
0x1800090c8  lea     rcx, [rbp+670h+var_6E8]
0x1800090cc  sub     rbx, rax
0x1800090cf  sar     rbx, 1
0x1800090d2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800090d8  mov     r8d, ebx
0x1800090db  lea     rcx, [rbp+670h+var_6B0]
0x1800090df  mov     rdx, rax
0x1800090e2  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800090e8  mov     ebx, eax
0x1800090ea  test    eax, eax
0x1800090ec  js      short loc_180009123
0x1800090ee  lea     rdx, [r13+2]
0x1800090f2  lea     rcx, [rbp+670h+var_678]
0x1800090f6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800090fc  mov     ebx, eax
0x1800090fe  test    eax, eax
0x180009100  js      short loc_180009123
0x180009102  lea     rcx, [rbp+670h+var_678]
0x180009106  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000910c  mov     rdx, rax
0x18000910f  lea     rcx, [rbp+670h+var_6E8]
0x180009113  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180009119  mov     ebx, eax
0x18000911b  test    eax, eax
0x18000911d  jns     loc_1800091DA
0x180009123  mov     r13, [rsp+770h+var_750]
0x180009128  test    r12, r12
0x18000912b  jz      short loc_180009135
0x18000912d  mov     rcx, r12; this
0x180009130  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180009135  test    r14, r14
0x180009138  jz      short loc_180009142
0x18000913a  mov     rcx, r14; this
0x18000913d  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180009142  test    r15, r15
0x180009145  jz      short loc_18000914F
0x180009147  mov     rcx, r15; this
0x18000914a  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18000914f  test    r13, r13
0x180009152  jz      short loc_18000915C
0x180009154  mov     rcx, r13; this
0x180009157  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18000915c  test    rsi, rsi
0x18000915f  jz      short loc_180009169
0x180009161  mov     rcx, rsi; this
0x180009164  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x180009169  lea     rcx, [rbp+670h+var_678]
0x18000916d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009173  lea     rcx, [rbp+670h+var_6E8]
0x180009177  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000917d  lea     rcx, [rbp+670h+var_6B0]
0x180009181  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009187  mov     eax, ebx
0x180009189  mov     rcx, [rbp+670h+var_40]
0x180009190  xor     rcx, rsp; StackCookie
0x180009193  call    __security_check_cookie
0x180009198  mov     rbx, [rsp+770h+arg_8]
0x1800091a0  add     rsp, 740h
0x1800091a7  pop     r15
0x1800091a9  pop     r14
0x1800091ab  pop     r13
0x1800091ad  pop     r12
0x1800091af  pop     rdi
0x1800091b0  pop     rsi
0x1800091b1  pop     rbp
0x1800091b2  retn
0x1800091b3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800091b9  mov     rdx, rax
0x1800091bc  lea     rcx, [rbp+670h+var_6B0]
0x1800091c0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800091c6  mov     ebx, eax
0x1800091c8  test    eax, eax
0x1800091ca  js      loc_180009123
0x1800091d0  lea     rcx, [rbp+670h+var_6E8]
0x1800091d4  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x1800091da  lea     rcx, [rbp+670h+var_6B0]
0x1800091de  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800091e4  lea     r8, [rsp+770h+var_740]; struct ABO_NODE **
0x1800091e9  mov     rcx, r14; this
0x1800091ec  mov     rdx, rax; unsigned __int16 *
0x1800091ef  call    ?QueryChildNodeByName@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::QueryChildNodeByName(ushort const *,ABO_NODE * *)
0x1800091f4  mov     ebx, eax
0x1800091f6  test    eax, eax
0x1800091f8  jns     short loc_180009214
0x1800091fa  mov     r12, [rsp+770h+var_740]
0x1800091ff  cmp     eax, 80070585h
0x180009204  jnz     loc_180009123
0x18000920a  xor     ebx, ebx
0x18000920c  mov     r13d, ebx
0x18000920f  jmp     loc_1800092B7
0x180009214  mov     rcx, [rsp+770h+var_740]; this
0x180009219  call    ?ReferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::ReferenceAboNode(void)
0x18000921e  mov     rcx, r14; this
0x180009221  mov     r13d, 1
0x180009227  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000922c  mov     r14, [rsp+770h+var_740]
0x180009231  lea     r8, [rsp+770h+var_738]; struct PROPERTY_ENTRY **
0x180009236  mov     edx, [rdi]; unsigned int
0x180009238  xor     ebx, ebx
0x18000923a  mov     r12d, ebx
0x18000923d  mov     [rsp+770h+var_740], rbx
0x180009242  lea     rcx, [r14+0B8h]; this
0x180009249  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x18000924e  test    eax, eax
0x180009250  js      short loc_1800092AD
0x180009252  lea     rcx, [rbp+670h+var_6E8]
0x180009256  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18000925c  test    al, al
0x18000925e  jnz     short loc_180009286
0x180009260  mov     rbx, [rsp+770h+var_738]
0x180009265  mov     [rsp+770h+var_748], r13d
0x18000926a  lea     rcx, [rbx+10h]
0x18000926e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180009274  test    [rax+4], r13b
0x180009278  jnz     short loc_18000928F
0x18000927a  mov     rcx, rbx; this
0x18000927d  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180009282  xor     ebx, ebx
0x180009284  jmp     short loc_18000928F
0x180009286  mov     [rsp+770h+var_748], ebx
0x18000928a  mov     rbx, [rsp+770h+var_738]
0x18000928f  test    r15, r15
0x180009292  jz      short loc_18000929C
0x180009294  mov     rcx, r15; this
0x180009297  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18000929c  mov     r15, rbx
0x18000929f  xor     ebx, ebx
0x1800092a1  mov     [rsp+770h+var_750], rbx
0x1800092a6  mov     [rsp+770h+var_738], rbx
0x1800092ab  jmp     short loc_1800092B7
0x1800092ad  mov     rax, [rsp+770h+var_738]
0x1800092b2  mov     [rsp+770h+var_750], rax
0x1800092b7  lea     rcx, [rbp+670h+var_6E8]
0x1800092bb  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x1800092c1  test    al, al
0x1800092c3  jz      loc_180009097
0x1800092c9  test    byte ptr [rsp+770h+var_730], 2
0x1800092ce  jnz     short loc_1800092DF
0x1800092d0  test    r13d, r13d
0x1800092d3  jnz     short loc_1800092DF
0x1800092d5  mov     ebx, 80070003h
0x1800092da  jmp     loc_180009123
0x1800092df  test    r15, r15
0x1800092e2  jz      short loc_18000931A
0x1800092e4  mov     r8, [rsp+770h+var_728]; unsigned int *
0x1800092e9  mov     rdx, rdi; struct _METADATA_RECORD *
0x1800092ec  mov     rcx, r15; this
0x1800092ef  call    ?CopyData@PROPERTY_ENTRY@@QEAAJPEAU_METADATA_RECORD@@PEAK@Z; PROPERTY_ENTRY::CopyData(_METADATA_RECORD *,ulong *)
0x1800092f4  xor     r13d, r13d
0x1800092f7  mov     ebx, eax
0x1800092f9  test    eax, eax
0x1800092fb  js      loc_180009123
0x180009301  cmp     [rsp+770h+var_748], r13d
0x180009306  mov     r13, [rsp+770h+var_750]
0x18000930b  jz      loc_180009128
0x180009311  or      dword ptr [rdi+4], 20h
0x180009315  jmp     loc_180009128
0x18000931a  mov     rcx, cs:?g_pPropertyIdTable@@3PEAVPROPERTY_ID_TABLE@@EA; PROPERTY_ID_TABLE * g_pPropertyIdTable
0x180009321  lea     r8, [rsp+770h+var_720]
0x180009326  mov     edx, [rdi]
0x180009328  add     rcx, 8
0x18000932c  call    ?FindKey@?$CTypedHashTable@VHANDLE_TABLE@@VHANDLE_ENTRY@@KVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@KPEAPEAVHANDLE_ENTRY@@@Z; CTypedHashTable<HANDLE_TABLE,HANDLE_ENTRY,ulong,CLKRHashTable>::FindKey(ulong,HANDLE_ENTRY * *)
0x180009331  mov     rsi, [rsp+770h+var_720]
0x180009336  test    eax, eax
0x180009338  jnz     short loc_1800093AE
0x18000933a  mov     rdx, [rsi+60h]; Src
0x18000933e  test    rdx, rdx
0x180009341  jz      short loc_1800093AE
0x180009343  mov     eax, [rsi+68h]
0x180009346  cmp     [rdi+10h], eax
0x180009349  jnb     short loc_18000935C
0x18000934b  mov     rcx, [rsp+770h+var_728]
0x180009350  mov     ebx, 8007007Ah
0x180009355  mov     [rcx], eax
0x180009357  jmp     loc_180009123
0x18000935c  mov     rcx, [rdi+18h]; void *
0x180009360  mov     r8, rax; Size
0x180009363  call    memcpy_0
0x180009368  mov     eax, [rsi+68h]
0x18000936b  mov     [rdi+10h], eax
0x18000936e  cmp     [rsi+58h], ebx
0x180009371  jbe     short loc_180009394
0x180009373  mov     rax, [rsi+50h]
0x180009377  mov     rcx, [rax]
0x18000937a  mov     eax, [rcx+98h]
0x180009380  mov     [rdi+0Ch], eax
0x180009383  mov     eax, [rcx+94h]
0x180009389  mov     [rdi+8], eax
0x18000938c  mov     eax, [rcx+9Ch]
0x180009392  jmp     short loc_1800093A3
0x180009394  mov     eax, [rsi+6Ch]
0x180009397  mov     [rdi+0Ch], eax
0x18000939a  mov     eax, [rsi+70h]
0x18000939d  mov     [rdi+8], eax
0x1800093a0  mov     eax, [rsi+74h]
0x1800093a3  or      eax, 20h
0x1800093a6  mov     [rdi+4], eax
0x1800093a9  jmp     loc_180009123
0x1800093ae  mov     r13d, 3EAh
0x1800093b4  cmp     [rdi], r13d
0x1800093b7  jnz     loc_180009469
  ... truncated ...
```
