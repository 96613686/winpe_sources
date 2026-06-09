# CImpIAccessor::ReleaseAccessor(unsigned __int64,ulong *)

- ea: `0x1800024d0`
- end: `0x180002615`
- name: `?ReleaseAccessor@CImpIAccessor@@UEAAJ_KPEAK@Z`
- size: `325`
- prototype: `int(CImpIAccessor *__hidden this, unsigned __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001dd8`
- `0x1800024d0`
- `0x180015fb4`
- `0x180016d94`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002502`
- `KERNEL32!GetCurrentThreadId` at `0x180002502`
- `KERNEL32!LeaveCriticalSection` at `0x1800025ca`
- `KERNEL32!LeaveCriticalSection` at `0x1800025fa`
- `KERNEL32!LeaveCriticalSection` at `0x1800025ca`
- `KERNEL32!LeaveCriticalSection` at `0x1800025fa`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180002523`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180002523`
- `MSDART!UMSEnterCSWraper` at `0x1800024f6`
- `MSDART!UMSEnterCSWraper` at `0x1800024f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIAccessor::ReleaseAccessor(CImpIAccessor *this, unsigned int a2, unsigned int *a3)
{
  __int64 v6; // rbx
  unsigned __int8 *v7; // rcx
  signed __int32 v8; // eax
  bool v9; // cc
  unsigned int v10; // eax
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  bool v13; // zf
  __int64 v14; // rcx
  unsigned int v16; // edi
  __int64 v17; // rcx
  unsigned __int8 *v18; // [rsp+40h] [rbp+8h] BYREF
  __int64 v19; // [rsp+50h] [rbp+18h]

  v6 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v6);
  if ( !*(_DWORD *)(v6 + 12) )
    *(_DWORD *)(v6 + 8) = GetCurrentThreadId();
  ++*(_DWORD *)(v6 + 12);
  ++*(_DWORD *)(v6 + 16);
  v19 = v6;
  v18 = 0;
  SetErrorInfo(0, 0);
  if ( a3 )
    *a3 = 0;
  if ( CExtBuffer::GetItemOfExtBuffer(*(CExtBuffer **)(*((_QWORD *)this + 3) + 192LL), a2, &v18) >= 0 && (v7 = v18) != 0 )
  {
    v8 = _InterlockedExchangeAdd((volatile signed __int32 *)v18 + 1, 0xFFFFFFFF);
    v9 = v8 <= 1;
    v10 = v8 - 1;
    if ( v9 )
    {
      if ( v7 )
        MMMFree(v7);
      if ( a3 )
        *a3 = 0;
      if ( a2 && (v11 = *(_QWORD *)(*((_QWORD *)this + 3) + 192LL), a2 <= *(_DWORD *)(v11 + 4)) )
        v12 = (_QWORD *)(*(_QWORD *)(v11 + 24) + *(_DWORD *)v11 * (a2 - 1));
      else
        v12 = 0;
      *v12 = 0;
    }
    else if ( a3 )
    {
      *a3 = v10;
    }
    --*(_DWORD *)(v6 + 16);
    v13 = (*(_DWORD *)(v6 + 12))-- == 1;
    if ( v13 )
      *(_DWORD *)(v6 + 8) = -1;
    v14 = *(_QWORD *)v6;
    --*(_DWORD *)(v14 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
    return 0;
  }
  else
  {
    v16 = Exit(-2147217920, 0);
    --*(_DWORD *)(v6 + 16);
    v13 = (*(_DWORD *)(v6 + 12))-- == 1;
    if ( v13 )
      *(_DWORD *)(v6 + 8) = -1;
    v17 = *(_QWORD *)v6;
    --*(_DWORD *)(v17 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 8));
    return v16;
  }
}

