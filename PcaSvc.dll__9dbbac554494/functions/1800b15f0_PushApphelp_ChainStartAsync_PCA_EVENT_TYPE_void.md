# PushApphelp_ChainStartAsync(_PCA_EVENT_TYPE,void *)

- ea: `0x1800b15f0`
- end: `0x1800b1a5c`
- name: `?PushApphelp_ChainStartAsync@@YAKW4_PCA_EVENT_TYPE@@PEAX@Z`
- size: `1132`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002714`
- `0x180008e14`
- `0x18000b6f0`
- `0x18000c73c`
- `0x180012920`
- `0x180013fac`
- `0x18001b320`
- `0x18001e688`
- `0x1800212b0`
- `0x18004290c`
- `0x18007a9cf`
- `0x180092ab8`
- `0x1800b15f0`
- `0x1800b1b24`
- `0x1800b1f44`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800b17dd`
- `msvcrt!wcscpy_s` at `0x1800b1829`
- `msvcrt!wcscpy_s` at `0x1800b191a`
- `msvcrt!wcscpy_s` at `0x1800b17dd`
- `msvcrt!wcscpy_s` at `0x1800b1829`
- `msvcrt!wcscpy_s` at `0x1800b191a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x1800b180b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x1800b1833`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x1800b180b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x1800b1833`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1800b1815`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1800b183d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1800b1815`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1800b183d`

## string_xrefs

- `0x1800b16fd`: `Opt-in by Telecommand`
- `0x1800b16cf`: `Failed to check Telecommand [%d]`
- `0x1800b18b5`: `Failed to cache shortcut scan result [%d]`
- `0x1800b18ed`: `Apphelp already shown,%S`

## pseudocode

