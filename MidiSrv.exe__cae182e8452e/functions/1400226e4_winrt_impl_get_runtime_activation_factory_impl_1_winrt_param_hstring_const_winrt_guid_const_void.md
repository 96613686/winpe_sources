# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x1400226e4`
- end: `0x14002294c`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `616`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002260c`

## callees

- `0x140005150`
- `0x1400054c0`
- `0x1400061dc`
- `0x140006224`
- `0x140006230`
- `0x1400062bc`
- `0x1400062e0`
- `0x140006304`
- `0x1400072d4`
- `0x140007c20`
- `0x14000cc2c`
- `0x14001487c`
- `0x14001f64c`
- `0x1400226e4`
- `0x14005a010`

## string_xrefs

- `0x140022748`: `combase.dll`
- `0x1400228a5`: `DllGetActivationFactory`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  const wchar_t *v13; // rdx
  __int64 v14; // r8
  LPCWSTR *v15; // r14
  char *v16; // rdi
  __int64 last_trivial_2; // rax
  const WCHAR *v18; // rcx
  HMODULE v19; // rdi
  FARPROC v20; // rax
  __int64 v21; // rax
  __int64 v23; // [rsp+20h] [rbp-40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-38h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v26; // [rsp+40h] [rbp-20h]
  unsigned __int64 v27; // [rsp+48h] [rbp-18h]

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
      v23 = 0;
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v23);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      *(_OWORD *)lpLibFileName = 0;
      v26 = 0;
      v27 = 0;
      v12 = *a2;
      if ( *a2 )
      {
        v13 = *(const wchar_t **)(v12 + 16);
        v14 = *(unsigned int *)(v12 + 4);
      }
      else
      {
        v13 = &S2;
        v14 = 0;
      }
      std::wstring::_Construct<1,unsigned short const *>(lpLibFileName, v13, v14);
      while ( 1 )
      {
        v15 = lpLibFileName;
        if ( v27 > 7 )
          v15 = (LPCWSTR *)lpLibFileName[0];
        if ( !v26 )
          break;
        v16 = (char *)v15 + 2 * v26;
        last_trivial_2 = _std_find_last_trivial_2(v15, v16, 46);
        if ( (char *)last_trivial_2 == v16 || (last_trivial_2 - (__int64)v15) >> 1 == -1 )
          break;
        std::wstring::resize(lpLibFileName);
        std::wstring::operator+=(lpLibFileName, L".dll");
        v18 = (const WCHAR *)lpLibFileName;
        if ( v27 > 7 )
          v18 = lpLibFileName[0];
        v19 = LoadLibraryExW_0(v18, 0, 0x1000u);
        std::wstring::resize(lpLibFileName);
        if ( v19 )
        {
          v20 = WINRT_IMPL_GetProcAddress(v19, "DllGetActivationFactory");
          if ( v20 )
          {
            v23 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v20)(*a2, &v23) )
            {
              v21 = v23;
              v23 = 0;
              *a4 = v21;
              *a1 = 0;
              goto LABEL_28;
            }
            if ( v23 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
          }
          WINRT_IMPL_FreeLibrary(v19);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_28:
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
0x1400226e4  push    rbp
0x1400226e6  push    rbx
0x1400226e7  push    rsi
0x1400226e8  push    rdi
0x1400226e9  push    r12
0x1400226eb  push    r14
0x1400226ed  push    r15
0x1400226ef  mov     rbp, rsp
0x1400226f2  sub     rsp, 60h
0x1400226f6  mov     rax, cs:__security_cookie
0x1400226fd  xor     rax, rsp
0x140022700  mov     [rbp+var_10], rax
0x140022704  mov     r15, r9
0x140022707  mov     rdi, r8
0x14002270a  mov     r12, rdx
0x14002270d  mov     rsi, rcx
0x140022710  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x140022717  mov     r8, r9
0x14002271a  mov     rdx, rdi
0x14002271d  mov     rcx, [r12]
0x140022721  test    rax, rax
0x140022724  jz      short loc_140022732
0x140022726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002272b  mov     [rsi], eax
0x14002272d  jmp     loc_14002292E
0x140022732  call    RoGetActivationFactory_0
0x140022737  mov     ebx, eax
0x140022739  cmp     eax, 800401F0h
0x14002273e  jnz     short loc_140022795
0x140022740  xor     edx, edx; hFile
0x140022742  mov     r8d, 1000h; dwFlags
0x140022748  lea     rcx, LibFileName; "combase.dll"
0x14002274f  call    LoadLibraryExW_0
0x140022754  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x14002275b  mov     rcx, rax; hModule
0x14002275e  call    WINRT_IMPL_GetProcAddress
0x140022763  test    rax, rax
0x140022766  jnz     short loc_140022773
0x140022768  mov     dword ptr [rsi], 800401F0h
0x14002276e  jmp     loc_14002292E
0x140022773  mov     [rbp+var_40], 0
0x14002277b  lea     rcx, [rbp+var_40]
0x14002277f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022784  mov     r8, r15
0x140022787  mov     rdx, rdi
0x14002278a  mov     rcx, [r12]
0x14002278e  call    RoGetActivationFactory_0
0x140022793  mov     ebx, eax
0x140022795  test    ebx, ebx
0x140022797  jnz     short loc_1400227A0
0x140022799  mov     [rsi], ebx
0x14002279b  jmp     loc_14002292E
0x1400227a0  mov     [rbp+pperrinfo], 0
0x1400227a8  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x1400227ac  xor     ecx, ecx; dwReserved
0x1400227ae  call    GetErrorInfo_0
0x1400227b3  xorps   xmm0, xmm0
0x1400227b6  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x1400227ba  mov     [rbp+var_20], 0
0x1400227c2  mov     [rbp+var_18], 0
0x1400227ca  mov     rax, [r12]
0x1400227ce  test    rax, rax
0x1400227d1  jz      short loc_1400227DD
0x1400227d3  mov     rdx, [rax+10h]
0x1400227d7  mov     r8d, [rax+4]
0x1400227db  jmp     short loc_1400227E7
0x1400227dd  lea     rdx, S2
0x1400227e4  xor     r8d, r8d
0x1400227e7  lea     rcx, [rbp+lpLibFileName]
0x1400227eb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400227f0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400227f4  mov     rax, [rbp+var_20]
0x1400227f8  lea     r14, [rbp+lpLibFileName]
0x1400227fc  cmp     [rbp+var_18], 7
0x140022801  cmova   r14, [rbp+lpLibFileName]
0x140022806  test    rax, rax
0x140022809  jz      loc_140022908
0x14002280f  dec     rax
0x140022812  cmp     rax, rcx
0x140022815  cmovnb  rax, rcx
0x140022819  inc     rax
0x14002281c  lea     rdi, [r14+rax*2]
0x140022820  mov     r8d, 2Eh ; '.'
0x140022826  mov     rdx, rdi
0x140022829  mov     rcx, r14
0x14002282c  call    __std_find_last_trivial_2
0x140022831  cmp     rax, rdi
0x140022834  jz      loc_140022908
0x14002283a  sub     rax, r14
0x14002283d  sar     rax, 1
0x140022840  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140022844  jz      loc_140022908
0x14002284a  mov     rdx, rax
0x14002284d  lea     rcx, [rbp+lpLibFileName]; Src
0x140022851  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x140022856  lea     rdx, aDll; ".dll"
0x14002285d  lea     rcx, [rbp+lpLibFileName]; Src
0x140022861  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x140022866  lea     rcx, [rbp+lpLibFileName]
0x14002286a  cmp     [rbp+var_18], 7
0x14002286f  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x140022874  xor     edx, edx; hFile
0x140022876  mov     r8d, 1000h; dwFlags
0x14002287c  call    LoadLibraryExW_0
0x140022881  mov     rdi, rax
0x140022884  mov     rdx, [rbp+var_20]
0x140022888  add     rdx, 0FFFFFFFFFFFFFFFCh
0x14002288c  lea     rcx, [rbp+lpLibFileName]; Src
0x140022890  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x140022895  test    rdi, rdi
0x140022898  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14002289f  jz      loc_1400227F4
0x1400228a5  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x1400228ac  mov     rcx, rdi; hModule
0x1400228af  call    WINRT_IMPL_GetProcAddress
0x1400228b4  test    rax, rax
0x1400228b7  jnz     short loc_1400228C6
0x1400228b9  mov     rcx, rdi; hLibModule
0x1400228bc  call    WINRT_IMPL_FreeLibrary
0x1400228c1  jmp     loc_1400227F0
0x1400228c6  mov     [rbp+var_40], 0
0x1400228ce  lea     rdx, [rbp+var_40]
0x1400228d2  mov     rcx, [r12]
0x1400228d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400228db  test    eax, eax
0x1400228dd  jz      short loc_1400228F1
0x1400228df  cmp     [rbp+var_40], 0
0x1400228e4  jz      short loc_1400228B9
0x1400228e6  lea     rcx, [rbp+var_40]
0x1400228ea  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400228ef  jmp     short loc_1400228B9
0x1400228f1  mov     rax, [rbp+var_40]
0x1400228f5  mov     [rbp+var_40], 0
0x1400228fd  mov     [r15], rax
0x140022900  mov     dword ptr [rsi], 0
0x140022906  jmp     short loc_140022915
0x140022908  mov     rdx, [rbp+pperrinfo]; perrinfo
0x14002290c  xor     ecx, ecx; dwReserved
0x14002290e  call    SetErrorInfo_0
0x140022913  mov     [rsi], ebx
0x140022915  lea     rcx, [rbp+lpLibFileName]; void *
0x140022919  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002291e  cmp     [rbp+pperrinfo], 0
0x140022923  jz      short loc_14002292E
0x140022925  lea     rcx, [rbp+pperrinfo]
0x140022929  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002292e  mov     rax, rsi
0x140022931  mov     rcx, [rbp+var_10]
0x140022935  xor     rcx, rsp; StackCookie
0x140022938  call    __security_check_cookie
0x14002293d  add     rsp, 60h
0x140022941  pop     r15
0x140022943  pop     r14
0x140022945  pop     r12
0x140022947  pop     rdi
0x140022948  pop     rsi
0x140022949  pop     rbx
0x14002294a  pop     rbp
0x14002294b  retn
```
