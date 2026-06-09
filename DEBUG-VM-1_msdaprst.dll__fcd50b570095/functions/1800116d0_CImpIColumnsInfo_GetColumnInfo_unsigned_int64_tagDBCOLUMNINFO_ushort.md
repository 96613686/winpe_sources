# CImpIColumnsInfo::GetColumnInfo(unsigned __int64 *,tagDBCOLUMNINFO * *,ushort * *)

- ea: `0x1800116d0`
- end: `0x1800119d1`
- name: `?GetColumnInfo@CImpIColumnsInfo@@UEAAJPEA_KPEAPEAUtagDBCOLUMNINFO@@PEAPEAG@Z`
- size: `769`
- prototype: `__int64 __fastcall(CImpIColumnsInfo *__hidden this, unsigned __int64 *, struct tagDBCOLUMNINFO **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task`

## callees

- `0x180003abc`
- `0x180004038`
- `0x180004070`
- `0x1800040a8`
- `0x18000416c`
- `0x1800041ac`
- `0x1800041f8`
- `0x1800116d0`
- `0x180015fb4`
- `0x18002e012`
- `0x18002e02a`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001171a`
- `KERNEL32!GetCurrentThreadId` at `0x18001171a`
- `KERNEL32!LeaveCriticalSection` at `0x180011988`
- `KERNEL32!LeaveCriticalSection` at `0x1800119b8`
- `KERNEL32!LeaveCriticalSection` at `0x180011988`
- `KERNEL32!LeaveCriticalSection` at `0x1800119b8`
- `ole32!CoTaskMemFree` at `0x1800117c1`
- `ole32!CoTaskMemFree` at `0x1800117c1`
- `ole32!CoTaskMemAlloc` at `0x180011786`
- `ole32!CoTaskMemAlloc` at `0x1800117ab`
- `ole32!CoTaskMemAlloc` at `0x180011786`
- `ole32!CoTaskMemAlloc` at `0x1800117ab`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001173a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001173a`
- `MSDART!UMSEnterCSWraper` at `0x18001170b`
- `MSDART!UMSEnterCSWraper` at `0x18001170b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIColumnsInfo::GetColumnInfo(
        CImpIColumnsInfo *this,
        unsigned __int64 *a2,
        struct tagDBCOLUMNINFO **a3,
        unsigned __int16 **a4)
{
  unsigned __int16 **v4; // r12
  struct tagDBCOLUMNINFO **v5; // rbx
  __int64 v8; // rdi
  unsigned __int16 v9; // r14
  struct tagDBCOLUMNINFO *v10; // rbp
  int v11; // ecx
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  CMetaData *v14; // r13
  char *v15; // rdi
  CMetaData *v16; // rcx
  unsigned __int16 *Name; // rcx
  __int16 v18; // r9
  __int64 v19; // rax
  size_t v20; // rbx
  unsigned __int16 *v21; // rax
  unsigned int Ordinal; // eax
  __int64 v23; // r10
  unsigned int Flags; // eax
  __int64 v25; // r10
  unsigned __int16 v26; // dx
  unsigned __int16 v27; // dx
  __int64 v28; // r10
  __int64 Size; // rax
  unsigned __int16 Type; // ax
  __int64 v31; // r10
  unsigned __int16 v32; // dx
  unsigned __int8 Scale; // al
  __int64 v34; // r10
  unsigned __int16 v35; // dx
  unsigned __int8 Precision; // al
  __int64 v37; // r10
  __int64 v38; // r11
  bool v39; // zf
  __int64 v40; // rcx
  unsigned int v42; // ebx
  __int64 v43; // rcx
  __int64 v44; // [rsp+20h] [rbp-58h]

  v4 = a4;
  v5 = a3;
  v8 = *((_QWORD *)this + 3) + 128LL;
  v44 = v8;
  UMSEnterCSWraper(v8);
  v9 = 0;
  if ( !*(_DWORD *)(v8 + 12) )
    *(_DWORD *)(v8 + 8) = GetCurrentThreadId();
  ++*(_DWORD *)(v8 + 12);
  ++*(_DWORD *)(v8 + 16);
  SetErrorInfo(0, 0);
  if ( a2 )
    *a2 = 0;
  if ( v5 )
    *v5 = 0;
  if ( v4 )
    *v4 = 0;
  if ( !a2 || !v5 || !v4 )
  {
    v11 = -2147024809;
    goto LABEL_33;
  }
  v10 = (struct tagDBCOLUMNINFO *)CoTaskMemAlloc(80LL * *(unsigned int *)(*((_QWORD *)this + 3) + 152LL));
  if ( !v10 )
  {
LABEL_13:
    v11 = -2147024882;
LABEL_33:
    v42 = Exit(v11, 0);
    --*(_DWORD *)(v8 + 16);
    v39 = (*(_DWORD *)(v8 + 12))-- == 1;
    if ( v39 )
      *(_DWORD *)(v8 + 8) = -1;
    v43 = *(_QWORD *)v8;
    --*(_DWORD *)(v43 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v43 + 8));
    return v42;
  }
  v12 = (unsigned __int16 *)CoTaskMemAlloc(2LL * *(unsigned int *)(*((_QWORD *)this + 3) + 268LL));
  if ( !v12 )
  {
    CoTaskMemFree(v10);
    goto LABEL_13;
  }
  v13 = *((_QWORD *)this + 3);
  v14 = (CMetaData *)(v13 + 304);
  memset_0(v10, 0, 80LL * *(unsigned int *)(v13 + 152));
  if ( *(_DWORD *)(*((_QWORD *)this + 3) + 152LL) )
  {
    v15 = (char *)v12;
    do
    {
      if ( CMetaData::mdGetName(v14, v9) )
      {
        Name = CMetaData::mdGetName(v16, v9);
        v19 = -1;
        do
          ++v19;
        while ( Name[v19] != v18 );
        v20 = 2LL * (unsigned int)(v19 + 1);
        v21 = CMetaData::mdGetName(v14, v9);
        memcpy_0(v15, v21, v20);
        v10[v9].pwszName = (LPOLESTR)v15;
        v15 += v20;
      }
      Ordinal = CMetaData::mdGetOrdinal(v14, v9);
      *(&v10->iOrdinal + v23) = Ordinal;
      Flags = CMetaData::mdGetFlags(v14, v9);
      *(&v10->dwFlags + 2 * v25) = Flags;
      if ( CMetaData::mdGetSize(v14, v26) == -1 )
        Size = -1;
      else
        Size = CMetaData::mdGetSize(v14, v27);
      *(&v10->ulColumnSize + v28) = Size;
      Type = CMetaData::mdGetType(v14, v9);
      *(&v10->wType + 4 * v31) = Type;
      Scale = CMetaData::mdGetScale(v14, v32);
      *(&v10->bScale + 8 * v34) = Scale;
      Precision = CMetaData::mdGetPrecision(v14, v35);
      *(&v10->bPrecision + 8 * v37) = Precision;
      if ( !*(_DWORD *)(9648 * v38 + *((_QWORD *)v14 + 4) + 2160) )
      {
        *(&v10->columnid.eKind + 2 * v37) = 6;
        *(union tagDBID::$8A6F84EEDBA9444E5F3B3798E7B3D46D *)((char *)&v10->columnid.uGuid + 8 * v37) = *(union tagDBID::$8A6F84EEDBA9444E5F3B3798E7B3D46D *)(9648 * v38 + *((_QWORD *)v14 + 4) + 2144);
      }
      ++v9;
    }
    while ( (unsigned int)v9 < *(_DWORD *)(*((_QWORD *)this + 3) + 152LL) );
    v8 = v44;
    v4 = a4;
    v5 = a3;
  }
  *v5 = v10;
  *v4 = v12;
  *a2 = *(unsigned __int16 *)(*((_QWORD *)this + 3) + 306LL);
  --*(_DWORD *)(v8 + 16);
  v39 = (*(_DWORD *)(v8 + 12))-- == 1;
  if ( v39 )
    *(_DWORD *)(v8 + 8) = -1;
  v40 = *(_QWORD *)v8;
  --*(_DWORD *)(v40 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v40 + 8));
  return 0;
}

```

