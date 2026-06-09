# ABO_NODE::GetDataPathsInternal(ulong,ulong,MULTISZ *,ushort const *)

- ea: `0x180008c90`
- end: `0x180008f21`
- name: `?GetDataPathsInternal@ABO_NODE@@AEAAJKKPEAVMULTISZ@@PEBG@Z`
- size: `657`
- prototype: `__int64 __fastcall(ABO_NODE *__hidden this, unsigned int, unsigned int, struct MULTISZ *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180008c90`
- `0x18000e170`

## callees

- `0x18000341a`
- `0x180003460`
- `0x1800077dc`
- `0x180008c90`
- `0x18000fec4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ddd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ddd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008d65`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008e34`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008d65`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008e34`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008d97`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008e66`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008d97`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008e66`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180008e91`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180008e91`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008d46`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008d46`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008d01`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008d01`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008ef6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008ef6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008d89`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008dc7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008e58`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008eb0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008d89`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008dc7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008e58`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008eb0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180008db2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180008e81`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180008e9f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180008db2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180008e81`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180008e9f`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180008d7a`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180008e49`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180008d7a`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180008e49`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180008dd3`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180008dd3`

## pseudocode

```c
__int64 __fastcall ABO_NODE::GetDataPathsInternal(
        ABO_NODE *this,
        unsigned int a2,
        unsigned int a3,
        struct MULTISZ *a4,
        const unsigned __int16 *a5)
{
  const unsigned __int16 *v5; // r14
  signed int DataPathsInternal; // ebx
  int Entry; // eax
  struct PROPERTY_ENTRY *v12; // rdi
  const unsigned __int16 *v13; // rdx
  unsigned __int16 *Str; // rbx
  const unsigned __int16 *v15; // rax
  signed int LastError; // eax
  __int64 v17; // rsi
  struct MULTISZ *v18; // rdi
  __int64 v19; // r15
  unsigned __int16 *v20; // rbx
  const unsigned __int16 *v21; // rax
  const unsigned __int16 *v22; // rax
  struct PROPERTY_ENTRY *v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v25; // [rsp+38h] [rbp-C8h]
  struct MULTISZ *v26; // [rsp+40h] [rbp-C0h]
  _BYTE v27[56]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v28[256]; // [rsp+80h] [rbp-80h] BYREF

  v5 = a5;
  v25 = a2;
  v26 = a4;
  v24 = 0;
  memset_0(v28, 0, sizeof(v28));
  STRU::STRU((STRU *)v27, v28, 0x100u);
  if ( !a4 )
  {
    DataPathsInternal = -2147024809;
    goto LABEL_29;
  }
  Entry = PROPERTY_BAG::FindEntry((ABO_NODE *)((char *)this + 184), a2, &v24);
  v12 = v24;
  if ( Entry < 0 )
    goto LABEL_16;
  if ( a3 && a3 != *((_DWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v24 + 16)) + 3) )
    goto LABEL_15;
  v13 = a5;
  if ( !a5 )
    v13 = &word_18002E968;
  DataPathsInternal = STRU::Copy((STRU *)v27, v13);
  if ( DataPathsInternal < 0 )
    goto LABEL_27;
  if ( STRU::IsEmpty((STRU *)v27) || (Str = STRU::QueryStr((STRU *)v27), Str[STRU::QueryCCH((STRU *)v27) - 1] != 47) )
  {
    DataPathsInternal = STRU::Append((STRU *)v27, L"/");
    if ( DataPathsInternal < 0 )
      goto LABEL_27;
  }
  v15 = STRU::QueryStr((STRU *)v27);
  if ( MULTISZ::Append(a4, v15) )
  {
LABEL_15:
    PROPERTY_MAPPING::DereferencePropertyMapping(v12);
    v12 = 0;
LABEL_16:
    DataPathsInternal = 0;
    v24 = v12;
    v17 = 0;
    if ( *((_DWORD *)this + 10) )
    {
      v18 = v26;
      if ( !a5 )
        v5 = &word_18002E968;
      do
      {
        v19 = *(_QWORD *)(*((_QWORD *)this + 4) + 8 * v17);
        DataPathsInternal = STRU::Copy((STRU *)v27, v5);
        if ( DataPathsInternal < 0 )
          break;
        if ( !STRU::IsEmpty((STRU *)v27) )
        {
          v20 = STRU::QueryStr((STRU *)v27);
          if ( v20[STRU::QueryCCH((STRU *)v27) - 1] == 47 )
            goto LABEL_32;
        }
        DataPathsInternal = STRU::Append((STRU *)v27, L"/");
        if ( DataPathsInternal < 0 )
          break;
LABEL_32:
        v21 = STRU::QueryStr((STRU *)(v19 + 56));
        DataPathsInternal = STRU::Append((STRU *)v27, v21);
        if ( DataPathsInternal < 0 )
          break;
        v22 = STRU::QueryStr((STRU *)v27);
        DataPathsInternal = ABO_NODE::GetDataPathsInternal((ABO_NODE *)v19, v25, a3, v18, v22);
        if ( DataPathsInternal < 0 )
          break;
        v17 = (unsigned int)(v17 + 1);
      }
      while ( (unsigned int)v17 < *((_DWORD *)this + 10) );
      v12 = v24;
    }
    goto LABEL_27;
  }
  LastError = GetLastError();
  DataPathsInternal = LastError;
  if ( LastError > 0 )
    DataPathsInternal = (unsigned __int16)LastError | 0x80070000;
LABEL_27:
  if ( v12 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v12);
LABEL_29:
  STRU::~STRU((STRU *)v27);
  return (unsigned int)DataPathsInternal;
}

```

