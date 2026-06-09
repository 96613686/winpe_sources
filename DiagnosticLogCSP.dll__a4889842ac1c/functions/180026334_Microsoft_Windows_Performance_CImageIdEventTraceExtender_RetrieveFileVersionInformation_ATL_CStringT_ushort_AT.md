# Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,XPerfCore::CFileMapping *)

- ea: `0x180026334`
- end: `0x1800266a8`
- name: `?RetrieveFileVersionInformation@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAVCFileMapping@XPerfCore@@@Z`
- size: `884`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001ffec`

## callees

- `0x180001b60`
- `0x180001bc8`
- `0x180015674`
- `0x180015710`
- `0x180015734`
- `0x18002215c`
- `0x180022240`
- `0x180022eec`
- `0x180022ffc`
- `0x1800237fc`
- `0x180026334`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18002645a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18002645a`

## string_xrefs

- `0x18002652c`: `CompanyName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(
        __int64 a1,
        __int64 *a2,
        const unsigned __int16 *a3,
        struct XPerfCore::CFileMapping *a4)
{
  void *v8; // rcx
  int VersionInfo; // edi
  unsigned __int64 v10; // r8
  __int64 result; // rax
  __int64 v12; // rsi
  __int64 v13; // r8
  unsigned __int64 v14; // r8
  __int64 v15; // r8
  void *v16; // rdi
  signed int Error; // ebx
  unsigned __int64 v18; // r8
  __int64 v19; // r8
  unsigned __int64 v20; // r8
  __int64 v21; // r8
  unsigned __int64 v22; // r8
  __int64 v23; // r8
  int v24; // eax
  __int64 *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 *v29; // rbx
  unsigned int puLen[2]; // [rsp+30h] [rbp-288h] BYREF
  LPCVOID pBlock; // [rsp+38h] [rbp-280h] BYREF
  unsigned __int16 v32; // [rsp+40h] [rbp-278h]
  LPVOID lpBuffer[2]; // [rsp+48h] [rbp-270h] BYREF
  ATL::CAtlException *v34; // [rsp+58h] [rbp-260h] BYREF
  unsigned __int16 v35[264]; // [rsp+60h] [rbp-258h] BYREF

  lpBuffer[1] = (LPVOID)a1;
  operator delete(0);
  v8 = 0;
  pBlock = 0;
  if ( !a4 )
  {
    VersionInfo = -2147467261;
LABEL_5:
    operator delete(v8);
    return (unsigned int)VersionInfo;
  }
  VersionInfo = XPerfCore::CFileVersionInfo::GetVersionInfo((XPerfCore::CFileVersionInfo *)&pBlock, a3, a4);
  if ( VersionInfo < 0 )
  {
    v8 = (void *)pBlock;
    goto LABEL_5;
  }
  XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v35, v10, L"FileDescription");
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( v35[v13] );
  try
  {
    ATL::CSimpleStringT<unsigned short,0>::Append(a2, (__int64)v35, v13);
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
    XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v35, v14, L"FileVersion");
    v15 = -1;
    do
      ++v15;
    while ( v35[v15] );
    ATL::CSimpleStringT<unsigned short,0>::Append(a2, (__int64)v35, v15);
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
    lpBuffer[0] = 0;
    v16 = (void *)pBlock;
    if ( !pBlock )
    {
      Error = -2147418113;
LABEL_14:
      operator delete(v16);
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
          v32);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v35, v18, L"ProductName");
        v19 = -1;
        do
          ++v19;
        while ( v35[v19] );
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, (__int64)v35, v19);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v35, v20, L"CompanyName");
        v21 = -1;
        do
          ++v21;
        while ( v35[v21] );
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, (__int64)v35, v21);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v35, v22, L"ProductVersion");
        v23 = -1;
        do
          ++v23;
        while ( v35[v23] );
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, (__int64)v35, v23);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        *(_QWORD *)puLen = 0;
        try
        {
          if ( Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable((Microsoft::Windows::Performance::CAeDelayLoad *)(a1 + 296)) )
            v24 = (*(__int64 (__fastcall **)(const unsigned __int16 *, __int64, unsigned int *))(a1 + 312))(
                    a3,
                    1,
                    puLen);
          else
            v24 = ATL::AtlHresultFromWin32(127);
          if ( v24 >= 0 )
          {
            v25 = *(__int64 **)puLen;
          }
          else
          {
            v25 = 0;
            *(_QWORD *)puLen = 0;
          }
          if ( v25 )
          {
            v26 = *v25;
            if ( *v25 )
            {
              v27 = -1;
              do
                ++v27;
              while ( *(_WORD *)(v26 + 2 * v27) );
              ATL::CSimpleStringT<unsigned short,0>::Append(a2, v26, v27);
            }
          }
          ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
          if ( *(_QWORD *)puLen )
          {
            v28 = *(_QWORD *)(*(_QWORD *)puLen + 8LL);
            if ( v28 )
            {
              do
                ++v12;
              while ( *(_WORD *)(v28 + 2 * v12) );
              ATL::CSimpleStringT<unsigned short,0>::Append(a2, v28, v12);
            }
          }
          ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
          v29 = *(__int64 **)puLen;
          if ( *(_QWORD *)puLen )
          {
            if ( Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable((Microsoft::Windows::Performance::CAeDelayLoad *)(a1 + 296)) )
              (*(void (__fastcall **)(__int64 *))(a1 + 320))(v29);
            *(_QWORD *)puLen = 0;
          }
        }
        catch ( ... )
        {
          throw;
        }
        operator delete((void *)pBlock);
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
    operator delete(v16);
    result = 2147549183LL;
  }
  catch ( ATL::CAtlException *v34 )
  {
    return *(unsigned int *)v34;
  }
  return result;
}

```

