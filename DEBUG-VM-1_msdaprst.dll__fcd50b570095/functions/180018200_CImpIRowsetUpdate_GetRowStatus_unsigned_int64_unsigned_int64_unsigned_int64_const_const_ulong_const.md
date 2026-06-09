# CImpIRowsetUpdate::GetRowStatus(unsigned __int64,unsigned __int64,unsigned __int64 const * const,ulong * const)

- ea: `0x180018200`
- end: `0x180018450`
- name: `?GetRowStatus@CImpIRowsetUpdate@@UEAAJ_K0QEB_KQEAK@Z`
- size: `592`
- prototype: `__int64 __fastcall(CImpIRowsetUpdate *__hidden this, unsigned __int64, unsigned __int64, const unsigned __int64 *const, unsigned int *const)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1800022f8`
- `0x180011484`
- `0x180015fb4`
- `0x180018200`
- `0x18001a6c8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180018245`
- `KERNEL32!GetCurrentThreadId` at `0x180018245`
- `KERNEL32!LeaveCriticalSection` at `0x18001827e`
- `KERNEL32!LeaveCriticalSection` at `0x180018430`
- `KERNEL32!LeaveCriticalSection` at `0x18001827e`
- `KERNEL32!LeaveCriticalSection` at `0x180018430`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001825c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001825c`
- `MSDART!UMSEnterCSWraper` at `0x180018235`
- `MSDART!UMSEnterCSWraper` at `0x180018235`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIRowsetUpdate::GetRowStatus(
        CImpIRowsetUpdate *this,
        __int64 a2,
        unsigned __int64 a3,
        const unsigned __int64 *const a4,
        unsigned int *const a5)
{
  __int64 v8; // rbx
  DWORD *v9; // rdi
  bool v10; // zf
  __int64 v11; // rcx
  unsigned int v13; // esi
  int v14; // r12d
  __int64 v15; // rbp
  int v16; // r9d
  __int64 v17; // r10
  int v18; // r11d
  unsigned int BidObjectID; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  wchar_t *v22; // r8
  char *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // [rsp+80h] [rbp+8h]

  v8 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v8);
  v9 = (DWORD *)(v8 + 8);
  if ( !*(_DWORD *)(v8 + 12) )
    *v9 = GetCurrentThreadId();
  ++*(_DWORD *)(v8 + 12);
  ++*(_DWORD *)(v8 + 16);
  SetErrorInfo(0, 0);
  if ( !a3 )
  {
    --*(_DWORD *)(v8 + 16);
    v10 = (*(_DWORD *)(v8 + 12))-- == 1;
    if ( v10 )
      *v9 = -1;
    v11 = *(_QWORD *)v8;
    --*(_DWORD *)(v11 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 8));
    return 0;
  }
  if ( a5 && a4 )
  {
    v13 = 0;
    v14 = 0;
    v26 = 0;
    v15 = 0;
    do
    {
      if ( (unsigned int)CBitArray::IsSlotSet(*(CBitArray **)(*((_QWORD *)this + 3) + 208LL), a4[v15]) )
      {
        v14 = 1;
        if ( (bidGblFlags & 2) != 0 && off_180048B30[0] )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
          bidTraceW(off_1800482A8[0], 166912, off_180048B30[0], BidObjectID, v15);
          v18 = v26;
        }
        v20 = 16;
      }
      else
      {
        v18 = 1;
        v26 = 1;
        v20 = *(_DWORD *)((unsigned int)(*(_DWORD *)(v17 + 220) * v16) + *(_QWORD *)(v17 + 224) + 28LL);
      }
      a5[v15] = v20;
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (unsigned int)v15 < a3 );
    if ( !v14 )
      goto LABEL_27;
    if ( v18 )
    {
      v13 = 265946;
      if ( (bidGblFlags & 2) == 0 || !off_180048B28[0] )
        goto LABEL_27;
      v21 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
      v22 = off_180048B28[0];
      v23 = off_1800482A0[0];
      v24 = 209920;
    }
    else
    {
      v13 = -2147217887;
      if ( (bidGblFlags & 2) == 0 || !off_180048B20[0] )
        goto LABEL_27;
      v21 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
      v22 = off_180048B20[0];
      v23 = off_180048298[0];
      v24 = 215040;
    }
    bidTraceW(v23, v24, v22, v21, v13);
  }
  else
  {
    v13 = Exit(-2147024809, 0);
  }
LABEL_27:
  --*(_DWORD *)(v8 + 16);
  v10 = (*(_DWORD *)(v8 + 12))-- == 1;
  if ( v10 )
    *v9 = -1;
  v25 = *(_QWORD *)v8;
  --*(_DWORD *)(v25 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v25 + 8));
  return v13;
}

```

