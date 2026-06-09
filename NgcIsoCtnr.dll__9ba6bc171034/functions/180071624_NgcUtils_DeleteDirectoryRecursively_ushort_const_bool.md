# NgcUtils::DeleteDirectoryRecursively(ushort const *,bool)

- ea: `0x180071624`
- end: `0x180071cc9`
- name: `?DeleteDirectoryRecursively@NgcUtils@@YAJPEBG_N@Z`
- size: `1701`
- prototype: `__int64 __fastcall(NgcUtils *this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003bb68`
- `0x18003bbb8`
- `0x18003bc08`
- `0x18003bec0`

## callees

- `0x180002654`
- `0x180007670`
- `0x1800084c8`
- `0x180011c9c`
- `0x180017d70`
- `0x18001cbe8`
- `0x18002ba68`
- `0x1800477fc`
- `0x18006ff74`
- `0x1800712b8`
- `0x1800713cc`
- `0x180071624`
- `0x180071cd0`
- `0x180071ef8`
- `0x180071f44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800719c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071c32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071c4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071c67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071c81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071caf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800719c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071c32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071c4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071c67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071c81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071caf`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18007176d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18007176d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800719f7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800719f7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18007181c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18007181c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800719bd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800719bd`

## pseudocode

```c
__int64 __fastcall NgcUtils::DeleteDirectoryRecursively(NgcUtils *this, const unsigned __int16 *a2)
{
  int v3; // esi
  __int64 v4; // rax
  __m128i si128; // xmm6
  __int128 *v6; // rbx
  char v7; // cl
  const WCHAR *v8; // rax
  signed int LastError; // edi
  int v10; // r8d
  int v11; // r9d
  __int128 *v12; // rcx
  const WCHAR *v13; // rax
  HANDLE FirstFile; // rax
  DWORD v15; // eax
  int v16; // r8d
  int v17; // r9d
  __int128 *v18; // rcx
  const WCHAR *v19; // rax
  int v20; // r8d
  int v21; // r9d
  DWORD v22; // eax
  int v23; // r8d
  int v24; // r9d
  __int128 *v25; // rcx
  signed int v27; // eax
  int v28; // edx
  unsigned int v29; // r8d
  signed int v30; // eax
  int v31; // edx
  unsigned int v32; // r8d
  signed int v33; // eax
  int v34; // edx
  unsigned int v35; // r8d
  signed int v36; // eax
  int v37; // edx
  unsigned int v38; // r8d
  signed int v39; // eax
  int v40; // edx
  unsigned int v41; // r8d
  signed int v42; // eax
  int v43; // edx
  unsigned int v44; // r8d
  __int64 v45; // [rsp+38h] [rbp-D0h] BYREF
  void **v46; // [rsp+40h] [rbp-C8h] BYREF
  __int64 hFindFile; // [rsp+48h] [rbp-C0h]
  HANDLE hFindFile_8[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v49; // [rsp+60h] [rbp-A8h]
  __int64 v50; // [rsp+70h] [rbp-98h]
  _QWORD v51[2]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v52[2]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v53[2]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v54; // [rsp+A8h] [rbp-60h] BYREF
  __m128i v55; // [rsp+B8h] [rbp-50h]
  _OWORD v56[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v57; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v58; // [rsp+F8h] [rbp-10h]
  char v59; // [rsp+108h] [rbp+0h]
  _OWORD v60[2]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v61[32]; // [rsp+130h] [rbp+28h] BYREF
  _OWORD v62[2]; // [rsp+150h] [rbp+48h] BYREF
  char v63; // [rsp+170h] [rbp+68h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+178h] [rbp+70h] BYREF

  v3 = 0;
  *(_OWORD *)hFindFile_8 = 0;
  v49 = 0;
  v50 = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(hFindFile_8, a2);
  v4 = std::wstring::wstring(v60, this);
  v57 = *(_OWORD *)v4;
  v58 = *(_OWORD *)(v4 + 16);
  *(_QWORD *)(v4 + 16) = 0;
  *(_QWORD *)(v4 + 24) = 7;
  *(_WORD *)v4 = 0;
  v59 = 0;
  std::stack<std::pair<std::wstring,bool>>::push(hFindFile_8, &v57);
  std::wstring::_Tidy_deallocate(&v57);
  std::wstring::_Tidy_deallocate(v60);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    if ( !v50 )
    {
      std::deque<std::pair<std::wstring,bool>>::~deque<std::pair<std::wstring,bool>>(hFindFile_8);
      return (unsigned int)v3;
    }
    v6 = (__int128 *)*((_QWORD *)hFindFile_8[1] + ((v49 - 1) & (*((_QWORD *)&v49 + 1) - 1LL + v50)));
    v7 = *((_BYTE *)v6 + 32);
    if ( !v7 )
      break;
    v57 = 0;
    v58 = 0;
    v57 = *v6;
    v58 = v6[1];
    *((_QWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 3) = 7;
    *(_WORD *)v6 = 0;
    v59 = v7;
    std::deque<std::pair<std::wstring,bool>>::pop_back(hFindFile_8);
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v57);
    if ( !RemoveDirectoryW(v8) )
    {
      LastError = GetLastError();
      if ( (unsigned int)(LastError - 2) > 1 )
      {
        if ( *(_DWORD *)g_logProvider > 2u )
        {
          LODWORD(v45) = LastError;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            g_logProvider,
            (unsigned int)byte_1800B39FD,
            v10,
            v11,
            (__int64)&v45);
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v25 = &v57;
        goto LABEL_46;
      }
    }
    v12 = &v57;
LABEL_7:
    std::wstring::_Tidy_deallocate(v12);
  }
  *((_BYTE *)v6 + 32) = 1;
  v51[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
  v51[1] = L"*";
  v56[0] = 0;
  v56[1] = si128;
  LOWORD(v56[0]) = 0;
  v3 = NgcUtils::ComposePath(v51, 2, v56);
  if ( v3 < 0 )
  {
LABEL_60:
    std::wstring::_Tidy_deallocate(v56);
    LastError = v3;
    goto LABEL_61;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56);
  FirstFile = FindFirstFileExW(v13, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
  v46 = &Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::`vftable';
  hFindFile = (__int64)FirstFile;
  if ( FirstFile == (HANDLE)-1LL )
  {
    v15 = GetLastError();
    LastError = v15;
    if ( ((v15 - 2) & 0xFFFFFFEE) != 0 || v15 == 19 )
    {
      if ( *(_DWORD *)g_logProvider > 2u )
      {
        LODWORD(v45) = v15;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          g_logProvider,
          (unsigned int)&dword_1800B3A24,
          v16,
          v17,
          (__int64)&v45);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v46 = &Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::`vftable';
      if ( hFindFile != -1 )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::InternalClose(&v46) )
        {
          v39 = GetLastError();
          if ( v39 > 0 )
            v39 = (unsigned __int16)v39 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v39, v40, v41);
          __debugbreak();
        }
        goto LABEL_44;
      }
      goto LABEL_45;
    }
    v46 = &Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::`vftable';
    if ( hFindFile == -1 )
      goto LABEL_32;
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::InternalClose(&v46) )
    {
      v30 = GetLastError();
      if ( v30 > 0 )
        v30 = (unsigned __int16)v30 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v30, v31, v32);
      __debugbreak();
    }
    goto LABEL_31;
  }
  while ( 1 )
  {
    std::wstring::wstring(v61, FindFileData.cFileName);
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    if ( (unsigned __int8)std::wstring::_Equal(v61, L".") || (unsigned __int8)std::wstring::_Equal(v61, L"..") )
      goto LABEL_25;
    v52[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
    v52[1] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61);
    v54 = 0;
    v55 = si128;
    LOWORD(v54) = 0;
    v3 = NgcUtils::ComposePath(v52, 2, &v54);
    if ( v3 < 0 )
    {
      std::wstring::_Tidy_deallocate(&v54);
      std::wstring::_Tidy_deallocate(v61);
      v46 = &Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::`vftable';
      if ( hFindFile == -1 )
        goto LABEL_60;
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::InternalClose(&v46) )
      {
        v33 = GetLastError();
        if ( v33 > 0 )
          v33 = (unsigned __int16)v33 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v33, v34, v35);
        __debugbreak();
      }
