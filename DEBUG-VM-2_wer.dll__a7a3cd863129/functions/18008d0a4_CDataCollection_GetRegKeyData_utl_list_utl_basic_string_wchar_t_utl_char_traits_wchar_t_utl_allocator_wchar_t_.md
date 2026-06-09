# CDataCollection::GetRegKeyData(utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> &,int,void *)

- ea: `0x18008d0a4`
- end: `0x18008d503`
- name: `?GetRegKeyData@CDataCollection@@AEAAJAEAV?$list@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@HPEAX@Z`
- size: `1119`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004ee3c`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18000bc10`
- `0x18000bfbc`
- `0x18000d75c`
- `0x18000dad0`
- `0x18000ea64`
- `0x180013a20`
- `0x18001c650`
- `0x18001c6d8`
- `0x18001f5bc`
- `0x18001fe24`
- `0x18002b7a4`
- `0x1800376c8`
- `0x180050db0`
- `0x18008af34`
- `0x18008af68`
- `0x18008afa0`
- `0x18008d0a4`
- `0x18009b818`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d29b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d29b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008d36f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008d36f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008d3aa`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008d3aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008d291`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008d291`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008d21e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008d242`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008d31f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008d21e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008d242`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008d31f`

## pseudocode

```c
__int64 __fastcall CDataCollection::GetRegKeyData(__int64 a1, __int64 **a2, int a3, void *a4)
{
  unsigned int v8; // edi
  _QWORD *v9; // rcx
  __int64 v10; // rax
  wchar_t *v11; // rcx
  int Key; // eax
  CDataCollection *v13; // rcx
  DWORD LastError; // eax
  DWORD v15; // r8d
  DWORD v16; // r9d
  DWORD i; // r14d
  __int64 v18; // rdi
  __int64 v19; // rcx
  __int64 *v20; // rdi
  __int64 v21; // rcx
  __int64 v22; // r8
  char v23; // al
  __int64 **v24; // rax
  __int64 *v25; // rcx
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cValues; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxValueLen; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  __int64 v34; // [rsp+80h] [rbp-80h] BYREF
  LPCVOID lpBuffer; // [rsp+88h] [rbp-78h] BYREF
  __int64 v36; // [rsp+90h] [rbp-70h]
  _BYTE v37[40]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR Name[264]; // [rsp+D0h] [rbp-30h] BYREF

  hKey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpBuffer);
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cSubKeys = 0;
  NumberOfBytesWritten = 0;
  if ( a4 == (void *)-1LL )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
    v8 = -2147024809;
  }
  else if ( *a2 == (__int64 *)a2 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, 2147500037LL);
    v8 = -2147467259;
  }
  else
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(&lpBuffer, *a2 + 2);
    v9 = (_QWORD *)(*a2)[1];
    v10 = **a2;
    *v9 = v10;
    *(_QWORD *)(v10 + 8) = v9;
    utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_DeleteNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>();
    v11 = (wchar_t *)lpBuffer;
    a2[2] = (__int64 *)((char *)a2[2] - 1);
    Key = CRegSetting::GetKey(v11);
    v8 = Key;
    if ( Key >= 0 )
    {
      WriteFile(a4, L"\r\n", 4u, &NumberOfBytesWritten, 0);
      WriteFile(a4, lpBuffer, 2 * ((v36 - (__int64)lpBuffer) >> 1), &NumberOfBytesWritten, 0);
      if ( RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0) )
      {
        LastError = GetLastError();
        v8 = ERROR_HR_FROM_WIN32(LastError);
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
      }
      else
      {
        v15 = cValues;
        v16 = cbMaxValueNameLen + 1;
        if ( cbMaxValueNameLen + 1 < 0xB )
          v16 = 11;
        cbMaxValueNameLen = v16;
        if ( cValues )
        {
          WriteFile(a4, L"\r\n", 4u, &NumberOfBytesWritten, 0);
          v15 = cValues;
          v16 = cbMaxValueNameLen;
        }
        CDataCollection::WriteValuesForRegKey(v13, hKey, v15, v16, cbMaxValueLen, a4);
        if ( a3 )
        {
          cchName = 0;
          for ( i = 0; i < cSubKeys; ++i )
          {
            if ( !WaitForSingleObject(*(HANDLE *)(a1 + 16), 0) )
            {
              v8 = -2145681407;
              goto LABEL_46;
            }
            cchName = 260;
            if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0)
              && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
            }
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v37);
            v18 = -1;
            do
              ++v18;
            while ( Name[v18] );
            if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(v37)
              && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                    v37,
                                    lpBuffer,
                                    (v36 - (__int64)lpBuffer) >> 1)
              && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                    v37,
                                    92)
              && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                    v37,
                                    Name,
                                    v18) )
            {
              v20 = *a2;
              utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_NewNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(
                v19,
                &v34);
              if ( !v34
                || (v23 = utl::allocator_traits<utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::construct<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(
                            v21,
                            v34 + 16,
                            v37),
                    LOBYTE(v22) = 1,
                    !v23) )
              {
                LOBYTE(v22) = 0;
              }
              v24 = (__int64 **)utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_NewNodeCommit<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(
                                  v21,
                                  &v34,
                                  v22);
              if ( v24 )
              {
                v25 = (__int64 *)v20[1];
                v24[1] = v25;
                *v24 = v20;
                *v25 = (__int64)v24;
                v20[1] = (__int64)v24;
                a2[2] = (__int64 *)((char *)a2[2] + 1);
              }
              utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v34);
            }
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v37);
          }
        }
        v8 = 0;
      }
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
        (unsigned int)Key);
    }
  }
LABEL_46:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpBuffer);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return v8;
}

```