## disassembly

```asm
0x180018200  mov     [rsp+arg_8], rbx
0x180018205  mov     [rsp+arg_18], r9
0x18001820a  push    rbp
0x18001820b  push    rsi
0x18001820c  push    rdi
0x18001820d  push    r12
0x18001820f  push    r13
0x180018211  push    r14
0x180018213  push    r15
0x180018215  sub     rsp, 40h
0x180018219  mov     rsi, r9
0x18001821c  mov     r15, r8
0x18001821f  mov     r14, rcx
0x180018222  mov     rbx, [rcx+18h]
0x180018226  sub     rbx, 0FFFFFFFFFFFFFF80h
0x18001822a  mov     [rsp+78h+arg_10], rbx
0x180018232  mov     rcx, rbx
0x180018235  call    cs:__imp_UMSEnterCSWraper
0x18001823b  lea     rdi, [rbx+8]
0x18001823f  cmp     dword ptr [rbx+0Ch], 0
0x180018243  jnz     short loc_18001824D
0x180018245  call    cs:__imp_GetCurrentThreadId
0x18001824b  mov     [rdi], eax
0x18001824d  inc     dword ptr [rbx+0Ch]
0x180018250  inc     dword ptr [rbx+10h]
0x180018253  mov     [rsp+78h+var_48], rbx
0x180018258  xor     edx, edx; perrinfo
0x18001825a  xor     ecx, ecx; dwReserved
0x18001825c  call    cs:__imp_SetErrorInfo
0x180018262  test    r15, r15
0x180018265  jnz     short loc_18001828B
0x180018267  or      edx, 0FFFFFFFFh
0x18001826a  add     [rbx+10h], edx
0x18001826d  add     [rbx+0Ch], edx
0x180018270  jnz     short loc_180018274
0x180018272  mov     [rdi], edx
0x180018274  mov     rcx, [rbx]
0x180018277  dec     dword ptr [rcx+30h]
0x18001827a  add     rcx, 8; lpCriticalSection
0x18001827e  call    cs:__imp_LeaveCriticalSection
0x180018284  xor     eax, eax
0x180018286  jmp     loc_180018438
0x18001828b  mov     r13, [rsp+78h+arg_20]
0x180018293  test    r13, r13
0x180018296  jz      loc_18001840B
0x18001829c  test    rsi, rsi
0x18001829f  jz      loc_18001840B
0x1800182a5  xor     esi, esi
0x1800182a7  xor     r12d, r12d
0x1800182aa  xor     r11d, r11d
0x1800182ad  mov     [rsp+78h+arg_0], r11d
0x1800182b5  xor     ebp, ebp
0x1800182b7  test    r15, r15
0x1800182ba  jz      loc_180018419
0x1800182c0  mov     rbx, [rsp+78h+arg_18]
0x1800182c8  mov     r10, [r14+18h]
0x1800182cc  mov     r9d, [rbx+rbp*8]
0x1800182d0  mov     edx, r9d; unsigned int
0x1800182d3  mov     rcx, [r10+0D0h]; this
0x1800182da  call    ?IsSlotSet@CBitArray@@QEAAJK@Z; CBitArray::IsSlotSet(ulong)
0x1800182df  test    eax, eax
0x1800182e1  jz      short loc_180018339
0x1800182e3  mov     r12d, 1
0x1800182e9  test    byte ptr cs:_bidGblFlags, 2
0x1800182f0  jz      short loc_180018332
0x1800182f2  mov     rax, cs:off_180048B30; "<CImpIRowsetUpdate::GetRowStatus|ERR|PE"...
0x1800182f9  test    rax, rax
0x1800182fc  jz      short loc_180018332
0x1800182fe  mov     rcx, [r14+18h]
0x180018302  add     rcx, 70h ; 'p'; this
0x180018306  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001830b  mov     r8, cs:off_180048B30; "<CImpIRowsetUpdate::GetRowStatus|ERR|PE"...
0x180018312  mov     rcx, cs:off_1800482A8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180018319  mov     [rsp+78h+var_58], ebp
0x18001831d  mov     r9d, eax
0x180018320  mov     edx, 28C00h
0x180018325  call    _bidTraceW
0x18001832a  mov     r11d, [rsp+78h+arg_0]
0x180018332  mov     eax, 10h
0x180018337  jmp     short loc_18001835B
0x180018339  mov     r11d, 1
0x18001833f  mov     [rsp+78h+arg_0], r11d
0x180018347  imul    r9d, [r10+0DCh]
0x18001834f  mov     rax, [r10+0E0h]
0x180018356  mov     eax, [r9+rax+1Ch]
0x18001835b  mov     [r13+rbp*4+0], eax
0x180018360  inc     ebp
0x180018362  mov     eax, ebp
0x180018364  cmp     rax, r15
0x180018367  jb      loc_1800182C8
0x18001836d  test    r12d, r12d
0x180018370  mov     rbx, [rsp+78h+arg_10]
0x180018378  jz      loc_180018419
0x18001837e  test    r11d, r11d
0x180018381  jz      short loc_1800183C3
0x180018383  mov     esi, 40EDAh
0x180018388  test    byte ptr cs:_bidGblFlags, 2
0x18001838f  jz      loc_180018419
0x180018395  mov     rax, cs:off_180048B28; "<CImpIRowsetUpdate::GetRowStatus|ERR|PE"...
0x18001839c  test    rax, rax
0x18001839f  jz      short loc_180018419
0x1800183a1  mov     rcx, [r14+18h]
0x1800183a5  add     rcx, 70h ; 'p'; this
0x1800183a9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800183ae  mov     r8, cs:off_180048B28; "<CImpIRowsetUpdate::GetRowStatus|ERR|PE"...
0x1800183b5  mov     rcx, cs:off_1800482A0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800183bc  mov     edx, 33400h
0x1800183c1  jmp     short loc_1800183FD
0x1800183c3  mov     esi, 80040E21h
0x1800183c8  test    byte ptr cs:_bidGblFlags, 2
0x1800183cf  jz      short loc_180018419
0x1800183d1  mov     rax, cs:off_180048B20; "<CImpIRowsetUpdate::GetRowStatus|ERR|PE"...
0x1800183d8  test    rax, rax
0x1800183db  jz      short loc_180018419
0x1800183dd  mov     rcx, [r14+18h]
0x1800183e1  add     rcx, 70h ; 'p'; this
0x1800183e5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800183ea  mov     r8, cs:off_180048B20; "<CImpIRowsetUpdate::GetRowStatus|ERR|PE"...
0x1800183f1  mov     rcx, cs:off_180048298; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800183f8  mov     edx, 34800h
0x1800183fd  mov     [rsp+78h+var_58], esi
0x180018401  mov     r9d, eax
0x180018404  call    _bidTraceW
0x180018409  jmp     short loc_180018419
0x18001840b  xor     edx, edx; unsigned int
0x18001840d  mov     ecx, 80070057h; int
0x180018412  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180018417  mov     esi, eax
0x180018419  or      edx, 0FFFFFFFFh
0x18001841c  add     [rbx+10h], edx
0x18001841f  add     [rbx+0Ch], edx
0x180018422  jnz     short loc_180018426
0x180018424  mov     [rdi], edx
0x180018426  mov     rcx, [rbx]
0x180018429  dec     dword ptr [rcx+30h]
0x18001842c  add     rcx, 8; lpCriticalSection
0x180018430  call    cs:__imp_LeaveCriticalSection
0x180018436  mov     eax, esi
0x180018438  mov     rbx, [rsp+78h+arg_8]
0x180018440  add     rsp, 40h
0x180018444  pop     r15
0x180018446  pop     r14
0x180018448  pop     r13
0x18001844a  pop     r12
0x18001844c  pop     rdi
0x18001844d  pop     rsi
0x18001844e  pop     rbp
0x18001844f  retn
```
