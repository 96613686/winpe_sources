# CManagedAppProcessor::EnumerateApps(IEnumPackage *)

- ea: `0x18000f024`
- end: `0x18000f3f5`
- name: `?EnumerateApps@CManagedAppProcessor@@AEAAJPEAUIEnumPackage@@@Z`
- size: `977`
- prototype: `__int64 __fastcall(LPCWSTR **this, struct IEnumPackage *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f634`

## callees

- `0x1800016d0`
- `0x1800016f4`
- `0x180002024`
- `0x180004e30`
- `0x180004fc0`
- `0x18000a2cc`
- `0x18000f024`
- `0x18001b1a0`
- `0x18001c0e0`
- `0x18002ad30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f12c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f12c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000f253`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000f253`
- `KERNEL32!lstrcmpiW` at `0x18000f236`
- `KERNEL32!lstrcmpiW` at `0x18000f236`

## pseudocode

```c
__int64 __fastcall CManagedAppProcessor::EnumerateApps(LPCWSTR **this, struct IEnumPackage *a2)
{
  int v4; // r12d
  unsigned int v5; // r15d
  int v6; // edi
  int v7; // esi
  CAppInfo *v8; // rax
  CAppInfo *v9; // rbx
  int v10; // edi
  unsigned int i; // ebx
  LPCWSTR *j; // rsi
  __int64 v13; // r12
  unsigned int v14; // r15d
  WCHAR *v15; // rbx
  __int64 *k; // rdi
  int v17; // eax
  unsigned int v18; // ecx
  unsigned int v20; // [rsp+30h] [rbp-D0h] BYREF
  int v21[3]; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v23; // [rsp+50h] [rbp-B0h]
  __int128 v24; // [rsp+60h] [rbp-A0h]
  __int64 v25; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v26; // [rsp+78h] [rbp-88h]
  __int128 v27; // [rsp+80h] [rbp-80h]
  CManagedAppProcessor *v28; // [rsp+90h] [rbp-70h]
  __int64 v29; // [rsp+98h] [rbp-68h]
  int v30; // [rsp+A0h] [rbp-60h]
  int v31; // [rsp+A4h] [rbp-5Ch]
  CAppInfo *v32; // [rsp+B0h] [rbp-50h]
  _BYTE v33[4160]; // [rsp+C0h] [rbp-40h] BYREF

  v20 = 0;
  v27 = 0;
  v26 = &v25;
  v25 = (__int64)&v25;
  v22[1] = 0;
  v23 = 0;
  v24 = 0;
  v22[0] = &CAppList::`vftable';
  v28 = (CManagedAppProcessor *)this;
  v29 = 0;
  v30 = -2147467259;
  v31 = 0;
  memset_0(v33, 0, sizeof(v33));
  do
  {
    v4 = (*(__int64 (__fastcall **)(struct IEnumPackage *, __int64, _BYTE *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
           a2,
           20,
           v33,
           &v20);
    if ( v4 < 0 )
    {
      CAppList::~CAppList((CAppList *)v22);
      return (unsigned int)v4;
    }
    v5 = v20;
    v6 = 0;
    if ( !v20 )
    {
LABEL_14:
      v10 = 1;
      goto LABEL_15;
    }
    while ( 1 )
    {
      if ( *(_DWORD *)&v33[208 * v6 + 12] != 5 && (*(_DWORD *)&v33[208 * v6 + 12] != 6 || !*((_DWORD *)this + 81)) )
        goto LABEL_13;
      v7 = 0;
      v21[0] = 0;
      v8 = (CAppInfo *)LocalAlloc(0, 0x1C8u);
      v32 = v8;
      if ( v8 )
      {
        v9 = CAppInfo::CAppInfo(
               v8,
               (struct CManagedAppProcessor *)this,
               (struct tagPACKAGEDISPINFO *)&v33[208 * v6],
               0,
               v21);
        v7 = v21[0];
      }
      else
      {
        v9 = 0;
      }
      if ( !v9 )
        goto LABEL_34;
      if ( !v7 )
        break;
      *((_QWORD *)v9 + 1) = v26;
      *(_QWORD *)v9 = &v25;
      *v26 = (__int64)v9;
      v26 = (__int64 *)v9;
LABEL_13:
      if ( ++v6 >= v5 )
        goto LABEL_14;
    }
    CAppInfo::~CAppInfo(v9);
    operator delete(v9);
LABEL_34:
    v10 = 0;
LABEL_15:
    for ( i = 0; i < v20; ++i )
      ReleasePackageInfo(&v33[208 * i]);
    if ( !v10 )
    {
      CAppList::~CAppList((CAppList *)v22);
      return 2147942414LL;
    }
  }
  while ( v4 != 1 );
  this[3] = this[2];
  for ( j = this[1]; ; j = (LPCWSTR *)this[2][1] )
  {
    this[2] = j;
    if ( j == (LPCWSTR *)this )
      j = 0;
    if ( !j )
      break;
    v13 = 0;
    v14 = 0;
    while ( 1 )
    {
      v15 = 0;
      *((_QWORD *)&v27 + 1) = v27;
      for ( k = v26; ; k = *(__int64 **)(v27 + 8) )
      {
        *(_QWORD *)&v27 = k;
        if ( k == &v25 )
          k = 0;
        if ( !k || lstrcmpiW(j[2], (LPCWSTR)k[6]) )
          break;
        if ( !v15 || CompareFileTime((const FILETIME *)((char *)k + 172), (const FILETIME *)(v15 + 86)) < 0 )
          v15 = (WCHAR *)k;
      }
      *(_QWORD *)&v27 = *((_QWORD *)&v27 + 1);
      if ( !v15 )
        break;
      v17 = *(_DWORD *)&gDebugLevel;
      if ( !v14 )
      {
        v13 = *((_QWORD *)v15 + 9);
        if ( *(_DWORD *)&gDebugLevel )
        {
          _DebugMsg(4, 0xC03u, *((_QWORD *)v15 + 9));
          v17 = *(_DWORD *)&gDebugLevel;
        }
      }
      ++v14;
      if ( (v17 & 2) != 0 )
      {
        v18 = *((_DWORD *)v15 + 53);
        if ( (v18 & 0x400) != 0 )
        {
          if ( v17 )
            _DebugMsg(4, 0xBBBu, *((_QWORD *)v15 + 5), v18);
        }
        else if ( (v18 & 8) != 0 )
        {
          if ( v17 )
            _DebugMsg(4, 0xBBCu, *((_QWORD *)v15 + 5), v18);
        }
        else if ( (v18 & 0x80u) == 0 )
        {
          if ( (v18 & 0x100) != 0 )
          {
            if ( v17 )
              _DebugMsg(4, 0xBC6u, *((_QWORD *)v15 + 5));
          }
          else if ( v17 )
          {
            _DebugMsg(4, 0xBD4u, *((_QWORD *)v15 + 5));
          }
        }
        else if ( v17 )
        {
          _DebugMsg(4, 0xBC0u, *((_QWORD *)v15 + 5));
        }
      }
      *(_QWORD *)(*(_QWORD *)v15 + 8LL) = *((_QWORD *)v15 + 1);
      **((_QWORD **)v15 + 1) = *(_QWORD *)v15;
      *((_QWORD *)v15 + 1) = this + 10;
      *(_QWORD *)v15 = this[10];
      this[10][1] = v15;
      this[10] = (LPCWSTR *)v15;
    }
    if ( v14 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xBC5u, v14, v13);
  }
  this[2] = this[3];
  CAppList::~CAppList((CAppList *)v22);
  return 0;
}

```

## disassembly

```asm
0x18000f024  mov     [rsp-8+arg_10], rbx
0x18000f029  push    rbp
0x18000f02a  push    rsi
0x18000f02b  push    rdi
0x18000f02c  push    r12
0x18000f02e  push    r13
0x18000f030  push    r14
0x18000f032  push    r15
0x18000f034  lea     rbp, [rsp-1010h]
0x18000f03c  mov     eax, 1110h
0x18000f041  call    _alloca_probe
0x18000f046  sub     rsp, rax
0x18000f049  mov     rax, cs:__security_cookie
0x18000f050  xor     rax, rsp
0x18000f053  mov     [rbp+1040h+var_40], rax
0x18000f05a  mov     r13, rdx
0x18000f05d  mov     r14, rcx
0x18000f060  xor     ecx, ecx
0x18000f062  mov     [rsp+1140h+var_1110], ecx
0x18000f066  xorps   xmm0, xmm0
0x18000f069  movdqa  [rbp+1040h+var_10C0], xmm0
0x18000f06e  lea     rax, [rsp+1140h+var_10D0]
0x18000f073  mov     [rsp+1140h+var_10C8], rax
0x18000f078  lea     rax, [rsp+1140h+var_10D0]
0x18000f07d  mov     [rsp+1140h+var_10D0], rax
0x18000f082  mov     [rsp+1140h+var_10F8], rcx
0x18000f087  movdqa  [rsp+1140h+var_10F0], xmm0
0x18000f08d  xorps   xmm1, xmm1
0x18000f090  movdqa  [rsp+1140h+var_10E0], xmm1
0x18000f096  lea     rax, ??_7CAppList@@6B@; const CAppList::`vftable'
0x18000f09d  mov     [rsp+1140h+var_1100], rax
0x18000f0a2  mov     [rbp+1040h+var_10B0], r14
0x18000f0a6  mov     [rbp+1040h+var_10A8], rcx
0x18000f0aa  mov     [rbp+1040h+var_10A0], 80004005h
0x18000f0b1  mov     [rbp+1040h+var_109C], ecx
0x18000f0b4  xor     edx, edx; Val
0x18000f0b6  mov     r8d, 1040h; Size
0x18000f0bc  lea     rcx, [rbp+1040h+var_1080]; void *
0x18000f0c0  call    memset_0
0x18000f0c5  mov     rax, [r13+0]
0x18000f0c9  lea     r9, [rsp+1140h+var_1110]
0x18000f0ce  lea     r8, [rbp+1040h+var_1080]
0x18000f0d2  mov     edx, 14h
0x18000f0d7  mov     rcx, r13
0x18000f0da  mov     rax, [rax+18h]
0x18000f0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0e3  mov     r12d, eax
0x18000f0e6  test    eax, eax
0x18000f0e8  js      loc_18000F3BE
0x18000f0ee  mov     r15d, [rsp+1140h+var_1110]
0x18000f0f3  xor     edi, edi
0x18000f0f5  test    r15d, r15d
0x18000f0f8  jz      loc_18000F19F
0x18000f0fe  mov     ecx, edi
0x18000f100  imul    rbx, rcx, 0D0h
0x18000f107  mov     edx, [rbp+rbx+1040h+var_1074]
0x18000f10b  sub     edx, 5
0x18000f10e  jz      short loc_18000F11F
0x18000f110  cmp     edx, 1
0x18000f113  jnz     short loc_18000F194
0x18000f115  cmp     dword ptr [r14+144h], 0
0x18000f11d  jz      short loc_18000F194
0x18000f11f  xor     esi, esi
0x18000f121  mov     [rsp+1140h+var_110C], esi
0x18000f125  mov     edx, 1C8h; uBytes
0x18000f12a  xor     ecx, ecx; uFlags
0x18000f12c  call    cs:__imp_LocalAlloc
0x18000f132  mov     [rbp+1040h+var_1090], rax
0x18000f136  test    rax, rax
0x18000f139  jz      short loc_18000F163
0x18000f13b  lea     r8, [rbp+1040h+var_1080]
0x18000f13f  add     r8, rbx; struct tagPACKAGEDISPINFO *
0x18000f142  lea     rcx, [rsp+1140h+var_110C]
0x18000f147  mov     [rsp+1140h+var_1120], rcx; int *
0x18000f14c  xor     r9d, r9d; int
0x18000f14f  mov     rdx, r14; struct CManagedAppProcessor *
0x18000f152  mov     rcx, rax; this
0x18000f155  call    ??0CAppInfo@@QEAA@PEAVCManagedAppProcessor@@PEAUtagPACKAGEDISPINFO@@HAEAH@Z; CAppInfo::CAppInfo(CManagedAppProcessor *,tagPACKAGEDISPINFO *,int,int &)
0x18000f15a  mov     rbx, rax
0x18000f15d  mov     esi, [rsp+1140h+var_110C]
0x18000f161  jmp     short loc_18000F165
0x18000f163  xor     ebx, ebx
0x18000f165  test    rbx, rbx
0x18000f168  jz      loc_18000F284
0x18000f16e  test    esi, esi
0x18000f170  jz      loc_18000F26F
0x18000f176  mov     rax, [rsp+1140h+var_10C8]
0x18000f17b  mov     [rbx+8], rax
0x18000f17f  lea     rax, [rsp+1140h+var_10D0]
0x18000f184  mov     [rbx], rax
0x18000f187  mov     rax, [rsp+1140h+var_10C8]
0x18000f18c  mov     [rax], rbx
0x18000f18f  mov     [rsp+1140h+var_10C8], rbx
0x18000f194  inc     edi
0x18000f196  cmp     edi, r15d
0x18000f199  jb      loc_18000F0FE
0x18000f19f  mov     edi, 1
0x18000f1a4  xor     ebx, ebx
0x18000f1a6  cmp     [rsp+1140h+var_1110], ebx
0x18000f1aa  jbe     short loc_18000F1C9
0x18000f1ac  mov     eax, ebx
0x18000f1ae  imul    rcx, rax, 0D0h
0x18000f1b5  lea     rax, [rbp+1040h+var_1080]
0x18000f1b9  add     rcx, rax; void *
0x18000f1bc  call    ReleasePackageInfo
0x18000f1c1  inc     ebx
0x18000f1c3  cmp     ebx, [rsp+1140h+var_1110]
0x18000f1c7  jb      short loc_18000F1AC
0x18000f1c9  test    edi, edi
0x18000f1cb  jz      loc_18000F3AD
0x18000f1d1  cmp     r12d, 1
0x18000f1d5  jnz     loc_18000F0C5
0x18000f1db  mov     rax, [r14+10h]
0x18000f1df  mov     [r14+18h], rax
0x18000f1e3  mov     rsi, [r14+8]
0x18000f1e7  lea     r13d, [r12+3]
0x18000f1ec  mov     [r14+10h], rsi
0x18000f1f0  xor     eax, eax
0x18000f1f2  cmp     rsi, r14
0x18000f1f5  cmovz   rsi, rax
0x18000f1f9  test    rsi, rsi
0x18000f1fc  jz      loc_18000F397
0x18000f202  xor     r12d, r12d
0x18000f205  xor     r15d, r15d
0x18000f208  xor     ebx, ebx
0x18000f20a  mov     rax, qword ptr [rbp+1040h+var_10C0]
0x18000f20e  mov     qword ptr [rbp+1040h+var_10C0+8], rax
0x18000f212  mov     rdi, [rsp+1140h+var_10C8]
0x18000f217  mov     qword ptr [rbp+1040h+var_10C0], rdi
0x18000f21b  xor     eax, eax
0x18000f21d  lea     rcx, [rsp+1140h+var_10D0]
0x18000f222  cmp     rdi, rcx
0x18000f225  cmovz   rdi, rax
0x18000f229  test    rdi, rdi
0x18000f22c  jz      short loc_18000F28B
0x18000f22e  mov     rdx, [rdi+30h]; lpString2
0x18000f232  mov     rcx, [rsi+10h]; lpString1
0x18000f236  call    cs:__imp_lstrcmpiW
0x18000f23c  test    eax, eax
0x18000f23e  jnz     short loc_18000F28B
0x18000f240  test    rbx, rbx
0x18000f243  jz      short loc_18000F25D
0x18000f245  lea     rdx, [rbx+0ACh]; lpFileTime2
0x18000f24c  lea     rcx, [rdi+0ACh]; lpFileTime1
0x18000f253  call    cs:__imp_CompareFileTime
0x18000f259  test    eax, eax
0x18000f25b  jns     short loc_18000F260
0x18000f25d  mov     rbx, rdi
0x18000f260  mov     rax, qword ptr [rbp+1040h+var_10C0]
0x18000f264  mov     rdi, [rax+8]
0x18000f268  lea     rax, [rsp+1140h+var_10D0]
0x18000f26d  jmp     short loc_18000F217
0x18000f26f  mov     rcx, rbx; this
0x18000f272  call    ??1CAppInfo@@QEAA@XZ; CAppInfo::~CAppInfo(void)
0x18000f277  mov     edx, 1C8h; unsigned __int64
0x18000f27c  mov     rcx, rbx; void *
0x18000f27f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f284  xor     edi, edi
0x18000f286  jmp     loc_18000F1A4
0x18000f28b  mov     rax, qword ptr [rbp+1040h+var_10C0+8]
0x18000f28f  mov     qword ptr [rbp+1040h+var_10C0], rax
0x18000f293  test    rbx, rbx
0x18000f296  jz      loc_18000F369
0x18000f29c  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x18000f2a2  test    r15d, r15d
0x18000f2a5  jnz     short loc_18000F2C5
0x18000f2a7  mov     r12, [rbx+48h]
0x18000f2ab  test    eax, eax
0x18000f2ad  jz      short loc_18000F2C5
0x18000f2af  mov     r8, r12
0x18000f2b2  mov     edx, 0C03h; unsigned int
0x18000f2b7  mov     ecx, r13d; unsigned int
0x18000f2ba  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000f2bf  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x18000f2c5  inc     r15d
0x18000f2c8  test    al, 2
0x18000f2ca  jz      short loc_18000F337
0x18000f2cc  mov     ecx, [rbx+0D4h]
0x18000f2d2  bt      ecx, 0Ah
0x18000f2d6  jnb     short loc_18000F2E3
0x18000f2d8  test    eax, eax
0x18000f2da  jz      short loc_18000F337
0x18000f2dc  mov     edx, 0BBBh
0x18000f2e1  jmp     short loc_18000F2F1
0x18000f2e3  test    cl, 8
0x18000f2e6  jz      short loc_18000F302
0x18000f2e8  test    eax, eax
0x18000f2ea  jz      short loc_18000F337
0x18000f2ec  mov     edx, 0BBCh; unsigned int
0x18000f2f1  mov     r8, [rbx+28h]
0x18000f2f5  mov     r9d, ecx
0x18000f2f8  mov     ecx, r13d; unsigned int
0x18000f2fb  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000f300  jmp     short loc_18000F337
0x18000f302  test    cl, cl
0x18000f304  jns     short loc_18000F311
0x18000f306  test    eax, eax
0x18000f308  jz      short loc_18000F337
0x18000f30a  mov     edx, 0BC0h
0x18000f30f  jmp     short loc_18000F32B
0x18000f311  bt      ecx, 8
0x18000f315  jnb     short loc_18000F322
0x18000f317  test    eax, eax
0x18000f319  jz      short loc_18000F337
0x18000f31b  mov     edx, 0BC6h
0x18000f320  jmp     short loc_18000F32B
0x18000f322  test    eax, eax
0x18000f324  jz      short loc_18000F337
0x18000f326  mov     edx, 0BD4h; unsigned int
0x18000f32b  mov     r8, [rbx+28h]
0x18000f32f  mov     ecx, r13d; unsigned int
0x18000f332  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000f337  mov     rcx, [rbx]
0x18000f33a  mov     rax, [rbx+8]
0x18000f33e  mov     [rcx+8], rax
0x18000f342  mov     rcx, [rbx+8]
0x18000f346  mov     rax, [rbx]
0x18000f349  mov     [rcx], rax
0x18000f34c  lea     rcx, [r14+50h]
0x18000f350  mov     [rbx+8], rcx
0x18000f354  mov     rax, [rcx]
0x18000f357  mov     [rbx], rax
0x18000f35a  mov     rax, [rcx]
0x18000f35d  mov     [rax+8], rbx
0x18000f361  mov     [rcx], rbx
0x18000f364  jmp     loc_18000F208
0x18000f369  test    r15d, r15d
0x18000f36c  jz      short loc_18000F38A
0x18000f36e  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000f375  jz      short loc_18000F38A
0x18000f377  mov     r9, r12
0x18000f37a  mov     r8d, r15d
0x18000f37d  mov     edx, 0BC5h; unsigned int
0x18000f382  mov     ecx, r13d; unsigned int
0x18000f385  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000f38a  mov     rax, [r14+10h]
0x18000f38e  mov     rsi, [rax+8]
0x18000f392  jmp     loc_18000F1EC
0x18000f397  mov     rax, [r14+18h]
0x18000f39b  mov     [r14+10h], rax
0x18000f39f  lea     rcx, [rsp+1140h+var_1100]; this
0x18000f3a4  call    ??1CAppList@@UEAA@XZ; CAppList::~CAppList(void)
0x18000f3a9  xor     eax, eax
0x18000f3ab  jmp     short loc_18000F3CB
0x18000f3ad  lea     rcx, [rsp+1140h+var_1100]; this
0x18000f3b2  call    ??1CAppList@@UEAA@XZ; CAppList::~CAppList(void)
0x18000f3b7  mov     eax, 8007000Eh
0x18000f3bc  jmp     short loc_18000F3CB
0x18000f3be  lea     rcx, [rsp+1140h+var_1100]; this
0x18000f3c3  call    ??1CAppList@@UEAA@XZ; CAppList::~CAppList(void)
0x18000f3c8  mov     eax, r12d
0x18000f3cb  mov     rcx, [rbp+1040h+var_40]
0x18000f3d2  xor     rcx, rsp; StackCookie
0x18000f3d5  call    __security_check_cookie
0x18000f3da  mov     rbx, [rsp+1140h+arg_10]
0x18000f3e2  add     rsp, 1110h
0x18000f3e9  pop     r15
0x18000f3eb  pop     r14
0x18000f3ed  pop     r13
0x18000f3ef  pop     r12
0x18000f3f1  pop     rdi
0x18000f3f2  pop     rsi
0x18000f3f3  pop     rbp
0x18000f3f4  retn
```
