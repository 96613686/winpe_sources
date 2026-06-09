# CBindingCallback::OnStopBinding(long,ushort const *)

- ea: `0x180021160`
- end: `0x180021671`
- name: `?OnStopBinding@CBindingCallback@@UEAAJJPEBG@Z`
- size: `1297`
- prototype: `__int64 __fastcall(CBindingCallback *__hidden this, int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180001d94`
- `0x180002650`
- `0x18000266c`
- `0x1800027c0`
- `0x18001a6c8`
- `0x180021160`
- `0x18002cd54`
- `0x18002e060`
- `0x18002e120`
- `0x180030010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18002144c`
- `KERNEL32!MultiByteToWideChar` at `0x18002144c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800215a3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800215a3`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18002149b`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18002149b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CBindingCallback::OnStopBinding(CBindingCallback *this, unsigned int a2, const unsigned __int16 *a3)
{
  unsigned int v3; // r12d
  _QWORD *v4; // r15
  int v5; // eax
  int v6; // edi
  int v7; // eax
  int v8; // edi
  int v9; // eax
  unsigned int v10; // edx
  int v11; // edi
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  void *v14; // rsp
  void *v15; // rsp
  CHAR *v16; // rsi
  unsigned __int64 v17; // rax
  __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  CHAR *lpWideCharStr; // r14
  unsigned __int128 v23; // rax
  int v24; // eax
  int v25; // edi
  int v26; // eax
  int v27; // edi
  HRESULT v28; // eax
  int v29; // edi
  int v30; // eax
  int v31; // edi
  int v32; // eax
  int v33; // edi
  HRESULT v34; // eax
  int v35; // edi
  CHAR MultiByteStr[4]; // [rsp+40h] [rbp+0h] BYREF
  int v38; // [rsp+44h] [rbp+4h] BYREF
  __int64 v39; // [rsp+48h] [rbp+8h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+50h] [rbp+10h] BYREF
  IErrorInfo *perrinfo; // [rsp+58h] [rbp+18h] BYREF
  CHAR *v42; // [rsp+60h] [rbp+20h] BYREF
  CHAR *v43; // [rsp+68h] [rbp+28h] BYREF
  char *v44; // [rsp+70h] [rbp+30h]
  __int64 v45; // [rsp+78h] [rbp+38h] BYREF

  try
  {
    v3 = a2;
    v39 = 0;
    pperrinfo = 0;
    perrinfo = 0;
    v38 = 0;
    *(_DWORD *)MultiByteStr = 0;
    v4 = (_QWORD *)((char *)this + 24);
    v44 = (char *)this + 24;
    v5 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
           *((_QWORD *)this + 3),
           &IID_IWinInetHttpInfo,
           &v39);
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180048BE8[0] )
          bidTraceW(off_1800481F8[0], 441344, off_180048BE8[0], (unsigned int)v5, 431);
      }
      ThrowHR(v6);
    }
    *(_DWORD *)MultiByteStr = 4;
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, int *, CHAR *, _QWORD, _QWORD))(*(_QWORD *)v39 + 32LL))(
           v39,
           536870931,
           &v38,
           MultiByteStr,
           0,
           0);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048BE0[0] )
        bidTraceW(off_1800481F8[0], 445440, off_180048BE0[0], (unsigned int)v7, 435);
      ThrowHR(v8);
    }
    if ( v38 == 500 )
    {
      *(_DWORD *)MultiByteStr = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, CHAR *, _QWORD, _QWORD))(*(_QWORD *)v39 + 32LL))(
             v39,
             20,
             0,
             MultiByteStr,
             0,
             0);
      v11 = v9;
      if ( v9 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048BD8[0] )
          bidTraceW(off_1800481F8[0], 456704, off_180048BD8[0], (unsigned int)v9, 446);
        ThrowHR(v11);
      }
      if ( *(_DWORD *)MultiByteStr > 1u )
      {
        v43 = 0;
        if ( *(_DWORD *)MultiByteStr > 0x400u )
        {
          v16 = (CHAR *)MMMAlloc(*(unsigned int *)MultiByteStr, v10);
          v43 = v16;
        }
        else
        {
          v12 = *(unsigned int *)MultiByteStr + 15LL;
          if ( v12 <= *(unsigned int *)MultiByteStr )
            v12 = 0xFFFFFFFFFFFFFF0LL;
          v13 = v12 & 0xFFFFFFFFFFFFFFF0uLL;
          v14 = alloca(v13);
          v15 = alloca(v13);
          v16 = MultiByteStr;
        }
        OnNullThrowOOM(v16);
        v42 = 0;
        if ( *(_DWORD *)MultiByteStr > 0x200u )
        {
          v23 = *(unsigned int *)MultiByteStr * (unsigned __int128)2uLL;
          if ( !is_mul_ok(*(unsigned int *)MultiByteStr, 2u) )
            LODWORD(v23) = -1;
          lpWideCharStr = (CHAR *)MMMAlloc(v23, DWORD2(v23));
          v42 = lpWideCharStr;
        }
        else
        {
          v17 = 2LL * *(unsigned int *)MultiByteStr;
          v18 = v17 + 15;
          if ( v17 + 15 < v17 )
            v18 = 0xFFFFFFFFFFFFFF0LL;
          v19 = v18 & 0xFFFFFFFFFFFFFFF0uLL;
          v20 = alloca(v19);
          v21 = alloca(v19);
          lpWideCharStr = MultiByteStr;
        }
        OnNullThrowOOM(lpWideCharStr);
        v16[*(_DWORD *)MultiByteStr - 1] = 0;
        v24 = (*(__int64 (__fastcall **)(__int64, __int64, CHAR *, CHAR *, _QWORD, _QWORD))(*(_QWORD *)v39 + 32LL))(
                v39,
                20,
                v16,
                MultiByteStr,
                0,
                0);
        v25 = v24;
        if ( v24 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048BD0[0] )
            bidTraceW(off_1800481F8[0], 466944, off_180048BD0[0], (unsigned int)v24, 456);
          ThrowHR(v25);
        }
        v26 = MultiByteToWideChar(
                0,
                0,
                v16,
                *(_DWORD *)MultiByteStr + 1,
                (LPWSTR)lpWideCharStr,
                *(_DWORD *)MultiByteStr + 1);
        v27 = v26;
        if ( v26 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048BC8[0] )
            bidTraceW(off_1800481F8[0], 471040, off_180048BC8[0], (unsigned int)v26, 460);
          ThrowHR(v27);
        }
        v28 = CreateErrorInfo(&pperrinfo);
        v29 = v28;
        if ( v28 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048BC0[0] )
            bidTraceW(off_1800481F8[0], 479232, off_180048BC0[0], (unsigned int)v28, 468);
          ThrowHR(v29);
        }
        v30 = ((__int64 (__fastcall *)(ICreateErrorInfo *, CHAR *))pperrinfo->lpVtbl->SetDescription)(
                pperrinfo,
                lpWideCharStr);
        v31 = v30;
        if ( v30 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048BB8[0] )
            bidTraceW(off_1800481F8[0], 480256, off_180048BB8[0], (unsigned int)v30, 469);
          ThrowHR(v31);
        }
        v32 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
                pperrinfo,
                &IID_IErrorInfo,
                &perrinfo);
        v33 = v32;
        if ( v32 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048BB0[0] )
            bidTraceW(off_1800481F8[0], 481280, off_180048BB0[0], (unsigned int)v32, 470);
          ThrowHR(v33);
        }
        v34 = SetErrorInfo(0, perrinfo);
        v35 = v34;
        if ( v34 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048BA8[0] )
            bidTraceW(off_1800481F8[0], 482304, off_180048BA8[0], (unsigned int)v34, 471);
          ThrowHR(v35);
        }
        CAutoP<_GUID>::~CAutoP<_GUID>(&v42);
        CAutoP<_GUID>::~CAutoP<_GUID>(&v43);
      }
    }
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&perrinfo);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&pperrinfo);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v39);
  }
  catch ( long v45 )
  {
    v3 = a2;
    v4 = v44;
  }
  if ( *v4 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 16LL))(*v4);
    *v4 = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180021160  mov     [rsp-8+arg_8], edx
0x180021164  push    rbp
0x180021165  push    rdi
0x180021166  push    r12
0x180021168  push    r14
0x18002116a  push    r15
0x18002116c  sub     rsp, 90h
0x180021173  lea     rbp, [rsp+40h]
0x180021178  mov     [rbp+70h+arg_0], rbx
0x18002117f  mov     [rbp+70h+arg_10], rsi
0x180021186  mov     rax, cs:__security_cookie
0x18002118d  xor     rax, rbp
0x180021190  mov     [rbp+70h+var_30], rax
0x180021194  mov     r12d, edx
0x180021197  xor     ebx, ebx
0x180021199  mov     [rbp+70h+var_68], rbx
0x18002119d  mov     [rbp+70h+pperrinfo], rbx
0x1800211a1  mov     [rbp+70h+perrinfo], rbx
0x1800211a5  mov     [rbp+70h+var_6C], ebx
0x1800211a8  mov     dword ptr [rbp+70h+MultiByteStr], ebx
0x1800211ab  lea     r15, [rcx+18h]
0x1800211af  mov     [rbp+70h+var_40], r15
0x1800211b3  mov     rcx, [r15]
0x1800211b6  mov     rax, [rcx]
0x1800211b9  lea     r8, [rbp+70h+var_68]
0x1800211bd  lea     rdx, IID_IWinInetHttpInfo
0x1800211c4  mov     rax, [rax]
0x1800211c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211cc  mov     edi, eax
0x1800211ce  test    eax, eax
0x1800211d0  jns     short loc_180021211
0x1800211d2  test    byte ptr cs:_bidGblFlags, 2
0x1800211d9  jz      short loc_18002120A
0x1800211db  mov     rcx, cs:off_180048BE8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x1800211e2  test    rcx, rcx
0x1800211e5  jz      short loc_18002120A
0x1800211e7  mov     dword ptr [rsp+0B0h+lpWideCharStr], 1AFh
0x1800211ef  mov     r9d, eax
0x1800211f2  mov     r8, cs:off_180048BE8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x1800211f9  mov     edx, 6BC00h
0x1800211fe  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180021205  call    _bidTraceW
0x18002120a  mov     ecx, edi; int
0x18002120c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180021211  mov     dword ptr [rbp+70h+MultiByteStr], 4
0x180021218  mov     rcx, [rbp+70h+var_68]
0x18002121c  mov     rax, [rcx]
0x18002121f  mov     qword ptr [rsp+0B0h+cchWideChar], rbx
0x180021224  mov     [rsp+0B0h+lpWideCharStr], rbx
0x180021229  lea     r9, [rbp+70h+MultiByteStr]
0x18002122d  lea     r8, [rbp+70h+var_6C]
0x180021231  mov     edx, 20000013h
0x180021236  mov     rax, [rax+20h]
0x18002123a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002123f  mov     edi, eax
0x180021241  test    eax, eax
0x180021243  jns     short loc_180021284
0x180021245  test    byte ptr cs:_bidGblFlags, 2
0x18002124c  jz      short loc_18002127D
0x18002124e  mov     rcx, cs:off_180048BE0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180021255  test    rcx, rcx
0x180021258  jz      short loc_18002127D
0x18002125a  mov     dword ptr [rsp+0B0h+lpWideCharStr], 1B3h
0x180021262  mov     r9d, eax
0x180021265  mov     r8, cs:off_180048BE0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x18002126c  mov     edx, 6CC00h
0x180021271  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180021278  call    _bidTraceW
0x18002127d  mov     ecx, edi; int
0x18002127f  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180021284  cmp     [rbp+70h+var_6C], 1F4h
0x18002128b  jnz     loc_180021603
0x180021291  mov     dword ptr [rbp+70h+MultiByteStr], ebx
0x180021294  mov     rcx, [rbp+70h+var_68]
0x180021298  mov     rax, [rcx]
0x18002129b  mov     qword ptr [rsp+0B0h+cchWideChar], rbx
0x1800212a0  mov     [rsp+0B0h+lpWideCharStr], rbx
0x1800212a5  lea     r9, [rbp+70h+MultiByteStr]
0x1800212a9  xor     r8d, r8d
0x1800212ac  lea     edx, [r8+14h]
0x1800212b0  mov     rax, [rax+20h]
0x1800212b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212b9  mov     edi, eax
0x1800212bb  test    eax, eax
0x1800212bd  jns     short loc_1800212FE
0x1800212bf  test    byte ptr cs:_bidGblFlags, 2
0x1800212c6  jz      short loc_1800212F7
0x1800212c8  mov     rcx, cs:off_180048BD8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x1800212cf  test    rcx, rcx
0x1800212d2  jz      short loc_1800212F7
0x1800212d4  mov     dword ptr [rsp+0B0h+lpWideCharStr], 1BEh
0x1800212dc  mov     r9d, eax
0x1800212df  mov     r8, cs:off_180048BD8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x1800212e6  mov     edx, 6F800h
0x1800212eb  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800212f2  call    _bidTraceW
0x1800212f7  mov     ecx, edi; int
0x1800212f9  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800212fe  mov     ecx, dword ptr [rbp+70h+MultiByteStr]; unsigned int
0x180021301  cmp     ecx, 1
0x180021304  jbe     loc_180021603
0x18002130a  mov     [rbp+70h+var_48], rbx
0x18002130e  cmp     ecx, 400h
0x180021314  ja      short loc_180021344
0x180021316  mov     eax, ecx
0x180021318  add     rcx, 0Fh
0x18002131c  mov     rdi, 0FFFFFFFFFFFFFF0h
0x180021326  cmp     rcx, rax
0x180021329  ja      short loc_18002132E
0x18002132b  mov     rcx, rdi
0x18002132e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180021332  mov     rax, rcx
0x180021335  call    _alloca_probe
0x18002133a  sub     rsp, rcx
0x18002133d  lea     rsi, [rsp+0B0h+MultiByteStr]
0x180021342  jmp     short loc_18002135A
0x180021344  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180021349  mov     rsi, rax
0x18002134c  mov     [rbp+70h+var_48], rax
0x180021350  mov     rdi, 0FFFFFFFFFFFFFF0h
0x18002135a  mov     rcx, rsi; void *
0x18002135d  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180021362  mov     [rbp+70h+var_50], rbx
0x180021366  mov     eax, dword ptr [rbp+70h+MultiByteStr]
0x180021369  cmp     eax, 200h
0x18002136e  ja      short loc_180021395
0x180021370  add     rax, rax
0x180021373  lea     rcx, [rax+0Fh]
0x180021377  cmp     rcx, rax
0x18002137a  ja      short loc_18002137F
0x18002137c  mov     rcx, rdi
0x18002137f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180021383  mov     rax, rcx
0x180021386  call    _alloca_probe
0x18002138b  sub     rsp, rcx
0x18002138e  lea     r14, [rsp+0B0h+MultiByteStr]
0x180021393  jmp     short loc_1800213B9
0x180021395  mov     rcx, rax
0x180021398  mov     eax, 2
0x18002139d  mul     rcx
0x1800213a0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800213a7  cmovb   rax, rcx
0x1800213ab  mov     ecx, eax; unsigned int
0x1800213ad  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800213b2  mov     r14, rax
0x1800213b5  mov     [rbp+70h+var_50], rax
0x1800213b9  mov     rcx, r14; void *
0x1800213bc  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800213c1  mov     eax, dword ptr [rbp+70h+MultiByteStr]
0x1800213c4  dec     eax
0x1800213c6  mov     [rax+rsi], bl
0x1800213c9  mov     rcx, [rbp+70h+var_68]
0x1800213cd  mov     rax, [rcx]
0x1800213d0  mov     qword ptr [rsp+0B0h+cchWideChar], rbx
0x1800213d5  mov     [rsp+0B0h+lpWideCharStr], rbx
0x1800213da  lea     r9, [rbp+70h+MultiByteStr]
0x1800213de  mov     r8, rsi
0x1800213e1  mov     edx, 14h
0x1800213e6  mov     rax, [rax+20h]
0x1800213ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213ef  mov     edi, eax
0x1800213f1  test    eax, eax
0x1800213f3  jns     short loc_180021434
0x1800213f5  test    byte ptr cs:_bidGblFlags, 2
0x1800213fc  jz      short loc_18002142D
0x1800213fe  mov     rcx, cs:off_180048BD0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180021405  test    rcx, rcx
0x180021408  jz      short loc_18002142D
0x18002140a  mov     dword ptr [rsp+0B0h+lpWideCharStr], 1C8h
0x180021412  mov     r9d, eax
0x180021415  mov     r8, cs:off_180048BD0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x18002141c  mov     edx, 72000h
0x180021421  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180021428  call    _bidTraceW
0x18002142d  mov     ecx, edi; int
0x18002142f  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180021434  mov     r9d, dword ptr [rbp+70h+MultiByteStr]
0x180021438  inc     r9d; cbMultiByte
0x18002143b  mov     [rsp+0B0h+cchWideChar], r9d; cchWideChar
0x180021440  mov     [rsp+0B0h+lpWideCharStr], r14; lpWideCharStr
0x180021445  mov     r8, rsi; lpMultiByteStr
0x180021448  xor     edx, edx; dwFlags
0x18002144a  xor     ecx, ecx; CodePage
0x18002144c  call    cs:__imp_MultiByteToWideChar
0x180021452  mov     edi, eax
0x180021454  test    eax, eax
0x180021456  jns     short loc_180021497
0x180021458  test    byte ptr cs:_bidGblFlags, 2
0x18002145f  jz      short loc_180021490
0x180021461  mov     rcx, cs:off_180048BC8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180021468  test    rcx, rcx
0x18002146b  jz      short loc_180021490
0x18002146d  mov     dword ptr [rsp+0B0h+lpWideCharStr], 1CCh
0x180021475  mov     r9d, eax
0x180021478  mov     r8, cs:off_180048BC8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x18002147f  mov     edx, 73000h
0x180021484  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002148b  call    _bidTraceW
0x180021490  mov     ecx, edi; int
0x180021492  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180021497  lea     rcx, [rbp+70h+pperrinfo]; pperrinfo
0x18002149b  call    cs:__imp_CreateErrorInfo
0x1800214a1  mov     edi, eax
0x1800214a3  test    eax, eax
0x1800214a5  jns     short loc_1800214E6
0x1800214a7  test    byte ptr cs:_bidGblFlags, 2
0x1800214ae  jz      short loc_1800214DF
0x1800214b0  mov     rcx, cs:off_180048BC0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x1800214b7  test    rcx, rcx
0x1800214ba  jz      short loc_1800214DF
0x1800214bc  mov     dword ptr [rsp+0B0h+lpWideCharStr], 1D4h
0x1800214c4  mov     r9d, eax
0x1800214c7  mov     r8, cs:off_180048BC0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x1800214ce  mov     edx, 75000h
0x1800214d3  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800214da  call    _bidTraceW
0x1800214df  mov     ecx, edi; int
0x1800214e1  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800214e6  mov     rcx, [rbp+70h+pperrinfo]
0x1800214ea  mov     rax, [rcx]
0x1800214ed  mov     rdx, r14
0x1800214f0  mov     rax, [rax+28h]
0x1800214f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214f9  mov     edi, eax
0x1800214fb  test    eax, eax
0x1800214fd  jns     short loc_18002153E
0x1800214ff  test    byte ptr cs:_bidGblFlags, 2
0x180021506  jz      short loc_180021537
0x180021508  mov     rcx, cs:off_180048BB8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x18002150f  test    rcx, rcx
0x180021512  jz      short loc_180021537
0x180021514  mov     dword ptr [rsp+0B0h+lpWideCharStr], 1D5h
0x18002151c  mov     r9d, eax
0x18002151f  mov     r8, cs:off_180048BB8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180021526  mov     edx, 75400h
0x18002152b  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180021532  call    _bidTraceW
0x180021537  mov     ecx, edi; int
0x180021539  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002153e  mov     rcx, [rbp+70h+pperrinfo]
0x180021542  mov     rax, [rcx]
0x180021545  lea     r8, [rbp+70h+perrinfo]
0x180021549  lea     rdx, IID_IErrorInfo
0x180021550  mov     rax, [rax]
0x180021553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021558  mov     edi, eax
0x18002155a  test    eax, eax
0x18002155c  jns     short loc_18002159D
0x18002155e  test    byte ptr cs:_bidGblFlags, 2
0x180021565  jz      short loc_180021596
0x180021567  mov     rcx, cs:off_180048BB0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x18002156e  test    rcx, rcx
0x180021571  jz      short loc_180021596
0x180021573  mov     dword ptr [rsp+0B0h+lpWideCharStr], 1D6h
0x18002157b  mov     r9d, eax
0x18002157e  mov     r8, cs:off_180048BB0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180021585  mov     edx, 75800h
0x18002158a  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180021591  call    _bidTraceW
0x180021596  mov     ecx, edi; int
0x180021598  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002159d  mov     rdx, [rbp+70h+perrinfo]; perrinfo
0x1800215a1  xor     ecx, ecx; dwReserved
0x1800215a3  call    cs:__imp_SetErrorInfo
0x1800215a9  mov     edi, eax
0x1800215ab  test    eax, eax
0x1800215ad  jns     short loc_1800215EF
0x1800215af  test    byte ptr cs:_bidGblFlags, 2
0x1800215b6  jz      short loc_1800215E7
0x1800215b8  mov     rcx, cs:off_180048BA8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x1800215bf  test    rcx, rcx
0x1800215c2  jz      short loc_1800215E7
0x1800215c4  mov     dword ptr [rsp+0B0h+lpWideCharStr], 1D7h
0x1800215cc  mov     r9d, eax
0x1800215cf  mov     r8, cs:off_180048BA8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x1800215d6  mov     edx, 75C00h
0x1800215db  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800215e2  call    _bidTraceW
0x1800215e7  mov     ecx, edi; int
0x1800215e9  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800215ef  lea     rcx, [rbp+70h+var_50]
0x1800215f3  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x1800215f8  nop
0x1800215f9  lea     rcx, [rbp+70h+var_48]
0x1800215fd  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x180021602  nop
0x180021603  lea     rcx, [rbp+70h+perrinfo]
0x180021607  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002160c  nop
0x18002160d  lea     rcx, [rbp+70h+pperrinfo]
0x180021611  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180021616  nop
0x180021617  lea     rcx, [rbp+70h+var_68]
0x18002161b  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180021620  nop
0x180021621  jmp     short loc_180021630
0x180021623  xor     ebx, ebx
0x180021625  mov     r12d, [rbp+70h+arg_8]
0x18002162c  mov     r15, [rbp+70h+var_40]
0x180021630  mov     rcx, [r15]
  ... truncated ...
```
