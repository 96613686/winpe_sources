# ForEachSettingDirectoryHandle(std::filesystem::path const &,winrt::delegate<void (std::filesystem::path const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)>)

- ea: `0x180029644`
- end: `0x1800299ed`
- name: `?ForEachSettingDirectoryHandle@@YAJAEBVpath@filesystem@std@@U?$delegate@$$A6AXAEBVpath@filesystem@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z@winrt@@@Z`
- size: `937`
- prototype: `__int64 __fastcall(struct std::filesystem::path *, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002bf50`

## callees

- `0x180002590`
- `0x18000ab14`
- `0x18000f29c`
- `0x180013890`
- `0x180024f28`
- `0x18002869c`
- `0x1800290a4`
- `0x180029644`
- `0x18002c7c0`
- `0x18002dbb4`
- `0x18002e0d0`
- `0x18002e12c`
- `0x180033010`

## string_xrefs

- `0x1800296da`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`
- `0x180029765`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
__int64 __fastcall ForEachSettingDirectoryHandle(struct std::filesystem::path *a1, _QWORD *a2)
{
  unsigned int *any_status; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  int DirHandle; // eax
  unsigned int v9; // r14d
  volatile signed __int32 *v10; // rsi
  int LockFile; // eax
  volatile signed __int32 *v12; // rsi
  __int64 v13; // r8
  std::filesystem *v14; // rcx
  const struct std::filesystem::path *v15; // r9
  int v16; // edx
  bool v17; // al
  volatile signed __int32 *v18; // rsi
  volatile signed __int32 *v19; // rsi
  volatile signed __int32 *v20; // rsi
  volatile signed __int32 *v21; // rsi
  __int128 v22; // [rsp+20h] [rbp-59h] BYREF
  __int128 v23; // [rsp+30h] [rbp-49h] BYREF
  char v24[16]; // [rsp+40h] [rbp-39h] BYREF
  char v25[4]; // [rsp+50h] [rbp-29h] BYREF
  void ***v26; // [rsp+58h] [rbp-21h]
  _QWORD *v27; // [rsp+60h] [rbp-19h]
  __int128 v28; // [rsp+68h] [rbp-11h] BYREF
  __int64 v29; // [rsp+78h] [rbp-1h]
  __int64 v30; // [rsp+80h] [rbp+7h]
  _BYTE Src[16]; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v32; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v27 = a2;
  any_status = (unsigned int *)std::filesystem::_Get_any_status(v24, a1);
  v5 = *any_status;
  v6 = any_status[2];
  if ( (_DWORD)v6 )
  {
    if ( (((_DWORD)v5 - 1) & 0xFFFFFFF7) != 0 )
      std::filesystem::_Throw_fs_error(v5, v6, a1);
    goto LABEL_5;
  }
  if ( (_DWORD)v5 != 3 )
  {
LABEL_5:
    if ( *a2 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
    return 2147942487LL;
  }
  v22 = 0;
  DirHandle = TryGetDirHandle(a1, &v22);
  v9 = DirHandle;
  if ( DirHandle < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
      (const char *)(unsigned int)DirHandle,
      v22);
    v10 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
    if ( !*((_QWORD *)&v22 + 1) )
    {
LABEL_13:
      if ( *a2 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
      return v9;
    }
LABEL_10:
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
    goto LABEL_13;
  }
  v23 = 0;
  LockFile = CreateAndGetLockFile((_QWORD **)&v22, &v23);
  v9 = LockFile;
  if ( LockFile < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
      (const char *)(unsigned int)LockFile,
      v22);
    v12 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
    if ( *((_QWORD *)&v23 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v23 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    v10 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
    if ( !*((_QWORD *)&v22 + 1) )
      goto LABEL_13;
    goto LABEL_10;
  }
  v13 = -1;
  do
    ++v13;
  while ( aSettingsDat[v13] );
  v28 = 0;
  v29 = 0;
  v30 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v28, L"settings.dat", v13);
  std::filesystem::operator/(Src, a1, (std::filesystem *)&v28);
  std::wstring::~wstring(&v28);
  if ( !v32 )
    goto LABEL_42;
  v14 = (std::filesystem *)std::filesystem::_Get_any_status(v24, Src);
  v16 = *((_DWORD *)v14 + 2);
  *(_DWORD *)v25 = v16;
  v26 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  if ( *(_DWORD *)v14 )
  {
    v17 = *(_DWORD *)v14 != 1;
  }
  else
  {
    v17 = 0;
    if ( v16 )
      std::filesystem::_Throw_fs_error(v14, v25, (const struct std::error_code *)Src, v15);
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(_QWORD, _BYTE *, __int128 *))(*(_QWORD *)*a2 + 24LL))(*a2, Src, &v23);
    std::wstring::~wstring(Src);
    v18 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
    if ( *((_QWORD *)&v23 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v23 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    v19 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
    if ( *((_QWORD *)&v22 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    if ( *a2 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
    return 0;
  }
  else
  {
LABEL_42:
    std::wstring::~wstring(Src);
    v20 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
    if ( *((_QWORD *)&v23 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v23 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
    v21 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
    if ( *((_QWORD *)&v22 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
    if ( *a2 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
    return 2147942402LL;
  }
}

```

