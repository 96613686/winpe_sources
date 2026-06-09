# Microsoft::Resources::Runtime::CResourceIndexInternal::GetM3FullyQualifiedReference(ushort const *,uint,ushort const *,ushort *,uint *)

- ea: `0x18002fe24`
- end: `0x180030161`
- name: `?GetM3FullyQualifiedReference@CResourceIndexInternal@Runtime@Resources@Microsoft@@QEAAJPEBGI0PEAGPEAI@Z`
- size: `829`
- prototype: `int(Microsoft::Resources::Runtime::CResourceIndexInternal *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180074710`

## callees

- `0x180028ad0`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x18002d0c0`
- `0x18002eb8c`
- `0x18002ec70`
- `0x18002fe24`
- `0x180037f58`
- `0x180065bf8`
- `0x180086800`
- `0x1800a91c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003007f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003007f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003008d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003008d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003005c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003005c`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Runtime::CResourceIndexInternal::GetM3FullyQualifiedReference(
        Microsoft::Resources::Runtime::CResourceIndexInternal *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int *a6)
{
  __int64 v8; // r14
  int Value; // eax
  unsigned int v10; // ebx
  __int64 v11; // rax
  unsigned __int16 *v12; // rdi
  unsigned __int16 *v13; // r9
  unsigned __int16 *v14; // rdi
  int PriFilePathBySchema; // eax
  void *v16; // rbx
  const unsigned __int16 *Ref; // rax
  __int64 v19; // r9
  unsigned __int16 *v20; // rax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  unsigned __int64 v24; // r9
  HANDLE ProcessHeap; // rax
  const unsigned __int16 *v26; // rax
  const unsigned __int16 **v27; // r9
  unsigned int v28; // eax
  int v29; // ecx
  int bIgnoreCase; // [rsp+20h] [rbp-B9h]
  int bIgnoreCasea; // [rsp+20h] [rbp-B9h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-B9h]
  Microsoft::Resources::StringResult *v33; // [rsp+60h] [rbp-79h] BYREF
  void *Block[2]; // [rsp+70h] [rbp-69h] BYREF
  __int64 v35; // [rsp+88h] [rbp-51h]
  void **v36; // [rsp+98h] [rbp-41h]
  __int128 v37; // [rsp+A0h] [rbp-39h]
  int v38; // [rsp+B0h] [rbp-29h]
  int v39; // [rsp+B4h] [rbp-25h]
  int v40; // [rsp+B8h] [rbp-21h]
  void *v41; // [rsp+C8h] [rbp-11h]
  int v42; // [rsp+D0h] [rbp-9h]
  LPVOID *p_lpMem; // [rsp+D8h] [rbp-1h] BYREF
  LPVOID lpMem; // [rsp+E0h] [rbp+7h] BYREF
  int v45; // [rsp+E8h] [rbp+Fh]
  __int64 v46; // [rsp+F0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+4Fh]
  unsigned __int16 *v48; // [rsp+130h] [rbp+57h] BYREF

  if ( (*((_BYTE *)this + 16) & 0xC) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F3,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)0x80070015LL,
      bIgnoreCase);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53F,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)0x80070015LL,
      bIgnoreCaseb);
    return 2147942421LL;
  }
  v8 = -1;
  v36 = &Microsoft::Resources::NamedResourceResult::`vftable';
  *(_OWORD *)Block = 0;
  p_lpMem = &lpMem;
  v35 = 0;
  bIgnoreCasea = 0;
  v37 = 0;
  v38 = -1;
  v39 = -1;
  v40 = -1;
  v41 = 0;
  v42 = 0;
  lpMem = 0;
  v45 = 0;
  v46 = 0;
  Value = Microsoft::Resources::Runtime::CResourceIndexInternal::_GetValue(this, a2, 0, 0);
  v10 = Value;
  if ( Value < 0 )
  {
    v28 = Value + 2147009780;
    if ( v28 <= 0xB )
    {
      v29 = 2065;
      if ( _bittest(&v29, v28) )
        goto LABEL_18;
    }
    v23 = 1356;
LABEL_28:
    v24 = v10;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)v24,
      bIgnoreCasea);
    Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal::~CResolvedInstanceCollectionInternal((Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal *)Block);
    return v10;
  }
  v11 = *((_QWORD *)this + 1);
  v12 = 0;
  v48 = 0;
  if ( (*(_BYTE *)(v11 + 72) & 2) != 0 )
  {
    v12 = L"Windows";
    goto LABEL_5;
  }
  Ref = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::Runtime::CResourceIndexInternal *)((char *)this + 24));
  v10 = -2147009761;
  if ( (*(_BYTE *)(v19 + 40) & 4) != 0 )
  {
    v33 = 0;
    if ( Microsoft::Resources::Runtime::CResourceManagerInternal::_TryGetIndexFromCollection(
           (RTL_SRWLOCK *)v19,
           Ref,
           &v33)
      && (v20 = (unsigned __int16 *)Microsoft::Resources::StringResult::GetRef(v33)) != 0 )
    {
      v12 = v20;
      v48 = v20;
      v21 = 0;
    }
    else
    {
      v21 = -2147009761;
    }
  }
  else
  {
    v21 = -2147024875;
  }
  if ( a4 )
  {
    if ( v21 < 0 )
    {
      v12 = a4;
    }
    else
    {
      v22 = CompareStringOrdinal(a4, -1, v12, -1, 1);
      if ( (unsigned int)IntToComparison((unsigned int)(v22 - 2)) )
      {
        v23 = 1389;
        goto LABEL_28;
      }
    }
  }
  else if ( v21 < 0 )
  {
    v26 = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::Runtime::CResourceIndexInternal *)((char *)this + 24));
    PriFilePathBySchema = Microsoft::Resources::Runtime::CResourceManagerInternal::GetPriFilePathBySchema(
                            *(Microsoft::Resources::Runtime::CResourceManagerInternal **)this,
                            v26,
                            (const unsigned __int16 **)&v48,
                            v27);
    v10 = PriFilePathBySchema;
    if ( PriFilePathBySchema < 0 )
    {
      v23 = 1401;
LABEL_39:
      v24 = (unsigned int)PriFilePathBySchema;
      goto LABEL_40;
    }
    v12 = v48;
  }
