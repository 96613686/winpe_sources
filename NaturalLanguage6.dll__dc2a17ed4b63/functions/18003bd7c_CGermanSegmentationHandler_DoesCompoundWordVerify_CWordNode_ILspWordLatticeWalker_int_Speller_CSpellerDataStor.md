# CGermanSegmentationHandler::DoesCompoundWordVerify(CWordNode *,ILspWordLatticeWalker *,int,Speller::CSpellerDataStorage *)

- ea: `0x18003bd7c`
- end: `0x18003c071`
- name: `?DoesCompoundWordVerify@CGermanSegmentationHandler@@SA_NPEAVCWordNode@@PEAUILspWordLatticeWalker@@HPEAVCSpellerDataStorage@Speller@@@Z`
- size: `757`
- prototype: `bool __fastcall(struct CWordNode *, struct ILspWordLatticeWalker *, int, struct Speller::CSpellerDataStorage *)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180093e24`

## callees

- `0x180003d38`
- `0x180016258`
- `0x1800162e4`
- `0x18002a918`
- `0x18002be20`
- `0x180035640`
- `0x18003bd7c`
- `0x18003c078`
- `0x18003ed6c`
- `0x18005dbdc`
- `0x180092f58`
- `0x180098848`
- `0x180098f8c`
- `0x18009e300`
- `0x1800b0010`

## pseudocode

