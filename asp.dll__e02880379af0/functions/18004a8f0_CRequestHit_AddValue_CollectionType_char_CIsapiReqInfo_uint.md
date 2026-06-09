# CRequestHit::AddValue(CollectionType,char *,CIsapiReqInfo *,uint)

- ea: `0x18004a8f0`
- end: `0x18004aa49`
- name: `?AddValue@CRequestHit@@QEAAJW4CollectionType@@PEADPEAVCIsapiReqInfo@@I@Z`
- size: `345`
- prototype: `int __fastcall(__int64, int, char *, struct CIsapiReqInfo *, unsigned int)`
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180035868`
- `0x180035924`
- `0x18004c610`
- `0x18004ca64`

## callees

- `0x18003537c`
- `0x180039cf0`
- `0x18003a0ac`
- `0x18003a660`
- `0x18004a8f0`
- `0x18005a164`
- `0x18005a26c`

## import_xrefs

- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004a93a`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004a993`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004a9ff`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004a93a`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004a993`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004a9ff`

## pseudocode

```c
int __fastcall CRequestHit::AddValue(__int64 a1, int a2, char *a3, struct CIsapiReqInfo *a4, unsigned int a5)
{
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int result; // eax
  CClCert *v12; // rax
  int v13; // ebx
  CClCert *v14; // rax
  struct IUnknown *v15; // rdx
  void (*v16)(void); // r8
  CCookie *v17; // rax
  struct IUnknown *v18; // r9
  CCookie *v19; // rax
  __int64 v20; // rsi
  CStringList *v21; // rax
  CStringList *v22; // rax
  struct IUnknown *v23; // rdx
  void (*v24)(void); // r8
  int v25; // eax
  void (*v26)(void); // [rsp+20h] [rbp-38h]

  v8 = a2 - 2;
  if ( !v8 )
  {
    v20 = 48;
    goto LABEL_21;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v20 = 56;
LABEL_21:
    v21 = *(CStringList **)(v20 + a1);
    v13 = 0;
    if ( v21 )
      goto LABEL_24;
    v22 = (CStringList *)ALLOC_CACHE_HANDLER::Alloc(CStringList::sm_pach);
    if ( !v22 )
    {
      *(_QWORD *)(v20 + a1) = 0;
      return -2147024882;
    }
    v21 = CStringList::CStringList(v22, v23, v24);
    *(_QWORD *)(v20 + a1) = v21;
    if ( v21 )
    {
LABEL_24:
      v25 = CStringList::AddValue(v21, a3, (int)a3, a5);
      if ( v25 < 0 )
        return v25;
      return v13;
    }
    return -2147024882;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    if ( !*(_QWORD *)(a1 + 64) )
    {
      v17 = (CCookie *)ALLOC_CACHE_HANDLER::Alloc(CCookie::sm_pach);
      if ( !v17 )
      {
        *(_QWORD *)(a1 + 64) = 0;
        return -2147024882;
      }
      v19 = CCookie::CCookie(v17, a4, a5, v18, v26);
      *(_QWORD *)(a1 + 64) = v19;
      if ( !v19 )
        return -2147024882;
      result = CCookie::Init(v19);
      if ( result < 0 )
        return result;
    }
    return CCookie::AddValue(*(CCookie **)(a1 + 64), a3, 0);
  }
  if ( v10 != 1 )
    return -2147467259;
  v12 = *(CClCert **)(a1 + 72);
  v13 = 0;
  if ( v12 )
    goto LABEL_9;
  v14 = (CClCert *)ALLOC_CACHE_HANDLER::Alloc(CClCert::sm_pach);
  if ( !v14 )
  {
    *(_QWORD *)(a1 + 72) = 0;
    return -2147024882;
  }
  v12 = CClCert::CClCert(v14, v15, v16);
  *(_QWORD *)(a1 + 72) = v12;
  if ( !v12 )
    return -2147024882;
LABEL_9:
  if ( *((_QWORD *)v12 + 13) )
    return -2147467259;
  *((_QWORD *)v12 + 13) = a3;
  *((_QWORD *)v12 + 14) = 8;
  return v13;
}

