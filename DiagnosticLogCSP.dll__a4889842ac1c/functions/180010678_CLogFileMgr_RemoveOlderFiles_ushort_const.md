# CLogFileMgr::RemoveOlderFiles(ushort const *)

- ea: `0x180010678`
- end: `0x180010a57`
- name: `?RemoveOlderFiles@CLogFileMgr@@CAXPEBG@Z`
- size: `991`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010230`

## callees

- `0x180001b60`
- `0x180001b84`
- `0x180001bc8`
- `0x18000262c`
- `0x180002d01`
- `0x180006518`
- `0x18000a600`
- `0x18000fb98`
- `0x18000fca8`
- `0x18000fde8`
- `0x18000fedc`
- `0x180010678`
- `0x180010b08`
- `0x180010d38`
- `0x180010d58`
- `0x180010d94`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800109b5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800109b5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001096f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001096f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800108b5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800108ee`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800108b5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800108ee`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180010a1d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180010a1d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180010739`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180010739`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CLogFileMgr::RemoveOlderFiles(const unsigned __int16 *a1)
{
  int v1; // eax
  void *v2; // rdx
  unsigned int v3; // r8d
  _QWORD *v4; // rax
  char *FirstFileW; // rdi
  unsigned __int64 v6; // r8
  __int64 v7; // r8
  __int128 *p_Src; // rcx
  unsigned __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rsi
  __int128 *v12; // rbx
  _QWORD *v13; // rbx
  FILETIME *v14; // rsi
  _QWORD *v15; // r14
  __int64 *v16; // rbx
  int v17; // r15d
  __int64 *v18; // r12
  unsigned __int64 v19; // rsi
  _QWORD *v20; // rbx
  const WCHAR *v21; // rcx
  void *v22; // rdx
  unsigned int v23; // r8d
  const char *v24; // r9
  __int64 **v25; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  _QWORD *v28; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v29; // [rsp+38h] [rbp-C8h]
  __int64 v30; // [rsp+40h] [rbp-C0h]
  _QWORD **v31; // [rsp+48h] [rbp-B8h]
  FILETIME *v32; // [rsp+50h] [rbp-B0h]
  __int64 *v33; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+6Ch] [rbp-94h]
  char *v36; // [rsp+70h] [rbp-90h]
  __int128 Src; // [rsp+90h] [rbp-70h] BYREF
  __int64 v38; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v39; // [rsp+A8h] [rbp-58h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR FileName[1032]; // [rsp+300h] [rbp+200h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B68h] [rbp+A68h]

  v1 = StringCchPrintfW(FileName, 0x401u, L"%s\\%s_%s*.etl", &CLogFileMgr::s_szCollectorsLogFolder);
  if ( v1 >= 0 )
  {
    v29 = 0;
    v4 = operator new(0x48u);
    *v4 = v4;
    v4[1] = v4;
    v4[2] = v4;
    *((_WORD *)v4 + 12) = 257;
    v28 = v4;
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = (char *)FindFirstFileW(FileName, &FindFileData);
    v36 = FirstFileW;
    if ( FirstFileW != (char *)-1LL )
    {
      do
      {
        if ( FindFileData.cFileName[0] != 46 || FindFileData.cFileName[1] )
        {
          Src = 0;
          v38 = 0;
          v39 = 0;
          v6 = -1;
          do
            ++v6;
          while ( *(&CLogFileMgr::s_szCollectorsLogFolder + v6) );
          std::wstring::_Construct<1,unsigned short const *>((char **)&Src, &CLogFileMgr::s_szCollectorsLogFolder, v6);
          v7 = v38;
          p_Src = &Src;
          if ( v39 == v38 )
          {
            std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
              &Src,
              1);
          }
          else
          {
            ++v38;
            if ( v39 > 7 )
              p_Src = (__int128 *)Src;
            *((_WORD *)p_Src + v7) = StringValue[0];
            *((_WORD *)p_Src + v7 + 1) = 0;
          }
          v9 = -1;
          do
            ++v9;
          while ( FindFileData.cFileName[v9] );
          v10 = v38;
          if ( v9 > v39 - v38 )
          {
            std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
              &Src,
              v9);
          }
          else
          {
            v11 = v9 + v38;
            v38 += v9;
            v12 = &Src;
            if ( v39 > 7 )
              v12 = (__int128 *)Src;
            memmove_0((char *)v12 + 2 * v10, FindFileData.cFileName, 2 * v9);
            *((_WORD *)v12 + v11) = 0;
          }
          v13 = v28;
          v31 = &v28;
          v32 = 0;
          v14 = (FILETIME *)operator new(0x48u);
          v32 = v14;
          std::wstring::wstring((__int64)&v14[4], (__int64)&Src);
          v14[8] = FindFileData.ftLastWriteTime;
          *v14 = (FILETIME)v13;
          v14[1] = (FILETIME)v13;
          v14[2] = (FILETIME)v13;
          LOWORD(v14[3].dwLowDateTime) = 0;
          v15 = v28;
          v16 = (__int64 *)v28[1];
          v17 = 0;
          v30 = 0;
          if ( *((_BYTE *)v16 + 25) )
          {
            v18 = v16;
          }
          else
          {
            do
            {
              v18 = v16;
              if ( CompareFileTime((const FILETIME *)v16 + 8, v14 + 8) == -1 )
              {
                v17 = 0;
                v16 = (__int64 *)v16[2];
              }
              else
              {
                v17 = 1;
                v15 = v16;
                v16 = (__int64 *)*v16;
              }
            }
            while ( !*((_BYTE *)v16 + 25) );
          }
          if ( *((_BYTE *)v15 + 25) || CompareFileTime(v14 + 8, (const FILETIME *)v15 + 8) == -1 )
          {
            if ( v29 == 0x38E38E38E38E38ELL )
              std::_Throw_tree_length_error();
            v32 = 0;
            v33 = v18;
            v34 = v17;
            v35 = v30;
            std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Insert_node(
              &v28,
              (__int64)&v33,
              (__int64)v14);
          }
          else
          {
            std::wstring::~wstring((char **)&v14[4]);
            operator delete(v14);
          }
          std::wstring::~wstring((char **)&Src);
        }
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      if ( v29 >= 4 )
      {
        v19 = v29 - 3;
        v20 = (_QWORD *)*v28;
        while ( v20 != v28 && v19 )
        {
          --v19;
          v21 = (const WCHAR *)(v20 + 4);
          if ( v20[7] > 7u )
            v21 = *(const WCHAR **)v21;
          if ( !DeleteFileW(v21) )
            wil::details::in1diag3::_Log_GetLastError(retaddr, v22, v23, v24);
          v25 = (__int64 **)v20[2];
          if ( *((_BYTE *)v25 + 25) )
          {
            for ( i = v20[1]; !*(_BYTE *)(i + 25) && v20 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
              v20 = (_QWORD *)i;
            v20 = (_QWORD *)i;
          }
          else
          {
            v20 = (_QWORD *)v20[2];
            for ( j = *v25; !*((_BYTE *)j + 25); j = (__int64 *)*j )
              v20 = j;
          }
        }
      }
    }
    if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      FindClose(FirstFileW);
    std::_Tree<std::_Tset_traits<std::tuple<_FILETIME,std::wstring>,FileTimeComparer,std::allocator<std::tuple<_FILETIME,std::wstring>>,0>>::~_Tree<std::_Tset_traits<std::tuple<_FILETIME,std::wstring>,FileTimeComparer,std::allocator<std::tuple<_FILETIME,std::wstring>>,0>>((void **)&v28);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(retaddr, v2, v3, (const char *)(unsigned int)v1, (int)L"DiagnosticLogCSP_Collector");
  }
}

```

