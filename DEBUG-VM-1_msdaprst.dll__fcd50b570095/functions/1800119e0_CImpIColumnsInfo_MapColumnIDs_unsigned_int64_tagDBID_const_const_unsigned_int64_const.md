# CImpIColumnsInfo::MapColumnIDs(unsigned __int64,tagDBID const * const,unsigned __int64 * const)

- ea: `0x1800119e0`
- end: `0x180011c4e`
- name: `?MapColumnIDs@CImpIColumnsInfo@@UEAAJ_KQEBUtagDBID@@QEA_K@Z`
- size: `622`
- prototype: `__int64 __fastcall(CImpIColumnsInfo *__hidden this, unsigned __int64, const struct tagDBID *const, unsigned __int64 *const)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800022f8`
- `0x1800119e0`
- `0x180015fb4`
- `0x18001a6c8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180011a25`
- `KERNEL32!GetCurrentThreadId` at `0x180011a25`
- `KERNEL32!LeaveCriticalSection` at `0x180011a5e`
- `KERNEL32!LeaveCriticalSection` at `0x180011a95`
- `KERNEL32!LeaveCriticalSection` at `0x180011c2e`
- `KERNEL32!LeaveCriticalSection` at `0x180011a5e`
- `KERNEL32!LeaveCriticalSection` at `0x180011a95`
- `KERNEL32!LeaveCriticalSection` at `0x180011c2e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180011a3c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180011a3c`
- `MSDART!UMSEnterCSWraper` at `0x180011a15`
- `MSDART!UMSEnterCSWraper` at `0x180011a15`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIColumnsInfo::MapColumnIDs(
        CImpIColumnsInfo *this,
        unsigned __int64 a2,
        const struct tagDBID *const a3,
        unsigned __int64 *const a4)
{
  __int64 v7; // rbx
  DWORD *v8; // rdi
  bool v9; // zf
  __int64 v10; // rcx
  unsigned int v12; // esi
  __int64 v13; // rcx
  unsigned int v14; // esi
  unsigned int v15; // ebp
  __int64 v16; // r15
  __int64 v17; // rcx
  unsigned __int64 ulPropid; // rdx
  char *v19; // rax
  unsigned int BidObjectID; // eax
  unsigned int v21; // eax
  wchar_t *v22; // r8
  char *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx

  v7 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v7);
  v8 = (DWORD *)(v7 + 8);
  if ( !*(_DWORD *)(v7 + 12) )
    *v8 = GetCurrentThreadId();
  ++*(_DWORD *)(v7 + 12);
  ++*(_DWORD *)(v7 + 16);
  SetErrorInfo(0, 0);
  if ( !a2 )
  {
    --*(_DWORD *)(v7 + 16);
    v9 = (*(_DWORD *)(v7 + 12))-- == 1;
    if ( v9 )
      *v8 = -1;
    v10 = *(_QWORD *)v7;
    --*(_DWORD *)(v10 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 8));
    return 0;
  }
  if ( a3 && a4 )
  {
    v14 = 0;
    v15 = 0;
    v16 = 0;
    do
    {
      v17 = (unsigned int)v16;
      ulPropid = a3[v17].uName.ulPropid;
      if ( !(_DWORD)ulPropid
        || (unsigned int)ulPropid > *(_DWORD *)(*((_QWORD *)this + 3) + 152LL)
        || a3[v17].eKind != 1 )
      {
        goto LABEL_20;
      }
      v19 = (char *)a3[v17].uGuid.pguid - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v19 )
        v19 = (char *)(*((_QWORD *)&a3[v17].uGuid.pguid + 1) - *(_QWORD *)GUID_NULL.Data4);
      if ( !v19 )
      {
        a4[v16] = ulPropid;
      }
      else
      {
LABEL_20:
        a4[v16] = -1;
        ++v14;
        if ( (bidGblFlags & 2) != 0 && off_1800488F0[0] )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
          bidTraceW(off_180048248[0], 194560, off_1800488F0[0], BidObjectID, v16);
        }
      }
      v16 = (unsigned int)(v16 + 1);
    }
    while ( (unsigned int)v16 < a2 );
    if ( !v14 )
      goto LABEL_33;
    if ( v14 >= a2 )
    {
      v15 = -2147217887;
      if ( (bidGblFlags & 2) == 0 || !off_1800488E0[0] )
        goto LABEL_33;
      v21 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
      v22 = off_1800488E0[0];
      v23 = off_180048238[0];
      v24 = 212992;
    }
    else
    {
      v15 = 265946;
      if ( (bidGblFlags & 2) == 0 || !off_1800488E8[0] )
        goto LABEL_33;
      v21 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
      v22 = off_1800488E8[0];
      v23 = off_180048240[0];
      v24 = 206848;
    }
    bidTraceW(v23, v24, v22, v21, v14);