## disassembly

```asm
0x18008d0a4  push    rbp
0x18008d0a6  push    rbx
0x18008d0a7  push    rsi
0x18008d0a8  push    rdi
0x18008d0a9  push    r12
0x18008d0ab  push    r14
0x18008d0ad  push    r15
0x18008d0af  lea     rbp, [rsp-1F0h]
0x18008d0b7  sub     rsp, 2F0h
0x18008d0be  mov     rax, cs:__security_cookie
0x18008d0c5  xor     rax, rsp
0x18008d0c8  mov     [rbp+220h+var_40], rax
0x18008d0cf  mov     r15, rcx
0x18008d0d2  xor     r12d, r12d
0x18008d0d5  lea     rcx, [rbp+220h+lpBuffer]; void *
0x18008d0d9  mov     [rsp+320h+hKey], r12
0x18008d0de  mov     rbx, r9
0x18008d0e1  mov     r14d, r8d
0x18008d0e4  mov     rsi, rdx
0x18008d0e7  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008d0ec  mov     [rsp+320h+cValues], r12d
0x18008d0f1  mov     [rsp+320h+cbMaxValueNameLen], r12d
0x18008d0f6  mov     [rsp+320h+cbMaxValueLen], r12d
0x18008d0fb  mov     [rsp+320h+cSubKeys], r12d
0x18008d100  mov     [rsp+320h+NumberOfBytesWritten], r12d
0x18008d105  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18008d109  jnz     short loc_18008D143
0x18008d10b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d112  lea     rbx, WPP_GLOBAL_Control
0x18008d119  cmp     rcx, rbx
0x18008d11c  jz      short loc_18008D139
0x18008d11e  test    byte ptr [rcx+1Ch], 1
0x18008d122  jz      short loc_18008D139
0x18008d124  mov     rcx, [rcx+10h]
0x18008d128  lea     edx, [r12+20h]
0x18008d12d  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008d134  call    WPP_SF_
0x18008d139  mov     edi, 80070057h
0x18008d13e  jmp     loc_18008D4CD
0x18008d143  mov     rdx, [rsi]
0x18008d146  cmp     rdx, rsi
0x18008d149  jnz     short loc_18008D189
0x18008d14b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d152  lea     rbx, WPP_GLOBAL_Control
0x18008d159  cmp     rcx, rbx
0x18008d15c  jz      short loc_18008D17F
0x18008d15e  test    byte ptr [rcx+1Ch], 1
0x18008d162  jz      short loc_18008D17F
0x18008d164  mov     rcx, [rcx+10h]
0x18008d168  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008d16f  mov     edx, 21h ; '!'
0x18008d174  mov     r9d, 80004005h
0x18008d17a  call    WPP_SF_d
0x18008d17f  mov     edi, 80004005h
0x18008d184  jmp     loc_18008D4CD
0x18008d189  add     rdx, 10h
0x18008d18d  lea     rcx, [rbp+220h+lpBuffer]
0x18008d191  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18008d196  mov     rdx, [rsi]
0x18008d199  mov     rcx, [rdx+8]
0x18008d19d  mov     rax, [rdx]
0x18008d1a0  mov     [rcx], rax
0x18008d1a3  mov     [rax+8], rcx
0x18008d1a7  call    ??$_DeleteNode@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@IEAAXPEAU?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@@Z; utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_DeleteNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>> *)
0x18008d1ac  mov     rcx, [rbp+220h+lpBuffer]; Str
0x18008d1b0  lea     r8, [rsp+320h+hKey]
0x18008d1b5  dec     qword ptr [rsi+10h]
0x18008d1b9  call    ?GetKey@CRegSetting@@SAJPEB_WKPEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; CRegSetting::GetKey(wchar_t const *,ulong,tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> *)
0x18008d1be  mov     edi, eax
0x18008d1c0  test    eax, eax
0x18008d1c2  jns     short loc_18008D202
0x18008d1c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d1cb  lea     rbx, WPP_GLOBAL_Control
0x18008d1d2  cmp     rcx, rbx
0x18008d1d5  jz      loc_18008D4CD
0x18008d1db  test    byte ptr [rcx+1Ch], 1
0x18008d1df  jz      loc_18008D4CD
0x18008d1e5  mov     rcx, [rcx+10h]
0x18008d1e9  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008d1f0  mov     edx, 22h ; '"'
0x18008d1f5  mov     r9d, eax
0x18008d1f8  call    WPP_SF_d
0x18008d1fd  jmp     loc_18008D4CD
0x18008d202  mov     edi, 4
0x18008d207  mov     [rsp+320h+lpOverlapped], r12; lpOverlapped
0x18008d20c  mov     r8d, edi; nNumberOfBytesToWrite
0x18008d20f  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008d214  lea     rdx, asc_1800B1BD0; "\r\n"
0x18008d21b  mov     rcx, rbx; hFile
0x18008d21e  call    cs:__imp_WriteFile
0x18008d224  mov     r8, [rbp+220h+var_290]
0x18008d228  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008d22d  mov     rdx, [rbp+220h+lpBuffer]; lpBuffer
0x18008d231  mov     rcx, rbx; hFile
0x18008d234  sub     r8, rdx
0x18008d237  mov     [rsp+320h+lpOverlapped], r12; lpOverlapped
0x18008d23c  sar     r8, 1
0x18008d23f  add     r8d, r8d; nNumberOfBytesToWrite
0x18008d242  call    cs:__imp_WriteFile
0x18008d248  mov     rcx, [rsp+320h+hKey]; hKey
0x18008d24d  lea     rax, [rsp+320h+cbMaxValueLen]
0x18008d252  mov     [rsp+320h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18008d257  xor     r9d, r9d; lpReserved
0x18008d25a  mov     [rsp+320h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18008d25f  xor     r8d, r8d; lpcchClass
0x18008d262  mov     [rsp+320h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18008d267  xor     edx, edx; lpClass
0x18008d269  lea     rax, [rsp+320h+cbMaxValueNameLen]
0x18008d26e  mov     [rsp+320h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18008d273  lea     rax, [rsp+320h+cValues]
0x18008d278  mov     [rsp+320h+lpcValues], rax; lpcValues
0x18008d27d  lea     rax, [rsp+320h+cSubKeys]
0x18008d282  mov     [rsp+320h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18008d287  mov     [rsp+320h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18008d28c  mov     [rsp+320h+lpOverlapped], rax; lpcSubKeys
0x18008d291  call    cs:__imp_RegQueryInfoKeyW
0x18008d297  test    eax, eax
0x18008d299  jz      short loc_18008D2E5
0x18008d29b  call    cs:__imp_GetLastError
0x18008d2a1  mov     ecx, eax; unsigned int
0x18008d2a3  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18008d2a8  mov     edi, eax
0x18008d2aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d2b1  lea     rbx, WPP_GLOBAL_Control
0x18008d2b8  cmp     rcx, rbx
0x18008d2bb  jz      loc_18008D4CD
0x18008d2c1  test    byte ptr [rcx+1Ch], 1
0x18008d2c5  jz      loc_18008D4CD
0x18008d2cb  mov     rcx, [rcx+10h]
0x18008d2cf  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008d2d6  mov     edx, 23h ; '#'
0x18008d2db  call    WPP_SF_
0x18008d2e0  jmp     loc_18008D4CD
0x18008d2e5  mov     r9d, [rsp+320h+cbMaxValueNameLen]
0x18008d2ea  mov     eax, 0Bh
0x18008d2ef  mov     r8d, [rsp+320h+cValues]
0x18008d2f4  inc     r9d
0x18008d2f7  cmp     r9d, eax
0x18008d2fa  cmovb   r9d, eax
0x18008d2fe  mov     [rsp+320h+cbMaxValueNameLen], r9d
0x18008d303  test    r8d, r8d
0x18008d306  jz      short loc_18008D32F
0x18008d308  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008d30d  mov     [rsp+320h+lpOverlapped], r12; lpOverlapped
0x18008d312  mov     r8d, edi; nNumberOfBytesToWrite
0x18008d315  lea     rdx, asc_1800B1BD0; "\r\n"
0x18008d31c  mov     rcx, rbx; hFile
0x18008d31f  call    cs:__imp_WriteFile
0x18008d325  mov     r8d, [rsp+320h+cValues]; unsigned int
0x18008d32a  mov     r9d, [rsp+320h+cbMaxValueNameLen]; unsigned int
0x18008d32f  mov     eax, [rsp+320h+cbMaxValueLen]
0x18008d333  mov     rdx, [rsp+320h+hKey]; HKEY
0x18008d338  mov     [rsp+320h+lpcbMaxSubKeyLen], rbx; void *
0x18008d33d  mov     dword ptr [rsp+320h+lpOverlapped], eax; unsigned int
0x18008d341  call    ?WriteValuesForRegKey@CDataCollection@@AEAAJPEAUHKEY__@@KKKPEAX@Z; CDataCollection::WriteValuesForRegKey(HKEY__ *,ulong,ulong,ulong,void *)
0x18008d346  test    r14d, r14d
0x18008d349  jz      loc_18008D4CA
0x18008d34f  mov     [rsp+320h+cchName], r12d
0x18008d354  lea     rbx, WPP_GLOBAL_Control
0x18008d35b  mov     r14d, r12d
0x18008d35e  cmp     r14d, [rsp+320h+cSubKeys]
0x18008d363  jnb     loc_18008D4CA
0x18008d369  mov     rcx, [r15+10h]; hHandle
0x18008d36d  xor     edx, edx; dwMilliseconds
0x18008d36f  call    cs:__imp_WaitForSingleObject
0x18008d375  test    eax, eax
0x18008d377  jz      loc_18008D4C3
0x18008d37d  mov     rcx, [rsp+320h+hKey]; hKey
0x18008d382  lea     r9, [rsp+320h+cchName]; lpcchName
0x18008d387  mov     [rsp+320h+lpcValues], r12; lpftLastWriteTime
0x18008d38c  lea     r8, [rbp+220h+Name]; lpName
0x18008d390  mov     [rsp+320h+lpcbMaxClassLen], r12; lpcchClass
0x18008d395  mov     edx, r14d; dwIndex
0x18008d398  mov     [rsp+320h+lpcbMaxSubKeyLen], r12; lpClass
0x18008d39d  mov     [rsp+320h+lpOverlapped], r12; lpReserved
0x18008d3a2  mov     [rsp+320h+cchName], 104h
0x18008d3aa  call    cs:__imp_RegEnumKeyExW
0x18008d3b0  test    eax, eax
0x18008d3b2  jz      short loc_18008D3DB
0x18008d3b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d3bb  cmp     rcx, rbx
0x18008d3be  jz      short loc_18008D3DB
0x18008d3c0  test    byte ptr [rcx+1Ch], 1
0x18008d3c4  jz      short loc_18008D3DB
0x18008d3c6  mov     rcx, [rcx+10h]
0x18008d3ca  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008d3d1  mov     edx, 24h ; '$'
0x18008d3d6  call    WPP_SF_
0x18008d3db  lea     rcx, [rbp+220h+var_278]; void *
0x18008d3df  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008d3e4  lea     rax, [rbp+220h+Name]
0x18008d3e8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008d3ec  inc     rdi
0x18008d3ef  cmp     [rax+rdi*2], r12w
0x18008d3f4  jnz     short loc_18008D3EC
0x18008d3f6  mov     rdx, [rbp+220h+var_290]
0x18008d3fa  lea     rcx, [rbp+220h+var_278]
0x18008d3fe  sub     rdx, [rbp+220h+lpBuffer]
0x18008d402  sar     rdx, 1
0x18008d405  inc     rdx
0x18008d408  add     rdx, rdi
0x18008d40b  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x18008d410  test    al, al
0x18008d412  jz      loc_18008D4B2
0x18008d418  mov     r8, [rbp+220h+var_290]
0x18008d41c  lea     rcx, [rbp+220h+var_278]
0x18008d420  mov     rdx, [rbp+220h+lpBuffer]
0x18008d424  sub     r8, rdx
0x18008d427  sar     r8, 1
0x18008d42a  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18008d42f  test    al, al
0x18008d431  jz      short loc_18008D4B2
0x18008d433  mov     edx, 5Ch ; '\'
0x18008d438  lea     rcx, [rbp+220h+var_278]
0x18008d43c  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18008d441  test    al, al
0x18008d443  jz      short loc_18008D4B2
0x18008d445  mov     r8, rdi
0x18008d448  lea     rdx, [rbp+220h+Name]
0x18008d44c  lea     rcx, [rbp+220h+var_278]
0x18008d450  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18008d455  test    al, al
0x18008d457  jz      short loc_18008D4B2
0x18008d459  mov     rdi, [rsi]
0x18008d45c  lea     rdx, [rbp+220h+var_2A0]
0x18008d460  call    ??$_NewNode@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@IEAA?AU?$_UninitializedAllocation@V?$allocator@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@utl@@@1@XZ; utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_NewNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x18008d465  mov     rdx, [rbp+220h+var_2A0]
0x18008d469  test    rdx, rdx
0x18008d46c  jz      short loc_18008D482
0x18008d46e  add     rdx, 10h
0x18008d472  lea     r8, [rbp+220h+var_278]
0x18008d476  call    ??$construct@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@?$allocator_traits@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@utl@@SA_NAEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@1@$$QEAV31@@Z; utl::allocator_traits<utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::construct<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18008d47b  mov     r8b, 1
0x18008d47e  test    al, al
0x18008d480  jnz     short loc_18008D485
0x18008d482  mov     r8b, r12b
0x18008d485  lea     rdx, [rbp+220h+var_2A0]
0x18008d489  call    ??$_NewNodeCommit@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@IEAAPEAU?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@AEAU?$_UninitializedAllocation@V?$allocator@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@utl@@@1@_N@Z; utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_NewNodeCommit<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>> &,bool)
0x18008d48e  test    rax, rax
0x18008d491  jz      short loc_18008D4A9
0x18008d493  mov     rcx, [rdi+8]
0x18008d497  mov     [rax+8], rcx
0x18008d49b  mov     [rax], rdi
0x18008d49e  mov     [rcx], rax
0x18008d4a1  mov     [rdi+8], rax
0x18008d4a5  inc     qword ptr [rsi+10h]
0x18008d4a9  lea     rcx, [rbp+220h+var_2A0]; void *
0x18008d4ad  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18008d4b2  lea     rcx, [rbp+220h+var_278]; void *
0x18008d4b6  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008d4bb  inc     r14d
0x18008d4be  jmp     loc_18008D35E
0x18008d4c3  mov     edi, 801B8001h
0x18008d4c8  jmp     short loc_18008D4CD
0x18008d4ca  mov     edi, r12d
0x18008d4cd  lea     rcx, [rbp+220h+lpBuffer]; void *
0x18008d4d1  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008d4d6  lea     rcx, [rsp+320h+hKey]
0x18008d4db  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18008d4e0  mov     eax, edi
0x18008d4e2  mov     rcx, [rbp+220h+var_40]
0x18008d4e9  xor     rcx, rsp; StackCookie
0x18008d4ec  call    __security_check_cookie
0x18008d4f1  add     rsp, 2F0h
0x18008d4f8  pop     r15
0x18008d4fa  pop     r14
0x18008d4fc  pop     r12
0x18008d4fe  pop     rdi
0x18008d4ff  pop     rsi
0x18008d500  pop     rbx
0x18008d501  pop     rbp
0x18008d502  retn
```