```c
__int64 __fastcall PushApphelp_ChainStartAsync(__int64 a1, __int64 a2)
{
  int v3; // r12d
  const unsigned __int16 *v4; // r15
  struct _PCA_CHAIN *v5; // rax
  unsigned int v6; // esi
  unsigned int v7; // eax
  unsigned int v8; // ebx
  const wchar_t **v9; // r8
  unsigned int v10; // r10d
  unsigned int v11; // eax
  const char *v12; // r9
  int v13; // r8d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  unsigned int v18[2]; // [rsp+20h] [rbp-E0h]
  unsigned int v19; // [rsp+20h] [rbp-E0h]
  unsigned int v20[2]; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+60h] [rbp-A0h] BYREF
  ULONGLONG pullResult; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v23; // [rsp+70h] [rbp-90h] BYREF
  char *v24; // [rsp+78h] [rbp-88h] BYREF
  char *v25; // [rsp+80h] [rbp-80h] BYREF
  char *v26; // [rsp+88h] [rbp-78h] BYREF
  char *v27; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v28; // [rsp+98h] [rbp-68h] BYREF
  char v29[8]; // [rsp+A0h] [rbp-60h] BYREF
  ULONGLONG ullMultiplicand; // [rsp+A8h] [rbp-58h]
  __int64 v31; // [rsp+B0h] [rbp-50h]
  ULONGLONG v32; // [rsp+C8h] [rbp-38h]
  wchar_t Destination[260]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v34; // [rsp+2D8h] [rbp+1D8h]
  int v35; // [rsp+2DCh] [rbp+1DCh]
  wchar_t v36[45]; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v37; // [rsp+33Ah] [rbp+23Ah] BYREF
  char v38; // [rsp+394h] [rbp+294h] BYREF
  char v39; // [rsp+59Ch] [rbp+49Ch] BYREF
  char v40; // [rsp+7A4h] [rbp+6A4h] BYREF
  int v41; // [rsp+9ACh] [rbp+8ACh]
  int v42; // [rsp+9B8h] [rbp+8B8h]
  wchar_t v43[266]; // [rsp+9BCh] [rbp+8BCh] BYREF

  v3 = 0;
  v21 = 0;
  memset_0(v36, 0, 0x8E4u);
  memset_0(Destination, 0, 0x210u);
  RtlNameValueArray::RtlNameValueArray((RtlNameValueArray *)v29);
  memset_0(v36, 0, 0x8E4u);
  memset_0(Destination, 0, 0x210u);
  v4 = (const unsigned __int16 *)PcapChainFromHandle(*(_QWORD *)(a2 + 8));
  v5 = PcapChainFromHandle(*(_QWORD *)(a2 + 8));
  if ( !g_PushApphelp )
    goto LABEL_30;
  v6 = *((_DWORD *)v5 + 4);
  v7 = PushApphelpp_Match(&v21, (struct _PUSHAPPHELP_PAYLOAD *)v36, qword_180159428, v4 + 1568, v6);
  v8 = v7;
  if ( v7 )
  {
    v18[0] = v7;
    AslLogCallPrintf(
      1,
      (unsigned int)"PushApphelp_ChainStartAsync",
      647,
      (unsigned int)"Failed to check Telecommand [%d]",
      *(_QWORD *)v18);
    goto LABEL_31;
  }
  if ( !v21 )
  {
LABEL_30:
    v8 = 0;
    goto LABEL_31;
  }
  PcaTracePrintf("PushApphelp", v6, 0, "Opt-in by Telecommand");
  if ( (unsigned int)PcaStoreGetValueEx(Destination, 528, v4 + 18, v4 + 2088, 12) )
  {
    if ( _InterlockedCompareExchange(&dword_18015C334, 1, 0) )
    {
      PcaTracePrintf("PushApphelp", v6, 0, "Skipping,Shortcut scan in progress for another chain");
      v8 = 0;
      goto LABEL_31;
    }
    v3 = 1;
    if ( PcaUtilityNameValueArrayScanShortcuts((struct RtlNameValueArray *)v29, v4 + 18, v4 + 1568, v4 + 544, v19)
      || !v31 )
    {
      wcscpy_s(Destination, 0x104u, v4 + 1568);
      PathStripPathW(Destination);
      PathRemoveExtensionW(Destination);
      PcaTracePrintf("PushApphelp", v6, 0, "File name,%S", v43);
    }
    else
    {
      pullResult = 0;
      if ( ULongLongMult(ullMultiplicand, 0, &pullResult) < 0
        || (v9 = (const wchar_t **)(v32 + pullResult), v32 + pullResult < v32) )
      {
        v9 = 0;
      }
      wcscpy_s(Destination, 0x104u, *v9);
      PcaTracePrintf("PushApphelp", v6, 0, "Shortcut name,%S", v43);
      PathStripPathW(Destination);
      PathRemoveExtensionW(Destination);
    }
  }
  v10 = v34;
  if ( v42 != v35 )
    v10 = 0;
  v34 = v10 + 1;
  v35 = v42;
  v11 = PcaStoreSetValueEx(v4 + 18, v4 + 2088, 12, Destination, 528);
  v8 = v11;
  if ( v11 )
  {
    v12 = "Failed to cache shortcut scan result [%d]";
    v13 = 721;
LABEL_19:
    v20[0] = v11;
    AslLogCallPrintf(1, (unsigned int)"PushApphelp_ChainStartAsync", v13, (_DWORD)v12, *(_QWORD *)v20);
    goto LABEL_28;
  }
  if ( v34 <= 1 )
  {
    wcscpy_s(v43, 0x104u, Destination);
    v11 = PushApphelpp_ShowApphelp(v36);
    v8 = v11;
    if ( v11 )
    {
      v12 = "Failed to show apphelp [%d]";
      v13 = 743;
      goto LABEL_19;
    }
    if ( (unsigned int)dword_180156510 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180156510, 0x800000000000LL) )
    {
      v21 = v41;
      v23 = v43;
      v24 = &v39;
      v25 = &v40;
      v26 = &v38;
      v27 = &v37;
      v28 = v36;
      LODWORD(pullResult) = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v14,
        (unsigned int)byte_18013B291,
        v15,
        v16,
        (__int64)&pullResult,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v21);
    }
  }
  else
  {
    PcaTracePrintf("PushApphelp", v6, 0, "Apphelp already shown,%S", v43);
  }
  v8 = 0;
LABEL_28:
  if ( v3 )
    dword_18015C334 = 0;
LABEL_31:
  RtlStringArray::~RtlStringArray((RtlStringArray *)v29);
  return v8;
}

```

## disassembly

