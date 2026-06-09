# WaasMedic::CBinaryHealthPlugin::InitBinaryHealthStatus(void)

- ea: `0x1800415d4`
- end: `0x180041968`
- name: `?InitBinaryHealthStatus@CBinaryHealthPlugin@WaasMedic@@AEAAJXZ`
- size: `916`
- prototype: `__int64 __fastcall(WaasMedic::CBinaryHealthPlugin *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x180040f00`
- `0x1800419d0`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180005ef1`
- `0x18000a5d0`
- `0x18000b308`
- `0x180024fc4`
- `0x1800250e0`
- `0x18002543c`
- `0x180040930`
- `0x1800415d4`
- `0x1800427e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004180f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041927`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004180f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041927`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041801`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041919`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041801`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041919`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004168b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004168b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004167e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004167e`

## string_xrefs

- `0x1800416a3`: `Error in GetSystemDirectory 0x%08X\n`
- `0x1800417e5`: `onecore\enduser\waasmedic\lib\plugins\binaryhealthplugin.cpp`
- `0x180041794`: `Failed to create file path using format string for binary: %ws`
- `0x1800418fc`: `Failed to create file path using format string for binary: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall WaasMedic::CBinaryHealthPlugin::InitBinaryHealthStatus(WaasMedic::CBinaryHealthPlugin *this)
{
  char *v2; // rsi
  char *v3; // r14
  char *v4; // rbx
  char *v5; // rax
  unsigned __int64 v6; // rdx
  unsigned __int16 **v7; // r8
  signed int LastError; // eax
  unsigned int v9; // ebx
  int v11; // r14d
  __int64 v12; // rdi
  _QWORD *v13; // r15
  _QWORD *i; // rbx
  unsigned __int64 v15; // r14
  char *v16; // rbx
  __int64 v17; // rax
  unsigned __int64 v18; // r14
  unsigned __int16 *v19; // rax
  int v20; // edi
  void *v21; // rbx
  HANDLE v22; // rax
  void *v23; // rbx
  __int64 v24; // r15
  unsigned int j; // edi
  wchar_t **v26; // r8
  _OWORD *v27; // rdx
  __int64 v28; // rax
  unsigned __int64 v29; // r14
  void *v30; // rax
  __int64 v31; // rcx
  HANDLE ProcessHeap; // rax
  const char *v33; // [rsp+28h] [rbp-260h]
  LPVOID lpMem[2]; // [rsp+30h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  v2 = (char *)this + 232;
  v3 = (char *)*((_QWORD *)this + 30);
  v4 = (char *)*((_QWORD *)this + 29);
  if ( v4 != v3 )
    return 0;
  if ( (unsigned __int64)((__int64)(*((_QWORD *)this + 31) - (_QWORD)v4) >> 5) < 0x15 )
  {
    std::vector<WaasMedic::tagBinaryHealthInfo>::_Clear_and_reserve_geometric((char *)this + 232, 21);
    v4 = *(char **)v2;
LABEL_4:
    memmove_0(v4, &off_180097290, 0x2A0u);
    v5 = v4 + 672;
    goto LABEL_5;
  }
  v15 = (v3 - v4) >> 5;
  if ( v15 >= 0x15 )
    goto LABEL_4;
  memmove_0(*((void **)this + 29), &off_180097290, 32 * v15);
  v16 = (char *)*((_QWORD *)v2 + 1);
  memmove_0(v16, &(&off_180097290)[4 * v15], 32 * (21 - v15));
  v5 = &v16[32 * (21 - v15)];
LABEL_5:
  *((_QWORD *)v2 + 1) = v5;
  memset_0(Buffer, 0, 0x20Au);
  if ( GetSystemDirectoryW(Buffer, 0x105u) )
  {
    v11 = 0;
    v12 = -1;
    do
      ++v12;
    while ( Buffer[v12] );
    v13 = (_QWORD *)*((_QWORD *)v2 + 1);
    for ( i = *(_QWORD **)v2; i != v13; i += 4 )
    {
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)(*i + 2 * v17) );
      v18 = (unsigned int)(v12 + v17 + 2);
      v19 = (unsigned __int16 *)WaasMedic::SafeAlloc((WaasMedic *)(2 * v18), v6, (bool)v7);
      i[1] = v19;
      if ( v19 )
      {
        v11 = StringCchPrintfW(v19, v18, L"%ws\\%ws", Buffer, *i);
        if ( v11 < 0 )
          LogLevelW(2u, L"Failed to create file path using format string for binary: %ws", *i);
      }
      else
      {
        v11 = -2147024882;
        LogLevelW(2u, L"Failed to allocate memory for binary: %ws", *i);
      }
    }
    lpMem[0] = 0;
    v20 = WaasMedic::SafeExpandEnvironmentString(
            L"%windir%\\UUS\\%PROCESSOR_ARCHITECTURE%",
            (const unsigned __int16 *)lpMem,
            v7);
    if ( v20 >= 0 )
    {
      v23 = lpMem[0];
      v24 = -1;
      do
        ++v24;
      while ( *((_WORD *)lpMem[0] + v24) );
      for ( j = 0; j < 0x19; ++j )
      {
        v26 = &(&off_180097530)[4 * j];
        v27 = (_OWORD *)*((_QWORD *)v2 + 1);
        if ( v27 == *((_OWORD **)v2 + 2) )
        {
          std::vector<WaasMedic::tagBinaryHealthInfo>::_Emplace_reallocate<WaasMedic::tagBinaryHealthInfo const &>(
            v2,
            v27,
            v26);
        }
        else
        {
          *v27 = *(_OWORD *)v26;
          v27[1] = *((_OWORD *)v26 + 1);
          *((_QWORD *)v2 + 1) += 32LL;
        }
        v28 = -1;
        do
          ++v28;
        while ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 30) - 32LL) + 2 * v28) );
        v29 = (unsigned int)(v24 + v28 + 2);
        v30 = WaasMedic::SafeAlloc((WaasMedic *)(2 * v29), (unsigned __int64)v27, (bool)v26);
        *(_QWORD *)(*((_QWORD *)this + 30) - 24LL) = v30;
        v31 = *((_QWORD *)this + 30);
        if ( v30 )
        {
          v11 = StringCchPrintfW(*(unsigned __int16 **)(v31 - 24), v29, L"%ws\\%ws", v23, *(_QWORD *)(v31 - 32));
          if ( v11 < 0 )
            LogLevelW(
              2u,
              L"Failed to create file path using format string for binary: %s",
              *(_QWORD *)(*((_QWORD *)this + 30) - 32LL));
        }
        else
        {
          v11 = -2147024882;
          LogLevelW(2u, L"Failed to allocate memory for binary: %s", *(_QWORD *)(v31 - 32));
        }
      }
      if ( v23 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v23);
      }
      return (unsigned int)v11;
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xAC,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\binaryhealthplugin.cpp",
        (const char *)(unsigned int)v20,
        (int)"Error in SafeExpandEnvironmentString",
        v33);
      v21 = lpMem[0];
      if ( lpMem[0] )
      {
        v22 = GetProcessHeap();
        HeapFree(v22, 0, v21);
      }
      return (unsigned int)v20;
    }
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    LogLevelW(2u, L"Error in GetSystemDirectory 0x%08X\n", v9);
    return v9;
  }
}

