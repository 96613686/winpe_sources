# HcfDetector::HandlePackageInstallingStatus(winrt::Windows::ApplicationModel::PackageCatalog &,winrt::Windows::ApplicationModel::PackageInstallingEventArgs &)

- ea: `0x180020724`
- end: `0x180020b6e`
- name: `?HandlePackageInstallingStatus@HcfDetector@@AEBAXAEAUPackageCatalog@ApplicationModel@Windows@winrt@@AEAUPackageInstallingEventArgs@345@@Z`
- size: `1098`
- prototype: `void __fastcall(wchar_t *this, struct winrt::Windows::ApplicationModel::PackageCatalog *, struct winrt::Windows::ApplicationModel::PackageInstallingEventArgs *)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800213c0`

## callees

- `0x1800058cb`
- `0x18000591f`
- `0x18000c478`
- `0x180019c3c`
- `0x180020594`
- `0x180020664`
- `0x1800206c4`
- `0x180020724`
- `0x180021290`
- `0x1800217e4`
- `0x180021894`
- `0x180021bd0`
- `0x180022574`
- `0x180022760`
- `0x1800227b0`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020b1d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020b2c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020b37`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020b1d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020b2c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020b37`

## string_xrefs

- `0x180020a06`: `"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\detecthcf.cpp"`
- `0x180020a25`: `"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\detecthcf.cpp"`
- `0x1800209fa`: `[WSAIFabricHost][HcfDetection] Package installation status. detector=%p PackageFamily='%ls' PackagePublisherId='%ls' PackageFullName='%ls' Version=%u.%u.%u.%u IsOk? %u Progress? %lf IsComplete? %u`
- `0x180020a19`: `[WSAIFabricHost][HcfDetection] Package installation complete. detector=%p`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall HcfDetector::HandlePackageInstallingStatus(
        wchar_t *this,
        struct winrt::Windows::ApplicationModel::PackageCatalog *a2,
        struct winrt::Windows::ApplicationModel::PackageInstallingEventArgs *a3)
{
  __int64 v5; // rcx
  int v6; // eax
  const char *v7; // r9
  void *v8; // rdi
  int v9; // eax
  HANDLE v10; // rax
  void *v11; // rdi
  int v12; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  int IsOK; // edi
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  char v22; // bl
  const wchar_t *v23; // r9
  const wchar_t *v24; // r11
  const wchar_t *v25; // r10
  void *v26; // rdi
  int v27; // eax
  HANDLE v28; // rax
  void *v29; // rdi
  int v30; // eax
  HANDLE v31; // rax
  void *v32; // rdi
  int v33; // ebx
  HANDLE v34; // rax
  LPVOID v35; // [rsp+70h] [rbp-78h] BYREF
  _WORD v36[4]; // [rsp+78h] [rbp-70h] BYREF
  __int64 v37; // [rsp+80h] [rbp-68h] BYREF
  __int64 v38; // [rsp+88h] [rbp-60h] BYREF
  LPVOID v39; // [rsp+90h] [rbp-58h] BYREF
  __int64 v40; // [rsp+98h] [rbp-50h] BYREF
  int v41; // [rsp+A0h] [rbp-48h] BYREF
  __int128 v42; // [rsp+A8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  struct winrt::Windows::ApplicationModel::PackageCatalog *v44; // [rsp+F8h] [rbp+10h] BYREF
  __int64 v45; // [rsp+100h] [rbp+18h] BYREF
  LPVOID lpMem; // [rsp+108h] [rbp+20h] BYREF