```asm
0x1800b15f0  push    rbp
0x1800b15f2  push    rbx
0x1800b15f3  push    rsi
0x1800b15f4  push    rdi
0x1800b15f5  push    r12
0x1800b15f7  push    r13
0x1800b15f9  push    r14
0x1800b15fb  push    r15
0x1800b15fd  lea     rbp, [rsp-0AE8h]
0x1800b1605  sub     rsp, 0BE8h
0x1800b160c  mov     rax, cs:__security_cookie
0x1800b1613  xor     rax, rsp
0x1800b1616  mov     [rbp+0B20h+var_50], rax
0x1800b161d  mov     rbx, rdx
0x1800b1620  xor     r12d, r12d
0x1800b1623  mov     [rsp+0C20h+var_BC0], r12d
0x1800b1628  mov     edi, 8E4h
0x1800b162d  mov     r8d, edi; Size
0x1800b1630  xor     edx, edx; Val
0x1800b1632  lea     rcx, [rbp+0B20h+var_940]; void *
0x1800b1639  call    memset_0
0x1800b163e  mov     esi, 210h
0x1800b1643  mov     r8d, esi; Size
0x1800b1646  xor     edx, edx; Val
0x1800b1648  lea     rcx, [rbp+0B20h+Destination]; void *
0x1800b164c  call    memset_0
0x1800b1651  lea     rcx, [rbp+0B20h+var_B80]; this
0x1800b1655  call    ??0RtlNameValueArray@@QEAA@XZ; RtlNameValueArray::RtlNameValueArray(void)
0x1800b165a  nop
0x1800b165b  mov     r8d, edi; Size
0x1800b165e  xor     edx, edx; Val
0x1800b1660  lea     rcx, [rbp+0B20h+var_940]; void *
0x1800b1667  call    memset_0
0x1800b166c  mov     r8d, esi; Size
0x1800b166f  xor     edx, edx; Val
0x1800b1671  lea     rcx, [rbp+0B20h+Destination]; void *
0x1800b1675  call    memset_0
0x1800b167a  mov     rcx, [rbx+8]; unsigned __int64
0x1800b167e  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800b1683  mov     r15, rax
0x1800b1686  mov     rcx, [rbx+8]; unsigned __int64
0x1800b168a  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800b168f  cmp     cs:?g_PushApphelp@@3U_PUSHAPPHELP_GLOBALS@@A, r12d; _PUSHAPPHELP_GLOBALS g_PushApphelp
0x1800b1696  jz      loc_1800B1A2B
0x1800b169c  mov     esi, [rax+10h]
0x1800b169f  lea     r14, [r15+0C40h]
0x1800b16a6  mov     [rsp+0C20h+var_C00], esi; unsigned int
0x1800b16aa  mov     r9, r14; unsigned __int16 *
0x1800b16ad  mov     r8, cs:qword_180159428; struct ITelecommandCache *
0x1800b16b4  lea     rdx, [rbp+0B20h+var_940]; struct _PUSHAPPHELP_PAYLOAD *
0x1800b16bb  lea     rcx, [rsp+0C20h+var_BC0]; int *
0x1800b16c0  call    ?PushApphelpp_Match@@YAKPEAHPEAU_PUSHAPPHELP_PAYLOAD@@PEAVITelecommandCache@@PEBGI@Z; PushApphelpp_Match(int *,_PUSHAPPHELP_PAYLOAD *,ITelecommandCache *,ushort const *,uint)
0x1800b16c5  mov     ebx, eax
0x1800b16c7  test    eax, eax
0x1800b16c9  jz      short loc_1800B16F2
0x1800b16cb  mov     [rsp+0C20h+var_C00], eax
0x1800b16cf  lea     r9, aFailedToCheckT_0; "Failed to check Telecommand [%d]"
0x1800b16d6  mov     r8d, 287h
0x1800b16dc  lea     rdx, aPushapphelpCha; "PushApphelp_ChainStartAsync"
0x1800b16e3  lea     ecx, [r12+1]
0x1800b16e8  call    AslLogCallPrintf
0x1800b16ed  jmp     loc_1800B1A2E
0x1800b16f2  cmp     [rsp+0C20h+var_BC0], r12d
0x1800b16f7  jz      loc_1800B1A2B
0x1800b16fd  lea     r9, aOptInByTelecom; "Opt-in by Telecommand"
0x1800b1704  xor     r8d, r8d; unsigned int
0x1800b1707  mov     edx, esi; unsigned int
0x1800b1709  lea     rcx, aPushapphelp; "PushApphelp"
0x1800b1710  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800b1715  lea     r13, [r15+1050h]
0x1800b171c  lea     rbx, [r15+24h]
0x1800b1720  mov     [rsp+0C20h+var_C00], 0Ch; unsigned int
0x1800b1728  mov     r9, r13
0x1800b172b  mov     r8, rbx
0x1800b172e  mov     edx, 210h
0x1800b1733  lea     rcx, [rbp+0B20h+Destination]
0x1800b1737  call    ?PcaStoreGetValueEx@@YAKPEAX_KPEBG2W4_PCA_SLOT_ID@@@Z; PcaStoreGetValueEx(void *,unsigned __int64,ushort const *,ushort const *,_PCA_SLOT_ID)
0x1800b173c  mov     edi, 1
0x1800b1741  test    eax, eax
0x1800b1743  jz      loc_1800B1867
0x1800b1749  xor     eax, eax
0x1800b174b  lock cmpxchg cs:dword_18015C334, edi
0x1800b1753  jz      short loc_1800B1774
0x1800b1755  lea     r9, aSkippingShortc; "Skipping,Shortcut scan in progress for "...
0x1800b175c  xor     r8d, r8d; unsigned int
0x1800b175f  mov     edx, esi; unsigned int
0x1800b1761  lea     rcx, aPushapphelp; "PushApphelp"
0x1800b1768  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800b176d  xor     ebx, ebx
0x1800b176f  jmp     loc_1800B1A2E
0x1800b1774  mov     r12d, edi
0x1800b1777  lea     r9, [r15+440h]; unsigned __int16 *
0x1800b177e  mov     r8, r14; unsigned __int16 *
0x1800b1781  mov     rdx, rbx; unsigned __int16 *
0x1800b1784  lea     rcx, [rbp+0B20h+var_B80]; struct RtlNameValueArray *
0x1800b1788  call    ?PcaUtilityNameValueArrayScanShortcuts@@YAKAEAVRtlNameValueArray@@PEBG11I@Z; PcaUtilityNameValueArrayScanShortcuts(RtlNameValueArray &,ushort const *,ushort const *,ushort const *,uint)
0x1800b178d  test    eax, eax
0x1800b178f  jnz     loc_1800B181D
0x1800b1795  mov     rax, [rbp+0B20h+var_B70]
0x1800b1799  test    rax, rax
0x1800b179c  jz      short loc_1800B181D
0x1800b179e  xor     r8d, r8d
0x1800b17a1  test    rax, rax
0x1800b17a4  jz      short loc_1800B17D1
0x1800b17a6  mov     [rsp+0C20h+pullResult], r8
0x1800b17ab  lea     r8, [rsp+0C20h+pullResult]; pullResult
0x1800b17b0  xor     edx, edx; ullMultiplier
0x1800b17b2  mov     rcx, [rbp+0B20h+ullMultiplicand]; ullMultiplicand
0x1800b17b6  call    ULongLongMult
0x1800b17bb  test    eax, eax
0x1800b17bd  js      short loc_1800B17CE
0x1800b17bf  mov     r8, [rsp+0C20h+pullResult]
0x1800b17c4  add     r8, [rbp+0B20h+var_B58]
0x1800b17c8  cmp     r8, [rbp+0B20h+var_B58]
0x1800b17cc  jnb     short loc_1800B17D1
0x1800b17ce  xor     r8d, r8d
0x1800b17d1  mov     r8, [r8]; Source
0x1800b17d4  mov     edx, 104h; SizeInWords
0x1800b17d9  lea     rcx, [rbp+0B20h+Destination]; Destination
0x1800b17dd  call    cs:__imp_wcscpy_s
0x1800b17e3  lea     rax, [rbp+0B20h+var_264]
0x1800b17ea  mov     qword ptr [rsp+0C20h+var_C00], rax
0x1800b17ef  lea     r9, aShortcutNameS; "Shortcut name,%S"
0x1800b17f6  xor     r8d, r8d; unsigned int
0x1800b17f9  mov     edx, esi; unsigned int
0x1800b17fb  lea     rcx, aPushapphelp; "PushApphelp"
0x1800b1802  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800b1807  lea     rcx, [rbp+0B20h+Destination]; pszPath
0x1800b180b  call    cs:__imp_PathStripPathW
0x1800b1811  lea     rcx, [rbp+0B20h+Destination]; pszPath
0x1800b1815  call    cs:__imp_PathRemoveExtensionW
0x1800b181b  jmp     short loc_1800B1867
0x1800b181d  mov     r8, r14; Source
0x1800b1820  mov     edx, 104h; SizeInWords
0x1800b1825  lea     rcx, [rbp+0B20h+Destination]; Destination
0x1800b1829  call    cs:__imp_wcscpy_s
0x1800b182f  lea     rcx, [rbp+0B20h+Destination]; pszPath
0x1800b1833  call    cs:__imp_PathStripPathW
0x1800b1839  lea     rcx, [rbp+0B20h+Destination]; pszPath
0x1800b183d  call    cs:__imp_PathRemoveExtensionW
0x1800b1843  lea     rax, [rbp+0B20h+var_264]
0x1800b184a  mov     qword ptr [rsp+0C20h+var_C00], rax
0x1800b184f  lea     r9, aFileNameS; "File name,%S"
0x1800b1856  xor     r8d, r8d; unsigned int
0x1800b1859  mov     edx, esi; unsigned int
0x1800b185b  lea     rcx, aPushapphelp; "PushApphelp"
0x1800b1862  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800b1867  mov     r10d, [rbp+0B20h+var_948]
0x1800b186e  xor     eax, eax
0x1800b1870  mov     r9d, [rbp+0B20h+var_268]
0x1800b1877  cmp     r9d, [rbp+0B20h+var_944]
0x1800b187e  cmovnz  r10d, eax
0x1800b1882  add     r10d, edi
0x1800b1885  mov     [rbp+0B20h+var_948], r10d
0x1800b188c  mov     [rbp+0B20h+var_944], r9d
0x1800b1893  mov     qword ptr [rsp+0C20h+var_C00], 210h
0x1800b189c  lea     r9, [rbp+0B20h+Destination]
0x1800b18a0  lea     r8d, [rax+0Ch]
0x1800b18a4  mov     rdx, r13
0x1800b18a7  mov     rcx, rbx
0x1800b18aa  call    ?PcaStoreSetValueEx@@YAKPEBG0W4_PCA_SLOT_ID@@PEAX_K@Z; PcaStoreSetValueEx(ushort const *,ushort const *,_PCA_SLOT_ID,void *,unsigned __int64)
0x1800b18af  mov     ebx, eax
0x1800b18b1  test    eax, eax
0x1800b18b3  jz      short loc_1800B18D9
0x1800b18b5  lea     r9, aFailedToCacheS; "Failed to cache shortcut scan result [%"...
0x1800b18bc  mov     r8d, 2D1h
0x1800b18c2  mov     [rsp+0C20h+var_C00], eax
0x1800b18c6  lea     rdx, aPushapphelpCha; "PushApphelp_ChainStartAsync"
0x1800b18cd  mov     ecx, edi
0x1800b18cf  call    AslLogCallPrintf
0x1800b18d4  jmp     loc_1800B1A1A
0x1800b18d9  cmp     [rbp+0B20h+var_948], edi
0x1800b18df  jbe     short loc_1800B190A
0x1800b18e1  lea     rax, [rbp+0B20h+var_264]
0x1800b18e8  mov     qword ptr [rsp+0C20h+var_C00], rax
0x1800b18ed  lea     r9, aApphelpAlready; "Apphelp already shown,%S"
0x1800b18f4  xor     r8d, r8d; unsigned int
0x1800b18f7  mov     edx, esi; unsigned int
0x1800b18f9  lea     rcx, aPushapphelp; "PushApphelp"
0x1800b1900  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800b1905  jmp     loc_1800B1A18
0x1800b190a  lea     r8, [rbp+0B20h+Destination]; Source
0x1800b190e  mov     edx, 104h; SizeInWords
0x1800b1913  lea     rcx, [rbp+0B20h+var_264]; Destination
0x1800b191a  call    cs:__imp_wcscpy_s
0x1800b1920  lea     rcx, [rbp+0B20h+var_940]; struct _PUSHAPPHELP_PAYLOAD *
0x1800b1927  call    ?PushApphelpp_ShowApphelp@@YAKPEAU_PUSHAPPHELP_PAYLOAD@@@Z; PushApphelpp_ShowApphelp(_PUSHAPPHELP_PAYLOAD *)
0x1800b192c  mov     ebx, eax
0x1800b192e  test    eax, eax
0x1800b1930  jz      short loc_1800B1941
0x1800b1932  lea     r9, aFailedToShowAp; "Failed to show apphelp [%d]"
0x1800b1939  mov     r8d, 2E7h
0x1800b193f  jmp     short loc_1800B18C2
0x1800b1941  mov     eax, cs:dword_180156510
0x1800b1947  cmp     eax, 5
0x1800b194a  jbe     loc_1800B1A18
0x1800b1950  mov     rdx, 800000000000h
0x1800b195a  lea     rcx, dword_180156510
0x1800b1961  call    _tlgKeywordOn
0x1800b1966  test    al, al
0x1800b1968  jz      loc_1800B1A18
0x1800b196e  mov     eax, [rbp+0B20h+var_274]
0x1800b1974  mov     [rsp+0C20h+var_BC0], eax
0x1800b1978  lea     rax, [rbp+0B20h+var_264]
0x1800b197f  mov     [rsp+0C20h+var_BB0], rax
0x1800b1984  lea     rax, [rbp+0B20h+var_684]
0x1800b198b  mov     [rsp+0C20h+var_BA8], rax
0x1800b1990  lea     rax, [rbp+0B20h+var_47C]
0x1800b1997  mov     [rbp+0B20h+var_BA0], rax
0x1800b199b  lea     rax, [rbp+0B20h+var_88C]
0x1800b19a2  mov     [rbp+0B20h+var_B98], rax
0x1800b19a6  lea     rax, [rbp+0B20h+var_8E6]
0x1800b19ad  mov     [rbp+0B20h+var_B90], rax
0x1800b19b1  lea     rax, [rbp+0B20h+var_940]
0x1800b19b8  mov     [rbp+0B20h+var_B88], rax
0x1800b19bc  mov     dword ptr [rsp+0C20h+pullResult], edi
0x1800b19c0  lea     rax, [rsp+0C20h+var_BC0]
0x1800b19c5  mov     [rsp+0C20h+var_BC8], rax
0x1800b19ca  lea     rax, [rsp+0C20h+var_BB0]
0x1800b19cf  mov     [rsp+0C20h+var_BD0], rax
0x1800b19d4  lea     rax, [rsp+0C20h+var_BA8]
0x1800b19d9  mov     [rsp+0C20h+var_BD8], rax
0x1800b19de  lea     rax, [rbp+0B20h+var_BA0]
0x1800b19e2  mov     [rsp+0C20h+var_BE0], rax
0x1800b19e7  lea     rax, [rbp+0B20h+var_B98]
0x1800b19eb  mov     [rsp+0C20h+var_BE8], rax
0x1800b19f0  lea     rax, [rbp+0B20h+var_B90]
0x1800b19f4  mov     [rsp+0C20h+var_BF0], rax
0x1800b19f9  lea     rax, [rbp+0B20h+var_B88]
0x1800b19fd  mov     [rsp+0C20h+var_BF8], rax
0x1800b1a02  lea     rax, [rsp+0C20h+pullResult]
0x1800b1a07  mov     qword ptr [rsp+0C20h+var_C00], rax
0x1800b1a0c  lea     rdx, byte_18013B291
0x1800b1a13  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@444443@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800b1a18  xor     ebx, ebx
0x1800b1a1a  test    r12d, r12d
0x1800b1a1d  jz      short loc_1800B1A2E
0x1800b1a1f  mov     cs:dword_18015C334, 0
0x1800b1a29  jmp     short loc_1800B1A2E
0x1800b1a2b  mov     ebx, r12d
0x1800b1a2e  lea     rcx, [rbp+0B20h+var_B80]; this
0x1800b1a32  call    ??1RtlStringArray@@QEAA@XZ; RtlStringArray::~RtlStringArray(void)
0x1800b1a37  mov     eax, ebx
0x1800b1a39  mov     rcx, [rbp+0B20h+var_50]
0x1800b1a40  xor     rcx, rsp; StackCookie
0x1800b1a43  call    __security_check_cookie
0x1800b1a48  add     rsp, 0BE8h
0x1800b1a4f  pop     r15
0x1800b1a51  pop     r14
0x1800b1a53  pop     r13
0x1800b1a55  pop     r12
0x1800b1a57  pop     rdi
0x1800b1a58  pop     rsi
0x1800b1a59  pop     rbx
0x1800b1a5a  pop     rbp
0x1800b1a5b  retn
```
