# CImpIRowset::AddRefRows(unsigned __int64,unsigned __int64 const * const,ulong * const,ulong * const)

- ea: `0x1800173c0`
- end: `0x180017663`
- name: `?AddRefRows@CImpIRowset@@UEAAJ_KQEB_KQEAK2@Z`
- size: `675`
- prototype: `__int64 __fastcall(CImpIRowset *__hidden this, unsigned __int64, const unsigned __int64 *const, unsigned int *const, unsigned int *const)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800022f8`
- `0x180011484`
- `0x180015fb4`
- `0x1800173c0`
- `0x18001a6c8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001740e`
- `KERNEL32!GetCurrentThreadId` at `0x18001740e`
- `KERNEL32!LeaveCriticalSection` at `0x180017466`
- `KERNEL32!LeaveCriticalSection` at `0x1800175d8`
- `KERNEL32!LeaveCriticalSection` at `0x18001764a`
- `KERNEL32!LeaveCriticalSection` at `0x180017466`
- `KERNEL32!LeaveCriticalSection` at `0x1800175d8`
- `KERNEL32!LeaveCriticalSection` at `0x18001764a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001742f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001742f`
- `MSDART!UMSEnterCSWraper` at `0x1800173f6`
- `MSDART!UMSEnterCSWraper` at `0x1800173f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CImpIRowset::AddRefRows(
        CImpIRowset *this,
        unsigned __int64 a2,
        const unsigned __int64 *const a3,
        unsigned int *const a4,
        unsigned int *const a5)
{
  __int64 v8; // rbx
  DWORD *v9; // rdi
  unsigned int v10; // esi
  bool v11; // zf
  __int64 v12; // rcx
  int v14; // r15d
  __int64 v15; // r14
  __int64 v16; // r13
  int v17; // r10d
  int v18; // r11d
  unsigned int BidObjectID; // eax
  __int64 v20; // r10
  __int64 v21; // r8
  unsigned int v22; // edi
  unsigned int v23; // eax
  __int64 v24; // rcx
  unsigned int v25; // eax
  __int64 v26; // rcx
  DWORD *v27; // [rsp+90h] [rbp+8h]

  v8 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v8);
  v9 = (DWORD *)(v8 + 8);
  v27 = (DWORD *)(v8 + 8);
  if ( *(_DWORD *)(v8 + 12) )
    v27 = (DWORD *)(v8 + 8);
  else
    *v9 = GetCurrentThreadId();
  ++*(_DWORD *)(v8 + 12);
  ++*(_DWORD *)(v8 + 16);
  SetErrorInfo(0, 0);
  if ( !a2 || a3 )
  {
    v14 = 0;
    v15 = 0;
    if ( !a2 )
      goto LABEL_35;
    do
    {
      v16 = *((_QWORD *)this + 3);
      if ( (unsigned int)CBitArray::IsSlotSet(*(CBitArray **)(v16 + 208), a3[v15]) )
      {
        if ( a5 )
          a5[v15] = 12;
        if ( (bidGblFlags & 2) != 0 && off_180048AE8[0] )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          bidTraceW(off_180048260[0], 483328, off_180048AE8[0], BidObjectID, v15);
        }
        v18 = 1;
      }
      else
      {
        v20 = (unsigned int)(*(_DWORD *)(v16 + 220) * v17);
        v21 = *(_QWORD *)(v16 + 224);
        ++*(_DWORD *)(v20 + v21);
        ++*(_DWORD *)(*((_QWORD *)this + 3) + 264LL);
        if ( a4 )
          a4[v15] = *(_DWORD *)(v20 + v21);
        if ( a5 )
          a5[v15] = 0;
        v14 = 1;
      }
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (unsigned int)v15 < a2 );
    v9 = v27;
    if ( v18 )
    {
      if ( v14 )
      {
        v22 = 265946;
        if ( (bidGblFlags & 2) != 0 && off_180048AE0[0] )
        {
          v23 = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          bidTraceW(off_180048258[0], 510976, off_180048AE0[0], v23, 265946);
        }
      }
      else
      {
        if ( (bidGblFlags & 2) != 0 && off_180048AD8[0] )
        {
          v25 = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          bidTraceW(off_180048250[0], 516096, off_180048AD8[0], v25, -2147217887);
        }
        v22 = Exit(-2147217887, 0);
      }
      --*(_DWORD *)(v8 + 16);
      v11 = (*(_DWORD *)(v8 + 12))-- == 1;
      if ( v11 )
        *(_DWORD *)(v8 + 8) = -1;
      v24 = *(_QWORD *)v8;
      --*(_DWORD *)(v24 + 48);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v24 + 8));
      return v22;
    }
    else
    {
LABEL_35:
      --*(_DWORD *)(v8 + 16);
      v11 = (*(_DWORD *)(v8 + 12))-- == 1;
      if ( v11 )
        *v9 = -1;
      v26 = *(_QWORD *)v8;
      --*(_DWORD *)(v26 + 48);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v26 + 8));
      return 0;
    }
  }
  else
  {
    v10 = Exit(-2147024809, 0);
    --*(_DWORD *)(v8 + 16);
    v11 = (*(_DWORD *)(v8 + 12))-- == 1;
    if ( v11 )
      *v9 = -1;
    v12 = *(_QWORD *)v8;
    --*(_DWORD *)(v12 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
    return v10;
  }
}

```

