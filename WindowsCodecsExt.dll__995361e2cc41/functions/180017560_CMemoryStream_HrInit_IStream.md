# CMemoryStream::HrInit(IStream *)

- ea: `0x180017560`
- end: `0x18001783a`
- name: `?HrInit@CMemoryStream@@QEAAJPEAUIStream@@@Z`
- size: `730`
- prototype: `__int64 __fastcall(CMemoryStream *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180008f24`

## callees

- `0x180011088`
- `0x180012178`
- `0x180012afc`
- `0x1800171c4`
- `0x180017560`
- `0x180021a30`
- `0x180022348`
- `0x18002b694`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800176d6`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800176d6`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x1800175fe`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x180017796`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x1800175fe`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x180017796`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001761b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001761b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800177e3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800177e3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800177ab`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800177ab`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180017610`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180017610`

## pseudocode

```c
__int64 __fastcall CMemoryStream::HrInit(CMemoryStream *this, struct IStream *a2)
{
  unsigned int v4; // ebx
  int v5; // ecx
  HRESULT HGlobalFromStream; // eax
  __int64 v8; // rax
  ULONGLONG v9; // rax
  LPVOID v10; // rbx
  unsigned int v11; // [rsp+30h] [rbp-D0h] BYREF
  HGLOBAL phglobal; // [rsp+38h] [rbp-C8h] BYREF
  ULONG pulResult; // [rsp+40h] [rbp-C0h] BYREF
  LPSTREAM pstm; // [rsp+48h] [rbp-B8h] BYREF
  int v15; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v16[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v17[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[16]; // [rsp+70h] [rbp-90h] BYREF
  ULONGLONG ullOperand; // [rsp+80h] [rbp-80h]
  _BYTE v20[1024]; // [rsp+C0h] [rbp-40h] BYREF

  CGuard<IGuardableStream>::CGuard<IGuardableStream>(v17, (char *)this + 16);
  v11 = 0;
  v15 = 0;
  phglobal = 0;
  memset_0(v18, 0, 0x50u);
  pstm = 0;
  if ( a2 )
  {
    CMemoryStream::HrClose(this);
    HGlobalFromStream = (*(__int64 (__fastcall **)(struct IStream *, _BYTE *, __int64))(*(_QWORD *)a2 + 96LL))(
                          a2,
                          v18,
                          1);
    v4 = HGlobalFromStream;
    if ( HGlobalFromStream < 0
      || (HGlobalFromStream = ULongLongToULong(ullOperand, &pulResult), v4 = HGlobalFromStream, HGlobalFromStream < 0)
      || (pulResult = 0,
          HGlobalFromStream = CreateStreamOnHGlobal(0, 0, &pstm),
          v4 = HGlobalFromStream,
          HGlobalFromStream < 0)
      || (HGlobalFromStream = (*(__int64 (__fastcall **)(LPSTREAM, ULONGLONG))(*(_QWORD *)pstm + 48LL))(
                                pstm,
                                ullOperand),
          v4 = HGlobalFromStream,
          HGlobalFromStream < 0) )
    {
LABEL_15:
      if ( !g_doStackCaptures )
        goto LABEL_6;
LABEL_16:
      v5 = HGlobalFromStream;
      goto LABEL_5;
    }
    do
    {
      v8 = *(_QWORD *)a2;
      v11 = 0;
      HGlobalFromStream = (*(__int64 (__fastcall **)(struct IStream *, _BYTE *, __int64, unsigned int *))(v8 + 24))(
                            a2,
                            v20,
                            1024,
                            &v11);
      v4 = HGlobalFromStream;
      if ( HGlobalFromStream < 0 )
      {
        if ( g_doStackCaptures )
          goto LABEL_16;
        goto LABEL_6;
      }
      if ( !v11 )
        break;
      v15 = 0;
      HGlobalFromStream = (*(__int64 (__fastcall **)(LPSTREAM, _BYTE *, _QWORD, int *))(*(_QWORD *)pstm + 32LL))(
                            pstm,
                            v20,
                            v11,
                            &v15);
      v4 = HGlobalFromStream;
      if ( HGlobalFromStream < 0 )
      {
        if ( g_doStackCaptures )
          goto LABEL_16;
        goto LABEL_6;
      }
    }
    while ( v11 );
    HGlobalFromStream = GetHGlobalFromStream(pstm, &phglobal);
    v4 = HGlobalFromStream;
    if ( HGlobalFromStream < 0 )
      goto LABEL_15;
    v9 = GlobalSize(phglobal);
    if ( !v9 )
    {
      if ( !v11 )
      {
        v4 = -2003292302;
        goto LABEL_3;
      }
LABEL_34:
      v4 = -2147024882;
      goto LABEL_3;
    }
    HGlobalFromStream = ULongLongToULong(v9, &pulResult);
    v4 = HGlobalFromStream;
    if ( HGlobalFromStream < 0 )
      goto LABEL_15;
    v10 = GlobalLock(phglobal);
    if ( !v10 )
      goto LABEL_34;
    CGuard<IGuardableStream>::CGuard<IGuardableStream>(v16, (char *)this + 16);
    CMemoryStream::HrClose(this);
    *((_DWORD *)this + 30) = pulResult;
    *((_QWORD *)this + 14) = v10;
    CGuard<IGuardableStream>::~CGuard<IGuardableStream>(v16);
    v4 = 0;
    *((_QWORD *)this + 16) = phglobal;
  }
  else
  {
    v4 = -2147024809;
LABEL_3:
    if ( g_doStackCaptures )
    {
      v5 = v4;
LABEL_5:
      DoStackCapture(v5);
    }
LABEL_6:
    if ( phglobal || pstm && (GetHGlobalFromStream(pstm, &phglobal), phglobal) )
    {
      GlobalUnlock(phglobal);
      GlobalFree(phglobal);
    }
    *((_QWORD *)this + 16) = 0;
  }
  if ( pstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)pstm + 16LL))(pstm);
    pstm = 0;
  }
  CGuard<IGuardableStream>::~CGuard<IGuardableStream>(v17);
  return v4;
}

```

