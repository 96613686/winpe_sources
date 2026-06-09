# Dr::WetInkAnalyzer::UpdateStrokesDataInAnalyzer(void)

- ea: `0x1804820b8`
- end: `0x18048248f`
- name: `?UpdateStrokesDataInAnalyzer@WetInkAnalyzer@Dr@@AEAAJXZ`
- size: `983`
- prototype: `__int64 __fastcall(Dr::WetInkAnalyzer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1807ff190`

## callees

- `0x18002a690`
- `0x180276a40`
- `0x180279050`
- `0x1802ea394`
- `0x18048121c`
- `0x1804820b8`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180482388`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180482388`
- `OLEAUT32!__imp_VariantInit` at `0x1804821ce`
- `OLEAUT32!__imp_VariantInit` at `0x180482203`
- `OLEAUT32!__imp_VariantInit` at `0x1804821ce`
- `OLEAUT32!__imp_VariantInit` at `0x180482203`
- `OLEAUT32!__imp_VariantClear` at `0x180482394`
- `OLEAUT32!__imp_VariantClear` at `0x1804823ed`
- `OLEAUT32!__imp_VariantClear` at `0x180482394`
- `OLEAUT32!__imp_VariantClear` at `0x1804823ed`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18048224a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180482264`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18048224a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180482264`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180482367`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180482379`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180482367`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180482379`
- `ole32!CLSIDFromString` at `0x1804822ce`
- `ole32!CLSIDFromString` at `0x1804822ce`

## pseudocode

