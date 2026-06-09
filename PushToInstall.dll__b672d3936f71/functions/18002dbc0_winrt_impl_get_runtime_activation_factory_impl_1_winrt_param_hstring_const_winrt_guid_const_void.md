# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18002dbc0`
- end: `0x18002de73`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `691`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002db60`

## callees

- `0x1800026b0`
- `0x1800033eb`
- `0x18000d620`
- `0x18000de0d`
- `0x18000deda`
- `0x18000dee6`
- `0x18000e05e`
- `0x18000e076`
- `0x180021cdc`
- `0x18002d5f8`
- `0x18002d674`
- `0x18002dbc0`
- `0x180030aac`
- `0x180030ca4`
- `0x18004f010`

## string_xrefs

- `0x18002dc24`: `combase.dll`
- `0x18002ddcc`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // edi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  const WCHAR *v13; // rdx
  unsigned __int64 v14; // r8
  LPCWSTR *v15; // r14
  char *v16; // rbx
  __int64 last_trivial_2; // rax
  unsigned __int64 v18; // rdx
  LPCWSTR *v19; // rcx
  const WCHAR *v20; // rcx
  HMODULE v21; // rbx
  unsigned __int64 v22; // rdx
  LPCWSTR *v23; // rcx
  FARPROC v24; // rax
  __int64 v25; // rax
  __int64 v27; // [rsp+20h] [rbp-40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-38h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v30; // [rsp+40h] [rbp-20h]
  unsigned __int64 v31; // [rsp+48h] [rbp-18h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD *))winrt_activation_handler)(v8, a3, a4);
  }
  else
  {
    ActivationFactory_0 = RoGetActivationFactory_0(v8, a3, a4);
    if ( ActivationFactory_0 == -2147221008 )
    {
      Library = LoadLibraryExW_0(L"combase.dll", 0, 0x1000u);
      ProcAddress = WINRT_IMPL_GetProcAddress(Library, "CoIncrementMTAUsage");
      if ( !ProcAddress )
      {
        *a1 = -2147221008;
        return a1;
      }
      v27 = 0;
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v27);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      *(_OWORD *)lpLibFileName = 0;
      v30 = 0;
      v31 = 0;
      v12 = *a2;
      if ( *a2 )
      {
        v13 = *(const WCHAR **)(v12 + 16);
        v14 = *(unsigned int *)(v12 + 4);
      }
      else
      {
        v13 = &ApplicationName;
        v14 = 0;
      }
      std::wstring::_Construct<1,unsigned short const *>(lpLibFileName, v13, v14);
      while ( 1 )
      {
        v15 = lpLibFileName;
        if ( v31 > 7 )
          v15 = (LPCWSTR *)lpLibFileName[0];
        if ( !v30 )
          break;
        v16 = (char *)v15 + 2 * v30;
        last_trivial_2 = _std_find_last_trivial_2(v15, v16, 46);
        if ( (char *)last_trivial_2 == v16 )
          break;
        v18 = (last_trivial_2 - (__int64)v15) >> 1;
        if ( v18 == -1 )
          break;
        v19 = lpLibFileName;
        if ( v18 > v30 )
        {
          std::wstring::append(lpLibFileName);
        }
        else
        {
          v30 = (last_trivial_2 - (__int64)v15) >> 1;
          if ( v31 > 7 )
            v19 = (LPCWSTR *)lpLibFileName[0];
          *((_WORD *)v19 + v18) = 0;
        }
        std::wstring::_Append<unsigned short>(lpLibFileName, L".dll", 4u);
        v20 = (const WCHAR *)lpLibFileName;
        if ( v31 > 7 )
          v20 = lpLibFileName[0];
        v21 = LoadLibraryExW_0(v20, 0, 0x1000u);
        v22 = v30 - 4;
        v23 = lpLibFileName;
        if ( v30 < 4 )
        {
          std::wstring::append(lpLibFileName);
        }
        else
        {
          v30 -= 4LL;
          if ( v31 > 7 )
            v23 = (LPCWSTR *)lpLibFileName[0];
          *((_WORD *)v23 + v22) = 0;
        }
        if ( v21 )
        {
          v24 = WINRT_IMPL_GetProcAddress(v21, "DllGetActivationFactory");
          if ( v24 )
          {
            v27 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v24)(*a2, &v27) )
            {
              v25 = v27;
              v27 = 0;
              *a4 = v25;
              *a1 = 0;
              goto LABEL_38;
            }
            if ( v27 )
              winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v27);
          }
          WINRT_IMPL_FreeLibrary(v21);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_38:
      std::wstring::_Tidy_deallocate(lpLibFileName);
      if ( pperrinfo )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&pperrinfo);
    }
    else
    {
      *a1 = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002dbc0  push    rbp
0x18002dbc2  push    rbx
0x18002dbc3  push    rsi
0x18002dbc4  push    rdi
0x18002dbc5  push    r12
0x18002dbc7  push    r14
0x18002dbc9  push    r15
0x18002dbcb  mov     rbp, rsp
0x18002dbce  sub     rsp, 60h
0x18002dbd2  mov     rax, cs:__security_cookie
0x18002dbd9  xor     rax, rsp
0x18002dbdc  mov     [rbp+var_10], rax
0x18002dbe0  mov     r15, r9
0x18002dbe3  mov     rbx, r8
0x18002dbe6  mov     r12, rdx
0x18002dbe9  mov     rsi, rcx
0x18002dbec  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18002dbf3  mov     r8, r9
0x18002dbf6  mov     rdx, rbx
0x18002dbf9  mov     rcx, [r12]
0x18002dbfd  test    rax, rax
0x18002dc00  jz      short loc_18002DC0E
0x18002dc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc07  mov     [rsi], eax
0x18002dc09  jmp     loc_18002DE55
0x18002dc0e  call    RoGetActivationFactory_0
0x18002dc13  mov     edi, eax
0x18002dc15  cmp     eax, 800401F0h
0x18002dc1a  jnz     short loc_18002DC71
0x18002dc1c  xor     edx, edx; hFile
0x18002dc1e  mov     r8d, 1000h; dwFlags
0x18002dc24  lea     rcx, LibFileName; "combase.dll"
0x18002dc2b  call    LoadLibraryExW_0
0x18002dc30  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18002dc37  mov     rcx, rax; hModule
0x18002dc3a  call    WINRT_IMPL_GetProcAddress
0x18002dc3f  test    rax, rax
0x18002dc42  jnz     short loc_18002DC4F
0x18002dc44  mov     dword ptr [rsi], 800401F0h
0x18002dc4a  jmp     loc_18002DE55
0x18002dc4f  mov     [rbp+var_40], 0
0x18002dc57  lea     rcx, [rbp+var_40]
0x18002dc5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc60  mov     r8, r15
0x18002dc63  mov     rdx, rbx
0x18002dc66  mov     rcx, [r12]
0x18002dc6a  call    RoGetActivationFactory_0
0x18002dc6f  mov     edi, eax
0x18002dc71  test    edi, edi
0x18002dc73  jnz     short loc_18002DC7C
0x18002dc75  mov     [rsi], edi
0x18002dc77  jmp     loc_18002DE55
0x18002dc7c  mov     [rbp+pperrinfo], 0
0x18002dc84  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18002dc88  xor     ecx, ecx; dwReserved
0x18002dc8a  call    GetErrorInfo_0
0x18002dc8f  xorps   xmm0, xmm0
0x18002dc92  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x18002dc96  mov     [rbp+var_20], 0
0x18002dc9e  mov     [rbp+var_18], 0
0x18002dca6  mov     rax, [r12]
0x18002dcaa  test    rax, rax
0x18002dcad  jz      short loc_18002DCB9
0x18002dcaf  mov     rdx, [rax+10h]
0x18002dcb3  mov     r8d, [rax+4]
0x18002dcb7  jmp     short loc_18002DCC3
0x18002dcb9  lea     rdx, ApplicationName
0x18002dcc0  xor     r8d, r8d
0x18002dcc3  lea     rcx, [rbp+lpLibFileName]
0x18002dcc7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002dccc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002dcd0  mov     rax, [rbp+var_20]
0x18002dcd4  lea     r14, [rbp+lpLibFileName]
0x18002dcd8  cmp     [rbp+var_18], 7
0x18002dcdd  cmova   r14, [rbp+lpLibFileName]
0x18002dce2  test    rax, rax
0x18002dce5  jz      loc_18002DE2F
0x18002dceb  dec     rax
0x18002dcee  cmp     rax, rcx
0x18002dcf1  cmovnb  rax, rcx
0x18002dcf5  inc     rax
0x18002dcf8  lea     rbx, [r14+rax*2]
0x18002dcfc  mov     r8d, 2Eh ; '.'
0x18002dd02  mov     rdx, rbx
0x18002dd05  mov     rcx, r14
0x18002dd08  call    __std_find_last_trivial_2
0x18002dd0d  mov     rdx, rax
0x18002dd10  cmp     rax, rbx
0x18002dd13  jz      loc_18002DE2F
0x18002dd19  sub     rdx, r14
0x18002dd1c  sar     rdx, 1
0x18002dd1f  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18002dd23  jz      loc_18002DE2F
0x18002dd29  lea     rcx, [rbp+lpLibFileName]; Src
0x18002dd2d  cmp     rdx, [rbp+var_20]
0x18002dd31  ja      short loc_18002DD49
0x18002dd33  mov     [rbp+var_20], rdx
0x18002dd37  cmp     [rbp+var_18], 7
0x18002dd3c  cmova   rcx, [rbp+lpLibFileName]
0x18002dd41  xor     eax, eax
0x18002dd43  mov     [rcx+rdx*2], ax
0x18002dd47  jmp     short loc_18002DD55
0x18002dd49  xor     r8d, r8d
0x18002dd4c  sub     rdx, [rbp+var_20]
0x18002dd50  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x18002dd55  mov     r8d, 4
0x18002dd5b  lea     rdx, aDll; ".dll"
0x18002dd62  lea     rcx, [rbp+lpLibFileName]; Src
0x18002dd66  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002dd6b  lea     rcx, [rbp+lpLibFileName]
0x18002dd6f  cmp     [rbp+var_18], 7
0x18002dd74  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18002dd79  xor     edx, edx; hFile
0x18002dd7b  mov     r8d, 1000h; dwFlags
0x18002dd81  call    LoadLibraryExW_0
0x18002dd86  mov     rbx, rax
0x18002dd89  mov     rax, [rbp+var_20]
0x18002dd8d  lea     rdx, [rax-4]
0x18002dd91  lea     rcx, [rbp+lpLibFileName]; Src
0x18002dd95  cmp     rdx, rax
0x18002dd98  ja      short loc_18002DDB0
0x18002dd9a  mov     [rbp+var_20], rdx
0x18002dd9e  cmp     [rbp+var_18], 7
0x18002dda3  cmova   rcx, [rbp+lpLibFileName]
0x18002dda8  xor     eax, eax
0x18002ddaa  mov     [rcx+rdx*2], ax
0x18002ddae  jmp     short loc_18002DDBC
0x18002ddb0  xor     r8d, r8d
0x18002ddb3  lea     rdx, [r8-4]
0x18002ddb7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x18002ddbc  test    rbx, rbx
0x18002ddbf  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002ddc6  jz      loc_18002DCD0
0x18002ddcc  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18002ddd3  mov     rcx, rbx; hModule
0x18002ddd6  call    WINRT_IMPL_GetProcAddress
0x18002dddb  test    rax, rax
0x18002ddde  jnz     short loc_18002DDED
0x18002dde0  mov     rcx, rbx; hLibModule
0x18002dde3  call    WINRT_IMPL_FreeLibrary
0x18002dde8  jmp     loc_18002DCCC
0x18002dded  mov     [rbp+var_40], 0
0x18002ddf5  lea     rdx, [rbp+var_40]
0x18002ddf9  mov     rcx, [r12]
0x18002ddfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de02  test    eax, eax
0x18002de04  jz      short loc_18002DE18
0x18002de06  cmp     [rbp+var_40], 0
0x18002de0b  jz      short loc_18002DDE0
0x18002de0d  lea     rcx, [rbp+var_40]
0x18002de11  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18002de16  jmp     short loc_18002DDE0
0x18002de18  mov     rax, [rbp+var_40]
0x18002de1c  mov     [rbp+var_40], 0
0x18002de24  mov     [r15], rax
0x18002de27  mov     dword ptr [rsi], 0
0x18002de2d  jmp     short loc_18002DE3C
0x18002de2f  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18002de33  xor     ecx, ecx; dwReserved
0x18002de35  call    SetErrorInfo_0
0x18002de3a  mov     [rsi], edi
0x18002de3c  lea     rcx, [rbp+lpLibFileName]
0x18002de40  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002de45  cmp     [rbp+pperrinfo], 0
0x18002de4a  jz      short loc_18002DE55
0x18002de4c  lea     rcx, [rbp+pperrinfo]
0x18002de50  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18002de55  mov     rax, rsi
0x18002de58  mov     rcx, [rbp+var_10]
0x18002de5c  xor     rcx, rsp; StackCookie
0x18002de5f  call    __security_check_cookie
0x18002de64  add     rsp, 60h
0x18002de68  pop     r15
0x18002de6a  pop     r14
0x18002de6c  pop     r12
0x18002de6e  pop     rdi
0x18002de6f  pop     rsi
0x18002de70  pop     rbx
0x18002de71  pop     rbp
0x18002de72  retn
```
