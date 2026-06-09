# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18000fc74`
- end: `0x18000fe50`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `476`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fb20`

## callees

- `0x180002c00`
- `0x180003865`
- `0x18000387d`
- `0x180003889`
- `0x180003895`
- `0x1800038ad`
- `0x1800038d1`
- `0x180009c74`
- `0x18000eea8`
- `0x18000fc74`
- `0x180012c9c`
- `0x180012d18`
- `0x180013454`
- `0x1800134d0`
- `0x18001c010`

## string_xrefs

- `0x18000fcd5`: `combase.dll`
- `0x18000fdae`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  const WCHAR *v13; // rcx
  HMODULE v14; // rdi
  FARPROC v15; // rax
  __int64 v16; // rax
  __int64 v18; // [rsp+20h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[4]; // [rsp+30h] [rbp-38h] BYREF

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
      v18 = 0;
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v18);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      std::wstring::wstring(lpLibFileName, a2);
      while ( 1 )
      {
        v12 = std::wstring::rfind(lpLibFileName);
        if ( v12 == -1 )
          break;
        std::wstring::resize(lpLibFileName, v12);
        std::wstring::append(lpLibFileName, L".dll");
        v13 = (const WCHAR *)lpLibFileName;
        if ( lpLibFileName[3] > (LPCWSTR)7 )
          v13 = lpLibFileName[0];
        v14 = LoadLibraryExW_0(v13, 0, 0x1000u);
        std::wstring::resize(lpLibFileName, lpLibFileName[2] - 2);
        if ( v14 )
        {
          v15 = WINRT_IMPL_GetProcAddress(v14, "DllGetActivationFactory");
          if ( v15 )
          {
            v18 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v15)(*a2, &v18) )
            {
              v16 = v18;
              v18 = 0;
              *a4 = v16;
              *a1 = 0;
              goto LABEL_21;
            }
            if ( v18 )
              winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v18);
          }
          WINRT_IMPL_FreeLibrary(v14);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_21:
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
0x18000fc74  push    rbp
0x18000fc76  push    rbx
0x18000fc77  push    rsi
0x18000fc78  push    rdi
0x18000fc79  push    r14
0x18000fc7b  push    r15
0x18000fc7d  mov     rbp, rsp
0x18000fc80  sub     rsp, 68h
0x18000fc84  mov     rax, cs:__security_cookie
0x18000fc8b  xor     rax, rsp
0x18000fc8e  mov     [rbp+var_18], rax
0x18000fc92  mov     r14, r9
0x18000fc95  mov     rdi, r8
0x18000fc98  mov     r15, rdx
0x18000fc9b  mov     rsi, rcx
0x18000fc9e  mov     rcx, [rdx]
0x18000fca1  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18000fca8  mov     r8, r9
0x18000fcab  mov     rdx, rdi
0x18000fcae  test    rax, rax
0x18000fcb1  jz      short loc_18000FCBF
0x18000fcb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcb8  mov     [rsi], eax
0x18000fcba  jmp     loc_18000FE34
0x18000fcbf  call    RoGetActivationFactory_0
0x18000fcc4  mov     ebx, eax
0x18000fcc6  cmp     eax, 800401F0h
0x18000fccb  jnz     short loc_18000FD21
0x18000fccd  xor     edx, edx; hFile
0x18000fccf  mov     r8d, 1000h; dwFlags
0x18000fcd5  lea     rcx, LibFileName; "combase.dll"
0x18000fcdc  call    LoadLibraryExW_0
0x18000fce1  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18000fce8  mov     rcx, rax; hModule
0x18000fceb  call    WINRT_IMPL_GetProcAddress
0x18000fcf0  test    rax, rax
0x18000fcf3  jnz     short loc_18000FD00
0x18000fcf5  mov     dword ptr [rsi], 800401F0h
0x18000fcfb  jmp     loc_18000FE34
0x18000fd00  mov     [rbp+var_48], 0
0x18000fd08  lea     rcx, [rbp+var_48]
0x18000fd0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd11  mov     r8, r14
0x18000fd14  mov     rdx, rdi
0x18000fd17  mov     rcx, [r15]
0x18000fd1a  call    RoGetActivationFactory_0
0x18000fd1f  mov     ebx, eax
0x18000fd21  test    ebx, ebx
0x18000fd23  jnz     short loc_18000FD2C
0x18000fd25  mov     [rsi], ebx
0x18000fd27  jmp     loc_18000FE34
0x18000fd2c  mov     [rbp+pperrinfo], 0
0x18000fd34  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000fd38  xor     ecx, ecx; dwReserved
0x18000fd3a  call    GetErrorInfo_0
0x18000fd3f  mov     rdx, r15
0x18000fd42  lea     rcx, [rbp+lpLibFileName]
0x18000fd46  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x18000fd4b  lea     rcx, [rbp+lpLibFileName]
0x18000fd4f  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x18000fd54  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fd58  jz      loc_18000FE0E
0x18000fd5e  mov     rdx, rax
0x18000fd61  lea     rcx, [rbp+lpLibFileName]
0x18000fd65  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000fd6a  lea     rdx, aDll; ".dll"
0x18000fd71  lea     rcx, [rbp+lpLibFileName]; Src
0x18000fd75  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18000fd7a  lea     rcx, [rbp+lpLibFileName]
0x18000fd7e  cmp     [rbp+var_20], 7
0x18000fd83  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000fd88  xor     edx, edx; hFile
0x18000fd8a  mov     r8d, 1000h; dwFlags
0x18000fd90  call    LoadLibraryExW_0
0x18000fd95  mov     rdi, rax
0x18000fd98  mov     rdx, [rbp+var_28]
0x18000fd9c  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18000fda0  lea     rcx, [rbp+lpLibFileName]
0x18000fda4  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000fda9  test    rdi, rdi
0x18000fdac  jz      short loc_18000FD4B
0x18000fdae  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18000fdb5  mov     rcx, rdi; hModule
0x18000fdb8  call    WINRT_IMPL_GetProcAddress
0x18000fdbd  test    rax, rax
0x18000fdc0  jz      short loc_18000FDEA
0x18000fdc2  mov     [rbp+var_48], 0
0x18000fdca  lea     rdx, [rbp+var_48]
0x18000fdce  mov     rcx, [r15]
0x18000fdd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdd6  test    eax, eax
0x18000fdd8  jz      short loc_18000FDF7
0x18000fdda  cmp     [rbp+var_48], 0
0x18000fddf  jz      short loc_18000FDEA
0x18000fde1  lea     rcx, [rbp+var_48]
0x18000fde5  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18000fdea  mov     rcx, rdi; hLibModule
0x18000fded  call    WINRT_IMPL_FreeLibrary
0x18000fdf2  jmp     loc_18000FD4B
0x18000fdf7  mov     rax, [rbp+var_48]
0x18000fdfb  mov     [rbp+var_48], 0
0x18000fe03  mov     [r14], rax
0x18000fe06  mov     dword ptr [rsi], 0
0x18000fe0c  jmp     short loc_18000FE1B
0x18000fe0e  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18000fe12  xor     ecx, ecx; dwReserved
0x18000fe14  call    SetErrorInfo_0
0x18000fe19  mov     [rsi], ebx
0x18000fe1b  lea     rcx, [rbp+lpLibFileName]
0x18000fe1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fe24  cmp     [rbp+pperrinfo], 0
0x18000fe29  jz      short loc_18000FE34
0x18000fe2b  lea     rcx, [rbp+pperrinfo]
0x18000fe2f  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18000fe34  mov     rax, rsi
0x18000fe37  mov     rcx, [rbp+var_18]
0x18000fe3b  xor     rcx, rsp; StackCookie
0x18000fe3e  call    __security_check_cookie
0x18000fe43  add     rsp, 68h
0x18000fe47  pop     r15
0x18000fe49  pop     r14
0x18000fe4b  pop     rdi
0x18000fe4c  pop     rsi
0x18000fe4d  pop     rbx
0x18000fe4e  pop     rbp
0x18000fe4f  retn
```