LABEL_5:
  if ( !Block[0] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57E,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)0x80070015LL,
      bIgnoreCasea);
    v10 = -2147024875;
LABEL_18:
    operator delete(Block[0]);
    operator delete(v41);
    operator delete(Block[1]);
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
    return v10;
  }
  v13 = v12;
  bIgnoreCasea = (int)Block[0];
  v14 = a5;
  PriFilePathBySchema = StringCchPrintfW(a5, 0x228u, L"@{%s?%s}", v13);
  v10 = PriFilePathBySchema;
  if ( PriFilePathBySchema < 0 )
  {
    v23 = 1413;
    goto LABEL_39;
  }
  if ( a6 )
  {
    do
      ++v8;
    while ( v14[v8] );
    *a6 = v8 + 1;
  }
  operator delete(Block[0]);
  operator delete(v41);
  operator delete(Block[1]);
  v16 = lpMem;
  if ( (lpMem || !v45) && (v45 || !lpMem) )
  {
    v46 = 0;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v16);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002fe24  mov     [rsp-8+arg_8], rbx
0x18002fe29  mov     [rsp-8+arg_10], rdi
0x18002fe2e  push    rbp
0x18002fe2f  push    r12
0x18002fe31  push    r13
0x18002fe33  push    r14
0x18002fe35  push    r15
0x18002fe37  lea     rbp, [rsp-27h]
0x18002fe3c  sub     rsp, 100h
0x18002fe43  test    byte ptr [rcx+10h], 0Ch
0x18002fe47  mov     r12, r9
0x18002fe4a  mov     r15, rcx
0x18002fe4d  jz      loc_1800300F3
0x18002fe53  xor     r13d, r13d
0x18002fe56  lea     rax, ??_7NamedResourceResult@Resources@Microsoft@@6B@; const Microsoft::Resources::NamedResourceResult::`vftable'
0x18002fe5d  mov     [rsp+120h+var_D0], r13
0x18002fe62  xorps   xmm0, xmm0
0x18002fe65  mov     [rsp+120h+var_D8], r13
0x18002fe6a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002fe6e  mov     [rbp+47h+var_88], rax
0x18002fe72  xor     r9d, r9d
0x18002fe75  lea     rax, [rbp+47h+lpMem]
0x18002fe79  movdqa  xmmword ptr [rbp+47h+Block], xmm0
0x18002fe7e  mov     [rbp+47h+var_48], rax
0x18002fe82  xor     r8d, r8d
0x18002fe85  lea     rax, [rbp+47h+Block]
0x18002fe89  mov     [rbp+47h+var_98], r13
0x18002fe8d  mov     [rsp+120h+var_E0], rax
0x18002fe92  mov     [rsp+120h+var_E8], r13
0x18002fe97  mov     [rsp+120h+var_F0], r13
0x18002fe9c  mov     [rsp+120h+var_F8], 4
0x18002fea4  mov     qword ptr [rsp+120h+bIgnoreCase], r13; int
0x18002fea9  movdqa  [rbp+47h+var_80], xmm0
0x18002feae  mov     [rbp+47h+var_70], r14d
0x18002feb2  mov     [rbp+47h+var_6C], r14d
0x18002feb6  mov     [rbp+47h+var_68], r14d
0x18002feba  mov     [rbp+47h+var_58], r13
0x18002febe  mov     [rbp+47h+var_50], r13d
0x18002fec2  mov     [rbp+47h+lpMem], r13
0x18002fec6  mov     [rbp+47h+var_38], r13d
0x18002feca  mov     [rbp+47h+var_30], r13
0x18002fece  call    ?_GetValue@CResourceIndexInternal@Runtime@Resources@Microsoft@@AEAAJPEBGPEAUIUri@@0PEAVCContext@234@W4RESOURCE_SEARCH_OPTIONS@234@PEAPEBGPEAVCResolvedInstanceInternal@234@PEAVCResolvedInstanceCollectionInternal@234@PEA_NPEAPEAV1234@@Z; Microsoft::Resources::Runtime::CResourceIndexInternal::_GetValue(ushort const *,IUri *,ushort const *,Microsoft::Resources::Runtime::CContext *,Microsoft::Resources::Runtime::RESOURCE_SEARCH_OPTIONS,ushort const * *,Microsoft::Resources::Runtime::CResolvedInstanceInternal *,Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal *,bool *,Microsoft::Resources::Runtime::CResourceIndexInternal * *)
0x18002fed3  mov     ebx, eax
0x18002fed5  test    eax, eax
0x18002fed7  js      loc_1800300D4
0x18002fedd  mov     rax, [r15+8]
0x18002fee1  mov     edi, r13d
0x18002fee4  mov     [rbp+47h+arg_0], r13
0x18002fee8  test    byte ptr [rax+48h], 2
0x18002feec  jz      loc_18002FFF1
0x18002fef2  lea     rdi, aWindows; "Windows"
0x18002fef9  mov     rax, [rbp+47h+Block]
0x18002fefd  test    rax, rax
0x18002ff00  jz      loc_18002FFA9
0x18002ff06  mov     r9, rdi
0x18002ff09  mov     qword ptr [rsp+120h+bIgnoreCase], rax; int
0x18002ff0e  mov     rdi, [rbp+47h+arg_20]
0x18002ff12  lea     r8, aSS_1; "@{%s?%s}"
0x18002ff19  mov     rcx, rdi; unsigned __int16 *
0x18002ff1c  mov     edx, 228h; unsigned __int64
0x18002ff21  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ff26  mov     ebx, eax
0x18002ff28  test    eax, eax
0x18002ff2a  js      loc_180030133
0x18002ff30  mov     rcx, [rbp+47h+arg_28]
0x18002ff34  test    rcx, rcx
0x18002ff37  jz      short loc_18002FF49
0x18002ff39  inc     r14
0x18002ff3c  cmp     [rdi+r14*2], r13w
0x18002ff41  jnz     short loc_18002FF39
0x18002ff43  lea     eax, [r14+1]
0x18002ff47  mov     [rcx], eax
0x18002ff49  mov     rcx, [rbp+47h+Block]; Block
0x18002ff4d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ff52  mov     rcx, [rbp+47h+var_58]; Block
0x18002ff56  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ff5b  mov     rcx, [rbp+47h+Block+8]; Block
0x18002ff5f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ff64  mov     rbx, [rbp+47h+lpMem]
0x18002ff68  mov     eax, [rbp+47h+var_38]
0x18002ff6b  test    rbx, rbx
0x18002ff6e  jnz     short loc_18002FF74
0x18002ff70  test    eax, eax
0x18002ff72  jnz     short loc_18002FF8A
0x18002ff74  test    eax, eax
0x18002ff76  jnz     short loc_18002FF7D
0x18002ff78  test    rbx, rbx
0x18002ff7b  jnz     short loc_18002FF8A
0x18002ff7d  mov     [rbp+47h+var_30], r13
0x18002ff81  test    rbx, rbx
0x18002ff84  jnz     loc_18003007F
0x18002ff8a  xor     eax, eax
0x18002ff8c  lea     r11, [rsp+120h+var_20]
0x18002ff94  mov     rbx, [r11+38h]
0x18002ff98  mov     rdi, [r11+40h]
0x18002ff9c  mov     rsp, r11
0x18002ff9f  pop     r15
0x18002ffa1  pop     r14
0x18002ffa3  pop     r13
0x18002ffa5  pop     r12
0x18002ffa7  pop     rbp
0x18002ffa8  retn
0x18002ffa9  mov     rcx, [rbp+4Fh]; this
0x18002ffad  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x18002ffb4  mov     r9d, 80070015h; char *
0x18002ffba  mov     edx, 57Eh; void *
0x18002ffbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ffc4  mov     ebx, 80070015h
0x18002ffc9  mov     rcx, [rbp+47h+Block]; Block
0x18002ffcd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ffd2  mov     rcx, [rbp+47h+var_58]; Block
0x18002ffd6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ffdb  mov     rcx, [rbp+47h+Block+8]; Block
0x18002ffdf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ffe4  lea     rcx, [rbp+47h+var_48]; this
0x18002ffe8  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18002ffed  mov     eax, ebx
0x18002ffef  jmp     short loc_18002FF8C
0x18002fff1  mov     r9, [r15]
0x18002fff4  lea     rcx, [r15+18h]; this
0x18002fff8  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x18002fffd  test    byte ptr [r9+28h], 4
0x180030002  mov     ebx, 80073B1Fh
0x180030007  jz      loc_180030098
0x18003000d  lea     r8, [rbp+47h+var_C0]; struct Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo **
0x180030011  mov     [rbp+47h+var_C0], rdi
0x180030015  mov     rdx, rax; unsigned __int16 *
0x180030018  mov     rcx, r9; this
0x18003001b  call    ?_TryGetIndexFromCollection@CResourceManagerInternal@Runtime@Resources@Microsoft@@AEAA_NPEBGPEAPEAVCSchemaPriIndexInfo@1234@@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::_TryGetIndexFromCollection(ushort const *,Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo * *)
0x180030020  test    al, al
0x180030022  jz      short loc_18003009F
0x180030024  mov     rcx, [rbp+47h+var_C0]; this
0x180030028  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x18003002d  test    rax, rax
0x180030030  jz      short loc_18003009F
0x180030032  mov     rdi, rax
0x180030035  mov     [rbp+47h+arg_0], rax
0x180030039  xor     eax, eax
0x18003003b  test    r12, r12
0x18003003e  jz      short loc_1800300A3
0x180030040  test    eax, eax
0x180030042  js      loc_180030159
0x180030048  mov     r9d, r14d; cchCount2
0x18003004b  mov     [rsp+120h+bIgnoreCase], 1; bIgnoreCase
0x180030053  mov     r8, rdi; lpString2
0x180030056  mov     edx, r14d; cchCount1
0x180030059  mov     rcx, r12; lpString1
0x18003005c  call    cs:__imp_CompareStringOrdinal
0x180030062  lea     ecx, [rax-2]
0x180030065  call    _IntToComparison
0x18003006a  test    eax, eax
0x18003006c  jz      loc_18002FEF9
0x180030072  mov     edx, 56Dh
0x180030077  mov     r9d, ebx
0x18003007a  jmp     loc_18003013B
0x18003007f  call    cs:__imp_GetProcessHeap
0x180030085  mov     r8, rbx; lpMem
0x180030088  xor     edx, edx; dwFlags
0x18003008a  mov     rcx, rax; hHeap
0x18003008d  call    cs:__imp_HeapFree
0x180030093  jmp     loc_18002FF8A
0x180030098  mov     eax, 80070015h
0x18003009d  jmp     short loc_18003003B
0x18003009f  mov     eax, ebx
0x1800300a1  jmp     short loc_18003003B
0x1800300a3  test    eax, eax
0x1800300a5  jns     loc_18002FEF9
0x1800300ab  lea     rcx, [r15+18h]; this
0x1800300af  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x1800300b4  mov     rcx, [r15]; this
0x1800300b7  lea     r8, [rbp+47h+arg_0]; unsigned __int16 **
0x1800300bb  mov     rdx, rax; unsigned __int16 *
0x1800300be  call    ?GetPriFilePathBySchema@CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAJPEBGPEAPEBG1@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::GetPriFilePathBySchema(ushort const *,ushort const * *,ushort const * *)
0x1800300c3  mov     ebx, eax
0x1800300c5  test    eax, eax
0x1800300c7  jns     loc_1800C19CE
0x1800300cd  mov     edx, 579h
0x1800300d2  jmp     short loc_180030138
0x1800300d4  add     eax, 7FF8C4F4h
0x1800300d9  cmp     eax, 0Bh
0x1800300dc  ja      short loc_1800300EC
0x1800300de  mov     ecx, 811h
0x1800300e3  bt      ecx, eax
0x1800300e6  jb      loc_18002FFC9
0x1800300ec  mov     edx, 54Ch
0x1800300f1  jmp     short loc_180030077
0x1800300f3  mov     rcx, [rbp+4Fh]; this
0x1800300f7  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x1800300fe  mov     r9d, 80070015h; char *
0x180030104  mov     edx, 7F3h; void *
0x180030109  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003010e  mov     rcx, [rbp+4Fh]; this
0x180030112  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180030119  mov     r9d, 80070015h; char *
0x18003011f  mov     edx, 53Fh; void *
0x180030124  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030129  mov     eax, 80070015h
0x18003012e  jmp     loc_18002FF8C
0x180030133  mov     edx, 585h; void *
0x180030138  mov     r9d, eax; char *
0x18003013b  mov     rcx, [rbp+4Fh]; this
0x18003013f  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180030146  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003014b  lea     rcx, [rbp+47h+Block]; this
0x18003014f  call    ??1CResolvedInstanceCollectionInternal@Runtime@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal::~CResolvedInstanceCollectionInternal(void)
0x180030154  jmp     loc_18002FFED
0x180030159  mov     rdi, r12
0x18003015c  jmp     loc_18002FEF9
0x1800c19ce  mov     rdi, [rbp+47h+arg_0]
0x1800c19d2  jmp     loc_18002FEF9
```
