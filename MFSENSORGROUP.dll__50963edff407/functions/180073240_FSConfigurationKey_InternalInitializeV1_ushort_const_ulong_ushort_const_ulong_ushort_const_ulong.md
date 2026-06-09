# FSConfigurationKey::InternalInitializeV1(ushort const *,ulong,ushort const *,ulong,ushort const *,ulong)

- ea: `0x180073240`
- end: `0x1800736f7`
- name: `?InternalInitializeV1@FSConfigurationKey@@MEAAJPEBGK0K0K@Z`
- size: `1207`
- prototype: `__int64 __usercall@<rax>(FSConfigurationKey *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callees

- `0x1800031fc`
- `0x180005fa0`
- `0x180015e80`
- `0x180016328`
- `0x18001635c`
- `0x18002943c`
- `0x18003c8c0`
- `0x180044b28`
- `0x180045900`
- `0x180073240`
- `0x180073930`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800732f3`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18007337f`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180073407`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800732f3`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18007337f`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180073407`

## pseudocode

```c
__int64 __fastcall FSConfigurationKey::InternalInitializeV1(
        FSConfigurationKey *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int16 *a6,
        unsigned int a7)
{
  unsigned __int64 v8; // rbx
  void **v10; // r13
  UCHAR *v11; // r14
  void **unique; // rax
  void *v13; // rcx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  char v17; // dl
  __int16 v18; // r8
  int v19; // r9d
  unsigned __int64 v20; // r15
  unsigned __int16 **v21; // r12
  void **v22; // rax
  void *v23; // rcx
  char v24; // dl
  __int16 v25; // r8
  int v26; // r9d
  unsigned __int64 v27; // rbx
  unsigned __int16 **v28; // rsi
  void **v29; // rax
  void *v30; // rcx
  char v31; // dl
  __int16 v32; // r8
  int v33; // r9d
  unsigned __int64 v34; // rax
  void *v35; // rbx
  __int64 v36; // r15
  void **v37; // rax
  void *v38; // rcx
  const unsigned __int16 *v39; // r8
  char *v40; // rsi
  __int64 v41; // rdx
  __int64 i; // r8
  __int64 v43; // rdx
  char v44; // al
  wchar_t v46; // [rsp+20h] [rbp-30h]
  wchar_t v47; // [rsp+20h] [rbp-30h]
  wchar_t v48; // [rsp+20h] [rbp-30h]
  unsigned int *v49; // [rsp+28h] [rbp-28h]
  unsigned int *v50; // [rsp+28h] [rbp-28h]
  unsigned int *v51; // [rsp+28h] [rbp-28h]
  unsigned int v52; // [rsp+28h] [rbp-28h]
  unsigned int v53; // [rsp+28h] [rbp-28h]
  unsigned int v54; // [rsp+28h] [rbp-28h]
  PUCHAR pbInput[2]; // [rsp+40h] [rbp-10h] BYREF
  void *Block; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v57; // [rsp+A0h] [rbp+50h] BYREF
  unsigned __int16 *v58; // [rsp+A8h] [rbp+58h]

  v58 = a4;
  v57 = a3;
  v8 = a3;
  v10 = (void **)((char *)this + 224);
  v11 = 0;
  pbInput[0] = 0;
  unique = (void **)wil::make_unique_nothrow<unsigned short [0]>(&Block, a3);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(v10, unique);
  v13 = Block;
  Block = 0;
  if ( v13 )
    operator delete(v13);
  if ( !*v10 )
  {
    v14 = -2147024882;
    v15 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_61;
    v16 = 56;
    goto LABEL_6;
  }
  v14 = StringCchCopyW((unsigned __int16 *)*v10, v8, a2);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 57;
LABEL_6:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this, v14);
      goto LABEL_61;
    }
    goto LABEL_61;
  }
  o((wchar_t)*v10, v17, v18, v19, v46, *(long double *)&v49);
  v20 = a5;
  v21 = (unsigned __int16 **)((char *)this + 232);
  v22 = (void **)wil::make_unique_nothrow<unsigned short [0]>(&Block, a5);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)this + 29, v22);
  v23 = Block;
  Block = 0;
  if ( v23 )
    operator delete(v23);
  if ( !*v21 )
  {
    v14 = -2147024882;
    v15 = -2147024882;
    if ( g_wppLevels )
    {
      v16 = 58;
      goto LABEL_6;
    }
LABEL_61:
    if ( byte_18008D62D )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 72, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this, v15);
    goto LABEL_63;
  }
  v14 = StringCchCopyW(*v21, v20, v58);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 59;
      goto LABEL_6;
    }
    goto LABEL_61;
  }
  o((wchar_t)*v21, v24, v25, v26, v47, *(long double *)&v50);
  v27 = a7;
  v28 = (unsigned __int16 **)((char *)this + 240);
  v29 = (void **)wil::make_unique_nothrow<unsigned short [0]>(&Block, a7);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)this + 30, v29);
  v30 = Block;
  Block = 0;
  if ( v30 )
    operator delete(v30);
  if ( !*v28 )
  {
    v14 = -2147024882;
    v15 = -2147024882;
    if ( g_wppLevels )
    {
      v16 = 60;
      goto LABEL_6;
    }
    goto LABEL_61;
  }
  v14 = StringCchCopyW(*v28, v27, a6);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 61;
      goto LABEL_6;
    }
    goto LABEL_61;
  }
  o((wchar_t)*v28, v31, v32, v33, v48, *(long double *)&v51);
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_qSSS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)*v28, (__int64)*v21, (__int64)*v10);
  v34 = a7 + (_DWORD)v20 + v57;
  v35 = (void *)v34;
  if ( !(a7 + (_DWORD)v20 + v57) )
  {
    v14 = -2147024362;
    v15 = -2147024362;
    if ( g_wppLevels )
    {
      v16 = 63;
      goto LABEL_6;
    }
    goto LABEL_61;
  }
  v36 = 2 * v34;
  if ( !(2 * v34) )
  {
    v14 = -2147024362;
    v15 = -2147024362;
    if ( g_wppLevels )
    {
      v16 = 64;
      goto LABEL_6;
    }
    goto LABEL_61;
  }
  v37 = (void **)wil::make_unique_nothrow<unsigned short [0]>(&Block, v34);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)pbInput, v37);
  v38 = Block;
  Block = 0;
  if ( v38 )
    operator delete(v38);
  v11 = pbInput[0];
  if ( !pbInput[0] )
  {
    v14 = -2147024882;
    v15 = -2147024882;
    if ( g_wppLevels )
    {
      v16 = (unsigned int)(LODWORD(pbInput[0]) + 65);
      goto LABEL_6;
    }
    goto LABEL_61;
  }
  memset_0(pbInput[0], 0, v36);
  v39 = (const unsigned __int16 *)*v10;
  pbInput[0] = v11;
  Block = v35;
  v14 = StringCchCopyExW(
          (unsigned __int16 *)v11,
          (unsigned __int64)v35,
          v39,
          (unsigned __int16 **)pbInput,
          (unsigned __int64 *)&Block,
          v52);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 66;
      goto LABEL_6;
    }
    goto LABEL_61;
  }
  v14 = StringCchCopyExW(
          (unsigned __int16 *)pbInput[0],
          (unsigned __int64)Block,
          *v21,
          (unsigned __int16 **)pbInput,
          (unsigned __int64 *)&Block,
          v53);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 67;
      goto LABEL_6;
    }
    goto LABEL_61;
  }
  v14 = StringCchCopyExW(
          (unsigned __int16 *)pbInput[0],
          (unsigned __int64)Block,
          *v28,
          (unsigned __int16 **)pbInput,
          (unsigned __int64 *)&Block,
          v54);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 68;
      goto LABEL_6;
    }
    goto LABEL_61;
  }
  v40 = (char *)this + 56;
  v14 = FSCreateHash(0, v11, v36, (PUCHAR)this + 56, 0x20u, &v57);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 69;
      goto LABEL_6;
    }
    goto LABEL_61;
  }
  if ( this == (FSConfigurationKey *)-56LL )
  {
    v15 = -2147024809;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids,
        -56,
        -2147024809);
    goto LABEL_61;
  }
  v41 = 0;
  for ( i = 0; i != 32; ++i )
  {
    *((_WORD *)this + v41 + 44) = a0123456789abcd[(unsigned __int64)(unsigned __int8)v40[i] >> 4];
    v43 = (unsigned int)(v41 + 1);
    v44 = v40[i];
    *((_WORD *)this + v43 + 44) = a0123456789abcd[v44 & 0xF];
    v41 = (unsigned int)(v43 + 1);
  }
  *((_WORD *)this + v41 + 44) = 0;
  v14 = FSConfigurationKey::InternalSerialize(this);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 71;
      goto LABEL_6;
    }
    goto LABEL_61;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 73, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this, v14);
