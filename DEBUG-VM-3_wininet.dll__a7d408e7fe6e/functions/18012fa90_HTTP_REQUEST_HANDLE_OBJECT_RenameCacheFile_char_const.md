# HTTP_REQUEST_HANDLE_OBJECT::RenameCacheFile(char const *)

- ea: `0x18012fa90`
- end: `0x180130112`
- name: `?RenameCacheFile@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKPEBD@Z`
- size: `1666`
- prototype: `unsigned int __fastcall(HTTP_REQUEST_HANDLE_OBJECT *__hidden this, LPCCH)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800610f0`

## callees

- `0x180009cf0`
- `0x180020fc4`
- `0x180025910`
- `0x18002658c`
- `0x180026710`
- `0x180028858`
- `0x18002e110`
- `0x18002ec74`
- `0x18002eee4`
- `0x18004b824`
- `0x1800701d0`
- `0x180075d1c`
- `0x180097e40`
- `0x180098be4`
- `0x180099100`
- `0x1800d1590`
- `0x1800e08a0`
- `0x1800e4580`
- `0x1800e9f10`
- `0x1800f20bc`
- `0x180103b94`
- `0x180110554`
- `0x1801116e0`
- `0x18012331c`
- `0x18012fa90`
- `0x18013f7b8`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x180184da8`
- `0x180199a40`
- `0x1801b132c`
- `0x1801e1790`
- `0x1801e285c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012fc20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012ff1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012fc20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012ff1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012fbcf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012fea0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012fbcf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012fea0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801300ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801300ac`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18013003c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18013003c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18012ff45`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180130014`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18012ff45`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180130014`

## pseudocode

```c
__int64 __fastcall HTTP_REQUEST_HANDLE_OBJECT::RenameCacheFile(HTTP_REQUEST_HANDLE_OBJECT *this, LPCCH a2)
{
  char *v4; // r15
  unsigned __int16 **v5; // r13
  unsigned __int16 *v6; // r14
  unsigned int File; // ebx
  int v8; // r12d
  int v9; // r14d
  unsigned int v10; // esi
  int v11; // eax
  unsigned int LastError; // eax
  const char *v13; // rdx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  const char *v17; // rsi
  const unsigned __int16 *EdpClaim; // rax
  int v19; // edx
  unsigned __int64 v20; // r9
  int v21; // ebx
  const unsigned __int16 *v22; // rax
  int v23; // edx
  struct _INTERNAL_CACHE_ENTRY_INFOEX *v24; // rsi
  __int64 v25; // rax
  __int64 v26; // rcx
  bool v27; // zf
  char *URL; // rax
  __int64 v29; // rdx
  __int64 v30; // rax
  int v31; // ecx
  __int64 v32; // rcx
  int v33; // esi
  __int64 v34; // rcx
  const unsigned __int16 *v35; // rax
  BOOL v37; // [rsp+70h] [rbp-90h]
  const WCHAR *lpExistingFileName; // [rsp+78h] [rbp-88h]
  const char *v39; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+88h] [rbp-78h]
  char *v41; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 **v42; // [rsp+98h] [rbp-68h]
  struct _INTERNAL_CACHE_ENTRY_INFOEX *v43; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE hUrlCacheStream; // [rsp+A8h] [rbp-58h] BYREF
  struct _HEADER_PAIR *v45[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v46[5]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v47; // [rsp+E8h] [rbp-18h]
  __int64 v48; // [rsp+F0h] [rbp-10h]
  __int64 v49; // [rsp+F8h] [rbp-8h]
  __int64 v50; // [rsp+100h] [rbp+0h]
  int v51; // [rsp+108h] [rbp+8h]
  unsigned int v52; // [rsp+10Ch] [rbp+Ch]
  __int64 v53; // [rsp+110h] [rbp+10h]
  int v54; // [rsp+118h] [rbp+18h]
  __int64 v55; // [rsp+120h] [rbp+20h]
  int v56; // [rsp+128h] [rbp+28h]
  __int64 v57; // [rsp+130h] [rbp+30h]
  int v58; // [rsp+138h] [rbp+38h]
  LPCWSTR lpNewFileName[2]; // [rsp+150h] [rbp+50h] BYREF
  char v60; // [rsp+160h] [rbp+60h]
  char v61[271]; // [rsp+161h] [rbp+61h] BYREF

  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_s(1036, 50, &WPP_017edf3cec9234d7dd95b912a2e256d5_Traceguids, a2);
  v4 = 0;
  v40 = 0;
  LODWORD(hUrlCacheStream) = 0;
  v5 = (unsigned __int16 **)((char *)this + 696);
  v39 = String;
  v6 = (unsigned __int16 *)*((_QWORD *)this + 87);
  lpNewFileName[0] = &Data;
  v41 = 0;
  v43 = 0;
  lpNewFileName[1] = 0;
  v45[0] = 0;
  v42 = (unsigned __int16 **)((char *)this + 696);
  lpExistingFileName = v6;
  if ( !*((_QWORD *)this + 84) )
  {
    File = 12016;
    goto LABEL_81;
  }
  v8 = *((_DWORD *)this + 198);
  if ( (unsigned int)IsValidExtension(a2) )
  {
    if ( (*((_DWORD *)this + 1319) & 0x8000) != 0 || *((_DWORD *)this + 1259) || *((_DWORD *)this + 1258) )
    {
      File = 12019;
      goto LABEL_67;
    }
    v9 = 0;
    v10 = 0;
    v11 = StringCchLengthA(a2, 0x7FFFFFFFu, (unsigned __int64 *)&hUrlCacheStream);
    if ( v11 < 0 )
    {
      LastError = MapHRtoWin32Error((unsigned int)v11);
      goto LABEL_69;
    }
    v13 = (const char *)*((_QWORD *)this + 673);
    if ( v13 )
    {
      v14 = CWxStringA::Set((CWxStringA *)&v39, v13);
      if ( v14 < 0 )
        goto LABEL_17;
      v14 = CWxStringA::ExtendBuffer((CWxStringA *)&v39, (int)v40 + 2 + (int)hUrlCacheStream);
      if ( v14 < 0 )
        goto LABEL_17;
      v10 = HIDWORD(v40);
      CWxStringA::Detach((CWxStringA *)&v39, &v41);
      v4 = v41;
    }
    else if ( v8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 4848));
      if ( !HTTP_REQUEST_HANDLE_OBJECT::GetFileNameFromDisposition(this, (struct CWxStringA *)&v39) )
      {
        v14 = CWxStringA::ExtendBuffer((CWxStringA *)&v39, (int)v40 + 2 + (int)hUrlCacheStream);
        if ( v14 < 0 )
        {
LABEL_17:
          LastError = WX_WIN32_FROM_HR((unsigned int)v14);
          goto LABEL_69;
        }
        v10 = HIDWORD(v40);
        CWxStringA::Detach((CWxStringA *)&v39, &v41);
        v4 = v41;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 4848));
      v5 = (unsigned __int16 **)((char *)this + 696);
    }
    if ( v4 )
    {
      v60 = 46;
      v15 = StringCchCopyA(v61, 0x103u, a2);
      if ( v15 < 0 )
      {
        LastError = MapHRtoWin32Error((unsigned int)v15);
LABEL_27:
        v10 = 0;
        goto LABEL_69;
      }
      v16 = PathCchRenameExtensionA(v4, v10, a2);
      if ( v16 < 0 )
      {
        LastError = WX_WIN32_FROM_HR((unsigned int)v16);
        goto LABEL_27;
      }
      v17 = v4;
    }
    else
    {
      v17 = word_180222338;
    }
    EdpClaim = HTTP_REQUEST_HANDLE_OBJECT::GetEdpClaim(this);
    if ( (*((_DWORD *)this + 1291) & 0x800) != 0 )
      v20 = *((_QWORD *)this + 618);
    else
      v20 = 0;
    File = UrlCacheCreateFileEx(
             *((LPCCH *)this + 84),
             v19,
             0,
             v20,
             a2,
             v17,
             EdpClaim,
             (struct CWxString *)lpNewFileName,
             0);
    if ( File )
      goto LABEL_74;
    memset_0(v46, 0, 0x88u);
    v9 = 1;
    if ( *((_DWORD *)this + 1348) || (v21 = 0, v8) )
    {
      hUrlCacheStream = 0;
      v22 = HTTP_REQUEST_HANDLE_OBJECT::GetEdpClaim(this);
      File = UrlCacheRetrieve(*((LPCCH *)this + 84), v23, 1, 0, 0, 0, v22, &hUrlCacheStream, 0, &v43, 0, 0, 0, 0);
      if ( File )
      {
LABEL_72:
        DeleteFileW(lpNewFileName[0]);
        goto LABEL_74;
      }
      UnlockUrlCacheEntryStream(hUrlCacheStream, 0);
      v24 = v43;
      if ( *((_DWORD *)v43 + 7) && (*((_DWORD *)v43 + 7) != 1 || !v8 || !*((_QWORD *)this + 97)) )
        goto LABEL_75;
      memset_0(v46, 0, 0x88u);
      v46[0] = *((_QWORD *)v24 + 1);
      v46[3] = lpNewFileName[0];
      v25 = *((unsigned int *)v24 + 9);
      v26 = *((unsigned int *)v24 + 10);
      v57 = 0;
      v46[4] = v25 | (v26 << 32);
      v51 = *((_DWORD *)v24 + 6);
      v53 = *((_QWORD *)v24 + 10);
      v54 = *((_DWORD *)v24 + 22);
      v55 = *((_QWORD *)v24 + 12);
      v56 = *((_DWORD *)v24 + 26);
      v48 = *(_QWORD *)((char *)v24 + 44);
      v47 = *(_QWORD *)((char *)v24 + 52);
      v27 = *((_DWORD *)this + 176) == 0;
      v49 = *(_QWORD *)((char *)v24 + 132);
      v50 = *(_QWORD *)((char *)v24 + 124);
      if ( v27 )
        v46[2] = *((_QWORD *)this + 103);
      if ( v8 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 4848));
        v52 = HTTP_REQUEST_HANDLE_OBJECT::CalculateCacheEntryFlags(this);
        if ( !v47
          && v48
          && !CHttpHeaders::FastFindHeader((HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 3104), 1u, 0, v45)
          && PrefixMatchHeaderValue(*((const char **)v45[0] + 2), *((_DWORD *)v45[0] + 6), "image/", 6u) )
        {
          URL = INTERNET_CONNECT_HANDLE_OBJECT::GetURL(this);
          LOWORD(v29) = 63;
          v30 = PrivateStrChr(URL, v29);
          v31 = v58;
          if ( !v30 )
            v31 = 1;
          v58 = v31;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 4848));
      }
      else
      {
        v52 = *((_DWORD *)this + 1350);
        v58 = *((_DWORD *)this + 1349);
      }
      v21 = 1;
    }
    v37 = MoveFileExW(lpExistingFileName, lpNewFileName[0], 1u);
    v10 = v37;
    if ( v37 )
    {
      if ( v21 )
      {
        v33 = 0;
        if ( v8 && *((_DWORD *)v43 + 7) == 1 )
        {
          if ( !UnlockUrlCacheEntryFileA(*((LPCSTR *)v43 + 1), 0) )
          {
            LastError = WxGetLastError(v34);
            v10 = v37;
            goto LABEL_69;
          }
          v33 = 1;
        }
        File = UrlCacheCommitFile((const struct AddUrlArg *)v46);
        if ( v33 )
        {
          v45[0] = 0;
          v35 = HTTP_REQUEST_HANDLE_OBJECT::GetEdpClaim(this);
          UrlCacheRetrieve(*((LPCCH *)this + 84), 0, 1, 0, 0, 0, v35, 0, 0, v45, 0, 0, 0, 0);
          WxHeapFree<_WX_AVL_TABLE>(v45);
        }
        if ( File )
          goto LABEL_66;
      }
      *v5 = 0;
      CWxString::Detach((CWxString *)lpNewFileName, v5);
      File = 0;
      goto LABEL_74;
    }
    LastError = WxGetLastError(v32);