## disassembly

```asm
0x180029644  mov     [rsp-8+arg_10], rbx
0x180029649  push    rbp
0x18002964a  push    rsi
0x18002964b  push    rdi
0x18002964c  push    r14
0x18002964e  push    r15
0x180029650  lea     rbp, [rsp-37h]
0x180029655  sub     rsp, 0B0h
0x18002965c  mov     rax, cs:__security_cookie
0x180029663  xor     rax, rsp
0x180029666  mov     [rbp+57h+var_28], rax
0x18002966a  mov     rdi, rdx
0x18002966d  mov     rsi, rcx
0x180029670  mov     [rbp+57h+var_70], rdx
0x180029674  xor     r15d, r15d
0x180029677  mov     rdx, rcx
0x18002967a  lea     rcx, [rbp+57h+var_90]
0x18002967e  call    ?_Get_any_status@filesystem@std@@YA?AU_File_status_and_error@12@AEBVpath@12@W4__std_fs_stats_flags@@@Z; std::filesystem::_Get_any_status(std::filesystem::path const &,__std_fs_stats_flags)
0x180029683  mov     ecx, [rax]
0x180029685  mov     edx, [rax+8]
0x180029688  test    edx, edx
0x18002968a  jz      short loc_18002969C
0x18002968c  lea     eax, [rcx-1]
0x18002968f  test    eax, 0FFFFFFF7h
0x180029694  jnz     loc_1800299D6
0x18002969a  jmp     short loc_1800296A1
0x18002969c  cmp     ecx, 3
0x18002969f  jz      short loc_1800296B8
0x1800296a1  cmp     [rdi], r15
0x1800296a4  jz      short loc_1800296AE
0x1800296a6  mov     rcx, rdi
0x1800296a9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800296ae  mov     eax, 80070057h
0x1800296b3  jmp     loc_1800299B3
0x1800296b8  xorps   xmm1, xmm1
0x1800296bb  movdqu  [rbp+57h+var_B0], xmm1
0x1800296c0  lea     rdx, [rbp+57h+var_B0]
0x1800296c4  mov     rcx, rsi; struct std::filesystem::path *
0x1800296c7  call    ?TryGetDirHandle@@YAJAEBVpath@filesystem@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; TryGetDirHandle(std::filesystem::path const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)
0x1800296cc  mov     r14d, eax
0x1800296cf  test    eax, eax
0x1800296d1  jns     short loc_180029742
0x1800296d3  mov     rcx, [rbp+5Fh]; this
0x1800296d7  mov     r9d, eax; char *
0x1800296da  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x1800296e1  mov     edx, 163h; void *
0x1800296e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800296eb  nop
0x1800296ec  mov     rsi, qword ptr [rbp+57h+var_B0+8]
0x1800296f0  test    rsi, rsi
0x1800296f3  jz      short loc_18002972D
0x1800296f5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800296f9  mov     eax, ebx
0x1800296fb  lock xadd [rsi+8], eax
0x180029700  add     eax, ebx
0x180029702  jnz     short loc_18002972D
0x180029704  mov     rax, [rsi]
0x180029707  mov     rcx, rsi
0x18002970a  mov     rax, [rax]
0x18002970d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029712  mov     eax, ebx
0x180029714  lock xadd [rsi+0Ch], eax
0x180029719  add     eax, ebx
0x18002971b  jnz     short loc_18002972D
0x18002971d  mov     rax, [rsi]
0x180029720  mov     rcx, rsi
0x180029723  mov     rax, [rax+8]
0x180029727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002972c  nop
0x18002972d  cmp     [rdi], r15
0x180029730  jz      short loc_18002973A
0x180029732  mov     rcx, rdi
0x180029735  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002973a  mov     eax, r14d
0x18002973d  jmp     loc_1800299B3
0x180029742  xorps   xmm1, xmm1
0x180029745  movdqu  [rbp+57h+var_A0], xmm1
0x18002974a  lea     rdx, [rbp+57h+var_A0]
0x18002974e  lea     rcx, [rbp+57h+var_B0]
0x180029752  call    ?CreateAndGetLockFile@@YAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@0@Z; CreateAndGetLockFile(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)
0x180029757  mov     r14d, eax
0x18002975a  test    eax, eax
0x18002975c  jns     short loc_1800297CA
0x18002975e  mov     rcx, [rbp+5Fh]; this
0x180029762  mov     r9d, eax; char *
0x180029765  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002976c  mov     edx, 166h; void *
0x180029771  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029776  nop
0x180029777  mov     rsi, qword ptr [rbp+57h+var_A0+8]
0x18002977b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002977f  test    rsi, rsi
0x180029782  jz      short loc_1800297B8
0x180029784  mov     eax, ebx
0x180029786  lock xadd [rsi+8], eax
0x18002978b  add     eax, ebx
0x18002978d  jnz     short loc_1800297B8
0x18002978f  mov     rax, [rsi]
0x180029792  mov     rcx, rsi
0x180029795  mov     rax, [rax]
0x180029798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002979d  mov     eax, ebx
0x18002979f  lock xadd [rsi+0Ch], eax
0x1800297a4  add     eax, ebx
0x1800297a6  jnz     short loc_1800297B8
0x1800297a8  mov     rax, [rsi]
0x1800297ab  mov     rcx, rsi
0x1800297ae  mov     rax, [rax+8]
0x1800297b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297b7  nop
0x1800297b8  mov     rsi, qword ptr [rbp+57h+var_B0+8]
0x1800297bc  test    rsi, rsi
0x1800297bf  jz      loc_18002972D
0x1800297c5  jmp     loc_1800296F9
0x1800297ca  mov     rdx, cs:off_180034630; "settings.dat"
0x1800297d1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800297d5  mov     r8, rbx
0x1800297d8  inc     r8
0x1800297db  cmp     [rdx+r8*2], r15w
0x1800297e0  jnz     short loc_1800297D8
0x1800297e2  xorps   xmm0, xmm0
0x1800297e5  movups  [rbp+57h+var_68], xmm0
0x1800297e9  mov     [rbp+57h+var_58], r15
0x1800297ed  mov     [rbp+57h+var_50], r15
0x1800297f1  lea     rcx, [rbp+57h+var_68]
0x1800297f5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800297fa  nop
0x1800297fb  lea     r8, [rbp+57h+var_68]; this
0x1800297ff  mov     rdx, rsi; struct std::filesystem::path *
0x180029802  lea     rcx, [rbp+57h+Src]; Src
0x180029806  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18002980b  nop
0x18002980c  lea     rcx, [rbp+57h+var_68]
0x180029810  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029815  cmp     [rbp+57h+var_38], r15
0x180029819  jz      loc_18002991D
0x18002981f  lea     rdx, [rbp+57h+Src]
0x180029823  lea     rcx, [rbp+57h+var_90]
0x180029827  call    ?_Get_any_status@filesystem@std@@YA?AU_File_status_and_error@12@AEBVpath@12@W4__std_fs_stats_flags@@@Z; std::filesystem::_Get_any_status(std::filesystem::path const &,__std_fs_stats_flags)
0x18002982c  mov     rcx, rax; this
0x18002982f  mov     edx, [rax+8]
0x180029832  mov     dword ptr [rbp+57h+var_80], edx
0x180029835  mov     eax, [rbp+57h+var_7C]
0x180029838  mov     [rbp+57h+var_7C], eax
0x18002983b  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180029842  mov     [rbp+57h+var_78], rax
0x180029846  cmp     [rcx], r15d
0x180029849  jz      loc_18002990D
0x18002984f  cmp     dword ptr [rcx], 1
0x180029852  setnz   al
0x180029855  test    al, al
0x180029857  jz      loc_18002991D
0x18002985d  mov     rcx, [rdi]
0x180029860  mov     rax, [rcx]
0x180029863  lea     r8, [rbp+57h+var_A0]
0x180029867  lea     rdx, [rbp+57h+Src]
0x18002986b  mov     rax, [rax+18h]
0x18002986f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029874  nop
0x180029875  lea     rcx, [rbp+57h+Src]
0x180029879  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002987e  nop
0x18002987f  mov     rsi, qword ptr [rbp+57h+var_A0+8]
0x180029883  test    rsi, rsi
0x180029886  jz      short loc_1800298BC
0x180029888  mov     eax, ebx
0x18002988a  lock xadd [rsi+8], eax
0x18002988f  add     eax, ebx
0x180029891  jnz     short loc_1800298BC
0x180029893  mov     rax, [rsi]
0x180029896  mov     rcx, rsi
0x180029899  mov     rax, [rax]
0x18002989c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298a1  mov     eax, ebx
0x1800298a3  lock xadd [rsi+0Ch], eax
0x1800298a8  add     eax, ebx
0x1800298aa  jnz     short loc_1800298BC
0x1800298ac  mov     rax, [rsi]
0x1800298af  mov     rcx, rsi
0x1800298b2  mov     rax, [rax+8]
0x1800298b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298bb  nop
0x1800298bc  mov     rsi, qword ptr [rbp+57h+var_B0+8]
0x1800298c0  test    rsi, rsi
0x1800298c3  jz      short loc_1800298F9
0x1800298c5  mov     eax, ebx
0x1800298c7  lock xadd [rsi+8], eax
0x1800298cc  add     eax, ebx
0x1800298ce  jnz     short loc_1800298F9
0x1800298d0  mov     rax, [rsi]
0x1800298d3  mov     rcx, rsi
0x1800298d6  mov     rax, [rax]
0x1800298d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298de  mov     eax, ebx
0x1800298e0  lock xadd [rsi+0Ch], eax
0x1800298e5  add     eax, ebx
0x1800298e7  jnz     short loc_1800298F9
0x1800298e9  mov     rax, [rsi]
0x1800298ec  mov     rcx, rsi
0x1800298ef  mov     rax, [rax+8]
0x1800298f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298f8  nop
0x1800298f9  cmp     [rdi], r15
0x1800298fc  jz      short loc_180029906
0x1800298fe  mov     rcx, rdi
0x180029901  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180029906  xor     eax, eax
0x180029908  jmp     loc_1800299B3
0x18002990d  mov     al, r15b
0x180029910  test    edx, edx
0x180029912  jnz     loc_1800299DF
0x180029918  jmp     loc_180029855
0x18002991d  lea     rcx, [rbp+57h+Src]
0x180029921  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029926  nop
0x180029927  mov     rsi, qword ptr [rbp+57h+var_A0+8]
0x18002992b  test    rsi, rsi
0x18002992e  jz      short loc_180029964
0x180029930  mov     eax, ebx
0x180029932  lock xadd [rsi+8], eax
0x180029937  add     eax, ebx
0x180029939  jnz     short loc_180029964
0x18002993b  mov     rax, [rsi]
0x18002993e  mov     rcx, rsi
0x180029941  mov     rax, [rax]
0x180029944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029949  mov     eax, ebx
0x18002994b  lock xadd [rsi+0Ch], eax
0x180029950  add     eax, ebx
0x180029952  jnz     short loc_180029964
0x180029954  mov     rax, [rsi]
0x180029957  mov     rcx, rsi
0x18002995a  mov     rax, [rax+8]
0x18002995e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029963  nop
0x180029964  mov     rsi, qword ptr [rbp+57h+var_B0+8]
0x180029968  test    rsi, rsi
0x18002996b  jz      short loc_1800299A1
0x18002996d  mov     eax, ebx
0x18002996f  lock xadd [rsi+8], eax
0x180029974  add     eax, ebx
0x180029976  jnz     short loc_1800299A1
0x180029978  mov     rax, [rsi]
0x18002997b  mov     rcx, rsi
0x18002997e  mov     rax, [rax]
0x180029981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029986  mov     eax, ebx
0x180029988  lock xadd [rsi+0Ch], eax
0x18002998d  add     eax, ebx
0x18002998f  jnz     short loc_1800299A1
0x180029991  mov     rax, [rsi]
0x180029994  mov     rcx, rsi
0x180029997  mov     rax, [rax+8]
0x18002999b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299a0  nop
0x1800299a1  cmp     [rdi], r15
0x1800299a4  jz      short loc_1800299AE
0x1800299a6  mov     rcx, rdi
0x1800299a9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800299ae  mov     eax, 80070002h
0x1800299b3  mov     rcx, [rbp+57h+var_28]
0x1800299b7  xor     rcx, rsp; StackCookie
0x1800299ba  call    __security_check_cookie
0x1800299bf  mov     rbx, [rsp+0D0h+arg_10]
0x1800299c7  add     rsp, 0B0h
0x1800299ce  pop     r15
0x1800299d0  pop     r14
0x1800299d2  pop     rdi
0x1800299d3  pop     rsi
0x1800299d4  pop     rbp
0x1800299d5  retn
0x1800299d6  mov     r8, rsi
0x1800299d9  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &)
0x1800299df  lea     r8, [rbp+57h+Src]; struct std::error_code *
0x1800299e3  lea     rdx, [rbp+57h+var_80]; char *
0x1800299e7  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
