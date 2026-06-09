# CImpIRowset::ReleaseRows(unsigned __int64,unsigned __int64 const * const,ulong * const,ulong * const,ulong * const)

- ea: `0x180017c20`
- end: `0x180017f7c`
- name: `?ReleaseRows@CImpIRowset@@UEAAJ_KQEB_KQEAK22@Z`
- size: `860`
- prototype: `__int64 __fastcall(CImpIRowset *__hidden this, unsigned __int64, const unsigned __int64 *const, unsigned int *const, unsigned int *const, unsigned int *const)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800022f8`
- `0x180011484`
- `0x180015fb4`
- `0x1800172e0`
- `0x180017c20`
- `0x18001a6c8`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180017c6c`
- `KERNEL32!GetCurrentThreadId` at `0x180017c6c`
- `KERNEL32!LeaveCriticalSection` at `0x180017cc1`
- `KERNEL32!LeaveCriticalSection` at `0x180017f5c`
- `KERNEL32!LeaveCriticalSection` at `0x180017cc1`
- `KERNEL32!LeaveCriticalSection` at `0x180017f5c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180017c8b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180017c8b`
- `MSDART!UMSEnterCSWraper` at `0x180017c57`
- `MSDART!UMSEnterCSWraper` at `0x180017c57`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CImpIRowset::ReleaseRows(
        CImpIRowset *this,
        unsigned __int64 a2,
        const unsigned __int64 *const a3,
        unsigned int *const a4,
        unsigned int *const a5,
        unsigned int *const a6)
{
  unsigned __int64 v7; // r13
  __int64 v9; // rdi
  DWORD *v10; // r14
  unsigned int v11; // ebx
  bool v12; // zf
  __int64 v13; // rcx
  int v15; // r12d
  __int64 v16; // rbx
  __int64 v17; // r15
  unsigned __int64 v18; // r8
  int v19; // r9d
  __int64 v20; // r10
  unsigned int *v21; // r12
  __int64 v22; // r9
  unsigned int v23; // r13d
  __int64 v24; // rcx
  unsigned int BidObjectID; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  __int64 v28; // rcx
  int v29; // [rsp+30h] [rbp-58h]
  DWORD *v30; // [rsp+38h] [rbp-50h]
  int v31; // [rsp+90h] [rbp+8h]

  v7 = a2;
  v9 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v9);
  v10 = (DWORD *)(v9 + 8);
  v30 = (DWORD *)(v9 + 8);
  if ( *(_DWORD *)(v9 + 12) )
    v30 = (DWORD *)(v9 + 8);
  else
    *v10 = GetCurrentThreadId();
  ++*(_DWORD *)(v9 + 12);
  ++*(_DWORD *)(v9 + 16);
  SetErrorInfo(0, 0);
  if ( v7 && !a3 )
  {
    v11 = Exit(-2147024809, 0);
    --*(_DWORD *)(v9 + 16);
    v12 = (*(_DWORD *)(v9 + 12))-- == 1;
    if ( v12 )
      *v10 = -1;
LABEL_8:
    v13 = *(_QWORD *)v9;
    --*(_DWORD *)(v13 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
    return v11;
  }
  v29 = 0;
  v15 = 0;
  v16 = 0;
  v31 = 0;
  if ( v7 )
  {
    do
    {
      v17 = (unsigned int)v16;
      if ( (unsigned int)CBitArray::IsSlotSet(*(CBitArray **)(*((_QWORD *)this + 3) + 208LL), a3[v16]) )
      {
        v29 = 1;
        if ( (bidGblFlags & 2) != 0 && off_180048B00[0] )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          bidTraceW(off_180048278[0], 375808, off_180048B00[0], BidObjectID, v16);
        }
        if ( a5 )
          a5[v16] = 0;
        if ( a6 )
          a6[v16] = 12;
      }
      else
      {
        v21 = (unsigned int *)(*(_QWORD *)(v20 + 224) + (unsigned int)(*(_DWORD *)(v20 + 220) * v19));
        --*v21;
        --*(_DWORD *)(*((_QWORD *)this + 3) + 264LL);
        if ( a5 )
          a5[v16] = *v21;
        if ( !*v21 )
        {
          v22 = *((_QWORD *)this + 3);
          if ( *(_DWORD *)(v22 + 152) )
          {
            v23 = 1;
            do
            {
              (*(void (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v22 + 80LL))(
                v22,
                (char *)v21 + *(unsigned int *)(*(_QWORD *)(v22 + 160) + 4LL * v23),
                v23);
              v24 = *((_QWORD *)this + 3);
              v18 = *(unsigned int *)(v24 + 216)
                  + (unsigned __int64)*(unsigned int *)(*(_QWORD *)(v24 + 160) + 4LL * v23);
              if ( *(unsigned int *)((char *)v21 + v18 + 4) != 8 )
                (*(void (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v24 + 80LL))(v24, (char *)v21 + v18, v23);
              ++v23;
              v22 = *((_QWORD *)this + 3);
            }
            while ( v23 <= *(_DWORD *)(v22 + 152) );
            LODWORD(v16) = v31;
            v7 = a2;
          }
          ReleaseSlots(*(struct tagLSTSLOT **)(v22 + 200), a3[v17], v18);
        }
        if ( a6 )
          a6[v17] = 0;
        v15 = 1;
      }
      v16 = (unsigned int)(v16 + 1);
      v31 = v16;
    }
    while ( (unsigned int)v16 < v7 );
    v10 = v30;
    if ( v29 )
    {
      if ( v15 )
      {
        v11 = 265946;
        if ( (bidGblFlags & 2) != 0 && off_180048AF8[0] )
        {
          v26 = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          bidTraceW(off_180048270[0], 388096, off_180048AF8[0], v26, 265946);
        }
      }
      else
      {
        if ( (bidGblFlags & 2) != 0 && off_180048AF0[0] )
        {
          v27 = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          bidTraceW(off_180048268[0], 393216, off_180048AF0[0], v27, -2147217887);
        }
        v11 = Exit(-2147217887, 0);
      }
      --*(_DWORD *)(v9 + 16);
      v12 = (*(_DWORD *)(v9 + 12))-- == 1;
      if ( v12 )
        *(_DWORD *)(v9 + 8) = -1;
      goto LABEL_8;
    }
  }
  --*(_DWORD *)(v9 + 16);
  v12 = (*(_DWORD *)(v9 + 12))-- == 1;
  if ( v12 )
    *v10 = -1;
  v28 = *(_QWORD *)v9;
  --*(_DWORD *)(v28 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v28 + 8));
  return 0;
}

```

