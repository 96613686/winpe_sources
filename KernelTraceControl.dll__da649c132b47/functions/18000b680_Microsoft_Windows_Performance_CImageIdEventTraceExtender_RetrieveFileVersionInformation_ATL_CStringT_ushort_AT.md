# Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,XPerfCore::CFileMapping *)

- ea: `0x18000b680`
- end: `0x18000ba1c`
- name: `?RetrieveFileVersionInformation@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAVCFileMapping@XPerfCore@@@Z`
- size: `924`
- prototype: `__int64 __fastcall(__int64, __int64, const unsigned __int16 *, struct XPerfCore::CFileMapping *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b468`

## callees

- `0x1800067f0`
- `0x180006960`
- `0x180008c7c`
- `0x18000b680`
- `0x18000d9bc`
- `0x18000e858`
- `0x180010e6c`
- `0x180011364`
- `0x180011490`
- `0x1800268f4`
- `0x180026e30`
- `0x180027910`

## import_xrefs

- `VERSION!VerQueryValueW` at `0x18000b7b8`
- `VERSION!VerQueryValueW` at `0x18000b7b8`

## string_xrefs

- `0x18000b897`: `CompanyName`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        struct XPerfCore::CFileMapping *a4)
{
  void *v8; // rbx
  int VersionInfo; // esi
  unsigned __int64 v10; // r8
  __int64 result; // rax
  __int64 v12; // r15
  __int64 v13; // rax
  unsigned __int64 v14; // r8
  __int64 v15; // rax
  void *v16; // r14
  int Error; // esi
  unsigned int v18; // r12d
  unsigned __int64 v19; // r8
  __int64 v20; // rax
  unsigned __int64 v21; // r8
  __int64 v22; // rax
  unsigned __int64 v23; // r8
  __int64 v24; // rax
  int v25; // eax
  __int64 *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 *v30; // rdi
  unsigned int puLen[2]; // [rsp+30h] [rbp-298h] BYREF
  LPCVOID pBlock; // [rsp+38h] [rbp-290h] BYREF
  unsigned __int16 v33; // [rsp+40h] [rbp-288h]
  LPVOID lpBuffer; // [rsp+48h] [rbp-280h] BYREF
  const unsigned __int16 *v35; // [rsp+50h] [rbp-278h]
  __int64 v36; // [rsp+58h] [rbp-270h]
  __int64 v37; // [rsp+60h] [rbp-268h]
  ATL::CAtlException *v38; // [rsp+68h] [rbp-260h] BYREF
  unsigned __int16 v39[264]; // [rsp+70h] [rbp-258h] BYREF

  v37 = -2;
  v35 = a3;
  v36 = a1;
  try
  {
    v8 = 0;
    operator delete(0);
    pBlock = 0;
    if ( !a4 )
    {
      VersionInfo = -2147467261;
LABEL_6:
      operator delete(v8);
      return (unsigned int)VersionInfo;
    }
    VersionInfo = XPerfCore::CFileVersionInfo::GetVersionInfo((XPerfCore::CFileVersionInfo *)&pBlock, a3, a4);
    if ( VersionInfo < 0 )
    {
      v8 = (void *)pBlock;
      goto LABEL_6;
    }
    XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v39, v10, L"FileDescription");
    v12 = -1;
    v13 = -1;
    do
      ++v13;
    while ( v39[v13] );
    ATL::CSimpleStringT<unsigned short,0>::Append(a2, v39, (unsigned int)v13);
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
    XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v39, v14, L"FileVersion");
    v15 = -1;
    do
      ++v15;
    while ( v39[v15] );
    ATL::CSimpleStringT<unsigned short,0>::Append(a2, v39, (unsigned int)v15);
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
    v16 = (void *)pBlock;
    if ( !pBlock )
    {
      Error = -2147418113;
LABEL_17:
      operator delete(v16);
      return (unsigned int)Error;
    }
    puLen[0] = 0;
    if ( VerQueryValueW(pBlock, L"\\", &lpBuffer, puLen) )
    {
      v18 = puLen[0];
      Error = 0;
    }
    else
    {
      lpBuffer = 0;
      v18 = 0;
      Error = ATL::AtlHresultFromLastError();
    }
    if ( Error < 0 )
      goto LABEL_17;
    if ( v18 >= 0xC )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        a2,
        L"%u.%u.%u.%u",
        *((unsigned __int16 *)lpBuffer + 5),
        *((unsigned __int16 *)lpBuffer + 4),
        *((unsigned __int16 *)lpBuffer + 7),
        *((unsigned __int16 *)lpBuffer + 6));
      ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        a2,
        L"%u",
        v33);
      ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
      XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v39, v19, L"ProductName");
      v20 = -1;
      do
        ++v20;
      while ( v39[v20] );
      ATL::CSimpleStringT<unsigned short,0>::Append(a2, v39, (unsigned int)v20);
      ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
      XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v39, v21, L"CompanyName");
      v22 = -1;
      do
        ++v22;
      while ( v39[v22] );
      ATL::CSimpleStringT<unsigned short,0>::Append(a2, v39, (unsigned int)v22);
      ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
      XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v39, v23, L"ProductVersion");
      v24 = -1;
      do
        ++v24;
      while ( v39[v24] );
      ATL::CSimpleStringT<unsigned short,0>::Append(a2, v39, (unsigned int)v24);
      ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
      *(_QWORD *)puLen = 0;
      try
      {
        if ( Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable((Microsoft::Windows::Performance::CAeDelayLoad *)(a1 + 352)) )
          v25 = (*(__int64 (__fastcall **)(const unsigned __int16 *, __int64, unsigned int *))(a1 + 368))(v35, 1, puLen);
        else
          v25 = ATL::AtlHresultFromWin32(0x7Fu);
        v26 = *(__int64 **)puLen;
        if ( v25 < 0 )
          v26 = 0;
        *(_QWORD *)puLen = v26;
        if ( v26 )
        {
          v27 = *v26;
          if ( *v26 )
          {
            v28 = -1;
            do
              ++v28;
            while ( *(_WORD *)(v27 + 2 * v28) );
            ATL::CSimpleStringT<unsigned short,0>::Append(a2, v27, (unsigned int)v28);
          }
        }
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        if ( *(_QWORD *)puLen )
        {
          v29 = *(_QWORD *)(*(_QWORD *)puLen + 8LL);
          if ( v29 )
          {
            do
              ++v12;
            while ( *(_WORD *)(v29 + 2 * v12) );
            ATL::CSimpleStringT<unsigned short,0>::Append(a2, v29, (unsigned int)v12);
          }
        }
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        v30 = *(__int64 **)puLen;
        if ( *(_QWORD *)puLen )
        {
          if ( Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable((Microsoft::Windows::Performance::CAeDelayLoad *)(a1 + 352)) )
            (*(void (__fastcall **)(__int64 *))(a1 + 376))(v30);
          *(_QWORD *)puLen = 0;
        }
      }
      catch ( ... )
      {
        throw;
      }
      operator delete((void *)pBlock);
      result = 0;
    }
    else
    {
      operator delete(v16);
      result = 2147549183LL;
    }
  }
  catch ( ATL::CAtlException *v38 )
  {
    return *(unsigned int *)v38;
  }
  v8 = 0;
}

