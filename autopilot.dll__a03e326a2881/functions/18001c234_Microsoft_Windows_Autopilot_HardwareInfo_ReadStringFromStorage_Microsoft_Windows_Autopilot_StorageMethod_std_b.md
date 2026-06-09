# Microsoft::Windows::Autopilot::HardwareInfo::ReadStringFromStorage(Microsoft::Windows::Autopilot::StorageMethod,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001c234`
- end: `0x18001c5ab`
- name: `?ReadStringFromStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z`
- size: `887`
- prototype: `__int64 __fastcall(int, const WCHAR *, __int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800197f4`
- `0x180019c14`
- `0x18001ba54`

## callees

- `0x1800045b0`
- `0x180009750`
- `0x1800105f4`
- `0x180013a40`
- `0x1800166dc`
- `0x1800174f0`
- `0x1800175f4`
- `0x180019230`
- `0x18001c234`
- `0x18001cd64`
- `0x18002553c`
- `0x18002661c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c308`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c3bd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c308`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c3bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c2bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c2bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c347`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c3f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c347`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c3f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c4a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c4a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c49a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c515`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c49a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c515`

## string_xrefs

- `0x18001c326`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001c3ce`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001c437`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001c47f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::ReadStringFromStorage(
        int a1,
        const WCHAR *a2,
        __int64 a3)
{
  const WCHAR *v4; // rdi
  signed int v5; // ebx
  LSTATUS v6; // eax
  __int64 v7; // rdx
  const WCHAR *v8; // r8
  LSTATUS ValueW; // eax
  unsigned __int64 v10; // rdx
  PVOID *v11; // rcx
  PVOID *pvData; // rax
  unsigned int v13; // eax
  int StateSeparationAwareExpandedFilePath; // eax
  const WCHAR *v15; // rcx
  int v16; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v18; // r8
  PVOID *v19; // rax
  PVOID *v20; // rcx
  char *v21; // rbx
  char *v22; // rdx
  __int64 trivial_2; // rax
  int phkResult; // [rsp+20h] [rbp-69h]
  int phkResulta; // [rsp+20h] [rbp-69h]
  unsigned int phkResultb; // [rsp+20h] [rbp-69h]
  DWORD pcbData; // [rsp+40h] [rbp-49h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-41h] BYREF
  HSTRING string; // [rsp+50h] [rbp-39h] BYREF
  char v31[8]; // [rsp+58h] [rbp-31h] BYREF
  PVOID Src[2]; // [rsp+60h] [rbp-29h] BYREF
  __m128i v33; // [rsp+70h] [rbp-19h]
  __int128 v34; // [rsp+80h] [rbp-9h] BYREF
  __m128i si128; // [rsp+90h] [rbp+7h]
  __int128 v36; // [rsp+A0h] [rbp+17h] BYREF
  __m128i v37; // [rsp+B0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v4 = a2;
  *(_OWORD *)Src = 0;
  v33.m128i_i64[0] = 0;
  v33.m128i_i64[1] = 7;
  LOWORD(Src[0]) = 0;
  if ( !a1 )
  {
    v34 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v34) = 0;
    if ( *((_QWORD *)a2 + 3) > 7u )
      v4 = *(const WCHAR **)a2;
    StateSeparationAwareExpandedFilePath = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(
                                             v4,
                                             &v34);
    v5 = StateSeparationAwareExpandedFilePath;
    if ( StateSeparationAwareExpandedFilePath >= 0 )
    {
      string = 0;
      v15 = (const WCHAR *)&v34;
      if ( si128.m128i_i64[1] > 7uLL )
        v15 = (const WCHAR *)v34;
      v16 = Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(v15, &string);
      v5 = v16;
      if ( v16 >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v36 = 0;
        v37 = 0;
        v18 = -1;
        do
          ++v18;
        while ( StringRawBuffer[v18] );
        std::wstring::_Construct<1,unsigned short const *>(&v36, StringRawBuffer, v18);
        std::wstring::_Tidy_deallocate(Src);
        *(_OWORD *)Src = v36;
        v33 = v37;
        v37 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v36) = 0;
        std::wstring::_Tidy_deallocate(&v36);
        if ( string )
          WindowsDeleteString(string);
        std::wstring::_Tidy_deallocate(&v34);
        goto LABEL_46;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BD,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)(unsigned int)v16,
        phkResult);
      if ( string )
        WindowsDeleteString(string);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BA,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)(unsigned int)StateSeparationAwareExpandedFilePath,
        phkResult);
    }
    std::wstring::_Tidy_deallocate(&v34);
    goto LABEL_52;
  }
  if ( a1 != 1 )
  {
    v5 = -2147418113;
    goto LABEL_52;
  }
  pcbData = 0;
  hkey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Provisioning\\HardwareInfo", 0, 0x20019u, &hkey);
  v5 = v6;
  if ( v6 > 0 )
    v5 = (unsigned __int16)v6 | 0x80070000;
  if ( v5 < 0 )
  {
    v7 = 417;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v5,
      phkResulta);
    goto LABEL_16;
  }
  if ( *((_QWORD *)v4 + 3) <= 7u )
    v8 = v4;
  else
    v8 = *(const WCHAR **)v4;
  ValueW = RegGetValueW(hkey, 0, v8, 2u, 0, 0, &pcbData);
  v5 = ValueW;
  if ( ValueW > 0 )
    v5 = (unsigned __int16)ValueW | 0x80070000;
  if ( v5 < 0 )
  {
    v7 = 426;
    goto LABEL_15;
  }
  v10 = (unsigned __int64)pcbData >> 1;
  v11 = Src;
  if ( v10 > v33.m128i_i64[0] )
  {
    std::wstring::append(Src);
  }
  else
  {
    v33.m128i_i64[0] = (unsigned __int64)pcbData >> 1;
    if ( v33.m128i_i64[1] > 7uLL )
      v11 = (PVOID *)Src[0];
    *((_WORD *)v11 + v10) = 0;
  }
  pvData = Src;
  if ( v33.m128i_i64[1] > 7uLL )
    pvData = (PVOID *)Src[0];
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(const WCHAR **)v4;
  v13 = RegGetValueW(hkey, 0, v4, 2u, 0, pvData, &pcbData);
  if ( v13 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1B4,
           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
           (const char *)v13,
           phkResultb);
LABEL_16:
    if ( hkey )
      RegCloseKey(hkey);
    goto LABEL_52;
  }
  if ( hkey )
    RegCloseKey(hkey);
LABEL_46:
  v19 = Src;
  v20 = (PVOID *)Src[0];
  if ( v33.m128i_i64[1] > 7uLL )
    v19 = (PVOID *)Src[0];
  v21 = (char *)v19 + 2 * v33.m128i_i64[0];
  if ( v33.m128i_i64[1] > 7uLL )
  {
    v22 = (char *)Src[0] + 2 * v33.m128i_i64[0];
  }
  else
  {
    v22 = (char *)Src + 2 * v33.m128i_i64[0];
    v20 = Src;
  }
  trivial_2 = _std_find_trivial_2(v20, v22, 0);
  std::wstring::erase(Src, v31, trivial_2, v21);
  std::wstring::operator=(a3, Src);
  v5 = 0;
LABEL_52:
  std::wstring::_Tidy_deallocate(Src);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001c234  mov     [rsp-8+arg_0], rbx
0x18001c239  mov     [rsp-8+arg_18], rsi
0x18001c23e  push    rbp
0x18001c23f  push    rdi
0x18001c240  push    r14
0x18001c242  lea     rbp, [rsp-47h]
0x18001c247  sub     rsp, 0D0h
0x18001c24e  mov     rax, cs:__security_cookie
0x18001c255  xor     rax, rsp
0x18001c258  mov     [rbp+57h+var_20], rax
0x18001c25c  mov     rsi, r8
0x18001c25f  mov     rdi, rdx
0x18001c262  xorps   xmm0, xmm0
0x18001c265  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18001c269  xor     r14d, r14d
0x18001c26c  mov     qword ptr [rbp+57h+var_70], r14
0x18001c270  mov     qword ptr [rbp+57h+var_70+8], 7
0x18001c278  mov     word ptr [rbp+57h+Src], r14w
0x18001c27d  test    ecx, ecx
0x18001c27f  jz      loc_18001C3FE
0x18001c285  cmp     ecx, 1
0x18001c288  jz      short loc_18001C294
0x18001c28a  mov     ebx, 8000FFFFh
0x18001c28f  jmp     loc_18001C57C
0x18001c294  mov     [rbp+57h+var_A0], r14d
0x18001c298  mov     [rbp+57h+hkey], r14
0x18001c29c  lea     rax, [rbp+57h+hkey]
0x18001c2a0  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18001c2a5  mov     r9d, 20019h; samDesired
0x18001c2ab  xor     r8d, r8d; ulOptions
0x18001c2ae  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Provisioning\\Hard"...
0x18001c2b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c2bc  call    cs:__imp_RegOpenKeyExW
0x18001c2c2  mov     ebx, eax
0x18001c2c4  test    eax, eax
0x18001c2c6  jle     short loc_18001C2D1
0x18001c2c8  movzx   ebx, ax
0x18001c2cb  or      ebx, 80070000h
0x18001c2d1  test    ebx, ebx
0x18001c2d3  jns     short loc_18001C2DC
0x18001c2d5  mov     edx, 1A1h
0x18001c2da  jmp     short loc_18001C326
0x18001c2dc  cmp     qword ptr [rdi+18h], 7
0x18001c2e1  jbe     short loc_18001C2E8
0x18001c2e3  mov     r8, [rdi]
0x18001c2e6  jmp     short loc_18001C2EB
0x18001c2e8  mov     r8, rdi; lpValue
0x18001c2eb  lea     rax, [rbp+57h+var_A0]
0x18001c2ef  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18001c2f4  mov     [rsp+0E0h+pvData], r14; pvData
0x18001c2f9  mov     [rsp+0E0h+phkResult], r14; int
0x18001c2fe  xor     edx, edx; lpSubKey
0x18001c300  lea     r9d, [rdx+2]; dwFlags
0x18001c304  mov     rcx, [rbp+57h+hkey]; hkey
0x18001c308  call    cs:__imp_RegGetValueW
0x18001c30e  mov     ebx, eax
0x18001c310  test    eax, eax
0x18001c312  jle     short loc_18001C31D
0x18001c314  movzx   ebx, ax
0x18001c317  or      ebx, 80070000h
0x18001c31d  test    ebx, ebx
0x18001c31f  jns     short loc_18001C352
0x18001c321  mov     edx, 1AAh; void *
0x18001c326  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001c32d  mov     r9d, ebx; char *
0x18001c330  mov     rcx, [rbp+5Fh]; this
0x18001c334  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c339  nop
0x18001c33a  mov     rcx, [rbp+57h+hkey]; hKey
0x18001c33e  test    rcx, rcx
0x18001c341  jz      loc_18001C57C
0x18001c347  call    cs:__imp_RegCloseKey
0x18001c34d  jmp     loc_18001C57C
0x18001c352  mov     edx, [rbp+57h+var_A0]
0x18001c355  shr     rdx, 1
0x18001c358  lea     rcx, [rbp+57h+Src]; Src
0x18001c35c  cmp     rdx, qword ptr [rbp+57h+var_70]
0x18001c360  ja      short loc_18001C377
0x18001c362  mov     qword ptr [rbp+57h+var_70], rdx
0x18001c366  cmp     qword ptr [rbp+57h+var_70+8], 7
0x18001c36b  cmova   rcx, [rbp+57h+Src]
0x18001c370  mov     [rcx+rdx*2], r14w
0x18001c375  jmp     short loc_18001C383
0x18001c377  xor     r8d, r8d
0x18001c37a  sub     rdx, qword ptr [rbp+57h+var_70]
0x18001c37e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x18001c383  lea     rax, [rbp+57h+Src]
0x18001c387  cmp     qword ptr [rbp+57h+var_70+8], 7
0x18001c38c  cmova   rax, [rbp+57h+Src]
0x18001c391  cmp     qword ptr [rdi+18h], 7
0x18001c396  jbe     short loc_18001C39B
0x18001c398  mov     rdi, [rdi]
0x18001c39b  lea     rcx, [rbp+57h+var_A0]
0x18001c39f  mov     [rsp+0E0h+pcbData], rcx; pcbData
0x18001c3a4  mov     [rsp+0E0h+pvData], rax; pvData
0x18001c3a9  mov     [rsp+0E0h+phkResult], r14; unsigned int
0x18001c3ae  mov     r9d, 2; dwFlags
0x18001c3b4  mov     r8, rdi; lpValue
0x18001c3b7  xor     edx, edx; lpSubKey
0x18001c3b9  mov     rcx, [rbp+57h+hkey]; hkey
0x18001c3bd  call    cs:__imp_RegGetValueW
0x18001c3c3  test    eax, eax
0x18001c3c5  jz      short loc_18001C3E6
0x18001c3c7  mov     rcx, [rbp+5Fh]; this
0x18001c3cb  mov     r9d, eax; char *
0x18001c3ce  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001c3d5  mov     edx, 1B4h; void *
0x18001c3da  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001c3df  mov     ebx, eax
0x18001c3e1  jmp     loc_18001C33A
0x18001c3e6  mov     rcx, [rbp+57h+hkey]; hKey
0x18001c3ea  test    rcx, rcx
0x18001c3ed  jz      loc_18001C525
0x18001c3f3  call    cs:__imp_RegCloseKey
0x18001c3f9  jmp     loc_18001C525
0x18001c3fe  movups  [rbp+57h+var_60], xmm0
0x18001c402  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001c40a  movdqu  [rbp+57h+var_50], xmm1
0x18001c40f  mov     word ptr [rbp+57h+var_60], r14w
0x18001c414  cmp     qword ptr [rdx+18h], 7
0x18001c419  jbe     short loc_18001C41E
0x18001c41b  mov     rdi, [rdx]
0x18001c41e  lea     rdx, [rbp+57h+var_60]
0x18001c422  mov     rcx, rdi
0x18001c425  call    ?GetStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x18001c42a  mov     ebx, eax
0x18001c42c  test    eax, eax
0x18001c42e  jns     short loc_18001C457
0x18001c430  mov     rcx, [rbp+5Fh]; this
0x18001c434  mov     r9d, eax; char *
0x18001c437  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001c43e  mov     edx, 1BAh; void *
0x18001c443  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c448  nop
0x18001c449  lea     rcx, [rbp+57h+var_60]
0x18001c44d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c452  jmp     loc_18001C57C
0x18001c457  mov     [rbp+57h+string], r14
0x18001c45b  lea     rcx, [rbp+57h+var_60]
0x18001c45f  cmp     qword ptr [rbp+57h+var_50+8], 7
0x18001c464  cmova   rcx, qword ptr [rbp+57h+var_60]
0x18001c469  lea     rdx, [rbp+57h+string]
0x18001c46d  call    ?ReadFromFile@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x18001c472  mov     ebx, eax
0x18001c474  test    eax, eax
0x18001c476  jns     short loc_18001C4A2
0x18001c478  mov     rcx, [rbp+5Fh]; this
0x18001c47c  mov     r9d, eax; char *
0x18001c47f  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001c486  mov     edx, 1BDh; void *
0x18001c48b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c490  nop
0x18001c491  mov     rcx, [rbp+57h+string]; string
0x18001c495  test    rcx, rcx
0x18001c498  jz      short loc_18001C449
0x18001c49a  call    cs:__imp_WindowsDeleteString
0x18001c4a0  jmp     short loc_18001C449
0x18001c4a2  xor     edx, edx; length
0x18001c4a4  mov     rcx, [rbp+57h+string]; string
0x18001c4a8  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c4ae  xorps   xmm0, xmm0
0x18001c4b1  movups  [rbp+57h+var_40], xmm0
0x18001c4b5  xorps   xmm1, xmm1
0x18001c4b8  movdqu  [rbp+57h+var_30], xmm1
0x18001c4bd  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c4c1  inc     r8
0x18001c4c4  cmp     [rax+r8*2], r14w
0x18001c4c9  jnz     short loc_18001C4C1
0x18001c4cb  mov     rdx, rax
0x18001c4ce  lea     rcx, [rbp+57h+var_40]
0x18001c4d2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001c4d7  lea     rcx, [rbp+57h+Src]
0x18001c4db  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c4e0  movups  xmm0, [rbp+57h+var_40]
0x18001c4e4  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18001c4e8  movups  xmm1, [rbp+57h+var_30]
0x18001c4ec  movups  [rbp+57h+var_70], xmm1
0x18001c4f0  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001c4f8  movdqu  [rbp+57h+var_30], xmm0
0x18001c4fd  mov     word ptr [rbp+57h+var_40], r14w
0x18001c502  lea     rcx, [rbp+57h+var_40]
0x18001c506  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c50b  nop
0x18001c50c  mov     rcx, [rbp+57h+string]; string
0x18001c510  test    rcx, rcx
0x18001c513  jz      short loc_18001C51C
0x18001c515  call    cs:__imp_WindowsDeleteString
0x18001c51b  nop
0x18001c51c  lea     rcx, [rbp+57h+var_60]
0x18001c520  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c525  lea     rax, [rbp+57h+Src]
0x18001c529  mov     rcx, [rbp+57h+Src]
0x18001c52d  cmp     qword ptr [rbp+57h+var_70+8], 7
0x18001c532  cmova   rax, rcx
0x18001c536  mov     rdx, qword ptr [rbp+57h+var_70]
0x18001c53a  lea     rbx, [rax+rdx*2]
0x18001c53e  ja      short loc_18001C54E
0x18001c540  lea     rax, [rbp+57h+Src]
0x18001c544  lea     rdx, [rax+rdx*2]
0x18001c548  lea     rcx, [rbp+57h+Src]
0x18001c54c  jmp     short loc_18001C552
0x18001c54e  lea     rdx, [rcx+rdx*2]
0x18001c552  xor     r8d, r8d
0x18001c555  call    __std_find_trivial_2
0x18001c55a  mov     r9, rbx
0x18001c55d  mov     r8, rax
0x18001c560  lea     rdx, [rbp+57h+var_88]
0x18001c564  lea     rcx, [rbp+57h+Src]
0x18001c568  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@0@Z; std::wstring::erase(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x18001c56d  lea     rdx, [rbp+57h+Src]
0x18001c571  mov     rcx, rsi
0x18001c574  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001c579  mov     ebx, r14d
0x18001c57c  lea     rcx, [rbp+57h+Src]
0x18001c580  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c585  mov     eax, ebx
0x18001c587  mov     rcx, [rbp+57h+var_20]
0x18001c58b  xor     rcx, rsp; StackCookie
0x18001c58e  call    __security_check_cookie
0x18001c593  lea     r11, [rsp+0E0h+var_10]
0x18001c59b  mov     rbx, [r11+20h]
0x18001c59f  mov     rsi, [r11+38h]
0x18001c5a3  mov     rsp, r11
0x18001c5a6  pop     r14
0x18001c5a8  pop     rdi
0x18001c5a9  pop     rbp
0x18001c5aa  retn
```
