# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::AddEtwSessionResultsToPackage(std::vector<ushort const *,std::allocator<ushort const *>> &,ushort const *,DhPackaging::IDhPackage *)

- ea: `0x180020004`
- end: `0x180020335`
- name: `?AddEtwSessionResultsToPackage@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAV?$vector@PEBGV?$allocator@PEBG@std@@@std@@PEBGPEAUIDhPackage@DhPackaging@@@Z`
- size: `817`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001b320`
- `0x18001c3b0`

## callees

- `0x1800023c4`
- `0x180002604`
- `0x18000288c`
- `0x18000a17c`
- `0x18001fa98`
- `0x18001fafc`
- `0x18001fbec`
- `0x180020004`
- `0x18002eaac`
- `0x18003d864`
- `0x180040d8c`
- `0x18004106c`
- `0x180049b04`
- `0x180049b50`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!wcsrchr` at `0x1800200e3`
- `VCRUNTIME140!wcsrchr` at `0x1800200e3`
- `KERNEL32!GetFileAttributesW` at `0x18002009f`
- `KERNEL32!GetFileAttributesW` at `0x18002025b`
- `KERNEL32!GetFileAttributesW` at `0x18002009f`
- `KERNEL32!GetFileAttributesW` at `0x18002025b`
- `KERNEL32!CompareStringOrdinal` at `0x180020123`
- `KERNEL32!CompareStringOrdinal` at `0x180020123`
- `ole32!StringFromGUID2` at `0x180020189`
- `ole32!StringFromGUID2` at `0x1800201dd`
- `ole32!StringFromGUID2` at `0x180020189`
- `ole32!StringFromGUID2` at `0x1800201dd`

## string_xrefs