```c
unsigned int __fastcall Dr::WetInkAnalyzer::UpdateStrokesDataInAnalyzer(Dr **this, struct IInkDisp *a2)
{
  Dr **v2; // r13
  unsigned int result; // eax
  signed int v4; // edi
  HRESULT StrokeTimestamp; // esi
  signed int i; // r15d
  int v7; // edi
  Dr *v8; // r14
  Dr *v9; // r13
  unsigned __int64 *v10; // r8
  unsigned int v11; // r8d
  unsigned __int64 v12; // r12
  unsigned __int128 v13; // rax
  CLSID *v14; // rdi
  __int64 v15; // rsi
  HRESULT v16; // eax
  unsigned int v17; // edx
  int v18; // r8d
  __int64 v19; // [rsp+40h] [rbp-A8h] BYREF
  void *ppvData; // [rsp+48h] [rbp-A0h] BYREF
  Dr *v21; // [rsp+50h] [rbp-98h] BYREF
  unsigned int v22; // [rsp+58h] [rbp-90h]
  void *v23; // [rsp+60h] [rbp-88h] BYREF
  __int64 v24; // [rsp+68h] [rbp-80h]
  VARIANTARG v25; // [rsp+70h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-60h] BYREF
  CLSID *v27; // [rsp+A0h] [rbp-48h]
  unsigned int v29; // [rsp+F8h] [rbp+10h] BYREF
  unsigned int v30; // [rsp+100h] [rbp+18h] BYREF
  struct IInkStrokeDisp v31; // [rsp+108h] [rbp+20h] BYREF

  v2 = this;
  result = Dr::GetStrokeCount(this[12], a2);
  v4 = result;
  v22 = result;
  if ( result )
  {
    v24 = 0;
    v19 = 0;
    StrokeTimestamp = (*(__int64 (__fastcall **)(Dr *, __int64 *))(*(_QWORD *)v2[12] + 56LL))(v2[12], &v19);
    if ( StrokeTimestamp >= 0 )
    {
      for ( i = 0; i < v4; ++i )
      {
        v21 = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, Dr **))(*(_QWORD *)v19 + 96LL))(v19, (unsigned int)i, &v21);
        if ( v7 < 0 )
        {
          if ( v21 )
            (*(void (__fastcall **)(Dr *))(*(_QWORD *)v21 + 16LL))(v21);
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          return v7;
        }
        v8 = v21;
        v9 = v2[7];
        v30 = i;
        if ( v21 && v9 )
        {
          VariantInit(&pvarg);
          StrokeTimestamp = (*(__int64 (__fastcall **)(Dr *, _QWORD, __int64, VARIANTARG *))(*(_QWORD *)v8 + 240LL))(
                              v8,
                              0,
                              0xFFFFFFFFLL,
                              &pvarg);
          if ( StrokeTimestamp >= 0 )
          {
            VariantInit(&v25);
            StrokeTimestamp = (*(__int64 (__fastcall **)(Dr *, VARIANTARG *))(*(_QWORD *)v8 + 144LL))(v8, &v25);
            if ( StrokeTimestamp >= 0 )
            {
              ppvData = 0;
              v23 = 0;
              StrokeTimestamp = SafeArrayAccessData(pvarg.parray, &ppvData);
              if ( StrokeTimestamp >= 0 )
              {
                StrokeTimestamp = SafeArrayAccessData(v25.parray, &v23);
                if ( StrokeTimestamp >= 0 )
                {
                  v12 = *(unsigned int *)(v25.llVal + 24);
                  LODWORD(v31.lpVtbl) = *(_DWORD *)(pvarg.llVal + 24);
                  v13 = v12 * (unsigned __int128)0x10uLL;
                  if ( !is_mul_ok(v12, 0x10u) )
                    *(_QWORD *)&v13 = -1;
                  v14 = (CLSID *)Mso::Memory::Throw::AllocateEx(
                                   (Mso::Memory::Throw *)v13,
                                   *((unsigned __int64 *)&v13 + 1),
                                   v11);
                  v27 = v14;
                  v15 = 0;
                  do
                  {
                    if ( (unsigned int)v15 >= (unsigned int)v12 )
                      break;
                    v16 = CLSIDFromString(*((LPCOLESTR *)v23 + v15), &v14[(unsigned int)v15]);
                    v15 = (unsigned int)(v15 + 1);
                  }
                  while ( v16 >= 0 );
                  v29 = LODWORD(v31.lpVtbl) / (unsigned int)v12;
                  v17 = 0;
                  if ( LODWORD(v31.lpVtbl) / (unsigned int)v12 )
                  {
                    v18 = HIDWORD(v24);
                    do
                      *((_DWORD *)ppvData + (unsigned int)v12 * v17++ + 1) += v18;
                    while ( v17 < v29 );
                  }
                  StrokeTimestamp = (*(__int64 (__fastcall **)(Dr *, __int64, unsigned int *, _QWORD, CLSID *, unsigned int *, void *))(*(_QWORD *)v9 + 216LL))(
                                      v9,
                                      1,
                                      &v30,
                                      (unsigned int)v12,
                                      v14,
                                      &v29,
                                      ppvData);
                  operator delete(v14);
                }
              }
              if ( SafeArrayUnaccessData(v25.parray) < 0 || SafeArrayUnaccessData(pvarg.parray) < 0 )
                MsoShipAssertTagProc(963851372);
            }
            VariantClear(&v25);
          }
          v31.lpVtbl = 0;
          if ( StrokeTimestamp >= 0 )
          {
            StrokeTimestamp = Dr::GetStrokeTimestamp(v8, &v31, v10);
            if ( StrokeTimestamp >= 0 )
              StrokeTimestamp = (*(__int64 (__fastcall **)(Dr *, _QWORD, struct IInkStrokeDispVtbl *))(*(_QWORD *)v9 + 464LL))(
                                  v9,
                                  v30,
                                  v31.lpVtbl);
          }
          VariantClear(&pvarg);
          v8 = v21;
        }
        else
        {
          StrokeTimestamp = -2147024809;
        }
        if ( StrokeTimestamp < 0 )
        {
          if ( v8 )
            (*(void (__fastcall **)(Dr *))(*(_QWORD *)v8 + 16LL))(v8);
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          return StrokeTimestamp;
        }
        if ( v8 )
          (*(void (__fastcall **)(Dr *))(*(_QWORD *)v8 + 16LL))(v8);
        v2 = this;
        v4 = v22;
      }
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      return StrokeTimestamp;
    }
    else
    {
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      return StrokeTimestamp;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1804820b8  mov     [rsp+arg_0], rcx
0x1804820bd  push    rsi
0x1804820be  push    rdi
0x1804820bf  push    r12
0x1804820c1  push    r13
0x1804820c3  push    r14
0x1804820c5  push    r15
0x1804820c7  sub     rsp, 0B8h
0x1804820ce  mov     r13, rcx
0x1804820d1  mov     rcx, [rcx+60h]; this
0x1804820d5  call    ?GetStrokeCount@Dr@@YAKPEAUIInkDisp@@@Z; Dr::GetStrokeCount(IInkDisp *)
0x1804820da  mov     edi, eax
0x1804820dc  mov     [rsp+0E8h+var_90], eax
0x1804820e0  test    eax, eax
0x1804820e2  jz      loc_18048247D
0x1804820e8  mov     [rsp+0E8h+var_80], 0
0x1804820f1  mov     [rsp+0E8h+var_A8], 0
0x1804820fa  mov     rcx, [r13+60h]
0x1804820fe  mov     rax, [rcx]
0x180482101  lea     rdx, [rsp+0E8h+var_A8]
0x180482106  mov     rax, [rax+38h]
0x18048210a  call    cs:__guard_dispatch_icall_fptr
0x180482110  mov     esi, eax
0x180482112  test    eax, eax
0x180482114  jns     short loc_180482134
0x180482116  mov     rcx, [rsp+0E8h+var_A8]
0x18048211b  test    rcx, rcx
0x18048211e  jz      short loc_18048212D
0x180482120  mov     rdx, [rcx]
0x180482123  mov     rax, [rdx+10h]
0x180482127  call    cs:__guard_dispatch_icall_fptr
0x18048212d  mov     eax, esi
0x18048212f  jmp     loc_18048247D
0x180482134  xor     r15d, r15d
0x180482137  or      r12, 0FFFFFFFFFFFFFFFFh
0x18048213b  cmp     r15d, edi
0x18048213e  jge     loc_18048245D
0x180482144  mov     [rsp+0E8h+var_98], 0
0x18048214d  mov     rcx, [rsp+0E8h+var_A8]
0x180482152  mov     rax, [rcx]
0x180482155  lea     r8, [rsp+0E8h+var_98]
0x18048215a  mov     edx, r15d
0x18048215d  mov     rax, [rax+60h]
0x180482161  call    cs:__guard_dispatch_icall_fptr
0x180482167  mov     edi, eax
0x180482169  test    eax, eax
0x18048216b  jns     short loc_1804821A3
0x18048216d  mov     rcx, [rsp+0E8h+var_98]
0x180482172  test    rcx, rcx
0x180482175  jz      short loc_180482185
0x180482177  mov     rdx, [rcx]
0x18048217a  mov     rax, [rdx+10h]
0x18048217e  call    cs:__guard_dispatch_icall_fptr
0x180482184  nop
0x180482185  mov     rcx, [rsp+0E8h+var_A8]
0x18048218a  test    rcx, rcx
0x18048218d  jz      short loc_18048219C
0x18048218f  mov     rax, [rcx]
0x180482192  mov     rax, [rax+10h]
0x180482196  call    cs:__guard_dispatch_icall_fptr
0x18048219c  mov     eax, edi
0x18048219e  jmp     loc_18048247D
0x1804821a3  mov     r14, [rsp+0E8h+var_98]
0x1804821a8  mov     r13, [r13+38h]
0x1804821ac  mov     [rsp+0E8h+arg_10], r15d
0x1804821b4  test    r14, r14
0x1804821b7  jz      loc_1804823FA
0x1804821bd  test    r13, r13
0x1804821c0  jz      loc_1804823FA
0x1804821c6  lea     rcx, [rsp+0E8h+pvarg]; pvarg
0x1804821ce  call    cs:__imp_VariantInit
0x1804821d4  mov     rax, [r14]
0x1804821d7  lea     r9, [rsp+0E8h+pvarg]
0x1804821df  mov     r8d, r12d
0x1804821e2  xor     edx, edx
0x1804821e4  mov     rcx, r14
0x1804821e7  mov     rax, [rax+0F0h]
0x1804821ee  call    cs:__guard_dispatch_icall_fptr
0x1804821f4  mov     esi, eax
0x1804821f6  test    eax, eax
0x1804821f8  js      loc_18048239A
0x1804821fe  lea     rcx, [rsp+0E8h+var_78]; pvarg
0x180482203  call    cs:__imp_VariantInit
0x180482209  mov     rax, [r14]
0x18048220c  lea     rdx, [rsp+0E8h+var_78]
0x180482211  mov     rcx, r14
0x180482214  mov     rax, [rax+90h]
0x18048221b  call    cs:__guard_dispatch_icall_fptr
0x180482221  mov     esi, eax
0x180482223  test    eax, eax
0x180482225  js      loc_18048238F
0x18048222b  mov     [rsp+0E8h+ppvData], 0
0x180482234  mov     [rsp+0E8h+var_88], 0
0x18048223d  lea     rdx, [rsp+0E8h+ppvData]; ppvData
0x180482242  mov     rcx, qword ptr [rsp+0E8h+pvarg+8]; psa
0x18048224a  call    cs:__imp_SafeArrayAccessData
0x180482250  mov     esi, eax
0x180482252  test    eax, eax
0x180482254  js      loc_180482362
0x18048225a  lea     rdx, [rsp+0E8h+var_88]; ppvData
0x18048225f  mov     rcx, qword ptr [rsp+0E8h+var_78+8]; psa
0x180482264  call    cs:__imp_SafeArrayAccessData
0x18048226a  mov     esi, eax
0x18048226c  test    eax, eax
0x18048226e  js      loc_180482362
0x180482274  mov     rax, qword ptr [rsp+0E8h+var_78+8]
0x180482279  mov     r12d, [rax+18h]
0x18048227d  mov     rax, qword ptr [rsp+0E8h+pvarg+8]
0x180482285  mov     eax, [rax+18h]
0x180482288  mov     dword ptr [rsp+0E8h+arg_18.lpVtbl], eax
0x18048228f  mov     eax, 10h
0x180482294  mul     r12
0x180482297  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18048229e  cmovb   rax, rcx
0x1804822a2  mov     rcx, rax; this
0x1804822a5  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1804822aa  mov     rdi, rax
0x1804822ad  mov     [rsp+0E8h+var_48], rax
0x1804822b5  xor     esi, esi
0x1804822b7  cmp     esi, r12d
0x1804822ba  jnb     short loc_1804822DA
0x1804822bc  mov     edx, esi
0x1804822be  mov     rax, [rsp+0E8h+var_88]
0x1804822c3  mov     rcx, [rax+rsi*8]; lpsz
0x1804822c7  shl     rdx, 4
0x1804822cb  add     rdx, rdi; pclsid
0x1804822ce  call    cs:__imp_CLSIDFromString
0x1804822d4  inc     esi
0x1804822d6  test    eax, eax
0x1804822d8  jns     short loc_1804822B7
0x1804822da  xor     edx, edx
0x1804822dc  mov     eax, dword ptr [rsp+0E8h+arg_18.lpVtbl]
0x1804822e3  div     r12d
0x1804822e6  mov     [rsp+0E8h+arg_8], eax
0x1804822ed  xor     edx, edx
0x1804822ef  test    eax, eax
0x1804822f1  jz      short loc_180482314
0x1804822f3  mov     r8d, dword ptr [rsp+0E8h+var_80+4]
0x1804822f8  mov     ecx, edx
0x1804822fa  imul    ecx, r12d
0x1804822fe  inc     ecx
0x180482300  mov     rax, [rsp+0E8h+ppvData]
0x180482305  add     [rax+rcx*4], r8d
0x180482309  inc     edx
0x18048230b  cmp     edx, [rsp+0E8h+arg_8]
0x180482312  jb      short loc_1804822F8
0x180482314  mov     rax, [r13+0]
0x180482318  mov     rcx, [rsp+0E8h+ppvData]
0x18048231d  mov     [rsp+0E8h+var_B8], rcx
0x180482322  lea     rcx, [rsp+0E8h+arg_8]
0x18048232a  mov     [rsp+0E8h+var_C0], rcx
0x18048232f  mov     [rsp+0E8h+var_C8], rdi
0x180482334  mov     r9d, r12d
0x180482337  lea     r8, [rsp+0E8h+arg_10]
0x18048233f  mov     edx, 1
0x180482344  mov     rcx, r13
0x180482347  mov     rax, [rax+0D8h]
0x18048234e  call    cs:__guard_dispatch_icall_fptr
0x180482354  mov     esi, eax
0x180482356  mov     rcx, rdi; void *
0x180482359  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18048235e  or      r12, 0FFFFFFFFFFFFFFFFh
0x180482362  mov     rcx, qword ptr [rsp+0E8h+var_78+8]; psa
0x180482367  call    cs:__imp_SafeArrayUnaccessData
0x18048236d  test    eax, eax
0x18048236f  js      short loc_180482383
0x180482371  mov     rcx, qword ptr [rsp+0E8h+pvarg+8]; psa
0x180482379  call    cs:__imp_SafeArrayUnaccessData
0x18048237f  test    eax, eax
0x180482381  jns     short loc_18048238F
0x180482383  mov     ecx, 3973346Ch
0x180482388  call    cs:__imp_MsoShipAssertTagProc
0x18048238e  nop
0x18048238f  lea     rcx, [rsp+0E8h+var_78]; pvarg
0x180482394  call    cs:__imp_VariantClear
0x18048239a  mov     [rsp+0E8h+arg_18.lpVtbl], 0
0x1804823a6  test    esi, esi
0x1804823a8  js      short loc_1804823E5
0x1804823aa  lea     rdx, [rsp+0E8h+arg_18]; struct IInkStrokeDisp *
0x1804823b2  mov     rcx, r14; this
0x1804823b5  call    ?GetStrokeTimestamp@Dr@@YAJPEAUIInkStrokeDisp@@AEA_K@Z; Dr::GetStrokeTimestamp(IInkStrokeDisp *,unsigned __int64 &)
0x1804823ba  mov     esi, eax
0x1804823bc  test    eax, eax
0x1804823be  js      short loc_1804823E5
0x1804823c0  mov     rax, [r13+0]
0x1804823c4  mov     r8, [rsp+0E8h+arg_18.lpVtbl]
0x1804823cc  mov     edx, [rsp+0E8h+arg_10]
0x1804823d3  mov     rcx, r13
0x1804823d6  mov     rax, [rax+1D0h]
0x1804823dd  call    cs:__guard_dispatch_icall_fptr
0x1804823e3  mov     esi, eax
0x1804823e5  lea     rcx, [rsp+0E8h+pvarg]; pvarg
0x1804823ed  call    cs:__imp_VariantClear
0x1804823f3  mov     r14, [rsp+0E8h+var_98]
0x1804823f8  jmp     short loc_1804823FF
0x1804823fa  mov     esi, 80070057h
0x1804823ff  test    esi, esi
0x180482401  jns     short loc_180482434
0x180482403  test    r14, r14
0x180482406  jz      short loc_180482419
0x180482408  mov     rax, [r14]
0x18048240b  mov     rcx, r14
0x18048240e  mov     rax, [rax+10h]
0x180482412  call    cs:__guard_dispatch_icall_fptr
0x180482418  nop
0x180482419  mov     rcx, [rsp+0E8h+var_A8]
0x18048241e  test    rcx, rcx
0x180482421  jz      short loc_180482430
0x180482423  mov     rax, [rcx]
0x180482426  mov     rax, [rax+10h]
0x18048242a  call    cs:__guard_dispatch_icall_fptr
0x180482430  mov     eax, esi
0x180482432  jmp     short loc_18048247D
0x180482434  test    r14, r14
0x180482437  jz      short loc_180482449
0x180482439  mov     rax, [r14]
0x18048243c  mov     rcx, r14
0x18048243f  mov     rax, [rax+10h]
0x180482443  call    cs:__guard_dispatch_icall_fptr
0x180482449  inc     r15d
0x18048244c  mov     r13, [rsp+0E8h+arg_0]
0x180482454  mov     edi, [rsp+0E8h+var_90]
0x180482458  jmp     loc_18048213B
0x18048245d  mov     rcx, [rsp+0E8h+var_A8]
0x180482462  test    rcx, rcx
0x180482465  jz      short loc_180482474
0x180482467  mov     rax, [rcx]
0x18048246a  mov     rax, [rax+10h]
0x18048246e  call    cs:__guard_dispatch_icall_fptr
0x180482474  mov     eax, esi
0x180482476  jmp     short loc_18048247D
0x180482478  mov     eax, 80004005h
0x18048247d  add     rsp, 0B8h
0x180482484  pop     r15
0x180482486  pop     r14
0x180482488  pop     r13
0x18048248a  pop     r12
0x18048248c  pop     rdi
0x18048248d  pop     rsi
0x18048248e  retn
```
