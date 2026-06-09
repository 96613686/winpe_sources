# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18001c574`
- end: `0x18001c7dc`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c49c`

## callees

- `0x180004ac0`
- `0x180005020`
- `0x180005f98`
- `0x180005fb0`
- `0x180005fc8`
- `0x180006001`
- `0x180006019`
- `0x18000603d`
- `0x18000d430`
- `0x180010b94`
- `0x180013118`
- `0x180015144`
- `0x18001a42c`
- `0x18001c574`
- `0x18005e010`

## string_xrefs

- `0x18001c5d8`: `combase.dll`
- `0x18001c735`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  LPCWSTR *v12; // r14
  char *v13; // rdi
  __int64 last_trivial_2; // rax
  const WCHAR *v15; // rcx
  HMODULE v16; // rdi
  FARPROC v17; // rax
  __int64 v18; // rax
  __int64 v20; // [rsp+20h] [rbp-40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-38h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v23; // [rsp+40h] [rbp-20h]
  unsigned __int64 v24; // [rsp+48h] [rbp-18h]

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
      v20 = 0;
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v20);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      *(_OWORD *)lpLibFileName = 0;
      v23 = 0;
      v24 = 0;
      std::wstring::_Construct<1,unsigned short const *>(lpLibFileName);
      while ( 1 )
      {
        v12 = lpLibFileName;
        if ( v24 > 7 )
          v12 = (LPCWSTR *)lpLibFileName[0];
        if ( !v23 )
          break;
        v13 = (char *)v12 + 2 * v23;
        last_trivial_2 = _std_find_last_trivial_2(v12, v13, 46);
        if ( (char *)last_trivial_2 == v13 || (last_trivial_2 - (__int64)v12) >> 1 == -1 )
          break;
        std::wstring::resize(lpLibFileName);
        std::wstring::operator+=(lpLibFileName, L".dll");
        v15 = (const WCHAR *)lpLibFileName;
        if ( v24 > 7 )
          v15 = lpLibFileName[0];
        v16 = LoadLibraryExW_0(v15, 0, 0x1000u);
        std::wstring::resize(lpLibFileName);
        if ( v16 )
        {
          v17 = WINRT_IMPL_GetProcAddress(v16, "DllGetActivationFactory");
          if ( v17 )
          {
            v20 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v17)(*a2, &v20) )
            {
              v18 = v20;
              v20 = 0;
              *a4 = v18;
              *a1 = 0;
              goto LABEL_25;
            }
            if ( v20 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
          }
          WINRT_IMPL_FreeLibrary(v16);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_25:
      std::wstring::~wstring(lpLibFileName);
      if ( pperrinfo )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
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
0x18001c574  push    rbp
0x18001c576  push    rbx
0x18001c577  push    rsi
0x18001c578  push    rdi
0x18001c579  push    r12
0x18001c57b  push    r14
0x18001c57d  push    r15
0x18001c57f  mov     rbp, rsp
0x18001c582  sub     rsp, 60h
0x18001c586  mov     rax, cs:__security_cookie
0x18001c58d  xor     rax, rsp
0x18001c590  mov     [rbp+var_10], rax
0x18001c594  mov     r15, r9
0x18001c597  mov     rdi, r8
0x18001c59a  mov     r12, rdx
0x18001c59d  mov     rsi, rcx
0x18001c5a0  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18001c5a7  mov     r8, r9
0x18001c5aa  mov     rdx, rdi
0x18001c5ad  mov     rcx, [r12]
0x18001c5b1  test    rax, rax
0x18001c5b4  jz      short loc_18001C5C2
0x18001c5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5bb  mov     [rsi], eax
0x18001c5bd  jmp     loc_18001C7BE
0x18001c5c2  call    RoGetActivationFactory_0
0x18001c5c7  mov     ebx, eax
0x18001c5c9  cmp     eax, 800401F0h
0x18001c5ce  jnz     short loc_18001C625
0x18001c5d0  xor     edx, edx; hFile
0x18001c5d2  mov     r8d, 1000h; dwFlags
0x18001c5d8  lea     rcx, aCombaseDll; "combase.dll"
0x18001c5df  call    LoadLibraryExW_0
0x18001c5e4  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18001c5eb  mov     rcx, rax; hModule
0x18001c5ee  call    WINRT_IMPL_GetProcAddress
0x18001c5f3  test    rax, rax
0x18001c5f6  jnz     short loc_18001C603
0x18001c5f8  mov     dword ptr [rsi], 800401F0h
0x18001c5fe  jmp     loc_18001C7BE
0x18001c603  mov     [rbp+var_40], 0
0x18001c60b  lea     rcx, [rbp+var_40]
0x18001c60f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c614  mov     r8, r15
0x18001c617  mov     rdx, rdi
0x18001c61a  mov     rcx, [r12]
0x18001c61e  call    RoGetActivationFactory_0
0x18001c623  mov     ebx, eax
0x18001c625  test    ebx, ebx
0x18001c627  jnz     short loc_18001C630
0x18001c629  mov     [rsi], ebx
0x18001c62b  jmp     loc_18001C7BE
0x18001c630  mov     [rbp+pperrinfo], 0
0x18001c638  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18001c63c  xor     ecx, ecx; dwReserved
0x18001c63e  call    GetErrorInfo_0
0x18001c643  xorps   xmm0, xmm0
0x18001c646  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x18001c64a  mov     [rbp+var_20], 0
0x18001c652  mov     [rbp+var_18], 0
0x18001c65a  mov     rax, [r12]
0x18001c65e  test    rax, rax
0x18001c661  jz      short loc_18001C66D
0x18001c663  mov     rdx, [rax+10h]
0x18001c667  mov     r8d, [rax+4]
0x18001c66b  jmp     short loc_18001C677
0x18001c66d  lea     rdx, S1
0x18001c674  xor     r8d, r8d
0x18001c677  lea     rcx, [rbp+lpLibFileName]
0x18001c67b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001c680  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001c684  mov     rax, [rbp+var_20]
0x18001c688  lea     r14, [rbp+lpLibFileName]
0x18001c68c  cmp     [rbp+var_18], 7
0x18001c691  cmova   r14, [rbp+lpLibFileName]
0x18001c696  test    rax, rax
0x18001c699  jz      loc_18001C798
0x18001c69f  dec     rax
0x18001c6a2  cmp     rax, rcx
0x18001c6a5  cmovnb  rax, rcx
0x18001c6a9  inc     rax
0x18001c6ac  lea     rdi, [r14+rax*2]
0x18001c6b0  mov     r8d, 2Eh ; '.'
0x18001c6b6  mov     rdx, rdi
0x18001c6b9  mov     rcx, r14
0x18001c6bc  call    __std_find_last_trivial_2
0x18001c6c1  cmp     rax, rdi
0x18001c6c4  jz      loc_18001C798
0x18001c6ca  sub     rax, r14
0x18001c6cd  sar     rax, 1
0x18001c6d0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c6d4  jz      loc_18001C798
0x18001c6da  mov     rdx, rax
0x18001c6dd  lea     rcx, [rbp+lpLibFileName]; Src
0x18001c6e1  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001c6e6  lea     rdx, aDll; ".dll"
0x18001c6ed  lea     rcx, [rbp+lpLibFileName]; Src
0x18001c6f1  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18001c6f6  lea     rcx, [rbp+lpLibFileName]
0x18001c6fa  cmp     [rbp+var_18], 7
0x18001c6ff  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18001c704  xor     edx, edx; hFile
0x18001c706  mov     r8d, 1000h; dwFlags
0x18001c70c  call    LoadLibraryExW_0
0x18001c711  mov     rdi, rax
0x18001c714  mov     rdx, [rbp+var_20]
0x18001c718  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18001c71c  lea     rcx, [rbp+lpLibFileName]; Src
0x18001c720  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001c725  test    rdi, rdi
0x18001c728  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001c72f  jz      loc_18001C684
0x18001c735  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18001c73c  mov     rcx, rdi; hModule
0x18001c73f  call    WINRT_IMPL_GetProcAddress
0x18001c744  test    rax, rax
0x18001c747  jnz     short loc_18001C756
0x18001c749  mov     rcx, rdi; hLibModule
0x18001c74c  call    WINRT_IMPL_FreeLibrary
0x18001c751  jmp     loc_18001C680
0x18001c756  mov     [rbp+var_40], 0
0x18001c75e  lea     rdx, [rbp+var_40]
0x18001c762  mov     rcx, [r12]
0x18001c766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c76b  test    eax, eax
0x18001c76d  jz      short loc_18001C781
0x18001c76f  cmp     [rbp+var_40], 0
0x18001c774  jz      short loc_18001C749
0x18001c776  lea     rcx, [rbp+var_40]
0x18001c77a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c77f  jmp     short loc_18001C749
0x18001c781  mov     rax, [rbp+var_40]
0x18001c785  mov     [rbp+var_40], 0
0x18001c78d  mov     [r15], rax
0x18001c790  mov     dword ptr [rsi], 0
0x18001c796  jmp     short loc_18001C7A5
0x18001c798  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18001c79c  xor     ecx, ecx; dwReserved
0x18001c79e  call    SetErrorInfo_0
0x18001c7a3  mov     [rsi], ebx
0x18001c7a5  lea     rcx, [rbp+lpLibFileName]; void *
0x18001c7a9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c7ae  cmp     [rbp+pperrinfo], 0
0x18001c7b3  jz      short loc_18001C7BE
0x18001c7b5  lea     rcx, [rbp+pperrinfo]
0x18001c7b9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c7be  mov     rax, rsi
0x18001c7c1  mov     rcx, [rbp+var_10]
0x18001c7c5  xor     rcx, rsp; StackCookie
0x18001c7c8  call    __security_check_cookie
0x18001c7cd  add     rsp, 60h
0x18001c7d1  pop     r15
0x18001c7d3  pop     r14
0x18001c7d5  pop     r12
0x18001c7d7  pop     rdi
0x18001c7d8  pop     rsi
0x18001c7d9  pop     rbx
0x18001c7da  pop     rbp
0x18001c7db  retn
```