## disassembly

```asm
0x1800116d0  mov     [rsp+arg_18], r9
0x1800116d5  mov     [rsp+arg_10], r8
0x1800116da  mov     [rsp+arg_8], rdx
0x1800116df  push    rbx
0x1800116e0  push    rbp
0x1800116e1  push    rsi
0x1800116e2  push    rdi
0x1800116e3  push    r12
0x1800116e5  push    r13
0x1800116e7  push    r14
0x1800116e9  push    r15
0x1800116eb  sub     rsp, 38h
0x1800116ef  mov     r12, r9
0x1800116f2  mov     rbx, r8
0x1800116f5  mov     rsi, rdx
0x1800116f8  mov     r15, rcx
0x1800116fb  mov     rdi, [rcx+18h]
0x1800116ff  sub     rdi, 0FFFFFFFFFFFFFF80h
0x180011703  mov     [rsp+78h+var_58], rdi
0x180011708  mov     rcx, rdi
0x18001170b  call    cs:__imp_UMSEnterCSWraper
0x180011711  xor     r14d, r14d
0x180011714  cmp     [rdi+0Ch], r14d
0x180011718  jnz     short loc_180011723
0x18001171a  call    cs:__imp_GetCurrentThreadId
0x180011720  mov     [rdi+8], eax
0x180011723  mov     eax, 1
0x180011728  add     [rdi+0Ch], eax
0x18001172b  add     [rdi+10h], eax
0x18001172e  mov     [rsp+78h+arg_0], rdi
0x180011736  xor     edx, edx; perrinfo
0x180011738  xor     ecx, ecx; dwReserved
0x18001173a  call    cs:__imp_SetErrorInfo
0x180011740  test    rsi, rsi
0x180011743  jz      short loc_180011748
0x180011745  mov     [rsi], r14
0x180011748  test    rbx, rbx
0x18001174b  jz      short loc_180011750
0x18001174d  mov     [rbx], r14
0x180011750  test    r12, r12
0x180011753  jz      short loc_180011759
0x180011755  mov     [r12], r14
0x180011759  test    rsi, rsi
0x18001175c  jz      loc_180011992
0x180011762  test    rbx, rbx
0x180011765  jz      loc_180011992
0x18001176b  test    r12, r12
0x18001176e  jz      loc_180011992
0x180011774  mov     rax, [r15+18h]
0x180011778  mov     ecx, [rax+98h]
0x18001177e  lea     rcx, [rcx+rcx*4]
0x180011782  shl     rcx, 4; cb
0x180011786  call    cs:__imp_CoTaskMemAlloc
0x18001178c  mov     rbp, rax
0x18001178f  test    rax, rax
0x180011792  jnz     short loc_18001179E
0x180011794  mov     ecx, 8007000Eh
0x180011799  jmp     loc_180011997
0x18001179e  mov     rax, [r15+18h]
0x1800117a2  mov     ecx, [rax+10Ch]
0x1800117a8  add     rcx, rcx; cb
0x1800117ab  call    cs:__imp_CoTaskMemAlloc
0x1800117b1  mov     rsi, rax
0x1800117b4  mov     [rsp+78h+var_50], rax
0x1800117b9  mov     rcx, rbp; void *
0x1800117bc  test    rax, rax
0x1800117bf  jnz     short loc_1800117C9
0x1800117c1  call    cs:__imp_CoTaskMemFree
0x1800117c7  jmp     short loc_180011794
0x1800117c9  mov     rax, [r15+18h]
0x1800117cd  lea     r13, [rax+130h]
0x1800117d4  mov     eax, [rax+98h]
0x1800117da  lea     r8, [rax+rax*4]
0x1800117de  shl     r8, 4; Size
0x1800117e2  xor     edx, edx; Val
0x1800117e4  call    memset_0
0x1800117e9  mov     [rsp+78h+arg_0], rsi
0x1800117f1  mov     rax, [r15+18h]
0x1800117f5  or      esi, 0FFFFFFFFh
0x1800117f8  xor     r9d, r9d
0x1800117fb  cmp     [rax+98h], r9d
0x180011802  jbe     loc_180011951
0x180011808  mov     rdi, [rsp+78h+arg_0]
0x180011810  lea     r12d, [r9+1]
0x180011814  movzx   edx, r14w; unsigned __int16
0x180011818  mov     rcx, r13; this
0x18001181b  call    ?mdGetName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetName(ushort)
0x180011820  test    rax, rax
0x180011823  jz      short loc_180011874
0x180011825  movzx   edx, r14w; unsigned __int16
0x180011829  call    ?mdGetName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetName(ushort)
0x18001182e  mov     rcx, rax
0x180011831  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011835  inc     rax
0x180011838  cmp     [rcx+rax*2], r9w
0x18001183d  jnz     short loc_180011835
0x18001183f  lea     ebx, [rax+1]
0x180011842  add     rbx, rbx
0x180011845  movzx   edx, r14w; unsigned __int16
0x180011849  mov     rcx, r13; this
0x18001184c  call    ?mdGetName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetName(ushort)
0x180011851  mov     rdx, rax; Src
0x180011854  mov     r8, rbx; Size
0x180011857  mov     rcx, rdi; void *
0x18001185a  call    memcpy_0
0x18001185f  movzx   r11d, r14w
0x180011863  lea     rax, [r11+r11*4]
0x180011867  add     rax, rax
0x18001186a  mov     [rbp+rax*8+0], rdi
0x18001186f  add     rdi, rbx
0x180011872  jmp     short loc_180011878
0x180011874  movzx   r11d, r14w
0x180011878  lea     r10, [r11+r11*4]
0x18001187c  add     r10, r10
0x18001187f  movzx   edx, r14w; unsigned __int16
0x180011883  mov     rcx, r13; this
0x180011886  call    ?mdGetOrdinal@CMetaData@@QEAAKG@Z; CMetaData::mdGetOrdinal(ushort)
0x18001188b  mov     edx, eax
0x18001188d  mov     [rbp+r10*8+10h], rdx
0x180011892  movzx   edx, r14w; unsigned __int16
0x180011896  mov     rcx, r13; this
0x180011899  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18001189e  mov     [rbp+r10*8+18h], eax
0x1800118a3  mov     rcx, r13; this
0x1800118a6  call    ?mdGetSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetSize(ushort)
0x1800118ab  cmp     eax, esi
0x1800118ad  jnz     short loc_1800118B5
0x1800118af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800118b3  jmp     short loc_1800118BF
0x1800118b5  mov     rcx, r13; this
0x1800118b8  call    ?mdGetSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetSize(ushort)
0x1800118bd  mov     eax, eax
0x1800118bf  mov     [rbp+r10*8+20h], rax
0x1800118c4  movzx   edx, r14w; unsigned __int16
0x1800118c8  mov     rcx, r13; this
0x1800118cb  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x1800118d0  mov     [rbp+r10*8+28h], ax
0x1800118d6  mov     rcx, r13; this
0x1800118d9  call    ?mdGetScale@CMetaData@@QEAAEG@Z; CMetaData::mdGetScale(ushort)
0x1800118de  mov     [rbp+r10*8+2Bh], al
0x1800118e3  mov     rcx, r13; this
0x1800118e6  call    ?mdGetPrecision@CMetaData@@QEAAEG@Z; CMetaData::mdGetPrecision(ushort)
0x1800118eb  mov     [rbp+r10*8+2Ah], al
0x1800118f0  imul    rcx, r11, 25B0h
0x1800118f7  mov     rax, [r13+20h]
0x1800118fb  xor     r9d, r9d
0x1800118fe  cmp     [rcx+rax+870h], r9d
0x180011906  jnz     short loc_180011924
0x180011908  mov     dword ptr [rbp+r10*8+40h], 6
0x180011911  mov     rax, [r13+20h]
0x180011915  movups  xmm0, xmmword ptr [rcx+rax+860h]
0x18001191d  movdqu  xmmword ptr [rbp+r10*8+30h], xmm0
0x180011924  add     r14w, r12w
0x180011928  mov     rcx, [r15+18h]
0x18001192c  movzx   eax, r14w
0x180011930  cmp     eax, [rcx+98h]
0x180011936  jb      loc_180011814
0x18001193c  mov     rdi, [rsp+78h+var_58]
0x180011941  mov     r12, [rsp+78h+arg_18]
0x180011949  mov     rbx, [rsp+78h+arg_10]
0x180011951  mov     [rbx], rbp
0x180011954  mov     rax, [rsp+78h+var_50]
0x180011959  mov     [r12], rax
0x18001195d  mov     rax, [r15+18h]
0x180011961  movzx   ecx, word ptr [rax+132h]
0x180011968  mov     rax, [rsp+78h+arg_8]
0x180011970  mov     [rax], rcx
0x180011973  add     [rdi+10h], esi
0x180011976  add     [rdi+0Ch], esi
0x180011979  jnz     short loc_18001197E
0x18001197b  mov     [rdi+8], esi
0x18001197e  mov     rcx, [rdi]
0x180011981  dec     dword ptr [rcx+30h]
0x180011984  add     rcx, 8; lpCriticalSection
0x180011988  call    cs:__imp_LeaveCriticalSection
0x18001198e  xor     eax, eax
0x180011990  jmp     short loc_1800119C0
0x180011992  mov     ecx, 80070057h; int
0x180011997  xor     edx, edx; unsigned int
0x180011999  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18001199e  mov     ebx, eax
0x1800119a0  or      esi, 0FFFFFFFFh
0x1800119a3  add     [rdi+10h], esi
0x1800119a6  add     [rdi+0Ch], esi
0x1800119a9  jnz     short loc_1800119AE
0x1800119ab  mov     [rdi+8], esi
0x1800119ae  mov     rcx, [rdi]
0x1800119b1  dec     dword ptr [rcx+30h]
0x1800119b4  add     rcx, 8; lpCriticalSection
0x1800119b8  call    cs:__imp_LeaveCriticalSection
0x1800119be  mov     eax, ebx
0x1800119c0  add     rsp, 38h
0x1800119c4  pop     r15
0x1800119c6  pop     r14
0x1800119c8  pop     r13
0x1800119ca  pop     r12
0x1800119cc  pop     rdi
0x1800119cd  pop     rsi
0x1800119ce  pop     rbp
0x1800119cf  pop     rbx
0x1800119d0  retn
```
