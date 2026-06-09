# CleanupPahcRegistry(ulong,ulong)

- ea: `0x180058208`
- end: `0x180058445`
- name: `?CleanupPahcRegistry@@YAJKK@Z`
- size: `573`
- prototype: `__int64 __fastcall(unsigned int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18001cd38`

## callees

- `0x180008788`
- `0x18000bef0`
- `0x18000e48c`
- `0x18001a42c`
- `0x18001a450`
- `0x180023634`
- `0x180024780`
- `0x180057f90`
- `0x180058208`
- `0x18005844c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180058357`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180058357`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005824e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005824e`

## string_xrefs

- `0x180058240`: `SYSTEM\CurrentControlSet\Services\TPM\WMI\PcrInfo`

## pseudocode

```c
__int64 __fastcall CleanupPahcRegistry(unsigned int a1, int a2)
{
  HKEY *v4; // rax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // rbx
  __int64 v9; // rdi
  const wchar_t *v10; // rax
  const WCHAR *v11; // rax
  unsigned int v12; // eax
  int v13; // eax
  unsigned int v14; // esi
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  __int128 v18; // [rsp+38h] [rbp-18h]
  __int64 v19; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  HKEY hKey; // [rsp+90h] [rbp+40h] BYREF
  __int64 v22; // [rsp+98h] [rbp+48h] BYREF

  hKey = 0;
  v4 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\TPM\\WMI\\PcrInfo", 0, 0x30119u, v4);
  if ( v5 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x147,
           (unsigned int)"onecore\\base\\ngscb\\tpm\\lib\\wbclhelper\\wbclhelper.cpp",
           (const char *)v5,
           phkResult);
  }
  else
  {
    v18 = 0;
    v19 = 0;
    v7 = EnumSubkeyNames(hKey);
    v6 = v7;
    if ( v7 >= 0 )
    {
      v9 = *((_QWORD *)&v18 + 1);
      v8 = v18;
      if ( (_QWORD)v18 == *((_QWORD *)&v18 + 1) )
      {
LABEL_15:
        if ( v8 )
        {
          std::_Destroy_range<std::allocator<std::wstring>>(v8, v9);
          std::_Deallocate<16>(v18, (v19 - v18) & 0xFFFFFFFFFFFFFFE0uLL);
          v18 = 0;
          v19 = 0;
        }
        v6 = 0;
      }
      else
      {
        while ( 1 )
        {
          v22 = 0;
          v17 = 0;
          v10 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
          if ( swscanf_s(v10, L"%llu-%llu", &v22, &v17) == 2 && (_DWORD)v22 != a2 && a2 - (int)v22 >= a1 )
          {
            v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
            v12 = RegDeleteTreeW(hKey, v11);
            if ( v12 - 2 > 1 )
            {
              if ( v12 )
              {
                v13 = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x95,
                        (unsigned int)"onecore\\base\\ngscb\\tpm\\lib\\wbclhelper\\wbclhelper.cpp",
                        (const char *)v12,
                        phkResult);
                v14 = v13;
                if ( v13 < 0 )
                  break;
              }
            }
          }
          v8 += 32;
          if ( v8 == v9 )
          {
            v9 = *((_QWORD *)&v18 + 1);
            v8 = v18;
            goto LABEL_15;
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x165,
          (unsigned int)"onecore\\base\\ngscb\\tpm\\lib\\wbclhelper\\wbclhelper.cpp",
          (const char *)(unsigned int)v13,
          phkResult);
        if ( (_QWORD)v18 )
        {
          std::_Destroy_range<std::allocator<std::wstring>>(v18, *((_QWORD *)&v18 + 1));
          std::_Deallocate<16>(v18, (v19 - v18) & 0xFFFFFFFFFFFFFFE0uLL);
          v18 = 0;
          v19 = 0;
        }
        v6 = v14;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14A,
        (unsigned int)"onecore\\base\\ngscb\\tpm\\lib\\wbclhelper\\wbclhelper.cpp",
        (const char *)(unsigned int)v7,
        phkResult);
      if ( (_QWORD)v18 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v18, *((_QWORD *)&v18 + 1));
        std::_Deallocate<16>(v18, (v19 - v18) & 0xFFFFFFFFFFFFFFE0uLL);
        v18 = 0;
        v19 = 0;
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v6;
}

```

## disassembly

