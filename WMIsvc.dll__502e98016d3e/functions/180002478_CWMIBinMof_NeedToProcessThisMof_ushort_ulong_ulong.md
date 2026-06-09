# CWMIBinMof::NeedToProcessThisMof(ushort *,ulong &,ulong &)

- ea: `0x180002478`
- end: `0x180002a55`
- name: `?NeedToProcessThisMof@CWMIBinMof@@QEAAHPEAGAEAK1@Z`
- size: `1501`
- prototype: `int(CWMIBinMof *__hidden this, unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000226c`
- `0x180002a5c`

## callees

- `0x1800021f0`
- `0x180002478`
- `0x180002ea4`
- `0x1800031e0`
- `0x180003494`
- `0x1800039f4`
- `0x180003b08`
- `0x180003e10`
- `0x1800079f0`
- `0x18000d904`
- `0x18000dc88`
- `0x18000e230`
- `0x1800172fc`
- `0x180017350`
- `0x180017460`
- `0x1800174ec`
- `0x180017dc8`
- `0x18001d377`
- `0x180020010`

## import_xrefs

- `wbemcomn!DebugTrace` at `0x18000296d`
- `wbemcomn!DebugTrace` at `0x18000296d`
- `wbemcomn!ErrorTrace` at `0x180002938`
- `wbemcomn!ErrorTrace` at `0x180002962`
- `wbemcomn!ErrorTrace` at `0x180002938`
- `wbemcomn!ErrorTrace` at `0x180002962`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002569`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000257f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002569`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000257f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800024d0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000251f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800024d0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000251f`
- `OLEAUT32!__imp_VariantInit` at `0x180002799`
- `OLEAUT32!__imp_VariantInit` at `0x1800027a4`
- `OLEAUT32!__imp_VariantInit` at `0x180002842`
- `OLEAUT32!__imp_VariantInit` at `0x180002799`
- `OLEAUT32!__imp_VariantInit` at `0x1800027a4`
- `OLEAUT32!__imp_VariantInit` at `0x180002842`
- `OLEAUT32!__imp_VariantClear` at `0x18000261c`
- `OLEAUT32!__imp_VariantClear` at `0x180002628`
- `OLEAUT32!__imp_VariantClear` at `0x1800028b8`
- `OLEAUT32!__imp_VariantClear` at `0x180002a34`
- `OLEAUT32!__imp_VariantClear` at `0x180002a3f`
- `OLEAUT32!__imp_VariantClear` at `0x18000261c`
- `OLEAUT32!__imp_VariantClear` at `0x180002628`
- `OLEAUT32!__imp_VariantClear` at `0x1800028b8`
- `OLEAUT32!__imp_VariantClear` at `0x180002a34`
- `OLEAUT32!__imp_VariantClear` at `0x180002a3f`

## string_xrefs

- `0x1800027cd`: `__RELPATH`
- `0x180002928`: `We have been requested to delete this mof:\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CWMIBinMof::NeedToProcessThisMof(
        CWMIBinMof *this,
        unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  unsigned int v7; // edi
  OLECHAR *v8; // rax
  OLECHAR *v9; // rsi
  unsigned int v10; // r14d
  unsigned int v11; // r15d
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rdi
  CWMIBinMof *v15; // rcx
  OLECHAR *v16; // rbx
  int v17; // ebx
  unsigned __int16 *v18; // rdx
  LONGLONG llVal; // r10
  const WCHAR *v20; // rcx
  const WCHAR *bstrVal; // rcx
  CWMIBinMof *v22; // rcx
  const unsigned __int16 *v23; // rdx
  unsigned __int16 *v24; // rdx
  size_t Size; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG v28; // [rsp+58h] [rbp-A8h] BYREF
  int v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  __int64 v31; // [rsp+80h] [rbp-80h] BYREF
  __int64 v32; // [rsp+88h] [rbp-78h] BYREF
  OLECHAR *psz; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v35; // [rsp+B0h] [rbp-50h]
  OLECHAR *v36; // [rsp+B8h] [rbp-48h]
  VARIANTARG v37; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v38; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v39[160]; // [rsp+F0h] [rbp-10h] BYREF

  v26 = 0;
  SafeInt<unsigned int>::MixedSizeAddition<int>(&Size, 1040);
  v7 = Size;
  v8 = (OLECHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)Size, 2u));
  v9 = v8;
  v36 = v8;
  if ( v8 )
    memset_0(v8, 0, v7);
  v10 = 1;
  SafeInt<unsigned int>::MixedSizeAddition<int>(&Size, 1040);
  v11 = Size;
  v12 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)Size, 2u));
  v13 = v12;
  v35 = v12;
  if ( v12 )
    memset_0(v12, 0, v11);
  if ( v13
    && v9
    && (int)ConvertStringToCTypeString(v13, 1040, a2) >= 0
    && (int)StringCchPrintfW(
              v9,
              0x410u,
              L"WmiBinaryMofResource.HighDateTime=%lu,LowDateTime=%lu,Name=\"%s\"",
              *a4,
              *a3,
              v13) >= 0 )
  {
    if ( *(_DWORD *)this )
    {
      v32 = 0;
      CBSTR::SetStr((CBSTR *)&v32, v9);
      if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, __int64 *, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 16LL)
                                                                                               + 48LL))(
              *(_QWORD *)(*((_QWORD *)this + 3) + 16LL),
              v32,
              0,
              *(_QWORD *)(*((_QWORD *)this + 3) + 24LL),
              &v26,
              0) )
      {
        v10 = 0;
        VariantInit(&pvarg);
        if ( !(*(unsigned int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v26 + 32LL))(
                v26,
                L"MofProcessed",
                0,
                &pvarg,
                0,
                0) )
          CWMIBinMof::AddThisMofToRegistryIfNeeded(
            (CWMIBinMof *)0xFFFFFFFFFFFFFFFFLL,
            v18,
            a2,
            a3,
            a4,
            pvarg.iVal == 0xFFFF);
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        v26 = 0;
        VariantClear(&pvarg);
      }
      v27 = 0;
      CAutoWChar::CAutoWChar((CAutoWChar *)&psz, 512);
      v16 = psz;
      if ( psz )
      {
        v29 = 0;
        if ( (int)StringCchPrintfW(psz, 0x200u, L"select * from WMIBinaryMofResource where Name = \"%s\"", v13) >= 0 )
        {
          v31 = 0;
          CBSTR::SetStr((CBSTR *)&v31, v16);
          v30 = 0;
          CBSTR::SetStr((CBSTR *)&v30, (OLECHAR *)L"WQL");
          if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64, __int64, __int64, _QWORD, __int64 *))(**(_QWORD **)(*((_QWORD *)this + 3) + 16LL) + 160LL))(
                  *(_QWORD *)(*((_QWORD *)this + 3) + 16LL),
                  v30,
                  v31,
                  48,
                  *(_QWORD *)(*((_QWORD *)this + 3) + 24LL),
                  &v27) )
          {
            Size = 0;
            do
            {
              v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, size_t *, int *))(*(_QWORD *)v27 + 32LL))(
                      v27,
                      2000,
                      1,
                      &Size,
                      &v29);
              if ( !v17 )
              {
                VariantInit(&v28);
                VariantInit(&pvarg);
                v17 = (*(__int64 (__fastcall **)(size_t, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)Size + 32LL))(
                        Size,
                        L"__RELPATH",
                        0,
                        &v28,
                        0,
                        0);
                if ( !v17 && v28.vt == 8 && v28.llVal && (unsigned int)wbem_wcsicmp(v28.bstrVal, v9) )
                {
                  llVal = 0;
                  if ( v28.vt == 8 )
                    llVal = v28.llVal;
                  v17 = (*(__int64 (__fastcall **)(_QWORD, LONGLONG, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 16LL)
                                                                                            + 128LL))(
                          *(_QWORD *)(*((_QWORD *)this + 3) + 16LL),
                          llVal,
                          0,
                          *(_QWORD *)(*((_QWORD *)this + 3) + 24LL),
                          0);
                  if ( v17 >= 0 )
                  {
                    DebugTrace(10, "We have been requested to delete this mof:\n");
                    bstrVal = 0;
                    if ( v28.vt == 8 )
                      bstrVal = v28.bstrVal;
                    TranslateAndLog(bstrVal, 1);
                    if ( !v17 )
                    {
                      v23 = 0;
                      if ( v28.vt == 8 )
                        v23 = v28.bstrVal;
                      CWMIBinMof::DeleteMofFromRegistry(v22, v23);
                      v17 = (*(__int64 (__fastcall **)(size_t, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)Size + 32LL))(
                              Size,
                              L"Driver",
                              0,
                              &pvarg,
                              0,
                              0);
                      if ( !v17 )
                      {
                        CNamespaceManagement::CNamespaceManagement((CNamespaceManagement *)v39, this);
                        CVARIANT::CVARIANT(&v38, *a3);
                        CVARIANT::CVARIANT(&v37, *a4);
                        v24 = 0;
                        if ( pvarg.vt == 8 )
                          v24 = pvarg.bstrVal;
                        CNamespaceManagement::DeleteOldClasses(
                          (CNamespaceManagement *)v39,
                          v24,
                          (struct CVARIANT *)&v38,
                          (struct CVARIANT *)&v37,
                          1);
                        VariantClear(&v37);
                        VariantClear(&v38);
                        CNamespaceManagement::~CNamespaceManagement((CNamespaceManagement *)v39);
                      }
                    }
                  }
                  else
                  {
                    ErrorTrace(10, "We have been requested to delete this mof:\n");
                    v20 = 0;
                    if ( v28.vt == 8 )
                      v20 = v28.bstrVal;
                    TranslateAndLog(v20, 0);
                    ErrorTrace(10, "It failed with 0x%08lx\n", v17);
                  }
                }
                VariantClear(&pvarg);
                VariantClear(&v28);
              }
              if ( Size )
                (*(void (__fastcall **)(size_t))(*(_QWORD *)Size + 16LL))(Size);
              Size = 0;
            }
            while ( !v17 );
            if ( v27 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
            v27 = 0;
          }
          CBSTR::Clear((CBSTR *)&v30);
          CBSTR::Clear((CBSTR *)&v31);
        }
      }
      CAutoWChar::~CAutoWChar((CAutoWChar *)&psz);
      CBSTR::Clear((CBSTR *)&v32);
    }
    else if ( (unsigned int)CWMIBinMof::ThisMofExistsInRegistry(
                              v15,
                              L"Software\\Microsoft\\WBEM\\WDM\\DREDGE",
                              a2,
                              *a3,
                              *a4,
                              1) )
    {
      v10 = 0;
    }
  }
  if ( v13 )
    CWin32DefaultArena::WbemMemFree(v13);
  v35 = 0;
  if ( v9 )
    CWin32DefaultArena::WbemMemFree(v9);
  v36 = 0;
  return v10;
}

