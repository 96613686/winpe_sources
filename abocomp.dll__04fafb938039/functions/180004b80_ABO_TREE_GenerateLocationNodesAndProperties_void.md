# ABO_TREE::GenerateLocationNodesAndProperties(void)

- ea: `0x180004b80`
- end: `0x180004f90`
- name: `?GenerateLocationNodesAndProperties@ABO_TREE@@AEAAJXZ`
- size: `1040`
- prototype: `__int64 __fastcall(ABO_TREE *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x180004f98`

## callees

- `0x180001f90`
- `0x1800029d0`
- `0x180003460`
- `0x180004398`
- `0x1800044e0`
- `0x18000473c`
- `0x180004b80`
- `0x18000542c`
- `0x180005cf4`
- `0x180007ac8`
- `0x180007d4c`
- `0x18000a8cc`
- `0x18000aaa8`
- `0x18002c010`

## import_xrefs

- `msvcrt!wcschr` at `0x180004d87`
- `msvcrt!wcschr` at `0x180004d87`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004d9b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004d9b`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180004f68`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180004f68`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180004e5f`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180004e5f`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180004c27`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180004c27`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004f5a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004f5a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004dc9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004dc9`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004c3c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004c3c`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x180004c46`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x180004c46`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180004dac`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180004dac`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180004ddb`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180004ddb`

## string_xrefs

- `0x180004e8e`: `IIsWebDirectory`

## pseudocode

```c
__int64 __fastcall ABO_TREE::GenerateLocationNodesAndProperties(ABO_NODE **this)
{
  SITE_NODE_TABLE_ENTRY *v1; // rdi
  struct ABO_NODE *v3; // rsi
  int HasLocationSupportedSections; // ebx
  unsigned int v5; // r12d
  ABO_TREE *v6; // rcx
  wchar_t *v7; // rax
  int v8; // eax
  unsigned __int16 *v9; // rax
  int Key; // eax
  ABO_TREE *v11; // rcx
  bool v12; // zf
  int LocationProperties; // ebx
  const unsigned __int16 *v14; // rax
  struct INativeConfigLocation *v16; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v17; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+5Ch] [rbp-A4h] BYREF
  wchar_t *Str; // [rsp+60h] [rbp-A0h] BYREF
  ABO_NODE *v20; // [rsp+68h] [rbp-98h] BYREF
  void *Block[2]; // [rsp+70h] [rbp-90h] BYREF
  struct ABO_NODE *v22; // [rsp+80h] [rbp-80h] BYREF
  int v23; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v24[64]; // [rsp+90h] [rbp-70h] BYREF
  void **v25; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v26[72]; // [rsp+D8h] [rbp-28h] BYREF

  v1 = 0;
  v16 = 0;
  v17 = 0;
  v3 = 0;
  Str = 0;
  v20 = 0;
  Block[1] = 0;
  v22 = 0;
  v18 = 0;
  v23 = 0;
  CLKRHashTable::CLKRHashTable(
    (CLKRHashTable *)v26,
    "SITE_NODE_TABLE",
    (unsigned __int64 (*)(const void *))CTypedHashTable<SITE_NODE_TABLE,SITE_NODE_TABLE_ENTRY,unsigned short const *,CLKRHashTable>::_ExtractKey,
    (unsigned int (*)(unsigned __int64))CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::_CalcKeyHash,
    (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<SITE_NODE_TABLE,SITE_NODE_TABLE_ENTRY,unsigned short const *,CLKRHashTable>::_EqualKeys,
    (void (*)(const void *, int))CTypedHashTable<SITE_NODE_TABLE,SITE_NODE_TABLE_ENTRY,unsigned short const *,CLKRHashTable>::_AddRefRecord,
    4.0,
    1u,
    0,
    0);
  v25 = &HANDLE_TABLE::`vftable';
  STRU::STRU((STRU *)v24);
  if ( CLKRHashTable::IsValid((CLKRHashTable *)v26) )
  {
    HasLocationSupportedSections = ABO_TREE::PopulateSiteNodeTable((ABO_TREE *)this, (struct SITE_NODE_TABLE *)&v25);
    if ( HasLocationSupportedSections >= 0 )
    {
      HasLocationSupportedSections = (*(__int64 (__fastcall **)(ABO_NODE *, unsigned int *))(*(_QWORD *)this[4] + 24LL))(
                                       this[4],
                                       &v17);
      if ( HasLocationSupportedSections >= 0 )
      {
        v5 = 0;
        if ( v17 )
        {
          do
          {
            HasLocationSupportedSections = (*(__int64 (__fastcall **)(ABO_NODE *, _QWORD, struct INativeConfigLocation **))(*(_QWORD *)this[4] + 32LL))(
                                             this[4],
                                             v5,
                                             &v16);
            if ( HasLocationSupportedSections < 0 )
              break;
            HasLocationSupportedSections = ABO_TREE::HasLocationSupportedSections(v6, v16, &v18);
            if ( HasLocationSupportedSections < 0 )
              break;
            if ( v18 )
            {
              HasLocationSupportedSections = (*(__int64 (__fastcall **)(struct INativeConfigLocation *, wchar_t **))(*(_QWORD *)v16 + 24LL))(
                                               v16,
                                               &Str);
              if ( HasLocationSupportedSections < 0 )
                break;
              if ( !*Str )
                ABO_NODE::FindNode(this[2], L"/LM/MIMEMAP", &v20);
              v7 = wcschr(Str, 0x2Fu);
              v8 = v7 ? STRU::Copy((STRU *)v24, Str, v7 - Str) : STRU::Copy((STRU *)v24, Str);
              HasLocationSupportedSections = v8;
              if ( v8 < 0 )
                break;
              Block[0] = 0;
              v9 = STRU::QueryStr((STRU *)v24);
              Key = CLKRHashTable::FindKey(v26, v9, Block);
              v1 = (SITE_NODE_TABLE_ENTRY *)Block[0];
              if ( Key )
              {
                if ( Key != 2 )
                {
                  HasLocationSupportedSections = -2147467259;
                  break;
                }
              }
              else
              {
                HasLocationSupportedSections = ABO_TREE::CreateSiteNodeChildFromLocationPath(
                                                 v11,
                                                 *((struct ABO_NODE **)Block[0] + 8),
                                                 Str,
                                                 &v22,
                                                 &v23);
                if ( HasLocationSupportedSections < 0 )
                {
                  v3 = v22;
                  break;
                }
                v12 = (*(_DWORD *)v1)-- == 1;
                if ( v12 )
                {
                  SITE_NODE_TABLE_ENTRY::~SITE_NODE_TABLE_ENTRY(v1);
                  operator delete(v1);
                }
                v1 = 0;
                v3 = v22;
                ABO_NODE::SetLocation(v22, v16);
                LocationProperties = ABO_NODE::GenerateLocationProperties(v3);
                if ( LocationProperties < 0 )
                {
                  v14 = STRU::QueryStr((struct ABO_NODE *)((char *)v3 + 56));
                  ABO_MAPPER_LOG::WriteLogEntry(
                    g_pAboLog,
                    L"Failed to generate location properties for Node (%s).  error = %08x\n",
                    v14,
                    (unsigned int)LocationProperties);
                  *((_DWORD *)v3 + 61) = 1;
                  *((_DWORD *)v3 + 62) = LocationProperties;
                }
                HasLocationSupportedSections = ABO_NODE::SetDefaultKeyType(v3, L"IIsWebDirectory");
                if ( HasLocationSupportedSections < 0 )
                {
                  HasLocationSupportedSections = 0;
                  break;
                }
                ABO_NODE::DereferenceAboNode(v3);
                v3 = 0;
                v22 = 0;
              }
            }
            (*(void (__fastcall **)(struct INativeConfigLocation *))(*(_QWORD *)v16 + 16LL))(v16);
            ++v5;
            v16 = 0;
          }
          while ( v5 < v17 );
          if ( v1 )
          {
            v12 = (*(_DWORD *)v1)-- == 1;
            if ( v12 )
            {
              SITE_NODE_TABLE_ENTRY::~SITE_NODE_TABLE_ENTRY(v1);
              operator delete(v1);
            }
          }
          if ( v3 )
            ABO_NODE::DereferenceAboNode(v3);
        }
      }
    }
  }
  else
  {
    HasLocationSupportedSections = -2147024888;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(struct INativeConfigLocation *))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  STRU::~STRU((STRU *)v24);
  v25 = &HANDLE_TABLE::`vftable';
  CLKRHashTable::~CLKRHashTable((CLKRHashTable *)v26);
  return (unsigned int)HasLocationSupportedSections;
}