```asm
0x180058208  mov     [rsp-28h+arg_0], rbx
0x18005820d  push    rbp
0x18005820e  push    rsi
0x18005820f  push    rdi
0x180058210  push    r14
0x180058212  push    r15
0x180058214  mov     rbp, rsp
0x180058217  sub     rsp, 50h
0x18005821b  mov     r14d, edx
0x18005821e  mov     r15d, ecx
0x180058221  mov     [rbp+hKey], 0
0x180058229  lea     rcx, [rbp+hKey]
0x18005822d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180058232  mov     qword ptr [rsp+50h+phkResult], rax; int
0x180058237  mov     r9d, 30119h; samDesired
0x18005823d  xor     r8d, r8d; ulOptions
0x180058240  lea     rdx, aSystemCurrentc_14; "SYSTEM\\CurrentControlSet\\Services\\TP"...
0x180058247  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005824e  call    cs:__imp_RegOpenKeyExW
0x180058254  test    eax, eax
0x180058256  jz      short loc_180058277
0x180058258  mov     rcx, [rbp+28h]; this
0x18005825c  mov     r9d, eax; char *
0x18005825f  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\tpm\\lib\\wbclhel"...
0x180058266  mov     edx, 147h; void *
0x18005826b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180058270  mov     ebx, eax
0x180058272  jmp     loc_1800583D2
0x180058277  xorps   xmm0, xmm0
0x18005827a  movdqu  [rbp+var_18], xmm0
0x18005827f  mov     [rbp+var_8], 0
0x180058287  lea     rdx, [rbp+var_18]
0x18005828b  mov     rcx, [rbp+hKey]; hKey
0x18005828f  call    EnumSubkeyNames
0x180058294  mov     ebx, eax
0x180058296  test    eax, eax
0x180058298  jns     short loc_1800582F2
0x18005829a  mov     rcx, [rbp+28h]; this
0x18005829e  mov     r9d, eax; char *
0x1800582a1  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\tpm\\lib\\wbclhel"...
0x1800582a8  mov     edx, 14Ah; void *
0x1800582ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800582b2  nop
0x1800582b3  mov     rcx, qword ptr [rbp+var_18]
0x1800582b7  test    rcx, rcx
0x1800582ba  jz      loc_1800583D2
0x1800582c0  mov     rdx, qword ptr [rbp+var_18+8]
0x1800582c4  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800582c9  mov     rcx, qword ptr [rbp+var_18]
0x1800582cd  mov     rdx, [rbp+var_8]
0x1800582d1  sub     rdx, rcx
0x1800582d4  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800582d8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800582dd  xorps   xmm0, xmm0
0x1800582e0  movdqu  [rbp+var_18], xmm0
0x1800582e5  mov     [rbp+var_8], 0
0x1800582ed  jmp     loc_1800583D2
0x1800582f2  mov     rbx, qword ptr [rbp+var_18]
0x1800582f6  mov     rdi, qword ptr [rbp+var_18+8]
0x1800582fa  cmp     rbx, rdi
0x1800582fd  jz      loc_18005839C
0x180058303  mov     [rbp+arg_18], 0
0x18005830b  mov     [rbp+var_20], 0
0x180058313  mov     rcx, rbx
0x180058316  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005831b  lea     r9, [rbp+var_20]
0x18005831f  lea     r8, [rbp+arg_18]
0x180058323  lea     rdx, aLluLlu; "%llu-%llu"
0x18005832a  mov     rcx, rax; Buffer
0x18005832d  call    swscanf_s
0x180058332  cmp     eax, 2
0x180058335  jnz     short loc_180058387
0x180058337  cmp     dword ptr [rbp+arg_18], r14d
0x18005833b  jz      short loc_180058387
0x18005833d  mov     eax, r14d
0x180058340  sub     eax, dword ptr [rbp+arg_18]
0x180058343  cmp     eax, r15d
0x180058346  jb      short loc_180058387
0x180058348  mov     rcx, rbx
0x18005834b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180058350  mov     rdx, rax; lpSubKey
0x180058353  mov     rcx, [rbp+hKey]; hKey
0x180058357  call    cs:__imp_RegDeleteTreeW
0x18005835d  lea     ecx, [rax-2]
0x180058360  cmp     ecx, 1
0x180058363  jbe     short loc_180058387
0x180058365  test    eax, eax
0x180058367  jz      short loc_180058387
0x180058369  mov     rcx, [rbp+28h]; this
0x18005836d  mov     r9d, eax; char *
0x180058370  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\tpm\\lib\\wbclhel"...
0x180058377  mov     edx, 95h; void *
0x18005837c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180058381  mov     esi, eax
0x180058383  test    eax, eax
0x180058385  js      short loc_1800583F1
0x180058387  add     rbx, 20h ; ' '
0x18005838b  cmp     rbx, rdi
0x18005838e  jnz     loc_180058303
0x180058394  mov     rdi, qword ptr [rbp+var_18+8]
0x180058398  mov     rbx, qword ptr [rbp+var_18]
0x18005839c  test    rbx, rbx
0x18005839f  jz      short loc_1800583D0
0x1800583a1  mov     rdx, rdi
0x1800583a4  mov     rcx, rbx
0x1800583a7  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800583ac  mov     rcx, qword ptr [rbp+var_18]
0x1800583b0  mov     rdx, [rbp+var_8]
0x1800583b4  sub     rdx, rcx
0x1800583b7  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800583bb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800583c0  xorps   xmm0, xmm0
0x1800583c3  movdqu  [rbp+var_18], xmm0
0x1800583c8  mov     [rbp+var_8], 0
0x1800583d0  xor     ebx, ebx
0x1800583d2  lea     rcx, [rbp+hKey]
0x1800583d6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800583db  mov     eax, ebx
0x1800583dd  mov     rbx, [rsp+50h+arg_0]
0x1800583e5  add     rsp, 50h
0x1800583e9  pop     r15
0x1800583eb  pop     r14
0x1800583ed  pop     rdi
0x1800583ee  pop     rsi
0x1800583ef  pop     rbp
0x1800583f0  retn
0x1800583f1  mov     rcx, [rbp+28h]; this
0x1800583f5  mov     r9d, esi; char *
0x1800583f8  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\tpm\\lib\\wbclhel"...
0x1800583ff  mov     edx, 165h; void *
0x180058404  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058409  nop
0x18005840a  mov     rcx, qword ptr [rbp+var_18]
0x18005840e  test    rcx, rcx
0x180058411  jz      short loc_180058440
0x180058413  mov     rdx, qword ptr [rbp+var_18+8]
0x180058417  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18005841c  mov     rcx, qword ptr [rbp+var_18]
0x180058420  mov     rdx, [rbp+var_8]
0x180058424  sub     rdx, rcx
0x180058427  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18005842b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180058430  xorps   xmm0, xmm0
0x180058433  movdqu  [rbp+var_18], xmm0
0x180058438  mov     [rbp+var_8], 0
0x180058440  mov     ebx, esi
0x180058442  jmp     short loc_1800583D2
```
