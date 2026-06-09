# CImpIAccessor::CreateAccessor(ulong,unsigned __int64,tagDBBINDING const * const,unsigned __int64,unsigned __int64 *,ulong * const)

- ea: `0x180001f40`
- end: `0x1800022f2`
- name: `?CreateAccessor@CImpIAccessor@@UEAAJK_KQEBUtagDBBINDING@@0PEA_KQEAK@Z`
- size: `946`
- prototype: `int(CImpIAccessor *__hidden this, unsigned int, unsigned __int64, const struct tagDBBINDING *const, unsigned __int64, unsigned __int64 *, unsigned int *const)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180001d94`
- `0x180001dd8`
- `0x180001f40`
- `0x1800022f8`
- `0x1800041f8`
- `0x180015fb4`
- `0x18001a6c8`
- `0x18002e012`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180001f7e`
- `KERNEL32!GetCurrentThreadId` at `0x180001f7e`
- `KERNEL32!LeaveCriticalSection` at `0x180002019`
- `KERNEL32!LeaveCriticalSection` at `0x180002296`
- `KERNEL32!LeaveCriticalSection` at `0x1800022d2`
- `KERNEL32!LeaveCriticalSection` at `0x180002019`
- `KERNEL32!LeaveCriticalSection` at `0x180002296`
- `KERNEL32!LeaveCriticalSection` at `0x1800022d2`
- `KERNEL32!VirtualAlloc` at `0x180002220`
- `KERNEL32!VirtualAlloc` at `0x180002220`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180001f9a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180001f9a`
- `MSDART!UMSEnterCSWraper` at `0x180001f6e`
- `MSDART!UMSEnterCSWraper` at `0x180001f6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIAccessor::CreateAccessor(
        CImpIAccessor *this,
        int a2,
        unsigned __int64 a3,
        const struct tagDBBINDING *const a4,
        unsigned __int64 a5,
        unsigned __int64 *a6,
        unsigned int *const a7)
{
  char v9; // bl
  __int64 v11; // rdi
  DWORD *v12; // rsi
  unsigned int v13; // edx
  unsigned __int64 *v14; // r13
  unsigned int v15; // ebx
  bool v16; // zf
  __int64 v17; // rcx
  __int64 i; // rbx
  __int64 v20; // r8
  unsigned int iOrdinal; // eax
  __int64 v22; // r10
  unsigned __int16 Type; // ax
  CMetaData *v24; // r9
  unsigned __int16 v25; // ax
  __int64 v26; // r10
  unsigned int v27; // eax
  unsigned int BidObjectID; // eax
  wchar_t *v29; // r8
  char *v30; // rcx
  __int64 v31; // rdx
  unsigned int v32; // edx
  int v33; // ecx
  unsigned int v34; // r15d
  unsigned __int8 *v35; // r14
  unsigned int *v36; // rbx
  unsigned int v37; // ebp
  __int64 v38; // rcx
  SIZE_T v39; // rdx
  unsigned __int64 v40; // rbx
  __int64 v41; // rcx
  __int64 v42; // rcx
  unsigned __int8 *Src; // [rsp+80h] [rbp+8h] BYREF
  int v44; // [rsp+88h] [rbp+10h]
  __int64 v45; // [rsp+90h] [rbp+18h]

  v44 = a2;
  v9 = a2;
  v11 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v11);
  v12 = (DWORD *)(v11 + 8);
  if ( !*(_DWORD *)(v11 + 12) )
    *v12 = GetCurrentThreadId();
  ++*(_DWORD *)(v11 + 12);
  ++*(_DWORD *)(v11 + 16);
  SetErrorInfo(0, 0);
  if ( a3 && !a4 || (v14 = a6) == 0 || (*a6 = 0, (v9 & 5) != 0) )
  {
    v33 = -2147024809;
LABEL_45:
    v32 = 0;
LABEL_46:
    v15 = Exit(v33, v32);
    --*(_DWORD *)(v11 + 16);
    v16 = (*(_DWORD *)(v11 + 12))-- == 1;
    goto LABEL_47;
  }
  if ( (v9 & 2) == 0 )
  {
    v15 = Exit(-2147024809, 0);
    --*(_DWORD *)(v11 + 16);
    v16 = (*(_DWORD *)(v11 + 12))-- == 1;
LABEL_47:
    if ( v16 )
      *v12 = -1;
    v42 = *(_QWORD *)v11;
    --*(_DWORD *)(v42 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v42 + 8));
    return v15;
  }
  v45 = (unsigned int)a3;
  if ( (unsigned int)a3 != a3 )
  {
    --*(_DWORD *)(v11 + 16);
    v16 = (*(_DWORD *)(v11 + 12))-- == 1;
    if ( v16 )
      *v12 = -1;
    v17 = *(_QWORD *)v11;
    --*(_DWORD *)(v17 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 8));
    return 2147500037LL;
  }
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
  {
    v20 = (unsigned int)i;
    iOrdinal = a4[v20].iOrdinal;
    if ( !iOrdinal || (v22 = *((_QWORD *)this + 3), iOrdinal > *(_DWORD *)(v22 + 152)) )
    {
      if ( (bidGblFlags & 2) != 0 && off_1800483B8[0] )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
        v29 = off_1800483B8[0];
        v30 = off_1800481B0[0];
        v31 = 143360;
LABEL_32:
        bidTraceW(v30, v31, v29, BidObjectID, -2147217887);
      }
LABEL_33:
      v32 = 114;
      v33 = -2147217887;
      goto LABEL_46;
    }
    if ( (a4[v20].dwPart & 7) == 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1800483B0[0] )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
        v29 = off_1800483B0[0];
        v30 = off_1800481A8[0];
        v31 = 158720;
        goto LABEL_32;
      }
      goto LABEL_33;
    }
    LOWORD(Src) = a4[v20].wType;
    Type = CMetaData::mdGetType((CMetaData *)(v22 + 304), iOrdinal - 1);
    if ( (_WORD)Src != Type )
    {
      v25 = CMetaData::mdGetType(v24, v13);
      if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v26 + 64LL))(
             v26,
             v25,
             (unsigned __int16)Src) )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800483A8[0] )
        {
          v27 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
          bidTraceW(off_1800481A0[0], 181248, off_1800483A8[0], v27, -2147217887);
        }
        if ( a7 )
          a7[i] = 2;
        goto LABEL_33;
      }
    }
  }
  v34 = 88 * v45;
  v35 = MMMAlloc(88 * (int)v45 + 16, v13);
  Src = v35;
  if ( !v35 )
  {
LABEL_35:
    v33 = -2147024882;
    goto LABEL_45;
  }
  v36 = *(unsigned int **)(*((_QWORD *)this + 3) + 192LL);
  v37 = v36[1] * *v36;
  v38 = v36[3];
  if ( v37 + *v36 > (unsigned int)v38 )
  {
    v39 = v36[4];
    if ( (int)v39 + (int)v38 > v36[2] || !VirtualAlloc((LPVOID)(*((_QWORD *)v36 + 3) + v38), v39, 0x1000u, 4u) )
    {
      MMMFree(v35);
      goto LABEL_35;
    }
    v36[3] += v36[4];
  }
  memcpy_0((void *)(*((_QWORD *)v36 + 3) + v37), &Src, *v36);
  v40 = ++v36[1];
  *(_DWORD *)v35 = v44;
  *((_DWORD *)v35 + 2) = v45;
  *((_DWORD *)v35 + 1) = 1;
  memcpy_0(v35 + 16, a4, v34);
  *v14 = v40;
  --*(_DWORD *)(v11 + 16);
  v16 = (*(_DWORD *)(v11 + 12))-- == 1;
  if ( v16 )
    *v12 = -1;
  v41 = *(_QWORD *)v11;
  --*(_DWORD *)(v41 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v41 + 8));
  return 0;
}

```

