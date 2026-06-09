# CMidi2KSMidiEndpointManager::OnDeviceUpdated(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)

- ea: `0x18001e8a0`
- end: `0x18001ecad`
- name: `?OnDeviceUpdated@CMidi2KSMidiEndpointManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z`
- size: `1037`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004410`
- `0x1800052fc`
- `0x180005374`
- `0x18000c250`
- `0x18000d1c0`
- `0x18000f304`
- `0x1800112b0`
- `0x180015348`
- `0x1800164c4`
- `0x18001e8a0`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001ebe8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001ebe8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001eb2a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001eb2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CMidi2KSMidiEndpointManager::OnDeviceUpdated(__int64 a1, __int64 *a2, __int64 *a3)
{
  __int64 v5; // rcx
  signed int v6; // eax
  __int64 v7; // r8
  signed int v8; // eax
  LPVOID v9; // rcx
  signed int v10; // eax
  __int64 v11; // r8
  void *v12; // rdi
  signed int v13; // eax
  __int64 v14; // r8
  void *v15; // rbx
  unsigned int v16; // esi
  int v17; // esi
  signed int v18; // eax
  __int64 v19; // r8
  unsigned int v20; // esi
  signed int v21; // eax
  __int64 v22; // r8
  const wchar_t *v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rax
  void *v26; // rdi
  int v27; // eax
  HANDLE ProcessHeap; // rax
  signed int v29; // eax
  __int64 v30; // r8
  _BYTE v32[8]; // [rsp+20h] [rbp-A9h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-A1h] BYREF
  unsigned int v34; // [rsp+30h] [rbp-99h]
  unsigned int v35; // [rsp+38h] [rbp-91h] BYREF
  const char *v36; // [rsp+40h] [rbp-89h]
  __int64 v37; // [rsp+48h] [rbp-81h]
  void *v38; // [rsp+50h] [rbp-79h] BYREF
  void *v39; // [rsp+58h] [rbp-71h] BYREF
  __int64 (__fastcall ***v40)(_QWORD, __int64 *, LPVOID *); // [rsp+60h] [rbp-69h] BYREF
  __int64 v41; // [rsp+68h] [rbp-61h] BYREF
  __int64 v42[3]; // [rsp+70h] [rbp-59h] BYREF
  _OWORD v43[2]; // [rsp+88h] [rbp-41h] BYREF
  _OWORD v44[2]; // [rsp+A8h] [rbp-21h] BYREF
  _BYTE v45[32]; // [rsp+C8h] [rbp-1h] BYREF

  v42[1] = (__int64)a2;
  v42[2] = (__int64)a3;
  v34 = 0;
  v40 = 0;
  v5 = *a3;
  v35 = 1098;
  v36 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
  v37 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, __int64 *, LPVOID *)))(*(_QWORD *)v5 + 56LL))(
         v5,
         &v40);
  if ( v6 < 0 )
    winrt::throw_hresult(v6, &v35, v7);
  v42[0] = (__int64)v40;
  v38 = 0;
  lpMem = 0;
  if ( v40 )
  {
    v8 = (**v40)(
           v40,
           winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>>,
           &lpMem);
    v9 = lpMem;
  }
  else
  {
    v8 = 0;
    v9 = 0;
  }
  v35 = 21;
  v36 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v37 = 0;
  if ( v8 < 0 )
    winrt::throw_hresult(v8, &v35, v7);
  v35 = 23;
  v36 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v37 = 0;
  v10 = (*(__int64 (__fastcall **)(LPVOID, void **))(*(_QWORD *)v9 + 48LL))(v9, &v38);
  if ( v10 < 0 )
    winrt::throw_hresult(v10, &v35, v11);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&lpMem);
  v12 = v38;
  lpMem = v38;
  v32[0] = 0;
  v35 = 64;
  v36 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v37 = 0;
  v13 = (*(__int64 (__fastcall **)(void *, _BYTE *))(*(_QWORD *)v38 + 56LL))(v38, v32);
  if ( v13 < 0 )
    winrt::throw_hresult(v13, &v35, v14);
  if ( v32[0] )
  {
    v15 = v12;
    v39 = v12;
  }
  else
  {
    v15 = 0;
    v39 = 0;
    if ( v12 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&lpMem);
    v12 = 0;
  }
  v16 = 15;
  v41 = 0;
  while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v39, &v41) )
  {
    v38 = 0;
    v17 = v16 | 0x20;
    v34 = v17;
    v35 = 46;
    v36 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    v37 = 0;
    v18 = (*(__int64 (__fastcall **)(void *, void **))(*(_QWORD *)v12 + 48LL))(v12, &v38);
    if ( v18 < 0 )
      winrt::throw_hresult(v18, &v35, v19);
    lpMem = 0;
    v20 = v17 & 0xFFFFFF8F | 0x50;
    v34 = v20;
    v35 = 118;
    v36 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    v37 = 0;
    v21 = (*(__int64 (__fastcall **)(void *, LPVOID *))(*(_QWORD *)v38 + 48LL))(v38, &lpMem);
    if ( v21 < 0 )
      winrt::throw_hresult(v21, &v35, v22);
    if ( lpMem )
      v23 = (const wchar_t *)*((_QWORD *)lpMem + 2);
    else
      v23 = &S1;
    memset(v44, 0, sizeof(v44));
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
    std::wstring::_Construct<1,unsigned short const *>(v44, v23, v24);
    memset(v43, 0, sizeof(v43));
    std::wstring::_Construct<1,unsigned short const *>(v43, L"KS: ", 4);
    v25 = std::operator+<unsigned short>(v45, v43, v44);
    if ( *(_QWORD *)(v25 + 24) > 7u )
      v25 = *(_QWORD *)v25;
    OutputDebugStringW((LPCWSTR)v25);
    std::wstring::~wstring(v45);
    std::wstring::~wstring(v43);
    std::wstring::~wstring(v44);
    v16 = v20 & 0xFFFFFFBF;
    v26 = lpMem;
    if ( lpMem )
    {
      v27 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v27 )
      {
        if ( v27 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v26);
      }
    }
    if ( v38 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v38);
    v32[0] = 0;
    v12 = v15;
    v35 = 82;
    v36 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    v37 = 0;
    v29 = (*(__int64 (__fastcall **)(void *, _BYTE *))(*(_QWORD *)v15 + 64LL))(v15, v32);
    if ( v29 < 0 )
      winrt::throw_hresult(v29, &v35, v30);
    if ( !v32[0] )
    {
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v39);
      v15 = 0;
      v39 = 0;
      v12 = 0;
    }
  }
  if ( v12 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v39);
  if ( v40 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v42);
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  if ( *a3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
  return 0;
}

```