LABEL_59:
      hFindFile = -1;
      goto LABEL_60;
    }
    v62[0] = v54;
    v62[1] = v55;
    v55 = si128;
    LOWORD(v54) = 0;
    v63 = 0;
    std::stack<std::pair<std::wstring,bool>>::push(hFindFile_8, v62);
    std::wstring::_Tidy_deallocate(v62);
    v18 = &v54;
LABEL_24:
    std::wstring::_Tidy_deallocate(v18);
LABEL_25:
    std::wstring::_Tidy_deallocate(v61);
    if ( !FindNextFileW((HANDLE)hFindFile, &FindFileData) )
    {
      v22 = GetLastError();
      if ( v22 != 18 && *(_DWORD *)g_logProvider > 3u )
      {
        LODWORD(v45) = v22;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          g_logProvider,
          (unsigned int)&byte_1800B39B7,
          v23,
          v24,
          (__int64)&v45);
      }
      v46 = &Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::`vftable';
      if ( hFindFile == -1 )
        goto LABEL_32;
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::InternalClose(&v46) )
      {
        v42 = GetLastError();
        if ( v42 > 0 )
          v42 = (unsigned __int16)v42 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v42, v43, v44);
        JUMPOUT(0x180071CC8LL);
      }
LABEL_31:
      hFindFile = -1;
LABEL_32:
      v12 = v56;
      goto LABEL_7;
    }
  }
  v53[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
  v53[1] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61);
  v60[0] = 0;
  v60[1] = si128;
  LOWORD(v60[0]) = 0;
  v3 = NgcUtils::ComposePath(v53, 2, v60);
  if ( v3 < 0 )
  {
    std::wstring::_Tidy_deallocate(v60);
    std::wstring::_Tidy_deallocate(v61);
    v46 = &Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::`vftable';
    if ( hFindFile == -1 )
      goto LABEL_60;
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::InternalClose(&v46) )
    {
      v27 = GetLastError();
      if ( v27 > 0 )
        v27 = (unsigned __int16)v27 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v27, v28, v29);
      __debugbreak();
    }
    goto LABEL_59;
  }
  v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v60);
  if ( DeleteFileW(v19) || (LastError = GetLastError(), (unsigned int)(LastError - 2) <= 1) )
  {
    v18 = v60;
    goto LABEL_24;
  }
  if ( *(_DWORD *)g_logProvider > 2u )
  {
    LODWORD(v45) = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      g_logProvider,
      (unsigned int)byte_1800B39DB,
      v20,
      v21,
      (__int64)&v45);
  }
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  std::wstring::_Tidy_deallocate(v60);
  std::wstring::_Tidy_deallocate(v61);
  v46 = &Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::`vftable';
  if ( hFindFile != -1 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::InternalClose(&v46) )
    {
      v36 = GetLastError();
      if ( v36 > 0 )
        v36 = (unsigned __int16)v36 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v36, v37, v38);
      __debugbreak();
    }
LABEL_44:
    hFindFile = -1;
  }
LABEL_45:
  v25 = v56;
LABEL_46:
  std::wstring::_Tidy_deallocate(v25);
LABEL_61:
  std::deque<std::pair<std::wstring,bool>>::~deque<std::pair<std::wstring,bool>>(hFindFile_8);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180071624  mov     rax, rsp
0x180071627  push    rbp
0x180071628  push    rbx
0x180071629  push    rsi
0x18007162a  push    rdi
0x18007162b  push    r12
0x18007162d  push    r15
0x18007162f  lea     rbp, [rax-318h]
0x180071636  sub     rsp, 3E8h
0x18007163d  movaps  xmmword ptr [rax-48h], xmm6
0x180071641  mov     rax, cs:__security_cookie
0x180071648  xor     rax, rsp
0x18007164b  mov     [rbp+310h+var_50], rax
0x180071652  mov     rbx, rcx
0x180071655  xor     esi, esi
0x180071657  xorps   xmm0, xmm0
0x18007165a  movdqu  xmmword ptr [rsp+410h+hFindFile+8], xmm0
0x180071660  xorps   xmm1, xmm1
0x180071663  movdqu  [rsp+410h+var_3C0+8], xmm1
0x180071669  mov     [rsp+410h+var_3A8], rsi
0x18007166e  lea     rcx, [rsp+410h+hFindFile+8]
0x180071673  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x180071678  nop
0x180071679  mov     rdx, rbx
0x18007167c  lea     rcx, [rbp+310h+var_308]
0x180071680  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180071685  mov     rcx, rax
0x180071688  movups  xmm1, xmmword ptr [rax]
0x18007168b  movups  [rbp+310h+var_330], xmm1
0x18007168f  movups  xmm0, xmmword ptr [rax+10h]
0x180071693  movups  [rbp+310h+var_320], xmm0
0x180071697  mov     [rax+10h], rsi
0x18007169b  mov     qword ptr [rax+18h], 7
0x1800716a3  xor     eax, eax
0x1800716a5  mov     [rcx], ax
0x1800716a8  mov     [rbp+310h+var_310], al
0x1800716ab  lea     rdx, [rbp+310h+var_330]
0x1800716af  lea     rcx, [rsp+410h+hFindFile+8]
0x1800716b4  call    ?push@?$stack@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@V?$deque@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@@2@@std@@QEAAX$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@2@@Z; std::stack<std::pair<std::wstring,bool>>::push(std::pair<std::wstring,bool> &&)
0x1800716b9  nop
0x1800716ba  lea     rcx, [rbp+310h+var_330]
0x1800716be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800716c3  nop
0x1800716c4  lea     rcx, [rbp+310h+var_308]
0x1800716c8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800716cd  lea     r12, ??_7?$HandleT@UFindHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::`vftable'
0x1800716d4  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800716d8  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800716e0  mov     rcx, [rsp+410h+var_3A8]
0x1800716e5  test    rcx, rcx
0x1800716e8  jz      loc_180071BFF
0x1800716ee  mov     rax, [rsp+410h+var_3B0]
0x1800716f3  dec     rax
0x1800716f6  add     rcx, rax
0x1800716f9  mov     rax, qword ptr [rsp+410h+var_3C0+8]
0x1800716fe  dec     rax
0x180071701  and     rcx, rax
0x180071704  mov     rax, qword ptr [rsp+410h+var_3C0]
0x180071709  mov     rbx, [rax+rcx*8]
0x18007170d  mov     cl, [rbx+20h]
0x180071710  test    cl, cl
0x180071712  jz      loc_180071799
0x180071718  xorps   xmm0, xmm0
0x18007171b  movups  [rbp+310h+var_330], xmm0
0x18007171f  xorps   xmm1, xmm1
0x180071722  movdqu  [rbp+310h+var_320], xmm1
0x180071727  movups  xmm0, xmmword ptr [rbx]
0x18007172a  movdqu  [rbp+310h+var_330], xmm0
0x18007172f  mov     rax, [rbx+10h]
0x180071733  mov     qword ptr [rbp+310h+var_320], rax
0x180071737  mov     rax, [rbx+18h]
0x18007173b  mov     qword ptr [rbp+310h+var_320+8], rax
0x18007173f  mov     qword ptr [rbx+10h], 0
0x180071747  mov     qword ptr [rbx+18h], 7
0x18007174f  xor     eax, eax
0x180071751  mov     [rbx], ax
0x180071754  mov     [rbp+310h+var_310], cl
0x180071757  lea     rcx, [rsp+410h+hFindFile+8]
0x18007175c  call    ?pop_back@?$deque@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@@std@@QEAAXXZ; std::deque<std::pair<std::wstring,bool>>::pop_back(void)
0x180071761  lea     rcx, [rbp+310h+var_330]
0x180071765  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007176a  mov     rcx, rax; lpPathName
0x18007176d  call    cs:__imp_RemoveDirectoryW
0x180071773  test    eax, eax
0x180071775  jnz     short loc_18007178B
0x180071777  call    cs:__imp_GetLastError
0x18007177d  mov     edi, eax
0x18007177f  add     eax, 0FFFFFFFEh
0x180071782  cmp     eax, 1
0x180071785  ja      loc_180071A65
0x18007178b  lea     rcx, [rbp+310h+var_330]
0x18007178f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180071794  jmp     loc_1800716E0
0x180071799  mov     byte ptr [rbx+20h], 1
0x18007179d  mov     rcx, rbx
0x1800717a0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800717a5  mov     [rsp+410h+var_3A0], rax
0x1800717aa  lea     rax, asc_18009A80C; "*"
0x1800717b1  mov     [rsp+78h], rax
0x1800717b6  xorps   xmm0, xmm0
0x1800717b9  movups  [rbp+310h+var_350], xmm0
0x1800717bd  movdqu  [rbp+310h+var_340], xmm6
0x1800717c2  xor     eax, eax
0x1800717c4  mov     word ptr [rbp+310h+var_350], ax
0x1800717c8  lea     r8, [rbp+310h+var_350]
0x1800717cc  lea     edx, [rax+2]
0x1800717cf  lea     rcx, [rsp+410h+var_3A0]
0x1800717d4  call    ?ComposePath@NgcUtils@@YAJQEBQEBGKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::ComposePath(ushort const * const * const,ulong,std::wstring *)
0x1800717d9  mov     esi, eax
0x1800717db  test    eax, eax
0x1800717dd  js      loc_180071BE6
0x1800717e3  xor     edx, edx; Val
0x1800717e5  mov     r8d, 250h; Size
0x1800717eb  lea     rcx, [rbp+310h+FindFileData]; void *
0x1800717ef  call    memset_0
0x1800717f4  lea     rcx, [rbp+310h+var_350]
0x1800717f8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800717fd  mov     rcx, rax; lpFileName
0x180071800  mov     [rsp+410h+dwAdditionalFlags], 0; dwAdditionalFlags
0x180071808  mov     [rsp+410h+lpSearchFilter], 0; lpSearchFilter
0x180071811  xor     r9d, r9d; fSearchOp
0x180071814  lea     r8, [rbp+310h+FindFileData]; lpFindFileData
0x180071818  lea     edx, [r9+1]; fInfoLevelId
0x18007181c  call    cs:__imp_FindFirstFileExW
0x180071822  mov     [rsp+410h+var_3D8], r12
0x180071827  mov     [rsp+410h+hFindFile], rax
0x18007182c  cmp     rax, r15
0x18007182f  jnz     short loc_180071878
0x180071831  call    cs:__imp_GetLastError
0x180071837  mov     edi, eax
0x180071839  lea     ecx, [rax-2]
0x18007183c  test    ecx, 0FFFFFFEEh
0x180071842  jnz     loc_180071AA0
0x180071848  cmp     eax, 13h
0x18007184b  jz      loc_180071AA0
0x180071851  mov     [rsp+410h+var_3D8], r12
0x180071856  cmp     [rsp+410h+hFindFile], r15
0x18007185b  jz      loc_180071A5C
0x180071861  lea     rcx, [rsp+410h+var_3D8]
0x180071866  call    ?InternalClose@?$HandleT@UFindHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::InternalClose(void)
0x18007186b  test    al, al
0x18007186d  jz      loc_180071C4D
0x180071873  jmp     loc_180071A57
0x180071878  lea     rdx, [rbp+310h+var_274]
0x18007187f  lea     rcx, [rbp+310h+var_2E8]
0x180071883  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180071888  nop
0x180071889  test    [rbp+310h+FindFileData], 10h
0x18007188d  jz      loc_18007196C
0x180071893  lea     rdx, asc_18009A818; "."
0x18007189a  lea     rcx, [rbp+310h+var_2E8]
0x18007189e  call    ?_Equal@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_NQEBG@Z; std::wstring::_Equal(ushort const * const)
0x1800718a3  test    al, al
0x1800718a5  jnz     loc_1800719E5
0x1800718ab  lea     rdx, asc_18009A810; ".."
0x1800718b2  lea     rcx, [rbp+310h+var_2E8]
0x1800718b6  call    ?_Equal@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_NQEBG@Z; std::wstring::_Equal(ushort const * const)
0x1800718bb  test    al, al
0x1800718bd  jnz     loc_1800719E5
0x1800718c3  mov     rcx, rbx
0x1800718c6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800718cb  mov     [rbp+310h+var_390], rax
0x1800718cf  lea     rcx, [rbp+310h+var_2E8]
0x1800718d3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800718d8  mov     [rbp+310h+var_388], rax
0x1800718dc  xorps   xmm0, xmm0
0x1800718df  movups  [rbp+310h+var_370], xmm0
0x1800718e3  movdqu  [rbp+310h+var_360], xmm6
0x1800718e8  xor     eax, eax
0x1800718ea  mov     word ptr [rbp+310h+var_370], ax
0x1800718ee  lea     r8, [rbp+310h+var_370]
0x1800718f2  lea     edx, [rax+2]
0x1800718f5  lea     rcx, [rbp+310h+var_390]
0x1800718f9  call    ?ComposePath@NgcUtils@@YAJQEBQEBGKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::ComposePath(ushort const * const * const,ulong,std::wstring *)
0x1800718fe  mov     esi, eax
0x180071900  test    eax, eax
0x180071902  js      loc_180071B07
0x180071908  xorps   xmm0, xmm0
0x18007190b  movups  [rbp+310h+var_2C8], xmm0
0x18007190f  movzx   eax, word ptr [rbp+310h+var_370]
0x180071913  mov     word ptr [rbp+310h+var_2C8], ax
0x180071917  movsd   xmm0, qword ptr [rbp+310h+var_370+2]
0x18007191c  movsd   qword ptr [rbp+310h+var_2C8+2], xmm0
0x180071921  mov     eax, dword ptr [rbp+310h+var_370+0Ah]
0x180071924  mov     dword ptr [rbp+310h+var_2C8+0Ah], eax
0x180071927  movzx   eax, word ptr [rbp+310h+var_370+0Eh]
0x18007192b  mov     word ptr [rbp+310h+var_2C8+0Eh], ax
0x18007192f  mov     rax, qword ptr [rbp+310h+var_360]
0x180071933  mov     qword ptr [rbp+310h+var_2B8], rax
0x180071937  mov     rax, qword ptr [rbp+310h+var_360+8]
0x18007193b  mov     qword ptr [rbp+310h+var_2B8+8], rax
0x18007193f  movdqu  [rbp+310h+var_360], xmm6
0x180071944  xor     eax, eax
0x180071946  mov     word ptr [rbp+310h+var_370], ax
0x18007194a  mov     [rbp+310h+var_2A8], al
0x18007194d  lea     rdx, [rbp+310h+var_2C8]
0x180071951  lea     rcx, [rsp+410h+hFindFile+8]
0x180071956  call    ?push@?$stack@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@V?$deque@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@@2@@std@@QEAAX$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@2@@Z; std::stack<std::pair<std::wstring,bool>>::push(std::pair<std::wstring,bool> &&)
0x18007195b  nop
0x18007195c  lea     rcx, [rbp+310h+var_2C8]
0x180071960  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180071965  nop
0x180071966  lea     rcx, [rbp+310h+var_370]
0x18007196a  jmp     short loc_1800719DF
0x18007196c  mov     rcx, rbx
0x18007196f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180071974  mov     [rbp+310h+var_380], rax
0x180071978  lea     rcx, [rbp+310h+var_2E8]
0x18007197c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180071981  mov     [rbp+310h+var_378], rax
0x180071985  xorps   xmm0, xmm0
0x180071988  movups  [rbp+310h+var_308], xmm0
0x18007198c  movdqu  [rbp+310h+var_2F8], xmm6
0x180071991  xor     eax, eax
0x180071993  mov     word ptr [rbp+310h+var_308], ax
0x180071997  lea     r8, [rbp+310h+var_308]
0x18007199b  lea     edx, [rax+2]
0x18007199e  lea     rcx, [rbp+310h+var_380]
0x1800719a2  call    ?ComposePath@NgcUtils@@YAJQEBQEBGKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::ComposePath(ushort const * const * const,ulong,std::wstring *)
0x1800719a7  mov     esi, eax
0x1800719a9  test    eax, eax
0x1800719ab  js      loc_180071BB3
0x1800719b1  lea     rcx, [rbp+310h+var_308]
0x1800719b5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800719ba  mov     rcx, rax; lpFileName
0x1800719bd  call    cs:__imp_DeleteFileW
0x1800719c3  test    eax, eax
0x1800719c5  jnz     short loc_1800719DB
0x1800719c7  call    cs:__imp_GetLastError
0x1800719cd  mov     edi, eax
0x1800719cf  lea     ecx, [rax-2]
0x1800719d2  cmp     ecx, 1
0x1800719d5  ja      loc_180071B42
0x1800719db  lea     rcx, [rbp+310h+var_308]
0x1800719df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800719e4  nop
0x1800719e5  lea     rcx, [rbp+310h+var_2E8]
0x1800719e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800719ee  lea     rdx, [rbp+310h+FindFileData]; lpFindFileData
0x1800719f2  mov     rcx, [rsp+410h+hFindFile]; hFindFile
0x1800719f7  call    cs:__imp_FindNextFileW
0x1800719fd  test    eax, eax
0x1800719ff  jnz     loc_180071878
0x180071a05  call    cs:__imp_GetLastError
0x180071a0b  cmp     eax, 12h
0x180071a0e  jz      short loc_180071A39
0x180071a10  mov     rcx, cs:g_logProvider
0x180071a17  mov     edx, [rcx]
0x180071a19  cmp     edx, 3
0x180071a1c  jbe     short loc_180071A39
0x180071a1e  mov     dword ptr [rsp+410h+var_3E0], eax
0x180071a22  lea     rax, [rsp+410h+var_3E0]
0x180071a27  mov     [rsp+410h+lpSearchFilter], rax
0x180071a2c  lea     rdx, byte_1800B39B7
0x180071a33  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180071a38  nop
0x180071a39  mov     [rsp+410h+var_3D8], r12
0x180071a3e  cmp     [rsp+410h+hFindFile], r15
0x180071a43  jz      short loc_180071A5C
0x180071a45  lea     rcx, [rsp+410h+var_3D8]
0x180071a4a  call    ?InternalClose@?$HandleT@UFindHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::InternalClose(void)
0x180071a4f  test    al, al
0x180071a51  jz      loc_180071CAF
0x180071a57  mov     [rsp+410h+hFindFile], r15
0x180071a5c  lea     rcx, [rbp+310h+var_350]
0x180071a60  jmp     loc_18007178F
0x180071a65  mov     rcx, cs:g_logProvider
0x180071a6c  mov     eax, [rcx]
0x180071a6e  cmp     eax, 2
0x180071a71  jbe     short loc_180071A8D
0x180071a73  mov     dword ptr [rsp+410h+var_3E0], edi
0x180071a77  lea     rax, [rsp+410h+var_3E0]
0x180071a7c  mov     [rsp+410h+lpSearchFilter], rax
0x180071a81  lea     rdx, byte_1800B39FD
0x180071a88  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180071a8d  test    edi, edi
0x180071a8f  jle     short loc_180071A9A
0x180071a91  movzx   edi, di
0x180071a94  or      edi, 80070000h
0x180071a9a  lea     rcx, [rbp+310h+var_330]
0x180071a9e  jmp     short loc_180071AFD
0x180071aa0  mov     rcx, cs:g_logProvider
0x180071aa7  mov     eax, [rcx]
0x180071aa9  cmp     eax, 2
0x180071aac  jbe     short loc_180071AC8
0x180071aae  mov     dword ptr [rsp+410h+var_3E0], edi
0x180071ab2  lea     rax, [rsp+410h+var_3E0]
0x180071ab7  mov     [rsp+410h+lpSearchFilter], rax
0x180071abc  lea     rdx, dword_1800B3A24
0x180071ac3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180071ac8  mov     ebx, 80070000h
0x180071acd  test    edi, edi
0x180071acf  jle     short loc_180071AD6
0x180071ad1  movzx   edi, di
0x180071ad4  or      edi, ebx
0x180071ad6  mov     [rsp+410h+var_3D8], r12
0x180071adb  cmp     [rsp+410h+hFindFile], r15
0x180071ae0  jz      short loc_180071AF9
0x180071ae2  lea     rcx, [rsp+410h+var_3D8]
0x180071ae7  call    ?InternalClose@?$HandleT@UFindHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<FindHandleTraits>::InternalClose(void)
  ... truncated ...
```
