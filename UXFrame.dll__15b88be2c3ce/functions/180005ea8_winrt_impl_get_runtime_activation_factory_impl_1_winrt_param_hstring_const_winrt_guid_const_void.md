# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180005ea8`
- end: `0x180006098`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005da8`

## callees

- `0x1800028ac`
- `0x180002b20`
- `0x180003db5`
- `0x180003dc1`
- `0x180003dfd`
- `0x180003e09`
- `0x180003e15`
- `0x1800049ac`
- `0x180004ad8`
- `0x180004f80`
- `0x1800052f0`
- `0x180005ea8`
- `0x180008968`
- `0x180008de8`
- `0x18005a010`

## string_xrefs

- `0x180005f09`: `combase.dll`
- `0x180005ff6`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  LPCWSTR *v12; // rcx
  __int64 v13; // rax
  const WCHAR *v14; // rcx
  HMODULE v15; // rdi
  FARPROC v16; // rax
  __int64 v17; // rax
  __int64 v19; // [rsp+20h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v22; // [rsp+40h] [rbp-28h]
  unsigned __int64 v23; // [rsp+48h] [rbp-20h]

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
      v19 = 0;
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v19);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      std::wstring::wstring(lpLibFileName, a2);
      while ( 1 )
      {
        v12 = lpLibFileName;
        if ( v23 > 7 )
          v12 = (LPCWSTR *)lpLibFileName[0];
        v13 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(v12, v22);
        if ( v13 == -1 )
          break;
        std::wstring::resize(lpLibFileName, v13);
        std::wstring::_Append<wchar_t>(lpLibFileName);
        v14 = (const WCHAR *)lpLibFileName;
        if ( v23 > 7 )
          v14 = lpLibFileName[0];
        v15 = LoadLibraryExW_0(v14, 0, 0x1000u);
        std::wstring::resize(lpLibFileName, v22 - 4);
        if ( v15 )
        {
          v16 = WINRT_IMPL_GetProcAddress(v15, "DllGetActivationFactory");
          if ( v16 )
          {
            v19 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v16)(*a2, &v19) )
            {
              v17 = v19;
              v19 = 0;
              *a4 = v17;
              *a1 = 0;
              goto LABEL_23;
            }
            if ( v19 )
              winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v19);
          }
          WINRT_IMPL_FreeLibrary(v15);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_23:
      std::wstring::_Tidy_deallocate(lpLibFileName);
      if ( pperrinfo )
        winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&pperrinfo);
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
0x180005ea8  push    rbp
0x180005eaa  push    rbx
0x180005eab  push    rsi
0x180005eac  push    rdi
0x180005ead  push    r14
0x180005eaf  push    r15
0x180005eb1  mov     rbp, rsp
0x180005eb4  sub     rsp, 68h
0x180005eb8  mov     rax, cs:__security_cookie
0x180005ebf  xor     rax, rsp
0x180005ec2  mov     [rbp+var_18], rax
0x180005ec6  mov     r14, r9
0x180005ec9  mov     rdi, r8
0x180005ecc  mov     r15, rdx
0x180005ecf  mov     rsi, rcx
0x180005ed2  mov     rcx, [rdx]
0x180005ed5  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180005edc  mov     r8, r9
0x180005edf  mov     rdx, rdi
0x180005ee2  test    rax, rax
0x180005ee5  jz      short loc_180005EF3
0x180005ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eec  mov     [rsi], eax
0x180005eee  jmp     loc_18000607C
0x180005ef3  call    RoGetActivationFactory_0
0x180005ef8  mov     ebx, eax
0x180005efa  cmp     eax, 800401F0h
0x180005eff  jnz     short loc_180005F55
0x180005f01  xor     edx, edx; hFile
0x180005f03  mov     r8d, 1000h; dwFlags
0x180005f09  lea     rcx, LibFileName; "combase.dll"
0x180005f10  call    LoadLibraryExW_0
0x180005f15  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x180005f1c  mov     rcx, rax; hModule
0x180005f1f  call    WINRT_IMPL_GetProcAddress
0x180005f24  test    rax, rax
0x180005f27  jnz     short loc_180005F34
0x180005f29  mov     dword ptr [rsi], 800401F0h
0x180005f2f  jmp     loc_18000607C
0x180005f34  mov     [rbp+var_48], 0
0x180005f3c  lea     rcx, [rbp+var_48]
0x180005f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f45  mov     r8, r14
0x180005f48  mov     rdx, rdi
0x180005f4b  mov     rcx, [r15]
0x180005f4e  call    RoGetActivationFactory_0
0x180005f53  mov     ebx, eax
0x180005f55  test    ebx, ebx
0x180005f57  jnz     short loc_180005F60
0x180005f59  mov     [rsi], ebx
0x180005f5b  jmp     loc_18000607C
0x180005f60  mov     [rbp+pperrinfo], 0
0x180005f68  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180005f6c  xor     ecx, ecx; dwReserved
0x180005f6e  call    GetErrorInfo_0
0x180005f73  mov     rdx, r15
0x180005f76  lea     rcx, [rbp+lpLibFileName]
0x180005f7a  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<wchar_t> const &)
0x180005f7f  lea     rcx, [rbp+lpLibFileName]
0x180005f83  cmp     [rbp+var_20], 7
0x180005f88  cmova   rcx, [rbp+lpLibFileName]
0x180005f8d  mov     rdx, [rbp+var_28]
0x180005f91  call    ??$_Traits_rfind_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_rfind_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x180005f96  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005f9a  jz      loc_180006056
0x180005fa0  mov     rdx, rax
0x180005fa3  lea     rcx, [rbp+lpLibFileName]
0x180005fa7  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180005fac  mov     r8d, 4
0x180005fb2  lea     rdx, aDll; ".dll"
0x180005fb9  lea     rcx, [rbp+lpLibFileName]; Src
0x180005fbd  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180005fc2  lea     rcx, [rbp+lpLibFileName]
0x180005fc6  cmp     [rbp+var_20], 7
0x180005fcb  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x180005fd0  xor     edx, edx; hFile
0x180005fd2  mov     r8d, 1000h; dwFlags
0x180005fd8  call    LoadLibraryExW_0
0x180005fdd  mov     rdi, rax
0x180005fe0  mov     rdx, [rbp+var_28]
0x180005fe4  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180005fe8  lea     rcx, [rbp+lpLibFileName]
0x180005fec  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180005ff1  test    rdi, rdi
0x180005ff4  jz      short loc_180005F7F
0x180005ff6  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x180005ffd  mov     rcx, rdi; hModule
0x180006000  call    WINRT_IMPL_GetProcAddress
0x180006005  test    rax, rax
0x180006008  jz      short loc_180006032
0x18000600a  mov     [rbp+var_48], 0
0x180006012  lea     rdx, [rbp+var_48]
0x180006016  mov     rcx, [r15]
0x180006019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000601e  test    eax, eax
0x180006020  jz      short loc_18000603F
0x180006022  cmp     [rbp+var_48], 0
0x180006027  jz      short loc_180006032
0x180006029  lea     rcx, [rbp+var_48]
0x18000602d  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180006032  mov     rcx, rdi; hLibModule
0x180006035  call    WINRT_IMPL_FreeLibrary
0x18000603a  jmp     loc_180005F7F
0x18000603f  mov     rax, [rbp+var_48]
0x180006043  mov     [rbp+var_48], 0
0x18000604b  mov     [r14], rax
0x18000604e  mov     dword ptr [rsi], 0
0x180006054  jmp     short loc_180006063
0x180006056  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18000605a  xor     ecx, ecx; dwReserved
0x18000605c  call    SetErrorInfo_0
0x180006061  mov     [rsi], ebx
0x180006063  lea     rcx, [rbp+lpLibFileName]
0x180006067  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000606c  cmp     [rbp+pperrinfo], 0
0x180006071  jz      short loc_18000607C
0x180006073  lea     rcx, [rbp+pperrinfo]
0x180006077  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18000607c  mov     rax, rsi
0x18000607f  mov     rcx, [rbp+var_18]
0x180006083  xor     rcx, rsp; StackCookie
0x180006086  call    __security_check_cookie
0x18000608b  add     rsp, 68h
0x18000608f  pop     r15
0x180006091  pop     r14
0x180006093  pop     rdi
0x180006094  pop     rsi
0x180006095  pop     rbx
0x180006096  pop     rbp
0x180006097  retn
```