## disassembly

```asm
0x180026334  push    rbx
0x180026336  push    rsi
0x180026337  push    rdi
0x180026338  push    r12
0x18002633a  push    r14
0x18002633c  push    r15
0x18002633e  sub     rsp, 288h
0x180026345  mov     rax, cs:__security_cookie
0x18002634c  xor     rax, rsp
0x18002634f  mov     [rsp+2B8h+var_48], rax
0x180026357  mov     rdi, r9
0x18002635a  mov     r15, r8
0x18002635d  mov     rbx, rdx
0x180026360  mov     r14, rcx
0x180026363  mov     [rsp+2B8h+var_268], rcx
0x180026368  xor     ecx, ecx; void *
0x18002636a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002636f  xor     r12d, r12d
0x180026372  mov     ecx, r12d
0x180026375  mov     [rsp+2B8h+pBlock], rcx
0x18002637a  test    rdi, rdi
0x18002637d  jnz     short loc_180026386
0x18002637f  mov     edi, 80004003h
0x180026384  jmp     short loc_1800263A1
0x180026386  mov     r8, rdi; struct XPerfCore::CFileMapping *
0x180026389  mov     rdx, r15; unsigned __int16 *
0x18002638c  lea     rcx, [rsp+2B8h+pBlock]; this
0x180026391  call    ?GetVersionInfo@CFileVersionInfo@XPerfCore@@QEAAJPEBGPEAVCFileMapping@2@@Z; XPerfCore::CFileVersionInfo::GetVersionInfo(ushort const *,XPerfCore::CFileMapping *)
0x180026396  mov     edi, eax
0x180026398  test    eax, eax
0x18002639a  jns     short loc_1800263AD
0x18002639c  mov     rcx, [rsp+2B8h+pBlock]; void *
0x1800263a1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800263a6  mov     eax, edi
0x1800263a8  jmp     loc_180026686
0x1800263ad  lea     r9, aFiledescriptio; "FileDescription"
0x1800263b4  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x1800263b9  lea     rcx, [rsp+2B8h+pBlock]; this
0x1800263be  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x1800263c3  lea     rax, [rsp+2B8h+var_258]
0x1800263c8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800263cc  mov     r8, rsi
0x1800263cf  inc     r8
0x1800263d2  cmp     [rax+r8*2], r12w
0x1800263d7  jnz     short loc_1800263CF
0x1800263d9  lea     rdx, [rsp+2B8h+var_258]
0x1800263de  mov     rcx, rbx
0x1800263e1  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800263e6  mov     rcx, rbx
0x1800263e9  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x1800263ee  lea     r9, aFileversion; "FileVersion"
0x1800263f5  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x1800263fa  lea     rcx, [rsp+2B8h+pBlock]; this
0x1800263ff  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x180026404  lea     rax, [rsp+2B8h+var_258]
0x180026409  mov     r8, rsi
0x18002640c  inc     r8
0x18002640f  cmp     [rax+r8*2], r12w
0x180026414  jnz     short loc_18002640C
0x180026416  lea     rdx, [rsp+2B8h+var_258]
0x18002641b  mov     rcx, rbx
0x18002641e  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180026423  mov     rcx, rbx
0x180026426  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18002642b  mov     [rsp+2B8h+lpBuffer], r12
0x180026430  mov     rdi, [rsp+2B8h+pBlock]
0x180026435  test    rdi, rdi
0x180026438  jnz     short loc_180026441
0x18002643a  mov     ebx, 8000FFFFh
0x18002643f  jmp     short loc_180026474
0x180026441  mov     [rsp+2B8h+puLen], r12d
0x180026446  lea     r9, [rsp+2B8h+puLen]; puLen
0x18002644b  lea     r8, [rsp+2B8h+lpBuffer]; lplpBuffer
0x180026450  lea     rdx, StringValue; "\\"
0x180026457  mov     rcx, rdi; pBlock
0x18002645a  call    cs:__imp_VerQueryValueW
0x180026460  test    eax, eax
0x180026462  jnz     short loc_180026483
0x180026464  mov     [rsp+2B8h+lpBuffer], r12
0x180026469  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002646e  mov     ebx, eax
0x180026470  test    eax, eax
0x180026472  jns     short loc_18002648A
0x180026474  mov     rcx, rdi; void *
0x180026477  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002647c  mov     eax, ebx
0x18002647e  jmp     loc_180026686
0x180026483  cmp     [rsp+2B8h+puLen], 0Ch
0x180026488  jnb     short loc_18002649C
0x18002648a  mov     rcx, rdi; void *
0x18002648d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026492  mov     eax, 8000FFFFh
0x180026497  jmp     loc_180026686
0x18002649c  mov     rdx, [rsp+2B8h+lpBuffer]
0x1800264a1  movzx   eax, word ptr [rdx+0Ch]
0x1800264a5  movzx   ecx, word ptr [rdx+0Eh]
0x1800264a9  movzx   r9d, word ptr [rdx+8]
0x1800264ae  movzx   r8d, word ptr [rdx+0Ah]
0x1800264b3  mov     [rsp+2B8h+var_290], eax
0x1800264b7  mov     [rsp+2B8h+var_298], ecx
0x1800264bb  lea     rdx, aUUUU; "%u.%u.%u.%u"
0x1800264c2  mov     rcx, rbx
0x1800264c5  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800264ca  mov     rcx, rbx
0x1800264cd  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x1800264d2  movzx   r8d, [rsp+2B8h+var_278]
0x1800264d8  lea     rdx, aU; "%u"
0x1800264df  mov     rcx, rbx
0x1800264e2  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800264e7  mov     rcx, rbx
0x1800264ea  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x1800264ef  lea     r9, aProductname; "ProductName"
0x1800264f6  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x1800264fb  lea     rcx, [rsp+2B8h+pBlock]; this
0x180026500  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x180026505  lea     rax, [rsp+2B8h+var_258]
0x18002650a  mov     r8, rsi
0x18002650d  inc     r8
0x180026510  cmp     [rax+r8*2], r12w
0x180026515  jnz     short loc_18002650D
0x180026517  lea     rdx, [rsp+2B8h+var_258]
0x18002651c  mov     rcx, rbx
0x18002651f  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180026524  mov     rcx, rbx
0x180026527  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18002652c  lea     r9, aCompanyname; "CompanyName"
0x180026533  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x180026538  lea     rcx, [rsp+2B8h+pBlock]; this
0x18002653d  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x180026542  lea     rax, [rsp+2B8h+var_258]
0x180026547  mov     r8, rsi
0x18002654a  inc     r8
0x18002654d  cmp     [rax+r8*2], r12w
0x180026552  jnz     short loc_18002654A
0x180026554  lea     rdx, [rsp+2B8h+var_258]
0x180026559  mov     rcx, rbx
0x18002655c  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180026561  mov     rcx, rbx
0x180026564  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x180026569  lea     r9, aProductversion; "ProductVersion"
0x180026570  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x180026575  lea     rcx, [rsp+2B8h+pBlock]; this
0x18002657a  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x18002657f  lea     rax, [rsp+2B8h+var_258]
0x180026584  mov     r8, rsi
0x180026587  inc     r8
0x18002658a  cmp     [rax+r8*2], r12w
0x18002658f  jnz     short loc_180026587
0x180026591  lea     rdx, [rsp+2B8h+var_258]
0x180026596  mov     rcx, rbx
0x180026599  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18002659e  mov     rcx, rbx
0x1800265a1  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x1800265a6  mov     qword ptr [rsp+2B8h+puLen], r12
0x1800265ab  lea     rdi, [r14+128h]
0x1800265b2  mov     rcx, rdi; this
0x1800265b5  call    ?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ; Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)
0x1800265ba  test    al, al
0x1800265bc  jz      short loc_1800265D6
0x1800265be  lea     r8, [rsp+2B8h+puLen]
0x1800265c3  mov     edx, 1
0x1800265c8  mov     rcx, r15
0x1800265cb  mov     rax, [rdi+10h]
0x1800265cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265d4  jmp     short loc_1800265E0
0x1800265d6  mov     ecx, 7Fh; unsigned int
0x1800265db  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800265e0  test    eax, eax
0x1800265e2  jns     short loc_1800265EE
0x1800265e4  mov     rax, r12
0x1800265e7  mov     qword ptr [rsp+2B8h+puLen], rax
0x1800265ec  jmp     short loc_1800265F3
0x1800265ee  mov     rax, qword ptr [rsp+2B8h+puLen]
0x1800265f3  test    rax, rax
0x1800265f6  jz      short loc_180026615
0x1800265f8  mov     rdx, [rax]
0x1800265fb  test    rdx, rdx
0x1800265fe  jz      short loc_180026615
0x180026600  mov     r8, rsi
0x180026603  inc     r8
0x180026606  cmp     [rdx+r8*2], r12w
0x18002660b  jnz     short loc_180026603
0x18002660d  mov     rcx, rbx
0x180026610  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180026615  mov     rcx, rbx
0x180026618  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18002661d  mov     rdx, qword ptr [rsp+2B8h+puLen]
0x180026622  test    rdx, rdx
0x180026625  jz      short loc_180026645
0x180026627  mov     rdx, [rdx+8]
0x18002662b  test    rdx, rdx
0x18002662e  jz      short loc_180026645
0x180026630  inc     rsi
0x180026633  cmp     [rdx+rsi*2], r12w
0x180026638  jnz     short loc_180026630
0x18002663a  mov     r8d, esi
0x18002663d  mov     rcx, rbx
0x180026640  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180026645  mov     rcx, rbx
0x180026648  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18002664d  mov     rbx, qword ptr [rsp+2B8h+puLen]
0x180026652  test    rbx, rbx
0x180026655  jz      short loc_180026674
0x180026657  mov     rcx, rdi; this
0x18002665a  call    ?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ; Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)
0x18002665f  test    al, al
0x180026661  jz      short loc_18002666F
0x180026663  mov     rcx, rbx
0x180026666  mov     rax, [rdi+18h]
0x18002666a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002666f  mov     qword ptr [rsp+2B8h+puLen], r12
0x180026674  mov     rcx, [rsp+2B8h+pBlock]; void *
0x180026679  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002667e  xor     eax, eax
0x180026680  jmp     short loc_180026686
0x180026682  mov     eax, [rsp+2B8h+puLen]
0x180026686  mov     rcx, [rsp+2B8h+var_48]
0x18002668e  xor     rcx, rsp; StackCookie
0x180026691  call    __security_check_cookie
0x180026696  add     rsp, 288h
0x18002669d  pop     r15
0x18002669f  pop     r14
0x1800266a1  pop     r12
0x1800266a3  pop     rdi
0x1800266a4  pop     rsi
0x1800266a5  pop     rbx
0x1800266a6  retn
```