```

## disassembly

```asm
0x180002478  mov     [rsp-8+arg_0], rcx
0x18000247d  push    rbp
0x18000247e  push    rbx
0x18000247f  push    rsi
0x180002480  push    rdi
0x180002481  push    r12
0x180002483  push    r13
0x180002485  push    r14
0x180002487  push    r15
0x180002489  lea     rbp, [rsp-58h]
0x18000248e  sub     rsp, 158h
0x180002495  mov     r12, r9
0x180002498  mov     r13, r8
0x18000249b  mov     rbx, rdx
0x18000249e  mov     [rsp+190h+var_148], 0
0x1800024a7  mov     edx, 410h
0x1800024ac  lea     rcx, [rsp+190h+Size]
0x1800024b1  call    ??$MixedSizeAddition@H@?$SafeInt@I@@CA?AV0@V0@H@Z; SafeInt<uint>::MixedSizeAddition<int>(SafeInt<uint>,int)
0x1800024b6  mov     edi, dword ptr [rsp+190h+Size]
0x1800024ba  mov     eax, 2
0x1800024bf  mul     rdi
0x1800024c2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800024c9  cmovb   rax, rcx
0x1800024cd  mov     rcx, rax
0x1800024d0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800024d6  mov     rsi, rax
0x1800024d9  mov     [rbp+90h+var_D8], rax
0x1800024dd  test    rax, rax
0x1800024e0  jz      short loc_1800024F0
0x1800024e2  mov     r8d, edi; Size
0x1800024e5  xor     edx, edx; Val
0x1800024e7  mov     rcx, rax; void *
0x1800024ea  call    memset_0
0x1800024ef  nop
0x1800024f0  mov     edx, 410h
0x1800024f5  mov     r14d, 1
0x1800024fb  lea     rcx, [rsp+190h+Size]
0x180002500  call    ??$MixedSizeAddition@H@?$SafeInt@I@@CA?AV0@V0@H@Z; SafeInt<uint>::MixedSizeAddition<int>(SafeInt<uint>,int)
0x180002505  mov     r15d, dword ptr [rsp+190h+Size]
0x18000250a  lea     eax, [r14+1]
0x18000250e  mul     r15
0x180002511  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002518  cmovb   rax, rcx
0x18000251c  mov     rcx, rax
0x18000251f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180002525  mov     rdi, rax
0x180002528  mov     [rbp+90h+var_E0], rax
0x18000252c  test    rax, rax
0x18000252f  jz      short loc_18000253F
0x180002531  mov     r8d, r15d; Size
0x180002534  xor     edx, edx; Val
0x180002536  mov     rcx, rax; void *
0x180002539  call    memset_0
0x18000253e  nop
0x18000253f  test    rdi, rdi
0x180002542  jz      short loc_180002561
0x180002544  test    rsi, rsi
0x180002547  jz      short loc_180002561
0x180002549  mov     r8, rbx; unsigned __int16 *
0x18000254c  mov     r15d, 410h
0x180002552  mov     edx, r15d; int
0x180002555  mov     rcx, rdi; unsigned __int16 *
0x180002558  call    ?ConvertStringToCTypeString@@YAJPEAGHPEBG@Z; ConvertStringToCTypeString(ushort *,int,ushort const *)
0x18000255d  test    eax, eax
0x18000255f  jns     short loc_1800025A4
0x180002561  test    rdi, rdi
0x180002564  jz      short loc_18000256F
0x180002566  mov     rcx, rdi
0x180002569  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000256f  mov     [rbp+90h+var_E0], 0
0x180002577  test    rsi, rsi
0x18000257a  jz      short loc_180002585
0x18000257c  mov     rcx, rsi
0x18000257f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180002585  mov     [rbp+90h+var_D8], 0
0x18000258d  mov     eax, r14d
0x180002590  add     rsp, 158h
0x180002597  pop     r15
0x180002599  pop     r14
0x18000259b  pop     r13
0x18000259d  pop     r12
0x18000259f  pop     rdi
0x1800025a0  pop     rsi
0x1800025a1  pop     rbx
0x1800025a2  pop     rbp
0x1800025a3  retn
0x1800025a4  mov     qword ptr [rsp+190h+var_168], rdi
0x1800025a9  mov     eax, [r13+0]
0x1800025ad  mov     dword ptr [rsp+190h+var_170], eax
0x1800025b1  mov     r9d, [r12]
0x1800025b5  lea     r8, aWmibinarymofre; "WmiBinaryMofResource.HighDateTime=%lu,L"...
0x1800025bc  mov     rdx, r15; unsigned __int64
0x1800025bf  mov     rcx, rsi; unsigned __int16 *
0x1800025c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800025c7  test    eax, eax
0x1800025c9  js      short loc_180002561
0x1800025cb  mov     r15, [rbp+90h+arg_0]
0x1800025d2  cmp     dword ptr [r15], 0
0x1800025d6  jnz     loc_1800027EC
0x1800025dc  mov     [rsp+190h+var_168], 1; int
0x1800025e4  mov     eax, [r12]
0x1800025e8  mov     dword ptr [rsp+190h+var_170], eax; unsigned int
0x1800025ec  mov     r9d, [r13+0]; unsigned int
0x1800025f0  mov     r8, rbx; unsigned __int16 *
0x1800025f3  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\WBEM\\WDM\\DREDGE"
0x1800025fa  call    ?ThisMofExistsInRegistry@CWMIBinMof@@QEAAHPEAG0KKH@Z; CWMIBinMof::ThisMofExistsInRegistry(ushort *,ushort *,ulong,ulong,int)
0x1800025ff  xor     ecx, ecx
0x180002601  test    eax, eax
0x180002603  cmovnz  r14d, ecx
0x180002607  jmp     loc_180002561
0x18000260c  cmp     word ptr [rsp+190h+var_138], 8
0x180002612  jz      loc_1800028C3
0x180002618  lea     rcx, [rbp+90h+pvarg]; pvarg
0x18000261c  call    cs:__imp_VariantClear
0x180002622  nop
0x180002623  lea     rcx, [rsp+190h+var_138]; pvarg
0x180002628  call    cs:__imp_VariantClear
0x18000262e  mov     rcx, [rsp+190h+Size]
0x180002633  test    rcx, rcx
0x180002636  jz      short loc_180002644
0x180002638  mov     rax, [rcx]
0x18000263b  mov     rax, [rax+10h]
0x18000263f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002644  mov     [rsp+190h+Size], 0
0x18000264d  test    ebx, ebx
0x18000264f  jz      loc_18000275F
0x180002655  mov     rcx, [rsp+190h+var_140]
0x18000265a  test    rcx, rcx
0x18000265d  jz      short loc_18000266B
0x18000265f  mov     rax, [rcx]
0x180002662  mov     rax, [rax+10h]
0x180002666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000266b  mov     [rsp+190h+var_140], 0
0x180002674  lea     rcx, [rsp+190h+var_118]; this
0x180002679  call    ?Clear@CBSTR@@QEAAXXZ; CBSTR::Clear(void)
0x18000267e  nop
0x18000267f  lea     rcx, [rbp+90h+var_110]; this
0x180002683  call    ?Clear@CBSTR@@QEAAXXZ; CBSTR::Clear(void)
0x180002688  nop
0x180002689  lea     rcx, [rbp+90h+psz]; this
0x18000268d  call    ??1CAutoWChar@@QEAA@XZ; CAutoWChar::~CAutoWChar(void)
0x180002692  nop
0x180002693  lea     rcx, [rbp+90h+var_108]; this
0x180002697  call    ?Clear@CBSTR@@QEAAXXZ; CBSTR::Clear(void)
0x18000269c  jmp     loc_180002561
0x1800026a1  mov     [rsp+190h+var_140], 0
0x1800026aa  mov     edx, 200h; int
0x1800026af  lea     rcx, [rbp+90h+psz]; this
0x1800026b3  call    ??0CAutoWChar@@QEAA@H@Z; CAutoWChar::CAutoWChar(int)
0x1800026b8  nop
0x1800026b9  mov     rbx, [rbp+90h+psz]
0x1800026bd  test    rbx, rbx
0x1800026c0  jz      short loc_180002689
0x1800026c2  mov     [rsp+190h+var_120], 0
0x1800026ca  mov     r9, rdi
0x1800026cd  lea     r8, aSelectFromWmib_0; "select * from WMIBinaryMofResource wher"...
0x1800026d4  mov     edx, 200h; unsigned __int64
0x1800026d9  mov     rcx, rbx; unsigned __int16 *
0x1800026dc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800026e1  test    eax, eax
0x1800026e3  js      short loc_180002689
0x1800026e5  mov     [rbp+90h+var_110], 0
0x1800026ed  mov     rdx, rbx; psz
0x1800026f0  lea     rcx, [rbp+90h+var_110]; this
0x1800026f4  call    ?SetStr@CBSTR@@QEAAXPEAG@Z; CBSTR::SetStr(ushort *)
0x1800026f9  nop
0x1800026fa  mov     [rsp+190h+var_118], 0
0x180002703  lea     rdx, aWql; "WQL"
0x18000270a  lea     rcx, [rsp+190h+var_118]; this
0x18000270f  call    ?SetStr@CBSTR@@QEAAXPEAG@Z; CBSTR::SetStr(ushort *)
0x180002714  nop
0x180002715  mov     rdx, [r15+18h]
0x180002719  mov     rcx, [rdx+10h]
0x18000271d  mov     rax, [rcx]
0x180002720  lea     r8, [rsp+190h+var_140]
0x180002725  mov     qword ptr [rsp+190h+var_168], r8
0x18000272a  mov     rdx, [rdx+18h]
0x18000272e  mov     [rsp+190h+var_170], rdx
0x180002733  mov     r9d, 30h ; '0'
0x180002739  mov     r8, [rbp+90h+var_110]
0x18000273d  mov     rdx, [rsp+190h+var_118]
0x180002742  mov     rax, [rax+0A0h]
0x180002749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000274e  test    eax, eax
0x180002750  jnz     loc_180002674
0x180002756  mov     [rsp+190h+Size], 0
0x18000275f  mov     rcx, [rsp+190h+var_140]
0x180002764  mov     rax, [rcx]
0x180002767  lea     rdx, [rsp+190h+var_120]
0x18000276c  mov     [rsp+190h+var_170], rdx
0x180002771  lea     r9, [rsp+190h+Size]
0x180002776  mov     edx, 7D0h
0x18000277b  mov     r8d, 1
0x180002781  mov     rax, [rax+20h]
0x180002785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000278a  mov     ebx, eax
0x18000278c  test    eax, eax
0x18000278e  jnz     loc_18000262E
0x180002794  lea     rcx, [rsp+190h+var_138]; pvarg
0x180002799  call    cs:__imp_VariantInit
0x18000279f  nop
0x1800027a0  lea     rcx, [rbp+90h+pvarg]; pvarg
0x1800027a4  call    cs:__imp_VariantInit
0x1800027aa  nop
0x1800027ab  mov     rcx, [rsp+190h+Size]
0x1800027b0  mov     rax, [rcx]
0x1800027b3  mov     qword ptr [rsp+190h+var_168], 0
0x1800027bc  mov     [rsp+190h+var_170], 0
0x1800027c5  lea     r9, [rsp+190h+var_138]
0x1800027ca  xor     r8d, r8d
0x1800027cd  lea     rdx, aRelpath; "__RELPATH"
0x1800027d4  mov     rax, [rax+20h]
0x1800027d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027dd  mov     ebx, eax
0x1800027df  test    eax, eax
0x1800027e1  jnz     loc_180002618
0x1800027e7  jmp     loc_18000260C
0x1800027ec  mov     [rbp+90h+var_108], 0
0x1800027f4  mov     rdx, rsi; psz
0x1800027f7  lea     rcx, [rbp+90h+var_108]; this
0x1800027fb  call    ?SetStr@CBSTR@@QEAAXPEAG@Z; CBSTR::SetStr(ushort *)
0x180002800  nop
0x180002801  mov     r9, [r15+18h]
0x180002805  mov     rcx, [r9+10h]
0x180002809  mov     rax, [rcx]
0x18000280c  mov     qword ptr [rsp+190h+var_168], 0
0x180002815  lea     rdx, [rsp+190h+var_148]
0x18000281a  mov     [rsp+190h+var_170], rdx
0x18000281f  mov     r9, [r9+18h]
0x180002823  xor     r8d, r8d
0x180002826  mov     rdx, [rbp+90h+var_108]
0x18000282a  mov     rax, [rax+30h]
0x18000282e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002833  test    eax, eax
0x180002835  jnz     loc_1800026A1
0x18000283b  xor     r14d, r14d
0x18000283e  lea     rcx, [rbp+90h+pvarg]; pvarg
0x180002842  call    cs:__imp_VariantInit
0x180002848  nop
0x180002849  mov     rcx, [rsp+190h+var_148]
0x18000284e  mov     rax, [rcx]
0x180002851  mov     qword ptr [rsp+190h+var_168], r14
0x180002856  mov     [rsp+190h+var_170], r14
0x18000285b  lea     r9, [rbp+90h+pvarg]
0x18000285f  xor     r8d, r8d
0x180002862  lea     rdx, aMofprocessed; "MofProcessed"
0x180002869  mov     rax, [rax+20h]
0x18000286d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002872  test    eax, eax
0x180002874  jnz     short loc_180002895
0x180002876  or      rcx, 0FFFFFFFFFFFFFFFFh; this
0x18000287a  cmp     word ptr [rbp+90h+pvarg+8], cx
0x18000287e  setz    al
0x180002881  mov     [rsp+190h+var_168], eax; int
0x180002885  mov     [rsp+190h+var_170], r12; unsigned int *
0x18000288a  mov     r9, r13; unsigned int *
0x18000288d  mov     r8, rbx; unsigned __int16 *
0x180002890  call    ?AddThisMofToRegistryIfNeeded@CWMIBinMof@@QEAAJPEAG0AEAK1H@Z; CWMIBinMof::AddThisMofToRegistryIfNeeded(ushort *,ushort *,ulong &,ulong &,int)
0x180002895  mov     rcx, [rsp+190h+var_148]
0x18000289a  test    rcx, rcx
0x18000289d  jz      short loc_1800028AB
0x18000289f  mov     rax, [rcx]
0x1800028a2  mov     rax, [rax+10h]
0x1800028a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028ab  mov     [rsp+190h+var_148], 0
0x1800028b4  lea     rcx, [rbp+90h+pvarg]; pvarg
0x1800028b8  call    cs:__imp_VariantClear
0x1800028be  jmp     loc_1800026A1
0x1800028c3  mov     rax, qword ptr [rsp+190h+var_138+8]
0x1800028c8  test    rax, rax
0x1800028cb  jz      loc_180002618
0x1800028d1  xor     ecx, ecx
0x1800028d3  cmp     word ptr [rsp+190h+var_138], 8
0x1800028d9  cmovz   rcx, rax; unsigned __int16 *
0x1800028dd  mov     rdx, rsi; unsigned __int16 *
0x1800028e0  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x1800028e5  test    eax, eax
0x1800028e7  jz      loc_180002618
0x1800028ed  mov     rdx, [r15+18h]
0x1800028f1  mov     rcx, [rdx+10h]
0x1800028f5  mov     rax, [rcx]
0x1800028f8  xor     r10d, r10d
0x1800028fb  cmp     word ptr [rsp+190h+var_138], 8
0x180002901  cmovz   r10, qword ptr [rsp+190h+var_138+8]
0x180002907  mov     [rsp+190h+var_170], 0
0x180002910  mov     r9, [rdx+18h]
0x180002914  xor     r8d, r8d
0x180002917  mov     rdx, r10
0x18000291a  mov     rax, [rax+80h]
0x180002921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002926  mov     ebx, eax
0x180002928  lea     rdx, aWeHaveBeenRequ_0; "We have been requested to delete this m"...
0x18000292f  mov     ecx, 0Ah
0x180002934  test    eax, eax
0x180002936  jns     short loc_18000296D
0x180002938  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x18000293e  xor     ecx, ecx
0x180002940  cmp     word ptr [rsp+190h+var_138], 8
0x180002946  cmovz   rcx, qword ptr [rsp+190h+var_138+8]; lpWideCharStr
0x18000294c  xor     edx, edx; int
  ... truncated ...
```
