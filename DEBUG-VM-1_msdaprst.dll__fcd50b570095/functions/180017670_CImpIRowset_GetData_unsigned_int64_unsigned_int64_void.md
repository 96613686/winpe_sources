# CImpIRowset::GetData(unsigned __int64,unsigned __int64,void *)

- ea: `0x180017670`
- end: `0x180017926`
- name: `?GetData@CImpIRowset@@UEAAJ_K0PEAX@Z`
- size: `694`
- prototype: `int(CImpIRowset *__hidden this, unsigned __int64, unsigned __int64, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800022f8`
- `0x180015fb4`
- `0x180017670`
- `0x18001a6c8`
- `0x180020998`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800176a8`
- `KERNEL32!GetCurrentThreadId` at `0x1800176a8`
- `KERNEL32!LeaveCriticalSection` at `0x180017718`
- `KERNEL32!LeaveCriticalSection` at `0x18001790d`
- `KERNEL32!LeaveCriticalSection` at `0x180017718`
- `KERNEL32!LeaveCriticalSection` at `0x18001790d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800176cb`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800176cb`
- `MSDART!UMSEnterCSWraper` at `0x180017698`
- `MSDART!UMSEnterCSWraper` at `0x180017698`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIRowset::GetData(CImpIRowset *this, unsigned __int64 a2, unsigned __int64 a3, char *a4)
{
  __int64 v8; // rbx
  DWORD *v9; // rsi
  int DataArgs; // eax
  int v11; // ecx
  unsigned int v12; // ebp
  bool v13; // zf
  __int64 v14; // rcx
  struct tagACCESSOR *v16; // rbp
  int v17; // r15d
  unsigned int v18; // r12d
  __int64 v19; // rax
  __int64 v20; // r9
  int v21; // ecx
  char *v22; // r11
  char *v23; // r10
  __int64 v24; // r8
  char *v25; // rdx
  unsigned int BidObjectID; // eax
  unsigned int v27; // eax
  wchar_t *v28; // r8
  char *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  int v32; // [rsp+20h] [rbp-98h]
  unsigned int v33; // [rsp+50h] [rbp-68h]
  __int64 v34; // [rsp+58h] [rbp-60h]
  struct tagACCESSOR *v35; // [rsp+C0h] [rbp+8h] BYREF

  v8 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v8);
  v9 = (DWORD *)(v8 + 8);
  if ( !*(_DWORD *)(v8 + 12) )
    *v9 = GetCurrentThreadId();
  ++*(_DWORD *)(v8 + 12);
  ++*(_DWORD *)(v8 + 16);
  v35 = 0;
  SetErrorInfo(0, 0);
  DataArgs = CRowset::ValidateGetDataArgs(*((CRowset **)this + 3), a2, a3, a4, &v35);
  if ( DataArgs < 0 )
  {
    v11 = DataArgs;
LABEL_5:
    v12 = Exit(v11, 0);
    goto LABEL_6;
  }
  if ( *(_DWORD *)((unsigned int)(*(_DWORD *)(*((_QWORD *)this + 3) + 220LL) * a2)
                 + *(_QWORD *)(*((_QWORD *)this + 3) + 224LL)
                 + 28LL) == 4 )
  {
    v11 = -2147217885;
    goto LABEL_5;
  }
  v16 = v35;
  v33 = *((_DWORD *)v35 + 2);
  v17 = 0;
  v18 = 0;
  if ( v33 )
  {
    v19 = 0;
    v34 = 0;
    do
    {
      v20 = 88 * v19;
      LODWORD(v35) = *((_DWORD *)v16 + 22 * v19 + 4);
      v21 = *((_DWORD *)v16 + 22 * v19 + 18);
      if ( (v21 & 1) != 0 )
        v22 = &a4[*(_QWORD *)((char *)v16 + v20 + 24)];
      else
        v22 = 0;
      if ( (v21 & 2) != 0 )
        v23 = &a4[*(_QWORD *)((char *)v16 + v20 + 32)];
      else
        v23 = 0;
      v24 = *(unsigned int *)((char *)v16 + v20 + 88);
      if ( v24 != *(_QWORD *)((char *)v16 + v20 + 88) )
        v24 = 0xFFFFFFFFLL;
      if ( (v21 & 4) != 0 )
        v25 = &a4[*(_QWORD *)((char *)v16 + v20 + 40)];
      else
        v25 = 0;
      LOBYTE(v32) = 0;
      LODWORD(v35) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, int, char *, char *, char *))(**((_QWORD **)this + 3) + 48LL))(
                       *((_QWORD *)this + 3),
                       (unsigned int)v35,
                       v24,
                       *(unsigned __int16 *)((char *)v16 + v20 + 100),
                       v32,
                       v25,
                       v23,
                       v22);
      if ( (_DWORD)v35 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048B18[0] )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          bidTraceW(off_180048290[0], 110592, off_180048B18[0], BidObjectID, (_DWORD)v35);
        }
        ++v17;
      }
      ++v18;
      v19 = ++v34;
    }
    while ( v18 < v33 );
    if ( v17 )
    {
      if ( v33 == v17 )
      {
        v12 = -2147217887;
        if ( (bidGblFlags & 2) != 0 && off_180048B10[0] )
        {
          v27 = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          v28 = off_180048B10[0];
          v29 = off_180048288[0];
          v30 = 121856;
LABEL_35:
          bidTraceW(v29, v30, v28, v27, v12);
        }
      }
      else
      {
        v12 = 265946;
        if ( (bidGblFlags & 2) != 0 && off_180048B08[0] )
        {
          v27 = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          v28 = off_180048B08[0];
          v29 = off_180048280[0];
          v30 = 126976;
          goto LABEL_35;
        }
      }
LABEL_6:
      --*(_DWORD *)(v8 + 16);
      v13 = (*(_DWORD *)(v8 + 12))-- == 1;
      if ( v13 )
        *v9 = -1;
      v14 = *(_QWORD *)v8;
      --*(_DWORD *)(v14 + 48);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
      return v12;
    }
  }
  --*(_DWORD *)(v8 + 16);
  v13 = (*(_DWORD *)(v8 + 12))-- == 1;
  if ( v13 )
    *v9 = -1;
  v31 = *(_QWORD *)v8;
  --*(_DWORD *)(v31 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v31 + 8));
  return 0;
}

