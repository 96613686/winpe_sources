# CClassContainer::Cleanup(_FILETIME *)

- ea: `0x180020180`
- end: `0x180020429`
- name: `?Cleanup@CClassContainer@@UEAAJPEAU_FILETIME@@@Z`
- size: `681`
- prototype: `__int64 __fastcall(CClassContainer *this, struct _FILETIME *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x1800016d0`
- `0x180008f58`
- `0x18001b1a0`
- `0x180020180`
- `0x1800205f4`
- `0x1800234b0`
- `0x180024458`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800201ee`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800201ee`
- `adsldpc!ADSIExecuteSearch` at `0x1800202b6`
- `adsldpc!ADSIExecuteSearch` at `0x1800202b6`
- `adsldpc!ADSIGetNextRow` at `0x1800203d4`
- `adsldpc!ADSIGetNextRow` at `0x1800203d4`
- `adsldpc!ADSICloseSearchHandle` at `0x1800203f5`
- `adsldpc!ADSICloseSearchHandle` at `0x1800203f5`
- `adsldpc!ADSIGetFirstRow` at `0x1800202c8`
- `adsldpc!ADSIGetFirstRow` at `0x1800202c8`
- `adsldpc!ADSIFreeColumn` at `0x180020330`
- `adsldpc!ADSIFreeColumn` at `0x1800203be`
- `adsldpc!ADSIFreeColumn` at `0x180020330`
- `adsldpc!ADSIFreeColumn` at `0x1800203be`

## string_xrefs

- `0x180020235`: `lastUpdateSequence`
- `0x180020354`: `ADsPath`

## pseudocode

```c
__int64 __fastcall CClassContainer::Cleanup(CClassContainer *this, struct _FILETIME *a2)
{
  int v4; // ebx
  int i; // eax
  ADS_BOOLEAN v6; // r14d
  const unsigned __int16 *DNString; // rsi
  int v8; // eax
  const unsigned __int16 *v9; // rdx
  struct ads_search_column *v10; // [rsp+20h] [rbp-E0h]
  struct ads_search_column *v11; // [rsp+20h] [rbp-E0h]
  __int64 v12; // [rsp+28h] [rbp-D8h]
  __int64 v13; // [rsp+30h] [rbp-D0h]
  __int64 v14; // [rsp+38h] [rbp-C8h]
  void *v15; // [rsp+50h] [rbp-B0h] BYREF
  struct ads_search_column v16; // [rsp+58h] [rbp-A8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v18[264]; // [rsp+90h] [rbp-70h] BYREF

  v15 = 0;
  SystemTime = 0;
  memset(&v16, 0, sizeof(v16));
  if ( !a2 )
    return 2147942487LL;
  FileTimeToSystemTime(a2, &SystemTime);
  v4 = StringCchPrintfW(
         v18,
         0x104u,
         L"(%s<=%04d%02d%02d%02d%02d%02d)",
         L"lastUpdateSequence",
         SystemTime.wYear,
         SystemTime.wMonth,
         SystemTime.wDay,
         SystemTime.wHour,
         SystemTime.wMinute,
         SystemTime.wSecond);
  if ( v4 >= 0 )
  {
    if ( gDebug )
    {
      LODWORD(v14) = SystemTime.wSecond;
      LODWORD(v13) = SystemTime.wMinute;
      LODWORD(v12) = SystemTime.wHour;
      LODWORD(v10) = SystemTime.wYear;
      _DebugMsg(4, 0xC81u, SystemTime.wMonth, SystemTime.wDay, v10, v12, v13, v14);
    }
    ADSIExecuteSearch(*((_QWORD *)this + 70), v18, &pszDeleteAttrNames, 2, &v15);
    for ( i = ADSIGetFirstRow(*((_QWORD *)this + 70), v15); ; i = ADSIGetNextRow(*((_QWORD *)this + 70), v15) )
    {
      v4 = i;
      if ( i < 0 || i == 20498 )
        break;
      if ( (int)DSGetAndValidateColumn(*((void **)this + 70), v15, ADSTYPE_INTEGER, L"packageFlags", &v16) >= 0 )
      {
        v6 = v16.dwNumValues ? v16.pADsValues->Boolean : 0;
        ADSIFreeColumn(*((_QWORD *)this + 70), &v16);
        if ( (v6 & 0x180) != 0
          && (int)DSGetAndValidateColumn(*((void **)this + 70), v15, ADSTYPE_CASE_IGNORE_STRING, L"ADsPath", &v16) >= 0 )
        {
          if ( v16.dwNumValues )
            DNString = v16.pADsValues->DNString;
          else
            DNString = 0;
          v8 = CClassContainer::DeletePackage(this, DNString);
          v4 = v8;
          if ( gDebug )
          {
            LODWORD(v11) = v8;
            _DebugMsg(2, 0xC82u, DNString, v6, v11);
          }
          ADSIFreeColumn(*((_QWORD *)this + 70), &v16);
          if ( v4 < 0 )
            break;
        }
      }
    }
  }
  v9 = (const unsigned __int16 *)v15;
  if ( v15 )
    ADSICloseSearchHandle(*((_QWORD *)this + 70));
  return RemapErrorCode(v4, v9);
}

```