LABEL_69:
    File = LastError;
    if ( !LastError )
      goto LABEL_74;
    if ( !v10 )
    {
      if ( v9 )
        goto LABEL_72;
LABEL_74:
      v24 = v43;
LABEL_75:
      v6 = (unsigned __int16 *)lpExistingFileName;
      goto LABEL_76;
    }
LABEL_66:
    v6 = (unsigned __int16 *)lpExistingFileName;
    MoveFileExW(lpNewFileName[0], lpExistingFileName, 2u);
    goto LABEL_67;
  }
  File = 87;
LABEL_67:
  v24 = v43;
LABEL_76:
  if ( v24 )
  {
    UrlCacheSetEntryInfoEx(*((const char **)v24 + 1), v24, 0x10u);
    WxHeapFree<_WX_AVL_TABLE>(&v43);
  }
  if ( v4 )
    WxHeapFree<char>(&v41);
  v5 = v42;
LABEL_81:
  if ( v6 != *v5 && v6 )
    HeapFree(g_hWxProcessHeap, 0, v6);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 51, &WPP_017edf3cec9234d7dd95b912a2e256d5_Traceguids, File);
  CWxString::_Release((CWxString *)lpNewFileName);
  CWxStringA::_Release((CWxStringA *)&v39);
  return File;
}