## disassembly

```asm
0x180017560  mov     [rsp-8+arg_10], rbx
0x180017565  push    rbp
0x180017566  push    rsi
0x180017567  push    rdi
0x180017568  push    r14
0x18001756a  push    r15
0x18001756c  lea     rbp, [rsp-3D0h]
0x180017574  sub     rsp, 4D0h
0x18001757b  mov     rax, cs:__security_cookie
0x180017582  xor     rax, rsp
0x180017585  mov     [rbp+3F0h+var_30], rax
0x18001758c  mov     rsi, rdx
0x18001758f  mov     rdi, rcx
0x180017592  lea     rdx, [rcx+10h]
0x180017596  lea     rcx, [rsp+4F0h+var_490]
0x18001759b  call    ??0?$CGuard@VIGuardableStream@@@@QEAA@AEAVIGuardableStream@@@Z; CGuard<IGuardableStream>::CGuard<IGuardableStream>(IGuardableStream &)
0x1800175a0  xor     r15d, r15d
0x1800175a3  lea     rcx, [rsp+4F0h+var_480]; void *
0x1800175a8  xor     edx, edx; Val
0x1800175aa  mov     [rsp+4F0h+var_4C0], r15d
0x1800175af  mov     [rsp+4F0h+var_4A0], r15d
0x1800175b4  mov     [rsp+4F0h+phglobal], r15
0x1800175b9  lea     r8d, [r15+50h]; Size
0x1800175bd  call    memset_0
0x1800175c2  mov     [rsp+4F0h+pstm], r15
0x1800175c7  test    rsi, rsi
0x1800175ca  jnz     loc_180017678
0x1800175d0  mov     ebx, 80070057h
0x1800175d5  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800175dc  jz      short loc_1800175E5
0x1800175de  mov     ecx, ebx; int
0x1800175e0  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800175e5  cmp     [rsp+4F0h+phglobal], r15
0x1800175ea  jnz     short loc_18001760B
0x1800175ec  mov     r8, [rsp+4F0h+pstm]
0x1800175f1  test    r8, r8
0x1800175f4  jz      short loc_180017621
0x1800175f6  lea     rdx, [rsp+4F0h+phglobal]; phglobal
0x1800175fb  mov     rcx, r8; pstm
0x1800175fe  call    cs:__imp_GetHGlobalFromStream
0x180017604  cmp     [rsp+4F0h+phglobal], r15
0x180017609  jz      short loc_180017621
0x18001760b  mov     rcx, [rsp+4F0h+phglobal]; hMem
0x180017610  call    cs:__imp_GlobalUnlock
0x180017616  mov     rcx, [rsp+4F0h+phglobal]; hMem
0x18001761b  call    cs:__imp_GlobalFree
0x180017621  mov     [rdi+80h], r15
0x180017628  mov     r8, [rsp+4F0h+pstm]
0x18001762d  test    r8, r8
0x180017630  jz      short loc_180017646
0x180017632  mov     rcx, [r8]
0x180017635  mov     rax, [rcx+10h]
0x180017639  mov     rcx, r8
0x18001763c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017641  mov     [rsp+4F0h+pstm], r15
0x180017646  lea     rcx, [rsp+4F0h+var_490]
0x18001764b  call    ??1?$CGuard@VIGuardableStream@@@@QEAA@XZ; CGuard<IGuardableStream>::~CGuard<IGuardableStream>(void)
0x180017650  mov     eax, ebx
0x180017652  mov     rcx, [rbp+3F0h+var_30]
0x180017659  xor     rcx, rsp; StackCookie
0x18001765c  call    __security_check_cookie
0x180017661  mov     rbx, [rsp+4F0h+arg_10]
0x180017669  add     rsp, 4D0h
0x180017670  pop     r15
0x180017672  pop     r14
0x180017674  pop     rdi
0x180017675  pop     rsi
0x180017676  pop     rbp
0x180017677  retn
0x180017678  mov     rcx, rdi; this
0x18001767b  call    ?HrClose@CMemoryStream@@AEAAJXZ; CMemoryStream::HrClose(void)
0x180017680  mov     rax, [rsi]
0x180017683  lea     rdx, [rsp+4F0h+var_480]
0x180017688  mov     r8d, 1
0x18001768e  mov     rcx, rsi
0x180017691  mov     rax, [rax+60h]
0x180017695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001769a  mov     ebx, eax
0x18001769c  test    eax, eax
0x18001769e  jns     short loc_1800176B4
0x1800176a0  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800176a7  jz      loc_1800175E5
0x1800176ad  mov     ecx, eax
0x1800176af  jmp     loc_1800175E0
0x1800176b4  mov     rcx, [rbp+3F0h+ullOperand]; ullOperand
0x1800176b8  lea     rdx, [rsp+4F0h+pulResult]; pulResult
0x1800176bd  call    ULongLongToULong
0x1800176c2  mov     ebx, eax
0x1800176c4  test    eax, eax
0x1800176c6  js      short loc_1800176A0
0x1800176c8  lea     r8, [rsp+4F0h+pstm]; ppstm
0x1800176cd  mov     [rsp+4F0h+pulResult], r15d
0x1800176d2  xor     edx, edx; fDeleteOnRelease
0x1800176d4  xor     ecx, ecx; hGlobal
0x1800176d6  call    cs:__imp_CreateStreamOnHGlobal
0x1800176dc  mov     ebx, eax
0x1800176de  test    eax, eax
0x1800176e0  js      short loc_1800176A0
0x1800176e2  mov     rcx, [rsp+4F0h+pstm]
0x1800176e7  mov     rdx, [rbp+3F0h+ullOperand]
0x1800176eb  mov     rax, [rcx]
0x1800176ee  mov     rax, [rax+30h]
0x1800176f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176f7  mov     ebx, eax
0x1800176f9  test    eax, eax
0x1800176fb  js      short loc_1800176A0
0x1800176fd  mov     rax, [rsi]
0x180017700  lea     r9, [rsp+4F0h+var_4C0]
0x180017705  mov     r8d, 400h
0x18001770b  mov     [rsp+4F0h+var_4C0], r15d
0x180017710  lea     rdx, [rbp+3F0h+var_430]
0x180017714  mov     rcx, rsi
0x180017717  mov     rax, [rax+18h]
0x18001771b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017720  mov     ebx, eax
0x180017722  test    eax, eax
0x180017724  jns     short loc_18001773B
0x180017726  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18001772d  jnz     loc_1800176AD
0x180017733  test    eax, eax
0x180017735  js      loc_1800175E5
0x18001773b  mov     edx, [rsp+4F0h+var_4C0]
0x18001773f  test    edx, edx
0x180017741  jz      short loc_18001778C
0x180017743  mov     rcx, [rsp+4F0h+pstm]
0x180017748  lea     r9, [rsp+4F0h+var_4A0]
0x18001774d  mov     [rsp+4F0h+var_4A0], r15d
0x180017752  mov     r8d, edx
0x180017755  lea     rdx, [rbp+3F0h+var_430]
0x180017759  mov     rax, [rcx]
0x18001775c  mov     rax, [rax+20h]
0x180017760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017765  mov     ebx, eax
0x180017767  test    eax, eax
0x180017769  jns     short loc_180017780
0x18001776b  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180017772  jnz     loc_1800176AD
0x180017778  test    eax, eax
0x18001777a  js      loc_1800175E5
0x180017780  mov     edx, [rsp+4F0h+var_4C0]
0x180017784  test    edx, edx
0x180017786  jnz     loc_1800176FD
0x18001778c  mov     rcx, [rsp+4F0h+pstm]; pstm
0x180017791  lea     rdx, [rsp+4F0h+phglobal]; phglobal
0x180017796  call    cs:__imp_GetHGlobalFromStream
0x18001779c  mov     ebx, eax
0x18001779e  test    eax, eax
0x1800177a0  js      loc_1800176A0
0x1800177a6  mov     rcx, [rsp+4F0h+phglobal]; hMem
0x1800177ab  call    cs:__imp_GlobalSize
0x1800177b1  test    rax, rax
0x1800177b4  jnz     short loc_1800177C7
0x1800177b6  cmp     [rsp+4F0h+var_4C0], r15d
0x1800177bb  jnz     short loc_1800177F1
0x1800177bd  mov     ebx, 88982F72h
0x1800177c2  jmp     loc_1800175D5
0x1800177c7  lea     rdx, [rsp+4F0h+pulResult]; pulResult
0x1800177cc  mov     rcx, rax; ullOperand
0x1800177cf  call    ULongLongToULong
0x1800177d4  mov     ebx, eax
0x1800177d6  test    eax, eax
0x1800177d8  js      loc_1800176A0
0x1800177de  mov     rcx, [rsp+4F0h+phglobal]; hMem
0x1800177e3  call    cs:__imp_GlobalLock
0x1800177e9  mov     rbx, rax
0x1800177ec  test    rax, rax
0x1800177ef  jnz     short loc_1800177FB
0x1800177f1  mov     ebx, 8007000Eh
0x1800177f6  jmp     loc_1800175D5
0x1800177fb  lea     rdx, [rdi+10h]
0x1800177ff  lea     rcx, [rsp+4F0h+var_498]
0x180017804  call    ??0?$CGuard@VIGuardableStream@@@@QEAA@AEAVIGuardableStream@@@Z; CGuard<IGuardableStream>::CGuard<IGuardableStream>(IGuardableStream &)
0x180017809  mov     rcx, rdi; this
0x18001780c  call    ?HrClose@CMemoryStream@@AEAAJXZ; CMemoryStream::HrClose(void)
0x180017811  mov     eax, [rsp+4F0h+pulResult]
0x180017815  mov     [rdi+78h], eax
0x180017818  mov     [rdi+70h], rbx
0x18001781c  lea     rcx, [rsp+4F0h+var_498]
0x180017821  call    ??1?$CGuard@VIGuardableStream@@@@QEAA@XZ; CGuard<IGuardableStream>::~CGuard<IGuardableStream>(void)
0x180017826  mov     rax, [rsp+4F0h+phglobal]
0x18001782b  mov     ebx, r15d
0x18001782e  mov     [rdi+80h], rax
0x180017835  jmp     loc_180017628
```