```c
char __fastcall CGermanSegmentationHandler::DoesCompoundWordVerify(
        struct CWordNode *a1,
        struct ILspWordLatticeWalker *a2,
        unsigned int a3,
        struct Speller::CSpellerDataStorage *a4)
{
  char v4; // r12
  __int64 v6; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  struct CZoneHeap *v12; // rax
  unsigned int v13; // edx
  unsigned int v14; // eax
  unsigned __int64 v15; // r14
  __int64 v16; // rax
  struct CWordNode *v17; // rdi
  __int64 v18; // r8
  int v19; // edx
  unsigned __int64 v20; // r8
  __int64 v21; // rcx
  unsigned __int64 v22; // rbx
  unsigned __int16 *v23; // rax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  struct CZoneHeap *v27; // rbx
  struct CNodeProperties *v28; // rax
  __int64 v29; // rcx
  unsigned __int64 v31; // [rsp+28h] [rbp-D8h]
  bool v32; // [rsp+40h] [rbp-C0h] BYREF
  bool v33; // [rsp+41h] [rbp-BFh] BYREF
  struct CZoneHeap *v34; // [rsp+48h] [rbp-B8h]
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v36[72]; // [rsp+90h] [rbp-70h] BYREF
  size_t v37[18]; // [rsp+120h] [rbp+20h] BYREF
  const void *retaddr; // [rsp+208h] [rbp+108h]

  v4 = 0;
  v6 = *((_QWORD *)a4 + 4);
  v36[0] = 0;
  v32 = 0;
  v33 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 80LL))(v6);
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 24LL))(v10);
  v12 = (struct CZoneHeap *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 112LL))(v11);
  v13 = *((_DWORD *)a1 + 4);
  v34 = v12;
  v14 = Speller::CWordCollection::IndexOf(
          (struct Speller::CSpellerDataStorage *)((char *)a4 + 104),
          v13,
          *(_DWORD *)((char *)a1 + *(int *)(*((_QWORD *)a1 + 1) + 4LL) + 80));
  if ( (unsigned __int64)v14 >= *((_QWORD *)a4 + 14) )
  {
    CNLException::CNLException((CNLException *)pExceptionObject, 2147942487LL, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  v15 = *((_QWORD *)a4 + 13) + ((unsigned __int64)v14 << 7);
  (**(void (__fastcall ***)(struct ILspWordLatticeWalker *, _QWORD))a2)(a2, *((_QWORD *)a1 + 2));
  while ( 1 )
  {
    v16 = (*(__int64 (__fastcall **)(struct ILspWordLatticeWalker *))(*(_QWORD *)a2 + 32LL))(a2);
    v17 = (struct CWordNode *)v16;
    if ( !v16 )
      break;
    v4 = 0;
    v18 = *(int *)(*(_QWORD *)(v16 + 8) + 4LL);
    if ( (*(_DWORD *)(v18 + v16 + 8) & 0xF8000000) == 0x38000000 )
    {
      v19 = *(_DWORD *)(v18 + v16 + 16);
      if ( (v19 & 0x400) != 0 && (a3 & 1) != 0
        || (v19 & 0x1000) != 0 && (a3 & 2) != 0
        || (v19 & 0x2000) != 0 && (a3 & 4) != 0
        || (v19 & 0x4000) != 0 && (a3 & 8) != 0 )
      {
        if ( (*(_DWORD *)(v18 + v16 + 36) & 0x100) == 0 || (v4 = 0, *(_DWORD *)(v15 + 76) == 6) )
        {
          v4 = 0;
          if ( CGermanSegmentationHandler::DoesCompoundWordVerifyAux(a1, a2, a3, a4, v36, v31, &v32, &v33) )
          {
            v4 = 1;
            if ( (*(_DWORD *)((_BYTE *)v17 + *(int *)(*((_QWORD *)v17 + 1) + 4LL) + 36) & 0x200) == 0
              || !CGermanSegmentationHandler::FindNormForms(v17, v36, v20, &v32) )
            {
              v21 = *(int *)(*((_QWORD *)v17 + 1) + 4LL);
              v22 = *(_QWORD *)((char *)v17 + v21 + 80);
              v23 = (unsigned __int16 *)LSP::CName::ToString((struct CWordNode *)((char *)v17 + v21 + 48));
              v24 = StringCchCopyNW((unsigned __int16 *)v37, 0x41u, v23, v22);
              ThrowIfFailed(v24);
              v25 = StringCchCatW((unsigned __int16 *)v37, 0x41u, v36);
              ThrowIfFailed(v25);
              v26 = StringCchCopyW(v36, 0x41u, v37);
              ThrowIfFailed(v26);
            }
            if ( v32 && !v33 )
            {
              v27 = v34;
              v28 = CMorphNode::NewProperties(
                      (struct CWordNode *)((char *)a1 + *(int *)(*((_QWORD *)a1 + 1) + 4LL) + 8),
                      v34);
              v29 = -1;
              do
                ++v29;
              while ( v36[v29] );
              CNodeProperties::AddNormalizedString(v28, *(_QWORD *)(*((_QWORD *)a4 + 4) + 168LL), v27, v36, v29, 242);
              *(_DWORD *)((char *)a1 + *(int *)(*((_QWORD *)a1 + 1) + 4LL) + 36) |= 0x200u;
              *(_BYTE *)(v15 + 57) = 1;
            }
            return v4;
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18003bd7c  push    rbp
0x18003bd7e  push    rbx
0x18003bd7f  push    rsi
0x18003bd80  push    rdi
0x18003bd81  push    r12
0x18003bd83  push    r13
0x18003bd85  push    r14
0x18003bd87  push    r15
0x18003bd89  lea     rbp, [rsp-0C8h]
0x18003bd91  sub     rsp, 1C8h
0x18003bd98  mov     rax, cs:__security_cookie
0x18003bd9f  xor     rax, rsp
0x18003bda2  mov     [rbp+100h+var_50], rax
0x18003bda9  xor     r12d, r12d
0x18003bdac  mov     rsi, rcx
0x18003bdaf  mov     rcx, [r9+20h]
0x18003bdb3  mov     r13, r9
0x18003bdb6  mov     [rbp+100h+var_170], r12w
0x18003bdbb  mov     ebx, r8d
0x18003bdbe  mov     [rsp+200h+var_1C0], r12b
0x18003bdc3  mov     r15, rdx
0x18003bdc6  mov     [rsp+200h+var_1BF], r12b
0x18003bdcb  mov     rax, [rcx]
0x18003bdce  mov     rax, [rax+50h]
0x18003bdd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdd7  mov     rdx, rax
0x18003bdda  mov     rcx, [rax]
0x18003bddd  mov     rax, [rcx+18h]
0x18003bde1  mov     rcx, rdx
0x18003bde4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bde9  mov     rdx, rax
0x18003bdec  mov     rcx, [rax]
0x18003bdef  mov     rax, [rcx+70h]
0x18003bdf3  mov     rcx, rdx
0x18003bdf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdfb  mov     edx, [rsi+10h]; unsigned int
0x18003bdfe  lea     rcx, [r13+68h]; this
0x18003be02  mov     [rsp+200h+var_1B8], rax
0x18003be07  mov     rax, [rsi+8]
0x18003be0b  movsxd  r8, dword ptr [rax+4]
0x18003be0f  mov     r8d, [r8+rsi+50h]; unsigned int
0x18003be14  call    ?IndexOf@CWordCollection@Speller@@QEAAHII@Z; Speller::CWordCollection::IndexOf(uint,uint)
0x18003be19  mov     r14d, eax
0x18003be1c  cmp     r14, [r13+70h]
0x18003be20  jb      short loc_18003BE4A
0x18003be22  mov     r8, [rbp+108h]; void *
0x18003be29  lea     rcx, [rsp+200h+pExceptionObject]; this
0x18003be2e  mov     edx, 80070057h; int
0x18003be33  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18003be38  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18003be3f  lea     rcx, [rsp+200h+pExceptionObject]; pExceptionObject
0x18003be44  call    _CxxThrowException_0
0x18003be4a  mov     rax, [r15]
0x18003be4d  mov     rcx, r15
0x18003be50  mov     rdx, [rsi+10h]
0x18003be54  shl     r14, 7
0x18003be58  add     r14, [r13+68h]
0x18003be5c  mov     rax, [rax]
0x18003be5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be64  mov     rax, [r15]
0x18003be67  mov     rcx, r15
0x18003be6a  mov     rax, [rax+20h]
0x18003be6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be73  mov     rdi, rax
0x18003be76  test    rax, rax
0x18003be79  jz      loc_18003C04B
0x18003be7f  mov     rcx, [rax+8]
0x18003be83  mov     r12d, 0
0x18003be89  movsxd  r8, dword ptr [rcx+4]
0x18003be8d  mov     ecx, [r8+rax+8]
0x18003be92  and     ecx, 0F8000000h
0x18003be98  cmp     ecx, 38000000h
0x18003be9e  jnz     short loc_18003BE64
0x18003bea0  mov     edx, [r8+rax+10h]
0x18003bea5  bt      edx, 0Ah
0x18003bea9  setb    cl
0x18003beac  test    bl, 1
0x18003beaf  setnz   al
0x18003beb2  test    al, cl
0x18003beb4  jnz     short loc_18003BEED
0x18003beb6  bt      edx, 0Ch
0x18003beba  setb    cl
0x18003bebd  test    bl, 2
0x18003bec0  setnz   al
0x18003bec3  test    al, cl
0x18003bec5  jnz     short loc_18003BEED
0x18003bec7  bt      edx, 0Dh
0x18003becb  setb    cl
0x18003bece  test    bl, 4
0x18003bed1  setnz   al
0x18003bed4  test    al, cl
0x18003bed6  jnz     short loc_18003BEED
0x18003bed8  bt      edx, 0Eh
0x18003bedc  setb    cl
0x18003bedf  test    bl, 8
0x18003bee2  setnz   al
0x18003bee5  test    al, cl
0x18003bee7  jz      loc_18003BE64
0x18003beed  test    dword ptr [r8+rdi+24h], 100h
0x18003bef6  jz      short loc_18003BF09
0x18003bef8  cmp     dword ptr [r14+4Ch], 6
0x18003befd  mov     r12d, 0
0x18003bf03  jnz     loc_18003BE64
0x18003bf09  lea     rax, [rsp+200h+var_1BF]
0x18003bf0e  mov     r9, r13; struct Speller::CSpellerDataStorage *
0x18003bf11  mov     [rsp+200h+var_1C8], rax; bool *
0x18003bf16  mov     r8d, ebx; int
0x18003bf19  lea     rax, [rsp+200h+var_1C0]
0x18003bf1e  mov     rdx, r15; struct ILspWordLatticeWalker *
0x18003bf21  mov     [rsp+200h+var_1D0], rax; bool *
0x18003bf26  mov     rcx, rsi; struct CWordNode *
0x18003bf29  lea     rax, [rbp+100h+var_170]
0x18003bf2d  mov     [rsp+200h+var_1E0], rax; unsigned __int16 *
0x18003bf32  call    ?DoesCompoundWordVerifyAux@CGermanSegmentationHandler@@SA_NPEAVCWordNode@@PEAUILspWordLatticeWalker@@HPEAVCSpellerDataStorage@Speller@@QEAG_KAEA_N5@Z; CGermanSegmentationHandler::DoesCompoundWordVerifyAux(CWordNode *,ILspWordLatticeWalker *,int,Speller::CSpellerDataStorage *,ushort * const,unsigned __int64,bool &,bool &)
0x18003bf37  xor     r12d, r12d
0x18003bf3a  test    al, al
0x18003bf3c  jz      loc_18003BE64
0x18003bf42  mov     rax, [rdi+8]
0x18003bf46  mov     r12b, 1
0x18003bf49  movsxd  rcx, dword ptr [rax+4]
0x18003bf4d  test    dword ptr [rcx+rdi+24h], 200h
0x18003bf55  jz      short loc_18003BF71
0x18003bf57  lea     r9, [rsp+200h+var_1C0]; bool *
0x18003bf5c  mov     rcx, rdi; struct CWordNode *
0x18003bf5f  lea     rdx, [rbp+100h+var_170]; unsigned __int16 *
0x18003bf63  call    ?FindNormForms@CGermanSegmentationHandler@@SA_NPEAVCWordNode@@QEAG_KAEA_N@Z; CGermanSegmentationHandler::FindNormForms(CWordNode *,ushort * const,unsigned __int64,bool &)
0x18003bf68  xor     r15d, r15d
0x18003bf6b  test    al, al
0x18003bf6d  jnz     short loc_18003BFD6
0x18003bf6f  jmp     short loc_18003BF74
0x18003bf71  xor     r15d, r15d
0x18003bf74  mov     rax, [rdi+8]
0x18003bf78  movsxd  rcx, dword ptr [rax+4]
0x18003bf7c  mov     rbx, [rcx+rdi+50h]
0x18003bf81  add     rcx, 30h ; '0'
0x18003bf85  add     rcx, rdi; this
0x18003bf88  call    ?ToString@CName@LSP@@QEBAPEBGXZ; LSP::CName::ToString(void)
0x18003bf8d  mov     r9, rbx; unsigned __int64
0x18003bf90  lea     rcx, [rbp+100h+var_E0]; unsigned __int16 *
0x18003bf94  mov     ebx, 41h ; 'A'
0x18003bf99  mov     r8, rax; unsigned __int16 *
0x18003bf9c  mov     edx, ebx; unsigned __int64
0x18003bf9e  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18003bfa3  mov     ecx, eax; int
0x18003bfa5  call    ?ThrowIfFailed@@YAXJ@Z; ThrowIfFailed(long)
0x18003bfaa  lea     r8, [rbp+100h+var_170]; unsigned __int16 *
0x18003bfae  mov     edx, ebx; unsigned __int64
0x18003bfb0  lea     rcx, [rbp+100h+var_E0]; unsigned __int16 *
0x18003bfb4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003bfb9  mov     ecx, eax; int
0x18003bfbb  call    ?ThrowIfFailed@@YAXJ@Z; ThrowIfFailed(long)
0x18003bfc0  lea     r8, [rbp+100h+var_E0]; unsigned __int16 *
0x18003bfc4  mov     edx, ebx; unsigned __int64
0x18003bfc6  lea     rcx, [rbp+100h+var_170]; unsigned __int16 *
0x18003bfca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003bfcf  mov     ecx, eax; int
0x18003bfd1  call    ?ThrowIfFailed@@YAXJ@Z; ThrowIfFailed(long)
0x18003bfd6  cmp     [rsp+200h+var_1C0], r15b
0x18003bfdb  jz      short loc_18003C04B
0x18003bfdd  cmp     [rsp+200h+var_1BF], r15b
0x18003bfe2  jnz     short loc_18003C04B
0x18003bfe4  mov     rax, [rsi+8]
0x18003bfe8  mov     rbx, [rsp+200h+var_1B8]
0x18003bfed  mov     rdx, rbx; struct CZoneHeap *
0x18003bff0  movsxd  rcx, dword ptr [rax+4]
0x18003bff4  add     rcx, 8
0x18003bff8  add     rcx, rsi; this
0x18003bffb  call    ?NewProperties@CMorphNode@@QEAAPEAVCNodeProperties@@AEAVCZoneHeap@@@Z; CMorphNode::NewProperties(CZoneHeap &)
0x18003c000  lea     rdx, [rbp+100h+var_170]
0x18003c004  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003c008  inc     rcx
0x18003c00b  cmp     [rdx+rcx*2], r15w
0x18003c010  jnz     short loc_18003C008
0x18003c012  mov     rdx, [r13+20h]
0x18003c016  lea     r9, [rbp+100h+var_170]
0x18003c01a  mov     dword ptr [rsp+200h+var_1D8], 0F2h
0x18003c022  mov     r8, rbx
0x18003c025  mov     [rsp+200h+var_1E0], rcx
0x18003c02a  mov     rcx, rax
0x18003c02d  mov     rdx, [rdx+0A8h]
0x18003c034  call    ?AddNormalizedString@CNodeProperties@@QEAAPEAVCNodeProperty@@PEAVCText@@AEAVCZoneHeap@@PEBG_KW4EMorphUnit@CMorphBits@@@Z; CNodeProperties::AddNormalizedString(CText *,CZoneHeap &,ushort const *,unsigned __int64,CMorphBits::EMorphUnit)
0x18003c039  mov     rcx, [rsi+8]
0x18003c03d  movsxd  rdx, dword ptr [rcx+4]
0x18003c041  bts     dword ptr [rdx+rsi+24h], 9
0x18003c047  mov     [r14+39h], r12b
0x18003c04b  mov     al, r12b
0x18003c04e  mov     rcx, [rbp+100h+var_50]
0x18003c055  xor     rcx, rsp; StackCookie
0x18003c058  call    __security_check_cookie
0x18003c05d  add     rsp, 1C8h
0x18003c064  pop     r15
0x18003c066  pop     r14
0x18003c068  pop     r13
0x18003c06a  pop     r12
0x18003c06c  pop     rdi
0x18003c06d  pop     rsi
0x18003c06e  pop     rbx
0x18003c06f  pop     rbp
0x18003c070  retn
```