```

## disassembly

```asm
0x1800024d0  mov     [rsp+arg_8], rbx
0x1800024d5  mov     [rsp+arg_18], rbp
0x1800024da  push    rsi
0x1800024db  push    rdi
0x1800024dc  push    r14
0x1800024de  sub     rsp, 20h
0x1800024e2  mov     rdi, r8
0x1800024e5  mov     rbp, rdx
0x1800024e8  mov     r14, rcx
0x1800024eb  mov     rbx, [rcx+18h]
0x1800024ef  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1800024f3  mov     rcx, rbx
0x1800024f6  call    cs:__imp_UMSEnterCSWraper
0x1800024fc  cmp     dword ptr [rbx+0Ch], 0
0x180002500  jnz     short loc_18000250B
0x180002502  call    cs:__imp_GetCurrentThreadId
0x180002508  mov     [rbx+8], eax
0x18000250b  inc     dword ptr [rbx+0Ch]
0x18000250e  inc     dword ptr [rbx+10h]
0x180002511  mov     [rsp+38h+arg_10], rbx
0x180002516  mov     [rsp+38h+arg_0], 0
0x18000251f  xor     edx, edx; perrinfo
0x180002521  xor     ecx, ecx; dwReserved
0x180002523  call    cs:__imp_SetErrorInfo
0x180002529  test    rdi, rdi
0x18000252c  jz      short loc_180002534
0x18000252e  mov     dword ptr [rdi], 0
0x180002534  mov     rcx, [r14+18h]
0x180002538  lea     r8, [rsp+38h+arg_0]; void *
0x18000253d  mov     edx, ebp; unsigned int
0x18000253f  mov     rcx, [rcx+0C0h]; this
0x180002546  call    ?GetItemOfExtBuffer@CExtBuffer@@QEAAJKPEAX@Z; CExtBuffer::GetItemOfExtBuffer(ulong,void *)
0x18000254b  test    eax, eax
0x18000254d  js      loc_1800025D4
0x180002553  mov     rcx, [rsp+38h+arg_0]; unsigned __int8 *
0x180002558  test    rcx, rcx
0x18000255b  jz      short loc_1800025D4
0x18000255d  or      eax, 0FFFFFFFFh
0x180002560  lock xadd [rcx+4], eax
0x180002565  sub     eax, 1
0x180002568  jg      short loc_1800025AB
0x18000256a  test    rcx, rcx
0x18000256d  jz      short loc_180002574
0x18000256f  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x180002574  test    rdi, rdi
0x180002577  jz      short loc_18000257F
0x180002579  mov     dword ptr [rdi], 0
0x18000257f  cmp     ebp, 1
0x180002582  jb      short loc_1800025A0
0x180002584  mov     rax, [r14+18h]
0x180002588  mov     rdx, [rax+0C0h]
0x18000258f  cmp     ebp, [rdx+4]
0x180002592  ja      short loc_1800025A0
0x180002594  lea     ecx, [rbp-1]
0x180002597  imul    ecx, [rdx]
0x18000259a  add     rcx, [rdx+18h]
0x18000259e  jmp     short loc_1800025A2
0x1800025a0  xor     ecx, ecx
0x1800025a2  mov     qword ptr [rcx], 0
0x1800025a9  jmp     short loc_1800025B2
0x1800025ab  test    rdi, rdi
0x1800025ae  jz      short loc_1800025B2
0x1800025b0  mov     [rdi], eax
0x1800025b2  or      edx, 0FFFFFFFFh
0x1800025b5  add     [rbx+10h], edx
0x1800025b8  add     [rbx+0Ch], edx
0x1800025bb  jnz     short loc_1800025C0
0x1800025bd  mov     [rbx+8], edx
0x1800025c0  mov     rcx, [rbx]
0x1800025c3  dec     dword ptr [rcx+30h]
0x1800025c6  add     rcx, 8; lpCriticalSection
0x1800025ca  call    cs:__imp_LeaveCriticalSection
0x1800025d0  xor     eax, eax
0x1800025d2  jmp     short loc_180002602
0x1800025d4  xor     edx, edx; unsigned int
0x1800025d6  mov     ecx, 80040E00h; int
0x1800025db  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800025e0  mov     edi, eax
0x1800025e2  or      edx, 0FFFFFFFFh
0x1800025e5  add     [rbx+10h], edx
0x1800025e8  add     [rbx+0Ch], edx
0x1800025eb  jnz     short loc_1800025F0
0x1800025ed  mov     [rbx+8], edx
0x1800025f0  mov     rcx, [rbx]
0x1800025f3  dec     dword ptr [rcx+30h]
0x1800025f6  add     rcx, 8; lpCriticalSection
0x1800025fa  call    cs:__imp_LeaveCriticalSection
0x180002600  mov     eax, edi
0x180002602  mov     rbx, [rsp+38h+arg_8]
0x180002607  mov     rbp, [rsp+38h+arg_18]
0x18000260c  add     rsp, 20h
0x180002610  pop     r14
0x180002612  pop     rdi
0x180002613  pop     rsi
0x180002614  retn
```