  v44 = a2;
  v37 = 0;
  v5 = *(_QWORD *)a3;
  v41 = 0;
  v42 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 56LL))(v5, &v37);
  try
  {
    if ( v6 < 0 )
      winrt::throw_hresult((unsigned int)v6, &v41);
    v38 = v37;
    winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::First(
      &v38,
      &v45);
    winrt::impl::consume_Windows_ApplicationModel_IPackageId<winrt::Windows::ApplicationModel::IPackageId>::FamilyName(
      &v45,
      &v35);
    winrt::impl::consume_Windows_ApplicationModel_IPackageId<winrt::Windows::ApplicationModel::IPackageId>::PublisherId(
      &v45,
      &lpMem);
    if ( !HcfDetector::IsHcfClientPackage((struct winrt::hstring *)&v35, (struct winrt::hstring *)&lpMem) )
    {
      v8 = lpMem;
      if ( !lpMem )
      {
LABEL_9:
        v11 = v35;
        if ( !v35 )
        {
LABEL_14:
          if ( v45 )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v45);
          if ( v37 )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v38);
          return;
        }
        v12 = _InterlockedDecrement((volatile signed __int32 *)v35 + 6);
        if ( !v12 )
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v11);
LABEL_13:
          v35 = 0;
          goto LABEL_14;
        }
        if ( v12 >= 0 )
          goto LABEL_13;
LABEL_54:
        abort();
      }
      v9 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( !v9 )
      {
        v10 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v10, 0, v8);
LABEL_8:
        lpMem = 0;
        goto LABEL_9;
      }
      if ( v9 >= 0 )
        goto LABEL_8;
LABEL_52:
      abort();
    }
    winrt::impl::consume_Windows_ApplicationModel_IPackageId<winrt::Windows::ApplicationModel::IPackageId>::FullName(
      &v45,
      &v39);
    winrt::impl::consume_Windows_ApplicationModel_IPackageId<winrt::Windows::ApplicationModel::IPackageId>::Version(
      &v45,
      v36);
    v16 = winrt::impl::consume_Windows_ApplicationModel_IPackage3<winrt::Windows::ApplicationModel::Package>::Status(
            &v38,
            &v44,
            v14,
            v15);
    IsOK = (unsigned __int8)winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(v16);
    if ( v44 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v44);
    v40 = 0;
    v18 = *(_QWORD *)a3;
    v41 = 0;
    v42 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 64LL))(v18, &v40);
    if ( v19 < 0 )
      winrt::throw_hresult((unsigned int)v19, &v41);
    LOBYTE(v44) = 0;
    v20 = *(_QWORD *)a3;
    v41 = 0;
    v42 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, struct winrt::Windows::ApplicationModel::PackageCatalog **))(*(_QWORD *)v20 + 72LL))(
            v20,
            &v44);
    if ( v21 < 0 )
      winrt::throw_hresult((unsigned int)v21, &v41);
    v22 = (char)v44;
    v23 = &pszText;
    if ( v39 )
      v24 = (const wchar_t *)*((_QWORD *)v39 + 2);
    else
      v24 = &pszText;
    if ( lpMem )
      v25 = (const wchar_t *)*((_QWORD *)lpMem + 2);
    else
      v25 = &pszText;
    if ( v35 )
      v23 = (const wchar_t *)*((_QWORD *)v35 + 2);
    SearchIndexerTrace::Information(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\aifabrichosthelper\\\\lib\\\\detecthcf.cpp\"",
      (const wchar_t *)0x214,
      (unsigned int)L"[WSAIFabricHost][HcfDetection] Package installation status. detector=%p PackageFamily='%ls' PackageP"
                     "ublisherId='%ls' PackageFullName='%ls' Version=%u.%u.%u.%u IsOk? %u Progress? %lf IsComplete? %u",
      this,
      v23,
      v25,
      v24,
      v36[0],
      v36[1],
      v36[2],
      v36[3],
      IsOK,
      v40,
      (_BYTE)v44 != 0);
    if ( v22 )
    {
      SearchIndexerTrace::Information(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\aifabrichosthelper\\\\lib\\\\detecthcf.cpp\"",
        (const wchar_t *)0x21B,
        (unsigned int)L"[WSAIFabricHost][HcfDetection] Package installation complete. detector=%p",
        this);
      HcfDetector::PublishStatus();
    }
    v26 = v39;
    if ( v39 )
    {
      v27 = _InterlockedDecrement((volatile signed __int32 *)v39 + 6);
      if ( v27 )
      {
        if ( v27 < 0 )
          abort();
      }
      else
      {
        v28 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v28, 0, v26);
      }
      v39 = 0;
    }
    v29 = lpMem;
    if ( lpMem )
    {
      v30 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v30 )
      {
        if ( v30 < 0 )
          goto LABEL_52;
      }
      else
      {
        v31 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v31, 0, v29);
      }
      lpMem = 0;
    }
    v32 = v35;
    if ( v35 )
    {
      v33 = _InterlockedDecrement((volatile signed __int32 *)v35 + 6);
      if ( v33 )
      {
        if ( v33 < 0 )
          goto LABEL_54;
      }
      else
      {
        v34 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v34, 0, v32);
      }
      v35 = 0;
    }
    if ( v45 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v45);
    if ( v37 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v38);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x220,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\detecthcf.cpp",
      v7);
  }
}

