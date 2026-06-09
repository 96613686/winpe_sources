# Dr::WetInkAnalyzer::UpdateStrokesDataInAnalyzer(void)

- ea: `0x18033f8a4`
- end: `0x18033fc7b`
- name: `?UpdateStrokesDataInAnalyzer@WetInkAnalyzer@Dr@@AEAAJXZ`
- size: `983`
- prototype: `__int64 __fastcall(Dr::WetInkAnalyzer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1807f2168`

## callees

- `0x180065990`
- `0x1800659a0`
- `0x180071720`
- `0x18033e9c8`
- `0x18033f8a4`
- `0x180353a48`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18033fb74`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18033fb74`
- `OLEAUT32!__imp_VariantInit` at `0x18033f9ba`
- `OLEAUT32!__imp_VariantInit` at `0x18033f9ef`
- `OLEAUT32!__imp_VariantInit` at `0x18033f9ba`
- `OLEAUT32!__imp_VariantInit` at `0x18033f9ef`
- `OLEAUT32!__imp_VariantClear` at `0x18033fb80`
- `OLEAUT32!__imp_VariantClear` at `0x18033fbd9`
- `OLEAUT32!__imp_VariantClear` at `0x18033fb80`
- `OLEAUT32!__imp_VariantClear` at `0x18033fbd9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18033fa36`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18033fa50`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18033fa36`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18033fa50`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18033fb53`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18033fb65`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18033fb53`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18033fb65`
- `ole32!CLSIDFromString` at `0x18033faba`
- `ole32!CLSIDFromString` at `0x18033faba`

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
0x18033f8a4  mov     [rsp+arg_0], rcx
0x18033f8a9  push    rsi
0x18033f8aa  push    rdi
0x18033f8ab  push    r12
0x18033f8ad  push    r13
0x18033f8af  push    r14
0x18033f8b1  push    r15
0x18033f8b3  sub     rsp, 0B8h
0x18033f8ba  mov     r13, rcx
0x18033f8bd  mov     rcx, [rcx+60h]; this
0x18033f8c1  call    ?GetStrokeCount@Dr@@YAKPEAUIInkDisp@@@Z; Dr::GetStrokeCount(IInkDisp *)
0x18033f8c6  mov     edi, eax
0x18033f8c8  mov     [rsp+0E8h+var_90], eax
0x18033f8cc  test    eax, eax
0x18033f8ce  jz      loc_18033FC69
0x18033f8d4  mov     [rsp+0E8h+var_80], 0
0x18033f8dd  mov     [rsp+0E8h+var_A8], 0
0x18033f8e6  mov     rcx, [r13+60h]
0x18033f8ea  mov     rax, [rcx]
0x18033f8ed  lea     rdx, [rsp+0E8h+var_A8]
0x18033f8f2  mov     rax, [rax+38h]
0x18033f8f6  call    cs:__guard_dispatch_icall_fptr
0x18033f8fc  mov     esi, eax
0x18033f8fe  test    eax, eax
0x18033f900  jns     short loc_18033F920
0x18033f902  mov     rcx, [rsp+0E8h+var_A8]
0x18033f907  test    rcx, rcx
0x18033f90a  jz      short loc_18033F919
0x18033f90c  mov     rdx, [rcx]
0x18033f90f  mov     rax, [rdx+10h]
0x18033f913  call    cs:__guard_dispatch_icall_fptr
0x18033f919  mov     eax, esi
0x18033f91b  jmp     loc_18033FC69
0x18033f920  xor     r15d, r15d
0x18033f923  or      r12, 0FFFFFFFFFFFFFFFFh
0x18033f927  cmp     r15d, edi
0x18033f92a  jge     loc_18033FC49
0x18033f930  mov     [rsp+0E8h+var_98], 0
0x18033f939  mov     rcx, [rsp+0E8h+var_A8]
0x18033f93e  mov     rax, [rcx]
0x18033f941  lea     r8, [rsp+0E8h+var_98]
0x18033f946  mov     edx, r15d
0x18033f949  mov     rax, [rax+60h]
0x18033f94d  call    cs:__guard_dispatch_icall_fptr
0x18033f953  mov     edi, eax
0x18033f955  test    eax, eax
0x18033f957  jns     short loc_18033F98F
0x18033f959  mov     rcx, [rsp+0E8h+var_98]
0x18033f95e  test    rcx, rcx
0x18033f961  jz      short loc_18033F971
0x18033f963  mov     rdx, [rcx]
0x18033f966  mov     rax, [rdx+10h]
0x18033f96a  call    cs:__guard_dispatch_icall_fptr
0x18033f970  nop
0x18033f971  mov     rcx, [rsp+0E8h+var_A8]
0x18033f976  test    rcx, rcx
0x18033f979  jz      short loc_18033F988
0x18033f97b  mov     rax, [rcx]
0x18033f97e  mov     rax, [rax+10h]
0x18033f982  call    cs:__guard_dispatch_icall_fptr
0x18033f988  mov     eax, edi
0x18033f98a  jmp     loc_18033FC69
0x18033f98f  mov     r14, [rsp+0E8h+var_98]
0x18033f994  mov     r13, [r13+38h]
0x18033f998  mov     [rsp+0E8h+arg_10], r15d
0x18033f9a0  test    r14, r14
0x18033f9a3  jz      loc_18033FBE6
0x18033f9a9  test    r13, r13
0x18033f9ac  jz      loc_18033FBE6
0x18033f9b2  lea     rcx, [rsp+0E8h+pvarg]; pvarg
0x18033f9ba  call    cs:__imp_VariantInit
0x18033f9c0  mov     rax, [r14]
0x18033f9c3  lea     r9, [rsp+0E8h+pvarg]
0x18033f9cb  mov     r8d, r12d
0x18033f9ce  xor     edx, edx
0x18033f9d0  mov     rcx, r14
0x18033f9d3  mov     rax, [rax+0F0h]
0x18033f9da  call    cs:__guard_dispatch_icall_fptr
0x18033f9e0  mov     esi, eax
0x18033f9e2  test    eax, eax
0x18033f9e4  js      loc_18033FB86
0x18033f9ea  lea     rcx, [rsp+0E8h+var_78]; pvarg
0x18033f9ef  call    cs:__imp_VariantInit
0x18033f9f5  mov     rax, [r14]
0x18033f9f8  lea     rdx, [rsp+0E8h+var_78]
0x18033f9fd  mov     rcx, r14
0x18033fa00  mov     rax, [rax+90h]
0x18033fa07  call    cs:__guard_dispatch_icall_fptr
0x18033fa0d  mov     esi, eax
0x18033fa0f  test    eax, eax
0x18033fa11  js      loc_18033FB7B
0x18033fa17  mov     [rsp+0E8h+ppvData], 0
0x18033fa20  mov     [rsp+0E8h+var_88], 0
0x18033fa29  lea     rdx, [rsp+0E8h+ppvData]; ppvData
0x18033fa2e  mov     rcx, qword ptr [rsp+0E8h+pvarg+8]; psa
0x18033fa36  call    cs:__imp_SafeArrayAccessData
0x18033fa3c  mov     esi, eax
0x18033fa3e  test    eax, eax
0x18033fa40  js      loc_18033FB4E
0x18033fa46  lea     rdx, [rsp+0E8h+var_88]; ppvData
0x18033fa4b  mov     rcx, qword ptr [rsp+0E8h+var_78+8]; psa
0x18033fa50  call    cs:__imp_SafeArrayAccessData
0x18033fa56  mov     esi, eax
0x18033fa58  test    eax, eax
0x18033fa5a  js      loc_18033FB4E
0x18033fa60  mov     rax, qword ptr [rsp+0E8h+var_78+8]
0x18033fa65  mov     r12d, [rax+18h]
0x18033fa69  mov     rax, qword ptr [rsp+0E8h+pvarg+8]
0x18033fa71  mov     eax, [rax+18h]
0x18033fa74  mov     dword ptr [rsp+0E8h+arg_18.lpVtbl], eax
0x18033fa7b  mov     eax, 10h
0x18033fa80  mul     r12
0x18033fa83  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18033fa8a  cmovb   rax, rcx
0x18033fa8e  mov     rcx, rax; this
0x18033fa91  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18033fa96  mov     rdi, rax
0x18033fa99  mov     [rsp+0E8h+var_48], rax
0x18033faa1  xor     esi, esi
0x18033faa3  cmp     esi, r12d
0x18033faa6  jnb     short loc_18033FAC6
0x18033faa8  mov     edx, esi
0x18033faaa  mov     rax, [rsp+0E8h+var_88]
0x18033faaf  mov     rcx, [rax+rsi*8]; lpsz
0x18033fab3  shl     rdx, 4
0x18033fab7  add     rdx, rdi; pclsid
0x18033faba  call    cs:__imp_CLSIDFromString
0x18033fac0  inc     esi
0x18033fac2  test    eax, eax
0x18033fac4  jns     short loc_18033FAA3
0x18033fac6  xor     edx, edx
0x18033fac8  mov     eax, dword ptr [rsp+0E8h+arg_18.lpVtbl]
0x18033facf  div     r12d
0x18033fad2  mov     [rsp+0E8h+arg_8], eax
0x18033fad9  xor     edx, edx
0x18033fadb  test    eax, eax
0x18033fadd  jz      short loc_18033FB00
0x18033fadf  mov     r8d, dword ptr [rsp+0E8h+var_80+4]
0x18033fae4  mov     ecx, edx
0x18033fae6  imul    ecx, r12d
0x18033faea  inc     ecx
0x18033faec  mov     rax, [rsp+0E8h+ppvData]
0x18033faf1  add     [rax+rcx*4], r8d
0x18033faf5  inc     edx
0x18033faf7  cmp     edx, [rsp+0E8h+arg_8]
0x18033fafe  jb      short loc_18033FAE4
0x18033fb00  mov     rax, [r13+0]
0x18033fb04  mov     rcx, [rsp+0E8h+ppvData]
0x18033fb09  mov     [rsp+0E8h+var_B8], rcx
0x18033fb0e  lea     rcx, [rsp+0E8h+arg_8]
0x18033fb16  mov     [rsp+0E8h+var_C0], rcx
0x18033fb1b  mov     [rsp+0E8h+var_C8], rdi
0x18033fb20  mov     r9d, r12d
0x18033fb23  lea     r8, [rsp+0E8h+arg_10]
0x18033fb2b  mov     edx, 1
0x18033fb30  mov     rcx, r13
0x18033fb33  mov     rax, [rax+0D8h]
0x18033fb3a  call    cs:__guard_dispatch_icall_fptr
0x18033fb40  mov     esi, eax
0x18033fb42  mov     rcx, rdi; void *
0x18033fb45  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18033fb4a  or      r12, 0FFFFFFFFFFFFFFFFh
0x18033fb4e  mov     rcx, qword ptr [rsp+0E8h+var_78+8]; psa
0x18033fb53  call    cs:__imp_SafeArrayUnaccessData
0x18033fb59  test    eax, eax
0x18033fb5b  js      short loc_18033FB6F
0x18033fb5d  mov     rcx, qword ptr [rsp+0E8h+pvarg+8]; psa
0x18033fb65  call    cs:__imp_SafeArrayUnaccessData
0x18033fb6b  test    eax, eax
0x18033fb6d  jns     short loc_18033FB7B
0x18033fb6f  mov     ecx, 3973346Ch
0x18033fb74  call    cs:__imp_MsoShipAssertTagProc
0x18033fb7a  nop
0x18033fb7b  lea     rcx, [rsp+0E8h+var_78]; pvarg
0x18033fb80  call    cs:__imp_VariantClear
0x18033fb86  mov     [rsp+0E8h+arg_18.lpVtbl], 0
0x18033fb92  test    esi, esi
0x18033fb94  js      short loc_18033FBD1
0x18033fb96  lea     rdx, [rsp+0E8h+arg_18]; struct IInkStrokeDisp *
0x18033fb9e  mov     rcx, r14; this
0x18033fba1  call    ?GetStrokeTimestamp@Dr@@YAJPEAUIInkStrokeDisp@@AEA_K@Z; Dr::GetStrokeTimestamp(IInkStrokeDisp *,unsigned __int64 &)
0x18033fba6  mov     esi, eax
0x18033fba8  test    eax, eax
0x18033fbaa  js      short loc_18033FBD1
0x18033fbac  mov     rax, [r13+0]
0x18033fbb0  mov     r8, [rsp+0E8h+arg_18.lpVtbl]
0x18033fbb8  mov     edx, [rsp+0E8h+arg_10]
0x18033fbbf  mov     rcx, r13
0x18033fbc2  mov     rax, [rax+1D0h]
0x18033fbc9  call    cs:__guard_dispatch_icall_fptr
0x18033fbcf  mov     esi, eax
0x18033fbd1  lea     rcx, [rsp+0E8h+pvarg]; pvarg
0x18033fbd9  call    cs:__imp_VariantClear
0x18033fbdf  mov     r14, [rsp+0E8h+var_98]
0x18033fbe4  jmp     short loc_18033FBEB
0x18033fbe6  mov     esi, 80070057h
0x18033fbeb  test    esi, esi
0x18033fbed  jns     short loc_18033FC20
0x18033fbef  test    r14, r14
0x18033fbf2  jz      short loc_18033FC05
0x18033fbf4  mov     rax, [r14]
0x18033fbf7  mov     rcx, r14
0x18033fbfa  mov     rax, [rax+10h]
0x18033fbfe  call    cs:__guard_dispatch_icall_fptr
0x18033fc04  nop
0x18033fc05  mov     rcx, [rsp+0E8h+var_A8]
0x18033fc0a  test    rcx, rcx
0x18033fc0d  jz      short loc_18033FC1C
0x18033fc0f  mov     rax, [rcx]
0x18033fc12  mov     rax, [rax+10h]
0x18033fc16  call    cs:__guard_dispatch_icall_fptr
0x18033fc1c  mov     eax, esi
0x18033fc1e  jmp     short loc_18033FC69
0x18033fc20  test    r14, r14
0x18033fc23  jz      short loc_18033FC35
0x18033fc25  mov     rax, [r14]
0x18033fc28  mov     rcx, r14
0x18033fc2b  mov     rax, [rax+10h]
0x18033fc2f  call    cs:__guard_dispatch_icall_fptr
0x18033fc35  inc     r15d
0x18033fc38  mov     r13, [rsp+0E8h+arg_0]
0x18033fc40  mov     edi, [rsp+0E8h+var_90]
0x18033fc44  jmp     loc_18033F927
0x18033fc49  mov     rcx, [rsp+0E8h+var_A8]
0x18033fc4e  test    rcx, rcx
0x18033fc51  jz      short loc_18033FC60
0x18033fc53  mov     rax, [rcx]
0x18033fc56  mov     rax, [rax+10h]
0x18033fc5a  call    cs:__guard_dispatch_icall_fptr
0x18033fc60  mov     eax, esi
0x18033fc62  jmp     short loc_18033FC69
0x18033fc64  mov     eax, 80004005h
0x18033fc69  add     rsp, 0B8h
0x18033fc70  pop     r15
0x18033fc72  pop     r14
0x18033fc74  pop     r13
0x18033fc76  pop     r12
0x18033fc78  pop     rdi
0x18033fc79  pop     rsi
0x18033fc7a  retn
```
