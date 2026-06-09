# CLogFileMgr::RemoveOlderFiles(ushort const *)

- ea: `0x180010ed4`
- end: `0x1800112d8`
- name: `?RemoveOlderFiles@CLogFileMgr@@CAXPEBG@Z`
- size: `1028`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010a7c`

## callees

- `0x180001b90`
- `0x180001bb4`
- `0x180001bf8`
- `0x18000265c`
- `0x180002d31`
- `0x180006498`
- `0x18000a924`
- `0x1800103a8`
- `0x1800104b8`
- `0x1800105f8`
- `0x1800106ec`
- `0x180010ed4`
- `0x18001138c`
- `0x1800115bc`
- `0x1800115dc`
- `0x180011618`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180011229`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180011229`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800111dd`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800111dd`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180011117`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180011156`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180011117`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180011156`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180011297`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180011297`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180010f95`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180010f95`

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
  __int64 v6; // r8
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
          std::wstring::_Construct<1,unsigned short const *>(&Src, &CLogFileMgr::s_szCollectorsLogFolder, v6);
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
          std::wstring::wstring(&v14[4], &Src);
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
              &v33,
              v14);
          }
          else
          {
            std::wstring::~wstring(&v14[4]);
            operator delete(v14, 0x48u);
          }
          std::wstring::~wstring(&Src);
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
    std::_Tree<std::_Tset_traits<std::tuple<_FILETIME,std::wstring>,FileTimeComparer,std::allocator<std::tuple<_FILETIME,std::wstring>>,0>>::~_Tree<std::_Tset_traits<std::tuple<_FILETIME,std::wstring>,FileTimeComparer,std::allocator<std::tuple<_FILETIME,std::wstring>>,0>>(&v28);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(retaddr, v2, v3, (const char *)(unsigned int)v1, (int)L"DiagnosticLogCSP_Collector");
  }
}

```

## disassembly