```

## disassembly

```asm
0x180020724  mov     r11, rsp
0x180020727  mov     [r11+10h], rdx
0x18002072b  push    rbx
0x18002072c  push    rsi
0x18002072d  push    rdi
0x18002072e  push    r14
0x180020730  push    r15
0x180020732  sub     rsp, 0C0h
0x180020739  mov     rbx, r8
0x18002073c  mov     r14, rcx
0x18002073f  xor     r15d, r15d
0x180020742  mov     [r11-68h], r15
0x180020746  mov     rcx, [r8]
0x180020749  mov     [r11-48h], r15d
0x18002074d  xorps   xmm0, xmm0
0x180020750  movdqu  xmmword ptr [r11-40h], xmm0
0x180020756  mov     rax, [rcx]
0x180020759  lea     rdx, [r11-68h]
0x18002075d  mov     rax, [rax+38h]
0x180020761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020766  test    eax, eax
0x180020768  js      loc_180020B3E
0x18002076e  mov     rax, [rsp+0E8h+var_68]
0x180020776  mov     [rsp+0E8h+var_60], rax
0x18002077e  lea     rdx, [rsp+0E8h+arg_10]
0x180020786  lea     rcx, [rsp+0E8h+var_60]
0x18002078e  call    ?First@?$consume_Windows_Foundation_Collections_IIterable@U?$IIterable@UPackage@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UPackage@ApplicationModel@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::First(void)
0x180020793  nop
0x180020794  lea     rdx, [rsp+0E8h+var_78]
0x180020799  lea     rcx, [rsp+0E8h+arg_10]
0x1800207a1  call    ?FamilyName@?$consume_Windows_ApplicationModel_IPackageId@UIPackageId@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageId<winrt::Windows::ApplicationModel::IPackageId>::FamilyName(void)
0x1800207a6  nop
0x1800207a7  lea     rdx, [rsp+0E8h+lpMem]
0x1800207af  lea     rcx, [rsp+0E8h+arg_10]
0x1800207b7  call    ?PublisherId@?$consume_Windows_ApplicationModel_IPackageId@UIPackageId@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageId<winrt::Windows::ApplicationModel::IPackageId>::PublisherId(void)
0x1800207bc  nop
0x1800207bd  lea     rdx, [rsp+0E8h+lpMem]; struct winrt::hstring *
0x1800207c5  lea     rcx, [rsp+0E8h+var_78]; struct winrt::hstring *
0x1800207ca  call    ?IsHcfClientPackage@HcfDetector@@CA_NAEAUhstring@winrt@@0@Z; HcfDetector::IsHcfClientPackage(winrt::hstring &,winrt::hstring &)
0x1800207cf  test    al, al
0x1800207d1  jnz     loc_180020883
0x1800207d7  mov     rdi, [rsp+0E8h+lpMem]
0x1800207df  or      ebx, 0FFFFFFFFh
0x1800207e2  test    rdi, rdi
0x1800207e5  jz      short loc_180020818
0x1800207e7  mov     eax, ebx
0x1800207e9  lock xadd [rdi+18h], eax
0x1800207ee  sub     eax, 1
0x1800207f1  jnz     short loc_180020808
0x1800207f3  nop
0x1800207f4  call    WINRT_IMPL_GetProcessHeap
0x1800207f9  mov     rcx, rax; hHeap
0x1800207fc  mov     r8, rdi; lpMem
0x1800207ff  xor     edx, edx; dwFlags
0x180020801  call    WINRT_IMPL_HeapFree
0x180020806  jmp     short loc_180020810
0x180020808  test    eax, eax
0x18002080a  js      loc_180020B2C
0x180020810  mov     [rsp+0E8h+lpMem], r15
0x180020818  mov     rdi, [rsp+0E8h+var_78]
0x18002081d  test    rdi, rdi
0x180020820  jz      short loc_18002084E
0x180020822  lock xadd [rdi+18h], ebx
0x180020827  sub     ebx, 1
0x18002082a  jnz     short loc_180020841
0x18002082c  nop
0x18002082d  call    WINRT_IMPL_GetProcessHeap
0x180020832  mov     rcx, rax; hHeap
0x180020835  mov     r8, rdi; lpMem
0x180020838  xor     edx, edx; dwFlags
0x18002083a  call    WINRT_IMPL_HeapFree
0x18002083f  jmp     short loc_180020849
0x180020841  test    ebx, ebx
0x180020843  js      loc_180020B37
0x180020849  mov     [rsp+0E8h+var_78], r15
0x18002084e  cmp     [rsp+0E8h+arg_10], r15
0x180020856  jz      short loc_180020866
0x180020858  lea     rcx, [rsp+0E8h+arg_10]
0x180020860  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180020865  nop
0x180020866  cmp     [rsp+0E8h+var_68], r15
0x18002086e  jz      short loc_18002087E
0x180020870  lea     rcx, [rsp+0E8h+var_60]
0x180020878  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18002087d  nop
0x18002087e  jmp     loc_180020B06
0x180020883  lea     rdx, [rsp+0E8h+var_58]
0x18002088b  lea     rcx, [rsp+0E8h+arg_10]
0x180020893  call    ?FullName@?$consume_Windows_ApplicationModel_IPackageId@UIPackageId@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageId<winrt::Windows::ApplicationModel::IPackageId>::FullName(void)
0x180020898  nop
0x180020899  lea     rdx, [rsp+0E8h+var_70]
0x18002089e  lea     rcx, [rsp+0E8h+arg_10]
0x1800208a6  call    ?Version@?$consume_Windows_ApplicationModel_IPackageId@UIPackageId@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageId<winrt::Windows::ApplicationModel::IPackageId>::Version(void)
0x1800208ab  lea     rdx, [rsp+0E8h+arg_8]
0x1800208b3  lea     rcx, [rsp+0E8h+var_60]
0x1800208bb  call    ?Status@?$consume_Windows_ApplicationModel_IPackage3@UPackage@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackage3<winrt::Windows::ApplicationModel::Package>::Status(void)
0x1800208c0  nop
0x1800208c1  mov     rcx, rax
0x1800208c4  call    ?VerifyIsOK@?$consume_Windows_ApplicationModel_IPackageStatus@UIPackageStatus@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(void)
0x1800208c9  movzx   edi, al
0x1800208cc  cmp     [rsp+0E8h+arg_8], r15
0x1800208d4  jz      short loc_1800208E3
0x1800208d6  lea     rcx, [rsp+0E8h+arg_8]
0x1800208de  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800208e3  xorps   xmm0, xmm0
0x1800208e6  movsd   [rsp+0E8h+var_50], xmm0
0x1800208ef  mov     rcx, [rbx]
0x1800208f2  mov     [rsp+0E8h+var_48], r15d
0x1800208fa  movdqu  [rsp+0E8h+var_40], xmm0
0x180020903  mov     rax, [rcx]
0x180020906  lea     rdx, [rsp+0E8h+var_50]
0x18002090e  mov     rax, [rax+40h]
0x180020912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020917  test    eax, eax
0x180020919  js      loc_180020B4E
0x18002091f  mov     byte ptr [rsp+0E8h+arg_8], r15b
0x180020927  mov     rcx, [rbx]
0x18002092a  mov     [rsp+0E8h+var_48], r15d
0x180020932  xorps   xmm0, xmm0
0x180020935  movdqu  [rsp+0E8h+var_40], xmm0
0x18002093e  mov     rax, [rcx]
0x180020941  lea     rdx, [rsp+0E8h+arg_8]
0x180020949  mov     rax, [rax+48h]
0x18002094d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020952  test    eax, eax
0x180020954  js      loc_180020B5D
0x18002095a  movsd   xmm0, [rsp+0E8h+var_50]
0x180020963  mov     bl, byte ptr [rsp+0E8h+arg_8]
0x18002096a  mov     esi, r15d
0x18002096d  test    bl, bl
0x18002096f  setnz   sil
0x180020973  mov     rax, [rsp+0E8h+var_58]
0x18002097b  lea     r9, pszText
0x180020982  test    rax, rax
0x180020985  jz      short loc_18002098D
0x180020987  mov     r11, [rax+10h]
0x18002098b  jmp     short loc_180020990
0x18002098d  mov     r11, r9
0x180020990  mov     rax, [rsp+0E8h+lpMem]
0x180020998  test    rax, rax
0x18002099b  jz      short loc_1800209A3
0x18002099d  mov     r10, [rax+10h]
0x1800209a1  jmp     short loc_1800209A6
0x1800209a3  mov     r10, r9
0x1800209a6  mov     rax, [rsp+0E8h+var_78]
0x1800209ab  test    rax, rax
0x1800209ae  jz      short loc_1800209B4
0x1800209b0  mov     r9, [rax+10h]
0x1800209b4  movzx   eax, [rsp+0E8h+var_6A]
0x1800209b9  movzx   ecx, [rsp+0E8h+var_6C]
0x1800209be  movzx   edx, [rsp+0E8h+var_6E]
0x1800209c3  movzx   r8d, [rsp+0E8h+var_70]
0x1800209c9  mov     [rsp+0E8h+var_80], esi
0x1800209cd  movsd   [rsp+0E8h+var_88], xmm0
0x1800209d3  mov     [rsp+0E8h+var_90], edi
0x1800209d7  mov     [rsp+0E8h+var_98], eax
0x1800209db  mov     [rsp+0E8h+var_A0], ecx
0x1800209df  mov     [rsp+0E8h+var_A8], edx
0x1800209e3  mov     [rsp+0E8h+var_B0], r8d
0x1800209e8  mov     [rsp+0E8h+var_B8], r11
0x1800209ed  mov     [rsp+0E8h+var_C0], r10
0x1800209f2  mov     [rsp+0E8h+var_C8], r9
0x1800209f7  mov     r9, r14; wchar_t *
0x1800209fa  lea     r8, aWsaifabrichost_4; "[WSAIFabricHost][HcfDetection] Package "...
0x180020a01  mov     edx, 214h; wchar_t *
0x180020a06  lea     rcx, aOnecoreuapBase_8; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180020a0d  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x180020a12  test    bl, bl
0x180020a14  jz      short loc_180020A37
0x180020a16  mov     r9, r14; wchar_t *
0x180020a19  lea     r8, aWsaifabrichost_2; "[WSAIFabricHost][HcfDetection] Package "...
0x180020a20  mov     edx, 21Bh; wchar_t *
0x180020a25  lea     rcx, aOnecoreuapBase_8; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180020a2c  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x180020a31  call    ?PublishStatus@HcfDetector@@CAXXZ; HcfDetector::PublishStatus(void)
0x180020a36  nop
0x180020a37  mov     rdi, [rsp+0E8h+var_58]
0x180020a3f  or      ebx, 0FFFFFFFFh
0x180020a42  test    rdi, rdi
0x180020a45  jz      short loc_180020A72
0x180020a47  mov     eax, ebx
0x180020a49  lock xadd [rdi+18h], eax
0x180020a4e  sub     eax, 1
0x180020a51  jnz     loc_180020B15
0x180020a57  nop
0x180020a58  call    WINRT_IMPL_GetProcessHeap
0x180020a5d  mov     rcx, rax; hHeap
0x180020a60  mov     r8, rdi; lpMem
0x180020a63  xor     edx, edx; dwFlags
0x180020a65  call    WINRT_IMPL_HeapFree
0x180020a6a  mov     [rsp+0E8h+var_58], r15
0x180020a72  mov     rdi, [rsp+0E8h+lpMem]
0x180020a7a  test    rdi, rdi
0x180020a7d  jz      short loc_180020AAA
0x180020a7f  mov     eax, ebx
0x180020a81  lock xadd [rdi+18h], eax
0x180020a86  sub     eax, 1
0x180020a89  jnz     loc_180020B24
0x180020a8f  nop
0x180020a90  call    WINRT_IMPL_GetProcessHeap
0x180020a95  mov     rcx, rax; hHeap
0x180020a98  mov     r8, rdi; lpMem
0x180020a9b  xor     edx, edx; dwFlags
0x180020a9d  call    WINRT_IMPL_HeapFree
0x180020aa2  mov     [rsp+0E8h+lpMem], r15
0x180020aaa  mov     rdi, [rsp+0E8h+var_78]
0x180020aaf  test    rdi, rdi
0x180020ab2  jz      short loc_180020AD6
0x180020ab4  lock xadd [rdi+18h], ebx
0x180020ab9  sub     ebx, 1
0x180020abc  jnz     short loc_180020B33
0x180020abe  nop
0x180020abf  call    WINRT_IMPL_GetProcessHeap
0x180020ac4  mov     rcx, rax; hHeap
0x180020ac7  mov     r8, rdi; lpMem
0x180020aca  xor     edx, edx; dwFlags
0x180020acc  call    WINRT_IMPL_HeapFree
0x180020ad1  mov     [rsp+0E8h+var_78], r15
0x180020ad6  cmp     [rsp+0E8h+arg_10], r15
0x180020ade  jz      short loc_180020AEE
0x180020ae0  lea     rcx, [rsp+0E8h+arg_10]
0x180020ae8  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180020aed  nop
0x180020aee  cmp     [rsp+0E8h+var_68], r15
0x180020af6  jz      short loc_180020B06
0x180020af8  lea     rcx, [rsp+0E8h+var_60]
0x180020b00  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180020b05  nop
0x180020b06  add     rsp, 0C0h
0x180020b0d  pop     r15
0x180020b0f  pop     r14
0x180020b11  pop     rdi
0x180020b12  pop     rsi
0x180020b13  pop     rbx
0x180020b14  retn
0x180020b15  test    eax, eax
0x180020b17  jns     loc_180020A6A
0x180020b1d  call    cs:__imp_abort
0x180020b24  test    eax, eax
0x180020b26  jns     loc_180020AA2
0x180020b2c  call    cs:__imp_abort
0x180020b33  test    ebx, ebx
0x180020b35  jns     short loc_180020AD1
0x180020b37  call    cs:__imp_abort
0x180020b3e  lea     rdx, [rsp+0E8h+var_48]
0x180020b46  mov     ecx, eax
0x180020b48  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180020b4e  lea     rdx, [rsp+0E8h+var_48]
0x180020b56  mov     ecx, eax
0x180020b58  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180020b5d  lea     rdx, [rsp+0E8h+var_48]
0x180020b65  mov     ecx, eax
0x180020b67  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