LABEL_33:
    --*(_DWORD *)(v7 + 16);
    v9 = (*(_DWORD *)(v7 + 12))-- == 1;
    if ( v9 )
      *v8 = -1;
    v25 = *(_QWORD *)v7;
    --*(_DWORD *)(v25 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v25 + 8));
    return v15;
  }
  v12 = Exit(-2147024809, 0);
  --*(_DWORD *)(v7 + 16);
  v9 = (*(_DWORD *)(v7 + 12))-- == 1;
  if ( v9 )
    *v8 = -1;
  v13 = *(_QWORD *)v7;
  --*(_DWORD *)(v13 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
  return v12;
}

```

## disassembly

```asm
0x1800119e0  mov     [rsp+arg_10], rbx
0x1800119e5  mov     [rsp+arg_0], rcx
0x1800119ea  push    rbp
0x1800119eb  push    rsi
0x1800119ec  push    rdi
0x1800119ed  push    r12
0x1800119ef  push    r13
0x1800119f1  push    r14
0x1800119f3  push    r15
0x1800119f5  sub     rsp, 40h
0x1800119f9  mov     r13, r9
0x1800119fc  mov     r14, r8
0x1800119ff  mov     r12, rdx
0x180011a02  mov     rbx, [rcx+18h]
0x180011a06  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180011a0a  mov     [rsp+78h+arg_8], rbx
0x180011a12  mov     rcx, rbx
0x180011a15  call    cs:__imp_UMSEnterCSWraper
0x180011a1b  lea     rdi, [rbx+8]
0x180011a1f  cmp     dword ptr [rbx+0Ch], 0
0x180011a23  jnz     short loc_180011A2D
0x180011a25  call    cs:__imp_GetCurrentThreadId
0x180011a2b  mov     [rdi], eax
0x180011a2d  inc     dword ptr [rbx+0Ch]
0x180011a30  inc     dword ptr [rbx+10h]
0x180011a33  mov     [rsp+78h+var_48], rbx
0x180011a38  xor     edx, edx; perrinfo
0x180011a3a  xor     ecx, ecx; dwReserved
0x180011a3c  call    cs:__imp_SetErrorInfo
0x180011a42  test    r12, r12
0x180011a45  jnz     short loc_180011A6B
0x180011a47  or      edx, 0FFFFFFFFh
0x180011a4a  add     [rbx+10h], edx
0x180011a4d  add     [rbx+0Ch], edx
0x180011a50  jnz     short loc_180011A54
0x180011a52  mov     [rdi], edx
0x180011a54  mov     rcx, [rbx]
0x180011a57  dec     dword ptr [rcx+30h]
0x180011a5a  add     rcx, 8; lpCriticalSection
0x180011a5e  call    cs:__imp_LeaveCriticalSection
0x180011a64  xor     eax, eax
0x180011a66  jmp     loc_180011C36
0x180011a6b  test    r14, r14
0x180011a6e  jnz     short loc_180011AA2
0x180011a70  xor     edx, edx; unsigned int
0x180011a72  mov     ecx, 80070057h; int
0x180011a77  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180011a7c  mov     esi, eax
0x180011a7e  or      edx, 0FFFFFFFFh
0x180011a81  add     [rbx+10h], edx
0x180011a84  add     [rbx+0Ch], edx
0x180011a87  jnz     short loc_180011A8B
0x180011a89  mov     [rdi], edx
0x180011a8b  mov     rcx, [rbx]
0x180011a8e  dec     dword ptr [rcx+30h]
0x180011a91  add     rcx, 8; lpCriticalSection
0x180011a95  call    cs:__imp_LeaveCriticalSection
0x180011a9b  mov     eax, esi
0x180011a9d  jmp     loc_180011C36
0x180011aa2  test    r13, r13
0x180011aa5  jz      short loc_180011A70
0x180011aa7  xor     esi, esi
0x180011aa9  xor     ebp, ebp
0x180011aab  xor     r15d, r15d
0x180011aae  test    r12, r12
0x180011ab1  jz      loc_180011C17
0x180011ab7  mov     rbx, [rsp+78h+arg_0]
0x180011abf  mov     ecx, r15d
0x180011ac2  shl     rcx, 5
0x180011ac6  mov     edx, [rcx+r14+18h]
0x180011acb  cmp     edx, 1
0x180011ace  jb      short loc_180011B09
0x180011ad0  mov     rax, [rbx+18h]
0x180011ad4  cmp     edx, [rax+98h]
0x180011ada  ja      short loc_180011B09
0x180011adc  cmp     dword ptr [rcx+r14+10h], 1
0x180011ae2  jnz     short loc_180011B09
0x180011ae4  mov     rax, [rcx+r14]
0x180011ae8  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180011aef  jnz     short loc_180011AFD
0x180011af1  mov     rax, [rcx+r14+8]
0x180011af6  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180011afd  test    rax, rax
0x180011b00  jnz     short loc_180011B09
0x180011b02  mov     [r13+r15*8+0], rdx
0x180011b07  jmp     short loc_180011B56
0x180011b09  mov     qword ptr [r13+r15*8+0], 0FFFFFFFFFFFFFFFFh
0x180011b12  inc     esi
0x180011b14  test    byte ptr cs:_bidGblFlags, 2
0x180011b1b  jz      short loc_180011B56
0x180011b1d  mov     rax, cs:off_1800488F0; "<CImpIColumnsInfo::MapColumnIDs|ERR|PER"...
0x180011b24  test    rax, rax
0x180011b27  jz      short loc_180011B56
0x180011b29  mov     rcx, [rbx+18h]
0x180011b2d  add     rcx, 70h ; 'p'; this
0x180011b31  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180011b36  mov     r8, cs:off_1800488F0; "<CImpIColumnsInfo::MapColumnIDs|ERR|PER"...
0x180011b3d  mov     rcx, cs:off_180048248; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180011b44  mov     [rsp+78h+var_58], r15d
0x180011b49  mov     r9d, eax
0x180011b4c  mov     edx, 2F800h
0x180011b51  call    _bidTraceW
0x180011b56  inc     r15d
0x180011b59  mov     eax, r15d
0x180011b5c  cmp     rax, r12
0x180011b5f  jb      loc_180011ABF
0x180011b65  test    esi, esi
0x180011b67  mov     rbx, [rsp+78h+arg_8]
0x180011b6f  jz      loc_180011C17
0x180011b75  mov     eax, esi
0x180011b77  cmp     rax, r12
0x180011b7a  jnb     short loc_180011BC4
0x180011b7c  mov     ebp, 40EDAh
0x180011b81  test    byte ptr cs:_bidGblFlags, 2
0x180011b88  jz      loc_180011C17
0x180011b8e  mov     rax, cs:off_1800488E8; "<CImpIColumnsInfo::MapColumnIDs|ERR|PER"...
0x180011b95  test    rax, rax
0x180011b98  jz      short loc_180011C17
0x180011b9a  mov     rcx, [rsp+78h+arg_0]
0x180011ba2  mov     rcx, [rcx+18h]
0x180011ba6  add     rcx, 70h ; 'p'; this
0x180011baa  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180011baf  mov     r8, cs:off_1800488E8; "<CImpIColumnsInfo::MapColumnIDs|ERR|PER"...
0x180011bb6  mov     rcx, cs:off_180048240; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180011bbd  mov     edx, 32800h
0x180011bc2  jmp     short loc_180011C06
0x180011bc4  mov     ebp, 80040E21h
0x180011bc9  test    byte ptr cs:_bidGblFlags, 2
0x180011bd0  jz      short loc_180011C17
0x180011bd2  mov     rax, cs:off_1800488E0; "<CImpIColumnsInfo::MapColumnIDs|ERR|PER"...
0x180011bd9  test    rax, rax
0x180011bdc  jz      short loc_180011C17
0x180011bde  mov     rcx, [rsp+78h+arg_0]
0x180011be6  mov     rcx, [rcx+18h]
0x180011bea  add     rcx, 70h ; 'p'; this
0x180011bee  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180011bf3  mov     r8, cs:off_1800488E0; "<CImpIColumnsInfo::MapColumnIDs|ERR|PER"...
0x180011bfa  mov     rcx, cs:off_180048238; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180011c01  mov     edx, 34000h
0x180011c06  mov     [rsp+78h+var_50], ebp
0x180011c0a  mov     [rsp+78h+var_58], esi
0x180011c0e  mov     r9d, eax
0x180011c11  call    _bidTraceW
0x180011c16  nop
0x180011c17  or      edx, 0FFFFFFFFh
0x180011c1a  add     [rbx+10h], edx
0x180011c1d  add     [rbx+0Ch], edx
0x180011c20  jnz     short loc_180011C24
0x180011c22  mov     [rdi], edx
0x180011c24  mov     rcx, [rbx]
0x180011c27  dec     dword ptr [rcx+30h]
0x180011c2a  add     rcx, 8; lpCriticalSection
0x180011c2e  call    cs:__imp_LeaveCriticalSection
0x180011c34  mov     eax, ebp
0x180011c36  mov     rbx, [rsp+78h+arg_10]
0x180011c3e  add     rsp, 40h
0x180011c42  pop     r15
0x180011c44  pop     r14
0x180011c46  pop     r13
0x180011c48  pop     r12
0x180011c4a  pop     rdi
0x180011c4b  pop     rsi
0x180011c4c  pop     rbp
0x180011c4d  retn
```