## disassembly

```asm
0x18001e8a0  mov     [rsp-8+arg_0], rbx
0x18001e8a5  push    rbp
0x18001e8a6  push    rsi
0x18001e8a7  push    rdi
0x18001e8a8  push    r12
0x18001e8aa  push    r13
0x18001e8ac  push    r14
0x18001e8ae  push    r15
0x18001e8b0  lea     rbp, [rsp-27h]
0x18001e8b5  sub     rsp, 0F0h
0x18001e8bc  mov     rax, cs:__security_cookie
0x18001e8c3  xor     rax, rsp
0x18001e8c6  mov     [rbp+57h+var_38], rax
0x18001e8ca  mov     r14, r8
0x18001e8cd  mov     r15, rdx
0x18001e8d0  mov     [rbp+57h+var_A8], rdx
0x18001e8d4  mov     [rbp+57h+var_A0], r8
0x18001e8d8  xor     r12d, r12d
0x18001e8db  mov     [rsp+120h+var_F0], r12d
0x18001e8e0  mov     [rbp+57h+var_C0], r12
0x18001e8e4  mov     rcx, [r8]
0x18001e8e7  mov     [rsp+120h+var_E8], 44Ah
0x18001e8ef  lea     rax, aOnecoreuapInte_11; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001e8f6  mov     [rsp+120h+var_E0], rax
0x18001e8fb  mov     [rsp+120h+var_D8], r12
0x18001e900  mov     rax, [rcx]
0x18001e903  lea     rdx, [rbp+57h+var_C0]
0x18001e907  mov     rax, [rax+38h]
0x18001e90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e910  test    eax, eax
0x18001e912  js      loc_18001EC5F
0x18001e918  mov     rcx, [rbp+57h+var_C0]
0x18001e91c  mov     [rbp+57h+var_B0], rcx
0x18001e920  mov     [rbp+57h+var_D0], r12
0x18001e924  mov     [rsp+120h+lpMem], r12
0x18001e929  test    rcx, rcx
0x18001e92c  jnz     short loc_18001E936
0x18001e92e  mov     eax, r12d
0x18001e931  mov     ecx, r12d
0x18001e934  jmp     short loc_18001E957
0x18001e936  mov     rax, [rcx]
0x18001e939  lea     r8, [rsp+120h+lpMem]
0x18001e93e  lea     rdx, ??$guid_v@U?$IIterable@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>>
0x18001e945  mov     rax, [rax]
0x18001e948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e94d  mov     rcx, [rsp+120h+lpMem]
0x18001e952  mov     [rsp+120h+lpMem], rcx
0x18001e957  mov     [rsp+120h+var_E8], 15h
0x18001e95f  lea     r13, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001e966  mov     [rsp+120h+var_E0], r13
0x18001e96b  mov     [rsp+120h+var_D8], r12
0x18001e970  test    eax, eax
0x18001e972  js      loc_18001EC6C
0x18001e978  mov     [rsp+120h+var_E8], 17h
0x18001e980  mov     [rsp+120h+var_E0], r13
0x18001e985  mov     [rsp+120h+var_D8], r12
0x18001e98a  mov     rax, [rcx]
0x18001e98d  lea     rdx, [rbp+57h+var_D0]
0x18001e991  mov     rax, [rax+30h]
0x18001e995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e99a  test    eax, eax
0x18001e99c  js      loc_18001EC79
0x18001e9a2  lea     rcx, [rsp+120h+lpMem]
0x18001e9a7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e9ac  mov     rdi, [rbp+57h+var_D0]
0x18001e9b0  mov     [rsp+120h+lpMem], rdi
0x18001e9b5  mov     [rsp+120h+var_100], r12b
0x18001e9ba  mov     [rsp+120h+var_E8], 40h ; '@'
0x18001e9c2  mov     [rsp+120h+var_E0], r13
0x18001e9c7  mov     [rsp+120h+var_D8], r12
0x18001e9cc  mov     rax, [rdi]
0x18001e9cf  lea     rdx, [rsp+120h+var_100]
0x18001e9d4  mov     rcx, rdi
0x18001e9d7  mov     rax, [rax+38h]
0x18001e9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9e0  test    eax, eax
0x18001e9e2  js      loc_18001EC86
0x18001e9e8  cmp     [rsp+120h+var_100], r12b
0x18001e9ed  jnz     short loc_18001EA0A
0x18001e9ef  mov     rbx, r12
0x18001e9f2  mov     [rbp+57h+var_C8], rbx
0x18001e9f6  test    rdi, rdi
0x18001e9f9  jz      short loc_18001EA05
0x18001e9fb  lea     rcx, [rsp+120h+lpMem]
0x18001ea00  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ea05  mov     rdi, r12
0x18001ea08  jmp     short loc_18001EA11
0x18001ea0a  mov     rbx, rdi
0x18001ea0d  mov     [rbp+57h+var_C8], rbx
0x18001ea11  mov     esi, 0Fh
0x18001ea16  mov     [rbp+57h+var_B8], r12
0x18001ea1a  lea     rdx, [rbp+57h+var_B8]
0x18001ea1e  lea     rcx, [rbp+57h+var_C8]
0x18001ea22  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001ea27  test    al, al
0x18001ea29  jnz     loc_18001EBEF
0x18001ea2f  mov     [rbp+57h+var_D0], r12
0x18001ea33  or      esi, 20h
0x18001ea36  mov     [rsp+120h+var_F0], esi
0x18001ea3a  mov     [rsp+120h+var_E8], 2Eh ; '.'
0x18001ea42  mov     [rsp+120h+var_E0], r13
0x18001ea47  mov     [rsp+120h+var_D8], r12
0x18001ea4c  mov     rax, [rdi]
0x18001ea4f  lea     rdx, [rbp+57h+var_D0]
0x18001ea53  mov     rcx, rdi
0x18001ea56  mov     rax, [rax+30h]
0x18001ea5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea5f  test    eax, eax
0x18001ea61  js      loc_18001EC52
0x18001ea67  and     esi, 0FFFFFFDFh
0x18001ea6a  or      esi, 10h
0x18001ea6d  mov     [rsp+120h+lpMem], r12
0x18001ea72  or      esi, 40h
0x18001ea75  mov     [rsp+120h+var_F0], esi
0x18001ea79  mov     rcx, [rbp+57h+var_D0]
0x18001ea7d  mov     [rsp+120h+var_E8], 76h ; 'v'
0x18001ea85  mov     [rsp+120h+var_E0], r13
0x18001ea8a  mov     [rsp+120h+var_D8], r12
0x18001ea8f  mov     rax, [rcx]
0x18001ea92  lea     rdx, [rsp+120h+lpMem]
0x18001ea97  mov     rax, [rax+30h]
0x18001ea9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaa0  test    eax, eax
0x18001eaa2  js      loc_18001ECA0
0x18001eaa8  mov     rax, [rsp+120h+lpMem]
0x18001eaad  test    rax, rax
0x18001eab0  jz      short loc_18001EAB8
0x18001eab2  mov     rdx, [rax+10h]
0x18001eab6  jmp     short loc_18001EABF
0x18001eab8  lea     rdx, S1
0x18001eabf  xorps   xmm0, xmm0
0x18001eac2  movups  [rbp+57h+var_78], xmm0
0x18001eac6  xorps   xmm1, xmm1
0x18001eac9  movdqu  [rbp+57h+var_68], xmm1
0x18001eace  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001ead2  inc     r8
0x18001ead5  cmp     [rdx+r8*2], r12w
0x18001eada  jnz     short loc_18001EAD2
0x18001eadc  lea     rcx, [rbp+57h+var_78]
0x18001eae0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001eae5  nop
0x18001eae6  xorps   xmm0, xmm0
0x18001eae9  movups  [rbp+57h+var_98], xmm0
0x18001eaed  xorps   xmm1, xmm1
0x18001eaf0  movdqu  [rbp+57h+var_88], xmm1
0x18001eaf5  mov     r8d, 4
0x18001eafb  lea     rdx, aKs; "KS: "
0x18001eb02  lea     rcx, [rbp+57h+var_98]
0x18001eb06  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001eb0b  nop
0x18001eb0c  lea     r8, [rbp+57h+var_78]
0x18001eb10  lea     rdx, [rbp+57h+var_98]
0x18001eb14  lea     rcx, [rbp+57h+var_58]
0x18001eb18  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18001eb1d  cmp     qword ptr [rax+18h], 7
0x18001eb22  jbe     short loc_18001EB27
0x18001eb24  mov     rax, [rax]
0x18001eb27  mov     rcx, rax; lpOutputString
0x18001eb2a  call    cs:__imp_OutputDebugStringW
0x18001eb30  lea     rcx, [rbp+57h+var_58]; void *
0x18001eb34  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001eb39  nop
0x18001eb3a  lea     rcx, [rbp+57h+var_98]; void *
0x18001eb3e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001eb43  nop
0x18001eb44  lea     rcx, [rbp+57h+var_78]; void *
0x18001eb48  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001eb4d  and     esi, 0FFFFFFBFh
0x18001eb50  mov     rdi, [rsp+120h+lpMem]
0x18001eb55  test    rdi, rdi
0x18001eb58  jz      short loc_18001EB80
0x18001eb5a  or      eax, 0FFFFFFFFh
0x18001eb5d  lock xadd [rdi+18h], eax
0x18001eb62  sub     eax, 1
0x18001eb65  jnz     short loc_18001EB7C
0x18001eb67  nop
0x18001eb68  call    WINRT_IMPL_GetProcessHeap
0x18001eb6d  mov     rcx, rax; hHeap
0x18001eb70  mov     r8, rdi; lpMem
0x18001eb73  xor     edx, edx; dwFlags
0x18001eb75  call    WINRT_IMPL_HeapFree
0x18001eb7a  jmp     short loc_18001EB80
0x18001eb7c  test    eax, eax
0x18001eb7e  js      short loc_18001EBE8
0x18001eb80  cmp     [rbp+57h+var_D0], r12
0x18001eb84  jz      short loc_18001EB8F
0x18001eb86  lea     rcx, [rbp+57h+var_D0]
0x18001eb8a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001eb8f  mov     [rsp+120h+var_100], r12b
0x18001eb94  mov     rdi, rbx
0x18001eb97  mov     [rsp+120h+var_E8], 52h ; 'R'
0x18001eb9f  mov     [rsp+120h+var_E0], r13
0x18001eba4  mov     [rsp+120h+var_D8], r12
0x18001eba9  mov     rax, [rbx]
0x18001ebac  lea     rdx, [rsp+120h+var_100]
0x18001ebb1  mov     rcx, rbx
0x18001ebb4  mov     rax, [rax+40h]
0x18001ebb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebbd  test    eax, eax
0x18001ebbf  js      loc_18001EC93
0x18001ebc5  cmp     [rsp+120h+var_100], r12b
0x18001ebca  jnz     loc_18001EA1A
0x18001ebd0  lea     rcx, [rbp+57h+var_C8]
0x18001ebd4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ebd9  mov     rbx, r12
0x18001ebdc  mov     [rbp+57h+var_C8], rbx
0x18001ebe0  mov     rdi, r12
0x18001ebe3  jmp     loc_18001EA1A
0x18001ebe8  call    cs:__imp_abort
0x18001ebef  test    rdi, rdi
0x18001ebf2  jz      short loc_18001EBFE
0x18001ebf4  lea     rcx, [rbp+57h+var_C8]
0x18001ebf8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ebfd  nop
0x18001ebfe  cmp     [rbp+57h+var_C0], r12
0x18001ec02  jz      short loc_18001EC0E
0x18001ec04  lea     rcx, [rbp+57h+var_B0]
0x18001ec08  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ec0d  nop
0x18001ec0e  cmp     [r15], r12
0x18001ec11  jz      short loc_18001EC1C
0x18001ec13  mov     rcx, r15
0x18001ec16  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ec1b  nop
0x18001ec1c  cmp     [r14], r12
0x18001ec1f  jz      short loc_18001EC29
0x18001ec21  mov     rcx, r14
0x18001ec24  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ec29  xor     eax, eax
0x18001ec2b  mov     rcx, [rbp+57h+var_38]
0x18001ec2f  xor     rcx, rsp; StackCookie
0x18001ec32  call    __security_check_cookie
0x18001ec37  mov     rbx, [rsp+120h+arg_0]
0x18001ec3f  add     rsp, 0F0h
0x18001ec46  pop     r15
0x18001ec48  pop     r14
0x18001ec4a  pop     r13
0x18001ec4c  pop     r12
0x18001ec4e  pop     rdi
0x18001ec4f  pop     rsi
0x18001ec50  pop     rbp
0x18001ec51  retn
0x18001ec52  lea     rdx, [rsp+120h+var_E8]
0x18001ec57  mov     ecx, eax
0x18001ec59  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001ec5f  lea     rdx, [rsp+120h+var_E8]
0x18001ec64  mov     ecx, eax
0x18001ec66  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001ec6c  lea     rdx, [rsp+120h+var_E8]
0x18001ec71  mov     ecx, eax
0x18001ec73  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001ec79  lea     rdx, [rsp+120h+var_E8]
0x18001ec7e  mov     ecx, eax
0x18001ec80  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001ec86  lea     rdx, [rsp+120h+var_E8]
0x18001ec8b  mov     ecx, eax
0x18001ec8d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001ec93  lea     rdx, [rsp+120h+var_E8]
0x18001ec98  mov     ecx, eax
0x18001ec9a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001eca0  lea     rdx, [rsp+120h+var_E8]
0x18001eca5  mov     ecx, eax
0x18001eca7  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
