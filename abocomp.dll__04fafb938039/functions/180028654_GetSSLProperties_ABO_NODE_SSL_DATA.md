# GetSSLProperties(ABO_NODE *,SSL_DATA *)

- ea: `0x180028654`
- end: `0x180028aae`
- name: `?GetSSLProperties@@YAJPEAVABO_NODE@@PEAUSSL_DATA@@@Z`
- size: `1114`
- prototype: `__int64 __fastcall(struct ABO_NODE *, struct SSL_DATA *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180016200`
- `0x1800165d0`
- `0x18002742c`
- `0x1800293b0`

## callees

- `0x180003402`
- `0x1800077dc`
- `0x18000fec4`
- `0x180028654`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002885d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002885d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800287b3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800288a1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800288f4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800287b3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800288a1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800288f4`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180028802`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180028802`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028796`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800287e2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028817`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028883`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800288d3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002891f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028977`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800289cb`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028a1e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028a6e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028796`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800287e2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028817`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028883`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800288d3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002891f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028977`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800289cb`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028a1e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028a6e`

## pseudocode

```c
__int64 __fastcall GetSSLProperties(struct ABO_NODE *a1, struct SSL_DATA *a2)
{
  struct PROPERTY_ENTRY *v4; // r12
  PROPERTY_BAG *v5; // r12
  int Entry; // eax
  unsigned int v7; // ebx
  struct PROPERTY_ENTRY *v8; // r15
  struct PROPERTY_ENTRY *v9; // r13
  struct PROPERTY_ENTRY *v10; // rsi
  struct PROPERTY_ENTRY *v11; // rdi
  void *Ptr; // rax
  const unsigned __int16 *v14; // rdx
  int v15; // eax
  _DWORD *v16; // rax
  _DWORD *v17; // rsi
  unsigned int v18; // edx
  unsigned int v19; // ebx
  const void *v20; // rdi
  void *v21; // rax
  int v22; // eax
  signed int LastError; // eax
  void *v24; // rax
  const unsigned __int16 *v25; // rdx
  int v26; // eax
  void *v27; // rax
  const unsigned __int16 *v28; // rdx
  int v29; // eax
  _QWORD *v30; // rax
  _DWORD *v31; // rcx
  int v32; // eax
  _QWORD *v33; // rax
  _DWORD *v34; // rcx
  int v35; // eax
  _QWORD *v36; // rax
  _DWORD *v37; // rcx
  int v38; // eax
  _QWORD *v39; // rax
  _DWORD *v40; // rdx
  int v41; // eax
  _QWORD *v42; // rax
  _DWORD *v43; // rcx
  unsigned int v44; // eax
  struct PROPERTY_ENTRY *v45; // [rsp+20h] [rbp-30h] BYREF
  struct PROPERTY_ENTRY *v46; // [rsp+28h] [rbp-28h] BYREF
  struct PROPERTY_ENTRY *v47; // [rsp+30h] [rbp-20h] BYREF
  struct PROPERTY_ENTRY *v48; // [rsp+38h] [rbp-18h] BYREF
  struct PROPERTY_ENTRY *v49; // [rsp+40h] [rbp-10h] BYREF
  struct PROPERTY_ENTRY *v50; // [rsp+48h] [rbp-8h] BYREF
  struct PROPERTY_ENTRY *v51; // [rsp+90h] [rbp+40h] BYREF
  struct PROPERTY_ENTRY *v52; // [rsp+A0h] [rbp+50h] BYREF
  struct PROPERTY_ENTRY *v53; // [rsp+A8h] [rbp+58h] BYREF

  v47 = 0;
  v48 = 0;
  v4 = 0;
  v49 = 0;
  v46 = 0;
  v50 = 0;
  v45 = 0;
  v53 = 0;
  v52 = 0;
  v51 = 0;
  if ( !a1 || !a2 )
  {
    v7 = -2147024809;
    goto LABEL_6;
  }
  v5 = (struct ABO_NODE *)((char *)a1 + 184);
  Entry = PROPERTY_BAG::FindEntry((struct ABO_NODE *)((char *)a1 + 184), 0x1587u, &v47);
  v7 = Entry;
  if ( Entry >= 0 )
  {
    Ptr = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v47 + 16));
    if ( *((_DWORD *)Ptr + 4) )
    {
      v14 = (const unsigned __int16 *)*((_QWORD *)Ptr + 3);
      if ( v14 )
      {
        if ( *((_DWORD *)Ptr + 3) == 2 )
          STRU::Copy(a2, v14);
      }
    }
  }
  else if ( Entry != -2147024894 )
  {
LABEL_5:
    v4 = v51;
LABEL_6:
    v8 = v46;
LABEL_7:
    v9 = v45;
LABEL_8:
    v10 = v53;
LABEL_9:
    v11 = v52;
    goto LABEL_10;
  }
  v15 = PROPERTY_BAG::FindEntry(v5, 0x1582u, &v48);
  v7 = v15;
  if ( v15 >= 0 )
  {
    v16 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v48 + 16));
    v17 = v16;
    v18 = v16[4];
    if ( v18 && *((_QWORD *)v16 + 3) && v16[3] == 3 )
    {
      if ( !BUFFER::Resize((struct SSL_DATA *)((char *)a2 + 56), v18) )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_5;
      }
      v19 = v17[4];
      v20 = (const void *)*((_QWORD *)v17 + 3);
      v21 = BUFFER::QueryPtr((struct SSL_DATA *)((char *)a2 + 56));
      memcpy_0(v21, v20, v19);
      *((_DWORD *)a2 + 59) = v17[4];
    }
  }
  else if ( v15 != -2147024894 )
  {
    goto LABEL_5;
  }
  v22 = PROPERTY_BAG::FindEntry(v5, 0x1588u, &v49);
  v7 = v22;
  if ( v22 >= 0 )
  {
    v24 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v49 + 16));
    if ( *((_DWORD *)v24 + 4) )
    {
      v25 = (const unsigned __int16 *)*((_QWORD *)v24 + 3);
      if ( v25 )
      {
        if ( *((_DWORD *)v24 + 3) == 2 )
          STRU::Copy((struct SSL_DATA *)((char *)a2 + 104), v25);
      }
    }
  }
  else if ( v22 != -2147024894 )
  {
    goto LABEL_5;
  }
  v26 = PROPERTY_BAG::FindEntry(v5, 0x158Du, &v46);
  v8 = v46;
  v7 = v26;
  if ( v26 >= 0 )
  {
    v27 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v46 + 16));
    if ( *((_DWORD *)v27 + 4) )
    {
      v28 = (const unsigned __int16 *)*((_QWORD *)v27 + 3);
      if ( v28 )
      {
        if ( *((_DWORD *)v27 + 3) == 2 )
          STRU::Copy((struct SSL_DATA *)((char *)a2 + 160), v28);
      }
    }
  }
  else if ( v26 != -2147024894 )
  {
LABEL_52:
    v4 = v51;
    goto LABEL_7;
  }
  v29 = PROPERTY_BAG::FindEntry(v5, 0x870u, &v50);
  v7 = v29;
  if ( v29 >= 0 )
  {
    v30 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v50 + 16));
    if ( *((_DWORD *)v30 + 4) == 4 )
    {
      v31 = (_DWORD *)v30[3];
      if ( v31 )
      {
        if ( *((_DWORD *)v30 + 3) == 1 )
          *((_DWORD *)a2 + 54) = *v31;
      }
    }
  }
  else if ( v29 != -2147024894 )
  {
    goto LABEL_52;
  }
  v32 = PROPERTY_BAG::FindEntry((PROPERTY_BAG *)(*((_QWORD *)a1 + 2) + 184LL), 0x158Fu, &v45);
  v9 = v45;
  v7 = v32;
  if ( v32 >= 0 )
  {
    v33 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v45 + 16));
    if ( *((_DWORD *)v33 + 4) == 4 )
    {
      v34 = (_DWORD *)v33[3];
      if ( v34 )
      {
        if ( *((_DWORD *)v33 + 3) == 1 )
          *((_DWORD *)a2 + 55) = *v34;
      }
    }
  }
  else if ( v32 != -2147024894 )
  {
    v4 = v51;
    goto LABEL_8;
  }
  v35 = PROPERTY_BAG::FindEntry(v5, 0x1591u, &v53);
  v7 = v35;
  if ( v35 >= 0 )
  {
    v10 = v53;
    v36 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v53 + 16));
    if ( *((_DWORD *)v36 + 4) == 4 )
    {
      v37 = (_DWORD *)v36[3];
      if ( v37 )
      {
        if ( *((_DWORD *)v36 + 3) == 1 )
          *((_DWORD *)a2 + 56) = *v37;
      }
    }
  }
  else
  {
    v10 = v53;
    if ( v35 != -2147024894 )
    {
      v4 = v51;
      goto LABEL_9;
    }
  }
  v38 = PROPERTY_BAG::FindEntry(v5, 0x871u, &v52);
  v11 = v52;
  v7 = v38;
  if ( v38 >= 0 )
  {
    v39 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v52 + 16));
    if ( *((_DWORD *)v39 + 4) == 4 )
    {
      v40 = (_DWORD *)v39[3];
      if ( v40 )
      {
        if ( *((_DWORD *)v39 + 3) == 1 )
          *((_DWORD *)a2 + 57) = *v40;
      }
    }
  }
  else if ( v38 != -2147024894 )
  {
    v4 = v51;
    goto LABEL_10;
  }
  v41 = PROPERTY_BAG::FindEntry(v5, 0x872u, &v51);
  v4 = v51;
  v7 = v41;
  if ( v41 >= 0 )
  {
    v42 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v51 + 16));
    if ( *((_DWORD *)v42 + 4) == 4 )
    {
      v43 = (_DWORD *)v42[3];
      if ( v43 )
      {
        if ( *((_DWORD *)v42 + 3) == 1 )
          *((_DWORD *)a2 + 58) = *v43;
      }
    }
  }
  else if ( v41 != -2147024894 )
  {
    goto LABEL_10;
  }
  v44 = 0;
  if ( v7 != -2147024894 )
    v44 = v7;
  v7 = v44;
LABEL_10:
  if ( v47 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v47);
  if ( v48 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v48);
  if ( v49 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v49);
  if ( v8 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v8);
  if ( v50 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v50);
  if ( v9 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v9);
  if ( v10 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v10);
  if ( v11 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v11);
  if ( v4 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v4);
  return v7;
}

```

