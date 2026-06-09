# ConnectedStorage::File::TryCreateFile(ushort const *,ConnectedStorage::File::Access,ConnectedStorage::VerifyFilePathHandler &)

- ea: `0x18004ff08`
- end: `0x18005009c`
- name: `?TryCreateFile@File@ConnectedStorage@@AEAAKPEBGW4Access@12@AEAVVerifyFilePathHandler@2@@Z`
- size: `404`
- prototype: `__int64 __fastcall(_QWORD *, const WCHAR *, int, _QWORD *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x18004e6bc`
- `0x18004ee1c`

## callees

- `0x180003c70`
- `0x180010e30`
- `0x18001c090`
- `0x18001c63c`
- `0x18001ff28`
- `0x18004eb40`
- `0x18004f1d0`
- `0x18004ff08`
- `0x1800500a4`
- `0x180050704`
- `0x180050cc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005006f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005006f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180050060`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180050060`

## pseudocode

```c
__int64 __fastcall ConnectedStorage::File::TryCreateFile(_QWORD *a1, const WCHAR *a2, int a3, _QWORD *a4)
{
  unsigned int v8; // edi
  __int64 v9; // rax
  DWORD dwCreationDisposition; // edx
  DWORD v11; // r8d
  DWORD v12; // eax
  HANDLE FileW; // rax
  __int64 v15; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v16[8]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v17[32]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v18[32]; // [rsp+70h] [rbp+7h] BYREF

  v8 = 0;
  std::wstring::wstring(v17);
  ConnectedStorage::VerifyFilePathHandler::VerifyPath(a4, v17);
  std::wstring::_Tidy_deallocate(v17);
  std::wstring::wstring(v17);
  ConnectedStorage::VerifyFilePathHandler::AddPath(a4, (__int64)v17);
  std::wstring::_Tidy_deallocate(v17);
  std::wstring::wstring(v18);
  ConnectedStorage::VerifyFilePathHandler::_SanitizePath(a4, v17, v18);
  std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::find(
    a4,
    &v15,
    v17);
  v9 = std::vector<ConnectedStorage::ContextDesc>::begin(a4, v16);
  if ( !(unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<ConnectedStorage::Container>>>>>::operator==(
                           &v15,
                           v9) )
    std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ConnectedStorage::Handle>>>>,0>(
      a4,
      v16,
      v15);
  std::wstring::_Tidy_deallocate(v17);
  std::wstring::_Tidy_deallocate(v18);
  if ( a3 )
  {
    if ( a3 == 1 )
    {
      dwCreationDisposition = 1;
    }
    else if ( a3 == 2 )
    {
      dwCreationDisposition = 2;
    }
    else
    {
      dwCreationDisposition = 0;
    }
    v11 = 4;
    if ( (unsigned int)(a3 - 1) < 2 )
      v12 = 0x40000000;
    else
      v12 = 0;
  }
  else
  {
    dwCreationDisposition = 3;
    v11 = 5;
    v12 = 0x80000000;
  }
  FileW = CreateFileW(a2, v12, v11, 0, dwCreationDisposition, 0x80u, 0);
  *a1 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  return v8;
}

```

## disassembly

```asm
0x18004ff08  mov     [rsp-8+arg_10], rbx
0x18004ff0d  push    rbp
0x18004ff0e  push    rsi
0x18004ff0f  push    rdi
0x18004ff10  push    r14
0x18004ff12  push    r15
0x18004ff14  lea     rbp, [rsp-37h]
0x18004ff19  sub     rsp, 0A0h
0x18004ff20  mov     rax, cs:__security_cookie
0x18004ff27  xor     rax, rsp
0x18004ff2a  mov     [rbp+57h+var_30], rax
0x18004ff2e  mov     rsi, r9
0x18004ff31  mov     ebx, r8d
0x18004ff34  mov     r14, rdx
0x18004ff37  mov     r15, rcx
0x18004ff3a  xor     edi, edi
0x18004ff3c  lea     rcx, [rbp+57h+var_70]
0x18004ff40  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ff45  nop
0x18004ff46  lea     rdx, [rbp+57h+var_70]
0x18004ff4a  mov     rcx, rsi
0x18004ff4d  call    ?VerifyPath@VerifyFilePathHandler@ConnectedStorage@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::VerifyFilePathHandler::VerifyPath(std::wstring const &)
0x18004ff52  nop
0x18004ff53  lea     rcx, [rbp+57h+var_70]
0x18004ff57  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ff5c  mov     rdx, r14
0x18004ff5f  lea     rcx, [rbp+57h+var_70]
0x18004ff63  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ff68  nop
0x18004ff69  lea     rdx, [rbp+57h+var_70]
0x18004ff6d  mov     rcx, rsi
0x18004ff70  call    ?AddPath@VerifyFilePathHandler@ConnectedStorage@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::VerifyFilePathHandler::AddPath(std::wstring const &)
0x18004ff75  nop
0x18004ff76  lea     rcx, [rbp+57h+var_70]
0x18004ff7a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ff7f  mov     rdx, r14
0x18004ff82  lea     rcx, [rbp+57h+var_50]
0x18004ff86  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ff8b  nop
0x18004ff8c  lea     r8, [rbp+57h+var_50]
0x18004ff90  lea     rdx, [rbp+57h+var_70]
0x18004ff94  mov     rcx, rsi
0x18004ff97  call    ?_SanitizePath@VerifyFilePathHandler@ConnectedStorage@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; ConnectedStorage::VerifyFilePathHandler::_SanitizePath(std::wstring const &)
0x18004ff9c  lea     r8, [rbp+57h+var_70]
0x18004ffa0  lea     rdx, [rbp+57h+var_80]
0x18004ffa4  mov     rcx, rsi
0x18004ffa7  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::find(std::wstring const &)
0x18004ffac  lea     rdx, [rbp+57h+var_78]
0x18004ffb0  mov     rcx, rsi
0x18004ffb3  call    ?begin@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::ContextDesc>::begin(void)
0x18004ffb8  mov     rdx, rax
0x18004ffbb  lea     rcx, [rbp+57h+var_80]
0x18004ffbf  call    ??8?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VContainer@ConnectedStorage@@@std@@@std@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<ConnectedStorage::Container>>>>>::operator==(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<ConnectedStorage::Container>>>>> const &)
0x18004ffc4  test    al, al
0x18004ffc6  jnz     short loc_18004FFD8
0x18004ffc8  mov     r8, [rbp+57h+var_80]
0x18004ffcc  lea     rdx, [rbp+57h+var_78]
0x18004ffd0  mov     rcx, rsi
0x18004ffd3  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ConnectedStorage::Handle>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ConnectedStorage::Handle>>>>)
0x18004ffd8  lea     rcx, [rbp+57h+var_70]
0x18004ffdc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ffe1  nop
0x18004ffe2  lea     rcx, [rbp+57h+var_50]
0x18004ffe6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ffeb  mov     ecx, ebx
0x18004ffed  test    ebx, ebx
0x18004ffef  jz      short loc_180050033
0x18004fff1  sub     ecx, 1
0x18004fff4  jz      short loc_18005000F
0x18004fff6  cmp     ecx, 1
0x18004fff9  jz      short loc_180050008
0x18004fffb  xor     edx, edx
0x18004fffd  mov     ecx, ebx
0x18004ffff  test    ebx, ebx
0x180050001  jz      short loc_180050038
0x180050003  sub     ecx, 1
0x180050006  jmp     short loc_180050014
0x180050008  mov     edx, 2
0x18005000d  jmp     short loc_180050014
0x18005000f  mov     edx, 1
0x180050014  mov     r8d, 4
0x18005001a  test    ebx, ebx
0x18005001c  jz      short loc_18005003E
0x18005001e  sub     ebx, 1
0x180050021  jz      short loc_18005002C
0x180050023  cmp     ebx, 1
0x180050026  jz      short loc_18005002C
0x180050028  xor     eax, eax
0x18005002a  jmp     short loc_180050043
0x18005002c  mov     eax, 40000000h
0x180050031  jmp     short loc_180050043
0x180050033  mov     edx, 3
0x180050038  mov     r8d, 5; dwShareMode
0x18005003e  mov     eax, 80000000h
0x180050043  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18005004c  mov     [rsp+0C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180050054  mov     [rsp+0C0h+dwCreationDisposition], edx; dwCreationDisposition
0x180050058  xor     r9d, r9d; lpSecurityAttributes
0x18005005b  mov     edx, eax; dwDesiredAccess
0x18005005d  mov     rcx, r14; lpFileName
0x180050060  call    cs:__imp_CreateFileW
0x180050066  mov     [r15], rax
0x180050069  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005006d  jnz     short loc_180050077
0x18005006f  call    cs:__imp_GetLastError
0x180050075  mov     edi, eax
0x180050077  mov     eax, edi
0x180050079  mov     rcx, [rbp+57h+var_30]
0x18005007d  xor     rcx, rsp; StackCookie
0x180050080  call    __security_check_cookie
0x180050085  mov     rbx, [rsp+0C0h+arg_10]
0x18005008d  add     rsp, 0A0h
0x180050094  pop     r15
0x180050096  pop     r14
0x180050098  pop     rdi
0x180050099  pop     rsi
0x18005009a  pop     rbp
0x18005009b  retn
```
