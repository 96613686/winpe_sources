# ContrastThemeBackupRestoreHandler::CopyInboxThemeFileToUserPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ITheme *)

- ea: `0x180093624`
- end: `0x18009371c`
- name: `?CopyInboxThemeFileToUserPath@ContrastThemeBackupRestoreHandler@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@PEAUITheme@@@Z`
- size: `248`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800929c8`
- `0x180093050`

## callees

- `0x18000c6e0`
- `0x180015668`
- `0x18001c180`
- `0x18001cf84`
- `0x18001cfa4`
- `0x18001d0a8`
- `0x18001ffa8`
- `0x180093624`
- `0x180093f70`
- `0x18012d010`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x1800936b8`
- `KERNEL32!CopyFileW` at `0x1800936b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ContrastThemeBackupRestoreHandler::CopyInboxThemeFileToUserPath(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  const WCHAR *v10; // rax
  const char *v11; // r9
  LPCWSTR lpExistingFileName; // [rsp+20h] [rbp-68h] BYREF
  int v14; // [rsp+28h] [rbp-60h]
  __int64 v15; // [rsp+30h] [rbp-58h]
  _BYTE v16[32]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v17; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v15 = a2;
  v17 = a3;
  v7 = std::wstring::wstring(v16, a3);
  ContrastThemeBackupRestoreHandler::GetCustomThemePath(v8, a2, v7);
  v14 = 1;
  lpExistingFileName = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, LPCWSTR *))(*(_QWORD *)a4 + 288LL))(
         a4,
         0xFFFFFFFFLL,
         &lpExistingFileName);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x252,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\contrastthemebackuprestorehandler.cpp",
      (const char *)(unsigned int)v9,
      (int)lpExistingFileName);
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  if ( !CopyFileW(lpExistingFileName, v10, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x254,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\contrastthemebackuprestorehandler.cpp",
      v11);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpExistingFileName);
  std::wstring::_Tidy_deallocate(a3);
  return a2;
}

```

## disassembly

```asm
0x180093624  push    rbx
0x180093626  push    rsi
0x180093627  push    rdi
0x180093628  sub     rsp, 70h
0x18009362c  mov     rax, cs:__security_cookie
0x180093633  xor     rax, rsp
0x180093636  mov     [rsp+88h+var_28], rax
0x18009363b  mov     rbx, r9
0x18009363e  mov     rsi, r8
0x180093641  mov     rdi, rdx
0x180093644  mov     [rsp+88h+var_58], rdx
0x180093649  mov     [rsp+88h+var_30], r8
0x18009364e  mov     [rsp+88h+var_60], 0
0x180093656  mov     rdx, r8
0x180093659  lea     rcx, [rsp+88h+var_50]
0x18009365e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180093663  mov     r8, rax
0x180093666  mov     rdx, rdi
0x180093669  call    ?GetCustomThemePath@ContrastThemeBackupRestoreHandler@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; ContrastThemeBackupRestoreHandler::GetCustomThemePath(std::wstring)
0x18009366e  mov     [rsp+88h+var_60], 1
0x180093676  mov     [rsp+88h+lpExistingFileName], 0; int
0x18009367f  mov     rax, [rbx]
0x180093682  or      edx, 0FFFFFFFFh
0x180093685  lea     r8, [rsp+88h+lpExistingFileName]
0x18009368a  mov     rcx, rbx
0x18009368d  mov     rax, [rax+120h]
0x180093694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093699  mov     rcx, [rsp+88h]; this
0x1800936a1  test    eax, eax
0x1800936a3  js      short loc_180093707
0x1800936a5  mov     rcx, rdi
0x1800936a8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800936ad  xor     r8d, r8d; bFailIfExists
0x1800936b0  mov     rdx, rax; lpNewFileName
0x1800936b3  mov     rcx, [rsp+88h+lpExistingFileName]; lpExistingFileName
0x1800936b8  call    cs:__imp_CopyFileW
0x1800936be  mov     rcx, [rsp+88h]; this
0x1800936c6  test    eax, eax
0x1800936c8  jz      short loc_1800936F5
0x1800936ca  lea     rcx, [rsp+88h+lpExistingFileName]
0x1800936cf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800936d4  nop
0x1800936d5  mov     rcx, rsi
0x1800936d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800936dd  mov     rax, rdi
0x1800936e0  mov     rcx, [rsp+88h+var_28]
0x1800936e5  xor     rcx, rsp; StackCookie
0x1800936e8  call    __security_check_cookie
0x1800936ed  add     rsp, 70h
0x1800936f1  pop     rdi
0x1800936f2  pop     rsi
0x1800936f3  pop     rbx
0x1800936f4  retn
0x1800936f5  lea     r8, aPcshellShellCl_28; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800936fc  mov     edx, 254h; void *
0x180093701  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180093707  mov     r9d, eax; char *
0x18009370a  lea     r8, aPcshellShellCl_28; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x180093711  mov     edx, 252h; void *
0x180093716  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
