# CWorkspace::SaveResourceMapRegistry(HKEY__ *,void *,int)

- ea: `0x180036234`
- end: `0x180036c96`
- name: `?SaveResourceMapRegistry@CWorkspace@@QEAAJPEAUHKEY__@@PEAXH@Z`
- size: `2658`
- prototype: `int(CWorkspace *__hidden this, HKEY, void *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x180034ffc`

## callees

- `0x18000224c`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001ead4`
- `0x180020a68`
- `0x180028ca0`
- `0x180028d04`
- `0x180036234`
- `0x18003add8`
- `0x1800772ec`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800369a5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180036c51`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800369a5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180036c51`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x1800363db`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x18003650f`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x1800363db`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x18003650f`
- `ADVAPI32!RegCloseKey` at `0x180036c09`
- `ADVAPI32!RegCloseKey` at `0x180036c61`
- `ADVAPI32!RegCloseKey` at `0x180036c74`
- `ADVAPI32!RegCloseKey` at `0x180036c09`
- `ADVAPI32!RegCloseKey` at `0x180036c61`
- `ADVAPI32!RegCloseKey` at `0x180036c74`
- `ADVAPI32!RegSetValueExW` at `0x1800365af`
- `ADVAPI32!RegSetValueExW` at `0x180036663`
- `ADVAPI32!RegSetValueExW` at `0x180036717`
- `ADVAPI32!RegSetValueExW` at `0x1800367d1`
- `ADVAPI32!RegSetValueExW` at `0x180036888`
- `ADVAPI32!RegSetValueExW` at `0x180036aa4`
- `ADVAPI32!RegSetValueExW` at `0x180036b44`
- `ADVAPI32!RegSetValueExW` at `0x1800365af`
- `ADVAPI32!RegSetValueExW` at `0x180036663`
- `ADVAPI32!RegSetValueExW` at `0x180036717`
- `ADVAPI32!RegSetValueExW` at `0x1800367d1`
- `ADVAPI32!RegSetValueExW` at `0x180036888`
- `ADVAPI32!RegSetValueExW` at `0x180036aa4`
- `ADVAPI32!RegSetValueExW` at `0x180036b44`
- `KERNEL32!RegDeleteTreeW` at `0x180036308`
- `KERNEL32!RegDeleteTreeW` at `0x180036308`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CWorkspace::SaveResourceMapRegistry(CWorkspace *this, HKEY a2, void *a3, int a4)
{
  unsigned int v6; // r13d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  void *v8; // r12
  int v9; // ebx
  unsigned int v10; // r14d
  unsigned int v11; // eax
  unsigned int v12; // r14d
  unsigned int v13; // eax
  char *v14; // r8
  __int64 v15; // rax
  __int64 v16; // r14
  const WCHAR *v17; // rax
  unsigned int v18; // r14d
  unsigned int v19; // eax
  unsigned int v20; // r14d
  unsigned int v21; // eax
  int v22; // ebx
  const BYTE *v23; // rax
  unsigned int v24; // r14d
  unsigned int v25; // eax
  int v26; // ebx
  const BYTE *v27; // rax
  unsigned int v28; // r14d
  unsigned int v29; // eax
  int v30; // ebx
  const BYTE *v31; // rax
  unsigned int v32; // r14d
  unsigned int v33; // eax
  int v34; // ebx
  const BYTE *v35; // rax
  unsigned int v36; // r14d
  unsigned int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // r8
  _QWORD *v40; // rax
  int v41; // r10d
  unsigned int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // r8
  _QWORD *v45; // rax
  int v46; // r10d
  unsigned int v47; // eax
  unsigned int v48; // r14d
  unsigned int v49; // eax
  const BYTE *v50; // r14
  unsigned int v51; // r14d
  unsigned int v52; // eax
  int v53; // ebx
  unsigned int v54; // eax
  __int64 samDesired; // [rsp+28h] [rbp-F0h]
  unsigned int v57; // [rsp+64h] [rbp-B4h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-B0h] BYREF
  void *v59; // [rsp+70h] [rbp-A8h]
  DWORD dwDisposition; // [rsp+78h] [rbp-A0h] BYREF
  _BYTE v61[8]; // [rsp+80h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-90h] BYREF
  unsigned int v63; // [rsp+90h] [rbp-88h]
  char *v64; // [rsp+98h] [rbp-80h]
  __int64 v65; // [rsp+A0h] [rbp-78h]
  _BYTE v66[8]; // [rsp+A8h] [rbp-70h] BYREF
  __int64 v67; // [rsp+B0h] [rbp-68h]
  __int64 v68; // [rsp+B8h] [rbp-60h]
  __int64 v69; // [rsp+C0h] [rbp-58h]
  __int64 v70; // [rsp+C8h] [rbp-50h]
  _BYTE v71[8]; // [rsp+D0h] [rbp-48h] BYREF
  _BYTE v72[8]; // [rsp+D8h] [rbp-40h] BYREF
  _BYTE v73[8]; // [rsp+E0h] [rbp-38h] BYREF
  _BYTE v74[8]; // [rsp+E8h] [rbp-30h] BYREF
  _BYTE v75[16]; // [rsp+F0h] [rbp-28h] BYREF

  v65 = -2;
  v59 = 0;
  v6 = 780;
  v57 = 0;
  hKey = 0;
  phkResult = 0;
  dwDisposition = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      209,
      WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  v8 = operator new[](0x618u);
  v59 = v8;
  if ( a4 && (v9 = RegDeleteTreeW(a2, L"ResourceMap"), (v9 & 0xFFFFFFFD) != 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      else
        v10 = v9;
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v11, v10);
    }
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
  }
  else
  {
    v9 = RegCreateKeyTransactedW(a2, L"ResourceMap", 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition, a3, 0);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( v9 > 0 )
          v12 = (unsigned __int16)v9 | 0x80070000;
        else
          v12 = v9;
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 211, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v13, v12);
      }
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
    }
    else
    {
      v64 = (char *)this + 872;
      std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::begin(
        (char *)this + 872,
        v61,
        (char *)this + 872);
      while ( 1 )
      {
        v15 = std::vector<unsigned int>::begin(v14, v66);
        if ( !(unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(
                                 v61,
                                 v15) )
        {
          v9 = 0;
          goto LABEL_135;
        }
        v16 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(v61);
        v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
        v9 = RegCreateKeyTransactedW(hKey, v17, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0, a3, 0);
        if ( v9 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v9 > 0 )
              v18 = (unsigned __int16)v9 | 0x80070000;
            else
              v18 = v9;
            v19 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              212,
              WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v19,
              v18);
          }
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
          goto LABEL_135;
        }
        v9 = RegSetValueExW(phkResult, L"IsRDP", 0, 4u, (const BYTE *)(v16 + 32), 4u);
        if ( v9 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v9 > 0 )
              v20 = (unsigned __int16)v9 | 0x80070000;
            else
              v20 = v9;
            v21 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              213,
              WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v21,
              v20);
          }
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
          goto LABEL_135;
        }
        v67 = *(_QWORD *)(v16 + 64);
        v22 = v67;
        v23 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16 + 48);
        v9 = RegSetValueExW(phkResult, L"ResourceFileExt", 0, 1u, v23, 2 * v22 + 2);
        if ( v9 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v9 > 0 )
              v24 = (unsigned __int16)v9 | 0x80070000;
            else
              v24 = v9;
            v25 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              214,
              WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v25,
              v24);
          }
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
          goto LABEL_135;
        }
        v68 = *(_QWORD *)(v16 + 96);
        v26 = v68;
        v27 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16 + 80);
        v9 = RegSetValueExW(phkResult, L"ResourceFile", 0, 1u, v27, 2 * v26 + 2);
        if ( v9 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v9 > 0 )
              v28 = (unsigned __int16)v9 | 0x80070000;
            else
              v28 = v9;
            v29 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              215,
              WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v29,
              v28);
          }
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
          goto LABEL_135;
        }
        v69 = *(_QWORD *)(v16 + 160);
        v30 = v69;
        v31 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16 + 144);
        v9 = RegSetValueExW(phkResult, L"Alias", 0, 1u, v31, 2 * v30 + 2);
        if ( v9 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v9 > 0 )
              v32 = (unsigned __int16)v9 | 0x80070000;
            else
              v32 = v9;
            v33 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              216,
              WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v33,
              v32);
          }
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
          goto LABEL_135;
        }
        v70 = *(_QWORD *)(v16 + 128);
        v34 = v70;
        v35 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16 + 112);
        v9 = RegSetValueExW(phkResult, L"IconFile", 0, 1u, v35, 2 * v34 + 2);
        if ( v9 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v9 > 0 )
              v36 = (unsigned __int16)v9 | 0x80070000;
            else
              v36 = v9;
            v37 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              217,
              WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v37,
              v36);
          }
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
          goto LABEL_135;
        }
        std::vector<unsigned int>::begin(v16 + 176, v71);
        v40 = (_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::begin(
                          v38,
                          v72,
                          v39);
        v9 = StringsToMultiSz<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>>(
               *v40,
               v41,
               (_DWORD)v8,
               v6,
               (__int64)&v57);
        if ( v9 == -2147024774 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          {
            v6 = v57;
          }
          else
          {
            v42 = RdpWppGetCurrentThreadActivityIdPrefix();
            v6 = v57;
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              218,
              WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v42,
              v57);
          }
          operator delete[](v8);
          v59 = 0;
          v8 = operator new[](saturated_mul(v6, 2u));
          v59 = v8;
          v63 = v6;
          std::vector<unsigned int>::begin(v16 + 176, v73);
          v45 = (_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::begin(
                            v43,
                            v74,
                            v44);
          v9 = StringsToMultiSz<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>>(
                 *v45,
                 v46,
                 (_DWORD)v8,
                 v6,
                 (__int64)&v57);
        }
        if ( v9 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v47 = RdpWppGetCurrentThreadActivityIdPrefix();
            LODWORD(samDesired) = v9;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              219,
              (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v47,
              (__int64)"StringsToMultiSz failed",
              samDesired);
          }
          goto LABEL_135;
        }
        v9 = RegSetValueExW(phkResult, L"Folders", 0, 7u, (const BYTE *)v8, 2 * v57);
        if ( v9 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v9 > 0 )
              v48 = (unsigned __int16)v9 | 0x80070000;
            else
              v48 = v9;
            v49 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              220,
              WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v49,
              v48);
          }
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
          goto LABEL_135;
        }
        v50 = (const BYTE *)(v16 + 36);
        v9 = RegSetValueExW(phkResult, L"ShowByDefault", 0, 4u, v50, 4u);
        if ( v9 )
          break;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v53 = *(_DWORD *)v50;
          v54 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v54, v53);
        }
        RegCloseKey(phkResult);
        phkResult = 0;
        std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,TS_WORKSPACE_DOWNLOAD_INFO>>>>::operator++(
          v61,
          v75);
        v14 = v64;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( v9 > 0 )
          v51 = (unsigned __int16)v9 | 0x80070000;
        else
          v51 = v9;
        v52 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 221, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v52, v51);
      }
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
    }
  }
LABEL_135:
  if ( v8 )
    operator delete[](v8);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180036234  mov     rax, rsp
0x180036237  mov     [rax+18h], r8
0x18003623b  mov     [rax+8], rcx
0x18003623f  push    r12
0x180036241  push    r13
0x180036243  push    r14
0x180036245  sub     rsp, 100h
0x18003624c  mov     qword ptr [rax-78h], 0FFFFFFFFFFFFFFFEh
0x180036254  mov     [rax+10h], rbx
0x180036258  mov     [rax+20h], rsi
0x18003625c  mov     ebx, r9d
0x18003625f  mov     r14, rdx
0x180036262  mov     [rsp+118h+var_A8], 0
0x18003626b  mov     r13d, 30Ch
0x180036271  mov     [rsp+118h+var_B4], 0
0x180036279  mov     qword ptr [rax-90h], 0
0x180036284  mov     [rsp+118h+var_B0], 0
0x18003628d  mov     [rsp+118h+dwDisposition], 0
0x180036295  lea     rcx, WPP_GLOBAL_Control
0x18003629c  mov     rax, cs:WPP_GLOBAL_Control
0x1800362a3  cmp     rax, rcx
0x1800362a6  jz      short loc_1800362DD
0x1800362a8  test    byte ptr [rax+1Ch], 1
0x1800362ac  jz      short loc_1800362DD
0x1800362ae  cmp     byte ptr [rax+19h], 4
0x1800362b2  jb      short loc_1800362DD
0x1800362b4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800362b9  mov     edx, 0D1h
0x1800362be  mov     r9d, eax
0x1800362c1  lea     rsi, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800362c8  mov     r8, rsi
0x1800362cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362d2  mov     rcx, [rcx+10h]
0x1800362d6  call    WPP_SF_D
0x1800362db  jmp     short loc_1800362E4
0x1800362dd  lea     rsi, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800362e4  mov     ecx, 618h; unsigned __int64
0x1800362e9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800362ee  mov     r12, rax
0x1800362f1  mov     [rsp+118h+var_A8], rax
0x1800362f6  test    ebx, ebx
0x1800362f8  jz      loc_180036385
0x1800362fe  lea     rdx, aResourcemap; "ResourceMap"
0x180036305  mov     rcx, r14; hKey
0x180036308  call    cs:__imp_RegDeleteTreeW
0x18003630e  mov     ebx, eax
0x180036310  test    eax, 0FFFFFFFDh
0x180036315  jz      short loc_180036385
0x180036317  mov     rax, cs:WPP_GLOBAL_Control
0x18003631e  lea     rcx, WPP_GLOBAL_Control
0x180036325  cmp     rax, rcx
0x180036328  jz      short loc_18003636F
0x18003632a  test    byte ptr [rax+1Ch], 8
0x18003632e  jz      short loc_18003636F
0x180036330  cmp     byte ptr [rax+19h], 2
0x180036334  jb      short loc_18003636F
0x180036336  test    ebx, ebx
0x180036338  jg      short loc_18003633F
0x18003633a  mov     r14d, ebx
0x18003633d  jmp     short loc_18003634A
0x18003633f  movzx   r14d, bx
0x180036343  or      r14d, 80070000h
0x18003634a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003634f  mov     edx, 0D2h
0x180036354  mov     [rsp+118h+dwOptions], r14d
0x180036359  mov     r9d, eax
0x18003635c  mov     r8, rsi
0x18003635f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036366  mov     rcx, [rcx+10h]
0x18003636a  call    WPP_SF_Dd
0x18003636f  test    ebx, ebx
0x180036371  jle     short loc_18003637C
0x180036373  movzx   ebx, bx
0x180036376  or      ebx, 80070000h
0x18003637c  mov     [rsp+118h+var_B8], ebx
0x180036380  jmp     loc_180036C49
0x180036385  mov     [rsp+118h+pExtendedParemeter], 0; pExtendedParemeter
0x18003638e  mov     rax, [rsp+118h+arg_10]
0x180036396  mov     [rsp+118h+hTransaction], rax; hTransaction
0x18003639b  lea     rax, [rsp+118h+dwDisposition]
0x1800363a0  mov     [rsp+118h+lpdwDisposition], rax; lpdwDisposition
0x1800363a5  lea     rax, [rsp+118h+hKey]
0x1800363ad  mov     [rsp+118h+phkResult], rax; phkResult
0x1800363b2  mov     [rsp+118h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800363bb  mov     dword ptr [rsp+118h+samDesired], 2001Fh; samDesired
0x1800363c3  mov     [rsp+118h+dwOptions], 0; dwOptions
0x1800363cb  xor     r9d, r9d; lpClass
0x1800363ce  xor     r8d, r8d; Reserved
0x1800363d1  lea     rdx, aResourcemap; "ResourceMap"
0x1800363d8  mov     rcx, r14; hKey
0x1800363db  call    cs:__imp_RegCreateKeyTransactedW
0x1800363e1  mov     ebx, eax
0x1800363e3  test    eax, eax
0x1800363e5  jz      short loc_180036455
0x1800363e7  mov     rax, cs:WPP_GLOBAL_Control
0x1800363ee  lea     rcx, WPP_GLOBAL_Control
0x1800363f5  cmp     rax, rcx
0x1800363f8  jz      short loc_18003643F
0x1800363fa  test    byte ptr [rax+1Ch], 8
0x1800363fe  jz      short loc_18003643F
0x180036400  cmp     byte ptr [rax+19h], 2
0x180036404  jb      short loc_18003643F
0x180036406  test    ebx, ebx
0x180036408  jg      short loc_18003640F
0x18003640a  mov     r14d, ebx
0x18003640d  jmp     short loc_18003641A
0x18003640f  movzx   r14d, bx
0x180036413  or      r14d, 80070000h
0x18003641a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003641f  mov     edx, 0D3h
0x180036424  mov     [rsp+118h+dwOptions], r14d
0x180036429  mov     r9d, eax
0x18003642c  mov     r8, rsi
0x18003642f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036436  mov     rcx, [rcx+10h]
0x18003643a  call    WPP_SF_Dd
0x18003643f  test    ebx, ebx
0x180036441  jle     short loc_18003644C
0x180036443  movzx   ebx, bx
0x180036446  or      ebx, 80070000h
0x18003644c  mov     [rsp+118h+var_B8], ebx
0x180036450  jmp     loc_180036C49
0x180036455  mov     r8, [rsp+118h+arg_0]
0x18003645d  add     r8, 368h
0x180036464  mov     [rsp+118h+var_80], r8
0x18003646c  lea     rdx, [rsp+118h+var_98]
0x180036474  mov     rcx, r8
0x180036477  call    ?begin@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::begin(void)
0x18003647c  lea     rdx, [rsp+118h+var_70]
0x180036484  mov     rcx, r8
0x180036487  call    ?begin@?$vector@IV?$allocator@_N@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@2@XZ; std::vector<uint>::begin(void)
0x18003648c  mov     rdx, rax
0x18003648f  lea     rcx, [rsp+118h+var_98]
0x180036497  call    ??9?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>> const &)
0x18003649c  test    al, al
0x18003649e  jz      loc_180036C3A
0x1800364a4  lea     rcx, [rsp+118h+var_98]
0x1800364ac  call    ??C?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEBAPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(void)
0x1800364b1  mov     r14, rax
0x1800364b4  mov     rcx, rax
0x1800364b7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800364bc  mov     [rsp+118h+pExtendedParemeter], 0; pExtendedParemeter
0x1800364c5  mov     rcx, [rsp+118h+arg_10]
0x1800364cd  mov     [rsp+118h+hTransaction], rcx; hTransaction
0x1800364d2  mov     [rsp+118h+lpdwDisposition], 0; lpdwDisposition
0x1800364db  lea     rcx, [rsp+118h+var_B0]
0x1800364e0  mov     [rsp+118h+phkResult], rcx; phkResult
0x1800364e5  mov     [rsp+118h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800364ee  mov     dword ptr [rsp+118h+samDesired], 2001Fh; samDesired
0x1800364f6  mov     [rsp+118h+dwOptions], 0; dwOptions
0x1800364fe  xor     r9d, r9d; lpClass
0x180036501  xor     r8d, r8d; Reserved
0x180036504  mov     rdx, rax; lpSubKey
0x180036507  mov     rcx, [rsp+118h+hKey]; hKey
0x18003650f  call    cs:__imp_RegCreateKeyTransactedW
0x180036515  mov     ebx, eax
0x180036517  test    eax, eax
0x180036519  jz      short loc_180036589
0x18003651b  mov     rax, cs:WPP_GLOBAL_Control
0x180036522  lea     rcx, WPP_GLOBAL_Control
0x180036529  cmp     rax, rcx
0x18003652c  jz      short loc_180036573
0x18003652e  test    byte ptr [rax+1Ch], 8
0x180036532  jz      short loc_180036573
0x180036534  cmp     byte ptr [rax+19h], 2
0x180036538  jb      short loc_180036573
0x18003653a  test    ebx, ebx
0x18003653c  jg      short loc_180036543
0x18003653e  mov     r14d, ebx
0x180036541  jmp     short loc_18003654E
0x180036543  movzx   r14d, bx
0x180036547  or      r14d, 80070000h
0x18003654e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180036553  mov     edx, 0D4h
0x180036558  mov     [rsp+118h+dwOptions], r14d
0x18003655d  mov     r9d, eax
0x180036560  mov     r8, rsi
0x180036563  mov     rcx, cs:WPP_GLOBAL_Control
0x18003656a  mov     rcx, [rcx+10h]
0x18003656e  call    WPP_SF_Dd
0x180036573  test    ebx, ebx
0x180036575  jle     short loc_180036580
0x180036577  movzx   ebx, bx
0x18003657a  or      ebx, 80070000h
0x180036580  mov     [rsp+118h+var_B8], ebx
0x180036584  jmp     loc_180036C49
0x180036589  lea     rax, [r14+20h]
0x18003658d  mov     dword ptr [rsp+118h+samDesired], 4; cbData
0x180036595  mov     qword ptr [rsp+118h+dwOptions], rax; lpData
0x18003659a  mov     r9d, 4; dwType
0x1800365a0  xor     r8d, r8d; Reserved
0x1800365a3  lea     rdx, ValueName; "IsRDP"
0x1800365aa  mov     rcx, [rsp+118h+var_B0]; hKey
0x1800365af  call    cs:__imp_RegSetValueExW
0x1800365b5  mov     ebx, eax
0x1800365b7  test    eax, eax
0x1800365b9  jz      short loc_180036629
0x1800365bb  mov     rax, cs:WPP_GLOBAL_Control
0x1800365c2  lea     rcx, WPP_GLOBAL_Control
0x1800365c9  cmp     rax, rcx
0x1800365cc  jz      short loc_180036613
0x1800365ce  test    byte ptr [rax+1Ch], 8
0x1800365d2  jz      short loc_180036613
0x1800365d4  cmp     byte ptr [rax+19h], 2
0x1800365d8  jb      short loc_180036613
0x1800365da  test    ebx, ebx
0x1800365dc  jg      short loc_1800365E3
0x1800365de  mov     r14d, ebx
0x1800365e1  jmp     short loc_1800365EE
0x1800365e3  movzx   r14d, bx
0x1800365e7  or      r14d, 80070000h
0x1800365ee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800365f3  mov     edx, 0D5h
0x1800365f8  mov     [rsp+118h+dwOptions], r14d
0x1800365fd  mov     r9d, eax
0x180036600  mov     r8, rsi
0x180036603  mov     rcx, cs:WPP_GLOBAL_Control
0x18003660a  mov     rcx, [rcx+10h]
0x18003660e  call    WPP_SF_Dd
0x180036613  test    ebx, ebx
0x180036615  jle     short loc_180036620
0x180036617  movzx   ebx, bx
0x18003661a  or      ebx, 80070000h
0x180036620  mov     [rsp+118h+var_B8], ebx
0x180036624  jmp     loc_180036C49
0x180036629  mov     rbx, [r14+40h]
0x18003662d  mov     [rsp+118h+var_68], rbx
0x180036635  lea     rcx, [r14+30h]
0x180036639  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003663e  lea     edx, ds:2[rbx*2]
0x180036645  mov     dword ptr [rsp+118h+samDesired], edx; cbData
0x180036649  mov     qword ptr [rsp+118h+dwOptions], rax; lpData
0x18003664e  mov     r9d, 1; dwType
0x180036654  xor     r8d, r8d; Reserved
0x180036657  lea     rdx, aResourcefileex; "ResourceFileExt"
0x18003665e  mov     rcx, [rsp+118h+var_B0]; hKey
0x180036663  call    cs:__imp_RegSetValueExW
0x180036669  mov     ebx, eax
0x18003666b  test    eax, eax
0x18003666d  jz      short loc_1800366DD
0x18003666f  mov     rax, cs:WPP_GLOBAL_Control
0x180036676  lea     rcx, WPP_GLOBAL_Control
0x18003667d  cmp     rax, rcx
0x180036680  jz      short loc_1800366C7
0x180036682  test    byte ptr [rax+1Ch], 8
0x180036686  jz      short loc_1800366C7
0x180036688  cmp     byte ptr [rax+19h], 2
0x18003668c  jb      short loc_1800366C7
0x18003668e  test    ebx, ebx
0x180036690  jg      short loc_180036697
0x180036692  mov     r14d, ebx
0x180036695  jmp     short loc_1800366A2
0x180036697  movzx   r14d, bx
0x18003669b  or      r14d, 80070000h
0x1800366a2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800366a7  mov     edx, 0D6h
0x1800366ac  mov     [rsp+118h+dwOptions], r14d
0x1800366b1  mov     r9d, eax
0x1800366b4  mov     r8, rsi
0x1800366b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800366be  mov     rcx, [rcx+10h]
0x1800366c2  call    WPP_SF_Dd
0x1800366c7  test    ebx, ebx
0x1800366c9  jle     short loc_1800366D4
0x1800366cb  movzx   ebx, bx
0x1800366ce  or      ebx, 80070000h
0x1800366d4  mov     [rsp+118h+var_B8], ebx
0x1800366d8  jmp     loc_180036C49
0x1800366dd  mov     rbx, [r14+60h]
0x1800366e1  mov     [rsp+118h+var_60], rbx
0x1800366e9  lea     rcx, [r14+50h]
0x1800366ed  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800366f2  lea     edx, ds:2[rbx*2]
0x1800366f9  mov     dword ptr [rsp+118h+samDesired], edx; cbData
0x1800366fd  mov     qword ptr [rsp+118h+dwOptions], rax; lpData
0x180036702  mov     r9d, 1; dwType
0x180036708  xor     r8d, r8d; Reserved
0x18003670b  lea     rdx, aResourcefile; "ResourceFile"
0x180036712  mov     rcx, [rsp+118h+var_B0]; hKey
0x180036717  call    cs:__imp_RegSetValueExW
0x18003671d  mov     ebx, eax
0x18003671f  test    eax, eax
0x180036721  jz      short loc_180036791
0x180036723  mov     rax, cs:WPP_GLOBAL_Control
0x18003672a  lea     rcx, WPP_GLOBAL_Control
0x180036731  cmp     rax, rcx
0x180036734  jz      short loc_18003677B
0x180036736  test    byte ptr [rax+1Ch], 8
0x18003673a  jz      short loc_18003677B
0x18003673c  cmp     byte ptr [rax+19h], 2
0x180036740  jb      short loc_18003677B
0x180036742  test    ebx, ebx
0x180036744  jg      short loc_18003674B
0x180036746  mov     r14d, ebx
0x180036749  jmp     short loc_180036756
0x18003674b  movzx   r14d, bx
0x18003674f  or      r14d, 80070000h
0x180036756  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003675b  mov     edx, 0D7h
0x180036760  mov     [rsp+118h+dwOptions], r14d
  ... truncated ...
```