## disassembly

```asm
0x180010678  push    rbp
0x18001067a  push    rbx
0x18001067b  push    rsi
0x18001067c  push    rdi
0x18001067d  push    r12
0x18001067f  push    r13
0x180010681  push    r14
0x180010683  push    r15
0x180010685  lea     rbp, [rsp-0A28h]
0x18001068d  sub     rsp, 0B28h
0x180010694  mov     rax, cs:__security_cookie
0x18001069b  xor     rax, rsp
0x18001069e  mov     [rbp+0A60h+var_50], rax
0x1800106a5  mov     [rsp+0B60h+var_B38], rcx
0x1800106aa  lea     rax, aDiagnosticlogc_3; "DiagnosticLogCSP_Collector"
0x1800106b1  mov     [rsp+0B60h+var_B40], rax; int
0x1800106b6  lea     rbx, ?s_szCollectorsLogFolder@CLogFileMgr@@0PAGA; ushort near * CLogFileMgr::s_szCollectorsLogFolder
0x1800106bd  mov     r9, rbx
0x1800106c0  lea     r8, aSSSEtl; "%s\\%s_%s*.etl"
0x1800106c7  mov     edx, 401h; unsigned __int64
0x1800106cc  lea     rcx, [rbp+0A60h+FileName]; unsigned __int16 *
0x1800106d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800106d8  mov     rcx, [rbp+0A68h]; this
0x1800106df  xor     r12d, r12d
0x1800106e2  test    eax, eax
0x1800106e4  jns     short loc_1800106F3
0x1800106e6  mov     r9d, eax; char *
0x1800106e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800106ee  jmp     loc_180010A2E
0x1800106f3  mov     [rsp+0B60h+var_B30], r12
0x1800106f8  mov     [rsp+0B60h+var_B28], r12
0x1800106fd  mov     ecx, 48h ; 'H'; Size
0x180010702  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010707  mov     [rax], rax
0x18001070a  mov     [rax+8], rax
0x18001070e  mov     [rax+10h], rax
0x180010712  mov     word ptr [rax+18h], 101h
0x180010718  mov     [rsp+0B60h+var_B30], rax
0x18001071d  xor     edx, edx; Val
0x18001071f  mov     r8d, 250h; Size
0x180010725  lea     rcx, [rbp+0A60h+FindFileData]; void *
0x180010729  call    memset_0
0x18001072e  lea     rdx, [rbp+0A60h+FindFileData]; lpFindFileData
0x180010732  lea     rcx, [rbp+0A60h+FileName]; lpFileName
0x180010739  call    cs:__imp_FindFirstFileW
0x18001073f  mov     rdi, rax
0x180010742  mov     [rsp+0B60h+var_AF0], rax
0x180010747  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001074b  jz      loc_180010A10
0x180010751  cmp     [rbp+0A60h+FindFileData.cFileName], 2Eh ; '.'
0x180010756  jnz     short loc_180010763
0x180010758  cmp     [rbp+0A60h+FindFileData.cFileName+2], r12w
0x18001075d  jz      loc_180010968
0x180010763  xorps   xmm0, xmm0
0x180010766  movups  [rbp+0A60h+Src], xmm0
0x18001076a  mov     [rbp+0A60h+var_AC0], r12
0x18001076e  mov     [rbp+0A60h+var_AB8], r12
0x180010772  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010776  inc     r8
0x180010779  cmp     [rbx+r8*2], r12w
0x18001077e  jnz     short loc_180010776
0x180010780  mov     rdx, rbx
0x180010783  lea     rcx, [rbp+0A60h+Src]
0x180010787  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001078c  nop
0x18001078d  mov     r8, [rbp+0A60h+var_AC0]
0x180010791  mov     rax, [rbp+0A60h+var_AB8]
0x180010795  sub     rax, r8
0x180010798  lea     rcx, [rbp+0A60h+Src]; Src
0x18001079c  cmp     rax, 1
0x1800107a0  jb      short loc_1800107C6
0x1800107a2  lea     rdx, [r8+1]
0x1800107a6  mov     [rbp+0A60h+var_AC0], rdx
0x1800107aa  cmp     [rbp+0A60h+var_AB8], 7
0x1800107af  cmova   rcx, qword ptr [rbp+0A60h+Src]
0x1800107b4  mov     eax, dword ptr cs:StringValue; "\\"
0x1800107ba  mov     [rcx+r8*2], ax
0x1800107bf  mov     [rcx+rdx*2], r12w
0x1800107c4  jmp     short loc_1800107E0
0x1800107c6  mov     [rsp+0B60h+var_B40], 1; __int64
0x1800107cf  lea     r9, StringValue; "\\"
0x1800107d6  mov     edx, 1
0x1800107db  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x1800107e0  lea     rax, [rbp+0A60h+FindFileData.cFileName]
0x1800107e4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800107e8  inc     rdx
0x1800107eb  cmp     [rax+rdx*2], r12w
0x1800107f0  jnz     short loc_1800107E8
0x1800107f2  mov     rcx, [rbp+0A60h+var_AC0]
0x1800107f6  mov     rax, [rbp+0A60h+var_AB8]
0x1800107fa  sub     rax, rcx
0x1800107fd  cmp     rdx, rax
0x180010800  ja      short loc_180010830
0x180010802  lea     rsi, [rdx+rcx]
0x180010806  mov     [rbp+0A60h+var_AC0], rsi
0x18001080a  lea     rbx, [rbp+0A60h+Src]
0x18001080e  cmp     [rbp+0A60h+var_AB8], 7
0x180010813  cmova   rbx, qword ptr [rbp+0A60h+Src]
0x180010818  lea     r8, [rdx+rdx]; Size
0x18001081c  lea     rcx, [rbx+rcx*2]; void *
0x180010820  lea     rdx, [rbp+0A60h+FindFileData.cFileName]; Src
0x180010824  call    memmove_0
0x180010829  mov     [rbx+rsi*2], r12w
0x18001082e  jmp     short loc_180010842
0x180010830  mov     [rsp+0B60h+var_B40], rdx; __int64
0x180010835  lea     r9, [rbp+0A60h+FindFileData.cFileName]
0x180010839  lea     rcx, [rbp+0A60h+Src]; Src
0x18001083d  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x180010842  mov     rbx, [rsp+0B60h+var_B30]
0x180010847  lea     rax, [rsp+0B60h+var_B30]
0x18001084c  mov     [rsp+0B60h+var_B18], rax
0x180010851  mov     [rsp+0B60h+var_B10], r12
0x180010856  mov     ecx, 48h ; 'H'; Size
0x18001085b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010860  mov     rsi, rax
0x180010863  mov     [rsp+0B60h+var_B10], rax
0x180010868  lea     rdx, [rbp+0A60h+Src]
0x18001086c  lea     rcx, [rax+20h]
0x180010870  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010875  lea     r13, [rsi+40h]
0x180010879  mov     rax, qword ptr [rbp+0A60h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18001087d  mov     [r13+0], rax
0x180010881  mov     [rsi], rbx
0x180010884  mov     [rsi+8], rbx
0x180010888  mov     [rsi+10h], rbx
0x18001088c  mov     word ptr [rsi+18h], 0
0x180010892  mov     r14, [rsp+0B60h+var_B30]
0x180010897  mov     rbx, [r14+8]
0x18001089b  mov     r15d, r12d
0x18001089e  xor     eax, eax
0x1800108a0  mov     [rsp+0B60h+var_B20], rax
0x1800108a5  cmp     [rbx+19h], r12b
0x1800108a9  jnz     short loc_1800108DD
0x1800108ab  mov     r12, rbx
0x1800108ae  lea     rcx, [rbx+40h]; lpFileTime1
0x1800108b2  mov     rdx, r13; lpFileTime2
0x1800108b5  call    cs:__imp_CompareFileTime
0x1800108bb  cmp     eax, 0FFFFFFFFh
0x1800108be  jnz     short loc_1800108C9
0x1800108c0  xor     r15d, r15d
0x1800108c3  mov     rbx, [rbx+10h]
0x1800108c7  jmp     short loc_1800108D5
0x1800108c9  mov     r15d, 1
0x1800108cf  mov     r14, rbx
0x1800108d2  mov     rbx, [rbx]
0x1800108d5  cmp     byte ptr [rbx+19h], 0
0x1800108d9  jz      short loc_1800108AB
0x1800108db  jmp     short loc_1800108E0
0x1800108dd  mov     r12, rbx
0x1800108e0  cmp     byte ptr [r14+19h], 0
0x1800108e5  jnz     short loc_180010911
0x1800108e7  lea     rdx, [r14+40h]; lpFileTime2
0x1800108eb  mov     rcx, r13; lpFileTime1
0x1800108ee  call    cs:__imp_CompareFileTime
0x1800108f4  cmp     eax, 0FFFFFFFFh
0x1800108f7  jz      short loc_180010911
0x1800108f9  lea     rcx, [rsi+20h]
0x1800108fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010902  mov     edx, 48h ; 'H'; unsigned __int64
0x180010907  mov     rcx, rsi; void *
0x18001090a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001090f  jmp     short loc_180010955
0x180010911  mov     rax, 38E38E38E38E38Eh
0x18001091b  cmp     [rsp+0B60h+var_B28], rax
0x180010920  jz      loc_180010A51
0x180010926  mov     [rsp+0B60h+var_B10], 0
0x18001092f  mov     [rsp+0B60h+var_B00], r12
0x180010934  mov     [rsp+0B60h+var_AF8], r15d
0x180010939  mov     rax, [rsp+0B60h+var_B20]
0x18001093e  mov     [rsp+0B60h+var_AF4], eax
0x180010942  mov     r8, rsi
0x180010945  lea     rdx, [rsp+0B60h+var_B00]
0x18001094a  lea     rcx, [rsp+0B60h+var_B30]
0x18001094f  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x180010954  nop
0x180010955  lea     rcx, [rbp+0A60h+Src]
0x180010959  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001095e  xor     r12d, r12d
0x180010961  lea     rbx, ?s_szCollectorsLogFolder@CLogFileMgr@@0PAGA; ushort near * CLogFileMgr::s_szCollectorsLogFolder
0x180010968  lea     rdx, [rbp+0A60h+FindFileData]; lpFindFileData
0x18001096c  mov     rcx, rdi; hFindFile
0x18001096f  call    cs:__imp_FindNextFileW
0x180010975  test    eax, eax
0x180010977  jnz     loc_180010751
0x18001097d  mov     rsi, [rsp+0B60h+var_B28]
0x180010982  cmp     rsi, 4
0x180010986  jb      loc_180010A10
0x18001098c  add     rsi, 0FFFFFFFFFFFFFFFDh
0x180010990  mov     rbx, [rsp+0B60h+var_B30]
0x180010995  mov     rbx, [rbx]
0x180010998  cmp     rbx, [rsp+0B60h+var_B30]
0x18001099d  jz      short loc_180010A10
0x18001099f  test    rsi, rsi
0x1800109a2  jz      short loc_180010A10
0x1800109a4  dec     rsi
0x1800109a7  lea     rcx, [rbx+20h]
0x1800109ab  cmp     qword ptr [rcx+18h], 7
0x1800109b0  jbe     short loc_1800109B5
0x1800109b2  mov     rcx, [rcx]; lpFileName
0x1800109b5  call    cs:__imp_DeleteFileW
0x1800109bb  test    eax, eax
0x1800109bd  jnz     short loc_1800109CB
0x1800109bf  mov     rcx, [rbp+0A68h]; this
0x1800109c6  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800109cb  mov     rcx, [rbx+10h]
0x1800109cf  cmp     [rcx+19h], r12b
0x1800109d3  jz      short loc_1800109F3
0x1800109d5  mov     rax, [rbx+8]
0x1800109d9  jmp     short loc_1800109E8
0x1800109db  cmp     rbx, [rax+10h]
0x1800109df  jnz     short loc_1800109EE
0x1800109e1  mov     rbx, rax
0x1800109e4  mov     rax, [rax+8]
0x1800109e8  cmp     [rax+19h], r12b
0x1800109ec  jz      short loc_1800109DB
0x1800109ee  mov     rbx, rax
0x1800109f1  jmp     short loc_180010998
0x1800109f3  mov     rbx, rcx
0x1800109f6  mov     rcx, [rcx]
0x1800109f9  cmp     [rcx+19h], r12b
0x1800109fd  jnz     short loc_180010998
0x1800109ff  mov     rbx, rcx
0x180010a02  mov     rax, [rcx]
0x180010a05  mov     rcx, rax
0x180010a08  cmp     [rax+19h], r12b
0x180010a0c  jz      short loc_1800109FF
0x180010a0e  jmp     short loc_180010998
0x180010a10  lea     rax, [rdi-1]
0x180010a14  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010a18  ja      short loc_180010A24
0x180010a1a  mov     rcx, rdi; hFindFile
0x180010a1d  call    cs:__imp_FindClose
0x180010a23  nop
0x180010a24  lea     rcx, [rsp+0B60h+var_B30]
0x180010a29  call    ??1?$_Tree@V?$_Tset_traits@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@UFileTimeComparer@@V?$allocator@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::tuple<_FILETIME,std::wstring>,FileTimeComparer,std::allocator<std::tuple<_FILETIME,std::wstring>>,0>>::~_Tree<std::_Tset_traits<std::tuple<_FILETIME,std::wstring>,FileTimeComparer,std::allocator<std::tuple<_FILETIME,std::wstring>>,0>>(void)
0x180010a2e  mov     rcx, [rbp+0A60h+var_50]
0x180010a35  xor     rcx, rsp; StackCookie
0x180010a38  call    __security_check_cookie
0x180010a3d  add     rsp, 0B28h
0x180010a44  pop     r15
0x180010a46  pop     r14
0x180010a48  pop     r13
0x180010a4a  pop     r12
0x180010a4c  pop     rdi
0x180010a4d  pop     rsi
0x180010a4e  pop     rbx
0x180010a4f  pop     rbp
0x180010a50  retn
0x180010a51  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
