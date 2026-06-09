# ConnectedStorage::EnumerateContextsOnDiskForXuid__lambda_46e1c9d127f72b8258e862530f406faa___

- ea: `0x18002f6b8`
- end: `0x18002f918`
- name: `ConnectedStorage::EnumerateContextsOnDiskForXuid__lambda_46e1c9d127f72b8258e862530f406faa___`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x180033d80`

## callees

- `0x180003c70`
- `0x180004754`
- `0x18000aae4`
- `0x18000ab18`
- `0x18000b67c`
- `0x1800125ec`
- `0x18001b9c8`
- `0x18001c090`
- `0x18001c63c`
- `0x18001ff28`
- `0x180020898`
- `0x1800270e8`
- `0x18002f6b8`
- `0x180030854`
- `0x180032674`
- `0x180033394`
- `0x1800333e8`
- `0x1800365b4`
- `0x1800510a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18002f708`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18002f708`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f8ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f8ee`

## string_xrefs

- `0x18002f758`: `StringCchPrintfW(rootDirectory, _countof(rootDirectory), c_SearchFormat, root.c_str(), xuidData)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HRESULT __fastcall ConnectedStorage::EnumerateContextsOnDiskForXuid__lambda_46e1c9d127f72b8258e862530f406faa___(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  int v5; // eax
  const unsigned __int16 *v6; // r8
  const unsigned __int16 *v7; // r8
  int v8; // edx
  int v9; // edx
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // r8
  __int64 v13; // rax
  signed int Next; // eax
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v18[8]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v19[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+70h] [rbp-90h]
  char v22; // [rsp+74h] [rbp-8Ch]
  _BYTE v23[8]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v24[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[8]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v26[32]; // [rsp+90h] [rbp-70h] BYREF
  _WIN32_FIND_DATAW v27; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v28[16]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v29[264]; // [rsp+320h] [rbp+220h] BYREF

  *(_OWORD *)v28 = *(_OWORD *)L"%s\\%016I64X*";
  *(_OWORD *)&v28[5] = *(_OWORD *)L"16I64X*";
  v3 = _o__wcstoui64(a1, 0, 10);
  v17 = 0;
  ConnectedStorage::LocalStorage::GetUserContextRoot((__int64)v26, 0, &v17);
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
  v5 = StringCchPrintfW(v29, 0x104u, v28, v4, v3);
  if ( v5 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v5,
      (int)L"StringCchPrintfW(rootDirectory, _countof(rootDirectory), c_SearchFormat, root.c_str(), xuidData)",
      v6);
  v16 = -1;
  memset_0(&v27, 0, sizeof(v27));
  if ( ConnectedStorage::FindFile::FindFirst((ConnectedStorage::FindFile *)&v16, v29, &v27) - 2 > 1 )
  {
    do
    {
      if ( (v27.dwFileAttributes & 0x10) != 0 )
      {
        v8 = v27.cFileName[0] - 46;
        if ( v27.cFileName[0] == 46 )
          v8 = v27.cFileName[1];
        if ( v8 )
        {
          v9 = v27.cFileName[0] - 46;
          if ( v27.cFileName[0] == 46 )
          {
            v9 = v27.cFileName[1] - 46;
            if ( v27.cFileName[1] == 46 )
              v9 = v27.cFileName[2];
          }
          if ( v9 )
          {
            memset(v19, 0, sizeof(v19));
            v20 = 0;
            v21 = 0;
            v22 = 1;
            if ( ConnectedStorage::ContextDesc::TryGetContextDescFromDirectoryName(v27.cFileName, (HSTRING *)v19, v7) )
            {
              std::vector<ConnectedStorage::BlobRecord>::end(*a2, v23);
              v11 = (_QWORD *)std::vector<ConnectedStorage::ContextDesc>::begin(v10, v24);
              std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ConnectedStorage::ContextDesc>>>,ConnectedStorage::ContextDesc>(
                v18,
                *v11,
                v12,
                v19);
              v13 = std::vector<ConnectedStorage::BlobRecord>::end(*a2, v25);
              if ( (unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<ConnectedStorage::Container>>>>>::operator==(
                                      v18,
                                      v13) )
                std::vector<ConnectedStorage::ContextDesc>::push_back(a2[1], v19);
            }
            ConnectedStorage::ContextDesc::~ContextDesc((HSTRING *)v19);
          }
        }
      }
      Next = ConnectedStorage::FindFile::FindNext((ConnectedStorage::FindFile *)&v16, &v27);
    }
    while ( !Next );
    if ( Next != 18 )
    {
      if ( Next > 0 )
        Next = (unsigned __int16)Next | 0x80070000;
      ConnectedStorage::ReportErrorNoThrow(
        (ConnectedStorage *)(unsigned int)Next,
        (int)L"EnumerateContextsOnDiskForXuid",
        (const unsigned __int16 *)0x80070000LL);
    }
  }
  ConnectedStorage::FindFile::Close((ConnectedStorage::FindFile *)&v16);
  std::wstring::_Tidy_deallocate(v26);
  return WindowsDeleteString(0);
}

```

## disassembly

```asm
0x18002f6b8  mov     [rsp-8+arg_10], rbx
0x18002f6bd  mov     [rsp-8+arg_18], rdi
0x18002f6c2  push    rbp
0x18002f6c3  lea     rbp, [rsp-440h]
0x18002f6cb  sub     rsp, 540h
0x18002f6d2  mov     rax, cs:__security_cookie
0x18002f6d9  xor     rax, rsp
0x18002f6dc  mov     [rbp+440h+var_10], rax
0x18002f6e3  mov     rdi, rdx
0x18002f6e6  movups  xmm0, xmmword ptr cs:aS016i64x; "%s\\%016I64X*"
0x18002f6ed  movups  xmmword ptr [rbp+440h+var_240], xmm0
0x18002f6f4  movups  xmm1, xmmword ptr cs:aS016i64x+0Ah; "16I64X*"
0x18002f6fb  movups  xmmword ptr [rbp+440h+var_240+0Ah], xmm1
0x18002f702  xor     edx, edx
0x18002f704  lea     r8d, [rdx+0Ah]
0x18002f708  call    cs:__imp__o__wcstoui64
0x18002f70e  mov     rbx, rax
0x18002f711  mov     [rsp+540h+var_508], 0
0x18002f71a  lea     r8, [rsp+540h+var_508]
0x18002f71f  xor     edx, edx
0x18002f721  lea     rcx, [rbp+440h+var_4B0]
0x18002f725  call    ?GetUserContextRoot@LocalStorage@ConnectedStorage@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KAEBVSimpleHStringWrapper@2@@Z; ConnectedStorage::LocalStorage::GetUserContextRoot(unsigned __int64,ConnectedStorage::SimpleHStringWrapper const &)
0x18002f72a  nop
0x18002f72b  lea     rcx, [rbp+440h+var_4B0]
0x18002f72f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f734  mov     r9, rax
0x18002f737  mov     [rsp+540h+var_520], rbx
0x18002f73c  lea     r8, [rbp+440h+var_240]; unsigned __int16 *
0x18002f743  mov     edx, 104h; unsigned __int64
0x18002f748  lea     rcx, [rbp+440h+var_220]; unsigned __int16 *
0x18002f74f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f754  test    eax, eax
0x18002f756  jns     short loc_18002F767
0x18002f758  lea     rdx, aStringcchprint; "StringCchPrintfW(rootDirectory, _counto"...
0x18002f75f  mov     ecx, eax; this
0x18002f761  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002f767  mov     [rsp+540h+var_510], 0FFFFFFFFFFFFFFFFh
0x18002f770  xor     edx, edx; Val
0x18002f772  mov     r8d, 250h; Size
0x18002f778  lea     rcx, [rbp+440h+var_490]; void *
0x18002f77c  call    memset_0
0x18002f781  lea     r8, [rbp+440h+var_490]; struct _WIN32_FIND_DATAW *
0x18002f785  lea     rdx, [rbp+440h+var_220]; unsigned __int16 *
0x18002f78c  lea     rcx, [rsp+540h+var_510]; this
0x18002f791  call    ?FindFirst@FindFile@ConnectedStorage@@QEAAKPEBGPEAU_WIN32_FIND_DATAW@@@Z; ConnectedStorage::FindFile::FindFirst(ushort const *,_WIN32_FIND_DATAW *)
0x18002f796  add     eax, 0FFFFFFFEh
0x18002f799  cmp     eax, 1
0x18002f79c  jbe     loc_18002F8D7
0x18002f7a2  mov     ebx, 2Eh ; '.'
0x18002f7a7  test    byte ptr [rbp+440h+var_490.dwFileAttributes], 10h
0x18002f7ab  jz      loc_18002F88A
0x18002f7b1  movzx   edx, [rbp+440h+var_490.cFileName]
0x18002f7b5  sub     edx, ebx
0x18002f7b7  jnz     short loc_18002F7C4
0x18002f7b9  movzx   edx, [rbp+440h+var_490.cFileName+2]
0x18002f7bd  xor     eax, eax
0x18002f7bf  movzx   ecx, ax
0x18002f7c2  sub     edx, ecx
0x18002f7c4  test    edx, edx
0x18002f7c6  jz      loc_18002F88A
0x18002f7cc  movzx   edx, [rbp+440h+var_490.cFileName]
0x18002f7d0  sub     edx, ebx
0x18002f7d2  jnz     short loc_18002F7E7
0x18002f7d4  movzx   edx, [rbp+440h+var_490.cFileName+2]
0x18002f7d8  sub     edx, ebx
0x18002f7da  jnz     short loc_18002F7E7
0x18002f7dc  movzx   edx, [rbp+440h+var_490.cFileName+4]
0x18002f7e0  xor     eax, eax
0x18002f7e2  movzx   ecx, ax
0x18002f7e5  sub     edx, ecx
0x18002f7e7  test    edx, edx
0x18002f7e9  jz      loc_18002F88A
0x18002f7ef  xorps   xmm0, xmm0
0x18002f7f2  movdqu  [rsp+540h+var_4F8], xmm0
0x18002f7f8  xorps   xmm1, xmm1
0x18002f7fb  movdqu  [rsp+540h+var_4E8], xmm1
0x18002f801  mov     [rsp+540h+var_4D8], 0
0x18002f80a  mov     [rsp+540h+var_4D0], 0
0x18002f812  mov     [rsp+540h+var_4CC], 1
0x18002f817  lea     rdx, [rsp+540h+var_4F8]; struct ConnectedStorage::ContextDesc *
0x18002f81c  lea     rcx, [rbp+440h+var_490.cFileName]; unsigned __int16 *
0x18002f820  call    ?TryGetContextDescFromDirectoryName@ContextDesc@ConnectedStorage@@SA_NPEAGPEAV12@@Z; ConnectedStorage::ContextDesc::TryGetContextDescFromDirectoryName(ushort *,ConnectedStorage::ContextDesc *)
0x18002f825  test    al, al
0x18002f827  jz      short loc_18002F880
0x18002f829  lea     rdx, [rsp+540h+var_4C8]
0x18002f82e  mov     rcx, [rdi]
0x18002f831  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002f836  mov     r8, [rax]
0x18002f839  lea     rdx, [rbp+440h+var_4C0]
0x18002f83d  call    ?begin@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::ContextDesc>::begin(void)
0x18002f842  lea     r9, [rsp+540h+var_4F8]
0x18002f847  mov     rdx, [rax]
0x18002f84a  lea     rcx, [rsp+540h+var_500]
0x18002f84f  call    ??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@std@@VContextDesc@ConnectedStorage@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@0@V10@V10@AEBVContextDesc@ConnectedStorage@@@Z; std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ConnectedStorage::ContextDesc>>>,ConnectedStorage::ContextDesc>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ConnectedStorage::ContextDesc>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ConnectedStorage::ContextDesc>>>,ConnectedStorage::ContextDesc const &)
0x18002f854  lea     rdx, [rbp+440h+var_4B8]
0x18002f858  mov     rcx, [rdi]
0x18002f85b  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002f860  mov     rdx, rax
0x18002f863  lea     rcx, [rsp+540h+var_500]
0x18002f868  call    ??8?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VContainer@ConnectedStorage@@@std@@@std@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<ConnectedStorage::Container>>>>>::operator==(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<ConnectedStorage::Container>>>>> const &)
0x18002f86d  test    al, al
0x18002f86f  jz      short loc_18002F880
0x18002f871  lea     rdx, [rsp+540h+var_4F8]
0x18002f876  mov     rcx, [rdi+8]
0x18002f87a  call    ?push_back@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAAXAEBVContextDesc@ConnectedStorage@@@Z; std::vector<ConnectedStorage::ContextDesc>::push_back(ConnectedStorage::ContextDesc const &)
0x18002f87f  nop
0x18002f880  lea     rcx, [rsp+540h+var_4F8]; this
0x18002f885  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x18002f88a  lea     rdx, [rbp+440h+var_490]; struct _WIN32_FIND_DATAW *
0x18002f88e  lea     rcx, [rsp+540h+var_510]; this
0x18002f893  call    ?FindNext@FindFile@ConnectedStorage@@QEAAKPEAU_WIN32_FIND_DATAW@@@Z; ConnectedStorage::FindFile::FindNext(_WIN32_FIND_DATAW *)
0x18002f898  test    eax, eax
0x18002f89a  jz      loc_18002F7A7
0x18002f8a0  cmp     eax, 12h
0x18002f8a3  jz      short loc_18002F8D7
0x18002f8a5  movzx   edx, ax
0x18002f8a8  mov     r8d, 80070000h; unsigned __int16 *
0x18002f8ae  test    eax, eax
0x18002f8b0  jg      short loc_18002F8B6
0x18002f8b2  mov     ecx, eax
0x18002f8b4  jmp     short loc_18002F8BB
0x18002f8b6  mov     ecx, edx
0x18002f8b8  or      ecx, r8d
0x18002f8bb  test    ecx, ecx
0x18002f8bd  jns     short loc_18002F8D7
0x18002f8bf  test    eax, eax
0x18002f8c1  jle     short loc_18002F8C8
0x18002f8c3  mov     eax, edx
0x18002f8c5  or      eax, r8d
0x18002f8c8  lea     rdx, aEnumerateconte; "EnumerateContextsOnDiskForXuid"
0x18002f8cf  mov     ecx, eax; this
0x18002f8d1  call    ?ReportErrorNoThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorNoThrow(long,ushort const *)
0x18002f8d6  nop
0x18002f8d7  lea     rcx, [rsp+540h+var_510]; this
0x18002f8dc  call    ?Close@FindFile@ConnectedStorage@@QEAAXXZ; ConnectedStorage::FindFile::Close(void)
0x18002f8e1  nop
0x18002f8e2  lea     rcx, [rbp+440h+var_4B0]
0x18002f8e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f8eb  nop
0x18002f8ec  xor     ecx, ecx; string
0x18002f8ee  call    cs:__imp_WindowsDeleteString
0x18002f8f4  mov     rcx, [rbp+440h+var_10]
0x18002f8fb  xor     rcx, rsp; StackCookie
0x18002f8fe  call    __security_check_cookie
0x18002f903  lea     r11, [rsp+540h+var_s0]
0x18002f90b  mov     rbx, [r11+20h]
0x18002f90f  mov     rdi, [r11+28h]
0x18002f913  mov     rsp, r11
0x18002f916  pop     rbp
0x18002f917  retn
```