## disassembly

```asm
0x180008c90  push    rbp
0x180008c92  push    rbx
0x180008c93  push    rsi
0x180008c94  push    rdi
0x180008c95  push    r12
0x180008c97  push    r13
0x180008c99  push    r14
0x180008c9b  push    r15
0x180008c9d  lea     rbp, [rsp-198h]
0x180008ca5  sub     rsp, 298h
0x180008cac  mov     rax, cs:__security_cookie
0x180008cb3  xor     rax, rsp
0x180008cb6  mov     [rbp+1D0h+var_50], rax
0x180008cbd  mov     r14, [rbp+1D0h+arg_20]
0x180008cc4  mov     r12d, r8d
0x180008cc7  mov     ebx, edx
0x180008cc9  mov     [rsp+2D0h+var_298], edx
0x180008ccd  mov     r13, rcx
0x180008cd0  mov     [rsp+2D0h+var_290], r9
0x180008cd5  xor     edx, edx; Val
0x180008cd7  mov     [rsp+2D0h+var_2A0], 0
0x180008ce0  mov     r8d, 200h; Size
0x180008ce6  lea     rcx, [rbp+1D0h+var_250]; void *
0x180008cea  mov     rsi, r9
0x180008ced  call    memset_0
0x180008cf2  mov     r8d, 100h
0x180008cf8  lea     rdx, [rbp+1D0h+var_250]
0x180008cfc  lea     rcx, [rsp+2D0h+var_288]
0x180008d01  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180008d07  test    rsi, rsi
0x180008d0a  jnz     short loc_180008D16
0x180008d0c  mov     ebx, 80070057h
0x180008d11  jmp     loc_180008EF1
0x180008d16  lea     rcx, [r13+0B8h]; this
0x180008d1d  mov     edx, ebx; unsigned int
0x180008d1f  lea     r8, [rsp+2D0h+var_2A0]; struct PROPERTY_ENTRY **
0x180008d24  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x180008d29  mov     rdi, [rsp+2D0h+var_2A0]
0x180008d2e  lea     r15, word_18002E968
0x180008d35  test    eax, eax
0x180008d37  js      loc_180008E05
0x180008d3d  test    r12d, r12d
0x180008d40  jz      short loc_180008D56
0x180008d42  lea     rcx, [rdi+10h]
0x180008d46  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180008d4c  cmp     r12d, [rax+0Ch]
0x180008d50  jnz     loc_180008DFB
0x180008d56  test    r14, r14
0x180008d59  lea     rcx, [rsp+2D0h+var_288]
0x180008d5e  mov     rdx, r14
0x180008d61  cmovz   rdx, r15
0x180008d65  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180008d6b  mov     ebx, eax
0x180008d6d  test    eax, eax
0x180008d6f  js      loc_180008EE4
0x180008d75  lea     rcx, [rsp+2D0h+var_288]
0x180008d7a  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180008d80  test    al, al
0x180008d82  jnz     short loc_180008DA6
0x180008d84  lea     rcx, [rsp+2D0h+var_288]
0x180008d89  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180008d8f  lea     rcx, [rsp+2D0h+var_288]
0x180008d94  mov     rbx, rax
0x180008d97  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180008d9d  dec     eax
0x180008d9f  cmp     word ptr [rbx+rax*2], 2Fh ; '/'
0x180008da4  jz      short loc_180008DC2
0x180008da6  lea     rdx, asc_18002E8E8; "/"
0x180008dad  lea     rcx, [rsp+2D0h+var_288]
0x180008db2  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180008db8  mov     ebx, eax
0x180008dba  test    eax, eax
0x180008dbc  js      loc_180008EE4
0x180008dc2  lea     rcx, [rsp+2D0h+var_288]
0x180008dc7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180008dcd  mov     rdx, rax
0x180008dd0  mov     rcx, rsi
0x180008dd3  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x180008dd9  test    eax, eax
0x180008ddb  jnz     short loc_180008DFB
0x180008ddd  call    cs:__imp_GetLastError
0x180008de3  mov     ebx, eax
0x180008de5  test    eax, eax
0x180008de7  jle     loc_180008EE4
0x180008ded  movzx   ebx, ax
0x180008df0  or      ebx, 80070000h
0x180008df6  jmp     loc_180008EE4
0x180008dfb  mov     rcx, rdi; this
0x180008dfe  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180008e03  xor     edi, edi
0x180008e05  xor     ebx, ebx
0x180008e07  mov     [rsp+2D0h+var_2A0], rdi
0x180008e0c  xor     esi, esi
0x180008e0e  cmp     [r13+28h], ebx
0x180008e12  jbe     loc_180008EE4
0x180008e18  mov     rdi, [rsp+2D0h+var_290]
0x180008e1d  test    r14, r14
0x180008e20  cmovz   r14, r15
0x180008e24  mov     rax, [r13+20h]
0x180008e28  lea     rcx, [rsp+2D0h+var_288]
0x180008e2d  mov     rdx, r14
0x180008e30  mov     r15, [rax+rsi*8]
0x180008e34  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180008e3a  mov     ebx, eax
0x180008e3c  test    eax, eax
0x180008e3e  js      loc_180008EDF
0x180008e44  lea     rcx, [rsp+2D0h+var_288]
0x180008e49  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180008e4f  test    al, al
0x180008e51  jnz     short loc_180008E75
0x180008e53  lea     rcx, [rsp+2D0h+var_288]
0x180008e58  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180008e5e  lea     rcx, [rsp+2D0h+var_288]
0x180008e63  mov     rbx, rax
0x180008e66  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180008e6c  dec     eax
0x180008e6e  cmp     word ptr [rbx+rax*2], 2Fh ; '/'
0x180008e73  jz      short loc_180008E8D
0x180008e75  lea     rdx, asc_18002E8E8; "/"
0x180008e7c  lea     rcx, [rsp+2D0h+var_288]
0x180008e81  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180008e87  mov     ebx, eax
0x180008e89  test    eax, eax
0x180008e8b  js      short loc_180008EDF
0x180008e8d  lea     rcx, [r15+38h]
0x180008e91  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180008e97  mov     rdx, rax
0x180008e9a  lea     rcx, [rsp+2D0h+var_288]
0x180008e9f  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180008ea5  mov     ebx, eax
0x180008ea7  test    eax, eax
0x180008ea9  js      short loc_180008EDF
0x180008eab  lea     rcx, [rsp+2D0h+var_288]
0x180008eb0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180008eb6  mov     edx, [rsp+2D0h+var_298]; unsigned int
0x180008eba  mov     r9, rdi; struct MULTISZ *
0x180008ebd  mov     r8d, r12d; unsigned int
0x180008ec0  mov     [rsp+2D0h+var_2B0], rax; unsigned __int16 *
0x180008ec5  mov     rcx, r15; this
0x180008ec8  call    ?GetDataPathsInternal@ABO_NODE@@AEAAJKKPEAVMULTISZ@@PEBG@Z; ABO_NODE::GetDataPathsInternal(ulong,ulong,MULTISZ *,ushort const *)
0x180008ecd  mov     ebx, eax
0x180008ecf  test    eax, eax
0x180008ed1  js      short loc_180008EDF
0x180008ed3  inc     esi
0x180008ed5  cmp     esi, [r13+28h]
0x180008ed9  jb      loc_180008E24
0x180008edf  mov     rdi, [rsp+2D0h+var_2A0]
0x180008ee4  test    rdi, rdi
0x180008ee7  jz      short loc_180008EF1
0x180008ee9  mov     rcx, rdi; this
0x180008eec  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180008ef1  lea     rcx, [rsp+2D0h+var_288]
0x180008ef6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008efc  mov     eax, ebx
0x180008efe  mov     rcx, [rbp+1D0h+var_50]
0x180008f05  xor     rcx, rsp; StackCookie
0x180008f08  call    __security_check_cookie
0x180008f0d  add     rsp, 298h
0x180008f14  pop     r15
0x180008f16  pop     r14
0x180008f18  pop     r13
0x180008f1a  pop     r12
0x180008f1c  pop     rdi
0x180008f1d  pop     rsi
0x180008f1e  pop     rbx
0x180008f1f  pop     rbp
0x180008f20  retn
```
