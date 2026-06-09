# CEncoderOptionsPropertyBag::Initialize(tagPROPBAG2 *,ulong)

- ea: `0x1800da558`
- end: `0x1800da782`
- name: `?Initialize@CEncoderOptionsPropertyBag@@QEAAJPEAUtagPROPBAG2@@K@Z`
- size: `554`
- prototype: `__int64 __fastcall(CEncoderOptionsPropertyBag *__hidden this, struct tagPROPBAG2 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800da460`

## callees

- `0x1800319d0`
- `0x1800351e0`
- `0x18003c670`
- `0x180042ae8`
- `0x180064b00`
- `0x1800bd9d4`
- `0x1800da558`
- `0x18017e438`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da70d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da70d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800da64e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800da64e`

## pseudocode

```c
__int64 __fastcall CEncoderOptionsPropertyBag::Initialize(
        CEncoderOptionsPropertyBag *this,
        struct tagPROPBAG2 *a2,
        unsigned int a3)
{
  unsigned int v6; // ebx
  bool v7; // zf
  char *v8; // rcx
  int v9; // eax
  int v10; // ecx
  ULONGLONG v11; // rdi
  unsigned int i; // r15d
  unsigned int j; // ebp
  const unsigned __int16 *pstrName; // rcx
  ULONGLONG v15; // rcx
  int v16; // r9d
  void *v17; // rax
  ULONGLONG pullResult; // [rsp+50h] [rbp+8h] BYREF
  char *v20; // [rsp+68h] [rbp+20h] BYREF

  pullResult = 0;
  v20 = (char *)this + 16;
  CMTALock::Enter((CEncoderOptionsPropertyBag *)((char *)this + 16));
  if ( a3 && !a2 )
  {
    v6 = -2147024809;
LABEL_4:
    v7 = (_DWORD)g_doStackCaptures == 0;
LABEL_33:
    if ( !v7 )
    {
      v10 = v6;
LABEL_35:
      DoStackCapture(v10);
      goto LABEL_36;
    }
    goto LABEL_36;
  }
  v8 = (char *)this + 80;
  if ( *((_DWORD *)this + 26) )
  {
    v6 = -2003292412;
    goto LABEL_4;
  }
  v6 = 0;
  if ( a3 )
  {
    v9 = DynArrayImpl<1>::AddMultiple((__int64)v8, 72, a3, &pullResult);
    v6 = v9;
    if ( v9 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_36;
LABEL_10:
      v10 = v9;
      goto LABEL_35;
    }
    v11 = pullResult;
    for ( i = 0; i < a3; ++i )
    {
      *(_OWORD *)v11 = *(_OWORD *)&a2->dwType;
      *(_OWORD *)(v11 + 16) = *(_OWORD *)&a2->pstrName;
      *(_QWORD *)(v11 + 32) = *(_QWORD *)a2->clsid.Data4;
      *(_QWORD *)(v11 + 16) = 0;
      if ( a2->pstrName )
      {
        for ( j = 1; j < 0x11; ++j )
        {
          if ( !lstrcmpW(a2->pstrName, (LPCWSTR)qword_1801D2550[5 * j + 2]) )
          {
            *(_OWORD *)v11 = *(_OWORD *)&qword_1801D2550[5 * j];
            *(_OWORD *)(v11 + 16) = *(_OWORD *)&qword_1801D2550[5 * j + 2];
            *(_QWORD *)(v11 + 32) = qword_1801D2550[5 * j + 4];
            *(_DWORD *)(v11 + 64) = 1;
            break;
          }
        }
        if ( !*(_QWORD *)(v11 + 16) )
        {
          pstrName = a2->pstrName;
          pullResult = 0;
          v9 = StringCchLengthW(pstrName, 0x7FFFFFFFu, &pullResult);
          v6 = v9;
          if ( v9 < 0 )
          {
            if ( (_DWORD)g_doStackCaptures )
              goto LABEL_10;
            break;
          }
          v15 = pullResult + 1;
          if ( pullResult + 1 < pullResult )
          {
            v6 = -2147024362;
            v7 = (_DWORD)g_doStackCaptures == 0;
            goto LABEL_33;
          }
          ++pullResult;
          v9 = ULongLongMult(v15, 2u, &pullResult);
          v6 = v9;
          if ( v9 < 0 )
          {
            if ( v16 )
              goto LABEL_10;
            break;
          }
          v17 = CoTaskMemAlloc(pullResult);
          *(_QWORD *)(v11 + 16) = v17;
          if ( !v17 )
          {
            v6 = -2147024882;
            goto LABEL_4;
          }
          memcpy_0(v17, a2->pstrName, pullResult);
        }
      }
      ++a2;
      v11 += 72LL;
    }
  }
LABEL_36:
  CGuard<CMTALock>::~CGuard<CMTALock>(&v20);
  return v6;
}