```

## disassembly

```asm
0x180004b80  push    rbp
0x180004b82  push    rbx
0x180004b83  push    rsi
0x180004b84  push    rdi
0x180004b85  push    r12
0x180004b87  push    r13
0x180004b89  push    r14
0x180004b8b  push    r15
0x180004b8d  lea     rbp, [rsp-38h]
0x180004b92  sub     rsp, 138h
0x180004b99  mov     rax, cs:__security_cookie
0x180004ba0  xor     rax, rsp
0x180004ba3  mov     [rbp+70h+var_50], rax
0x180004ba7  movsd   xmm0, cs:__real@4010000000000000
0x180004baf  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VSITE_NODE_TABLE@@VSITE_NODE_TABLE_ENTRY@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<SITE_NODE_TABLE,SITE_NODE_TABLE_ENTRY,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x180004bb6  xor     edi, edi
0x180004bb8  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180004bbf  mov     [rsp+170h+var_128], dil
0x180004bc4  lea     r8, ?_ExtractKey@?$CTypedHashTable@VSITE_NODE_TABLE@@VSITE_NODE_TABLE_ENTRY@@PEBGVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<SITE_NODE_TABLE,SITE_NODE_TABLE_ENTRY,ushort const *,CLKRHashTable>::_ExtractKey(void const *)
0x180004bcb  mov     [rsp+170h+var_130], edi
0x180004bcf  lea     rdx, aSiteNodeTable; "SITE_NODE_TABLE"
0x180004bd6  mov     [rsp+170h+var_138], 1
0x180004bde  mov     r13, rcx
0x180004be1  movsd   [rsp+170h+var_140], xmm0
0x180004be7  lea     rcx, [rbp+70h+var_98]
0x180004beb  mov     [rsp+170h+var_148], rax
0x180004bf0  mov     r15d, edi
0x180004bf3  lea     rax, ?_EqualKeys@?$CTypedHashTable@VSITE_NODE_TABLE@@VSITE_NODE_TABLE_ENTRY@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<SITE_NODE_TABLE,SITE_NODE_TABLE_ENTRY,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x180004bfa  mov     [rsp+170h+var_120], rdi
0x180004bff  mov     [rsp+170h+var_150], rax
0x180004c04  mov     r14d, edi
0x180004c07  mov     [rsp+170h+var_118], edi
0x180004c0b  mov     esi, edi
0x180004c0d  mov     [rsp+170h+Str], rdi
0x180004c12  mov     [rsp+170h+var_108], rdi
0x180004c17  mov     [rsp+170h+var_F8], rdi
0x180004c1c  mov     [rbp+70h+var_F0], rdi
0x180004c20  mov     [rsp+170h+var_114], edi
0x180004c24  mov     [rbp+70h+var_E8], edi
0x180004c27  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x180004c2d  lea     r12, ??_7HANDLE_TABLE@@6B@; const HANDLE_TABLE::`vftable'
0x180004c34  lea     rcx, [rbp+70h+var_E0]
0x180004c38  mov     [rbp+70h+var_A0], r12
0x180004c3c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004c42  lea     rcx, [rbp+70h+var_98]
0x180004c46  call    cs:__imp_?IsValid@CLKRHashTable@@QEBA_NXZ; CLKRHashTable::IsValid(void)
0x180004c4c  test    al, al
0x180004c4e  jnz     short loc_180004C5A
0x180004c50  mov     ebx, 80070008h
0x180004c55  jmp     loc_180004F3B
0x180004c5a  lea     rdx, [rbp+70h+var_A0]; struct SITE_NODE_TABLE *
0x180004c5e  mov     rcx, r13; this
0x180004c61  call    ?PopulateSiteNodeTable@ABO_TREE@@AEAAJPEAVSITE_NODE_TABLE@@@Z; ABO_TREE::PopulateSiteNodeTable(SITE_NODE_TABLE *)
0x180004c66  mov     ebx, eax
0x180004c68  test    eax, eax
0x180004c6a  js      loc_180004F3B
0x180004c70  mov     rcx, [r13+20h]
0x180004c74  lea     rdx, [rsp+170h+var_118]
0x180004c79  mov     rax, [rcx]
0x180004c7c  mov     rax, [rax+18h]
0x180004c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c85  mov     ebx, eax
0x180004c87  test    eax, eax
0x180004c89  js      loc_180004F3B
0x180004c8f  xor     eax, eax
0x180004c91  mov     r12d, eax
0x180004c94  cmp     [rsp+170h+var_118], eax
0x180004c98  jbe     loc_180004F34
0x180004c9e  mov     rcx, [r13+20h]
0x180004ca2  lea     r8, [rsp+170h+var_120]
0x180004ca7  mov     edx, r12d
0x180004caa  mov     rax, [rcx]
0x180004cad  mov     rax, [rax+20h]
0x180004cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cb6  mov     ebx, eax
0x180004cb8  test    eax, eax
0x180004cba  js      loc_180004EF1
0x180004cc0  mov     rdx, [rsp+170h+var_120]; struct INativeConfigLocation *
0x180004cc5  lea     r8, [rsp+170h+var_114]; int *
0x180004cca  call    ?HasLocationSupportedSections@ABO_TREE@@AEAAJPEAVINativeConfigLocation@@PEAH@Z; ABO_TREE::HasLocationSupportedSections(INativeConfigLocation *,int *)
0x180004ccf  mov     ebx, eax
0x180004cd1  xor     eax, eax
0x180004cd3  test    ebx, ebx
0x180004cd5  js      loc_180004EF1
0x180004cdb  cmp     [rsp+170h+var_114], eax
0x180004cdf  jz      loc_180004EB1
0x180004ce5  mov     rcx, [rsp+170h+var_120]
0x180004cea  lea     rdx, [rsp+170h+Str]
0x180004cef  mov     rax, [rcx]
0x180004cf2  mov     rax, [rax+18h]
0x180004cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cfb  mov     ebx, eax
0x180004cfd  test    eax, eax
0x180004cff  js      loc_180004EF1
0x180004d05  mov     rcx, [rsp+170h+Str]; Str
0x180004d0a  xor     ebx, ebx
0x180004d0c  cmp     [rcx], bx
0x180004d0f  jnz     short loc_180004D82
0x180004d11  mov     rcx, [r13+10h]; this
0x180004d15  lea     r8, [rsp+170h+var_108]; struct ABO_NODE **
0x180004d1a  lea     rdx, aLmMimemap_0; "/LM/MIMEMAP"
0x180004d21  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x180004d26  mov     ebx, eax
0x180004d28  test    eax, eax
0x180004d2a  js      loc_180004EE2
0x180004d30  mov     rdx, [rsp+170h+var_120]; struct INativeConfigLocation *
0x180004d35  mov     rcx, [rsp+170h+var_108]; this
0x180004d3a  call    ?SetLocation@ABO_NODE@@QEAAXPEAVINativeConfigLocation@@@Z; ABO_NODE::SetLocation(INativeConfigLocation *)
0x180004d3f  mov     rcx, [rsp+170h+var_108]; this
0x180004d44  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180004d49  mov     rcx, [r13+10h]; this
0x180004d4d  lea     r8, [rsp+170h+var_F8]; struct ABO_NODE **
0x180004d52  xor     r14d, r14d
0x180004d55  lea     rdx, aLmW3svc; "LM/W3SVC"
0x180004d5c  mov     r15d, r14d
0x180004d5f  mov     [rsp+170h+var_108], r14
0x180004d64  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x180004d69  mov     ebx, eax
0x180004d6b  test    eax, eax
0x180004d6d  js      loc_180004EDB
0x180004d73  mov     rsi, [rsp+170h+var_F8]
0x180004d78  mov     [rsp+170h+var_F8], r14
0x180004d7d  jmp     loc_180004E40
0x180004d82  mov     edx, 2Fh ; '/'; Ch
0x180004d87  call    cs:__imp_wcschr
0x180004d8d  mov     rdx, [rsp+170h+Str]
0x180004d92  lea     rcx, [rbp+70h+var_E0]
0x180004d96  test    rax, rax
0x180004d99  jnz     short loc_180004DA3
0x180004d9b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004da1  jmp     short loc_180004DB2
0x180004da3  sub     rax, rdx
0x180004da6  sar     rax, 1
0x180004da9  mov     r8d, eax
0x180004dac  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180004db2  mov     ebx, eax
0x180004db4  test    eax, eax
0x180004db6  js      loc_180004EF1
0x180004dbc  lea     rcx, [rbp+70h+var_E0]
0x180004dc0  mov     [rsp+170h+Block], 0
0x180004dc9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004dcf  mov     rdx, rax
0x180004dd2  lea     r8, [rsp+170h+Block]
0x180004dd7  lea     rcx, [rbp+70h+var_98]
0x180004ddb  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180004de1  mov     rdi, [rsp+170h+Block]
0x180004de6  test    eax, eax
0x180004de8  jz      short loc_180004DFD
0x180004dea  cmp     eax, 2
0x180004ded  jz      loc_180004EB1
0x180004df3  mov     ebx, 80004005h
0x180004df8  jmp     loc_180004EF1
0x180004dfd  mov     r8, [rsp+170h+Str]; unsigned __int16 *
0x180004e02  lea     rax, [rbp+70h+var_E8]
0x180004e06  mov     rdx, [rdi+40h]; struct ABO_NODE *
0x180004e0a  lea     r9, [rbp+70h+var_F0]; struct ABO_NODE **
0x180004e0e  mov     [rsp+170h+var_150], rax; int *
0x180004e13  call    ?CreateSiteNodeChildFromLocationPath@ABO_TREE@@AEAAJPEAVABO_NODE@@PEBGPEAPEAV2@PEAH@Z; ABO_TREE::CreateSiteNodeChildFromLocationPath(ABO_NODE *,ushort const *,ABO_NODE * *,int *)
0x180004e18  xor     esi, esi
0x180004e1a  mov     ebx, eax
0x180004e1c  test    eax, eax
0x180004e1e  js      loc_180004EED
0x180004e24  add     dword ptr [rdi], 0FFFFFFFFh
0x180004e27  jnz     short loc_180004E39
0x180004e29  mov     rcx, rdi; this
0x180004e2c  call    ??1SITE_NODE_TABLE_ENTRY@@QEAA@XZ; SITE_NODE_TABLE_ENTRY::~SITE_NODE_TABLE_ENTRY(void)
0x180004e31  mov     rcx, rdi; Block
0x180004e34  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004e39  mov     rdi, rsi
0x180004e3c  mov     rsi, [rbp+70h+var_F0]
0x180004e40  mov     rdx, [rsp+170h+var_120]; struct INativeConfigLocation *
0x180004e45  mov     rcx, rsi; this
0x180004e48  call    ?SetLocation@ABO_NODE@@QEAAXPEAVINativeConfigLocation@@@Z; ABO_NODE::SetLocation(INativeConfigLocation *)
0x180004e4d  mov     rcx, rsi; this
0x180004e50  call    ?GenerateLocationProperties@ABO_NODE@@QEAAJXZ; ABO_NODE::GenerateLocationProperties(void)
0x180004e55  mov     ebx, eax
0x180004e57  test    eax, eax
0x180004e59  jns     short loc_180004E8E
0x180004e5b  lea     rcx, [rsi+38h]
0x180004e5f  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180004e65  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180004e6c  lea     rdx, aFailedToGenera_11; "Failed to generate location properties "...
0x180004e73  mov     r8, rax
0x180004e76  mov     r9d, ebx
0x180004e79  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180004e7e  mov     dword ptr [rsi+0F4h], 1
0x180004e88  mov     [rsi+0F8h], ebx
0x180004e8e  lea     rdx, aIiswebdirector; "IIsWebDirectory"
0x180004e95  mov     rcx, rsi; this
0x180004e98  call    ?SetDefaultKeyType@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::SetDefaultKeyType(ushort const *)
0x180004e9d  mov     ebx, eax
0x180004e9f  test    eax, eax
0x180004ea1  js      short loc_180004EE9
0x180004ea3  mov     rcx, rsi; this
0x180004ea6  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180004eab  xor     esi, esi
0x180004ead  mov     [rbp+70h+var_F0], rsi
0x180004eb1  mov     rcx, [rsp+170h+var_120]
0x180004eb6  mov     rax, [rcx]
0x180004eb9  mov     rax, [rax+10h]
0x180004ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ec2  inc     r12d
0x180004ec5  mov     [rsp+170h+var_120], 0
0x180004ece  cmp     r12d, [rsp+170h+var_118]
0x180004ed3  jb      loc_180004C9E
0x180004ed9  jmp     short loc_180004EF1
0x180004edb  mov     r14, [rsp+170h+var_F8]
0x180004ee0  jmp     short loc_180004EF1
0x180004ee2  mov     r15, [rsp+170h+var_108]
0x180004ee7  jmp     short loc_180004EF1
0x180004ee9  xor     ebx, ebx
0x180004eeb  jmp     short loc_180004EF1
0x180004eed  mov     rsi, [rbp+70h+var_F0]
0x180004ef1  test    rdi, rdi
0x180004ef4  jz      short loc_180004F0B
0x180004ef6  add     dword ptr [rdi], 0FFFFFFFFh
0x180004ef9  jnz     short loc_180004F0B
0x180004efb  mov     rcx, rdi; this
0x180004efe  call    ??1SITE_NODE_TABLE_ENTRY@@QEAA@XZ; SITE_NODE_TABLE_ENTRY::~SITE_NODE_TABLE_ENTRY(void)
0x180004f03  mov     rcx, rdi; Block
0x180004f06  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004f0b  xor     edi, edi
0x180004f0d  test    rsi, rsi
0x180004f10  jz      short loc_180004F1A
0x180004f12  mov     rcx, rsi; this
0x180004f15  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180004f1a  test    r14, r14
0x180004f1d  jz      short loc_180004F27
0x180004f1f  mov     rcx, r14; this
0x180004f22  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180004f27  test    r15, r15
0x180004f2a  jz      short loc_180004F34
0x180004f2c  mov     rcx, r15; this
0x180004f2f  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180004f34  lea     r12, ??_7HANDLE_TABLE@@6B@; const HANDLE_TABLE::`vftable'
0x180004f3b  mov     rcx, [rsp+170h+var_120]
0x180004f40  test    rcx, rcx
0x180004f43  jz      short loc_180004F56
0x180004f45  mov     rax, [rcx]
0x180004f48  mov     rax, [rax+10h]
0x180004f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f51  mov     [rsp+170h+var_120], rdi
0x180004f56  lea     rcx, [rbp+70h+var_E0]
0x180004f5a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004f60  lea     rcx, [rbp+70h+var_98]
0x180004f64  mov     [rbp+70h+var_A0], r12
0x180004f68  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180004f6e  mov     eax, ebx
0x180004f70  mov     rcx, [rbp+70h+var_50]
0x180004f74  xor     rcx, rsp; StackCookie
0x180004f77  call    __security_check_cookie
0x180004f7c  add     rsp, 138h
0x180004f83  pop     r15
0x180004f85  pop     r14
0x180004f87  pop     r13
0x180004f89  pop     r12
0x180004f8b  pop     rdi
0x180004f8c  pop     rsi
0x180004f8d  pop     rbx
0x180004f8e  pop     rbp
0x180004f8f  retn
```