```

## disassembly

```asm
0x18004a8f0  push    rbx
0x18004a8f2  push    rbp
0x18004a8f3  push    rsi
0x18004a8f4  push    rdi
0x18004a8f5  sub     rsp, 38h
0x18004a8f9  mov     rsi, r9
0x18004a8fc  mov     rbp, r8
0x18004a8ff  mov     rdi, rcx
0x18004a902  sub     edx, 2
0x18004a905  jz      loc_18004A9E8
0x18004a90b  sub     edx, 1
0x18004a90e  jz      loc_18004A9E1
0x18004a914  sub     edx, 1
0x18004a917  jz      short loc_18004A984
0x18004a919  cmp     edx, 1
0x18004a91c  jz      short loc_18004A928
0x18004a91e  mov     eax, 80004005h
0x18004a923  jmp     loc_18004AA35
0x18004a928  mov     rax, [rcx+48h]
0x18004a92c  xor     ebx, ebx
0x18004a92e  test    rax, rax
0x18004a931  jnz     short loc_18004A95A
0x18004a933  mov     rcx, cs:?sm_pach@CClCert@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CClCert::sm_pach
0x18004a93a  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18004a940  test    rax, rax
0x18004a943  jz      short loc_18004A96A
0x18004a945  mov     rcx, rax; this
0x18004a948  call    ??0CClCert@@QEAA@PEAUIUnknown@@P6AXXZ@Z; CClCert::CClCert(IUnknown *,void (*)(void))
0x18004a94d  mov     [rdi+48h], rax
0x18004a951  test    rax, rax
0x18004a954  jz      loc_18004AA42
0x18004a95a  cmp     [rax+68h], rbx
0x18004a95e  jz      short loc_18004A973
0x18004a960  mov     ebx, 80004005h
0x18004a965  jmp     loc_18004AA33
0x18004a96a  mov     [rdi+48h], rbx
0x18004a96e  jmp     loc_18004AA42
0x18004a973  mov     [rax+68h], rbp
0x18004a977  mov     qword ptr [rax+70h], 8
0x18004a97f  jmp     loc_18004AA33
0x18004a984  xor     ebx, ebx
0x18004a986  cmp     [rcx+40h], rbx
0x18004a98a  jnz     short loc_18004A9CA
0x18004a98c  mov     rcx, cs:?sm_pach@CCookie@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CCookie::sm_pach
0x18004a993  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18004a999  test    rax, rax
0x18004a99c  jz      short loc_18004A9DB
0x18004a99e  mov     r8d, [rsp+58h+arg_20]; unsigned int
0x18004a9a6  mov     rdx, rsi; struct CIsapiReqInfo *
0x18004a9a9  mov     rcx, rax; this
0x18004a9ac  call    ??0CCookie@@QEAA@PEAVCIsapiReqInfo@@IPEAUIUnknown@@P6AXXZ@Z; CCookie::CCookie(CIsapiReqInfo *,uint,IUnknown *,void (*)(void))
0x18004a9b1  mov     [rdi+40h], rax
0x18004a9b5  test    rax, rax
0x18004a9b8  jz      loc_18004AA42
0x18004a9be  mov     rcx, rax; this
0x18004a9c1  call    ?Init@CCookie@@QEAAJXZ; CCookie::Init(void)
0x18004a9c6  test    eax, eax
0x18004a9c8  js      short loc_18004AA35
0x18004a9ca  mov     rcx, [rdi+40h]; this
0x18004a9ce  xor     r8d, r8d; int
0x18004a9d1  mov     rdx, rbp; char *
0x18004a9d4  call    ?AddValue@CCookie@@QEAAJPEADH@Z; CCookie::AddValue(char *,int)
0x18004a9d9  jmp     short loc_18004AA35
0x18004a9db  mov     [rdi+40h], rbx
0x18004a9df  jmp     short loc_18004AA42
0x18004a9e1  mov     esi, 38h ; '8'
0x18004a9e6  jmp     short loc_18004A9ED
0x18004a9e8  mov     esi, 30h ; '0'
0x18004a9ed  mov     rax, [rsi+rcx]
0x18004a9f1  xor     ebx, ebx
0x18004a9f3  test    rax, rax
0x18004a9f6  jnz     short loc_18004AA1B
0x18004a9f8  mov     rcx, cs:?sm_pach@CStringList@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CStringList::sm_pach
0x18004a9ff  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18004aa05  test    rax, rax
0x18004aa08  jz      short loc_18004AA3E
0x18004aa0a  mov     rcx, rax; this
0x18004aa0d  call    ??0CStringList@@QEAA@PEAUIUnknown@@P6AXXZ@Z; CStringList::CStringList(IUnknown *,void (*)(void))
0x18004aa12  mov     [rsi+rdi], rax
0x18004aa16  test    rax, rax
0x18004aa19  jz      short loc_18004AA42
0x18004aa1b  mov     r9d, [rsp+58h+arg_20]; unsigned int
0x18004aa23  mov     rdx, rbp; char *
0x18004aa26  mov     rcx, rax; this
0x18004aa29  call    ?AddValue@CStringList@@QEAAJPEADHI@Z; CStringList::AddValue(char *,int,uint)
0x18004aa2e  test    eax, eax
0x18004aa30  cmovs   ebx, eax
0x18004aa33  mov     eax, ebx
0x18004aa35  add     rsp, 38h
0x18004aa39  pop     rdi
0x18004aa3a  pop     rsi
0x18004aa3b  pop     rbp
0x18004aa3c  pop     rbx
0x18004aa3d  retn
0x18004aa3e  mov     [rsi+rdi], rbx
0x18004aa42  mov     eax, 8007000Eh
0x18004aa47  jmp     short loc_18004AA35
```