## disassembly

```asm
0x180020180  mov     [rsp-8+arg_10], rbx
0x180020185  mov     [rsp-8+arg_18], rsi
0x18002018a  push    rbp
0x18002018b  push    rdi
0x18002018c  push    r14
0x18002018e  lea     rbp, [rsp-1B0h]
0x180020196  sub     rsp, 2B0h
0x18002019d  mov     rax, cs:__security_cookie
0x1800201a4  xor     rax, rsp
0x1800201a7  mov     [rbp+1C0h+var_20], rax
0x1800201ae  xorps   xmm1, xmm1
0x1800201b1  mov     [rsp+2C0h+var_270], 0
0x1800201ba  mov     rdi, rcx
0x1800201bd  xorps   xmm0, xmm0
0x1800201c0  xor     ecx, ecx
0x1800201c2  mov     rax, rdx
0x1800201c5  mov     [rsp+2C0h+var_268.hReserved], rcx
0x1800201ca  movups  xmmword ptr [rbp+1C0h+SystemTime.wYear], xmm0
0x1800201ce  movups  xmmword ptr [rsp+2C0h+var_268.pszAttrName], xmm1
0x1800201d3  movups  xmmword ptr [rsp+2C0h+var_268.pADsValues], xmm1
0x1800201d8  test    rdx, rdx
0x1800201db  jnz     short loc_1800201E7
0x1800201dd  mov     eax, 80070057h
0x1800201e2  jmp     loc_180020402
0x1800201e7  lea     rdx, [rbp+1C0h+SystemTime]; lpSystemTime
0x1800201eb  mov     rcx, rax; lpFileTime
0x1800201ee  call    cs:__imp_FileTimeToSystemTime
0x1800201f4  movzx   ecx, [rbp+1C0h+SystemTime.wMinute]
0x1800201f8  movzx   edx, [rbp+1C0h+SystemTime.wHour]
0x1800201fc  movzx   r8d, [rbp+1C0h+SystemTime.wDay]
0x180020201  movzx   r9d, [rbp+1C0h+SystemTime.wMonth]
0x180020206  movzx   eax, [rbp+1C0h+SystemTime.wSecond]
0x18002020a  movzx   r10d, [rbp+1C0h+SystemTime.wYear]
0x18002020f  mov     [rsp+2C0h+var_278], eax
0x180020213  mov     [rsp+2C0h+var_280], ecx
0x180020217  lea     rcx, [rbp+1C0h+var_230]; unsigned __int16 *
0x18002021b  mov     dword ptr [rsp+2C0h+var_288], edx
0x18002021f  mov     edx, 104h; unsigned __int64
0x180020224  mov     dword ptr [rsp+2C0h+var_290], r8d
0x180020229  lea     r8, aS04d02d02d02d0_0; "(%s<=%04d%02d%02d%02d%02d%02d)"
0x180020230  mov     dword ptr [rsp+2C0h+var_298], r9d
0x180020235  lea     r9, aLastupdatesequ; "lastUpdateSequence"
0x18002023c  mov     dword ptr [rsp+2C0h+var_2A0], r10d
0x180020241  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020246  mov     ebx, eax
0x180020248  test    eax, eax
0x18002024a  js      loc_1800203E4
0x180020250  cmp     cs:?gDebug@@3KA, 0; ulong gDebug
0x180020257  jz      short loc_180020294
0x180020259  movzx   ecx, [rbp+1C0h+SystemTime.wMinute]
0x18002025d  movzx   edx, [rbp+1C0h+SystemTime.wHour]
0x180020261  movzx   eax, [rbp+1C0h+SystemTime.wSecond]
0x180020265  movzx   r10d, [rbp+1C0h+SystemTime.wYear]
0x18002026a  movzx   r9d, [rbp+1C0h+SystemTime.wDay]
0x18002026f  movzx   r8d, [rbp+1C0h+SystemTime.wMonth]
0x180020274  mov     dword ptr [rsp+2C0h+var_288], eax
0x180020278  mov     dword ptr [rsp+2C0h+var_290], ecx
0x18002027c  mov     ecx, 4; unsigned int
0x180020281  mov     dword ptr [rsp+2C0h+var_298], edx
0x180020285  mov     edx, 0C81h; unsigned int
0x18002028a  mov     dword ptr [rsp+2C0h+var_2A0], r10d
0x18002028f  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180020294  mov     rcx, [rdi+230h]
0x18002029b  lea     rax, [rsp+2C0h+var_270]
0x1800202a0  mov     r9d, 2
0x1800202a6  mov     [rsp+2C0h+var_2A0], rax
0x1800202ab  lea     r8, ?pszDeleteAttrNames@@3PAPEAGA; ushort * near * pszDeleteAttrNames
0x1800202b2  lea     rdx, [rbp+1C0h+var_230]
0x1800202b6  call    cs:__imp_ADSIExecuteSearch
0x1800202bc  mov     rdx, [rsp+2C0h+var_270]
0x1800202c1  mov     rcx, [rdi+230h]
0x1800202c8  call    cs:__imp_ADSIGetFirstRow
0x1800202ce  jmp     loc_1800203DA
0x1800202d3  cmp     ebx, 5012h
0x1800202d9  jz      loc_1800203E4
0x1800202df  mov     rdx, [rsp+2C0h+var_270]; void *
0x1800202e4  lea     rax, [rsp+2C0h+var_268]
0x1800202e9  mov     rcx, [rdi+230h]; void *
0x1800202f0  lea     r9, aPackageflags; "packageFlags"
0x1800202f7  mov     r8d, 7; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x1800202fd  mov     [rsp+2C0h+var_2A0], rax; struct ads_search_column *
0x180020302  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x180020307  test    eax, eax
0x180020309  js      loc_1800203C8
0x18002030f  cmp     [rsp+2C0h+var_268.dwNumValues], 0
0x180020314  jz      short loc_180020321
0x180020316  mov     rax, [rsp+2C0h+var_268.pADsValues]
0x18002031b  mov     r14d, [rax+8]
0x18002031f  jmp     short loc_180020324
0x180020321  xor     r14d, r14d
0x180020324  mov     rcx, [rdi+230h]
0x18002032b  lea     rdx, [rsp+2C0h+var_268]
0x180020330  call    cs:__imp_ADSIFreeColumn
0x180020336  test    r14d, 180h
0x18002033d  jz      loc_1800203C8
0x180020343  mov     rdx, [rsp+2C0h+var_270]; void *
0x180020348  lea     rax, [rsp+2C0h+var_268]
0x18002034d  mov     rcx, [rdi+230h]; void *
0x180020354  lea     r9, aAdspath; "ADsPath"
0x18002035b  mov     r8d, 3; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x180020361  mov     [rsp+2C0h+var_2A0], rax; struct ads_search_column *
0x180020366  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x18002036b  test    eax, eax
0x18002036d  js      short loc_1800203C8
0x18002036f  cmp     [rsp+2C0h+var_268.dwNumValues], 0
0x180020374  jz      short loc_180020381
0x180020376  mov     rax, [rsp+2C0h+var_268.pADsValues]
0x18002037b  mov     rsi, [rax+8]
0x18002037f  jmp     short loc_180020383
0x180020381  xor     esi, esi
0x180020383  mov     rdx, rsi; unsigned __int16 *
0x180020386  mov     rcx, rdi; this
0x180020389  call    ?DeletePackage@CClassContainer@@QEAAJPEBG@Z; CClassContainer::DeletePackage(ushort const *)
0x18002038e  cmp     cs:?gDebug@@3KA, 0; ulong gDebug
0x180020395  mov     ebx, eax
0x180020397  jz      short loc_1800203B2
0x180020399  mov     r9d, r14d
0x18002039c  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x1800203a0  mov     r8, rsi
0x1800203a3  mov     edx, 0C82h; unsigned int
0x1800203a8  mov     ecx, 2; unsigned int
0x1800203ad  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800203b2  mov     rcx, [rdi+230h]
0x1800203b9  lea     rdx, [rsp+2C0h+var_268]
0x1800203be  call    cs:__imp_ADSIFreeColumn
0x1800203c4  test    ebx, ebx
0x1800203c6  js      short loc_1800203E4
0x1800203c8  mov     rdx, [rsp+2C0h+var_270]
0x1800203cd  mov     rcx, [rdi+230h]
0x1800203d4  call    cs:__imp_ADSIGetNextRow
0x1800203da  mov     ebx, eax
0x1800203dc  test    eax, eax
0x1800203de  jns     loc_1800202D3
0x1800203e4  mov     rdx, [rsp+2C0h+var_270]
0x1800203e9  test    rdx, rdx
0x1800203ec  jz      short loc_1800203FB
0x1800203ee  mov     rcx, [rdi+230h]
0x1800203f5  call    cs:__imp_ADSICloseSearchHandle
0x1800203fb  mov     ecx, ebx; int
0x1800203fd  call    ?RemapErrorCode@@YAJJPEBG@Z; RemapErrorCode(long,ushort const *)
0x180020402  mov     rcx, [rbp+1C0h+var_20]
0x180020409  xor     rcx, rsp; StackCookie
0x18002040c  call    __security_check_cookie
0x180020411  lea     r11, [rsp+2C0h+var_10]
0x180020419  mov     rbx, [r11+30h]
0x18002041d  mov     rsi, [r11+38h]
0x180020421  mov     rsp, r11
0x180020424  pop     r14
0x180020426  pop     rdi
0x180020427  pop     rbp
0x180020428  retn
```
