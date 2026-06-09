# CPersistDSO::CreateSession(IUnknown *,_GUID const &,IUnknown * *)

- ea: `0x180013f30`
- end: `0x18001426d`
- name: `?CreateSession@CPersistDSO@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAU2@@Z`
- size: `829`
- prototype: `__int64 __fastcall(CPersistDSO *__hidden this, struct IUnknown *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001d94`
- `0x1800022f8`
- `0x180013f30`
- `0x180015fb4`
- `0x18001a6c8`
- `0x180020a08`
- `0x18002cd54`
- `0x18002dd80`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180013f6e`
- `KERNEL32!GetCurrentThreadId` at `0x180013f6e`
- `KERNEL32!LeaveCriticalSection` at `0x1800141e2`
- `KERNEL32!LeaveCriticalSection` at `0x180014223`
- `KERNEL32!LeaveCriticalSection` at `0x180014252`
- `KERNEL32!LeaveCriticalSection` at `0x1800141e2`
- `KERNEL32!LeaveCriticalSection` at `0x180014223`
- `KERNEL32!LeaveCriticalSection` at `0x180014252`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180013f9b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180013f9b`
- `MSDART!UMSEnterCSWraper` at `0x180013f59`
- `MSDART!UMSEnterCSWraper` at `0x180013f59`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPersistDSO::CreateSession(
        GUID *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        struct IUnknown **a4)
{
  GUID *v7; // rdi
  unsigned __int8 *v8; // r14
  unsigned int v9; // edx
  int v10; // eax
  int v11; // ebx
  CPersistSession *v12; // rax
  int v13; // r9d
  CPersistSession *v14; // rbx
  int BidObjectID; // r15d
  unsigned int v16; // eax
  int v17; // eax
  int v18; // r15d
  int v19; // eax
  int v20; // ebx
  bool v21; // zf
  __int64 v22; // rcx
  unsigned int v24; // ebx
  GUID *v25; // rcx
  __int64 v26; // rcx
  GUID *v27; // rcx
  __int64 v28; // rcx
  int v29; // [rsp+30h] [rbp-68h] BYREF
  GUID *v30; // [rsp+38h] [rbp-60h]
  GUID *v31; // [rsp+40h] [rbp-58h]
  unsigned __int8 *v32; // [rsp+48h] [rbp-50h]
  GUID *v33; // [rsp+50h] [rbp-48h]

  v7 = this + 4;
  v30 = this + 4;
  UMSEnterCSWraper(&this[4]);
  v8 = &v7->Data4[4];
  v32 = &v7->Data4[4];
  if ( !*(_DWORD *)&v7->Data4[4] )
    *(_DWORD *)v7->Data4 = GetCurrentThreadId();
  ++*(_DWORD *)v8;
  v31 = v7 + 1;
  ++v7[1].Data1;
  v33 = v7;
  SetErrorInfo(0, 0);
  try
  {
    this[7] = IID_IDBCreateSession;
    *(_DWORD *)&this[264].Data2 = 0;
    if ( a2 )
    {
      v10 = Exit(-2147217886, 0);
      v11 = v10;
      if ( v10 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_180048A08[0] )
            bidTraceW(off_1800481E0[0], 126976, off_180048A08[0], (unsigned int)v10, 124);
        }
        ThrowHR(v11);
      }
    }
    else
    {
      v12 = (CPersistSession *)MMMAlloc(0x1248u, v9);
      v14 = v12;
      if ( v12 )
      {
        CPersistSession::CPersistSession(v12);
        *(_QWORD *)v14 = &ATL::CComObject<CPersistSession>::`vftable'{for `IOpenRowset'};
        *((_QWORD *)v14 + 1) = &ATL::CComObject<CPersistSession>::`vftable'{for `IGetDataSource'};
        *((_QWORD *)v14 + 2) = &ATL::CComObject<CPersistSession>::`vftable'{for `ISessionProperties'};
        *((_QWORD *)v14 + 3) = &ATL::CComObject<CPersistSession>::`vftable'{for `ISupportErrorInfo'};
        _InterlockedIncrement(&dword_1800454E8);
      }
      else
      {
        v14 = 0;
      }
      if ( !v14 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048A00[0] )
          bidTraceW(off_1800481E0[0], 137216, off_180048A00[0], 2147942414LL, 134);
        ThrowHR(-2147024882);
      }
      if ( (bidGblFlags & 2) != 0 && off_1800489F8[0] )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)this[287].Data4);
        v16 = CBidGenericBase::GetBidObjectID((CPersistSession *)((char *)v14 + 4536));
        bidTraceW(off_1800481E0[0], 142336, off_1800489F8[0], v16, BidObjectID);
      }
      v17 = CProviderSession::Init(v14, (struct IDSOCallBack *)this[-1].Data4, &this[311], v13);
      v18 = v17;
      if ( v17 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800489F0[0] )
          bidTraceW(off_1800481E0[0], 144384, off_1800489F0[0], (unsigned int)v17, 141);
        ThrowHR(v18);
      }
      v19 = (**(__int64 (__fastcall ***)(CPersistSession *, const struct _GUID *, struct IUnknown **))v14)(v14, a3, a4);
      v20 = v19;
      if ( v19 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800489E8[0] )
          bidTraceW(off_1800481E0[0], 146432, off_1800489E8[0], (unsigned int)v19, 143);
        ThrowHR(v20);
      }
    }
    ++*(_DWORD *)this[3].Data4;
  }
  catch ( long v29 )
  {
    v24 = Exit(v29, 0x88u);
    --v31->Data1;
    v21 = (*(_DWORD *)v32)-- == 1;
    v25 = v30;
    if ( v21 )
      *(_DWORD *)v30->Data4 = -1;
    v26 = *(_QWORD *)&v25->Data1;
    --*(_DWORD *)(v26 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v26 + 8));
    return v24;
  }
  catch ( ... )
  {
    --v31->Data1;
    v21 = (*(_DWORD *)v32)-- == 1;
    v27 = v30;
    if ( v21 )
      *(_DWORD *)v30->Data4 = -1;
    v28 = *(_QWORD *)&v27->Data1;
    --*(_DWORD *)(v28 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v28 + 8));
    return 2147500037LL;
  }
  --v7[1].Data1;
  v21 = (*(_DWORD *)v8)-- == 1;
  if ( v21 )
    *(_DWORD *)v7->Data4 = -1;
  v22 = *(_QWORD *)&v7->Data1;
  --*(_DWORD *)(v22 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v22 + 8));
  return 0;
}