```

## disassembly

```asm
0x1800da558  mov     rax, rsp
0x1800da55b  mov     [rax+10h], rbx
0x1800da55f  mov     [rax+18h], rbp
0x1800da563  push    rsi
0x1800da564  push    rdi
0x1800da565  push    r12
0x1800da567  push    r14
0x1800da569  push    r15
0x1800da56b  sub     rsp, 20h
0x1800da56f  mov     rbx, rcx
0x1800da572  mov     qword ptr [rax+8], 0
0x1800da57a  add     rcx, 10h; this
0x1800da57e  mov     r14d, r8d
0x1800da581  mov     [rax+20h], rcx
0x1800da585  mov     rsi, rdx
0x1800da588  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1800da58d  test    r14d, r14d
0x1800da590  jz      short loc_1800DA5A8
0x1800da592  test    rsi, rsi
0x1800da595  jnz     short loc_1800DA5A8
0x1800da597  mov     ebx, 80070057h
0x1800da59c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800da5a3  jmp     loc_1800DA755
0x1800da5a8  lea     rcx, [rbx+50h]
0x1800da5ac  cmp     dword ptr [rcx+18h], 0
0x1800da5b0  jbe     short loc_1800DA5B9
0x1800da5b2  mov     ebx, 88982F04h
0x1800da5b7  jmp     short loc_1800DA59C
0x1800da5b9  xor     ebx, ebx
0x1800da5bb  test    r14d, r14d
0x1800da5be  jz      loc_1800DA75E
0x1800da5c4  lea     r9, [rsp+48h+pullResult]
0x1800da5c9  mov     r8d, r14d
0x1800da5cc  lea     edx, [rbx+48h]
0x1800da5cf  call    ?AddMultiple@?$DynArrayImpl@$00@@IEAAJIIPEAPEAX@Z; DynArrayImpl<1>::AddMultiple(uint,uint,void * *)
0x1800da5d4  mov     ebx, eax
0x1800da5d6  test    eax, eax
0x1800da5d8  jns     short loc_1800DA5F2
0x1800da5da  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800da5e1  jz      short loc_1800DA5EA
0x1800da5e3  mov     ecx, eax
0x1800da5e5  jmp     loc_1800DA759
0x1800da5ea  test    eax, eax
0x1800da5ec  js      loc_1800DA75E
0x1800da5f2  mov     rdi, [rsp+48h+pullResult]
0x1800da5f7  xor     r15d, r15d
0x1800da5fa  lea     rcx, qword_1801D2550
0x1800da601  cmp     r15d, r14d
0x1800da604  jnb     loc_1800DA75E
0x1800da60a  movups  xmm0, xmmword ptr [rsi]
0x1800da60d  movups  xmmword ptr [rdi], xmm0
0x1800da610  movups  xmm1, xmmword ptr [rsi+10h]
0x1800da614  movups  xmmword ptr [rdi+10h], xmm1
0x1800da618  movsd   xmm0, qword ptr [rsi+20h]
0x1800da61d  movsd   qword ptr [rdi+20h], xmm0
0x1800da622  mov     qword ptr [rdi+10h], 0
0x1800da62a  cmp     qword ptr [rsi+10h], 0
0x1800da62f  jz      loc_1800DA733
0x1800da635  mov     ebp, 1
0x1800da63a  cmp     ebp, 11h
0x1800da63d  jnb     short loc_1800DA68E
0x1800da63f  mov     eax, ebp
0x1800da641  lea     r12, [rax+rax*4]
0x1800da645  mov     rdx, [rcx+r12*8+10h]; lpString2
0x1800da64a  mov     rcx, [rsi+10h]; lpString1
0x1800da64e  call    cs:__imp_lstrcmpW
0x1800da655  nop     dword ptr [rax+rax+00h]
0x1800da65a  lea     rcx, qword_1801D2550
0x1800da661  test    eax, eax
0x1800da663  jz      short loc_1800DA669
0x1800da665  inc     ebp
0x1800da667  jmp     short loc_1800DA63A
0x1800da669  movups  xmm0, xmmword ptr [rcx+r12*8]
0x1800da66e  movups  xmmword ptr [rdi], xmm0
0x1800da671  movups  xmm1, xmmword ptr [rcx+r12*8+10h]
0x1800da677  movups  xmmword ptr [rdi+10h], xmm1
0x1800da67b  movsd   xmm0, qword ptr [rcx+r12*8+20h]
0x1800da682  movsd   qword ptr [rdi+20h], xmm0
0x1800da687  mov     dword ptr [rdi+40h], 1
0x1800da68e  cmp     qword ptr [rdi+10h], 0
0x1800da693  jnz     loc_1800DA733
0x1800da699  mov     rcx, [rsi+10h]; unsigned __int16 *
0x1800da69d  lea     r8, [rsp+48h+pullResult]; unsigned __int64 *
0x1800da6a2  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800da6a7  mov     [rsp+48h+pullResult], 0
0x1800da6b0  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800da6b5  mov     r9d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800da6bc  mov     ebx, eax
0x1800da6be  test    eax, eax
0x1800da6c0  jns     short loc_1800DA6D3
0x1800da6c2  test    r9d, r9d
0x1800da6c5  jnz     loc_1800DA5E3
0x1800da6cb  test    eax, eax
0x1800da6cd  js      loc_1800DA75E
0x1800da6d3  mov     rax, [rsp+48h+pullResult]
0x1800da6d8  lea     rcx, [rax+1]; ullMultiplicand
0x1800da6dc  cmp     rcx, rax
0x1800da6df  jb      short loc_1800DA74D
0x1800da6e1  lea     r8, [rsp+48h+pullResult]; pullResult
0x1800da6e6  mov     [rsp+48h+pullResult], rcx
0x1800da6eb  mov     edx, 2; ullMultiplier
0x1800da6f0  call    ULongLongMult
0x1800da6f5  mov     ebx, eax
0x1800da6f7  test    eax, eax
0x1800da6f9  jns     short loc_1800DA708
0x1800da6fb  test    r9d, r9d
0x1800da6fe  jnz     loc_1800DA5E3
0x1800da704  test    eax, eax
0x1800da706  js      short loc_1800DA75E
0x1800da708  mov     rcx, [rsp+48h+pullResult]; cb
0x1800da70d  call    cs:__imp_CoTaskMemAlloc
0x1800da714  nop     dword ptr [rax+rax+00h]
0x1800da719  mov     [rdi+10h], rax
0x1800da71d  test    rax, rax
0x1800da720  jz      short loc_1800DA743
0x1800da722  mov     r8, [rsp+48h+pullResult]; Size
0x1800da727  mov     rcx, rax; void *
0x1800da72a  mov     rdx, [rsi+10h]; Src
0x1800da72e  call    memcpy_0
0x1800da733  inc     r15d
0x1800da736  add     rsi, 28h ; '('
0x1800da73a  add     rdi, 48h ; 'H'
0x1800da73e  jmp     loc_1800DA5FA
0x1800da743  mov     ebx, 8007000Eh
0x1800da748  jmp     loc_1800DA59C
0x1800da74d  mov     ebx, 80070216h
0x1800da752  test    r9d, r9d
0x1800da755  jz      short loc_1800DA75E
0x1800da757  mov     ecx, ebx; int
0x1800da759  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800da75e  lea     rcx, [rsp+48h+arg_18]
0x1800da763  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x1800da768  mov     rbp, [rsp+48h+arg_10]
0x1800da76d  mov     eax, ebx
0x1800da76f  mov     rbx, [rsp+48h+arg_8]
0x1800da774  add     rsp, 20h
0x1800da778  pop     r15
0x1800da77a  pop     r14
0x1800da77c  pop     r12
0x1800da77e  pop     rdi
0x1800da77f  pop     rsi
0x1800da780  retn
```
