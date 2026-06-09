# VpersistDict::VpersistDict(Vstring const &,ushort,char,char)

- ea: `0x180095380`
- end: `0x18009580d`
- name: `??0VpersistDict@@QEAA@AEBVVstring@@GDD@Z`
- size: `1165`
- prototype: `VpersistDict *(VpersistDict *__hidden this, const struct Vstring *, unsigned __int16, char, char)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x1800410b0`
- `0x180042720`
- `0x180047c50`
- `0x180083790`
- `0x1800838f0`
- `0x180090560`
- `0x180095100`
- `0x180095380`
- `0x180096038`
- `0x180103634`
- `0x1801388b0`
- `0x18013bc20`
- `0x18013c010`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800955b6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009563d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800956be`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800956f5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180095790`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800957e4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800955b6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009563d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800956be`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800956f5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180095790`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800957e4`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180095445`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180095507`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180095445`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180095507`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18009570b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18009570b`
- `api-ms-win-crt-filesystem-l1-1-0!_waccess` at `0x1800954e4`
- `api-ms-win-crt-filesystem-l1-1-0!_waccess` at `0x1800954e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=18 #try_helpers=1
VpersistDict *__fastcall VpersistDict::VpersistDict(
        VpersistDict *this,
        const struct Vstring *a2,
        __int16 a3,
        char a4,
        char a5)
{
  char **v9; // r12
  __int64 v10; // rax
  RWFileManager *v11; // rax
  RWFileManager *v12; // rbx
  char v13; // di
  RWFileManager *v14; // rax
  __int64 v15; // rcx
  void *v16; // rax
  __int64 v17; // rcx
  RWFileManager *v18; // rbx
  __int64 v19; // rax
  int *v20; // rcx
  __int64 (__fastcall *v21)(const char *, const char *, unsigned int); // rax
  RWFileManager *v22; // rbx
  char *v23; // rbx
  __int64 v24; // rax
  _QWORD v26[3]; // [rsp+68h] [rbp-F0h] BYREF
  char *v27; // [rsp+80h] [rbp-D8h]
  RWFileManager *v28; // [rsp+88h] [rbp-D0h]
  _BYTE v29[8]; // [rsp+90h] [rbp-C8h] BYREF
  void *v30; // [rsp+98h] [rbp-C0h]
  __int64 v31; // [rsp+A0h] [rbp-B8h]
  void *Block; // [rsp+A8h] [rbp-B0h]
  void *v33; // [rsp+B0h] [rbp-A8h]
  __int64 v34; // [rsp+C0h] [rbp-98h]
  RWFileManager *v35; // [rsp+C8h] [rbp-90h]
  const wchar_t **Unicode; // [rsp+D0h] [rbp-88h]
  const wchar_t *v37; // [rsp+D8h] [rbp-80h]
  __int64 v38; // [rsp+E0h] [rbp-78h]
  void *v39; // [rsp+E8h] [rbp-70h]
  RWFileManager *v40; // [rsp+F0h] [rbp-68h]
  char *v41; // [rsp+F8h] [rbp-60h]
  _QWORD *v42; // [rsp+100h] [rbp-58h]
  __int64 (__fastcall *v43)(const char *, const char *, unsigned int); // [rsp+108h] [rbp-50h]
  RWFileManager *v44; // [rsp+110h] [rbp-48h]
  char *v45; // [rsp+118h] [rbp-40h]
  _QWORD *v46; // [rsp+120h] [rbp-38h]
  int v47; // [rsp+180h] [rbp+28h]

  v34 = -2;
  Vdict::Vdict(this, 1, 0);
  *(_QWORD *)this = &VpersistDict::`vftable';
  *((_BYTE *)this + 64) = a4;
  *((_BYTE *)this + 65) = a5;
  *((_QWORD *)this + 9) = 0;
  *((_WORD *)this + 40) = a3;
  *((_QWORD *)this + 11) = 0;
  v9 = (char **)((char *)this + 96);
  v27 = (char *)this + 96;
  v10 = *(_QWORD *)a2;
  *((_QWORD *)this + 12) = *(_QWORD *)a2;
  _InterlockedIncrement((volatile signed __int32 *)(v10 - 12));
  v27 = (char *)this + 104;
  *((_QWORD *)this + 13) = dword_1802AFD5C;
  _InterlockedIncrement(&dword_1802AFD50);
  *((_QWORD *)this + 14) = 0;
  Vpath::Vpath((Vpath *)v26, a2);
  if ( dword_1802B0018 )
    v11 = (RWFileManager *)COWSAllocator::AllocCurrentHeap(0x20u);
  else
    v11 = (RWFileManager *)malloc(0x20u);
  v12 = v11;
  v35 = v11;
  if ( v11 )
  {
    Unicode = (const wchar_t **)Vstring::getUnicode((char *)this + 96, v29);
    v13 = 1;
    v37 = *Unicode;
    v14 = RWFileManager::RWFileManager(v12, v37, 0);
  }
  else
  {
    v14 = 0;
    v13 = 0;
  }
  v28 = v14;
  *((_QWORD *)this + 9) = v14;
  if ( (v13 & 1) != 0 )
    Vwstring::~Vwstring((Vwstring *)v29);
  v15 = *((_QWORD *)this + 9);
  if ( *(_QWORD *)(v15 + 8) && (v38 = *((_QWORD *)this + 9), waccess(*(const wchar_t **)v15, 0) >= 0) )
  {
    if ( dword_1802B0018 )
      v16 = COWSAllocator::AllocCurrentHeap(0x80u);
    else
      v16 = malloc(0x80u);
    v30 = v16;
    v39 = v16;
    if ( v16 )
    {
      v17 = RWBTreeOnDisk::RWBTreeOnDisk(
              v16,
              *((_QWORD *)this + 9),
              10,
              0,
              *((unsigned __int16 *)this + 40),
              0,
              -1,
              0,
              10,
              10,
              *((char *)this + 65));
      v31 = v17;
    }
    else
    {
      v17 = 0;
      v31 = 0;
    }
    *((_QWORD *)this + 11) = v17;
    if ( v17 )
    {
      v21 = Vstrnicmp;
      if ( *((_BYTE *)this + 64) )
        v21 = Vstrncmp;
      v43 = v21;
      *(_QWORD *)(v17 + 24) = v21;
      Vpath::ClearStat((Vpath *)v26);
      v27 = (char *)v26;
      v20 = (int *)(v26[0] - 12LL);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26[0] - 12LL), 0xFFFFFFFF) == 1
        && v20 != &dword_1802AFD50 )
      {
        if ( !dword_1802B0018 )
        {
          free(v20);
          return this;
        }
        goto LABEL_39;
      }
    }
    else
    {
      v18 = (RWFileManager *)*((_QWORD *)this + 9);
      v40 = v18;
      if ( v18 )
      {
        RWFileManager::~RWFileManager(v18);
        if ( dword_1802B0018 )
          COWSAllocator::Free(v18);
        else
          free(v18);
      }
      *((_QWORD *)this + 9) = 0;
      v41 = *v9;
      v19 = sub_180047C50(0x20005u, 0, v41);
      sub_180096038(this, v19);
      Vpath::ClearStat((Vpath *)v26);
      v42 = v26;
      Block = (void *)(v26[0] - 12LL);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26[0] - 12LL), 0xFFFFFFFF) == 1 )
      {
        v20 = (int *)Block;
        if ( Block != &dword_1802AFD50 )
        {
          if ( !dword_1802B0018 )
          {
            free(Block);
            return this;
          }
LABEL_39:
          COWSAllocator::Free(v20);
        }
      }
    }
  }
  else
  {
    v22 = (RWFileManager *)*((_QWORD *)this + 9);
    v44 = v22;
    if ( v22 )
    {
      RWFileManager::~RWFileManager(v22);
      if ( dword_1802B0018 )
        COWSAllocator::Free(v22);
      else
        free(v22);
    }
    *((_QWORD *)this + 9) = 0;
    v45 = *v9;
    v23 = v45;
    v47 = *errno();
    v24 = sub_180047C50(0x20005u, v47 | 0x20000000u, v23);
    sub_180096038(this, v24);
    Vpath::ClearStat((Vpath *)v26);
    v46 = v26;
    v33 = (void *)(v26[0] - 12LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26[0] - 12LL), 0xFFFFFFFF) == 1 )
    {
      v20 = (int *)v33;
      if ( v33 != &dword_1802AFD50 )
      {
        if ( !dword_1802B0018 )
        {
          free(v33);
          return this;
        }
        goto LABEL_39;
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180095380  mov     rax, rsp
0x180095383  mov     [rax+8], rcx
0x180095387  push    rsi
0x180095388  push    rdi
0x180095389  push    r12
0x18009538b  push    r14
0x18009538d  push    r15
0x18009538f  sub     rsp, 130h
0x180095396  mov     qword ptr [rax-98h], 0FFFFFFFFFFFFFFFEh
0x1800953a1  mov     [rax+18h], rbx
0x1800953a5  mov     bl, r9b
0x1800953a8  movzx   edi, r8w
0x1800953ac  mov     rsi, rdx
0x1800953af  mov     r15, rcx
0x1800953b2  xor     r14d, r14d
0x1800953b5  mov     [rsp+158h+var_F8], r14d
0x1800953ba  xor     r8d, r8d; char
0x1800953bd  mov     dl, 1; char
0x1800953bf  call    ??0Vdict@@QEAA@DD@Z; Vdict::Vdict(char,char)
0x1800953c4  nop
0x1800953c5  lea     rax, ??_7VpersistDict@@6B@; const VpersistDict::`vftable'
0x1800953cc  mov     [r15], rax
0x1800953cf  mov     [r15+40h], bl
0x1800953d3  mov     al, [rsp+158h+arg_20]
0x1800953da  mov     [r15+41h], al
0x1800953de  mov     [r15+48h], r14
0x1800953e2  mov     [r15+50h], di
0x1800953e7  mov     [r15+58h], r14
0x1800953eb  lea     r12, [r15+60h]
0x1800953ef  mov     [rsp+158h+var_D8], r12
0x1800953f7  mov     rax, [rsi]
0x1800953fa  mov     [r12], rax
0x1800953fe  lock inc dword ptr [rax-0Ch]
0x180095402  lea     rax, [r15+68h]
0x180095406  mov     [rsp+158h+var_D8], rax
0x18009540e  lea     rcx, dword_1802AFD5C
0x180095415  mov     [rax], rcx
0x180095418  lock inc cs:dword_1802AFD50
0x18009541f  mov     [r15+70h], r14
0x180095423  mov     rdx, rsi; struct Vstring *
0x180095426  lea     rcx, [rsp+158h+var_F0]; this
0x18009542b  call    ??0Vpath@@QEAA@AEBVVstring@@@Z; Vpath::Vpath(Vstring const &)
0x180095430  nop
0x180095431  lea     ecx, [r14+20h]; unsigned __int64
0x180095435  cmp     cs:dword_1802B0018, r14d
0x18009543c  jz      short loc_180095445
0x18009543e  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180095443  jmp     short loc_18009544B
0x180095445  call    cs:malloc
0x18009544b  mov     [rsp+158h+arg_8], rax
0x180095453  mov     rbx, rax
0x180095456  mov     [rsp+158h+var_90], rax
0x18009545e  test    rax, rax
0x180095461  jz      short loc_18009549C
0x180095463  lea     rdx, [rsp+158h+var_C8]
0x18009546b  mov     rcx, r12
0x18009546e  call    ?getUnicode@Vstring@@QEBA?AVVwstring@@XZ; Vstring::getUnicode(void)
0x180095473  mov     [rsp+158h+var_88], rax
0x18009547b  mov     edi, 1
0x180095480  mov     [rsp+158h+var_F8], edi
0x180095484  mov     rdx, [rax]; wchar_t *
0x180095487  mov     [rsp+158h+var_80], rdx
0x18009548f  xor     r8d, r8d; wchar_t *
0x180095492  mov     rcx, rbx; this
0x180095495  call    ??0RWFileManager@@QEAA@PEB_W0@Z; RWFileManager::RWFileManager(wchar_t const *,wchar_t const *)
0x18009549a  jmp     short loc_1800954A3
0x18009549c  mov     rax, r14
0x18009549f  mov     edi, [rsp+158h+var_F8]
0x1800954a3  mov     [rsp+158h+var_D0], rax
0x1800954ab  mov     [r15+48h], rax
0x1800954af  test    dil, 1
0x1800954b3  jz      short loc_1800954C9
0x1800954b5  and     edi, 0FFFFFFFEh
0x1800954b8  mov     [rsp+158h+var_F8], edi
0x1800954bc  lea     rcx, [rsp+158h+var_C8]; this
0x1800954c4  call    ??1Vwstring@@QEAA@XZ_0; Vwstring::~Vwstring(void)
0x1800954c9  mov     rcx, [r15+48h]
0x1800954cd  cmp     [rcx+8], r14
0x1800954d1  jz      loc_1800956C9
0x1800954d7  mov     [rsp+158h+var_78], rcx
0x1800954df  xor     edx, edx; AccessMode
0x1800954e1  mov     rcx, [rcx]; FileName
0x1800954e4  call    cs:_waccess
0x1800954ea  test    eax, eax
0x1800954ec  js      loc_1800956C9
0x1800954f2  mov     ecx, 80h; unsigned __int64
0x1800954f7  cmp     cs:dword_1802B0018, r14d
0x1800954fe  jz      short loc_180095507
0x180095500  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180095505  jmp     short loc_18009550D
0x180095507  call    cs:malloc
0x18009550d  mov     [rsp+158h+var_C0], rax
0x180095515  mov     r10, rax
0x180095518  mov     [rsp+158h+var_70], rax
0x180095520  test    rax, rax
0x180095523  jz      short loc_180095572
0x180095525  movsx   eax, byte ptr [r15+41h]
0x18009552a  movzx   ecx, word ptr [r15+50h]
0x18009552f  mov     [rsp+158h+var_108], eax
0x180095533  mov     r8d, 0Ah
0x180095539  mov     [rsp+158h+var_110], r8d
0x18009553e  mov     [rsp+158h+var_118], r8d
0x180095543  mov     [rsp+158h+var_120], r14d
0x180095548  or      [rsp+158h+var_128], 0FFFFFFFFh
0x18009554d  mov     [rsp+158h+var_130], r14d
0x180095552  mov     [rsp+158h+var_138], ecx
0x180095556  xor     r9d, r9d
0x180095559  mov     rdx, [r15+48h]
0x18009555d  mov     rcx, r10
0x180095560  call    ??0RWBTreeOnDisk@@QEAA@AEAVRWFileManager@@IW4createMode@0@IHJW4styleMode@0@IIH@Z; RWBTreeOnDisk::RWBTreeOnDisk(RWFileManager &,uint,RWBTreeOnDisk::createMode,uint,int,long,RWBTreeOnDisk::styleMode,uint,uint,int)
0x180095565  mov     rcx, rax
0x180095568  mov     [rsp+158h+var_B8], rax
0x180095570  jmp     short loc_18009557D
0x180095572  mov     rcx, r14
0x180095575  mov     [rsp+158h+var_B8], rcx
0x18009557d  mov     [r15+58h], rcx
0x180095581  test    rcx, rcx
0x180095584  jnz     loc_180095648
0x18009558a  mov     rbx, [r15+48h]
0x18009558e  mov     [rsp+158h+var_68], rbx
0x180095596  test    rbx, rbx
0x180095599  jz      short loc_1800955BC
0x18009559b  mov     rcx, rbx; this
0x18009559e  call    ??1RWFileManager@@QEAA@XZ; RWFileManager::~RWFileManager(void)
0x1800955a3  mov     rcx, rbx; void *
0x1800955a6  cmp     cs:dword_1802B0018, r14d
0x1800955ad  jz      short loc_1800955B6
0x1800955af  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800955b4  jmp     short loc_1800955BC
0x1800955b6  call    cs:free
0x1800955bc  mov     [r15+48h], r14
0x1800955c0  mov     r8, [r12]
0x1800955c4  mov     [rsp+158h+var_60], r8
0x1800955cc  xor     edx, edx
0x1800955ce  mov     ecx, 20005h
0x1800955d3  call    sub_180047C50
0x1800955d8  mov     rdx, rax
0x1800955db  mov     rcx, r15
0x1800955de  call    sub_180096038
0x1800955e3  nop
0x1800955e4  lea     rcx, [rsp+158h+var_F0]; this
0x1800955e9  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x1800955ee  nop
0x1800955ef  lea     rax, [rsp+158h+var_F0]
0x1800955f4  mov     [rsp+158h+var_58], rax
0x1800955fc  mov     rcx, [rsp+158h+var_F0]
0x180095601  add     rcx, 0FFFFFFFFFFFFFFF4h
0x180095605  mov     [rsp+158h+Block], rcx
0x18009560d  or      eax, 0FFFFFFFFh
0x180095610  lock xadd [rcx], eax
0x180095614  cmp     eax, 1
0x180095617  jnz     short loc_180095643
0x180095619  lea     rax, dword_1802AFD50
0x180095620  mov     rcx, [rsp+158h+Block]; void *
0x180095628  cmp     rcx, rax
0x18009562b  jz      short loc_180095643
0x18009562d  cmp     cs:dword_1802B0018, r14d
0x180095634  jz      short loc_18009563D
0x180095636  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18009563b  jmp     short loc_180095643
0x18009563d  call    cs:free
0x180095643  jmp     loc_1800957F2
0x180095648  lea     rax, ?Vstrnicmp@@YAJPEBD0I@Z; Vstrnicmp(char const *,char const *,uint)
0x18009564f  lea     rdx, ?Vstrncmp@@YAJPEBD0I@Z; Vstrncmp(char const *,char const *,uint)
0x180095656  cmp     [r15+40h], r14b
0x18009565a  cmovnz  rax, rdx
0x18009565e  mov     [rsp+158h+var_50], rax
0x180095666  mov     [rcx+18h], rax
0x18009566a  lea     rcx, [rsp+158h+var_F0]; this
0x18009566f  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x180095674  nop
0x180095675  lea     rax, [rsp+158h+var_F0]
0x18009567a  mov     [rsp+158h+var_D8], rax
0x180095682  mov     rcx, [rsp+158h+var_F0]
0x180095687  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18009568b  or      eax, 0FFFFFFFFh
0x18009568e  lock xadd [rcx], eax
0x180095692  cmp     eax, 1
0x180095695  jnz     loc_1800957F2
0x18009569b  lea     rax, dword_1802AFD50
0x1800956a2  cmp     rcx, rax
0x1800956a5  jz      loc_1800957F2
0x1800956ab  cmp     cs:dword_1802B0018, r14d
0x1800956b2  jz      short loc_1800956BE
0x1800956b4  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800956b9  jmp     loc_1800957F2
0x1800956be  call    cs:free
0x1800956c4  jmp     loc_1800957F2
0x1800956c9  mov     rbx, [r15+48h]
0x1800956cd  mov     [rsp+158h+var_48], rbx
0x1800956d5  test    rbx, rbx
0x1800956d8  jz      short loc_1800956FB
0x1800956da  mov     rcx, rbx; this
0x1800956dd  call    ??1RWFileManager@@QEAA@XZ; RWFileManager::~RWFileManager(void)
0x1800956e2  mov     rcx, rbx; void *
0x1800956e5  cmp     cs:dword_1802B0018, r14d
0x1800956ec  jz      short loc_1800956F5
0x1800956ee  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800956f3  jmp     short loc_1800956FB
0x1800956f5  call    cs:free
0x1800956fb  mov     [r15+48h], r14
0x1800956ff  mov     rbx, [r12]
0x180095703  mov     [rsp+158h+var_40], rbx
0x18009570b  call    cs:_errno
0x180095711  mov     edx, [rax]
0x180095713  mov     dword ptr [rsp+158h+arg_20], edx
0x18009571a  bts     edx, 1Dh
0x18009571e  mov     r8, rbx
0x180095721  mov     ecx, 20005h
0x180095726  call    sub_180047C50
0x18009572b  mov     rdx, rax
0x18009572e  mov     rcx, r15
0x180095731  call    sub_180096038
0x180095736  nop
0x180095737  lea     rcx, [rsp+158h+var_F0]; this
0x18009573c  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x180095741  nop
0x180095742  lea     rax, [rsp+158h+var_F0]
0x180095747  mov     [rsp+158h+var_38], rax
0x18009574f  mov     rcx, [rsp+158h+var_F0]
0x180095754  add     rcx, 0FFFFFFFFFFFFFFF4h
0x180095758  mov     [rsp+158h+var_A8], rcx
0x180095760  or      eax, 0FFFFFFFFh
0x180095763  lock xadd [rcx], eax
0x180095767  cmp     eax, 1
0x18009576a  jnz     short loc_180095796
0x18009576c  lea     rax, dword_1802AFD50
0x180095773  mov     rcx, [rsp+158h+var_A8]; void *
0x18009577b  cmp     rcx, rax
0x18009577e  jz      short loc_180095796
0x180095780  cmp     cs:dword_1802B0018, r14d
0x180095787  jz      short loc_180095790
0x180095789  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18009578e  jmp     short loc_180095796
0x180095790  call    cs:free
0x180095796  jmp     short loc_1800957F2
0x180095798  lea     rcx, [rsp+158h+var_F0]; this
0x18009579d  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x1800957a2  nop
0x1800957a3  lea     rax, [rsp+158h+var_F0]
0x1800957a8  mov     [rsp+158h+var_D8], rax
0x1800957b0  mov     rcx, [rsp+158h+var_F0]
0x1800957b5  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800957b9  or      eax, 0FFFFFFFFh
0x1800957bc  lock xadd [rcx], eax
0x1800957c0  cmp     eax, 1
0x1800957c3  jnz     short loc_1800957EA
0x1800957c5  lea     rax, dword_1802AFD50
0x1800957cc  cmp     rcx, rax
0x1800957cf  jz      short loc_1800957EA
0x1800957d1  xor     r14d, r14d
0x1800957d4  cmp     cs:dword_1802B0018, r14d
0x1800957db  jz      short loc_1800957E4
0x1800957dd  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800957e2  jmp     short loc_1800957EA
0x1800957e4  call    cs:free
0x1800957ea  mov     r15, [rsp+158h+arg_0]
0x1800957f2  mov     rax, r15
0x1800957f5  mov     rbx, [rsp+158h+arg_10]
0x1800957fd  add     rsp, 130h
0x180095804  pop     r15
0x180095806  pop     r14
0x180095808  pop     r12
0x18009580a  pop     rdi
0x18009580b  pop     rsi
0x18009580c  retn
```
