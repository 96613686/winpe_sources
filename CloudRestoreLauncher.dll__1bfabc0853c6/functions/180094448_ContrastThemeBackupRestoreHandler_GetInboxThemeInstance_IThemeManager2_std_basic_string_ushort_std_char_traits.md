# ContrastThemeBackupRestoreHandler::GetInboxThemeInstance(IThemeManager2 *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180094448`
- end: `0x1800945bc`
- name: `?GetInboxThemeInstance@ContrastThemeBackupRestoreHandler@@AEAA?AV?$com_ptr_t@UITheme@@Uerr_exception_policy@wil@@@wil@@PEAUIThemeManager2@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `372`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64 *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800929c8`
- `0x180093050`

## callees

- `0x18001649c`
- `0x18001cf84`
- `0x18001cfa4`
- `0x18001ffa8`
- `0x180094448`
- `0x18012d010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180094513`
- `KERNEL32!CompareStringOrdinal` at `0x180094513`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall ContrastThemeBackupRestoreHandler::GetInboxThemeInstance(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3,
        __int64 a4)
{
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  const WCHAR *v13; // rax
  _QWORD *v15; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-20h]
  LPCWCH lpString1; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  int v19; // [rsp+60h] [rbp+20h] BYREF
  int v20; // [rsp+64h] [rbp+24h]
  _QWORD *v21; // [rsp+70h] [rbp+30h] BYREF

  v20 = HIDWORD(a1);
  v19 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, int *))(*a3 + 64))(a3, &v19);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\contrastthemebackuprestorehandler.cpp",
      (const char *)(unsigned int)v7,
      bIgnoreCase);
  v8 = 0;
  if ( v19 <= 0 )
  {
LABEL_7:
    *a2 = 0;
  }
  else
  {
    while ( 1 )
    {
      v9 = *a3;
      v21 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD **))(v9 + 72))(a3, v8, &v21);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x231,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\contrastthemebackuprestorehandler.cpp",
          (const char *)(unsigned int)v10,
          bIgnoreCase);
      lpString1 = 0;
      v11 = *v21;
      lpString1 = 0;
      v12 = (*(__int64 (__fastcall **)(_QWORD *, LPCWCH *))(v11 + 24))(v21, &lpString1);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x234,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\contrastthemebackuprestorehandler.cpp",
          (const char *)(unsigned int)v12,
          bIgnoreCase);
      v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
      if ( CompareStringOrdinal(lpString1, -1, v13, -1, 1) == 2 )
        break;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
      wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&v21);
      if ( (int)++v8 >= v19 )
        goto LABEL_7;
    }
    v15 = v21;
    v21 = 0;
    *a2 = v15;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&v21);
  }
  return a2;
}

```

## disassembly

```asm
0x180094448  mov     [rsp-18h+arg_8], rbx
0x18009444d  mov     [rsp-18h+arg_18], rsi
0x180094452  mov     [rsp-18h+arg_0], rcx
0x180094457  push    rbp
0x180094458  push    rdi
0x180094459  push    r14
0x18009445b  mov     rbp, rsp
0x18009445e  sub     rsp, 40h
0x180094462  mov     r14, r9
0x180094465  mov     rsi, r8
0x180094468  mov     rbx, rdx
0x18009446b  mov     dword ptr [rbp+arg_0], 0
0x180094472  mov     rax, [r8]
0x180094475  lea     rdx, [rbp+arg_0]
0x180094479  mov     rcx, r8
0x18009447c  mov     rax, [rax+40h]
0x180094480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094485  mov     rcx, [rbp+18h]; this
0x180094489  test    eax, eax
0x18009448b  js      loc_1800945A7
0x180094491  xor     edi, edi
0x180094493  cmp     dword ptr [rbp+arg_0], edi
0x180094496  jle     loc_18009453C
0x18009449c  mov     rax, [rsi]
0x18009449f  mov     [rbp+arg_10], 0
0x1800944a7  lea     r8, [rbp+arg_10]
0x1800944ab  mov     edx, edi
0x1800944ad  mov     rcx, rsi
0x1800944b0  mov     rax, [rax+48h]
0x1800944b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800944b9  mov     rcx, [rbp+18h]; this
0x1800944bd  test    eax, eax
0x1800944bf  js      loc_180094592
0x1800944c5  mov     [rbp+lpString1], 0
0x1800944cd  mov     rcx, [rbp+arg_10]
0x1800944d1  mov     rax, [rcx]
0x1800944d4  mov     [rbp+lpString1], 0
0x1800944dc  lea     rdx, [rbp+lpString1]
0x1800944e0  mov     rax, [rax+18h]
0x1800944e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800944e9  mov     rcx, [rbp+18h]; this
0x1800944ed  test    eax, eax
0x1800944ef  js      loc_18009457D
0x1800944f5  mov     rcx, r14
0x1800944f8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800944fd  mov     r8, rax; lpString2
0x180094500  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x180094508  or      r9d, 0FFFFFFFFh; cchCount2
0x18009450c  or      edx, r9d; cchCount1
0x18009450f  mov     rcx, [rbp+lpString1]; lpString1
0x180094513  call    cs:__imp_CompareStringOrdinal
0x180094519  cmp     eax, 2
0x18009451c  jz      short loc_180094559
0x18009451e  lea     rcx, [rbp+lpString1]
0x180094522  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180094527  nop
0x180094528  lea     rcx, [rbp+arg_10]
0x18009452c  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x180094531  inc     edi
0x180094533  cmp     edi, dword ptr [rbp+arg_0]
0x180094536  jl      loc_18009449C
0x18009453c  mov     qword ptr [rbx], 0
0x180094543  mov     rax, rbx
0x180094546  mov     rbx, [rsp+40h+arg_8]
0x18009454b  mov     rsi, [rsp+40h+arg_18]
0x180094550  add     rsp, 40h
0x180094554  pop     r14
0x180094556  pop     rdi
0x180094557  pop     rbp
0x180094558  retn
0x180094559  mov     rax, [rbp+arg_10]
0x18009455d  mov     [rbp+arg_10], 0
0x180094565  mov     [rbx], rax
0x180094568  lea     rcx, [rbp+lpString1]
0x18009456c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180094571  nop
0x180094572  lea     rcx, [rbp+arg_10]
0x180094576  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x18009457b  jmp     short loc_180094543
0x18009457d  mov     r9d, eax; char *
0x180094580  lea     r8, aPcshellShellCl_28; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x180094587  mov     edx, 234h; void *
0x18009458c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180094592  mov     r9d, eax; char *
0x180094595  lea     r8, aPcshellShellCl_28; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x18009459c  mov     edx, 231h; void *
0x1800945a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800945a7  mov     r9d, eax; char *
0x1800945aa  lea     r8, aPcshellShellCl_28; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800945b1  mov     edx, 22Ch; void *
0x1800945b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
