# Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18008d04c`
- end: `0x18008d267`
- name: `?CreateFolderHierarchyWithAcls@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `539`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18008cfd4`
- `0x18008d578`

## callees

- `0x18000b820`
- `0x180067a34`
- `0x180067a54`
- `0x18007755c`
- `0x18008019c`
- `0x1800839bc`
- `0x18008cf40`
- `0x18008d04c`
- `0x18008d270`
- `0x18008dd4c`
- `0x18008de14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d1a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d1a8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008d19e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008d19e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d105`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d203`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d234`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d105`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d203`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d234`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008d0c1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008d0c1`

## string_xrefs

- `0x18008d0df`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18008d1d3`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls(
        __int64 a1,
        __int64 a2)
{
  struct _SECURITY_ATTRIBUTES *v3; // rsi
  const WCHAR *v4; // rax
  BOOL v5; // ebx
  const char *v6; // r9
  unsigned int LastError; // ebx
  HLOCAL v8; // rcx
  __int64 first_of; // rdi
  __int64 v11; // rdx
  char v12; // bl
  const WCHAR *v13; // rax
  signed int v14; // eax
  unsigned int v15; // ebx
  HLOCAL v16; // rcx
  HLOCAL v17; // rcx
  HLOCAL hMem; // [rsp+20h] [rbp-88h] BYREF
  __int128 v19; // [rsp+28h] [rbp-80h] BYREF
  __int64 v20; // [rsp+38h] [rbp-70h]
  HLOCAL *p_hMem; // [rsp+40h] [rbp-68h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-60h] BYREF
  char v23; // [rsp+50h] [rbp-58h]
  _BYTE v24[32]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v19 = 0;
  v20 = 0;
  hMem = 0;
  if ( *(_QWORD *)(a2 + 16) )
  {
    p_hMem = &hMem;
    SecurityDescriptor = 0;
    v23 = 1;
    v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v5 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v4, 1u, &SecurityDescriptor, 0);
    wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( !v5 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x87,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
                    v6);
      v8 = hMem;
      hMem = 0;
      if ( v8 )
        LocalFree(v8);
      return LastError;
    }
    LODWORD(v19) = 24;
    *((_QWORD *)&v19 + 1) = hMem;
    LODWORD(v20) = 0;
    v3 = (struct _SECURITY_ATTRIBUTES *)&v19;
  }
  else
  {
    v3 = 0;
  }
  first_of = 0;
  do
  {
    first_of = std::wstring::find_first_of(a1, L"\\/", first_of + 1);
    std::wstring::substr(a1, &p_hMem, 0, first_of);
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&p_hMem);
    std::wstring::wstring(v24, v11);
    v12 = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(v24);
    std::wstring::_Tidy_deallocate(v24);
    if ( !v12 )
    {
      v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&p_hMem);
      if ( !CreateDirectoryW(v13, v3) )
      {
        v14 = GetLastError();
        v15 = v14;
        if ( v14 != 183 )
        {
          if ( v14 > 0 )
            v15 = (unsigned __int16)v14 | 0x80070000;
          if ( (v15 & 0x80000000) != 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9C,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
              (const char *)v15,
              (int)hMem);
          std::wstring::_Tidy_deallocate(&p_hMem);
          v16 = hMem;
          hMem = 0;
          if ( v16 )
            LocalFree(v16);
          return v15;
        }
      }
    }
    std::wstring::_Tidy_deallocate(&p_hMem);
  }
  while ( first_of != -1 );
  v17 = hMem;
  hMem = 0;
  if ( v17 )
    LocalFree(v17);
  return 0;
}

```

## disassembly