- `0x18002011a`: `StandardCollector.Service.exe`
- `0x180020288`: `DiagnosticsHub.Resource.SymbolCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::AddEtwSessionResultsToPackage(
        __int64 a1,
        _QWORD *a2,
        unsigned __int16 *a3,
        __int64 a4)
{
  __int64 result; // rax
  struct ATL::IAtlStringMgr *Instance; // rax
  DiagHubCommon *v10; // rbx
  const unsigned __int16 *v11; // rdx
  wchar_t *v12; // rax
  const WCHAR *v13; // rcx
  int v14; // esi
  const unsigned __int16 *v15; // r8
  _QWORD *v16; // rsi
  _QWORD *v17; // r14
  int v18; // edi
  __int64 bIgnoreCase; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *Str[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v23; // [rsp+60h] [rbp-A0h]
  LPCWCH lpString1; // [rsp+70h] [rbp-90h]
  _BYTE v25[24]; // [rsp+78h] [rbp-88h] BYREF
  OLECHAR sz[116]; // [rsp+90h] [rbp-70h] BYREF

  result = Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::GetDirectoryPath(
             *(Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory **)(a1 + 3928),
             &pExceptionObject);
  if ( (int)result < 0 )
  {
    _mm_lfence();
    return result;
  }
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  lpFileName = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                       + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &lpFileName,
    L"%sEP",
    pExceptionObject);
  v10 = (DiagHubCommon *)lpFileName;
  if ( GetFileAttributesW(lpFileName) != -1 )
    DiagHubCommon::DeleteDirectory(v10, v11);
  *(_OWORD *)Str = 0;
  v23 = 0;
  lpString1 = 0;
  if ( (int)DiagHubCommon::ModulePath::GetModulePath(0) >= 0 && (v12 = wcsrchr(Str[0], 0x5Cu)) != 0 )
  {
    *v12 = 0;
    *((wchar_t **)&v23 + 1) = Str[0];
    v13 = v12 + 1;
    lpString1 = v12 + 1;
  }
  else
  {
    v13 = lpString1;
  }
  if ( CompareStringOrdinal(v13, -1, L"StandardCollector.Service.exe", -1, 1) == 2 )
  {
    CodeMarker(25241);
    v14 = anonymous_namespace_::MergeEtlFilesOutOfProc((__int64)a3, a2, (__int64)v10, *(_BYTE *)(a1 + 3937));
    CodeMarker(25242);
    if ( !v14 || *((_QWORD *)_logger + 7) == *((_QWORD *)_logger + 8) )
      goto LABEL_20;
    if ( !StringFromGUID2((const GUID *const)(a1 + 840), sz, 39) )
    {
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v15 = L"%s : Out of Proc Merge failed (HRESULT %#08x)";
  }
  else
  {
    v14 = anonymous_namespace_::MergeEtlFilesInProc(a3);
    if ( !v14 || *((_QWORD *)_logger + 7) == *((_QWORD *)_logger + 8) )
      goto LABEL_20;
    if ( !StringFromGUID2((const GUID *const)(a1 + 840), sz, 39) )
    {
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v15 = L"%s : In Proc Merge failed (HRESULT %#08x)";
  }
  LODWORD(bIgnoreCase) = v14;
  sz[39] = 0;
  sz[78] = 0;
  DiagHubCommon::LogStream::Write(
    (DiagHubCommon::LogStream *)((char *)_logger + 56),
    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
    v15,
    sz,
    bIgnoreCase);
LABEL_20:
  if ( *(_BYTE *)(a1 + 3937) )
  {
    v16 = (_QWORD *)*a2;
    v17 = (_QWORD *)a2[1];
    while ( v16 != v17 )
    {
      v18 = anonymous_namespace_::AddEtlFileToPackage(*v16, a4);
      if ( v18 < 0 )
        goto LABEL_29;
      ++v16;
    }
  }
  v18 = anonymous_namespace_::AddEtlFileToPackage(a3, a4);
  if ( v18 >= 0 )
  {
    if ( GetFileAttributesW((LPCWSTR)v10) == -1
      || (_mm_lfence(),
          v18 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, DiagHubCommon *, const wchar_t *, int, _BYTE *))(*(_QWORD *)a4 + 64LL))(
                  a4,
                  L"DiagnosticsHub.Resource.SymbolCache",
                  v10,
                  L"EmbeddedPdbs",
                  1,
                  v25),
          v18 >= 0) )
    {
      v18 = 0;
    }
  }
LABEL_29:
  std::vector<unsigned short>::~vector<unsigned short>(Str);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 - 3) + 8LL))(*((_QWORD *)v10 - 3));
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180020004  push    rbp
0x180020006  push    rbx
0x180020007  push    rsi
0x180020008  push    rdi
0x180020009  push    r12
0x18002000b  push    r13
0x18002000d  push    r14
0x18002000f  push    r15
0x180020011  lea     rbp, [rsp-88h]
0x180020019  sub     rsp, 188h
0x180020020  mov     rax, cs:__security_cookie
0x180020027  xor     rax, rsp
0x18002002a  mov     [rbp+0C0h+var_48], rax
0x18002002e  mov     r15, r9
0x180020031  mov     r12, r8
0x180020034  mov     r14, rdx
0x180020037  mov     rdi, rcx
0x18002003a  lea     rdx, [rsp+1C0h+pExceptionObject]; unsigned __int16 **
0x18002003f  mov     rcx, [rcx+0F58h]; this
0x180020046  call    ?GetDirectoryPath@SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJPEAPEBG@Z; Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::GetDirectoryPath(ushort const * *)
0x18002004b  xor     r13d, r13d
0x18002004e  test    eax, eax
0x180020050  jns     short loc_18002005A
0x180020052  lfence
0x180020055  jmp     loc_1800202D6
0x18002005a  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18002005f  mov     rcx, rax
0x180020062  test    rax, rax
0x180020065  jz      loc_180020310
0x18002006b  mov     rax, [rax]
0x18002006e  mov     rax, [rax+18h]
0x180020072  call    cs:__guard_dispatch_icall_fptr
0x180020078  add     rax, 18h
0x18002007c  mov     [rsp+1C0h+lpFileName], rax
0x180020081  mov     r8, [rsp+1C0h+pExceptionObject]
0x180020086  lea     rdx, aSep; "%sEP"
0x18002008d  lea     rcx, [rsp+1C0h+lpFileName]
0x180020092  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180020097  mov     rbx, [rsp+1C0h+lpFileName]
0x18002009c  mov     rcx, rbx; lpFileName
0x18002009f  call    cs:__imp_GetFileAttributesW
0x1800200a5  cmp     eax, 0FFFFFFFFh
0x1800200a8  jz      short loc_1800200B2
0x1800200aa  mov     rcx, rbx; this
0x1800200ad  call    ?DeleteDirectory@DiagHubCommon@@YAJPEBG_N@Z; DiagHubCommon::DeleteDirectory(ushort const *,bool)
0x1800200b2  xorps   xmm0, xmm0
0x1800200b5  movdqu  xmmword ptr [rsp+1C0h+Str], xmm0
0x1800200bb  xorps   xmm1, xmm1
0x1800200be  movdqu  [rsp+1C0h+var_160], xmm1
0x1800200c4  mov     [rsp+1C0h+lpString1], r13
0x1800200c9  lea     rdx, [rsp+1C0h+Str]
0x1800200ce  xor     ecx, ecx; hModule
0x1800200d0  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x1800200d5  test    eax, eax
0x1800200d7  js      short loc_180020107
0x1800200d9  mov     edx, 5Ch ; '\'; Ch
0x1800200de  mov     rcx, [rsp+1C0h+Str]; Str
0x1800200e3  call    cs:__imp_wcsrchr
0x1800200e9  test    rax, rax
0x1800200ec  jz      short loc_180020107
0x1800200ee  mov     [rax], r13w
0x1800200f2  mov     rcx, [rsp+1C0h+Str]
0x1800200f7  mov     qword ptr [rsp+1C0h+var_160+8], rcx
0x1800200fc  lea     rcx, [rax+2]
0x180020100  mov     [rsp+1C0h+lpString1], rcx
0x180020105  jmp     short loc_18002010C
0x180020107  mov     rcx, [rsp+1C0h+lpString1]; lpString1
0x18002010c  mov     dword ptr [rsp+1C0h+bIgnoreCase], 1; bIgnoreCase
0x180020114  or      eax, 0FFFFFFFFh
0x180020117  mov     r9d, eax; cchCount2
0x18002011a  lea     r8, aStandardcollec; "StandardCollector.Service.exe"
0x180020121  mov     edx, eax; cchCount1
0x180020123  call    cs:__imp_CompareStringOrdinal
0x180020129  cmp     eax, 2
0x18002012c  jnz     short loc_1800201A0
0x18002012e  mov     ecx, 6299h
0x180020133  call    ?CodeMarker@@YAXW4CodeMarkerEvent@Performance@Internal@Microsoft@@@Z; CodeMarker(Microsoft::Internal::Performance::CodeMarkerEvent)
0x180020138  nop
0x180020139  mov     r9b, [rdi+0F61h]
0x180020140  mov     r8, rbx
0x180020143  mov     rdx, r14
0x180020146  mov     rcx, r12
0x180020149  call    _anonymous_namespace___MergeEtlFilesOutOfProc
0x18002014e  mov     esi, eax
0x180020150  mov     ecx, 629Ah
0x180020155  call    ?CodeMarker@@YAXW4CodeMarkerEvent@Performance@Internal@Microsoft@@@Z; CodeMarker(Microsoft::Internal::Performance::CodeMarkerEvent)
0x18002015a  nop
0x18002015b  test    esi, esi
0x18002015d  jz      loc_18002021B
0x180020163  mov     rdx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18002016a  mov     rcx, [rdx+40h]
0x18002016e  cmp     [rdx+38h], rcx
0x180020172  jz      loc_18002021B
0x180020178  lea     rcx, [rdi+348h]; rguid
0x18002017f  mov     r8d, 27h ; '''; cchMax
0x180020185  lea     rdx, [rbp+0C0h+sz]; lpsz
0x180020189  call    cs:__imp_StringFromGUID2
0x18002018f  test    eax, eax
0x180020191  jz      loc_18002031B
0x180020197  lea     r8, aSOutOfProcMerg; "%s : Out of Proc Merge failed (HRESULT "...
0x18002019e  jmp     short loc_1800201F2
0x1800201a0  mov     r9b, [rdi+0F61h]
0x1800201a7  mov     r8, rbx
0x1800201aa  mov     rdx, r14
0x1800201ad  mov     rcx, r12; unsigned __int16 *
0x1800201b0  call    _anonymous_namespace___MergeEtlFilesInProc
0x1800201b5  mov     esi, eax
0x1800201b7  test    eax, eax
0x1800201b9  jz      short loc_18002021B
0x1800201bb  mov     rdx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800201c2  mov     rcx, [rdx+40h]
0x1800201c6  cmp     [rdx+38h], rcx
0x1800201ca  jz      short loc_18002021B
0x1800201cc  lea     rcx, [rdi+348h]; rguid
0x1800201d3  mov     r8d, 27h ; '''; cchMax
0x1800201d9  lea     rdx, [rbp+0C0h+sz]; lpsz
0x1800201dd  call    cs:__imp_StringFromGUID2
0x1800201e3  test    eax, eax
0x1800201e5  jz      loc_1800202F6
0x1800201eb  lea     r8, aSInProcMergeFa; "%s : In Proc Merge failed (HRESULT %#08"...
0x1800201f2  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800201f9  mov     dword ptr [rsp+1C0h+bIgnoreCase], esi
0x1800201fd  mov     [rbp+0C0h+var_E2], r13w
0x180020202  mov     [rbp+0C0h+var_94], r13w
0x180020207  lea     r9, [rbp+0C0h+sz]
0x18002020b  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180020212  add     rcx, 38h ; '8'; this
0x180020216  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18002021b  cmp     [rdi+0F61h], r13b
0x180020222  jz      short loc_180020247
0x180020224  mov     rsi, [r14]
0x180020227  mov     r14, [r14+8]
0x18002022b  jmp     short loc_180020242
0x18002022d  mov     rdx, r15
0x180020230  mov     rcx, [rsi]
0x180020233  call    _anonymous_namespace___AddEtlFileToPackage
0x180020238  mov     edi, eax
0x18002023a  test    eax, eax
0x18002023c  js      short loc_1800202A5
0x18002023e  add     rsi, 8
0x180020242  cmp     rsi, r14
0x180020245  jnz     short loc_18002022D
0x180020247  mov     rdx, r15
0x18002024a  mov     rcx, r12
0x18002024d  call    _anonymous_namespace___AddEtlFileToPackage
0x180020252  mov     edi, eax
0x180020254  test    eax, eax
0x180020256  js      short loc_1800202A5
0x180020258  mov     rcx, rbx; lpFileName
0x18002025b  call    cs:__imp_GetFileAttributesW
0x180020261  cmp     eax, 0FFFFFFFFh
0x180020264  jz      short loc_1800202A2
0x180020266  lfence
0x180020269  mov     rax, [r15]
0x18002026c  lea     rcx, [rsp+1C0h+var_148]
0x180020271  mov     [rsp+1C0h+var_198], rcx
0x180020276  mov     dword ptr [rsp+1C0h+bIgnoreCase], 1
0x18002027e  lea     r9, aEmbeddedpdbs; "EmbeddedPdbs"
0x180020285  mov     r8, rbx
0x180020288  lea     rdx, aDiagnosticshub_0; "DiagnosticsHub.Resource.SymbolCache"
0x18002028f  mov     rcx, r15
0x180020292  mov     rax, [rax+40h]
0x180020296  call    cs:__guard_dispatch_icall_fptr
0x18002029c  mov     edi, eax
0x18002029e  test    eax, eax
0x1800202a0  js      short loc_1800202A5
0x1800202a2  mov     edi, r13d
0x1800202a5  lea     rcx, [rsp+1C0h+Str]
0x1800202aa  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800202af  nop
0x1800202b0  lea     rdx, [rbx-18h]
0x1800202b4  or      ecx, 0FFFFFFFFh
0x1800202b7  lock xadd [rdx+10h], ecx
0x1800202bc  sub     ecx, 1
0x1800202bf  jg      short loc_1800202D4
0x1800202c1  lfence
0x1800202c4  mov     rcx, [rdx]
0x1800202c7  mov     r8, [rcx]
0x1800202ca  mov     rax, [r8+8]
0x1800202ce  call    cs:__guard_dispatch_icall_fptr
0x1800202d4  mov     eax, edi
0x1800202d6  mov     rcx, [rbp+0C0h+var_48]
0x1800202da  xor     rcx, rsp; StackCookie
0x1800202dd  call    __security_check_cookie
0x1800202e2  add     rsp, 188h
0x1800202e9  pop     r15
0x1800202eb  pop     r14
0x1800202ed  pop     r13
0x1800202ef  pop     r12
0x1800202f1  pop     rdi
0x1800202f2  pop     rsi
0x1800202f3  pop     rbx
0x1800202f4  pop     rbp
0x1800202f5  retn
0x1800202f6  mov     dword ptr [rsp+1C0h+pExceptionObject], 8007000Eh
0x1800202fe  lea     rdx, _TI1J; pThrowInfo
0x180020305  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x18002030a  call    _CxxThrowException_0
0x180020310  mov     ecx, 80004005h; int
0x180020315  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002031b  mov     dword ptr [rsp+1C0h+pExceptionObject], 8007000Eh
0x180020323  lea     rdx, _TI1J; pThrowInfo
0x18002032a  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x18002032f  call    _CxxThrowException_0
```