```

## disassembly

```asm
0x180013f30  mov     [rsp+arg_10], r8
0x180013f35  push    rbx
0x180013f36  push    rsi
0x180013f37  push    rdi
0x180013f38  push    r12
0x180013f3a  push    r13
0x180013f3c  push    r14
0x180013f3e  push    r15
0x180013f40  sub     rsp, 60h
0x180013f44  mov     r13, r9
0x180013f47  mov     rbx, rdx
0x180013f4a  mov     rsi, rcx
0x180013f4d  lea     rdi, [rcx+40h]
0x180013f51  mov     [rsp+98h+var_60], rdi
0x180013f56  mov     rcx, rdi
0x180013f59  call    cs:__imp_UMSEnterCSWraper
0x180013f5f  lea     r14, [rdi+0Ch]
0x180013f63  mov     [rsp+98h+var_50], r14
0x180013f68  cmp     dword ptr [r14], 0
0x180013f6c  jnz     short loc_180013F77
0x180013f6e  call    cs:__imp_GetCurrentThreadId
0x180013f74  mov     [rdi+8], eax
0x180013f77  inc     dword ptr [r14]
0x180013f7a  lea     r12, [rdi+10h]
0x180013f7e  mov     [rsp+98h+var_58], r12
0x180013f83  inc     dword ptr [r12]
0x180013f87  mov     [rsp+98h+var_48], rdi
0x180013f8c  mov     [rsp+98h+arg_0], 88h
0x180013f97  xor     edx, edx; perrinfo
0x180013f99  xor     ecx, ecx; dwReserved
0x180013f9b  call    cs:__imp_SetErrorInfo
0x180013fa1  movups  xmm0, xmmword ptr cs:IID_IDBCreateSession.Data1
0x180013fa8  movdqu  xmmword ptr [rsi+70h], xmm0
0x180013fad  mov     dword ptr [rsi+1084h], 0
0x180013fb7  test    rbx, rbx
0x180013fba  jz      short loc_180014011
0x180013fbc  xor     edx, edx; unsigned int
0x180013fbe  mov     ecx, 80040E22h; int
0x180013fc3  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180013fc8  mov     ebx, eax
0x180013fca  test    eax, eax
0x180013fcc  jns     loc_1800141C6
0x180013fd2  test    byte ptr cs:_bidGblFlags, 2
0x180013fd9  jz      short loc_18001400A
0x180013fdb  mov     rcx, cs:off_180048A08; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x180013fe2  test    rcx, rcx
0x180013fe5  jz      short loc_18001400A
0x180013fe7  mov     [rsp+98h+var_78], 7Ch ; '|'
0x180013fef  mov     r9d, eax
0x180013ff2  mov     r8, cs:off_180048A08; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x180013ff9  mov     edx, 1F000h
0x180013ffe  mov     rcx, cs:off_1800481E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180014005  call    _bidTraceW
0x18001400a  mov     ecx, ebx; int
0x18001400c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180014011  mov     ecx, 1248h; unsigned int
0x180014016  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18001401b  mov     rbx, rax
0x18001401e  mov     [rsp+98h+arg_8], rax
0x180014026  test    rax, rax
0x180014029  jz      short loc_180014067
0x18001402b  mov     rcx, rax; this
0x18001402e  call    ??0CPersistSession@@QEAA@XZ; CPersistSession::CPersistSession(void)
0x180014033  lea     rax, ??_7?$CComObject@VCPersistSession@@@ATL@@6BIOpenRowset@@@; const ATL::CComObject<CPersistSession>::`vftable'{for `IOpenRowset'}
0x18001403a  mov     [rbx], rax
0x18001403d  lea     rax, ??_7?$CComObject@VCPersistSession@@@ATL@@6BIGetDataSource@@@; const ATL::CComObject<CPersistSession>::`vftable'{for `IGetDataSource'}
0x180014044  mov     [rbx+8], rax
0x180014048  lea     rax, ??_7?$CComObject@VCPersistSession@@@ATL@@6BISessionProperties@@@; const ATL::CComObject<CPersistSession>::`vftable'{for `ISessionProperties'}
0x18001404f  mov     [rbx+10h], rax
0x180014053  lea     rax, ??_7?$CComObject@VCPersistSession@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CPersistSession>::`vftable'{for `ISupportErrorInfo'}
0x18001405a  mov     [rbx+18h], rax
0x18001405e  lock inc cs:dword_1800454E8
0x180014065  jmp     short loc_180014069
0x180014067  xor     ebx, ebx
0x180014069  test    rbx, rbx
0x18001406c  jnz     short loc_1800140BE
0x18001406e  mov     [rsp+98h+arg_0], 8007000Eh
0x180014079  test    byte ptr cs:_bidGblFlags, 2
0x180014080  jz      short loc_1800140B4
0x180014082  mov     rax, cs:off_180048A00; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x180014089  test    rax, rax
0x18001408c  jz      short loc_1800140B4
0x18001408e  mov     [rsp+98h+var_78], 86h
0x180014096  mov     r9d, 8007000Eh
0x18001409c  mov     r8, cs:off_180048A00; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x1800140a3  mov     edx, 21800h
0x1800140a8  mov     rcx, cs:off_1800481E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800140af  call    _bidTraceW
0x1800140b4  mov     ecx, 8007000Eh; int
0x1800140b9  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800140be  test    byte ptr cs:_bidGblFlags, 2
0x1800140c5  jz      short loc_18001410E
0x1800140c7  mov     rax, cs:off_1800489F8; "<CPersistDSO::CreateSession|ADO|PERSIST"...
0x1800140ce  test    rax, rax
0x1800140d1  jz      short loc_18001410E
0x1800140d3  lea     rcx, [rsi+11F8h]; this
0x1800140da  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800140df  mov     r15d, eax
0x1800140e2  lea     rcx, [rbx+11B8h]; this
0x1800140e9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800140ee  mov     r8, cs:off_1800489F8; "<CPersistDSO::CreateSession|ADO|PERSIST"...
0x1800140f5  mov     rcx, cs:off_1800481E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800140fc  mov     [rsp+98h+var_78], r15d
0x180014101  mov     r9d, eax
0x180014104  mov     edx, 22C00h
0x180014109  call    _bidTraceW
0x18001410e  lea     r8, [rsi+1370h]; void *
0x180014115  lea     rdx, [rsi-8]; struct IDSOCallBack *
0x180014119  mov     rcx, rbx; this
0x18001411c  call    ?Init@CProviderSession@@QEAAJPEAUIDSOCallBack@@PEAXH@Z; CProviderSession::Init(IDSOCallBack *,void *,int)
0x180014121  mov     r15d, eax
0x180014124  test    eax, eax
0x180014126  jns     short loc_180014168
0x180014128  test    byte ptr cs:_bidGblFlags, 2
0x18001412f  jz      short loc_180014160
0x180014131  mov     rcx, cs:off_1800489F0; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x180014138  test    rcx, rcx
0x18001413b  jz      short loc_180014160
0x18001413d  mov     [rsp+98h+var_78], 8Dh
0x180014145  mov     r9d, eax
0x180014148  mov     r8, cs:off_1800489F0; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x18001414f  mov     edx, 23400h
0x180014154  mov     rcx, cs:off_1800481E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001415b  call    _bidTraceW
0x180014160  mov     ecx, r15d; int
0x180014163  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180014168  mov     rax, [rbx]
0x18001416b  mov     r8, r13
0x18001416e  mov     rdx, [rsp+98h+arg_10]
0x180014176  mov     rcx, rbx
0x180014179  mov     rax, [rax]
0x18001417c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014181  mov     ebx, eax
0x180014183  test    eax, eax
0x180014185  jns     short loc_1800141C6
0x180014187  test    byte ptr cs:_bidGblFlags, 2
0x18001418e  jz      short loc_1800141BF
0x180014190  mov     rcx, cs:off_1800489E8; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x180014197  test    rcx, rcx
0x18001419a  jz      short loc_1800141BF
0x18001419c  mov     [rsp+98h+var_78], 8Fh
0x1800141a4  mov     r9d, eax
0x1800141a7  mov     r8, cs:off_1800489E8; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x1800141ae  mov     edx, 23C00h
0x1800141b3  mov     rcx, cs:off_1800481E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800141ba  call    _bidTraceW
0x1800141bf  mov     ecx, ebx; int
0x1800141c1  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800141c6  inc     dword ptr [rsi+38h]
0x1800141c9  or      edx, 0FFFFFFFFh
0x1800141cc  add     [r12], edx
0x1800141d0  add     [r14], edx
0x1800141d3  jnz     short loc_1800141D8
0x1800141d5  mov     [rdi+8], edx
0x1800141d8  mov     rcx, [rdi]
0x1800141db  dec     dword ptr [rcx+30h]
0x1800141de  add     rcx, 8; lpCriticalSection
0x1800141e2  call    cs:__imp_LeaveCriticalSection
0x1800141e8  xor     eax, eax
0x1800141ea  jmp     short loc_18001425D
0x1800141ec  mov     edx, [rsp+98h+arg_0]; unsigned int
0x1800141f3  mov     ecx, [rsp+98h+var_68]; int
0x1800141f7  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800141fc  mov     ebx, eax
0x1800141fe  or      edx, 0FFFFFFFFh
0x180014201  mov     rcx, [rsp+98h+var_58]
0x180014206  add     [rcx], edx
0x180014208  mov     rcx, [rsp+98h+var_50]
0x18001420d  add     [rcx], edx
0x18001420f  mov     rcx, [rsp+98h+var_60]
0x180014214  jnz     short loc_180014219
0x180014216  mov     [rcx+8], edx
0x180014219  mov     rcx, [rcx]
0x18001421c  dec     dword ptr [rcx+30h]
0x18001421f  add     rcx, 8; lpCriticalSection
0x180014223  call    cs:__imp_LeaveCriticalSection
0x180014229  mov     eax, ebx
0x18001422b  jmp     short loc_18001425D
0x18001422d  or      edx, 0FFFFFFFFh
0x180014230  mov     rax, [rsp+98h+var_58]
0x180014235  add     [rax], edx
0x180014237  mov     rax, [rsp+98h+var_50]
0x18001423c  add     [rax], edx
0x18001423e  mov     rcx, [rsp+98h+var_60]
0x180014243  jnz     short loc_180014248
0x180014245  mov     [rcx+8], edx
0x180014248  mov     rcx, [rcx]
0x18001424b  dec     dword ptr [rcx+30h]
0x18001424e  add     rcx, 8; lpCriticalSection
0x180014252  call    cs:__imp_LeaveCriticalSection
0x180014258  mov     eax, 80004005h
0x18001425d  add     rsp, 60h
0x180014261  pop     r15
0x180014263  pop     r14
0x180014265  pop     r13
0x180014267  pop     r12
0x180014269  pop     rdi
0x18001426a  pop     rsi
0x18001426b  pop     rbx
0x18001426c  retn
```
