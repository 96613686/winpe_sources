# Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18008e138`
- end: `0x18008e33e`
- name: `?CreateFolderHierarchyWithAcls@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `518`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18008e0c0`
- `0x18008e664`

## callees

- `0x18000b8f0`
- `0x180067e34`
- `0x180067e54`
- `0x180077de0`
- `0x180080bac`
- `0x180084574`
- `0x18008e048`
- `0x18008e138`
- `0x18008e344`
- `0x18008ee38`
- `0x18008eec8`
- `0x18008ef2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e293`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008e283`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008e283`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008e1ad`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008e1ad`

## string_xrefs

- `0x18008e1d1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18008e2c4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls(
        __int64 a1,
        __int64 a2)
{
  struct _SECURITY_ATTRIBUTES *v3; // rsi
  const WCHAR *v4; // rax
  BOOL v5; // ebx
  const char *v6; // r9
  unsigned int LastError; // ebx
  __int64 first_of; // rdi
  __int64 v10; // rdx
  char v11; // bl
  const WCHAR *v12; // rax
  signed int v13; // eax
  unsigned int v14; // ebx
  int v15[2]; // [rsp+20h] [rbp-88h] BYREF
  __int128 v16; // [rsp+28h] [rbp-80h] BYREF
  __int64 v17; // [rsp+38h] [rbp-70h]
  int *v18; // [rsp+40h] [rbp-68h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-60h] BYREF
  char v20; // [rsp+50h] [rbp-58h]
  _BYTE v21[32]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v16 = 0;
  v17 = 0;
  *(_QWORD *)v15 = 0;
  if ( *(_QWORD *)(a2 + 16) )
  {
    v18 = v15;
    SecurityDescriptor = 0;
    v20 = 1;
    v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v5 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v4, 1u, &SecurityDescriptor, 0);
    wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v18);
    if ( !v5 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x87,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
                    v6);
      wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        v15,
        0);
      return LastError;
    }
    LODWORD(v16) = 24;
    *((_QWORD *)&v16 + 1) = *(_QWORD *)v15;
    LODWORD(v17) = 0;
    v3 = (struct _SECURITY_ATTRIBUTES *)&v16;
  }
  else
  {
    v3 = 0;
  }
  first_of = 0;
  while ( 1 )
  {
    first_of = std::wstring::find_first_of(a1, L"\\/", first_of + 1);
    std::wstring::substr(a1, &v18, 0, first_of);
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v18);
    std::wstring::wstring(v21, v10);
    v11 = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(v21);
    std::wstring::_Tidy_deallocate(v21);
    if ( !v11 )
    {
      v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v18);
      if ( !CreateDirectoryW(v12, v3) )
      {
        v13 = GetLastError();
        v14 = v13;
        if ( v13 != 183 )
          break;
      }
    }
    std::wstring::_Tidy_deallocate(&v18);
    if ( first_of == -1 )
    {
      wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        v15,
        0);
      return 0;
    }
  }
  if ( v13 > 0 )
    v14 = (unsigned __int16)v13 | 0x80070000;
  if ( (v14 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
      (const char *)v14,
      v15[0]);
  std::wstring::_Tidy_deallocate(&v18);
  wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
    v15,
    0);
  return v14;
}

```

## disassembly