```asm
0x180010ed4  push    rbp
0x180010ed6  push    rbx
0x180010ed7  push    rsi
0x180010ed8  push    rdi
0x180010ed9  push    r12
0x180010edb  push    r13
0x180010edd  push    r14
0x180010edf  push    r15
0x180010ee1  lea     rbp, [rsp-0A28h]
0x180010ee9  sub     rsp, 0B28h
0x180010ef0  mov     rax, cs:__security_cookie
0x180010ef7  xor     rax, rsp
0x180010efa  mov     [rbp+0A60h+var_50], rax
0x180010f01  mov     [rsp+0B60h+var_B38], rcx
0x180010f06  lea     rax, aDiagnosticlogc_3; "DiagnosticLogCSP_Collector"
0x180010f0d  mov     [rsp+0B60h+var_B40], rax; int
0x180010f12  lea     rbx, ?s_szCollectorsLogFolder@CLogFileMgr@@0PAGA; ushort near * CLogFileMgr::s_szCollectorsLogFolder
0x180010f19  mov     r9, rbx
0x180010f1c  lea     r8, aSSSEtl; "%s\\%s_%s*.etl"
0x180010f23  mov     edx, 401h; unsigned __int64
0x180010f28  lea     rcx, [rbp+0A60h+FileName]; unsigned __int16 *
0x180010f2f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010f34  mov     rcx, [rbp+0A68h]; this
0x180010f3b  xor     r12d, r12d
0x180010f3e  test    eax, eax
0x180010f40  jns     short loc_180010F4F
0x180010f42  mov     r9d, eax; char *
0x180010f45  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010f4a  jmp     loc_1800112AE
0x180010f4f  mov     [rsp+0B60h+var_B30], r12
0x180010f54  mov     [rsp+0B60h+var_B28], r12
0x180010f59  mov     ecx, 48h ; 'H'; Size
0x180010f5e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010f63  mov     [rax], rax
0x180010f66  mov     [rax+8], rax
0x180010f6a  mov     [rax+10h], rax
0x180010f6e  mov     word ptr [rax+18h], 101h
0x180010f74  mov     [rsp+0B60h+var_B30], rax
0x180010f79  xor     edx, edx; Val
0x180010f7b  mov     r8d, 250h; Size
0x180010f81  lea     rcx, [rbp+0A60h+FindFileData]; void *
0x180010f85  call    memset_0
0x180010f8a  lea     rdx, [rbp+0A60h+FindFileData]; lpFindFileData
0x180010f8e  lea     rcx, [rbp+0A60h+FileName]; lpFileName
0x180010f95  call    cs:__imp_FindFirstFileW
0x180010f9c  nop     dword ptr [rax+rax+00h]
0x180010fa1  mov     rdi, rax
0x180010fa4  mov     [rsp+0B60h+var_AF0], rax
0x180010fa9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010fad  jz      loc_18001128A
0x180010fb3  cmp     [rbp+0A60h+FindFileData.cFileName], 2Eh ; '.'
0x180010fb8  jnz     short loc_180010FC5
0x180010fba  cmp     [rbp+0A60h+FindFileData.cFileName+2], r12w
0x180010fbf  jz      loc_1800111D6
0x180010fc5  xorps   xmm0, xmm0
0x180010fc8  movups  [rbp+0A60h+Src], xmm0
0x180010fcc  mov     [rbp+0A60h+var_AC0], r12
0x180010fd0  mov     [rbp+0A60h+var_AB8], r12
0x180010fd4  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010fd8  inc     r8
0x180010fdb  cmp     [rbx+r8*2], r12w
0x180010fe0  jnz     short loc_180010FD8
0x180010fe2  mov     rdx, rbx
0x180010fe5  lea     rcx, [rbp+0A60h+Src]
0x180010fe9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180010fee  nop
0x180010fef  mov     r8, [rbp+0A60h+var_AC0]
0x180010ff3  mov     rax, [rbp+0A60h+var_AB8]
0x180010ff7  sub     rax, r8
0x180010ffa  lea     rcx, [rbp+0A60h+Src]; Src
0x180010ffe  cmp     rax, 1
0x180011002  jb      short loc_180011028
0x180011004  lea     rdx, [r8+1]
0x180011008  mov     [rbp+0A60h+var_AC0], rdx
0x18001100c  cmp     [rbp+0A60h+var_AB8], 7
0x180011011  cmova   rcx, qword ptr [rbp+0A60h+Src]
0x180011016  mov     eax, dword ptr cs:StringValue; "\\"
0x18001101c  mov     [rcx+r8*2], ax
0x180011021  mov     [rcx+rdx*2], r12w
0x180011026  jmp     short loc_180011042
0x180011028  mov     [rsp+0B60h+var_B40], 1; __int64
0x180011031  lea     r9, StringValue; "\\"
0x180011038  mov     edx, 1
0x18001103d  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x180011042  lea     rax, [rbp+0A60h+FindFileData.cFileName]
0x180011046  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001104a  inc     rdx
0x18001104d  cmp     [rax+rdx*2], r12w
0x180011052  jnz     short loc_18001104A
0x180011054  mov     rcx, [rbp+0A60h+var_AC0]
0x180011058  mov     rax, [rbp+0A60h+var_AB8]
0x18001105c  sub     rax, rcx
0x18001105f  cmp     rdx, rax
0x180011062  ja      short loc_180011092
0x180011064  lea     rsi, [rdx+rcx]
0x180011068  mov     [rbp+0A60h+var_AC0], rsi
0x18001106c  lea     rbx, [rbp+0A60h+Src]
0x180011070  cmp     [rbp+0A60h+var_AB8], 7
0x180011075  cmova   rbx, qword ptr [rbp+0A60h+Src]
0x18001107a  lea     r8, [rdx+rdx]; Size
0x18001107e  lea     rcx, [rbx+rcx*2]; void *
0x180011082  lea     rdx, [rbp+0A60h+FindFileData.cFileName]; Src
0x180011086  call    memmove_0
0x18001108b  mov     [rbx+rsi*2], r12w
0x180011090  jmp     short loc_1800110A4
0x180011092  mov     [rsp+0B60h+var_B40], rdx; __int64
0x180011097  lea     r9, [rbp+0A60h+FindFileData.cFileName]
0x18001109b  lea     rcx, [rbp+0A60h+Src]; Src
0x18001109f  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x1800110a4  mov     rbx, [rsp+0B60h+var_B30]
0x1800110a9  lea     rax, [rsp+0B60h+var_B30]
0x1800110ae  mov     [rsp+0B60h+var_B18], rax
0x1800110b3  mov     [rsp+0B60h+var_B10], r12
0x1800110b8  mov     ecx, 48h ; 'H'; Size
0x1800110bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800110c2  mov     rsi, rax
0x1800110c5  mov     [rsp+0B60h+var_B10], rax
0x1800110ca  lea     rdx, [rbp+0A60h+Src]
0x1800110ce  lea     rcx, [rax+20h]
0x1800110d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800110d7  lea     r13, [rsi+40h]
0x1800110db  mov     rax, qword ptr [rbp+0A60h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x1800110df  mov     [r13+0], rax
0x1800110e3  mov     [rsi], rbx
0x1800110e6  mov     [rsi+8], rbx
0x1800110ea  mov     [rsi+10h], rbx
0x1800110ee  mov     word ptr [rsi+18h], 0
0x1800110f4  mov     r14, [rsp+0B60h+var_B30]
0x1800110f9  mov     rbx, [r14+8]
0x1800110fd  mov     r15d, r12d
0x180011100  xor     eax, eax
0x180011102  mov     [rsp+0B60h+var_B20], rax
0x180011107  cmp     [rbx+19h], r12b
0x18001110b  jnz     short loc_180011145
0x18001110d  mov     r12, rbx
0x180011110  lea     rcx, [rbx+40h]; lpFileTime1
0x180011114  mov     rdx, r13; lpFileTime2
0x180011117  call    cs:__imp_CompareFileTime
0x18001111e  nop     dword ptr [rax+rax+00h]
0x180011123  cmp     eax, 0FFFFFFFFh
0x180011126  jnz     short loc_180011131
0x180011128  xor     r15d, r15d
0x18001112b  mov     rbx, [rbx+10h]
0x18001112f  jmp     short loc_18001113D
0x180011131  mov     r15d, 1
0x180011137  mov     r14, rbx
0x18001113a  mov     rbx, [rbx]
0x18001113d  cmp     byte ptr [rbx+19h], 0
0x180011141  jz      short loc_18001110D
0x180011143  jmp     short loc_180011148
0x180011145  mov     r12, rbx
0x180011148  cmp     byte ptr [r14+19h], 0
0x18001114d  jnz     short loc_18001117F
0x18001114f  lea     rdx, [r14+40h]; lpFileTime2
0x180011153  mov     rcx, r13; lpFileTime1
0x180011156  call    cs:__imp_CompareFileTime
0x18001115d  nop     dword ptr [rax+rax+00h]
0x180011162  cmp     eax, 0FFFFFFFFh
0x180011165  jz      short loc_18001117F
0x180011167  lea     rcx, [rsi+20h]
0x18001116b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011170  mov     edx, 48h ; 'H'; unsigned __int64
0x180011175  mov     rcx, rsi; void *
0x180011178  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001117d  jmp     short loc_1800111C3
0x18001117f  mov     rax, 38E38E38E38E38Eh
0x180011189  cmp     [rsp+0B60h+var_B28], rax
0x18001118e  jz      loc_1800112D2
0x180011194  mov     [rsp+0B60h+var_B10], 0
0x18001119d  mov     [rsp+0B60h+var_B00], r12
0x1800111a2  mov     [rsp+0B60h+var_AF8], r15d
0x1800111a7  mov     rax, [rsp+0B60h+var_B20]
0x1800111ac  mov     [rsp+0B60h+var_AF4], eax
0x1800111b0  mov     r8, rsi
0x1800111b3  lea     rdx, [rsp+0B60h+var_B00]
0x1800111b8  lea     rcx, [rsp+0B60h+var_B30]
0x1800111bd  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x1800111c2  nop
0x1800111c3  lea     rcx, [rbp+0A60h+Src]
0x1800111c7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800111cc  xor     r12d, r12d
0x1800111cf  lea     rbx, ?s_szCollectorsLogFolder@CLogFileMgr@@0PAGA; ushort near * CLogFileMgr::s_szCollectorsLogFolder
0x1800111d6  lea     rdx, [rbp+0A60h+FindFileData]; lpFindFileData
0x1800111da  mov     rcx, rdi; hFindFile
0x1800111dd  call    cs:__imp_FindNextFileW
0x1800111e4  nop     dword ptr [rax+rax+00h]
0x1800111e9  test    eax, eax
0x1800111eb  jnz     loc_180010FB3
0x1800111f1  mov     rsi, [rsp+0B60h+var_B28]
0x1800111f6  cmp     rsi, 4
0x1800111fa  jb      loc_18001128A
0x180011200  add     rsi, 0FFFFFFFFFFFFFFFDh
0x180011204  mov     rbx, [rsp+0B60h+var_B30]
0x180011209  mov     rbx, [rbx]
0x18001120c  cmp     rbx, [rsp+0B60h+var_B30]
0x180011211  jz      short loc_18001128A
0x180011213  test    rsi, rsi
0x180011216  jz      short loc_18001128A
0x180011218  dec     rsi
0x18001121b  lea     rcx, [rbx+20h]
0x18001121f  cmp     qword ptr [rcx+18h], 7
0x180011224  jbe     short loc_180011229
0x180011226  mov     rcx, [rcx]; lpFileName
0x180011229  call    cs:__imp_DeleteFileW
0x180011230  nop     dword ptr [rax+rax+00h]
0x180011235  test    eax, eax
0x180011237  jnz     short loc_180011245
0x180011239  mov     rcx, [rbp+0A68h]; this
0x180011240  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180011245  mov     rcx, [rbx+10h]
0x180011249  cmp     [rcx+19h], r12b
0x18001124d  jz      short loc_18001126D
0x18001124f  mov     rax, [rbx+8]
0x180011253  jmp     short loc_180011262
0x180011255  cmp     rbx, [rax+10h]
0x180011259  jnz     short loc_180011268
0x18001125b  mov     rbx, rax
0x18001125e  mov     rax, [rax+8]
0x180011262  cmp     [rax+19h], r12b
0x180011266  jz      short loc_180011255
0x180011268  mov     rbx, rax
0x18001126b  jmp     short loc_18001120C
0x18001126d  mov     rbx, rcx
0x180011270  mov     rcx, [rcx]
0x180011273  cmp     [rcx+19h], r12b
0x180011277  jnz     short loc_18001120C
0x180011279  mov     rbx, rcx
0x18001127c  mov     rax, [rcx]
0x18001127f  mov     rcx, rax
0x180011282  cmp     [rax+19h], r12b
0x180011286  jz      short loc_180011279
0x180011288  jmp     short loc_18001120C
0x18001128a  lea     rax, [rdi-1]
0x18001128e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011292  ja      short loc_1800112A4
0x180011294  mov     rcx, rdi; hFindFile
0x180011297  call    cs:__imp_FindClose
0x18001129e  nop     dword ptr [rax+rax+00h]
0x1800112a3  nop
0x1800112a4  lea     rcx, [rsp+0B60h+var_B30]
0x1800112a9  call    ??1?$_Tree@V?$_Tset_traits@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@UFileTimeComparer@@V?$allocator@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::tuple<_FILETIME,std::wstring>,FileTimeComparer,std::allocator<std::tuple<_FILETIME,std::wstring>>,0>>::~_Tree<std::_Tset_traits<std::tuple<_FILETIME,std::wstring>,FileTimeComparer,std::allocator<std::tuple<_FILETIME,std::wstring>>,0>>(void)
0x1800112ae  mov     rcx, [rbp+0A60h+var_50]
0x1800112b5  xor     rcx, rsp; StackCookie
0x1800112b8  call    __security_check_cookie
0x1800112bd  add     rsp, 0B28h
0x1800112c4  pop     r15
0x1800112c6  pop     r14
0x1800112c8  pop     r13
0x1800112ca  pop     r12
0x1800112cc  pop     rdi
0x1800112cd  pop     rsi
0x1800112ce  pop     rbx
0x1800112cf  pop     rbp
0x1800112d0  retn
0x1800112d2  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