LABEL_63:
  if ( v11 )
    operator delete(v11);
  return v15;
}

```

## disassembly

```asm
0x180073240  mov     [rsp-38h+arg_8], rbx
0x180073245  mov     [rsp-38h+arg_18], r9
0x18007324a  mov     [rsp-38h+arg_10], r8d
0x18007324f  push    rbp
0x180073250  push    rsi
0x180073251  push    rdi
0x180073252  push    r12
0x180073254  push    r13
0x180073256  push    r14
0x180073258  push    r15
0x18007325a  mov     rbp, rsp
0x18007325d  sub     rsp, 50h
0x180073261  mov     rsi, rdx
0x180073264  mov     ebx, r8d
0x180073267  mov     rdi, rcx
0x18007326a  mov     edx, r8d
0x18007326d  lea     r13, [rcx+0E0h]
0x180073274  xor     r14d, r14d
0x180073277  lea     rcx, [rbp+Block]
0x18007327b  mov     [rbp+pbInput], r14
0x18007327f  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180073284  mov     rdx, rax
0x180073287  mov     rcx, r13
0x18007328a  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18007328f  mov     rcx, [rbp+Block]; Block
0x180073293  mov     [rbp+Block], r14
0x180073297  test    rcx, rcx
0x18007329a  jz      short loc_1800732A1
0x18007329c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800732a1  mov     rcx, [r13+0]; unsigned __int16 *
0x1800732a5  test    rcx, rcx
0x1800732a8  jnz     short loc_1800732CA
0x1800732aa  mov     eax, 8007000Eh
0x1800732af  mov     ebx, eax
0x1800732b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800732b8  jb      loc_1800736A1
0x1800732be  lea     edx, [rcx+38h]
0x1800732c1  mov     dword ptr [rsp+50h+var_30], eax
0x1800732c5  jmp     loc_180073687
0x1800732ca  mov     r8, rsi; unsigned __int16 *
0x1800732cd  mov     rdx, rbx; unsigned __int64
0x1800732d0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800732d5  mov     ebx, eax
0x1800732d7  test    eax, eax
0x1800732d9  jns     short loc_1800732EF
0x1800732db  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800732e2  jb      loc_1800736A1
0x1800732e8  mov     edx, 39h ; '9'
0x1800732ed  jmp     short loc_1800732C1
0x1800732ef  mov     rcx, [r13+0]
0x1800732f3  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800732f9  mov     r15d, [rbp+arg_20]
0x1800732fd  lea     rcx, [rbp+Block]
0x180073301  mov     edx, r15d
0x180073304  lea     r12, [rdi+0E8h]
0x18007330b  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180073310  mov     rdx, rax
0x180073313  mov     rcx, r12
0x180073316  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18007331b  mov     rcx, [rbp+Block]; Block
0x18007331f  mov     [rbp+Block], r14
0x180073323  test    rcx, rcx
0x180073326  jz      short loc_18007332D
0x180073328  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007332d  mov     rcx, [r12]; unsigned __int16 *
0x180073331  test    rcx, rcx
0x180073334  jnz     short loc_180073352
0x180073336  mov     eax, 8007000Eh
0x18007333b  mov     ebx, eax
0x18007333d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073344  jb      loc_1800736A1
0x18007334a  lea     edx, [rcx+3Ah]
0x18007334d  jmp     loc_1800732C1
0x180073352  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x180073356  mov     rdx, r15; unsigned __int64
0x180073359  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007335e  mov     ebx, eax
0x180073360  test    eax, eax
0x180073362  jns     short loc_18007337B
0x180073364  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007336b  jb      loc_1800736A1
0x180073371  mov     edx, 3Bh ; ';'
0x180073376  jmp     loc_1800732C1
0x18007337b  mov     rcx, [r12]
0x18007337f  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x180073385  mov     ebx, [rbp+arg_30]
0x180073388  lea     rcx, [rbp+Block]
0x18007338c  mov     edx, ebx
0x18007338e  lea     rsi, [rdi+0F0h]
0x180073395  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18007339a  mov     rdx, rax
0x18007339d  mov     rcx, rsi
0x1800733a0  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x1800733a5  mov     rcx, [rbp+Block]; Block
0x1800733a9  mov     [rbp+Block], r14
0x1800733ad  test    rcx, rcx
0x1800733b0  jz      short loc_1800733B7
0x1800733b2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800733b7  mov     rcx, [rsi]; unsigned __int16 *
0x1800733ba  test    rcx, rcx
0x1800733bd  jnz     short loc_1800733DB
0x1800733bf  mov     eax, 8007000Eh
0x1800733c4  mov     ebx, eax
0x1800733c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800733cd  jb      loc_1800736A1
0x1800733d3  lea     edx, [rcx+3Ch]
0x1800733d6  jmp     loc_1800732C1
0x1800733db  mov     r8, [rbp+arg_28]; unsigned __int16 *
0x1800733df  mov     rdx, rbx; unsigned __int64
0x1800733e2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800733e7  mov     ebx, eax
0x1800733e9  test    eax, eax
0x1800733eb  jns     short loc_180073404
0x1800733ed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800733f4  jb      loc_1800736A1
0x1800733fa  mov     edx, 3Dh ; '='
0x1800733ff  jmp     loc_1800732C1
0x180073404  mov     rcx, [rsi]
0x180073407  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18007340d  cmp     cs:byte_18008D62D, 8
0x180073414  jb      short loc_18007344B
0x180073416  mov     rax, [r13+0]
0x18007341a  mov     edx, 3Eh ; '>'
0x18007341f  mov     rcx, cs:WPP_GLOBAL_Control
0x180073426  mov     r9, rdi
0x180073429  mov     [rsp+50h+var_20], rax; __int64
0x18007342e  mov     rax, [r12]
0x180073432  mov     [rsp+50h+var_28], rax; unsigned int
0x180073437  mov     rax, [rsi]
0x18007343a  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180073441  mov     [rsp+50h+var_30], rax; __int64
0x180073446  call    WPP_SF_qSSS
0x18007344b  mov     eax, [rbp+arg_10]
0x18007344e  add     eax, r15d
0x180073451  add     eax, [rbp+arg_30]
0x180073454  mov     ebx, eax
0x180073456  jnz     short loc_180073476
0x180073458  mov     eax, 80070216h
0x18007345d  mov     ebx, eax
0x18007345f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073466  jb      loc_1800736A1
0x18007346c  mov     edx, 3Fh ; '?'
0x180073471  jmp     loc_1800732C1
0x180073476  lea     r15, [rax+rax]
0x18007347a  test    r15, r15
0x18007347d  jnz     short loc_18007349C
0x18007347f  mov     eax, 80070216h
0x180073484  mov     ebx, eax
0x180073486  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007348d  jb      loc_1800736A1
0x180073493  lea     edx, [r15+40h]
0x180073497  jmp     loc_1800732C1
0x18007349c  mov     rdx, rbx
0x18007349f  lea     rcx, [rbp+Block]
0x1800734a3  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x1800734a8  mov     rdx, rax
0x1800734ab  lea     rcx, [rbp+pbInput]
0x1800734af  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x1800734b4  mov     rcx, [rbp+Block]; Block
0x1800734b8  mov     [rbp+Block], r14
0x1800734bc  test    rcx, rcx
0x1800734bf  jz      short loc_1800734C6
0x1800734c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800734c6  mov     r14, [rbp+pbInput]
0x1800734ca  test    r14, r14
0x1800734cd  jnz     short loc_1800734EC
0x1800734cf  mov     eax, 8007000Eh
0x1800734d4  mov     ebx, eax
0x1800734d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800734dd  jb      loc_1800736A1
0x1800734e3  lea     edx, [r14+41h]
0x1800734e7  jmp     loc_1800732C1
0x1800734ec  mov     r8, r15; Size
0x1800734ef  xor     edx, edx; Val
0x1800734f1  mov     rcx, r14; void *
0x1800734f4  call    memset_0
0x1800734f9  mov     r8, [r13+0]; unsigned __int16 *
0x1800734fd  lea     rax, [rbp+Block]
0x180073501  lea     r9, [rbp+pbInput]; unsigned __int16 **
0x180073505  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x18007350a  mov     rdx, rbx; unsigned __int64
0x18007350d  mov     [rbp+pbInput], r14
0x180073511  mov     rcx, r14; unsigned __int16 *
0x180073514  mov     [rbp+Block], rbx
0x180073518  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18007351d  mov     ebx, eax
0x18007351f  test    eax, eax
0x180073521  jns     short loc_18007353A
0x180073523  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007352a  jb      loc_1800736A1
0x180073530  mov     edx, 42h ; 'B'
0x180073535  jmp     loc_1800732C1
0x18007353a  mov     r8, [r12]; unsigned __int16 *
0x18007353e  lea     rax, [rbp+Block]
0x180073542  mov     rdx, [rbp+Block]; unsigned __int64
0x180073546  lea     r9, [rbp+pbInput]; unsigned __int16 **
0x18007354a  mov     rcx, [rbp+pbInput]; unsigned __int16 *
0x18007354e  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x180073553  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180073558  mov     ebx, eax
0x18007355a  test    eax, eax
0x18007355c  jns     short loc_180073575
0x18007355e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073565  jb      loc_1800736A1
0x18007356b  mov     edx, 43h ; 'C'
0x180073570  jmp     loc_1800732C1
0x180073575  mov     r8, [rsi]; unsigned __int16 *
0x180073578  lea     rax, [rbp+Block]
0x18007357c  mov     rdx, [rbp+Block]; unsigned __int64
0x180073580  lea     r9, [rbp+pbInput]; unsigned __int16 **
0x180073584  mov     rcx, [rbp+pbInput]; unsigned __int16 *
0x180073588  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x18007358d  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180073592  mov     ebx, eax
0x180073594  test    eax, eax
0x180073596  jns     short loc_1800735AF
0x180073598  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007359f  jb      loc_1800736A1
0x1800735a5  mov     edx, 44h ; 'D'
0x1800735aa  jmp     loc_1800732C1
0x1800735af  lea     rax, [rbp+arg_10]
0x1800735b3  mov     r8d, r15d; cbInput
0x1800735b6  mov     [rsp+50h+var_28], rax; unsigned int *
0x1800735bb  lea     rsi, [rdi+38h]
0x1800735bf  mov     r9, rsi; pbOutput
0x1800735c2  mov     dword ptr [rsp+50h+var_30], 20h ; ' '; unsigned int
0x1800735ca  mov     rdx, r14; pbInput
0x1800735cd  xor     ecx, ecx; pszAlgId
0x1800735cf  call    ?FSCreateHash@@YAJPEBGPEAEK1KPEAK@Z; FSCreateHash(ushort const *,uchar *,ulong,uchar *,ulong,ulong *)
0x1800735d4  mov     ebx, eax
0x1800735d6  test    eax, eax
0x1800735d8  jns     short loc_1800735F1
0x1800735da  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800735e1  jb      loc_1800736A1
0x1800735e7  mov     edx, 45h ; 'E'
0x1800735ec  jmp     loc_1800732C1
0x1800735f1  test    rsi, rsi
0x1800735f4  jz      short loc_180073670
0x1800735f6  xor     edx, edx
0x1800735f8  lea     r9, a0123456789abcd; "0123456789ABCDEF"
0x1800735ff  xor     r8d, r8d
0x180073602  movzx   eax, byte ptr [rsi+r8]
0x180073607  shr     rax, 4
0x18007360b  movzx   eax, word ptr [r9+rax*2]
0x180073610  mov     [rdi+rdx*2+58h], ax
0x180073615  inc     edx
0x180073617  movzx   eax, byte ptr [rsi+r8]
0x18007361c  inc     r8
0x18007361f  and     eax, 0Fh
0x180073622  movzx   eax, word ptr [r9+rax*2]
0x180073627  mov     [rdi+rdx*2+58h], ax
0x18007362c  inc     edx
0x18007362e  cmp     r8, 20h ; ' '
0x180073632  jnz     short loc_180073602
0x180073634  xor     eax, eax
0x180073636  mov     [rdi+rdx*2+58h], ax
0x18007363b  mov     rcx, rdi; this
0x18007363e  call    ?InternalSerialize@FSConfigurationKey@@IEAAJXZ; FSConfigurationKey::InternalSerialize(void)
0x180073643  mov     ebx, eax
0x180073645  test    eax, eax
0x180073647  jns     short loc_18007365C
0x180073649  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073650  jb      short loc_1800736A1
0x180073652  mov     edx, 47h ; 'G'
0x180073657  jmp     loc_1800732C1
0x18007365c  cmp     cs:byte_18008D62D, 8
0x180073663  jb      short loc_1800736D0
0x180073665  mov     edx, 49h ; 'I'
0x18007366a  mov     dword ptr [rsp+50h+var_30], eax
0x18007366e  jmp     short loc_1800736B3
0x180073670  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073677  mov     ebx, 80070057h
0x18007367c  jb      short loc_1800736A1
0x18007367e  mov     edx, 46h ; 'F'
0x180073683  mov     dword ptr [rsp+50h+var_30], ebx
0x180073687  mov     rcx, cs:WPP_GLOBAL_Control
0x18007368e  lea     r8, WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids
0x180073695  mov     r9, rdi
0x180073698  mov     rcx, [rcx+10h]
0x18007369c  call    WPP_SF_qD
0x1800736a1  cmp     cs:byte_18008D62D, 1
0x1800736a8  jb      short loc_1800736D0
0x1800736aa  mov     edx, 48h ; 'H'
0x1800736af  mov     dword ptr [rsp+50h+var_30], ebx
0x1800736b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800736ba  lea     r8, WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids
0x1800736c1  mov     r9, rdi
0x1800736c4  mov     rcx, [rcx+0D8h]
0x1800736cb  call    WPP_SF_qD
0x1800736d0  test    r14, r14
0x1800736d3  jz      short loc_1800736DD
0x1800736d5  mov     rcx, r14; Block
0x1800736d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800736dd  mov     eax, ebx
0x1800736df  mov     rbx, [rsp+50h+arg_8]
0x1800736e7  add     rsp, 50h
0x1800736eb  pop     r15
0x1800736ed  pop     r14
0x1800736ef  pop     r13
0x1800736f1  pop     r12
  ... truncated ...
```