```

## disassembly

```asm
0x18012fa90  mov     [rsp-8+arg_10], rbx
0x18012fa95  push    rbp
0x18012fa96  push    rsi
0x18012fa97  push    rdi
0x18012fa98  push    r12
0x18012fa9a  push    r13
0x18012fa9c  push    r14
0x18012fa9e  push    r15
0x18012faa0  lea     rbp, [rsp-180h]
0x18012faa8  sub     rsp, 280h
0x18012faaf  mov     rax, cs:__security_cookie
0x18012fab6  xor     rax, rsp
0x18012fab9  mov     [rbp+1B0h+var_40], rax
0x18012fac0  mov     rbx, rdx
0x18012fac3  mov     rdi, rcx
0x18012fac6  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18012facd  jz      short loc_18012FAE8
0x18012facf  mov     edx, 32h ; '2'
0x18012fad4  lea     r8, WPP_017edf3cec9234d7dd95b912a2e256d5_Traceguids
0x18012fadb  mov     ecx, 40Ch
0x18012fae0  mov     r9, rbx
0x18012fae3  call    WPP_SF_s
0x18012fae8  xor     r15d, r15d
0x18012faeb  mov     [rbp+1B0h+var_228], 0
0x18012faf3  lea     rax, String
0x18012fafa  mov     dword ptr [rbp+1B0h+hUrlCacheStream], 0
0x18012fb01  lea     r13, [rdi+2B8h]
0x18012fb08  mov     [rbp+1B0h+var_230], rax
0x18012fb0c  lea     rax, Data
0x18012fb13  mov     r14, [r13+0]
0x18012fb17  mov     [rbp+1B0h+lpNewFileName], rax
0x18012fb1b  mov     [rbp+1B0h+var_220], r15
0x18012fb1f  mov     [rbp+1B0h+var_210], r15
0x18012fb23  mov     [rbp+1B0h+var_158], r15
0x18012fb27  mov     [rbp+1B0h+var_200], r15
0x18012fb2b  mov     [rbp+1B0h+var_218], r13
0x18012fb2f  mov     [rsp+2B0h+lpExistingFileName], r14
0x18012fb34  cmp     [rdi+2A0h], r15
0x18012fb3b  jnz     short loc_18012FB47
0x18012fb3d  mov     ebx, 2EF0h
0x18012fb42  jmp     loc_180130095
0x18012fb47  mov     r12d, [rdi+318h]
0x18012fb4e  mov     rcx, rbx; char *
0x18012fb51  call    ?IsValidExtension@@YAHPEBD@Z; IsValidExtension(char const *)
0x18012fb56  test    eax, eax
0x18012fb58  jnz     short loc_18012FB62
0x18012fb5a  lea     ebx, [rax+57h]
0x18012fb5d  jmp     loc_18013001A
0x18012fb62  test    dword ptr [rdi+149Ch], 8000h
0x18012fb6c  jz      short loc_18012FB78
0x18012fb6e  mov     ebx, 2EF3h
0x18012fb73  jmp     loc_18013001A
0x18012fb78  cmp     [rdi+13ACh], r15d
0x18012fb7f  jnz     short loc_18012FB6E
0x18012fb81  cmp     [rdi+13A8h], r15d
0x18012fb88  jnz     short loc_18012FB6E
0x18012fb8a  lea     r8, [rbp+1B0h+hUrlCacheStream]; unsigned __int64 *
0x18012fb8e  mov     edx, 7FFFFFFFh; unsigned __int64
0x18012fb93  mov     rcx, rbx; char *
0x18012fb96  xor     r14d, r14d
0x18012fb99  xor     esi, esi
0x18012fb9b  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18012fba0  test    eax, eax
0x18012fba2  jns     short loc_18012FBB0
0x18012fba4  mov     ecx, eax
0x18012fba6  call    MapHRtoWin32Error
0x18012fbab  jmp     loc_180130029
0x18012fbb0  mov     rdx, [rdi+1508h]; char *
0x18012fbb7  test    rdx, rdx
0x18012fbba  jnz     short loc_18012FC2F
0x18012fbbc  test    r12d, r12d
0x18012fbbf  jz      loc_18012FC74
0x18012fbc5  lea     r13, [rdi+12F0h]
0x18012fbcc  mov     rcx, r13; lpCriticalSection
0x18012fbcf  call    cs:__imp_EnterCriticalSection
0x18012fbd5  lea     rdx, [rbp+1B0h+var_230]; struct CWxStringA *
0x18012fbd9  mov     rcx, rdi; this
0x18012fbdc  call    ?GetFileNameFromDisposition@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKPEAVCWxStringA@@@Z; HTTP_REQUEST_HANDLE_OBJECT::GetFileNameFromDisposition(CWxStringA *)
0x18012fbe1  test    eax, eax
0x18012fbe3  jnz     short loc_18012FC1D
0x18012fbe5  mov     eax, dword ptr [rbp+1B0h+var_228]
0x18012fbe8  lea     rcx, [rbp+1B0h+var_230]; this
0x18012fbec  mov     edx, dword ptr [rbp+1B0h+hUrlCacheStream]
0x18012fbef  add     eax, 2
0x18012fbf2  add     edx, eax; unsigned int
0x18012fbf4  call    ?ExtendBuffer@CWxStringA@@QEAAJK@Z; CWxStringA::ExtendBuffer(ulong)
0x18012fbf9  test    eax, eax
0x18012fbfb  jns     short loc_18012FC09
0x18012fbfd  mov     ecx, eax
0x18012fbff  call    WX_WIN32_FROM_HR
0x18012fc04  jmp     loc_180130029
0x18012fc09  mov     esi, dword ptr [rbp+1B0h+var_228+4]
0x18012fc0c  lea     rdx, [rbp+1B0h+var_220]; char **
0x18012fc10  lea     rcx, [rbp+1B0h+var_230]; this
0x18012fc14  call    ?Detach@CWxStringA@@QEAAXPEAPEAD@Z; CWxStringA::Detach(char * *)
0x18012fc19  mov     r15, [rbp+1B0h+var_220]
0x18012fc1d  mov     rcx, r13; lpCriticalSection
0x18012fc20  call    cs:__imp_LeaveCriticalSection
0x18012fc26  lea     r13, [rdi+2B8h]
0x18012fc2d  jmp     short loc_18012FC74
0x18012fc2f  lea     rcx, [rbp+1B0h+var_230]; this
0x18012fc33  call    ?Set@CWxStringA@@QEAAJPEBD@Z; CWxStringA::Set(char const *)
0x18012fc38  test    eax, eax
0x18012fc3a  jns     short loc_18012FC48
0x18012fc3c  mov     ecx, eax
0x18012fc3e  call    WX_WIN32_FROM_HR
0x18012fc43  jmp     loc_180130029
0x18012fc48  mov     eax, dword ptr [rbp+1B0h+var_228]
0x18012fc4b  lea     rcx, [rbp+1B0h+var_230]; this
0x18012fc4f  mov     edx, dword ptr [rbp+1B0h+hUrlCacheStream]
0x18012fc52  add     eax, 2
0x18012fc55  add     edx, eax; unsigned int
0x18012fc57  call    ?ExtendBuffer@CWxStringA@@QEAAJK@Z; CWxStringA::ExtendBuffer(ulong)
0x18012fc5c  test    eax, eax
0x18012fc5e  js      short loc_18012FC3C
0x18012fc60  mov     esi, dword ptr [rbp+1B0h+var_228+4]
0x18012fc63  lea     rdx, [rbp+1B0h+var_220]; char **
0x18012fc67  lea     rcx, [rbp+1B0h+var_230]; this
0x18012fc6b  call    ?Detach@CWxStringA@@QEAAXPEAPEAD@Z; CWxStringA::Detach(char * *)
0x18012fc70  mov     r15, [rbp+1B0h+var_220]
0x18012fc74  test    r15, r15
0x18012fc77  jz      short loc_18012FCC0
0x18012fc79  mov     r8, rbx; char *
0x18012fc7c  mov     [rbp+1B0h+var_150], 2Eh ; '.'
0x18012fc80  mov     edx, 103h; unsigned __int64
0x18012fc85  lea     rcx, [rbp+1B0h+var_14F]; char *
0x18012fc89  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18012fc8e  test    eax, eax
0x18012fc90  jns     short loc_18012FCA1
0x18012fc92  mov     ecx, eax
0x18012fc94  call    MapHRtoWin32Error
0x18012fc99  mov     esi, r14d
0x18012fc9c  jmp     loc_180130029
0x18012fca1  mov     edx, esi; unsigned __int64
0x18012fca3  mov     r8, rbx; char *
0x18012fca6  mov     rcx, r15; char *
0x18012fca9  call    ?PathCchRenameExtensionA@@YAJPEAD_KPEBD@Z; PathCchRenameExtensionA(char *,unsigned __int64,char const *)
0x18012fcae  test    eax, eax
0x18012fcb0  jns     short loc_18012FCBB
0x18012fcb2  mov     ecx, eax
0x18012fcb4  call    WX_WIN32_FROM_HR
0x18012fcb9  jmp     short loc_18012FC99
0x18012fcbb  mov     rsi, r15
0x18012fcbe  jmp     short loc_18012FCC7
0x18012fcc0  lea     rsi, word_180222338
0x18012fcc7  mov     rcx, rdi; this
0x18012fcca  call    ?GetEdpClaim@HTTP_REQUEST_HANDLE_OBJECT@@AEAAPEBGXZ; HTTP_REQUEST_HANDLE_OBJECT::GetEdpClaim(void)
0x18012fccf  test    dword ptr [rdi+142Ch], 800h
0x18012fcd9  jz      short loc_18012FCE4
0x18012fcdb  mov     r9, [rdi+1350h]
0x18012fce2  jmp     short loc_18012FCE7
0x18012fce4  xor     r9d, r9d; unsigned __int64
0x18012fce7  mov     [rsp+2B0h+var_270], r14; void **
0x18012fcec  lea     rcx, [rbp+1B0h+lpNewFileName]
0x18012fcf0  mov     [rsp+2B0h+var_278], rcx; struct CWxString *
0x18012fcf5  xor     r8d, r8d; struct CAppCacheHandle *
0x18012fcf8  mov     rcx, [rdi+2A0h]; lpMultiByteStr
0x18012fcff  mov     [rsp+2B0h+var_280], rax; unsigned __int16 *
0x18012fd04  mov     [rsp+2B0h+var_288], rsi; char *
0x18012fd09  mov     [rsp+2B0h+var_290], rbx; LPCCH
0x18012fd0e  call    ?UrlCacheCreateFileEx@@YAKPEBDHPEAVCAppCacheHandle@@_K00PEBGPEAVCWxString@@PEAPEAX@Z; UrlCacheCreateFileEx(char const *,int,CAppCacheHandle *,unsigned __int64,char const *,char const *,ushort const *,CWxString *,void * *)
0x18012fd13  mov     ebx, eax
0x18012fd15  test    eax, eax
0x18012fd17  jnz     loc_18013005A
0x18012fd1d  xor     edx, edx; Val
0x18012fd1f  lea     rcx, [rbp+1B0h+var_1F0]; void *
0x18012fd23  mov     r8d, 88h; Size
0x18012fd29  call    memset_0
0x18012fd2e  xor     esi, esi
0x18012fd30  lea     r14d, [rbx+1]
0x18012fd34  cmp     [rdi+1510h], esi
0x18012fd3a  jnz     short loc_18012FD47
0x18012fd3c  mov     ebx, esi
0x18012fd3e  test    r12d, r12d
0x18012fd41  jz      loc_18012FF39
0x18012fd47  mov     rcx, rdi; this
0x18012fd4a  mov     [rbp+1B0h+hUrlCacheStream], rsi
0x18012fd4e  call    ?GetEdpClaim@HTTP_REQUEST_HANDLE_OBJECT@@AEAAPEBGXZ; HTTP_REQUEST_HANDLE_OBJECT::GetEdpClaim(void)
0x18012fd53  mov     [rsp+2B0h+var_248], rsi; unsigned __int64 *
0x18012fd58  lea     rcx, [rbp+1B0h+var_210]
0x18012fd5c  mov     [rsp+2B0h+var_250], rsi; unsigned int *
0x18012fd61  xor     r9d, r9d; struct CAppCacheHandle *
0x18012fd64  mov     [rsp+2B0h+var_258], rsi; unsigned int *
0x18012fd69  mov     r8d, r14d; int
0x18012fd6c  mov     [rsp+2B0h+var_260], rsi; unsigned __int8 **
0x18012fd71  mov     [rsp+2B0h+var_268], rcx; struct _INTERNAL_CACHE_ENTRY_INFOEX **
0x18012fd76  lea     rcx, [rbp+1B0h+hUrlCacheStream]
0x18012fd7a  mov     [rsp+2B0h+var_270], rsi; struct _APP_CACHE_RETRIEVE_STATE *
0x18012fd7f  mov     [rsp+2B0h+var_278], rcx; void **
0x18012fd84  mov     rcx, [rdi+2A0h]; lpMultiByteStr
0x18012fd8b  mov     [rsp+2B0h+var_280], rax; unsigned __int16 *
0x18012fd90  mov     dword ptr [rsp+2B0h+var_288], esi; int
0x18012fd94  mov     dword ptr [rsp+2B0h+var_290], esi; int
0x18012fd98  call    ?UrlCacheRetrieve@@YAKPEBDHHPEAVCAppCacheHandle@@HHPEBGPEAPEAXPEAU_APP_CACHE_RETRIEVE_STATE@@PEAPEAU_INTERNAL_CACHE_ENTRY_INFOEX@@PEAPEAEPEAK7PEA_K@Z; UrlCacheRetrieve(char const *,int,int,CAppCacheHandle *,int,int,ushort const *,void * *,_APP_CACHE_RETRIEVE_STATE *,_INTERNAL_CACHE_ENTRY_INFOEX * *,uchar * *,ulong *,ulong *,unsigned __int64 *)
0x18012fd9d  mov     ebx, eax
0x18012fd9f  test    eax, eax
0x18012fda1  jnz     loc_180130038
0x18012fda7  mov     rcx, [rbp+1B0h+hUrlCacheStream]; hUrlCacheStream
0x18012fdab  xor     edx, edx; Reserved
0x18012fdad  call    UnlockUrlCacheEntryStream
0x18012fdb2  mov     rsi, [rbp+1B0h+var_210]
0x18012fdb6  cmp     [rsi+1Ch], ebx
0x18012fdb9  jz      short loc_18012FDDC
0x18012fdbb  cmp     [rsi+1Ch], r14d
0x18012fdbf  jnz     loc_18013005E
0x18012fdc5  test    r12d, r12d
0x18012fdc8  jz      loc_18013005E
0x18012fdce  cmp     qword ptr [rdi+308h], 0
0x18012fdd6  jz      loc_18013005E
0x18012fddc  xor     edx, edx; Val
0x18012fdde  lea     rcx, [rbp+1B0h+var_1F0]; void *
0x18012fde2  mov     r8d, 88h; Size
0x18012fde8  call    memset_0
0x18012fded  mov     rax, [rsi+8]
0x18012fdf1  mov     [rbp+1B0h+var_1F0], rax
0x18012fdf5  mov     rax, [rbp+1B0h+lpNewFileName]
0x18012fdf9  mov     [rbp+1B0h+var_1D8], rax
0x18012fdfd  mov     eax, [rsi+24h]
0x18012fe00  mov     ecx, [rsi+28h]
0x18012fe03  mov     [rbp+1B0h+var_180], 0
0x18012fe0b  shl     rcx, 20h
0x18012fe0f  or      rcx, rax
0x18012fe12  mov     [rbp+1B0h+var_1D0], rcx
0x18012fe16  mov     eax, [rsi+18h]
0x18012fe19  mov     [rbp+1B0h+var_1A8], eax
0x18012fe1c  mov     rax, [rsi+50h]
0x18012fe20  mov     [rbp+1B0h+var_1A0], rax
0x18012fe24  mov     eax, [rsi+58h]
0x18012fe27  mov     [rbp+1B0h+var_198], eax
0x18012fe2a  mov     rax, [rsi+60h]
0x18012fe2e  mov     [rbp+1B0h+var_190], rax
0x18012fe32  mov     eax, [rsi+68h]
0x18012fe35  mov     [rbp+1B0h+var_188], eax
0x18012fe38  mov     eax, [rsi+2Ch]
0x18012fe3b  mov     ecx, [rsi+30h]
0x18012fe3e  shl     rcx, 20h
0x18012fe42  or      rcx, rax
0x18012fe45  mov     [rbp+1B0h+var_1C0], rcx
0x18012fe49  mov     eax, [rsi+34h]
0x18012fe4c  mov     ecx, [rsi+38h]
0x18012fe4f  shl     rcx, 20h
0x18012fe53  or      rcx, rax
0x18012fe56  mov     [rbp+1B0h+var_1C8], rcx
0x18012fe5a  mov     eax, [rsi+84h]
0x18012fe60  mov     ecx, [rsi+88h]
0x18012fe66  shl     rcx, 20h
0x18012fe6a  or      rcx, rax
0x18012fe6d  cmp     dword ptr [rdi+2C0h], 0
0x18012fe74  mov     [rbp+1B0h+var_1B8], rcx
0x18012fe78  mov     rax, [rsi+7Ch]
0x18012fe7c  mov     [rbp+1B0h+var_1B0], rax
0x18012fe80  jnz     short loc_18012FE8D
0x18012fe82  mov     rax, [rdi+338h]
0x18012fe89  mov     [rbp+1B0h+var_1E0], rax
0x18012fe8d  test    r12d, r12d
0x18012fe90  jz      loc_18012FF24
0x18012fe96  lea     rsi, [rdi+12F0h]
0x18012fe9d  mov     rcx, rsi; lpCriticalSection
0x18012fea0  call    cs:__imp_EnterCriticalSection
0x18012fea6  mov     rcx, rdi; this
0x18012fea9  call    ?CalculateCacheEntryFlags@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKXZ; HTTP_REQUEST_HANDLE_OBJECT::CalculateCacheEntryFlags(void)
0x18012feae  cmp     [rbp+1B0h+var_1C8], 0
0x18012feb3  mov     [rbp+1B0h+var_1A4], eax
0x18012feb6  jnz     short loc_18012FF19
0x18012feb8  cmp     [rbp+1B0h+var_1C0], 0
0x18012febd  jz      short loc_18012FF19
0x18012febf  lea     r9, [rbp+1B0h+var_200]; struct _HEADER_PAIR **
0x18012fec3  xor     r8d, r8d; unsigned int
0x18012fec6  mov     edx, r14d; unsigned int
0x18012fec9  lea     rcx, [rdi+0C20h]; this
0x18012fed0  call    ?FastFindHeader@CHttpHeaders@@QEAAKKKPEAPEBU_HEADER_PAIR@@@Z; CHttpHeaders::FastFindHeader(ulong,ulong,_HEADER_PAIR const * *)
0x18012fed5  test    eax, eax
0x18012fed7  jnz     short loc_18012FF19
0x18012fed9  mov     rcx, [rbp+1B0h+var_200]
0x18012fedd  lea     r9d, [rax+6]; unsigned int
0x18012fee1  lea     r8, aImage; "image/"
0x18012fee8  mov     edx, [rcx+18h]; unsigned int
0x18012feeb  mov     rcx, [rcx+10h]; char *
0x18012feef  call    ?PrefixMatchHeaderValue@@YAHPEBDK0K@Z; PrefixMatchHeaderValue(char const *,ulong,char const *,ulong)
0x18012fef4  test    eax, eax
0x18012fef6  jz      short loc_18012FF19
0x18012fef8  mov     rcx, rdi; this
0x18012fefb  call    ?GetURL@INTERNET_CONNECT_HANDLE_OBJECT@@QEAAPEADXZ; INTERNET_CONNECT_HANDLE_OBJECT::GetURL(void)
0x18012ff00  mov     rcx, rax
0x18012ff03  mov     dx, 3Fh ; '?'
0x18012ff07  call    PrivateStrChr
0x18012ff0c  mov     ecx, [rbp+1B0h+var_178]
0x18012ff0f  test    rax, rax
0x18012ff12  cmovz   ecx, r14d
0x18012ff16  mov     [rbp+1B0h+var_178], ecx
0x18012ff19  mov     rcx, rsi; lpCriticalSection
0x18012ff1c  call    cs:__imp_LeaveCriticalSection
0x18012ff22  jmp     short loc_18012FF36
0x18012ff24  mov     eax, [rdi+1518h]
0x18012ff2a  mov     [rbp+1B0h+var_1A4], eax
0x18012ff2d  mov     eax, [rdi+1514h]
0x18012ff33  mov     [rbp+1B0h+var_178], eax
0x18012ff36  mov     ebx, r14d
0x18012ff39  mov     rdx, [rbp+1B0h+lpNewFileName]; lpNewFileName
0x18012ff3d  mov     r8d, r14d; dwFlags
  ... truncated ...
```
