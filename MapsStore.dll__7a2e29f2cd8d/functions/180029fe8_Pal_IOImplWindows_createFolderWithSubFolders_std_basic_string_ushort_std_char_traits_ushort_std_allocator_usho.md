# Pal::IOImplWindows::createFolderWithSubFolders(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180029fe8`
- end: `0x18002a1d9`
- name: `?createFolderWithSubFolders@IOImplWindows@Pal@@AEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180029f90`

## callees

- `0x18000d090`
- `0x1800126c4`
- `0x180012720`
- `0x1800140f0`
- `0x180014d44`
- `0x18001cc74`
- `0x18001de0c`
- `0x180024c14`
- `0x180025c68`
- `0x180029fe8`
- `0x18002c76c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a02b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a156`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a18d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a02b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a156`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a18d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a01d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a099`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a14c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a183`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a01d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a099`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a14c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a183`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Pal::IOImplWindows::createFolderWithSubFolders(__int64 a1, __int64 a2)
{
  const WCHAR *v3; // rax
  DWORD LastError; // eax
  bool v5; // bl
  __int64 v7; // rbx
  const WCHAR *v8; // rax
  DWORD v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rbx
  char v12; // di
  const WCHAR *v13; // rax
  const WCHAR *v14; // rax
  _BYTE v15[4]; // [rsp+20h] [rbp-58h] BYREF
  int v16; // [rsp+24h] [rbp-54h] BYREF
  _QWORD v17[3]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-38h] BYREF

  CallingStateTracker::CallingStateTracker(v15);
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  if ( CreateDirectoryW(v3, 0) )
  {
    CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v15);
    return 1;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 3 )
    {
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>(v17);
      v7 = std::wstring::rfind(a2, 92, -1);
      while ( v7 != -1 )
      {
        std::wstring::substr(a2, v18, 0, v7);
        v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
        if ( CreateDirectoryW(v8, 0) || (v9 = GetLastError(), v9 == 183) )
        {
          std::wstring::_Tidy_deallocate(v18);
          break;
        }
        if ( v9 != 3 )
        {
LABEL_10:
          std::wstring::_Tidy_deallocate(v18);
          std::vector<enum MapControl::PersistentDataType>::_Tidy(v17);
          CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v15);
          return 0;
        }
        v16 = v7;
        std::vector<int>::_Emplace_one_at_back<int>(v17, &v16);
        v7 = std::wstring::rfind(a2, 92, v7 - 1);
        std::wstring::_Tidy_deallocate(v18);
      }
      v10 = v17[0];
      v11 = (__int64)(v17[1] - v17[0]) >> 2;
      v12 = 1;
      while ( 1 )
      {
        LODWORD(v11) = v11 - 1;
        if ( (int)v11 < 0 )
          break;
        std::wstring::substr(a2, v18, 0, *(int *)(v10 + 4LL * (int)v11));
        v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
        if ( !CreateDirectoryW(v13, 0) && GetLastError() != 183 )
          goto LABEL_10;
        std::wstring::_Tidy_deallocate(v18);
        v10 = v17[0];
      }
      v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      if ( !CreateDirectoryW(v14, 0) && GetLastError() != 183 )
        v12 = 0;
      std::vector<enum MapControl::PersistentDataType>::_Tidy(v17);
      CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v15);
      return v12;
    }
    else
    {
      v5 = LastError == 183;
      CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v15);
      return v5;
    }
  }
}

```

## disassembly

