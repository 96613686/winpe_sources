# Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,XPerfCore::CFileMapping *)

- ea: `0x180027508`
- end: `0x180027882`
- name: `?RetrieveFileVersionInformation@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAVCFileMapping@XPerfCore@@@Z`
- size: `890`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002102c`

## callees

- `0x180001b90`
- `0x180001bf8`
- `0x1800161d4`
- `0x180016274`
- `0x18001629c`
- `0x1800230a0`
- `0x180023180`
- `0x180023f6c`
- `0x180024084`
- `0x180024908`
- `0x180027508`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18002762e`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18002762e`

## string_xrefs

- `0x180027706`: `CompanyName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(
        __int64 a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        struct XPerfCore::CFileMapping *a4)
{
  unsigned __int64 v8; // rdx
  void *v9; // rcx
  int VersionInfo; // edi
  unsigned __int64 v11; // r8
  __int64 result; // rax
  __int64 v13; // rsi
  __int64 v14; // r8
  unsigned __int64 v15; // r8
  __int64 v16; // r8
  unsigned __int64 v17; // rdx
  void *v18; // rdi
  int Error; // ebx
  unsigned __int64 v20; // r8
  __int64 v21; // r8
  unsigned __int64 v22; // r8
  __int64 v23; // r8
  unsigned __int64 v24; // r8
  __int64 v25; // r8
  int v26; // eax
  __int64 *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdx
  unsigned __int64 v31; // rdx
  __int64 *v32; // rbx
  unsigned int puLen[2]; // [rsp+30h] [rbp-288h] BYREF
  LPCVOID pBlock; // [rsp+38h] [rbp-280h] BYREF
  unsigned __int16 v35; // [rsp+40h] [rbp-278h]
  LPVOID lpBuffer[2]; // [rsp+48h] [rbp-270h] BYREF
  ATL::CAtlException *v37; // [rsp+58h] [rbp-260h] BYREF
  unsigned __int16 v38[264]; // [rsp+60h] [rbp-258h] BYREF

  lpBuffer[1] = (LPVOID)a1;
  operator delete(0, a2);
  v9 = 0;
  pBlock = 0;
  if ( !a4 )
  {
    VersionInfo = -2147467261;
LABEL_5:
    operator delete(v9, v8);
    return (unsigned int)VersionInfo;
  }
  VersionInfo = XPerfCore::CFileVersionInfo::GetVersionInfo((XPerfCore::CFileVersionInfo *)&pBlock, a3, a4);
  if ( VersionInfo < 0 )
  {
    v9 = (void *)pBlock;
    goto LABEL_5;
  }
  XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v38, v11, L"FileDescription");
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( v38[v14] );
  try
  {
    ATL::CSimpleStringT<unsigned short,0>::Append(a2, v38, v14);
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
    XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v38, v15, L"FileVersion");
    v16 = -1;
    do
      ++v16;
    while ( v38[v16] );
    ATL::CSimpleStringT<unsigned short,0>::Append(a2, v38, v16);
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
    lpBuffer[0] = 0;
    v18 = (void *)pBlock;
    if ( !pBlock )
    {
      Error = -2147418113;
LABEL_14:
      operator delete(v18, v17);
      return (unsigned int)Error;
    }
    puLen[0] = 0;
    if ( VerQueryValueW(pBlock, L"\\", lpBuffer, puLen) )
    {
      if ( puLen[0] >= 0xC )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          a2,
          L"%u.%u.%u.%u",
          *((unsigned __int16 *)lpBuffer[0] + 5),
          *((unsigned __int16 *)lpBuffer[0] + 4),
          *((unsigned __int16 *)lpBuffer[0] + 7),
          *((unsigned __int16 *)lpBuffer[0] + 6));
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          a2,
          L"%u",
          v35);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v38, v20, L"ProductName");
        v21 = -1;
        do
          ++v21;
        while ( v38[v21] );
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, v38, v21);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v38, v22, L"CompanyName");
        v23 = -1;
        do
          ++v23;
        while ( v38[v23] );
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, v38, v23);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v38, v24, L"ProductVersion");
        v25 = -1;
        do
          ++v25;
        while ( v38[v25] );
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, v38, v25);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        *(_QWORD *)puLen = 0;
        try
        {
          if ( Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable((Microsoft::Windows::Performance::CAeDelayLoad *)(a1 + 296)) )
            v26 = (*(__int64 (__fastcall **)(const unsigned __int16 *, __int64, unsigned int *))(a1 + 312))(
                    a3,
                    1,
                    puLen);
          else
            v26 = ATL::AtlHresultFromWin32(0x7Fu);
          if ( v26 >= 0 )
          {
            v27 = *(__int64 **)puLen;
          }
          else
          {
            v27 = 0;
            *(_QWORD *)puLen = 0;
          }
          if ( v27 )
          {
            v28 = *v27;
            if ( *v27 )
            {
              v29 = -1;
              do
                ++v29;
              while ( *(_WORD *)(v28 + 2 * v29) );
              ATL::CSimpleStringT<unsigned short,0>::Append(a2, v28, v29);
            }
          }
          ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
          if ( *(_QWORD *)puLen )
          {
            v30 = *(_QWORD *)(*(_QWORD *)puLen + 8LL);
            if ( v30 )
            {
              do
                ++v13;
              while ( *(_WORD *)(v30 + 2 * v13) );
              ATL::CSimpleStringT<unsigned short,0>::Append(a2, v30, (unsigned int)v13);
            }
          }
          ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
          v32 = *(__int64 **)puLen;
          if ( *(_QWORD *)puLen )
          {
            if ( Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable((Microsoft::Windows::Performance::CAeDelayLoad *)(a1 + 296)) )
              (*(void (__fastcall **)(__int64 *))(a1 + 320))(v32);
            *(_QWORD *)puLen = 0;
          }
        }
        catch ( ... )
        {
          throw;
        }
        operator delete((void *)pBlock, v31);
        return 0;
      }
    }
    else
    {
      lpBuffer[0] = 0;
      Error = ATL::AtlHresultFromLastError();
      if ( Error < 0 )
        goto LABEL_14;
    }
    operator delete(v18, v17);
    result = 2147549183LL;
  }
  catch ( ATL::CAtlException *v37 )
  {
    return *(unsigned int *)v37;
  }
  return result;
}

