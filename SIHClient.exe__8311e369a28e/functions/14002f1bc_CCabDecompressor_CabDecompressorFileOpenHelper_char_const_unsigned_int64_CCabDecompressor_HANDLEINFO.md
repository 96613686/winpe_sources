# CCabDecompressor::CabDecompressorFileOpenHelper(char const *,unsigned __int64,CCabDecompressor *,HANDLEINFO * *)

- ea: `0x14002f1bc`
- end: `0x14002f509`
- name: `?CabDecompressorFileOpenHelper@CCabDecompressor@@CAJPEBD_KPEAV1@PEAPEAUHANDLEINFO@@@Z`
- size: `845`
- prototype: `__int64 __fastcall(const char *, unsigned int, struct CCabDecompressor *, struct HANDLEINFO **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x14002fb40`

## callees

- `0x140008de4`
- `0x14000cdb8`
- `0x14000ce30`
- `0x14000efd0`
- `0x14000feec`
- `0x1400129cc`
- `0x14002f1bc`
- `0x140030484`
- `0x14003be88`
- `0x140045dc0`
- `0x140045de4`
- `0x140045df0`
- `0x14004cd80`

## string_xrefs

- `0x14002f20d`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`
- `0x14002f286`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`
- `0x14002f37d`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`
- `0x14002f43b`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`
- `0x14002f424`: `C:\__w\1\s\src\Client\lib\CabDecompressor\OutputMemoryFile.cpp`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::CabDecompressorFileOpenHelper(
        const char *a1,
        unsigned int a2,
        struct CCabDecompressor *a3,
        struct HANDLEINFO **a4)
{
  char *v7; // rax
  void *v8; // r14
  int FileAndDirectories; // ebp
  char *v10; // rax
  char *v11; // rsi
  COutputMemoryFile *v12; // rdi
  char *v13; // rdx
  __int64 v14; // rcx
  char v15; // al
  char *v16; // rax
  int v17; // eax
  void *v18; // rbx
  __int64 v19; // rdx
  unsigned int v20; // r8d
  unsigned int v21; // r9d
  _QWORD *v22; // rax
  _QWORD *v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  char **v27; // rax
  struct HANDLEINFO **v28; // rax
  char **v30; // rax
  struct _SECURITY_ATTRIBUTES *v31; // [rsp+20h] [rbp-2A8h]
  int v32; // [rsp+20h] [rbp-2A8h]
  unsigned int v33; // [rsp+28h] [rbp-2A0h]
  unsigned int v34; // [rsp+30h] [rbp-298h]
  void *v35; // [rsp+38h] [rbp-290h]
  void *lpMem; // [rsp+50h] [rbp-278h] BYREF
  struct HANDLEINFO **v37; // [rsp+58h] [rbp-270h]
  wchar_t v38[264]; // [rsp+60h] [rbp-268h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+0h]