## disassembly

```asm
0x180028654  mov     [rsp-38h+arg_8], rbx
0x180028659  push    rbp
0x18002865a  push    rsi
0x18002865b  push    rdi
0x18002865c  push    r12
0x18002865e  push    r13
0x180028660  push    r14
0x180028662  push    r15
0x180028664  mov     rbp, rsp
0x180028667  sub     rsp, 50h
0x18002866b  xor     edi, edi
0x18002866d  mov     r14, rdx
0x180028670  mov     [rbp+var_20], rdi
0x180028674  mov     r13, rcx
0x180028677  mov     [rbp+var_18], rdi
0x18002867b  mov     r12d, edi
0x18002867e  mov     [rbp+var_10], rdi
0x180028682  mov     [rbp+var_28], rdi
0x180028686  mov     [rbp+var_8], rdi
0x18002868a  mov     [rbp+var_30], rdi
0x18002868e  mov     [rbp+arg_18], rdi
0x180028692  mov     [rbp+arg_10], rdi
0x180028696  mov     [rbp+arg_0], rdi
0x18002869a  test    rcx, rcx
0x18002869d  jz      loc_180028AA4
0x1800286a3  test    rdx, rdx
0x1800286a6  jz      loc_180028AA4
0x1800286ac  lea     r12, [rcx+0B8h]
0x1800286b3  mov     edx, 1587h; unsigned int
0x1800286b8  mov     rcx, r12; this
0x1800286bb  lea     r8, [rbp+var_20]; struct PROPERTY_ENTRY **
0x1800286bf  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x1800286c4  mov     ebx, eax
0x1800286c6  mov     esi, 80070002h
0x1800286cb  test    eax, eax
0x1800286cd  jns     loc_18002878E
0x1800286d3  cmp     eax, esi
0x1800286d5  jz      loc_1800287B9
0x1800286db  mov     r12, [rbp+arg_0]
0x1800286df  mov     r15, [rbp+var_28]
0x1800286e3  mov     r13, [rbp+var_30]
0x1800286e7  mov     rsi, [rbp+arg_18]
0x1800286eb  mov     rdi, [rbp+arg_10]
0x1800286ef  mov     rax, [rbp+var_20]
0x1800286f3  test    rax, rax
0x1800286f6  jz      short loc_180028700
0x1800286f8  mov     rcx, rax; this
0x1800286fb  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180028700  mov     rax, [rbp+var_18]
0x180028704  test    rax, rax
0x180028707  jz      short loc_180028711
0x180028709  mov     rcx, rax; this
0x18002870c  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180028711  mov     rax, [rbp+var_10]
0x180028715  test    rax, rax
0x180028718  jz      short loc_180028722
0x18002871a  mov     rcx, rax; this
0x18002871d  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180028722  test    r15, r15
0x180028725  jz      short loc_18002872F
0x180028727  mov     rcx, r15; this
0x18002872a  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18002872f  mov     rax, [rbp+var_8]
0x180028733  test    rax, rax
0x180028736  jz      short loc_180028740
0x180028738  mov     rcx, rax; this
0x18002873b  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180028740  test    r13, r13
0x180028743  jz      short loc_18002874D
0x180028745  mov     rcx, r13; this
0x180028748  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18002874d  test    rsi, rsi
0x180028750  jz      short loc_18002875A
0x180028752  mov     rcx, rsi; this
0x180028755  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18002875a  test    rdi, rdi
0x18002875d  jz      short loc_180028767
0x18002875f  mov     rcx, rdi; this
0x180028762  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180028767  test    r12, r12
0x18002876a  jz      short loc_180028774
0x18002876c  mov     rcx, r12; this
0x18002876f  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180028774  mov     eax, ebx
0x180028776  mov     rbx, [rsp+50h+arg_8]
0x18002877e  add     rsp, 50h
0x180028782  pop     r15
0x180028784  pop     r14
0x180028786  pop     r13
0x180028788  pop     r12
0x18002878a  pop     rdi
0x18002878b  pop     rsi
0x18002878c  pop     rbp
0x18002878d  retn
0x18002878e  mov     rcx, [rbp+var_20]
0x180028792  add     rcx, 10h
0x180028796  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002879c  cmp     [rax+10h], edi
0x18002879f  jz      short loc_1800287B9
0x1800287a1  mov     rdx, [rax+18h]
0x1800287a5  test    rdx, rdx
0x1800287a8  jz      short loc_1800287B9
0x1800287aa  cmp     dword ptr [rax+0Ch], 2
0x1800287ae  jnz     short loc_1800287B9
0x1800287b0  mov     rcx, r14
0x1800287b3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800287b9  lea     r8, [rbp+var_18]; struct PROPERTY_ENTRY **
0x1800287bd  mov     edx, 1582h; unsigned int
0x1800287c2  mov     rcx, r12; this
0x1800287c5  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x1800287ca  mov     ebx, eax
0x1800287cc  test    eax, eax
0x1800287ce  jns     short loc_1800287DA
0x1800287d0  cmp     eax, esi
0x1800287d2  jnz     loc_1800286DB
0x1800287d8  jmp     short loc_18002883C
0x1800287da  mov     rcx, [rbp+var_18]
0x1800287de  add     rcx, 10h
0x1800287e2  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800287e8  mov     rsi, rax
0x1800287eb  mov     edx, [rax+10h]
0x1800287ee  test    edx, edx
0x1800287f0  jz      short loc_180028837
0x1800287f2  cmp     [rax+18h], rdi
0x1800287f6  jz      short loc_180028837
0x1800287f8  cmp     dword ptr [rax+0Ch], 3
0x1800287fc  jnz     short loc_180028837
0x1800287fe  lea     rcx, [r14+38h]
0x180028802  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180028808  test    al, al
0x18002880a  jz      short loc_18002885D
0x18002880c  mov     ebx, [rsi+10h]
0x18002880f  lea     rcx, [r14+38h]
0x180028813  mov     rdi, [rsi+18h]
0x180028817  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002881d  mov     r8d, ebx; Size
0x180028820  mov     rdx, rdi; Src
0x180028823  mov     rcx, rax; void *
0x180028826  call    memcpy_0
0x18002882b  mov     eax, [rsi+10h]
0x18002882e  xor     edi, edi
0x180028830  mov     [r14+0ECh], eax
0x180028837  mov     esi, 80070002h
0x18002883c  lea     r8, [rbp+var_10]; struct PROPERTY_ENTRY **
0x180028840  mov     edx, 1588h; unsigned int
0x180028845  mov     rcx, r12; this
0x180028848  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x18002884d  mov     ebx, eax
0x18002884f  test    eax, eax
0x180028851  jns     short loc_18002887B
0x180028853  cmp     eax, esi
0x180028855  jnz     loc_1800286DB
0x18002885b  jmp     short loc_1800288A7
0x18002885d  call    cs:__imp_GetLastError
0x180028863  mov     ebx, eax
0x180028865  test    eax, eax
0x180028867  jle     loc_1800286DB
0x18002886d  movzx   ebx, ax
0x180028870  or      ebx, 80070000h
0x180028876  jmp     loc_1800286DB
0x18002887b  mov     rcx, [rbp+var_10]
0x18002887f  add     rcx, 10h
0x180028883  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180028889  cmp     [rax+10h], edi
0x18002888c  jz      short loc_1800288A7
0x18002888e  mov     rdx, [rax+18h]
0x180028892  test    rdx, rdx
0x180028895  jz      short loc_1800288A7
0x180028897  cmp     dword ptr [rax+0Ch], 2
0x18002889b  jnz     short loc_1800288A7
0x18002889d  lea     rcx, [r14+68h]
0x1800288a1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800288a7  lea     r8, [rbp+var_28]; struct PROPERTY_ENTRY **
0x1800288ab  mov     edx, 158Dh; unsigned int
0x1800288b0  mov     rcx, r12; this
0x1800288b3  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x1800288b8  mov     r15, [rbp+var_28]
0x1800288bc  mov     ebx, eax
0x1800288be  test    eax, eax
0x1800288c0  jns     short loc_1800288CF
0x1800288c2  cmp     eax, esi
0x1800288c4  jz      short loc_1800288FA
0x1800288c6  mov     r12, [rbp+arg_0]
0x1800288ca  jmp     loc_1800286E3
0x1800288cf  lea     rcx, [r15+10h]
0x1800288d3  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800288d9  cmp     [rax+10h], edi
0x1800288dc  jz      short loc_1800288FA
0x1800288de  mov     rdx, [rax+18h]
0x1800288e2  test    rdx, rdx
0x1800288e5  jz      short loc_1800288FA
0x1800288e7  cmp     dword ptr [rax+0Ch], 2
0x1800288eb  jnz     short loc_1800288FA
0x1800288ed  lea     rcx, [r14+0A0h]
0x1800288f4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800288fa  lea     r8, [rbp+var_8]; struct PROPERTY_ENTRY **
0x1800288fe  mov     edx, 870h; unsigned int
0x180028903  mov     rcx, r12; this
0x180028906  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x18002890b  mov     ebx, eax
0x18002890d  test    eax, eax
0x18002890f  jns     short loc_180028917
0x180028911  cmp     eax, esi
0x180028913  jnz     short loc_1800288C6
0x180028915  jmp     short loc_180028943
0x180028917  mov     rcx, [rbp+var_8]
0x18002891b  add     rcx, 10h
0x18002891f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180028925  cmp     dword ptr [rax+10h], 4
0x180028929  jnz     short loc_180028943
0x18002892b  mov     rcx, [rax+18h]
0x18002892f  test    rcx, rcx
0x180028932  jz      short loc_180028943
0x180028934  cmp     dword ptr [rax+0Ch], 1
0x180028938  jnz     short loc_180028943
0x18002893a  mov     eax, [rcx]
0x18002893c  mov     [r14+0D8h], eax
0x180028943  mov     rcx, [r13+10h]
0x180028947  lea     r8, [rbp+var_30]; struct PROPERTY_ENTRY **
0x18002894b  add     rcx, 0B8h; this
0x180028952  mov     edx, 158Fh; unsigned int
0x180028957  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x18002895c  mov     r13, [rbp+var_30]
0x180028960  mov     ebx, eax
0x180028962  test    eax, eax
0x180028964  jns     short loc_180028973
0x180028966  cmp     eax, esi
0x180028968  jz      short loc_18002899B
0x18002896a  mov     r12, [rbp+arg_0]
0x18002896e  jmp     loc_1800286E7
0x180028973  lea     rcx, [r13+10h]
0x180028977  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002897d  cmp     dword ptr [rax+10h], 4
0x180028981  jnz     short loc_18002899B
0x180028983  mov     rcx, [rax+18h]
0x180028987  test    rcx, rcx
0x18002898a  jz      short loc_18002899B
0x18002898c  cmp     dword ptr [rax+0Ch], 1
0x180028990  jnz     short loc_18002899B
0x180028992  mov     eax, [rcx]
0x180028994  mov     [r14+0DCh], eax
0x18002899b  lea     r8, [rbp+arg_18]; struct PROPERTY_ENTRY **
0x18002899f  mov     edx, 1591h; unsigned int
0x1800289a4  mov     rcx, r12; this
0x1800289a7  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x1800289ac  mov     ebx, eax
0x1800289ae  test    eax, eax
0x1800289b0  jns     short loc_1800289C3
0x1800289b2  cmp     eax, esi
0x1800289b4  mov     rsi, [rbp+arg_18]
0x1800289b8  jz      short loc_1800289EF
0x1800289ba  mov     r12, [rbp+arg_0]
0x1800289be  jmp     loc_1800286EB
0x1800289c3  mov     rsi, [rbp+arg_18]
0x1800289c7  lea     rcx, [rsi+10h]
0x1800289cb  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800289d1  cmp     dword ptr [rax+10h], 4
0x1800289d5  jnz     short loc_1800289EF
0x1800289d7  mov     rcx, [rax+18h]
0x1800289db  test    rcx, rcx
0x1800289de  jz      short loc_1800289EF
0x1800289e0  cmp     dword ptr [rax+0Ch], 1
0x1800289e4  jnz     short loc_1800289EF
0x1800289e6  mov     eax, [rcx]
0x1800289e8  mov     [r14+0E0h], eax
0x1800289ef  lea     r8, [rbp+arg_10]; struct PROPERTY_ENTRY **
0x1800289f3  mov     edx, 871h; unsigned int
0x1800289f8  mov     rcx, r12; this
0x1800289fb  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x180028a00  mov     rdi, [rbp+arg_10]
0x180028a04  mov     ebx, eax
0x180028a06  test    eax, eax
0x180028a08  jns     short loc_180028A1A
0x180028a0a  cmp     eax, 80070002h
0x180028a0f  jz      short loc_180028A42
0x180028a11  mov     r12, [rbp+arg_0]
0x180028a15  jmp     loc_1800286EF
0x180028a1a  lea     rcx, [rdi+10h]
0x180028a1e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180028a24  cmp     dword ptr [rax+10h], 4
0x180028a28  jnz     short loc_180028A42
0x180028a2a  mov     rdx, [rax+18h]
0x180028a2e  test    rdx, rdx
0x180028a31  jz      short loc_180028A42
0x180028a33  cmp     dword ptr [rax+0Ch], 1
0x180028a37  jnz     short loc_180028A42
0x180028a39  mov     eax, [rdx]
0x180028a3b  mov     [r14+0E4h], eax
0x180028a42  lea     r8, [rbp+arg_0]; struct PROPERTY_ENTRY **
0x180028a46  mov     edx, 872h; unsigned int
0x180028a4b  mov     rcx, r12; this
0x180028a4e  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x180028a53  mov     r12, [rbp+arg_0]
0x180028a57  mov     ebx, eax
0x180028a59  test    eax, eax
0x180028a5b  jns     short loc_180028A69
0x180028a5d  cmp     eax, 80070002h
0x180028a62  jz      short loc_180028A92
0x180028a64  jmp     loc_1800286EF
0x180028a69  lea     rcx, [r12+10h]
  ... truncated ...
```