```

## disassembly

```asm
0x18000b680  push    rbx
0x18000b682  push    rsi
0x18000b683  push    rdi
0x18000b684  push    r12
0x18000b686  push    r13
0x18000b688  push    r14
0x18000b68a  push    r15
0x18000b68c  sub     rsp, 290h
0x18000b693  mov     [rsp+2C8h+var_268], 0FFFFFFFFFFFFFFFEh
0x18000b69c  mov     rax, cs:__security_cookie
0x18000b6a3  xor     rax, rsp
0x18000b6a6  mov     [rsp+2C8h+var_48], rax
0x18000b6ae  mov     rsi, r9
0x18000b6b1  mov     r14, r8
0x18000b6b4  mov     [rsp+2C8h+var_278], r8
0x18000b6b9  mov     rdi, rdx
0x18000b6bc  mov     r13, rcx
0x18000b6bf  mov     [rsp+2C8h+var_270], rcx
0x18000b6c4  xor     ebx, ebx
0x18000b6c6  mov     [rsp+2C8h+pBlock], rbx
0x18000b6cb  xor     ecx, ecx; Block
0x18000b6cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b6d2  mov     [rsp+2C8h+pBlock], rbx
0x18000b6d7  test    rsi, rsi
0x18000b6da  jnz     short loc_18000B6E3
0x18000b6dc  mov     esi, 80004003h
0x18000b6e1  jmp     short loc_18000B6FE
0x18000b6e3  mov     r8, rsi; struct XPerfCore::CFileMapping *
0x18000b6e6  mov     rdx, r14; unsigned __int16 *
0x18000b6e9  lea     rcx, [rsp+2C8h+pBlock]; this
0x18000b6ee  call    ?GetVersionInfo@CFileVersionInfo@XPerfCore@@QEAAJPEBGPEAVCFileMapping@2@@Z; XPerfCore::CFileVersionInfo::GetVersionInfo(ushort const *,XPerfCore::CFileMapping *)
0x18000b6f3  mov     esi, eax
0x18000b6f5  test    eax, eax
0x18000b6f7  jns     short loc_18000B70D
0x18000b6f9  mov     rbx, [rsp+2C8h+pBlock]
0x18000b6fe  mov     rcx, rbx; Block
0x18000b701  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b706  mov     eax, esi
0x18000b708  jmp     loc_18000B9F8
0x18000b70d  lea     r9, aFiledescriptio; "FileDescription"
0x18000b714  lea     rdx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18000b719  lea     rcx, [rsp+2C8h+pBlock]; this
0x18000b71e  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x18000b723  lea     rcx, [rsp+2C8h+var_258]
0x18000b728  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000b72c  mov     rax, r15
0x18000b72f  inc     rax
0x18000b732  cmp     [rcx+rax*2], bx
0x18000b736  jnz     short loc_18000B72F
0x18000b738  mov     r8d, eax
0x18000b73b  lea     rdx, [rsp+2C8h+var_258]
0x18000b740  mov     rcx, rdi
0x18000b743  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18000b748  mov     rcx, rdi
0x18000b74b  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18000b750  lea     r9, aFileversion; "FileVersion"
0x18000b757  lea     rdx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18000b75c  lea     rcx, [rsp+2C8h+pBlock]; this
0x18000b761  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x18000b766  lea     rcx, [rsp+2C8h+var_258]
0x18000b76b  mov     rax, r15
0x18000b76e  inc     rax
0x18000b771  cmp     [rcx+rax*2], bx
0x18000b775  jnz     short loc_18000B76E
0x18000b777  mov     r8d, eax
0x18000b77a  lea     rdx, [rsp+2C8h+var_258]
0x18000b77f  mov     rcx, rdi
0x18000b782  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18000b787  mov     rcx, rdi
0x18000b78a  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18000b78f  mov     r14, [rsp+2C8h+pBlock]
0x18000b794  test    r14, r14
0x18000b797  jnz     short loc_18000B7A0
0x18000b799  mov     esi, 8000FFFFh
0x18000b79e  jmp     short loc_18000B7DE
0x18000b7a0  mov     [rsp+2C8h+puLen], ebx
0x18000b7a4  lea     r9, [rsp+2C8h+puLen]; puLen
0x18000b7a9  lea     r8, [rsp+2C8h+lpBuffer]; lplpBuffer
0x18000b7ae  lea     rdx, SubBlock; "\\"
0x18000b7b5  mov     rcx, r14; pBlock
0x18000b7b8  call    cs:__imp_VerQueryValueW
0x18000b7be  test    eax, eax
0x18000b7c0  jnz     short loc_18000B7D3
0x18000b7c2  mov     [rsp+2C8h+lpBuffer], rbx
0x18000b7c7  mov     r12d, ebx
0x18000b7ca  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000b7cf  mov     esi, eax
0x18000b7d1  jmp     short loc_18000B7DA
0x18000b7d3  mov     r12d, [rsp+2C8h+puLen]
0x18000b7d8  mov     esi, ebx
0x18000b7da  test    esi, esi
0x18000b7dc  jns     short loc_18000B7ED
0x18000b7de  mov     rcx, r14; Block
0x18000b7e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b7e6  mov     eax, esi
0x18000b7e8  jmp     loc_18000B9F8
0x18000b7ed  cmp     r12d, 0Ch
0x18000b7f1  jnb     short loc_18000B805
0x18000b7f3  mov     rcx, r14; Block
0x18000b7f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b7fb  mov     eax, 8000FFFFh
0x18000b800  jmp     loc_18000B9F8
0x18000b805  mov     rdx, [rsp+2C8h+lpBuffer]
0x18000b80a  movzx   eax, word ptr [rdx+0Ch]
0x18000b80e  movzx   ecx, word ptr [rdx+0Eh]
0x18000b812  movzx   r9d, word ptr [rdx+8]
0x18000b817  movzx   r8d, word ptr [rdx+0Ah]
0x18000b81c  mov     [rsp+2C8h+var_2A0], eax
0x18000b820  mov     [rsp+2C8h+var_2A8], ecx
0x18000b824  lea     rdx, aUUUU; "%u.%u.%u.%u"
0x18000b82b  mov     rcx, rdi
0x18000b82e  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18000b833  mov     rcx, rdi
0x18000b836  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18000b83b  movzx   r8d, [rsp+2C8h+var_288]
0x18000b841  lea     rdx, aU; "%u"
0x18000b848  mov     rcx, rdi
0x18000b84b  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18000b850  mov     rcx, rdi
0x18000b853  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18000b858  lea     r9, aProductname; "ProductName"
0x18000b85f  lea     rdx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18000b864  lea     rcx, [rsp+2C8h+pBlock]; this
0x18000b869  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x18000b86e  lea     rcx, [rsp+2C8h+var_258]
0x18000b873  mov     rax, r15
0x18000b876  inc     rax
0x18000b879  cmp     [rcx+rax*2], bx
0x18000b87d  jnz     short loc_18000B876
0x18000b87f  mov     r8d, eax
0x18000b882  lea     rdx, [rsp+2C8h+var_258]
0x18000b887  mov     rcx, rdi
0x18000b88a  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18000b88f  mov     rcx, rdi
0x18000b892  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18000b897  lea     r9, aCompanyname; "CompanyName"
0x18000b89e  lea     rdx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18000b8a3  lea     rcx, [rsp+2C8h+pBlock]; this
0x18000b8a8  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x18000b8ad  lea     rcx, [rsp+2C8h+var_258]
0x18000b8b2  mov     rax, r15
0x18000b8b5  inc     rax
0x18000b8b8  cmp     [rcx+rax*2], bx
0x18000b8bc  jnz     short loc_18000B8B5
0x18000b8be  mov     r8d, eax
0x18000b8c1  lea     rdx, [rsp+2C8h+var_258]
0x18000b8c6  mov     rcx, rdi
0x18000b8c9  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18000b8ce  mov     rcx, rdi
0x18000b8d1  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18000b8d6  lea     r9, aProductversion; "ProductVersion"
0x18000b8dd  lea     rdx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18000b8e2  lea     rcx, [rsp+2C8h+pBlock]; this
0x18000b8e7  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x18000b8ec  lea     rcx, [rsp+2C8h+var_258]
0x18000b8f1  mov     rax, r15
0x18000b8f4  inc     rax
0x18000b8f7  cmp     [rcx+rax*2], bx
0x18000b8fb  jnz     short loc_18000B8F4
0x18000b8fd  mov     r8d, eax
0x18000b900  lea     rdx, [rsp+2C8h+var_258]
0x18000b905  mov     rcx, rdi
0x18000b908  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18000b90d  mov     rcx, rdi
0x18000b910  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18000b915  mov     qword ptr [rsp+2C8h+puLen], rbx
0x18000b91a  lea     rsi, [r13+160h]
0x18000b921  mov     rcx, rsi; this
0x18000b924  call    ?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ; Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)
0x18000b929  test    al, al
0x18000b92b  jz      short loc_18000B948
0x18000b92d  lea     r8, [rsp+2C8h+puLen]
0x18000b932  mov     edx, 1
0x18000b937  mov     rcx, [rsp+2C8h+var_278]
0x18000b93c  mov     rax, [rsi+10h]
0x18000b940  call    cs:__guard_dispatch_icall_fptr
0x18000b946  jmp     short loc_18000B952
0x18000b948  mov     ecx, 7Fh; unsigned int
0x18000b94d  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000b952  mov     rcx, qword ptr [rsp+2C8h+puLen]
0x18000b957  test    eax, eax
0x18000b959  cmovs   rcx, rbx
0x18000b95d  mov     qword ptr [rsp+2C8h+puLen], rcx
0x18000b962  test    rcx, rcx
0x18000b965  jz      short loc_18000B986
0x18000b967  mov     rdx, [rcx]
0x18000b96a  test    rdx, rdx
0x18000b96d  jz      short loc_18000B986
0x18000b96f  mov     rax, r15
0x18000b972  inc     rax
0x18000b975  cmp     [rdx+rax*2], bx
0x18000b979  jnz     short loc_18000B972
0x18000b97b  mov     r8d, eax
0x18000b97e  mov     rcx, rdi
0x18000b981  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18000b986  mov     rcx, rdi
0x18000b989  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18000b98e  mov     rdx, qword ptr [rsp+2C8h+puLen]
0x18000b993  test    rdx, rdx
0x18000b996  jz      short loc_18000B9B6
0x18000b998  mov     rdx, [rdx+8]
0x18000b99c  test    rdx, rdx
0x18000b99f  jz      short loc_18000B9B6
0x18000b9a1  inc     r15
0x18000b9a4  cmp     [rdx+r15*2], bx
0x18000b9a9  jnz     short loc_18000B9A1
0x18000b9ab  mov     r8d, r15d
0x18000b9ae  mov     rcx, rdi
0x18000b9b1  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18000b9b6  mov     rcx, rdi
0x18000b9b9  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18000b9be  mov     rdi, qword ptr [rsp+2C8h+puLen]
0x18000b9c3  test    rdi, rdi
0x18000b9c6  jz      short loc_18000B9E6
0x18000b9c8  mov     rcx, rsi; this
0x18000b9cb  call    ?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ; Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)
0x18000b9d0  test    al, al
0x18000b9d2  jz      short loc_18000B9E1
0x18000b9d4  mov     rcx, rdi
0x18000b9d7  mov     rax, [rsi+18h]
0x18000b9db  call    cs:__guard_dispatch_icall_fptr
0x18000b9e1  mov     qword ptr [rsp+2C8h+puLen], rbx
0x18000b9e6  mov     rcx, [rsp+2C8h+pBlock]; Block
0x18000b9eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b9f0  xor     eax, eax
0x18000b9f2  jmp     short loc_18000B9F8
0x18000b9f4  mov     eax, [rsp+2C8h+puLen]
0x18000b9f8  mov     rcx, [rsp+2C8h+var_48]
0x18000ba00  xor     rcx, rsp; StackCookie
0x18000ba03  call    __security_check_cookie
0x18000ba08  add     rsp, 290h
0x18000ba0f  pop     r15
0x18000ba11  pop     r14
0x18000ba13  pop     r13
0x18000ba15  pop     r12
0x18000ba17  pop     rdi
0x18000ba18  pop     rsi
0x18000ba19  pop     rbx
0x18000ba1a  retn
```