```asm
0x18008d04c  mov     [rsp+arg_10], rbx
0x18008d051  push    rsi
0x18008d052  push    rdi
0x18008d053  push    r14
0x18008d055  sub     rsp, 90h
0x18008d05c  mov     rax, cs:__security_cookie
0x18008d063  xor     rax, rsp
0x18008d066  mov     [rsp+0A8h+var_28], rax
0x18008d06e  mov     r14, rcx
0x18008d071  xorps   xmm0, xmm0
0x18008d074  xor     eax, eax
0x18008d076  movups  [rsp+0A8h+var_80], xmm0
0x18008d07b  mov     [rsp+0A8h+var_70], rax
0x18008d080  mov     [rsp+0A8h+hMem], rax; int
0x18008d085  cmp     [rdx+10h], rax
0x18008d089  jnz     short loc_18008D092
0x18008d08b  xor     esi, esi
0x18008d08d  jmp     loc_18008D131
0x18008d092  lea     rax, [rsp+0A8h+hMem]
0x18008d097  mov     [rsp+0A8h+var_68], rax
0x18008d09c  mov     [rsp+0A8h+SecurityDescriptor], 0
0x18008d0a5  mov     [rsp+0A8h+var_58], 1
0x18008d0aa  mov     rcx, rdx
0x18008d0ad  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008d0b2  xor     r9d, r9d; SecurityDescriptorSize
0x18008d0b5  lea     r8, [rsp+0A8h+SecurityDescriptor]; SecurityDescriptor
0x18008d0ba  lea     edx, [r9+1]; StringSDRevision
0x18008d0be  mov     rcx, rax; StringSecurityDescriptor
0x18008d0c1  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18008d0c7  mov     ebx, eax
0x18008d0c9  lea     rcx, [rsp+0A8h+var_68]
0x18008d0ce  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18008d0d3  test    ebx, ebx
0x18008d0d5  jnz     short loc_18008D112
0x18008d0d7  mov     rcx, [rsp+0A8h]; this
0x18008d0df  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008d0e6  mov     edx, 87h; void *
0x18008d0eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008d0f0  mov     ebx, eax
0x18008d0f2  mov     rcx, [rsp+0A8h+hMem]; hMem
0x18008d0f7  mov     [rsp+0A8h+hMem], 0
0x18008d100  test    rcx, rcx
0x18008d103  jz      short loc_18008D10B
0x18008d105  call    cs:__imp_LocalFree
0x18008d10b  mov     eax, ebx
0x18008d10d  jmp     loc_18008D242
0x18008d112  mov     dword ptr [rsp+0A8h+var_80], 18h
0x18008d11a  mov     rax, [rsp+0A8h+hMem]
0x18008d11f  mov     qword ptr [rsp+0A8h+var_80+8], rax
0x18008d124  mov     dword ptr [rsp+0A8h+var_70], 0
0x18008d12c  lea     rsi, [rsp+0A8h+var_80]
0x18008d131  xor     edi, edi
0x18008d133  lea     r8, [rdi+1]
0x18008d137  lea     rdx, asc_1802253DC; "\\/"
0x18008d13e  mov     rcx, r14
0x18008d141  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_first_of(ushort const * const,unsigned __int64)
0x18008d146  mov     rdi, rax
0x18008d149  mov     r9, rax
0x18008d14c  xor     r8d, r8d
0x18008d14f  lea     rdx, [rsp+0A8h+var_68]
0x18008d154  mov     rcx, r14
0x18008d157  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18008d15c  nop
0x18008d15d  lea     rcx, [rsp+0A8h+var_68]
0x18008d162  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008d167  mov     rdx, rax
0x18008d16a  lea     rcx, [rsp+0A8h+var_48]
0x18008d16f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008d174  lea     rcx, [rsp+0A8h+var_48]
0x18008d179  call    ?DirectoryExists@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(std::wstring const &)
0x18008d17e  mov     bl, al
0x18008d180  lea     rcx, [rsp+0A8h+var_48]
0x18008d185  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d18a  test    bl, bl
0x18008d18c  jnz     short loc_18008D20D
0x18008d18e  lea     rcx, [rsp+0A8h+var_68]
0x18008d193  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008d198  mov     rcx, rax; lpPathName
0x18008d19b  mov     rdx, rsi; lpSecurityAttributes
0x18008d19e  call    cs:__imp_CreateDirectoryW
0x18008d1a4  test    eax, eax
0x18008d1a6  jnz     short loc_18008D20D
0x18008d1a8  call    cs:__imp_GetLastError
0x18008d1ae  mov     ebx, eax
0x18008d1b0  cmp     eax, 0B7h
0x18008d1b5  jz      short loc_18008D20D
0x18008d1b7  test    eax, eax
0x18008d1b9  jle     short loc_18008D1C4
0x18008d1bb  movzx   ebx, ax
0x18008d1be  or      ebx, 80070000h
0x18008d1c4  test    ebx, ebx
0x18008d1c6  jns     short loc_18008D1E5
0x18008d1c8  mov     rcx, [rsp+0A8h]; this
0x18008d1d0  mov     r9d, ebx; char *
0x18008d1d3  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008d1da  mov     edx, 9Ch; void *
0x18008d1df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d1e4  nop
0x18008d1e5  lea     rcx, [rsp+0A8h+var_68]
0x18008d1ea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d1ef  nop
0x18008d1f0  mov     rcx, [rsp+0A8h+hMem]; hMem
0x18008d1f5  mov     [rsp+0A8h+hMem], 0
0x18008d1fe  test    rcx, rcx
0x18008d201  jz      short loc_18008D209
0x18008d203  call    cs:__imp_LocalFree
0x18008d209  mov     eax, ebx
0x18008d20b  jmp     short loc_18008D242
0x18008d20d  lea     rcx, [rsp+0A8h+var_68]
0x18008d212  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d217  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18008d21b  jnz     loc_18008D133
0x18008d221  mov     rcx, [rsp+0A8h+hMem]; hMem
0x18008d226  mov     [rsp+0A8h+hMem], 0
0x18008d22f  test    rcx, rcx
0x18008d232  jz      short loc_18008D23A
0x18008d234  call    cs:__imp_LocalFree
0x18008d23a  xor     eax, eax
0x18008d23c  jmp     short loc_18008D242
0x18008d23e  mov     eax, dword ptr [rsp+0A8h+hMem]
0x18008d242  mov     rcx, [rsp+0A8h+var_28]
0x18008d24a  xor     rcx, rsp; StackCookie
0x18008d24d  call    __security_check_cookie
0x18008d252  mov     rbx, [rsp+0A8h+arg_10]
0x18008d25a  add     rsp, 90h
0x18008d261  pop     r14
0x18008d263  pop     rdi
0x18008d264  pop     rsi
0x18008d265  retn
```