```asm
0x18008e138  mov     [rsp+arg_10], rbx
0x18008e13d  push    rsi
0x18008e13e  push    rdi
0x18008e13f  push    r14
0x18008e141  sub     rsp, 90h
0x18008e148  mov     rax, cs:__security_cookie
0x18008e14f  xor     rax, rsp
0x18008e152  mov     [rsp+0A8h+var_28], rax
0x18008e15a  mov     r14, rcx
0x18008e15d  xorps   xmm0, xmm0
0x18008e160  xor     eax, eax
0x18008e162  movups  [rsp+0A8h+var_80], xmm0
0x18008e167  mov     [rsp+0A8h+var_70], rax
0x18008e16c  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18008e171  cmp     [rdx+10h], rax
0x18008e175  jnz     short loc_18008E17E
0x18008e177  xor     esi, esi
0x18008e179  jmp     loc_18008E216
0x18008e17e  lea     rax, [rsp+0A8h+var_88]
0x18008e183  mov     [rsp+0A8h+var_68], rax
0x18008e188  mov     [rsp+0A8h+SecurityDescriptor], 0
0x18008e191  mov     [rsp+0A8h+var_58], 1
0x18008e196  mov     rcx, rdx
0x18008e199  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008e19e  xor     r9d, r9d; SecurityDescriptorSize
0x18008e1a1  lea     r8, [rsp+0A8h+SecurityDescriptor]; SecurityDescriptor
0x18008e1a6  lea     edx, [r9+1]; StringSDRevision
0x18008e1aa  mov     rcx, rax; StringSecurityDescriptor
0x18008e1ad  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18008e1b4  nop     dword ptr [rax+rax+00h]
0x18008e1b9  mov     ebx, eax
0x18008e1bb  lea     rcx, [rsp+0A8h+var_68]
0x18008e1c0  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18008e1c5  test    ebx, ebx
0x18008e1c7  jnz     short loc_18008E1F7
0x18008e1c9  mov     rcx, [rsp+0A8h]; this
0x18008e1d1  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008e1d8  mov     edx, 87h; void *
0x18008e1dd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008e1e2  mov     ebx, eax
0x18008e1e4  xor     edx, edx
0x18008e1e6  lea     rcx, [rsp+0A8h+var_88]
0x18008e1eb  call    ?reset@?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_SECURITY_DESCRIPTOR *)
0x18008e1f0  mov     eax, ebx
0x18008e1f2  jmp     loc_18008E319
0x18008e1f7  mov     dword ptr [rsp+0A8h+var_80], 18h
0x18008e1ff  mov     rax, qword ptr [rsp+0A8h+var_88]
0x18008e204  mov     qword ptr [rsp+0A8h+var_80+8], rax
0x18008e209  mov     dword ptr [rsp+0A8h+var_70], 0
0x18008e211  lea     rsi, [rsp+0A8h+var_80]
0x18008e216  xor     edi, edi
0x18008e218  lea     r8, [rdi+1]
0x18008e21c  lea     rdx, asc_18022B41C; "\\/"
0x18008e223  mov     rcx, r14
0x18008e226  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_first_of(ushort const * const,unsigned __int64)
0x18008e22b  mov     rdi, rax
0x18008e22e  mov     r9, rax
0x18008e231  xor     r8d, r8d
0x18008e234  lea     rdx, [rsp+0A8h+var_68]
0x18008e239  mov     rcx, r14
0x18008e23c  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18008e241  nop
0x18008e242  lea     rcx, [rsp+0A8h+var_68]
0x18008e247  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008e24c  mov     rdx, rax
0x18008e24f  lea     rcx, [rsp+0A8h+var_48]
0x18008e254  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008e259  lea     rcx, [rsp+0A8h+var_48]
0x18008e25e  call    ?DirectoryExists@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(std::wstring const &)
0x18008e263  mov     bl, al
0x18008e265  lea     rcx, [rsp+0A8h+var_48]
0x18008e26a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008e26f  test    bl, bl
0x18008e271  jnz     short loc_18008E2F1
0x18008e273  lea     rcx, [rsp+0A8h+var_68]
0x18008e278  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008e27d  mov     rcx, rax; lpPathName
0x18008e280  mov     rdx, rsi; lpSecurityAttributes
0x18008e283  call    cs:__imp_CreateDirectoryW
0x18008e28a  nop     dword ptr [rax+rax+00h]
0x18008e28f  test    eax, eax
0x18008e291  jnz     short loc_18008E2F1
0x18008e293  call    cs:__imp_GetLastError
0x18008e29a  nop     dword ptr [rax+rax+00h]
0x18008e29f  mov     ebx, eax
0x18008e2a1  cmp     eax, 0B7h
0x18008e2a6  jz      short loc_18008E2F1
0x18008e2a8  test    eax, eax
0x18008e2aa  jle     short loc_18008E2B5
0x18008e2ac  movzx   ebx, ax
0x18008e2af  or      ebx, 80070000h
0x18008e2b5  test    ebx, ebx
0x18008e2b7  jns     short loc_18008E2D6
0x18008e2b9  mov     rcx, [rsp+0A8h]; this
0x18008e2c1  mov     r9d, ebx; char *
0x18008e2c4  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008e2cb  mov     edx, 9Ch; void *
0x18008e2d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e2d5  nop
0x18008e2d6  lea     rcx, [rsp+0A8h+var_68]
0x18008e2db  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008e2e0  nop
0x18008e2e1  xor     edx, edx
0x18008e2e3  lea     rcx, [rsp+0A8h+var_88]
0x18008e2e8  call    ?reset@?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_SECURITY_DESCRIPTOR *)
0x18008e2ed  mov     eax, ebx
0x18008e2ef  jmp     short loc_18008E319
0x18008e2f1  lea     rcx, [rsp+0A8h+var_68]
0x18008e2f6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008e2fb  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18008e2ff  jnz     loc_18008E218
0x18008e305  xor     edx, edx
0x18008e307  lea     rcx, [rsp+0A8h+var_88]
0x18008e30c  call    ?reset@?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_SECURITY_DESCRIPTOR *)
0x18008e311  xor     eax, eax
0x18008e313  jmp     short loc_18008E319
0x18008e315  mov     eax, [rsp+0A8h+var_88]
0x18008e319  mov     rcx, [rsp+0A8h+var_28]
0x18008e321  xor     rcx, rsp; StackCookie
0x18008e324  call    __security_check_cookie
0x18008e329  mov     rbx, [rsp+0A8h+arg_10]
0x18008e331  add     rsp, 90h
0x18008e338  pop     r14
0x18008e33a  pop     rdi
0x18008e33b  pop     rsi
0x18008e33c  retn
```
