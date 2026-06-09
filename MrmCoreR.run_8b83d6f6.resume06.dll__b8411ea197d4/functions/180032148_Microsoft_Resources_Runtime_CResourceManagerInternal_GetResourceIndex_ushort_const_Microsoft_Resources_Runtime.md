# Microsoft::Resources::Runtime::CResourceManagerInternal::GetResourceIndex(ushort const *,Microsoft::Resources::Runtime::CResourceIndexInternal * *)

- ea: `0x180032148`
- end: `0x180032450`
- name: `?GetResourceIndex@CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAJPEBGPEAPEAVCResourceIndexInternal@234@@Z`
- size: `776`
- prototype: `__int64 __fastcall(Microsoft::Resources::Runtime::CResourceManagerInternal *__hidden this, const unsigned __int16 *, struct Microsoft::Resources::Runtime::CResourceIndexInternal **)`
- caller_count: `11`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002d0c0`
- `0x180030168`
- `0x180032030`
- `0x180032458`
- `0x1800325e0`
- `0x180059b50`
- `0x180059de0`
- `0x180079a70`
- `0x1800aac98`
- `0x1800ad010`
- `0x1800ad170`

## callees

- `0x180015944`
- `0x180017960`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x180032148`
- `0x180037f58`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800321b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180032230`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800321b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180032230`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180032211`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003228a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180032211`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003228a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800321ef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003225e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800321ef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003225e`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Runtime::CResourceManagerInternal::GetResourceIndex(
        Microsoft::Resources::Runtime::CResourceManagerInternal *this,
        const unsigned __int16 *a2,
        struct Microsoft::Resources::Runtime::CResourceIndexInternal **a3)
{
  struct Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo *v6; // r15
  int v7; // r13d
  unsigned __int64 v8; // rbx
  const WCHAR *v9; // rax
  unsigned __int64 i; // rbx
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // esi
  int PriFile; // eax
  unsigned int v16; // ebx
  int bIgnoreCase; // [rsp+20h] [rbp-30h]
  _BYTE *v18; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v19[24]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  LPCWCH lpString2; // [rsp+90h] [rbp+40h] BYREF
  struct Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo *v22; // [rsp+A0h] [rbp+50h] BYREF
  const WCHAR *v23; // [rsp+A8h] [rbp+58h]

  *a3 = 0;
  if ( (*((_BYTE *)this + 40) & 4) == 0 )
    return 2147942421LL;
  if ( !a2 )
    return 2147957535LL;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 22) + 24LL))(*((_QWORD *)this + 22)) )
    return 2147942405LL;
  v6 = 0;
  v22 = 0;
  v23 = 0;
  AcquireSRWLockShared((PSRWLOCK)this + 21);
  v7 = -2147023728;
  v8 = 0;
  LODWORD(lpString2) = -2147023728;
  while ( v8 < *((_QWORD *)this + 20) )
  {
    if ( CompareStringOrdinal(*(LPCWCH *)(*((_QWORD *)this + 17) + 16 * v8), -1, a2, -1, 1) == 2 )
    {
      if ( v8 < *((_QWORD *)this + 20) )
      {
        v12 = *((_QWORD *)this + 17);
        LODWORD(lpString2) = 0;
        v23 = *(const WCHAR **)(v12 + 16 * v8 + 8);
      }
      break;
    }
    ++v8;
  }
  ReleaseSRWLockShared((PSRWLOCK)this + 21);
  v9 = a2;
  if ( (int)lpString2 >= 0 )
    v9 = v23;
  lpString2 = v9;
  AcquireSRWLockShared((PSRWLOCK)this + 16);
  for ( i = 0; i < *((_QWORD *)this + 15); ++i )
  {
    if ( CompareStringOrdinal(*(LPCWCH *)(*((_QWORD *)this + 12) + 16 * i), -1, lpString2, -1, 1) == 2 )
    {
      if ( i < *((_QWORD *)this + 15) )
      {
        v7 = 0;
        v6 = *(struct Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo **)(*((_QWORD *)this + 12) + 16 * i + 8);
        v22 = v6;
      }
      break;
    }
  }
  ReleaseSRWLockShared((PSRWLOCK)this + 16);
  if ( v7 >= 0 )
  {
    *a3 = (struct Microsoft::Resources::Runtime::CResourceIndexInternal *)*((_QWORD *)v6 + 8);
    return 0;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 22) + 32LL))(*((_QWORD *)this + 22)) )
    return 2147957535LL;
  DefStringResult_InitBuf(v19);
  LOBYTE(lpString2) = 0;
  v18 = v19;
  v13 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _BYTE **, LPCWCH *))(**((_QWORD **)this + 22)
                                                                                        + 272LL))(
          *((_QWORD *)this + 22),
          a2,
          &v18,
          &lpString2);
  v14 = v13;
  if ( v13 < 0 )
  {
    v16 = -2147009737;
    if ( v13 != -2147009737 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x327,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
        (const char *)(unsigned int)v13,
        bIgnoreCase);
      v16 = v14;
    }
  }
  else
  {
    PriFile = Microsoft::Resources::Runtime::CResourceManagerInternal::LoadPriFile(this, 1);
    v16 = PriFile;
    if ( PriFile < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x328,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
        (const char *)(unsigned int)PriFile,
        0);
    }
    else
    {
      if ( Microsoft::Resources::Runtime::CResourceManagerInternal::_TryGetIndexFromCollection(this, a2, &v22) )
      {
        *a3 = (struct Microsoft::Resources::Runtime::CResourceIndexInternal *)*((_QWORD *)v22 + 8);
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v18);
        return 0;
      }
      v16 = -2147009761;
    }
  }
  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v18);
  return v16;
}

```