## disassembly

```asm
0x1800173c0  mov     [rsp+arg_18], r9
0x1800173c5  mov     [rsp+arg_10], r8
0x1800173ca  push    rbx
0x1800173cb  push    rbp
0x1800173cc  push    rsi
0x1800173cd  push    rdi
0x1800173ce  push    r12
0x1800173d0  push    r13
0x1800173d2  push    r14
0x1800173d4  push    r15
0x1800173d6  sub     rsp, 48h
0x1800173da  mov     rsi, r8
0x1800173dd  mov     r12, rdx
0x1800173e0  mov     rbp, rcx
0x1800173e3  mov     rbx, [rcx+18h]
0x1800173e7  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1800173eb  mov     [rsp+88h+arg_8], rbx
0x1800173f3  mov     rcx, rbx
0x1800173f6  call    cs:__imp_UMSEnterCSWraper
0x1800173fc  lea     rdi, [rbx+8]
0x180017400  mov     [rsp+88h+arg_0], rdi
0x180017408  cmp     dword ptr [rbx+0Ch], 0
0x18001740c  jnz     short loc_180017418
0x18001740e  call    cs:__imp_GetCurrentThreadId
0x180017414  mov     [rdi], eax
0x180017416  jmp     short loc_180017420
0x180017418  mov     [rsp+88h+arg_0], rdi
0x180017420  inc     dword ptr [rbx+0Ch]
0x180017423  inc     dword ptr [rbx+10h]
0x180017426  mov     [rsp+88h+var_58], rbx
0x18001742b  xor     edx, edx; perrinfo
0x18001742d  xor     ecx, ecx; dwReserved
0x18001742f  call    cs:__imp_SetErrorInfo
0x180017435  test    r12, r12
0x180017438  jz      short loc_180017473
0x18001743a  test    rsi, rsi
0x18001743d  jnz     short loc_180017473
0x18001743f  xor     edx, edx; unsigned int
0x180017441  mov     ecx, 80070057h; int
0x180017446  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18001744b  mov     esi, eax
0x18001744d  dec     dword ptr [rbx+10h]
0x180017450  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x180017454  jnz     short loc_18001745C
0x180017456  mov     dword ptr [rdi], 0FFFFFFFFh
0x18001745c  mov     rcx, [rbx]
0x18001745f  dec     dword ptr [rcx+30h]
0x180017462  add     rcx, 8; lpCriticalSection
0x180017466  call    cs:__imp_LeaveCriticalSection
0x18001746c  mov     eax, esi
0x18001746e  jmp     loc_180017652
0x180017473  mov     rsi, [rsp+88h+arg_20]
0x18001747b  xor     r11d, r11d
0x18001747e  xor     r15d, r15d
0x180017481  xor     r14d, r14d
0x180017484  test    r12, r12
0x180017487  jz      loc_180017631
0x18001748d  mov     rbx, [rsp+88h+arg_10]
0x180017495  mov     rdi, [rsp+88h+arg_18]
0x18001749d  mov     r13, [rbp+18h]
0x1800174a1  mov     r10d, [rbx+r14*8]
0x1800174a5  mov     edx, r10d; unsigned int
0x1800174a8  mov     rcx, [r13+0D0h]; this
0x1800174af  call    ?IsSlotSet@CBitArray@@QEAAJK@Z; CBitArray::IsSlotSet(ulong)
0x1800174b4  test    eax, eax
0x1800174b6  jz      short loc_18001750B
0x1800174b8  test    rsi, rsi
0x1800174bb  jz      short loc_1800174C5
0x1800174bd  mov     dword ptr [rsi+r14*4], 0Ch
0x1800174c5  test    byte ptr cs:_bidGblFlags, 2
0x1800174cc  jz      short loc_180017503
0x1800174ce  mov     rax, cs:off_180048AE8; "<CImpIRowset::AddRefRows|ERR|PERSIST> %"...
0x1800174d5  test    rax, rax
0x1800174d8  jz      short loc_180017503
0x1800174da  lea     rcx, [rbp+20h]; this
0x1800174de  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800174e3  mov     r8, cs:off_180048AE8; "<CImpIRowset::AddRefRows|ERR|PERSIST> %"...
0x1800174ea  mov     rcx, cs:off_180048260; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800174f1  mov     [rsp+88h+var_68], r14d
0x1800174f6  mov     r9d, eax
0x1800174f9  mov     edx, 76000h
0x1800174fe  call    _bidTraceW
0x180017503  mov     r11d, 1
0x180017509  jmp     short loc_18001754E
0x18001750b  imul    r10d, [r13+0DCh]
0x180017513  mov     r8, [r13+0E0h]
0x18001751a  inc     dword ptr [r10+r8]
0x18001751e  mov     rax, [rbp+18h]
0x180017522  inc     dword ptr [rax+108h]
0x180017528  lea     rcx, ds:0[r14*4]
0x180017530  test    rdi, rdi
0x180017533  jz      short loc_18001753C
0x180017535  mov     eax, [r10+r8]
0x180017539  mov     [rdi+rcx], eax
0x18001753c  test    rsi, rsi
0x18001753f  jz      short loc_180017548
0x180017541  mov     dword ptr [rsi+rcx], 0
0x180017548  mov     r15d, 1
0x18001754e  inc     r14d
0x180017551  mov     eax, r14d
0x180017554  cmp     rax, r12
0x180017557  jb      loc_18001749D
0x18001755d  test    r11d, r11d
0x180017560  mov     rbx, [rsp+88h+arg_8]
0x180017568  mov     rdi, [rsp+88h+arg_0]
0x180017570  jz      loc_180017631
0x180017576  test    r15d, r15d
0x180017579  jz      short loc_1800175E2
0x18001757b  mov     edi, 40EDAh
0x180017580  test    byte ptr cs:_bidGblFlags, 2
0x180017587  jz      short loc_1800175BE
0x180017589  mov     rax, cs:off_180048AE0; "<CImpIRowset::AddRefRows|ERR|PERSIST> %"...
0x180017590  test    rax, rax
0x180017593  jz      short loc_1800175BE
0x180017595  lea     rcx, [rbp+20h]; this
0x180017599  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001759e  mov     r8, cs:off_180048AE0; "<CImpIRowset::AddRefRows|ERR|PERSIST> %"...
0x1800175a5  mov     rcx, cs:off_180048258; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800175ac  mov     [rsp+88h+var_68], edi
0x1800175b0  mov     r9d, eax
0x1800175b3  mov     edx, 7CC00h
0x1800175b8  call    _bidTraceW
0x1800175bd  nop
0x1800175be  dec     dword ptr [rbx+10h]
0x1800175c1  sub     dword ptr [rbx+0Ch], 1
0x1800175c5  jnz     short loc_1800175CE
0x1800175c7  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x1800175ce  mov     rcx, [rbx]
0x1800175d1  dec     dword ptr [rcx+30h]
0x1800175d4  add     rcx, 8; lpCriticalSection
0x1800175d8  call    cs:__imp_LeaveCriticalSection
0x1800175de  mov     eax, edi
0x1800175e0  jmp     short loc_180017652
0x1800175e2  mov     edi, 80040E21h
0x1800175e7  test    byte ptr cs:_bidGblFlags, 2
0x1800175ee  jz      short loc_180017624
0x1800175f0  mov     rax, cs:off_180048AD8; "<CImpIRowset::AddRefRows|ERR|PERSIST> %"...
0x1800175f7  test    rax, rax
0x1800175fa  jz      short loc_180017624
0x1800175fc  lea     rcx, [rbp+20h]; this
0x180017600  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180017605  mov     r8, cs:off_180048AD8; "<CImpIRowset::AddRefRows|ERR|PERSIST> %"...
0x18001760c  mov     rcx, cs:off_180048250; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180017613  mov     [rsp+88h+var_68], edi
0x180017617  mov     r9d, eax
0x18001761a  mov     edx, 7E000h
0x18001761f  call    _bidTraceW
0x180017624  xor     edx, edx; unsigned int
0x180017626  mov     ecx, edi; int
0x180017628  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18001762d  mov     edi, eax
0x18001762f  jmp     short loc_1800175BE
0x180017631  dec     dword ptr [rbx+10h]
0x180017634  sub     dword ptr [rbx+0Ch], 1
0x180017638  jnz     short loc_180017640
0x18001763a  mov     dword ptr [rdi], 0FFFFFFFFh
0x180017640  mov     rcx, [rbx]
0x180017643  dec     dword ptr [rcx+30h]
0x180017646  add     rcx, 8; lpCriticalSection
0x18001764a  call    cs:__imp_LeaveCriticalSection
0x180017650  xor     eax, eax
0x180017652  add     rsp, 48h
0x180017656  pop     r15
0x180017658  pop     r14
0x18001765a  pop     r13
0x18001765c  pop     r12
0x18001765e  pop     rdi
0x18001765f  pop     rsi
0x180017660  pop     rbp
0x180017661  pop     rbx
0x180017662  retn
```