## disassembly

```asm
0x180017c20  mov     [rsp+arg_18], rbx
0x180017c25  mov     [rsp+arg_10], r8
0x180017c2a  mov     [rsp+arg_8], rdx
0x180017c2f  push    rbp
0x180017c30  push    rsi
0x180017c31  push    rdi
0x180017c32  push    r12
0x180017c34  push    r13
0x180017c36  push    r14
0x180017c38  push    r15
0x180017c3a  sub     rsp, 50h
0x180017c3e  mov     rbx, r8
0x180017c41  mov     r13, rdx
0x180017c44  mov     rbp, rcx
0x180017c47  mov     rdi, [rcx+18h]
0x180017c4b  sub     rdi, 0FFFFFFFFFFFFFF80h
0x180017c4f  mov     [rsp+88h+var_48], rdi
0x180017c54  mov     rcx, rdi
0x180017c57  call    cs:__imp_UMSEnterCSWraper
0x180017c5d  lea     r14, [rdi+8]
0x180017c61  mov     [rsp+88h+var_50], r14
0x180017c66  cmp     dword ptr [rdi+0Ch], 0
0x180017c6a  jnz     short loc_180017C77
0x180017c6c  call    cs:__imp_GetCurrentThreadId
0x180017c72  mov     [r14], eax
0x180017c75  jmp     short loc_180017C7C
0x180017c77  mov     [rsp+88h+var_50], r14
0x180017c7c  inc     dword ptr [rdi+0Ch]
0x180017c7f  inc     dword ptr [rdi+10h]
0x180017c82  mov     [rsp+88h+var_40], rdi
0x180017c87  xor     edx, edx; perrinfo
0x180017c89  xor     ecx, ecx; dwReserved
0x180017c8b  call    cs:__imp_SetErrorInfo
0x180017c91  test    r13, r13
0x180017c94  jz      short loc_180017CCE
0x180017c96  test    rbx, rbx
0x180017c99  jnz     short loc_180017CCE
0x180017c9b  xor     edx, edx; unsigned int
0x180017c9d  mov     ecx, 80070057h; int
0x180017ca2  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180017ca7  mov     ebx, eax
0x180017ca9  or      esi, 0FFFFFFFFh
0x180017cac  add     [rdi+10h], esi
0x180017caf  add     [rdi+0Ch], esi
0x180017cb2  jnz     short loc_180017CB7
0x180017cb4  mov     [r14], esi
0x180017cb7  mov     rcx, [rdi]
0x180017cba  dec     dword ptr [rcx+30h]
0x180017cbd  add     rcx, 8; lpCriticalSection
0x180017cc1  call    cs:__imp_LeaveCriticalSection
0x180017cc7  mov     eax, ebx
0x180017cc9  jmp     loc_180017F64
0x180017cce  xor     eax, eax
0x180017cd0  mov     [rsp+88h+var_58], eax
0x180017cd4  xor     r12d, r12d
0x180017cd7  xor     ebx, ebx
0x180017cd9  mov     [rsp+88h+arg_0], ebx
0x180017ce0  or      esi, 0FFFFFFFFh
0x180017ce3  test    r13, r13
0x180017ce6  jz      loc_180017F46
0x180017cec  mov     rdi, [rsp+88h+arg_28]
0x180017cf4  mov     r14, [rsp+88h+arg_20]
0x180017cfc  mov     r10, [rbp+18h]
0x180017d00  mov     r15d, ebx
0x180017d03  mov     rax, [rsp+88h+arg_10]
0x180017d0b  mov     r9d, [rax+rbx*8]
0x180017d0f  mov     edx, r9d; unsigned int
0x180017d12  mov     rcx, [r10+0D0h]; this
0x180017d19  call    ?IsSlotSet@CBitArray@@QEAAJK@Z; CBitArray::IsSlotSet(ulong)
0x180017d1e  test    eax, eax
0x180017d20  jnz     loc_180017E13
0x180017d26  imul    r9d, [r10+0DCh]
0x180017d2e  mov     r12d, r9d
0x180017d31  add     r12, [r10+0E0h]
0x180017d38  add     [r12], esi
0x180017d3c  mov     rax, [rbp+18h]
0x180017d40  add     [rax+108h], esi
0x180017d46  test    r14, r14
0x180017d49  jz      short loc_180017D53
0x180017d4b  mov     eax, [r12]
0x180017d4f  mov     [r14+rbx*4], eax
0x180017d53  cmp     dword ptr [r12], 0
0x180017d58  jnz     loc_180017DFE
0x180017d5e  mov     r9, [rbp+18h]
0x180017d62  cmp     dword ptr [r9+98h], 1
0x180017d6a  jb      short loc_180017DE6
0x180017d6c  mov     r13d, 1
0x180017d72  mov     ebx, r13d
0x180017d75  mov     rcx, [r9]
0x180017d78  mov     rax, [r9+0A0h]
0x180017d7f  mov     edx, [rax+rbx*4]
0x180017d82  add     rdx, r12
0x180017d85  mov     rax, [rcx+50h]
0x180017d89  mov     r8d, r13d
0x180017d8c  mov     rcx, r9
0x180017d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d94  mov     rcx, [rbp+18h]
0x180017d98  mov     rax, [rcx+0A0h]
0x180017d9f  mov     r8d, [rax+rbx*4]
0x180017da3  mov     eax, [rcx+0D8h]
0x180017da9  add     r8, rax
0x180017dac  cmp     dword ptr [r8+r12+4], 8
0x180017db2  jz      short loc_180017DC7
0x180017db4  mov     rax, [rcx]
0x180017db7  lea     rdx, [r8+r12]
0x180017dbb  mov     r8d, r13d
0x180017dbe  mov     rax, [rax+50h]
0x180017dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dc7  inc     r13d
0x180017dca  mov     r9, [rbp+18h]
0x180017dce  cmp     r13d, [r9+98h]
0x180017dd5  jbe     short loc_180017D72
0x180017dd7  mov     ebx, [rsp+88h+arg_0]
0x180017dde  mov     r13, [rsp+88h+arg_8]
0x180017de6  mov     rax, [rsp+88h+arg_10]
0x180017dee  mov     edx, [rax+r15*8]; unsigned int
0x180017df2  mov     rcx, [r9+0C8h]; struct tagLSTSLOT *
0x180017df9  call    ?ReleaseSlots@@YAJPEAUtagLSTSLOT@@KK@Z; ReleaseSlots(tagLSTSLOT *,ulong,ulong)
0x180017dfe  test    rdi, rdi
0x180017e01  jz      short loc_180017E0B
0x180017e03  mov     dword ptr [rdi+r15*4], 0
0x180017e0b  mov     r12d, 1
0x180017e11  jmp     short loc_180017E71
0x180017e13  mov     [rsp+88h+var_58], 1
0x180017e1b  test    byte ptr cs:_bidGblFlags, 2
0x180017e22  jz      short loc_180017E58
0x180017e24  mov     rax, cs:off_180048B00; "<CImpIRowset::ReleaseRows|ERR|PERSIST> "...
0x180017e2b  test    rax, rax
0x180017e2e  jz      short loc_180017E58
0x180017e30  lea     rcx, [rbp+20h]; this
0x180017e34  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180017e39  mov     r8, cs:off_180048B00; "<CImpIRowset::ReleaseRows|ERR|PERSIST> "...
0x180017e40  mov     rcx, cs:off_180048278; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180017e47  mov     [rsp+88h+var_68], ebx
0x180017e4b  mov     r9d, eax
0x180017e4e  mov     edx, 5BC00h
0x180017e53  call    _bidTraceW
0x180017e58  test    r14, r14
0x180017e5b  jz      short loc_180017E65
0x180017e5d  mov     dword ptr [r14+rbx*4], 0
0x180017e65  test    rdi, rdi
0x180017e68  jz      short loc_180017E71
0x180017e6a  mov     dword ptr [rdi+rbx*4], 0Ch
0x180017e71  inc     ebx
0x180017e73  mov     [rsp+88h+arg_0], ebx
0x180017e7a  mov     eax, ebx
0x180017e7c  cmp     rax, r13
0x180017e7f  jb      loc_180017CFC
0x180017e85  cmp     [rsp+88h+var_58], 0
0x180017e8a  mov     rdi, [rsp+88h+var_48]
0x180017e8f  mov     r14, [rsp+88h+var_50]
0x180017e94  jz      loc_180017F46
0x180017e9a  test    r12d, r12d
0x180017e9d  jz      short loc_180017EF7
0x180017e9f  mov     ebx, 40EDAh
0x180017ea4  test    byte ptr cs:_bidGblFlags, 2
0x180017eab  jz      short loc_180017EE2
0x180017ead  mov     rax, cs:off_180048AF8; "<CImpIRowset::ReleaseRows|ERR|PERSIST> "...
0x180017eb4  test    rax, rax
0x180017eb7  jz      short loc_180017EE2
0x180017eb9  lea     rcx, [rbp+20h]; this
0x180017ebd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180017ec2  mov     r8, cs:off_180048AF8; "<CImpIRowset::ReleaseRows|ERR|PERSIST> "...
0x180017ec9  mov     rcx, cs:off_180048270; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180017ed0  mov     [rsp+88h+var_68], ebx
0x180017ed4  mov     r9d, eax
0x180017ed7  mov     edx, 5EC00h
0x180017edc  call    _bidTraceW
0x180017ee1  nop
0x180017ee2  dec     dword ptr [rdi+10h]
0x180017ee5  sub     dword ptr [rdi+0Ch], 1
0x180017ee9  jnz     loc_180017CB7
0x180017eef  mov     [rdi+8], esi
0x180017ef2  jmp     loc_180017CB7
0x180017ef7  mov     ebx, 80040E21h
0x180017efc  test    byte ptr cs:_bidGblFlags, 2
0x180017f03  jz      short loc_180017F39
0x180017f05  mov     rax, cs:off_180048AF0; "<CImpIRowset::ReleaseRows|ERR|PERSIST> "...
0x180017f0c  test    rax, rax
0x180017f0f  jz      short loc_180017F39
0x180017f11  lea     rcx, [rbp+20h]; this
0x180017f15  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180017f1a  mov     r8, cs:off_180048AF0; "<CImpIRowset::ReleaseRows|ERR|PERSIST> "...
0x180017f21  mov     rcx, cs:off_180048268; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180017f28  mov     [rsp+88h+var_68], ebx
0x180017f2c  mov     r9d, eax
0x180017f2f  mov     edx, 60000h
0x180017f34  call    _bidTraceW
0x180017f39  xor     edx, edx; unsigned int
0x180017f3b  mov     ecx, ebx; int
0x180017f3d  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180017f42  mov     ebx, eax
0x180017f44  jmp     short loc_180017EE2
0x180017f46  dec     dword ptr [rdi+10h]
0x180017f49  sub     dword ptr [rdi+0Ch], 1
0x180017f4d  jnz     short loc_180017F52
0x180017f4f  mov     [r14], esi
0x180017f52  mov     rcx, [rdi]
0x180017f55  dec     dword ptr [rcx+30h]
0x180017f58  add     rcx, 8; lpCriticalSection
0x180017f5c  call    cs:__imp_LeaveCriticalSection
0x180017f62  xor     eax, eax
0x180017f64  mov     rbx, [rsp+88h+arg_18]
0x180017f6c  add     rsp, 50h
0x180017f70  pop     r15
0x180017f72  pop     r14
0x180017f74  pop     r13
0x180017f76  pop     r12
0x180017f78  pop     rdi
0x180017f79  pop     rsi
0x180017f7a  pop     rbp
0x180017f7b  retn
```