## disassembly

```asm
0x180032148  mov     [rsp-38h+arg_8], rbx
0x18003214d  push    rbp
0x18003214e  push    rsi
0x18003214f  push    rdi
0x180032150  push    r12
0x180032152  push    r13
0x180032154  push    r14
0x180032156  push    r15
0x180032158  mov     rbp, rsp
0x18003215b  sub     rsp, 50h
0x18003215f  mov     qword ptr [r8], 0
0x180032166  mov     r12, r8
0x180032169  test    byte ptr [rcx+28h], 4
0x18003216d  mov     r14, rdx
0x180032170  mov     rdi, rcx
0x180032173  jz      loc_180032446
0x180032179  test    rdx, rdx
0x18003217c  jz      loc_1800322D1
0x180032182  mov     rcx, [rcx+0B0h]
0x180032189  mov     rax, [rcx]
0x18003218c  mov     rax, [rax+18h]
0x180032190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032195  test    al, al
0x180032197  jz      loc_1800322F4
0x18003219d  xor     r15d, r15d
0x1800321a0  lea     rcx, [rdi+0A8h]; SRWLock
0x1800321a7  mov     [rbp+arg_10], r15
0x1800321ab  xor     esi, esi
0x1800321ad  mov     [rbp+arg_18], r15
0x1800321b1  call    cs:__imp_AcquireSRWLockShared
0x1800321b7  mov     r13d, 80070490h
0x1800321bd  xor     ebx, ebx
0x1800321bf  mov     dword ptr [rbp+lpString2], r13d
0x1800321c3  cmp     rbx, [rdi+0A0h]
0x1800321ca  jnb     short loc_18003220A
0x1800321cc  mov     rcx, [rdi+88h]
0x1800321d3  or      r9d, 0FFFFFFFFh; cchCount2
0x1800321d7  mov     rax, rbx
0x1800321da  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x1800321e2  add     rax, rax
0x1800321e5  mov     r8, r14; lpString2
0x1800321e8  or      edx, r9d; cchCount1
0x1800321eb  mov     rcx, [rcx+rax*8]; lpString1
0x1800321ef  call    cs:__imp_CompareStringOrdinal
0x1800321f5  cmp     eax, 2
0x1800321f8  jnz     short loc_18003226E
0x1800321fa  mov     rsi, rbx
0x1800321fd  cmp     rbx, [rdi+0A0h]
0x180032204  jb      loc_1800322D8
0x18003220a  lea     rcx, [rdi+0A8h]; SRWLock
0x180032211  call    cs:__imp_ReleaseSRWLockShared
0x180032217  cmp     dword ptr [rbp+lpString2], r15d
0x18003221b  lea     rcx, [rdi+80h]; SRWLock
0x180032222  mov     rax, r14
0x180032225  cmovge  rax, [rbp+arg_18]
0x18003222a  xor     esi, esi
0x18003222c  mov     [rbp+lpString2], rax
0x180032230  call    cs:__imp_AcquireSRWLockShared
0x180032236  xor     ebx, ebx
0x180032238  cmp     rbx, [rdi+78h]
0x18003223c  jnb     short loc_180032283
0x18003223e  mov     rcx, [rdi+60h]
0x180032242  or      edx, 0FFFFFFFFh; cchCount1
0x180032245  mov     r8, [rbp+lpString2]; lpString2
0x180032249  mov     rax, rbx
0x18003224c  add     rax, rax
0x18003224f  mov     [rsp+50h+bIgnoreCase], 1; int
0x180032257  mov     r9d, edx; cchCount2
0x18003225a  mov     rcx, [rcx+rax*8]; lpString1
0x18003225e  call    cs:__imp_CompareStringOrdinal
0x180032264  cmp     eax, 2
0x180032267  jz      short loc_180032276
0x180032269  inc     rbx
0x18003226c  jmp     short loc_180032238
0x18003226e  inc     rbx
0x180032271  jmp     loc_1800321C3
0x180032276  mov     rsi, rbx
0x180032279  cmp     rbx, [rdi+78h]
0x18003227d  jb      loc_1800323BA
0x180032283  lea     rcx, [rdi+80h]; SRWLock
0x18003228a  call    cs:__imp_ReleaseSRWLockShared
0x180032290  test    r13d, r13d
0x180032293  js      short loc_1800322B7
0x180032295  mov     rax, [r15+40h]
0x180032299  mov     [r12], rax
0x18003229d  xor     eax, eax
0x18003229f  mov     rbx, [rsp+50h+arg_8]
0x1800322a7  add     rsp, 50h
0x1800322ab  pop     r15
0x1800322ad  pop     r14
0x1800322af  pop     r13
0x1800322b1  pop     r12
0x1800322b3  pop     rdi
0x1800322b4  pop     rsi
0x1800322b5  pop     rbp
0x1800322b6  retn
0x1800322b7  mov     rcx, [rdi+0B0h]
0x1800322be  mov     rax, [rcx]
0x1800322c1  mov     rax, [rax+20h]
0x1800322c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322ca  xor     r15d, r15d
0x1800322cd  test    al, al
0x1800322cf  jnz     short loc_1800322FB
0x1800322d1  mov     eax, 80073B1Fh
0x1800322d6  jmp     short loc_18003229F
0x1800322d8  mov     rax, [rdi+88h]
0x1800322df  add     rsi, rsi
0x1800322e2  mov     dword ptr [rbp+lpString2], r15d
0x1800322e6  mov     rax, [rax+rsi*8+8]
0x1800322eb  mov     [rbp+arg_18], rax
0x1800322ef  jmp     loc_18003220A
0x1800322f4  mov     eax, 80070005h
0x1800322f9  jmp     short loc_18003229F
0x1800322fb  lea     rcx, [rbp+var_18]
0x1800322ff  call    DefStringResult_InitBuf
0x180032304  lea     rcx, [rbp+var_18]
0x180032308  mov     byte ptr [rbp+lpString2], r15b
0x18003230c  mov     [rbp+var_20], rcx
0x180032310  lea     r9, [rbp+lpString2]
0x180032314  mov     rcx, [rdi+0B0h]
0x18003231b  lea     r8, [rbp+var_20]
0x18003231f  mov     rdx, r14
0x180032322  mov     rax, [rcx]
0x180032325  mov     rax, [rax+110h]
0x18003232c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032331  mov     esi, eax
0x180032333  test    eax, eax
0x180032335  js      loc_180032421
0x18003233b  mov     al, byte ptr [rbp+lpString2]
0x18003233e  mov     rcx, [rbp+var_20]
0x180032342  neg     al
0x180032344  sbb     rdx, rdx
0x180032347  and     rdx, r14
0x18003234a  test    rcx, rcx
0x18003234d  jz      loc_180032414
0x180032353  cmp     [rcx], r15
0x180032356  jnz     short loc_180032362
0x180032358  cmp     [rcx+8], r15d
0x18003235c  ja      loc_180032414
0x180032362  cmp     [rcx+8], r15d
0x180032366  jnz     short loc_180032371
0x180032368  cmp     [rcx], r15
0x18003236b  jnz     loc_180032414
0x180032371  mov     rax, [rcx+10h]
0x180032375  mov     ecx, r15d
0x180032378  test    ecx, ecx
0x18003237a  mov     [rsp+50h+var_28], rdx
0x18003237f  mov     r9, r15
0x180032382  mov     qword ptr [rsp+50h+bIgnoreCase], r15; int
0x180032387  cmovns  r9, rax
0x18003238b  mov     rcx, rdi
0x18003238e  xor     r8d, r8d
0x180032391  lea     edx, [r8+1]
0x180032395  call    ?LoadPriFile@CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAJW4_MRMPROFILE_PHASE@34@W4LoadPriFlags@34@PEBG22@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::LoadPriFile(Microsoft::Resources::_MRMPROFILE_PHASE,Microsoft::Resources::LoadPriFlags,ushort const *,ushort const *,ushort const *)
0x18003239a  mov     ebx, eax
0x18003239c  test    eax, eax
0x18003239e  js      short loc_1800323D2
0x1800323a0  lea     r8, [rbp+arg_10]; struct Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo **
0x1800323a4  mov     rdx, r14; unsigned __int16 *
0x1800323a7  mov     rcx, rdi; this
0x1800323aa  call    ?_TryGetIndexFromCollection@CResourceManagerInternal@Runtime@Resources@Microsoft@@AEAA_NPEBGPEAPEAVCSchemaPriIndexInfo@1234@@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::_TryGetIndexFromCollection(ushort const *,Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo * *)
0x1800323af  test    al, al
0x1800323b1  jnz     short loc_1800323FA
0x1800323b3  mov     ebx, 80073B1Fh
0x1800323b8  jmp     short loc_1800323EA
0x1800323ba  mov     rax, [rdi+60h]
0x1800323be  xor     r13d, r13d
0x1800323c1  add     rsi, rsi
0x1800323c4  mov     r15, [rax+rsi*8+8]
0x1800323c9  mov     [rbp+arg_10], r15
0x1800323cd  jmp     loc_180032283
0x1800323d2  mov     rcx, [rbp+38h]; this
0x1800323d6  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x1800323dd  mov     r9d, eax; char *
0x1800323e0  mov     edx, 328h; void *
0x1800323e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800323ea  lea     rcx, [rbp+var_20]; this
0x1800323ee  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x1800323f3  mov     eax, ebx
0x1800323f5  jmp     loc_18003229F
0x1800323fa  mov     rax, [rbp+arg_10]
0x1800323fe  mov     rcx, [rax+40h]
0x180032402  mov     [r12], rcx
0x180032406  lea     rcx, [rbp+var_20]; this
0x18003240a  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18003240f  jmp     loc_18003229D
0x180032414  mov     rax, r15
0x180032417  mov     ecx, 80070057h
0x18003241c  jmp     loc_180032378
0x180032421  mov     ebx, 80073B37h
0x180032426  cmp     esi, ebx
0x180032428  jz      short loc_1800323EA
0x18003242a  mov     rcx, [rbp+38h]; this
0x18003242e  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180032435  mov     r9d, esi; char *
0x180032438  mov     edx, 327h; void *
0x18003243d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032442  mov     ebx, esi
0x180032444  jmp     short loc_1800323EA
0x180032446  mov     eax, 80070015h
0x18003244b  jmp     loc_18003229F
```