```

## disassembly

```asm
0x180027508  push    rbx
0x18002750a  push    rsi
0x18002750b  push    rdi
0x18002750c  push    r12
0x18002750e  push    r14
0x180027510  push    r15
0x180027512  sub     rsp, 288h
0x180027519  mov     rax, cs:__security_cookie
0x180027520  xor     rax, rsp
0x180027523  mov     [rsp+2B8h+var_48], rax
0x18002752b  mov     rdi, r9
0x18002752e  mov     r15, r8
0x180027531  mov     rbx, rdx
0x180027534  mov     r14, rcx
0x180027537  mov     [rsp+2B8h+var_268], rcx
0x18002753c  xor     ecx, ecx; void *
0x18002753e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027543  xor     r12d, r12d
0x180027546  mov     ecx, r12d
0x180027549  mov     [rsp+2B8h+pBlock], rcx
0x18002754e  test    rdi, rdi
0x180027551  jnz     short loc_18002755A
0x180027553  mov     edi, 80004003h
0x180027558  jmp     short loc_180027575
0x18002755a  mov     r8, rdi; struct XPerfCore::CFileMapping *
0x18002755d  mov     rdx, r15; unsigned __int16 *
0x180027560  lea     rcx, [rsp+2B8h+pBlock]; this
0x180027565  call    ?GetVersionInfo@CFileVersionInfo@XPerfCore@@QEAAJPEBGPEAVCFileMapping@2@@Z; XPerfCore::CFileVersionInfo::GetVersionInfo(ushort const *,XPerfCore::CFileMapping *)
0x18002756a  mov     edi, eax
0x18002756c  test    eax, eax
0x18002756e  jns     short loc_180027581
0x180027570  mov     rcx, [rsp+2B8h+pBlock]; void *
0x180027575  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002757a  mov     eax, edi
0x18002757c  jmp     loc_180027860
0x180027581  lea     r9, aFiledescriptio; "FileDescription"
0x180027588  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x18002758d  lea     rcx, [rsp+2B8h+pBlock]; this
0x180027592  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x180027597  lea     rax, [rsp+2B8h+var_258]
0x18002759c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800275a0  mov     r8, rsi
0x1800275a3  inc     r8
0x1800275a6  cmp     [rax+r8*2], r12w
0x1800275ab  jnz     short loc_1800275A3
0x1800275ad  lea     rdx, [rsp+2B8h+var_258]
0x1800275b2  mov     rcx, rbx
0x1800275b5  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800275ba  mov     rcx, rbx
0x1800275bd  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x1800275c2  lea     r9, aFileversion; "FileVersion"
0x1800275c9  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x1800275ce  lea     rcx, [rsp+2B8h+pBlock]; this
0x1800275d3  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x1800275d8  lea     rax, [rsp+2B8h+var_258]
0x1800275dd  mov     r8, rsi
0x1800275e0  inc     r8
0x1800275e3  cmp     [rax+r8*2], r12w
0x1800275e8  jnz     short loc_1800275E0
0x1800275ea  lea     rdx, [rsp+2B8h+var_258]
0x1800275ef  mov     rcx, rbx
0x1800275f2  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800275f7  mov     rcx, rbx
0x1800275fa  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x1800275ff  mov     [rsp+2B8h+lpBuffer], r12
0x180027604  mov     rdi, [rsp+2B8h+pBlock]
0x180027609  test    rdi, rdi
0x18002760c  jnz     short loc_180027615
0x18002760e  mov     ebx, 8000FFFFh
0x180027613  jmp     short loc_18002764E
0x180027615  mov     [rsp+2B8h+puLen], r12d
0x18002761a  lea     r9, [rsp+2B8h+puLen]; puLen
0x18002761f  lea     r8, [rsp+2B8h+lpBuffer]; lplpBuffer
0x180027624  lea     rdx, StringValue; "\\"
0x18002762b  mov     rcx, rdi; pBlock
0x18002762e  call    cs:__imp_VerQueryValueW
0x180027635  nop     dword ptr [rax+rax+00h]
0x18002763a  test    eax, eax
0x18002763c  jnz     short loc_18002765D
0x18002763e  mov     [rsp+2B8h+lpBuffer], r12
0x180027643  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180027648  mov     ebx, eax
0x18002764a  test    eax, eax
0x18002764c  jns     short loc_180027664
0x18002764e  mov     rcx, rdi; void *
0x180027651  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027656  mov     eax, ebx
0x180027658  jmp     loc_180027860
0x18002765d  cmp     [rsp+2B8h+puLen], 0Ch
0x180027662  jnb     short loc_180027676
0x180027664  mov     rcx, rdi; void *
0x180027667  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002766c  mov     eax, 8000FFFFh
0x180027671  jmp     loc_180027860
0x180027676  mov     rdx, [rsp+2B8h+lpBuffer]
0x18002767b  movzx   eax, word ptr [rdx+0Ch]
0x18002767f  movzx   ecx, word ptr [rdx+0Eh]
0x180027683  movzx   r9d, word ptr [rdx+8]
0x180027688  movzx   r8d, word ptr [rdx+0Ah]
0x18002768d  mov     [rsp+2B8h+var_290], eax
0x180027691  mov     [rsp+2B8h+var_298], ecx
0x180027695  lea     rdx, aUUUU; "%u.%u.%u.%u"
0x18002769c  mov     rcx, rbx
0x18002769f  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800276a4  mov     rcx, rbx
0x1800276a7  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x1800276ac  movzx   r8d, [rsp+2B8h+var_278]
0x1800276b2  lea     rdx, aU; "%u"
0x1800276b9  mov     rcx, rbx
0x1800276bc  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800276c1  mov     rcx, rbx
0x1800276c4  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x1800276c9  lea     r9, aProductname; "ProductName"
0x1800276d0  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x1800276d5  lea     rcx, [rsp+2B8h+pBlock]; this
0x1800276da  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x1800276df  lea     rax, [rsp+2B8h+var_258]
0x1800276e4  mov     r8, rsi
0x1800276e7  inc     r8
0x1800276ea  cmp     [rax+r8*2], r12w
0x1800276ef  jnz     short loc_1800276E7
0x1800276f1  lea     rdx, [rsp+2B8h+var_258]
0x1800276f6  mov     rcx, rbx
0x1800276f9  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800276fe  mov     rcx, rbx
0x180027701  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x180027706  lea     r9, aCompanyname; "CompanyName"
0x18002770d  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x180027712  lea     rcx, [rsp+2B8h+pBlock]; this
0x180027717  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x18002771c  lea     rax, [rsp+2B8h+var_258]
0x180027721  mov     r8, rsi
0x180027724  inc     r8
0x180027727  cmp     [rax+r8*2], r12w
0x18002772c  jnz     short loc_180027724
0x18002772e  lea     rdx, [rsp+2B8h+var_258]
0x180027733  mov     rcx, rbx
0x180027736  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18002773b  mov     rcx, rbx
0x18002773e  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x180027743  lea     r9, aProductversion; "ProductVersion"
0x18002774a  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x18002774f  lea     rcx, [rsp+2B8h+pBlock]; this
0x180027754  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x180027759  lea     rax, [rsp+2B8h+var_258]
0x18002775e  mov     r8, rsi
0x180027761  inc     r8
0x180027764  cmp     [rax+r8*2], r12w
0x180027769  jnz     short loc_180027761
0x18002776b  lea     rdx, [rsp+2B8h+var_258]
0x180027770  mov     rcx, rbx
0x180027773  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180027778  mov     rcx, rbx
0x18002777b  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x180027780  mov     qword ptr [rsp+2B8h+puLen], r12
0x180027785  lea     rdi, [r14+128h]
0x18002778c  mov     rcx, rdi; this
0x18002778f  call    ?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ; Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)
0x180027794  test    al, al
0x180027796  jz      short loc_1800277B0
0x180027798  lea     r8, [rsp+2B8h+puLen]
0x18002779d  mov     edx, 1
0x1800277a2  mov     rcx, r15
0x1800277a5  mov     rax, [rdi+10h]
0x1800277a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277ae  jmp     short loc_1800277BA
0x1800277b0  mov     ecx, 7Fh; unsigned int
0x1800277b5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800277ba  test    eax, eax
0x1800277bc  jns     short loc_1800277C8
0x1800277be  mov     rax, r12
0x1800277c1  mov     qword ptr [rsp+2B8h+puLen], rax
0x1800277c6  jmp     short loc_1800277CD
0x1800277c8  mov     rax, qword ptr [rsp+2B8h+puLen]
0x1800277cd  test    rax, rax
0x1800277d0  jz      short loc_1800277EF
0x1800277d2  mov     rdx, [rax]
0x1800277d5  test    rdx, rdx
0x1800277d8  jz      short loc_1800277EF
0x1800277da  mov     r8, rsi
0x1800277dd  inc     r8
0x1800277e0  cmp     [rdx+r8*2], r12w
0x1800277e5  jnz     short loc_1800277DD
0x1800277e7  mov     rcx, rbx
0x1800277ea  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800277ef  mov     rcx, rbx
0x1800277f2  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x1800277f7  mov     rdx, qword ptr [rsp+2B8h+puLen]
0x1800277fc  test    rdx, rdx
0x1800277ff  jz      short loc_18002781F
0x180027801  mov     rdx, [rdx+8]
0x180027805  test    rdx, rdx
0x180027808  jz      short loc_18002781F
0x18002780a  inc     rsi
0x18002780d  cmp     [rdx+rsi*2], r12w
0x180027812  jnz     short loc_18002780A
0x180027814  mov     r8d, esi
0x180027817  mov     rcx, rbx
0x18002781a  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18002781f  mov     rcx, rbx
0x180027822  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x180027827  mov     rbx, qword ptr [rsp+2B8h+puLen]
0x18002782c  test    rbx, rbx
0x18002782f  jz      short loc_18002784E
0x180027831  mov     rcx, rdi; this
0x180027834  call    ?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ; Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)
0x180027839  test    al, al
0x18002783b  jz      short loc_180027849
0x18002783d  mov     rcx, rbx
0x180027840  mov     rax, [rdi+18h]
0x180027844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027849  mov     qword ptr [rsp+2B8h+puLen], r12
0x18002784e  mov     rcx, [rsp+2B8h+pBlock]; void *
0x180027853  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027858  xor     eax, eax
0x18002785a  jmp     short loc_180027860
0x18002785c  mov     eax, [rsp+2B8h+puLen]
0x180027860  mov     rcx, [rsp+2B8h+var_48]
0x180027868  xor     rcx, rsp; StackCookie
0x18002786b  call    __security_check_cookie
0x180027870  add     rsp, 288h
0x180027877  pop     r15
0x180027879  pop     r14
0x18002787b  pop     r12
0x18002787d  pop     rdi
0x18002787e  pop     rsi
0x18002787f  pop     rbx
0x180027880  retn
```