  v37 = a4;
  *a4 = 0;
  v7 = (char *)SusAlloc(0x20u);
  v8 = v7;
  if ( !v7 )
  {
    FileAndDirectories = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
      (const char *)0x8007000ELL,
      (int)v31);
    return (unsigned int)FileAndDirectories;
  }
  *(_QWORD *)(v7 + 20) = 0;
  *(_DWORD *)v7 = 1;
  v10 = (char *)operator new(0x120u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    *(_QWORD *)v10 = 0;
    *((_QWORD *)v10 + 1) = 0;
    *((_QWORD *)v10 + 2) = 0;
    v10[24] = 0;
  }
  else
  {
    v11 = 0;
  }
  FileAndDirectories = -2147024882;
  v12 = (COutputMemoryFile *)v11;
  if ( !v11 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x260,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
      (const char *)0x8007000ELL,
      (int)v31);
    FileAndDirectories = -2147024882;
    goto LABEL_41;
  }
  v13 = v11 + 24;
  v14 = 260;
  do
  {
    if ( v14 == -2147483386 )
      break;
    v15 = v13[a1 - (v11 + 24)];
    if ( !v15 )
      break;
    *v13++ = v15;
    --v14;
  }
  while ( v14 );
  v16 = v13 - 1;
  if ( v14 )
    v16 = v13;
  *v16 = 0;
  if ( *((_DWORD *)a3 + 35) != 1 )
  {
    v22 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v23 = v22;
    if ( v22 )
    {
      v22[1] = 0;
      *v22 = &CSafeBuffer<unsigned char>::`vftable';
      v22[2] = 0;
      if ( a2 )
        CSafeBuffer<unsigned char>::resize(v22, a2);
    }
    else
    {
      v23 = 0;
    }
    *((_QWORD *)v11 + 2) = v23;
    if ( v23 )
    {
      if ( v23[1] )
      {
        *((_QWORD *)v8 + 1) = v23;
        *((_DWORD *)v8 + 4) = 0;
        goto LABEL_35;
      }
      v24 = 39;
    }
    else
    {
      v24 = 38;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\OutputMemoryFile.cpp",
      (const char *)0x8007000ELL,
      (int)v31);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x285,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
      (const char *)0x8007000ELL,
      v32);
    goto LABEL_41;
  }
  lpMem = 0;
  memset(v38, 0, 522);
  v17 = ConvertAnsiToWide_Alloc(a1, (wchar_t **)&lpMem);
  v18 = lpMem;
  FileAndDirectories = v17;
  if ( v17 < 0 )
  {
    v19 = 621;
    goto LABEL_21;
  }
  FileAndDirectories = WUPathCchCombine(v38, 0x105u, *((const wchar_t **)a3 + 16), (const wchar_t *)lpMem);
  if ( FileAndDirectories < 0 )
  {
    v19 = 626;
    goto LABEL_21;
  }
  FileAndDirectories = SusCreateFileAndDirectories(
                         v38,
                         *((_DWORD *)a3 + 38),
                         v20,
                         v21,
                         v31,
                         v33,
                         v34,
                         v35,
                         (void **)v8 + 1);
  if ( FileAndDirectories < 0 )
  {
    v19 = 636;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
      (const char *)(unsigned int)FileAndDirectories,
      (int)v31);
    if ( v18 )
      SusFree(v18);
    goto LABEL_41;
  }
  *((_DWORD *)v8 + 4) = 1;
  if ( v18 )
    SusFree(v18);
LABEL_35:
  v25 = *((_QWORD *)a3 + 8);
  v12 = 0;
  v26 = *(_QWORD *)(v25 + 16);
  *(_QWORD *)(v25 + 32) = v26;
  ++*(_DWORD *)(v25 + 24);
  *(_QWORD *)v11 = v26;
  if ( v26 )
  {
    *((_QWORD *)v11 + 1) = *(_QWORD *)(v26 + 8);
    *(_QWORD *)(v26 + 8) = v11;
    v30 = (char **)*((_QWORD *)v11 + 1);
    if ( v30 )
    {
      *v30 = v11;
      goto LABEL_40;
    }
  }
  else
  {
    v27 = *(char ***)(v25 + 8);
    if ( v27 )
      *v27 = v11;
    *((_QWORD *)v11 + 1) = *(_QWORD *)(v25 + 8);
    *(_QWORD *)(v25 + 8) = v11;
    if ( *(_QWORD *)(v25 + 16) )
      goto LABEL_40;
  }
  *(_QWORD *)(v25 + 16) = v11;
LABEL_40:
  v28 = v37;
  FileAndDirectories = 0;
  *(_QWORD *)(v25 + 32) = v11;
  *v28 = (struct HANDLEINFO *)v8;
  v8 = 0;
LABEL_41:
  SusFree(v8);
  if ( v12 )
  {
    COutputMemoryFile::~COutputMemoryFile(v12);
    operator delete(v12, (const struct std::nothrow_t *)0x120);
  }
  return (unsigned int)FileAndDirectories;
}

```

## disassembly

```asm
0x14002f1bc  push    rbx
0x14002f1be  push    rbp
0x14002f1bf  push    rsi
0x14002f1c0  push    rdi
0x14002f1c1  push    r12
0x14002f1c3  push    r13
0x14002f1c5  push    r14
0x14002f1c7  push    r15
0x14002f1c9  sub     rsp, 288h
0x14002f1d0  mov     rax, cs:__security_cookie
0x14002f1d7  xor     rax, rsp
0x14002f1da  mov     [rsp+2C8h+var_58], rax
0x14002f1e2  xor     ebx, ebx
0x14002f1e4  mov     [rsp+2C8h+var_270], r9
0x14002f1e9  mov     r12, rcx
0x14002f1ec  mov     [r9], rbx
0x14002f1ef  mov     r13, r8
0x14002f1f2  mov     r15, rdx
0x14002f1f5  lea     ecx, [rbx+20h]; unsigned __int64
0x14002f1f8  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x14002f1fd  mov     r14, rax
0x14002f200  test    rax, rax
0x14002f203  jnz     short loc_14002F22B
0x14002f205  mov     rcx, [rsp+2C8h]; this
0x14002f20d  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x14002f214  mov     ebp, 8007000Eh
0x14002f219  mov     edx, 255h; void *
0x14002f21e  mov     r9d, ebp; char *
0x14002f221  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002f226  jmp     loc_14002F4C9
0x14002f22b  mov     [rax+14h], rbx
0x14002f22f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002f236  mov     ecx, 120h; unsigned __int64
0x14002f23b  mov     dword ptr [rax], 1
0x14002f241  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002f246  xor     r9d, r9d
0x14002f249  mov     rsi, rax
0x14002f24c  test    rax, rax
0x14002f24f  jz      short loc_14002F262
0x14002f251  mov     [rax], r9
0x14002f254  mov     [rax+8], r9
0x14002f258  mov     [rax+10h], r9
0x14002f25c  mov     [rax+18h], r9b
0x14002f260  jmp     short loc_14002F265
0x14002f262  mov     rsi, r9
0x14002f265  mov     rax, rsi
0x14002f268  mov     ebp, 8007000Eh
0x14002f26d  neg     rax
0x14002f270  mov     rdi, rsi
0x14002f273  sbb     ebx, ebx
0x14002f275  not     ebx
0x14002f277  and     ebx, ebp
0x14002f279  test    rsi, rsi
0x14002f27c  jnz     short loc_14002F2A1
0x14002f27e  mov     rcx, [rsp+2C8h]; this
0x14002f286  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x14002f28d  mov     r9d, ebx; char *
0x14002f290  mov     edx, 260h; void *
0x14002f295  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002f29a  mov     ebp, ebx
0x14002f29c  jmp     loc_14002F4A7
0x14002f2a1  lea     rdx, [rsi+18h]
0x14002f2a5  mov     r8, r12
0x14002f2a8  sub     r8, rdx
0x14002f2ab  mov     ecx, 104h
0x14002f2b0  lea     rax, [rcx+7FFFFEFAh]
0x14002f2b7  test    rax, rax
0x14002f2ba  jz      short loc_14002F2CF
0x14002f2bc  mov     al, [rdx+r8]
0x14002f2c0  test    al, al
0x14002f2c2  jz      short loc_14002F2CF
0x14002f2c4  mov     [rdx], al
0x14002f2c6  inc     rdx
0x14002f2c9  sub     rcx, 1
0x14002f2cd  jnz     short loc_14002F2B0
0x14002f2cf  test    rcx, rcx
0x14002f2d2  lea     rax, [rdx-1]
0x14002f2d6  cmovnz  rax, rdx
0x14002f2da  mov     [rax], r9b
0x14002f2dd  cmp     dword ptr [r13+8Ch], 1
0x14002f2e5  jnz     loc_14002F3C0
0x14002f2eb  xor     edx, edx; Val
0x14002f2ed  mov     [rsp+2C8h+lpMem], r9
0x14002f2f2  mov     r8d, 208h; Size
0x14002f2f8  mov     [rsp+2C8h+var_268], r9w
0x14002f2fe  lea     rcx, [rsp+2C8h+var_266]; void *
0x14002f303  call    memset
0x14002f308  lea     rdx, [rsp+2C8h+lpMem]; wchar_t **
0x14002f30d  mov     rcx, r12; lpMultiByteStr
0x14002f310  call    ?ConvertAnsiToWide_Alloc@@YAJPEBDPEAPEA_W@Z; ConvertAnsiToWide_Alloc(char const *,wchar_t * *)
0x14002f315  mov     rbx, [rsp+2C8h+lpMem]
0x14002f31a  xor     r12d, r12d
0x14002f31d  mov     ebp, eax
0x14002f31f  test    eax, eax
0x14002f321  jns     short loc_14002F32A
0x14002f323  mov     edx, 26Dh
0x14002f328  jmp     short loc_14002F375
0x14002f32a  mov     r8, [r13+80h]; wchar_t *
0x14002f331  lea     rcx, [rsp+2C8h+var_268]; wchar_t *
0x14002f336  mov     r9, rbx; wchar_t *
0x14002f339  mov     edx, 105h; unsigned int
0x14002f33e  call    ?WUPathCchCombine@@YAJPEA_WKPEB_W1@Z; WUPathCchCombine(wchar_t *,ulong,wchar_t const *,wchar_t const *)
0x14002f343  mov     ebp, eax
0x14002f345  test    eax, eax
0x14002f347  jns     short loc_14002F350
0x14002f349  mov     edx, 272h
0x14002f34e  jmp     short loc_14002F375
0x14002f350  mov     edx, [r13+98h]; unsigned int
0x14002f357  lea     rax, [r14+8]
0x14002f35b  lea     rcx, [rsp+2C8h+var_268]; wchar_t *
0x14002f360  mov     [rsp+2C8h+var_288], rax; void **
0x14002f365  call    ?SusCreateFileAndDirectories@@YAJPEB_WKKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEAPEAX@Z; SusCreateFileAndDirectories(wchar_t const *,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,void * *)
0x14002f36a  mov     ebp, eax
0x14002f36c  test    eax, eax
0x14002f36e  jns     short loc_14002F3A2
0x14002f370  mov     edx, 27Ch; void *
0x14002f375  mov     rcx, [rsp+2C8h]; this
0x14002f37d  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x14002f384  mov     r9d, ebp; char *
0x14002f387  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002f38c  test    rbx, rbx
0x14002f38f  jz      loc_14002F4A7
0x14002f395  mov     rcx, rbx; lpMem
0x14002f398  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14002f39d  jmp     loc_14002F4A7
0x14002f3a2  mov     dword ptr [r14+10h], 1
0x14002f3aa  test    rbx, rbx
0x14002f3ad  jz      loc_14002F459
0x14002f3b3  mov     rcx, rbx; lpMem
0x14002f3b6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14002f3bb  jmp     loc_14002F459
0x14002f3c0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002f3c7  mov     ecx, 18h; unsigned __int64
0x14002f3cc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002f3d1  xor     r12d, r12d
0x14002f3d4  mov     rbx, rax
0x14002f3d7  test    rax, rax
0x14002f3da  jz      short loc_14002F400
0x14002f3dc  mov     [rbx+8], r12
0x14002f3e0  lea     rax, ??_7?$CSafeBuffer@E@@6B@; const CSafeBuffer<uchar>::`vftable'
0x14002f3e7  mov     [rbx], rax
0x14002f3ea  mov     [rbx+10h], r12
0x14002f3ee  test    r15d, r15d
0x14002f3f1  jz      short loc_14002F403
0x14002f3f3  mov     edx, r15d
0x14002f3f6  mov     rcx, rbx
0x14002f3f9  call    ?resize@?$CSafeBuffer@E@@QEAAJI@Z; CSafeBuffer<uchar>::resize(uint)
0x14002f3fe  jmp     short loc_14002F403
0x14002f400  mov     rbx, r12
0x14002f403  mov     [rsi+10h], rbx
0x14002f407  test    rbx, rbx
0x14002f40a  jnz     short loc_14002F411
0x14002f40c  lea     edx, [rbx+26h]
0x14002f40f  jmp     short loc_14002F41C
0x14002f411  cmp     [rbx+8], r12
0x14002f415  jnz     short loc_14002F451
0x14002f417  mov     edx, 27h ; '''; void *
0x14002f41c  mov     rcx, [rsp+2C8h]; this
0x14002f424  lea     r8, aCW1SSrcClientL_19; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x14002f42b  mov     r9d, ebp; char *
0x14002f42e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002f433  mov     rcx, [rsp+2C8h]; this
0x14002f43b  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x14002f442  mov     r9d, ebp; char *
0x14002f445  mov     edx, 285h; void *
0x14002f44a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002f44f  jmp     short loc_14002F4A7
0x14002f451  mov     [r14+8], rbx
0x14002f455  mov     [r14+10h], r12d
0x14002f459  mov     rcx, [r13+40h]
0x14002f45d  mov     rdi, r12
0x14002f460  mov     rdx, [rcx+10h]
0x14002f464  mov     [rcx+20h], rdx
0x14002f468  inc     dword ptr [rcx+18h]
0x14002f46b  mov     [rsi], rdx
0x14002f46e  test    rdx, rdx
0x14002f471  jnz     short loc_14002F4EF
0x14002f473  mov     rax, [rcx+8]
0x14002f477  test    rax, rax
0x14002f47a  jz      short loc_14002F47F
0x14002f47c  mov     [rax], rsi
0x14002f47f  mov     rax, [rcx+8]
0x14002f483  mov     [rsi+8], rax
0x14002f487  mov     [rcx+8], rsi
0x14002f48b  cmp     [rcx+10h], r12
0x14002f48f  jnz     short loc_14002F495
0x14002f491  mov     [rcx+10h], rsi
0x14002f495  mov     rax, [rsp+2C8h+var_270]
0x14002f49a  mov     ebp, r12d
0x14002f49d  mov     [rcx+20h], rsi
0x14002f4a1  mov     [rax], r14
0x14002f4a4  mov     r14, r12
0x14002f4a7  mov     rcx, r14; lpMem
0x14002f4aa  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14002f4af  test    rdi, rdi
0x14002f4b2  jz      short loc_14002F4C9
0x14002f4b4  mov     rcx, rdi; this
0x14002f4b7  call    ??1COutputMemoryFile@@QEAA@XZ; COutputMemoryFile::~COutputMemoryFile(void)
0x14002f4bc  mov     edx, 120h; struct std::nothrow_t *
0x14002f4c1  mov     rcx, rdi; void *
0x14002f4c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002f4c9  mov     eax, ebp
0x14002f4cb  mov     rcx, [rsp+2C8h+var_58]
0x14002f4d3  xor     rcx, rsp; StackCookie
0x14002f4d6  call    __security_check_cookie
0x14002f4db  add     rsp, 288h
0x14002f4e2  pop     r15
0x14002f4e4  pop     r14
0x14002f4e6  pop     r13
0x14002f4e8  pop     r12
0x14002f4ea  pop     rdi
0x14002f4eb  pop     rsi
0x14002f4ec  pop     rbp
0x14002f4ed  pop     rbx
0x14002f4ee  retn
0x14002f4ef  mov     rax, [rdx+8]
0x14002f4f3  mov     [rsi+8], rax
0x14002f4f7  mov     [rdx+8], rsi
0x14002f4fb  mov     rax, [rsi+8]
0x14002f4ff  test    rax, rax
0x14002f502  jz      short loc_14002F491
0x14002f504  mov     [rax], rsi
0x14002f507  jmp     short loc_14002F495
```