```asm
0x180029fe8  push    rbp
0x180029fea  push    rbx
0x180029feb  push    rdi
0x180029fec  push    r14
0x180029fee  mov     rbp, rsp
0x180029ff1  sub     rsp, 78h
0x180029ff5  mov     rax, cs:__security_cookie
0x180029ffc  xor     rax, rsp
0x180029fff  mov     [rbp+var_18], rax
0x18002a003  mov     r14, rdx
0x18002a006  lea     rcx, [rbp+var_58]
0x18002a00a  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x18002a00f  nop
0x18002a010  mov     rcx, r14
0x18002a013  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a018  xor     edx, edx; lpSecurityAttributes
0x18002a01a  mov     rcx, rax; lpPathName
0x18002a01d  call    cs:__imp_CreateDirectoryW
0x18002a023  test    eax, eax
0x18002a025  jnz     loc_18002A1B5
0x18002a02b  call    cs:__imp_GetLastError
0x18002a031  cmp     eax, 3
0x18002a034  jz      short loc_18002A04E
0x18002a036  cmp     eax, 0B7h
0x18002a03b  setz    bl
0x18002a03e  lea     rcx, [rbp+var_58]; this
0x18002a042  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x18002a047  mov     al, bl
0x18002a049  jmp     loc_18002A1C3
0x18002a04e  lea     rcx, [rbp+var_50]; void *
0x18002a052  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@H_K@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@H_K@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@H_K@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>(std::allocator<std::pair<std::wstring const,std::pair<int,unsigned __int64>>> const &)
0x18002a057  nop
0x18002a058  mov     edi, 5Ch ; '\'
0x18002a05d  mov     edx, edi
0x18002a05f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002a063  mov     rcx, r14
0x18002a066  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x18002a06b  mov     rbx, rax
0x18002a06e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002a072  jz      loc_18002A10E
0x18002a078  mov     r9, rbx
0x18002a07b  xor     r8d, r8d
0x18002a07e  lea     rdx, [rbp+var_38]
0x18002a082  mov     rcx, r14
0x18002a085  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18002a08a  nop
0x18002a08b  lea     rcx, [rbp+var_38]
0x18002a08f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a094  mov     rcx, rax; lpPathName
0x18002a097  xor     edx, edx; lpSecurityAttributes
0x18002a099  call    cs:__imp_CreateDirectoryW
0x18002a09f  test    eax, eax
0x18002a0a1  jnz     short loc_18002A105
0x18002a0a3  call    cs:__imp_GetLastError
0x18002a0a9  cmp     eax, 0B7h
0x18002a0ae  jz      short loc_18002A105
0x18002a0b0  cmp     eax, 3
0x18002a0b3  jnz     short loc_18002A0E1
0x18002a0b5  mov     [rbp+var_54], ebx
0x18002a0b8  lea     rdx, [rbp+var_54]
0x18002a0bc  lea     rcx, [rbp+var_50]
0x18002a0c0  call    ??$_Emplace_one_at_back@H@?$vector@HV?$allocator@H@std@@@std@@AEAAAEAH$$QEAH@Z; std::vector<int>::_Emplace_one_at_back<int>(int &&)
0x18002a0c5  lea     r8, [rbx-1]
0x18002a0c9  mov     edx, edi
0x18002a0cb  mov     rcx, r14
0x18002a0ce  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x18002a0d3  mov     rbx, rax
0x18002a0d6  lea     rcx, [rbp+var_38]
0x18002a0da  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a0df  jmp     short loc_18002A06E
0x18002a0e1  lea     rcx, [rbp+var_38]
0x18002a0e5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a0ea  nop
0x18002a0eb  lea     rcx, [rbp+var_50]
0x18002a0ef  call    ?_Tidy@?$vector@W4PersistentDataType@MapControl@@V?$allocator@W4PersistentDataType@MapControl@@@std@@@std@@AEAAXXZ; std::vector<MapControl::PersistentDataType>::_Tidy(void)
0x18002a0f4  nop
0x18002a0f5  lea     rcx, [rbp+var_58]; this
0x18002a0f9  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x18002a0fe  xor     al, al
0x18002a100  jmp     loc_18002A1C3
0x18002a105  lea     rcx, [rbp+var_38]
0x18002a109  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a10e  mov     rbx, [rbp+var_48]
0x18002a112  mov     rcx, [rbp+var_50]
0x18002a116  sub     rbx, rcx
0x18002a119  sar     rbx, 2
0x18002a11d  mov     edi, 1
0x18002a122  sub     ebx, edi
0x18002a124  test    ebx, ebx
0x18002a126  js      short loc_18002A176
0x18002a128  movsxd  rax, ebx
0x18002a12b  movsxd  r9, dword ptr [rcx+rax*4]
0x18002a12f  xor     r8d, r8d
0x18002a132  lea     rdx, [rbp+var_38]
0x18002a136  mov     rcx, r14
0x18002a139  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18002a13e  lea     rcx, [rbp+var_38]
0x18002a142  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a147  mov     rcx, rax; lpPathName
0x18002a14a  xor     edx, edx; lpSecurityAttributes
0x18002a14c  call    cs:__imp_CreateDirectoryW
0x18002a152  test    eax, eax
0x18002a154  jnz     short loc_18002A167
0x18002a156  call    cs:__imp_GetLastError
0x18002a15c  cmp     eax, 0B7h
0x18002a161  jnz     loc_18002A0E1
0x18002a167  lea     rcx, [rbp+var_38]
0x18002a16b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a170  mov     rcx, [rbp+var_50]
0x18002a174  jmp     short loc_18002A122
0x18002a176  mov     rcx, r14
0x18002a179  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a17e  xor     edx, edx; lpSecurityAttributes
0x18002a180  mov     rcx, rax; lpPathName
0x18002a183  call    cs:__imp_CreateDirectoryW
0x18002a189  test    eax, eax
0x18002a18b  jnz     short loc_18002A19D
0x18002a18d  call    cs:__imp_GetLastError
0x18002a193  cmp     eax, 0B7h
0x18002a198  jz      short loc_18002A19D
0x18002a19a  xor     dil, dil
0x18002a19d  lea     rcx, [rbp+var_50]
0x18002a1a1  call    ?_Tidy@?$vector@W4PersistentDataType@MapControl@@V?$allocator@W4PersistentDataType@MapControl@@@std@@@std@@AEAAXXZ; std::vector<MapControl::PersistentDataType>::_Tidy(void)
0x18002a1a6  nop
0x18002a1a7  lea     rcx, [rbp+var_58]; this
0x18002a1ab  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x18002a1b0  mov     al, dil
0x18002a1b3  jmp     short loc_18002A1C3
0x18002a1b5  lea     rcx, [rbp+var_58]; this
0x18002a1b9  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x18002a1be  mov     eax, 1
0x18002a1c3  mov     rcx, [rbp+var_18]
0x18002a1c7  xor     rcx, rsp; StackCookie
0x18002a1ca  call    __security_check_cookie
0x18002a1cf  add     rsp, 78h
0x18002a1d3  pop     r14
0x18002a1d5  pop     rdi
0x18002a1d6  pop     rbx
0x18002a1d7  pop     rbp
0x18002a1d8  retn
```