```

## disassembly

```asm
0x180017670  push    rbx
0x180017672  push    rbp
0x180017673  push    rsi
0x180017674  push    rdi
0x180017675  push    r12
0x180017677  push    r13
0x180017679  push    r14
0x18001767b  push    r15
0x18001767d  sub     rsp, 78h
0x180017681  mov     r13, r9
0x180017684  mov     rbp, r8
0x180017687  mov     rdi, rdx
0x18001768a  mov     r14, rcx
0x18001768d  mov     rbx, [rcx+18h]
0x180017691  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180017695  mov     rcx, rbx
0x180017698  call    cs:__imp_UMSEnterCSWraper
0x18001769e  lea     rsi, [rbx+8]
0x1800176a2  cmp     dword ptr [rbx+0Ch], 0
0x1800176a6  jnz     short loc_1800176B0
0x1800176a8  call    cs:__imp_GetCurrentThreadId
0x1800176ae  mov     [rsi], eax
0x1800176b0  inc     dword ptr [rbx+0Ch]
0x1800176b3  inc     dword ptr [rbx+10h]
0x1800176b6  mov     [rsp+0B8h+var_58], rbx
0x1800176bb  mov     [rsp+0B8h+arg_0], 0
0x1800176c7  xor     edx, edx; perrinfo
0x1800176c9  xor     ecx, ecx; dwReserved
0x1800176cb  call    cs:__imp_SetErrorInfo
0x1800176d1  lea     rax, [rsp+0B8h+arg_0]
0x1800176d9  mov     [rsp+0B8h+var_98], rax; struct tagACCESSOR **
0x1800176de  mov     r9, r13; void *
0x1800176e1  mov     r8, rbp; unsigned __int64
0x1800176e4  mov     rdx, rdi; unsigned __int64
0x1800176e7  mov     rcx, [r14+18h]; this
0x1800176eb  call    ?ValidateGetDataArgs@CRowset@@QEAAJ_K0PEAXPEAPEAUtagACCESSOR@@@Z; CRowset::ValidateGetDataArgs(unsigned __int64,unsigned __int64,void *,tagACCESSOR * *)
0x1800176f0  test    eax, eax
0x1800176f2  jns     short loc_180017725
0x1800176f4  mov     ecx, eax; int
0x1800176f6  xor     edx, edx; unsigned int
0x1800176f8  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800176fd  mov     ebp, eax
0x1800176ff  mov     edi, 0FFFFFFFFh
0x180017704  add     [rbx+10h], edi
0x180017707  add     [rbx+0Ch], edi
0x18001770a  jnz     short loc_18001770E
0x18001770c  mov     [rsi], edi
0x18001770e  mov     rcx, [rbx]
0x180017711  dec     dword ptr [rcx+30h]
0x180017714  add     rcx, 8; lpCriticalSection
0x180017718  call    cs:__imp_LeaveCriticalSection
0x18001771e  mov     eax, ebp
0x180017720  jmp     loc_180017915
0x180017725  mov     rax, [r14+18h]
0x180017729  imul    edi, [rax+0DCh]
0x180017730  mov     rax, [rax+0E0h]
0x180017737  cmp     dword ptr [rdi+rax+1Ch], 4
0x18001773c  jnz     short loc_180017745
0x18001773e  mov     ecx, 80040E23h
0x180017743  jmp     short loc_1800176F6
0x180017745  mov     rbp, [rsp+0B8h+arg_0]
0x18001774d  mov     edx, [rbp+8]
0x180017750  mov     [rsp+0B8h+var_68], edx
0x180017754  xor     r15d, r15d
0x180017757  xor     r12d, r12d
0x18001775a  mov     edi, 0FFFFFFFFh
0x18001775f  test    edx, edx
0x180017761  jz      loc_1800178F9
0x180017767  xor     eax, eax
0x180017769  mov     [rsp+0B8h+var_60], rax
0x18001776e  imul    r9, rax, 58h ; 'X'
0x180017772  mov     eax, [r9+rbp+10h]
0x180017777  mov     dword ptr [rsp+0B8h+arg_0], eax
0x18001777e  mov     ecx, [r9+rbp+48h]
0x180017783  test    cl, 1
0x180017786  jz      short loc_180017792
0x180017788  mov     r11, [r9+rbp+18h]
0x18001778d  add     r11, r13
0x180017790  jmp     short loc_180017795
0x180017792  xor     r11d, r11d
0x180017795  test    cl, 2
0x180017798  jz      short loc_1800177A4
0x18001779a  mov     r10, [r9+rbp+20h]
0x18001779f  add     r10, r13
0x1800177a2  jmp     short loc_1800177A7
0x1800177a4  xor     r10d, r10d
0x1800177a7  mov     r8d, [r9+rbp+58h]
0x1800177ac  cmp     r8, [r9+rbp+58h]
0x1800177b1  cmovnz  r8, rdi
0x1800177b5  test    cl, 4
0x1800177b8  jz      short loc_1800177C4
0x1800177ba  mov     rdx, [r9+rbp+28h]
0x1800177bf  add     rdx, r13
0x1800177c2  jmp     short loc_1800177C6
0x1800177c4  xor     edx, edx
0x1800177c6  mov     rcx, [r14+18h]
0x1800177ca  mov     rax, [rcx]
0x1800177cd  mov     [rsp+0B8h+var_80], r11
0x1800177d2  mov     [rsp+0B8h+var_88], r10
0x1800177d7  mov     [rsp+0B8h+var_90], rdx
0x1800177dc  mov     byte ptr [rsp+0B8h+var_98], 0
0x1800177e1  movzx   r9d, word ptr [r9+rbp+64h]
0x1800177e7  mov     edx, dword ptr [rsp+0B8h+arg_0]
0x1800177ee  mov     rax, [rax+30h]
0x1800177f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177f7  mov     dword ptr [rsp+0B8h+arg_0], eax
0x1800177fe  test    eax, eax
0x180017800  jz      short loc_18001784E
0x180017802  test    byte ptr cs:_bidGblFlags, 2
0x180017809  jz      short loc_18001784B
0x18001780b  mov     rcx, cs:off_180048B18; "<CImpIRowset::GetData|ERR|PERSIST> %u#,"...
0x180017812  test    rcx, rcx
0x180017815  jz      short loc_18001784B
0x180017817  lea     rcx, [r14+20h]; this
0x18001781b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180017820  mov     r8, cs:off_180048B18; "<CImpIRowset::GetData|ERR|PERSIST> %u#,"...
0x180017827  mov     rcx, cs:off_180048290; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001782e  mov     dword ptr [rsp+0B8h+var_90], r12d
0x180017833  mov     edx, dword ptr [rsp+0B8h+arg_0]
0x18001783a  mov     dword ptr [rsp+0B8h+var_98], edx
0x18001783e  mov     r9d, eax
0x180017841  mov     edx, 1B000h
0x180017846  call    _bidTraceW
0x18001784b  inc     r15d
0x18001784e  inc     r12d
0x180017851  mov     rax, [rsp+0B8h+var_60]
0x180017856  inc     rax
0x180017859  mov     [rsp+0B8h+var_60], rax
0x18001785e  mov     edx, [rsp+0B8h+var_68]
0x180017862  cmp     r12d, edx
0x180017865  jb      loc_18001776E
0x18001786b  test    r15d, r15d
0x18001786e  jz      loc_1800178F9
0x180017874  cmp     edx, r15d
0x180017877  jnz     short loc_1800178C1
0x180017879  mov     ebp, 80040E21h
0x18001787e  test    byte ptr cs:_bidGblFlags, 2
0x180017885  jz      short loc_1800178BC
0x180017887  mov     rax, cs:off_180048B10; "<CImpIRowset::GetData|ERR|PERSIST> %u#,"...
0x18001788e  test    rax, rax
0x180017891  jz      short loc_1800178BC
0x180017893  lea     rcx, [r14+20h]; this
0x180017897  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001789c  mov     r8, cs:off_180048B10; "<CImpIRowset::GetData|ERR|PERSIST> %u#,"...
0x1800178a3  mov     rcx, cs:off_180048288; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800178aa  mov     edx, 1DC00h
0x1800178af  mov     r9d, eax
0x1800178b2  mov     dword ptr [rsp+0B8h+var_98], ebp
0x1800178b6  call    _bidTraceW
0x1800178bb  nop
0x1800178bc  jmp     loc_180017704
0x1800178c1  mov     ebp, 40EDAh
0x1800178c6  test    byte ptr cs:_bidGblFlags, 2
0x1800178cd  jz      short loc_1800178BC
0x1800178cf  mov     rax, cs:off_180048B08; "<CImpIRowset::GetData|ERR|PERSIST> %u#,"...
0x1800178d6  test    rax, rax
0x1800178d9  jz      short loc_1800178BC
0x1800178db  lea     rcx, [r14+20h]; this
0x1800178df  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800178e4  mov     r8, cs:off_180048B08; "<CImpIRowset::GetData|ERR|PERSIST> %u#,"...
0x1800178eb  mov     rcx, cs:off_180048280; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800178f2  mov     edx, 1F000h
0x1800178f7  jmp     short loc_1800178AF
0x1800178f9  add     [rbx+10h], edi
0x1800178fc  add     [rbx+0Ch], edi
0x1800178ff  jnz     short loc_180017903
0x180017901  mov     [rsi], edi
0x180017903  mov     rcx, [rbx]
0x180017906  dec     dword ptr [rcx+30h]
0x180017909  add     rcx, 8; lpCriticalSection
0x18001790d  call    cs:__imp_LeaveCriticalSection
0x180017913  xor     eax, eax
0x180017915  add     rsp, 78h
0x180017919  pop     r15
0x18001791b  pop     r14
0x18001791d  pop     r13
0x18001791f  pop     r12
0x180017921  pop     rdi
0x180017922  pop     rsi
0x180017923  pop     rbp
0x180017924  pop     rbx
0x180017925  retn
```