## disassembly

```asm
0x180001f40  mov     [rsp+arg_18], rbx
0x180001f45  mov     [rsp+arg_8], edx
0x180001f49  push    rbp
0x180001f4a  push    rsi
0x180001f4b  push    rdi
0x180001f4c  push    r12
0x180001f4e  push    r13
0x180001f50  push    r14
0x180001f52  push    r15
0x180001f54  sub     rsp, 40h
0x180001f58  mov     r12, r9
0x180001f5b  mov     r14, r8
0x180001f5e  mov     ebx, edx
0x180001f60  mov     rbp, rcx
0x180001f63  mov     rdi, [rcx+18h]
0x180001f67  sub     rdi, 0FFFFFFFFFFFFFF80h
0x180001f6b  mov     rcx, rdi
0x180001f6e  call    cs:__imp_UMSEnterCSWraper
0x180001f74  lea     rsi, [rdi+8]
0x180001f78  cmp     dword ptr [rdi+0Ch], 0
0x180001f7c  jnz     short loc_180001F86
0x180001f7e  call    cs:__imp_GetCurrentThreadId
0x180001f84  mov     [rsi], eax
0x180001f86  mov     eax, 1
0x180001f8b  add     [rdi+0Ch], eax
0x180001f8e  add     [rdi+10h], eax
0x180001f91  mov     [rsp+78h+var_48], rdi
0x180001f96  xor     edx, edx; perrinfo
0x180001f98  xor     ecx, ecx; dwReserved
0x180001f9a  call    cs:__imp_SetErrorInfo
0x180001fa0  test    r14, r14
0x180001fa3  jz      short loc_180001FAE
0x180001fa5  test    r12, r12
0x180001fa8  jz      loc_1800022AD
0x180001fae  mov     r13, [rsp+78h+arg_28]
0x180001fb6  test    r13, r13
0x180001fb9  jz      loc_1800022AD
0x180001fbf  mov     qword ptr [r13+0], 0
0x180001fc7  test    bl, 5
0x180001fca  jnz     loc_1800022AD
0x180001fd0  test    bl, 2
0x180001fd3  jnz     short loc_180001FF2
0x180001fd5  xor     edx, edx; unsigned int
0x180001fd7  mov     ecx, 80070057h; int
0x180001fdc  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180001fe1  mov     ebx, eax
0x180001fe3  or      edx, 0FFFFFFFFh
0x180001fe6  add     [rdi+10h], edx
0x180001fe9  sub     dword ptr [rdi+0Ch], 1
0x180001fed  jmp     loc_1800022C4
0x180001ff2  mov     eax, r14d
0x180001ff5  mov     [rsp+78h+arg_10], rax
0x180001ffd  cmp     rax, r14
0x180002000  jz      short loc_180002029
0x180002002  or      edx, 0FFFFFFFFh
0x180002005  add     [rdi+10h], edx
0x180002008  add     [rdi+0Ch], edx
0x18000200b  jnz     short loc_18000200F
0x18000200d  mov     [rsi], edx
0x18000200f  mov     rcx, [rdi]
0x180002012  dec     dword ptr [rcx+30h]
0x180002015  add     rcx, 8; lpCriticalSection
0x180002019  call    cs:__imp_LeaveCriticalSection
0x18000201f  mov     eax, 80004005h
0x180002024  jmp     loc_1800022DA
0x180002029  xor     ebx, ebx
0x18000202b  mov     r15d, ebx
0x18000202e  cmp     r15, r14
0x180002031  jnb     loc_1800021B9
0x180002037  imul    r8, r15, 58h ; 'X'
0x18000203b  mov     eax, [r8+r12]
0x18000203f  test    eax, eax
0x180002041  jz      loc_180002161
0x180002047  mov     r10, [rbp+18h]
0x18000204b  cmp     eax, [r10+98h]
0x180002052  ja      loc_180002161
0x180002058  test    byte ptr [r8+r12+38h], 7
0x18000205e  jz      loc_18000212A
0x180002064  lea     r9, [r10+130h]
0x18000206b  lea     r11d, [rax-1]
0x18000206f  movzx   eax, word ptr [r8+r12+54h]
0x180002075  mov     word ptr [rsp+78h+Src], ax
0x18000207d  movzx   edx, r11w; unsigned __int16
0x180002081  mov     rcx, r9; this
0x180002084  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x180002089  cmp     word ptr [rsp+78h+Src], ax
0x180002091  jz      short loc_1800020BD
0x180002093  mov     rcx, r9; this
0x180002096  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x18000209b  mov     rdx, [r10]
0x18000209e  mov     r9, [rdx+40h]
0x1800020a2  movzx   r8d, word ptr [rsp+78h+Src]
0x1800020ab  movzx   edx, ax
0x1800020ae  mov     rcx, r10
0x1800020b1  mov     rax, r9
0x1800020b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020b9  test    eax, eax
0x1800020bb  jnz     short loc_1800020C4
0x1800020bd  inc     ebx
0x1800020bf  jmp     loc_18000202B
0x1800020c4  test    byte ptr cs:_bidGblFlags, 2
0x1800020cb  jz      short loc_18000210D
0x1800020cd  mov     rax, cs:off_1800483A8; "<CImpIAccessor::CreateAccessor|ERR|PERS"...
0x1800020d4  test    rax, rax
0x1800020d7  jz      short loc_18000210D
0x1800020d9  mov     rcx, [rbp+18h]
0x1800020dd  add     rcx, 70h ; 'p'; this
0x1800020e1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800020e6  mov     r8, cs:off_1800483A8; "<CImpIAccessor::CreateAccessor|ERR|PERS"...
0x1800020ed  mov     rcx, cs:off_1800481A0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800020f4  mov     [rsp+78h+var_50], ebx
0x1800020f8  mov     [rsp+78h+var_58], 80040E21h
0x180002100  mov     r9d, eax
0x180002103  mov     edx, 2C400h
0x180002108  call    _bidTraceW
0x18000210d  mov     rax, [rsp+78h+arg_30]
0x180002115  test    rax, rax
0x180002118  jz      loc_1800021AA
0x18000211e  mov     dword ptr [rax+rbx*4], 2
0x180002125  jmp     loc_1800021AA
0x18000212a  test    byte ptr cs:_bidGblFlags, 2
0x180002131  jz      short loc_1800021AA
0x180002133  mov     rax, cs:off_1800483B0; "<CImpIAccessor::CreateAccessor|ERR|PERS"...
0x18000213a  test    rax, rax
0x18000213d  jz      short loc_1800021AA
0x18000213f  mov     rcx, [rbp+18h]
0x180002143  add     rcx, 70h ; 'p'; this
0x180002147  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000214c  mov     r8, cs:off_1800483B0; "<CImpIAccessor::CreateAccessor|ERR|PERS"...
0x180002153  mov     rcx, cs:off_1800481A8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000215a  mov     edx, 26C00h
0x18000215f  jmp     short loc_180002196
0x180002161  test    byte ptr cs:_bidGblFlags, 2
0x180002168  jz      short loc_1800021AA
0x18000216a  mov     rax, cs:off_1800483B8; "<CImpIAccessor::CreateAccessor|ERR|PERS"...
0x180002171  test    rax, rax
0x180002174  jz      short loc_1800021AA
0x180002176  mov     rcx, [rbp+18h]
0x18000217a  add     rcx, 70h ; 'p'; this
0x18000217e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180002183  mov     r8, cs:off_1800483B8; "<CImpIAccessor::CreateAccessor|ERR|PERS"...
0x18000218a  mov     rcx, cs:off_1800481B0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180002191  mov     edx, 23000h
0x180002196  mov     [rsp+78h+var_50], ebx
0x18000219a  mov     [rsp+78h+var_58], 80040E21h
0x1800021a2  mov     r9d, eax
0x1800021a5  call    _bidTraceW
0x1800021aa  mov     edx, 72h ; 'r'
0x1800021af  mov     ecx, 80040E21h
0x1800021b4  jmp     loc_1800022B4
0x1800021b9  imul    r15d, dword ptr [rsp+78h+arg_10], 58h ; 'X'
0x1800021c2  lea     ecx, [r15+10h]; unsigned int
0x1800021c6  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800021cb  mov     r14, rax
0x1800021ce  mov     [rsp+78h+Src], rax
0x1800021d6  test    rax, rax
0x1800021d9  jnz     short loc_1800021E5
0x1800021db  mov     ecx, 8007000Eh
0x1800021e0  jmp     loc_1800022B2
0x1800021e5  mov     rax, [rbp+18h]
0x1800021e9  mov     rbx, [rax+0C0h]
0x1800021f0  mov     eax, [rbx]
0x1800021f2  mov     ebp, eax
0x1800021f4  imul    ebp, [rbx+4]
0x1800021f8  mov     ecx, [rbx+0Ch]
0x1800021fb  add     eax, ebp
0x1800021fd  cmp     eax, ecx
0x1800021ff  jbe     short loc_180002231
0x180002201  mov     edx, [rbx+10h]; dwSize
0x180002204  lea     eax, [rdx+rcx]
0x180002207  cmp     eax, [rbx+8]
0x18000220a  ja      loc_1800022A0
0x180002210  add     rcx, [rbx+18h]; lpAddress
0x180002214  mov     r9d, 4; flProtect
0x18000221a  mov     r8d, 1000h; flAllocationType
0x180002220  call    cs:__imp_VirtualAlloc
0x180002226  test    rax, rax
0x180002229  jz      short loc_1800022A0
0x18000222b  mov     eax, [rbx+10h]
0x18000222e  add     [rbx+0Ch], eax
0x180002231  mov     r8d, [rbx]; Size
0x180002234  mov     ecx, ebp
0x180002236  add     rcx, [rbx+18h]; void *
0x18000223a  lea     rdx, [rsp+78h+Src]; Src
0x180002242  call    memcpy_0
0x180002247  mov     ecx, 1
0x18000224c  add     [rbx+4], ecx
0x18000224f  mov     ebx, [rbx+4]
0x180002252  mov     eax, [rsp+78h+arg_8]
0x180002259  mov     [r14], eax
0x18000225c  mov     rax, [rsp+78h+arg_10]
0x180002264  mov     [r14+8], eax
0x180002268  mov     [r14+4], ecx
0x18000226c  mov     r8d, r15d; Size
0x18000226f  lea     rcx, [r14+10h]; void *
0x180002273  mov     rdx, r12; Src
0x180002276  call    memcpy_0
0x18000227b  mov     [r13+0], rbx
0x18000227f  or      edx, 0FFFFFFFFh
0x180002282  add     [rdi+10h], edx
0x180002285  add     [rdi+0Ch], edx
0x180002288  jnz     short loc_18000228C
0x18000228a  mov     [rsi], edx
0x18000228c  mov     rcx, [rdi]
0x18000228f  dec     dword ptr [rcx+30h]
0x180002292  add     rcx, 8; lpCriticalSection
0x180002296  call    cs:__imp_LeaveCriticalSection
0x18000229c  xor     eax, eax
0x18000229e  jmp     short loc_1800022DA
0x1800022a0  mov     rcx, r14; unsigned __int8 *
0x1800022a3  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x1800022a8  jmp     loc_1800021DB
0x1800022ad  mov     ecx, 80070057h; int
0x1800022b2  xor     edx, edx; unsigned int
0x1800022b4  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800022b9  mov     ebx, eax
0x1800022bb  or      edx, 0FFFFFFFFh
0x1800022be  add     [rdi+10h], edx
0x1800022c1  add     [rdi+0Ch], edx
0x1800022c4  jnz     short loc_1800022C8
0x1800022c6  mov     [rsi], edx
0x1800022c8  mov     rcx, [rdi]
0x1800022cb  dec     dword ptr [rcx+30h]
0x1800022ce  add     rcx, 8; lpCriticalSection
0x1800022d2  call    cs:__imp_LeaveCriticalSection
0x1800022d8  mov     eax, ebx
0x1800022da  mov     rbx, [rsp+78h+arg_18]
0x1800022e2  add     rsp, 40h
0x1800022e6  pop     r15
0x1800022e8  pop     r14
0x1800022ea  pop     r13
0x1800022ec  pop     r12
0x1800022ee  pop     rdi
0x1800022ef  pop     rsi
0x1800022f0  pop     rbp
0x1800022f1  retn
```