```

## disassembly

```asm
0x1800415d4  mov     [rsp+arg_8], rbx
0x1800415d9  mov     [rsp+arg_10], rsi
0x1800415de  push    rdi
0x1800415df  push    r12
0x1800415e1  push    r13
0x1800415e3  push    r14
0x1800415e5  push    r15
0x1800415e7  sub     rsp, 260h
0x1800415ee  mov     rax, cs:__security_cookie
0x1800415f5  xor     rax, rsp
0x1800415f8  mov     [rsp+288h+var_38], rax
0x180041600  mov     r13, rcx
0x180041603  lea     rsi, [rcx+0E8h]
0x18004160a  mov     r14, [rsi+8]
0x18004160e  mov     rbx, [rsi]
0x180041611  cmp     rbx, r14
0x180041614  jnz     loc_180041932
0x18004161a  mov     rax, [rsi+10h]
0x18004161e  sub     rax, rbx
0x180041621  sar     rax, 5
0x180041625  mov     r15d, 15h
0x18004162b  cmp     rax, r15
0x18004162e  jnb     loc_1800416DD
0x180041634  mov     edx, r15d
0x180041637  mov     rcx, rsi
0x18004163a  call    ?_Clear_and_reserve_geometric@?$vector@UtagBinaryHealthInfo@WaasMedic@@V?$allocator@UtagBinaryHealthInfo@WaasMedic@@@std@@@std@@AEAAX_K@Z; std::vector<WaasMedic::tagBinaryHealthInfo>::_Clear_and_reserve_geometric(unsigned __int64)
0x18004163f  mov     rbx, [rsi]
0x180041642  mov     r8d, 2A0h; Size
0x180041648  lea     rdx, off_180097290; Src
0x18004164f  mov     rcx, rbx; void *
0x180041652  call    memmove_0
0x180041657  lea     rax, [rbx+2A0h]
0x18004165e  mov     [rsi+8], rax
0x180041662  xor     edx, edx; Val
0x180041664  mov     r8d, 20Ah; Size
0x18004166a  lea     rcx, [rsp+288h+Buffer]; void *
0x18004166f  call    memset_0
0x180041674  mov     edx, 105h; uSize
0x180041679  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x18004167e  call    cs:__imp_GetSystemDirectoryW
0x180041684  xor     r12d, r12d
0x180041687  test    eax, eax
0x180041689  jnz     short loc_1800416BB
0x18004168b  call    cs:__imp_GetLastError
0x180041691  mov     ebx, eax
0x180041693  test    eax, eax
0x180041695  jle     short loc_1800416A0
0x180041697  movzx   ebx, ax
0x18004169a  or      ebx, 80070000h
0x1800416a0  mov     r8d, ebx
0x1800416a3  lea     rdx, aErrorInGetsyst; "Error in GetSystemDirectory 0x%08X\n"
0x1800416aa  mov     ecx, 2; unsigned __int8
0x1800416af  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800416b4  mov     eax, ebx
0x1800416b6  jmp     loc_18004193A
0x1800416bb  mov     r14d, r12d
0x1800416be  lea     rax, [rsp+288h+Buffer]
0x1800416c3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800416c7  inc     rdi
0x1800416ca  cmp     [rax+rdi*2], r12w
0x1800416cf  jnz     short loc_1800416C7
0x1800416d1  mov     r15, [rsi+8]
0x1800416d5  mov     rbx, [rsi]
0x1800416d8  jmp     loc_1800417A9
0x1800416dd  sub     r14, rbx
0x1800416e0  sar     r14, 5
0x1800416e4  cmp     r14, r15
0x1800416e7  jnb     loc_180041642
0x1800416ed  mov     rdi, r14
0x1800416f0  shl     rdi, 5
0x1800416f4  mov     r8, rdi; Size
0x1800416f7  lea     r12, off_180097290; "dosvc.dll"
0x1800416fe  mov     rdx, r12; Src
0x180041701  mov     rcx, rbx; void *
0x180041704  call    memmove_0
0x180041709  mov     rbx, [rsi+8]
0x18004170d  sub     r15, r14
0x180041710  shl     r15, 5
0x180041714  lea     rdx, [rdi+r12]; Src
0x180041718  mov     r8, r15; Size
0x18004171b  mov     rcx, rbx; void *
0x18004171e  call    memmove_0
0x180041723  lea     rax, [r15+rbx]
0x180041727  jmp     loc_18004165E
0x18004172c  mov     rcx, [rbx]
0x18004172f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180041733  inc     rax
0x180041736  cmp     [rcx+rax*2], r12w
0x18004173b  jnz     short loc_180041733
0x18004173d  lea     r14, [rax+2]
0x180041741  add     r14, rdi
0x180041744  mov     r14d, r14d
0x180041747  lea     rcx, [r14+r14]; this
0x18004174b  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x180041750  mov     [rbx+8], rax
0x180041754  mov     rcx, [rbx]
0x180041757  test    rax, rax
0x18004175a  jnz     short loc_18004176E
0x18004175c  mov     r14d, 8007000Eh
0x180041762  mov     r8, rcx
0x180041765  lea     rdx, aFailedToAlloca_6; "Failed to allocate memory for binary: %"...
0x18004176c  jmp     short loc_18004179B
0x18004176e  mov     qword ptr [rsp+288h+var_268], rcx
0x180041773  lea     r9, [rsp+288h+Buffer]
0x180041778  lea     r8, aWsWs_0; "%ws\\%ws"
0x18004177f  mov     rdx, r14; unsigned __int64
0x180041782  mov     rcx, rax; unsigned __int16 *
0x180041785  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004178a  mov     r14d, eax
0x18004178d  test    eax, eax
0x18004178f  jns     short loc_1800417A5
0x180041791  mov     r8, [rbx]
0x180041794  lea     rdx, aFailedToCreate_12; "Failed to create file path using format"...
0x18004179b  mov     ecx, 2; unsigned __int8
0x1800417a0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800417a5  add     rbx, 20h ; ' '
0x1800417a9  cmp     rbx, r15
0x1800417ac  jnz     loc_18004172C
0x1800417b2  mov     [rsp+288h+lpMem], r12
0x1800417b7  lea     rdx, [rsp+288h+lpMem]; unsigned __int16 *
0x1800417bc  lea     rcx, aWindirUusProce; "%windir%\\UUS\\%PROCESSOR_ARCHITECTURE%"
0x1800417c3  call    ?SafeExpandEnvironmentString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeExpandEnvironmentString(ushort const *,ushort * *)
0x1800417c8  mov     edi, eax
0x1800417ca  test    eax, eax
0x1800417cc  jns     short loc_18004181C
0x1800417ce  mov     rcx, [rsp+288h]; this
0x1800417d6  lea     rax, aErrorInSafeexp; "Error in SafeExpandEnvironmentString"
0x1800417dd  mov     qword ptr [rsp+288h+var_268], rax; int
0x1800417e2  mov     r9d, edi; char *
0x1800417e5  lea     r8, aOnecoreEnduser_47; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x1800417ec  mov     edx, 0ACh; void *
0x1800417f1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800417f6  nop
0x1800417f7  mov     rbx, [rsp+288h+lpMem]
0x1800417fc  test    rbx, rbx
0x1800417ff  jz      short loc_180041815
0x180041801  call    cs:__imp_GetProcessHeap
0x180041807  mov     rcx, rax; hHeap
0x18004180a  mov     r8, rbx; lpMem
0x18004180d  xor     edx, edx; dwFlags
0x18004180f  call    cs:__imp_HeapFree
0x180041815  mov     eax, edi
0x180041817  jmp     loc_18004193A
0x18004181c  mov     rbx, [rsp+288h+lpMem]
0x180041821  or      r15, 0FFFFFFFFFFFFFFFFh
0x180041825  inc     r15
0x180041828  cmp     [rbx+r15*2], r12w
0x18004182d  jnz     short loc_180041825
0x18004182f  mov     edi, r12d
0x180041832  cmp     edi, 19h
0x180041835  jnb     loc_180041914
0x18004183b  mov     r8d, edi
0x18004183e  shl     r8, 5
0x180041842  lea     rcx, off_180097530; "doclient.dll"
0x180041849  add     r8, rcx
0x18004184c  mov     rdx, [rsi+8]
0x180041850  cmp     rdx, [rsi+10h]
0x180041854  jz      short loc_18004186D
0x180041856  movups  xmm0, xmmword ptr [r8]
0x18004185a  movups  xmmword ptr [rdx], xmm0
0x18004185d  movups  xmm1, xmmword ptr [r8+10h]
0x180041862  movups  xmmword ptr [rdx+10h], xmm1
0x180041866  add     qword ptr [rsi+8], 20h ; ' '
0x18004186b  jmp     short loc_180041875
0x18004186d  mov     rcx, rsi
0x180041870  call    ??$_Emplace_reallocate@AEBUtagBinaryHealthInfo@WaasMedic@@@?$vector@UtagBinaryHealthInfo@WaasMedic@@V?$allocator@UtagBinaryHealthInfo@WaasMedic@@@std@@@std@@AEAAPEAUtagBinaryHealthInfo@WaasMedic@@QEAU23@AEBU23@@Z; std::vector<WaasMedic::tagBinaryHealthInfo>::_Emplace_reallocate<WaasMedic::tagBinaryHealthInfo const &>(WaasMedic::tagBinaryHealthInfo * const,WaasMedic::tagBinaryHealthInfo const &)
0x180041875  mov     rax, [r13+0F0h]
0x18004187c  mov     rcx, [rax-20h]
0x180041880  or      rax, 0FFFFFFFFFFFFFFFFh
0x180041884  inc     rax
0x180041887  cmp     [rcx+rax*2], r12w
0x18004188c  jnz     short loc_180041884
0x18004188e  lea     r14, [rax+2]
0x180041892  add     r14, r15
0x180041895  mov     r14d, r14d
0x180041898  lea     rcx, [r14+r14]; this
0x18004189c  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x1800418a1  mov     rcx, [r13+0F0h]
0x1800418a8  mov     [rcx-18h], rax
0x1800418ac  mov     rcx, [r13+0F0h]
0x1800418b3  test    rax, rax
0x1800418b6  jnz     short loc_1800418CB
0x1800418b8  mov     r14d, 8007000Eh
0x1800418be  mov     r8, [rcx-20h]
0x1800418c2  lea     rdx, aFailedToAlloca_10; "Failed to allocate memory for binary: %"...
0x1800418c9  jmp     short loc_180041903
0x1800418cb  mov     rax, [rcx-20h]
0x1800418cf  mov     qword ptr [rsp+288h+var_268], rax
0x1800418d4  mov     r9, rbx
0x1800418d7  lea     r8, aWsWs_0; "%ws\\%ws"
0x1800418de  mov     rdx, r14; unsigned __int64
0x1800418e1  mov     rcx, [rcx-18h]; unsigned __int16 *
0x1800418e5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800418ea  mov     r14d, eax
0x1800418ed  test    eax, eax
0x1800418ef  jns     short loc_18004190D
0x1800418f1  mov     r8, [r13+0F0h]
0x1800418f8  mov     r8, [r8-20h]
0x1800418fc  lea     rdx, aFailedToCreate_11; "Failed to create file path using format"...
0x180041903  mov     ecx, 2; unsigned __int8
0x180041908  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004190d  inc     edi
0x18004190f  jmp     loc_180041832
0x180041914  test    rbx, rbx
0x180041917  jz      short loc_18004192D
0x180041919  call    cs:__imp_GetProcessHeap
0x18004191f  mov     rcx, rax; hHeap
0x180041922  mov     r8, rbx; lpMem
0x180041925  xor     edx, edx; dwFlags
0x180041927  call    cs:__imp_HeapFree
0x18004192d  mov     eax, r14d
0x180041930  jmp     short loc_18004193A
0x180041932  xor     eax, eax
0x180041934  jmp     short loc_18004193A
0x180041936  mov     eax, dword ptr [rsp+288h+lpMem]
0x18004193a  mov     rcx, [rsp+288h+var_38]
0x180041942  xor     rcx, rsp; StackCookie
0x180041945  call    __security_check_cookie
0x18004194a  lea     r11, [rsp+288h+var_28]
0x180041952  mov     rbx, [r11+38h]
0x180041956  mov     rsi, [r11+40h]
0x18004195a  mov     rsp, r11
0x18004195d  pop     r15
0x18004195f  pop     r14
0x180041961  pop     r13
0x180041963  pop     r12
0x180041965  pop     rdi
0x180041966  retn
```
