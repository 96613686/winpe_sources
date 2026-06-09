# Microsoft::Windows::Autopilot::HardwareInfo::ReadStringFromStorage(Microsoft::Windows::Autopilot::StorageMethod,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001c958`
- end: `0x18001cd00`
- name: `?ReadStringFromStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z`
- size: `936`
- prototype: `__int64 __fastcall(int, const WCHAR *, __int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019e18`
- `0x18001a238`
- `0x18001c190`

## callees

- `0x1800045d0`
- `0x1800096e0`
- `0x180010764`
- `0x180013de4`
- `0x180016b80`
- `0x180017a20`
- `0x180017b2c`
- `0x18001982c`
- `0x18001c958`
- `0x18001d4e4`
- `0x180026358`
- `0x1800275ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ca32`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001caf3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ca32`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001caf3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c9e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c9e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ca77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cb2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ca77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cb2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cbf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cbf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cbdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cc63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cbdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cc63`

## string_xrefs

- `0x18001ca56`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001cb0a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001cb79`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001cbc1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  __int128 *v15; // rcx
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
      v15 = &v34;
      if ( si128.m128i_i64[1] > 7uLL )
        v15 = (__int128 *)v34;
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
        std::wstring::_Construct<1,unsigned short const *>(&v36, StringRawBuffer);
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
0x18001c958  mov     [rsp-8+arg_0], rbx
0x18001c95d  mov     [rsp-8+arg_18], rsi
0x18001c962  push    rbp
0x18001c963  push    rdi
0x18001c964  push    r14
0x18001c966  lea     rbp, [rsp-47h]
0x18001c96b  sub     rsp, 0D0h
0x18001c972  mov     rax, cs:__security_cookie
0x18001c979  xor     rax, rsp
0x18001c97c  mov     [rbp+57h+var_20], rax
0x18001c980  mov     rsi, r8
0x18001c983  mov     rdi, rdx
0x18001c986  xorps   xmm0, xmm0
0x18001c989  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18001c98d  xor     r14d, r14d
0x18001c990  mov     qword ptr [rbp+57h+var_70], r14
0x18001c994  mov     qword ptr [rbp+57h+var_70+8], 7
0x18001c99c  mov     word ptr [rbp+57h+Src], r14w
0x18001c9a1  test    ecx, ecx
0x18001c9a3  jz      loc_18001CB40
0x18001c9a9  cmp     ecx, 1
0x18001c9ac  jz      short loc_18001C9B8
0x18001c9ae  mov     ebx, 8000FFFFh
0x18001c9b3  jmp     loc_18001CCD0
0x18001c9b8  mov     [rbp+57h+var_A0], r14d
0x18001c9bc  mov     [rbp+57h+hkey], r14
0x18001c9c0  lea     rax, [rbp+57h+hkey]
0x18001c9c4  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18001c9c9  mov     r9d, 20019h; samDesired
0x18001c9cf  xor     r8d, r8d; ulOptions
0x18001c9d2  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Provisioning\\Hard"...
0x18001c9d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c9e0  call    cs:__imp_RegOpenKeyExW
0x18001c9e7  nop     dword ptr [rax+rax+00h]
0x18001c9ec  mov     ebx, eax
0x18001c9ee  test    eax, eax
0x18001c9f0  jle     short loc_18001C9FB
0x18001c9f2  movzx   ebx, ax
0x18001c9f5  or      ebx, 80070000h
0x18001c9fb  test    ebx, ebx
0x18001c9fd  jns     short loc_18001CA06
0x18001c9ff  mov     edx, 1A1h
0x18001ca04  jmp     short loc_18001CA56
0x18001ca06  cmp     qword ptr [rdi+18h], 7
0x18001ca0b  jbe     short loc_18001CA12
0x18001ca0d  mov     r8, [rdi]
0x18001ca10  jmp     short loc_18001CA15
0x18001ca12  mov     r8, rdi; lpValue
0x18001ca15  lea     rax, [rbp+57h+var_A0]
0x18001ca19  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18001ca1e  mov     [rsp+0E0h+pvData], r14; pvData
0x18001ca23  mov     [rsp+0E0h+phkResult], r14; int
0x18001ca28  xor     edx, edx; lpSubKey
0x18001ca2a  lea     r9d, [rdx+2]; dwFlags
0x18001ca2e  mov     rcx, [rbp+57h+hkey]; hkey
0x18001ca32  call    cs:__imp_RegGetValueW
0x18001ca39  nop     dword ptr [rax+rax+00h]
0x18001ca3e  mov     ebx, eax
0x18001ca40  test    eax, eax
0x18001ca42  jle     short loc_18001CA4D
0x18001ca44  movzx   ebx, ax
0x18001ca47  or      ebx, 80070000h
0x18001ca4d  test    ebx, ebx
0x18001ca4f  jns     short loc_18001CA88
0x18001ca51  mov     edx, 1AAh; void *
0x18001ca56  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ca5d  mov     r9d, ebx; char *
0x18001ca60  mov     rcx, [rbp+5Fh]; this
0x18001ca64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ca69  nop
0x18001ca6a  mov     rcx, [rbp+57h+hkey]; hKey
0x18001ca6e  test    rcx, rcx
0x18001ca71  jz      loc_18001CCD0
0x18001ca77  call    cs:__imp_RegCloseKey
0x18001ca7e  nop     dword ptr [rax+rax+00h]
0x18001ca83  jmp     loc_18001CCD0
0x18001ca88  mov     edx, [rbp+57h+var_A0]
0x18001ca8b  shr     rdx, 1
0x18001ca8e  lea     rcx, [rbp+57h+Src]; Src
0x18001ca92  cmp     rdx, qword ptr [rbp+57h+var_70]
0x18001ca96  ja      short loc_18001CAAD
0x18001ca98  mov     qword ptr [rbp+57h+var_70], rdx
0x18001ca9c  cmp     qword ptr [rbp+57h+var_70+8], 7
0x18001caa1  cmova   rcx, [rbp+57h+Src]
0x18001caa6  mov     [rcx+rdx*2], r14w
0x18001caab  jmp     short loc_18001CAB9
0x18001caad  xor     r8d, r8d
0x18001cab0  sub     rdx, qword ptr [rbp+57h+var_70]
0x18001cab4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x18001cab9  lea     rax, [rbp+57h+Src]
0x18001cabd  cmp     qword ptr [rbp+57h+var_70+8], 7
0x18001cac2  cmova   rax, [rbp+57h+Src]
0x18001cac7  cmp     qword ptr [rdi+18h], 7
0x18001cacc  jbe     short loc_18001CAD1
0x18001cace  mov     rdi, [rdi]
0x18001cad1  lea     rcx, [rbp+57h+var_A0]
0x18001cad5  mov     [rsp+0E0h+pcbData], rcx; pcbData
0x18001cada  mov     [rsp+0E0h+pvData], rax; pvData
0x18001cadf  mov     [rsp+0E0h+phkResult], r14; unsigned int
0x18001cae4  mov     r9d, 2; dwFlags
0x18001caea  mov     r8, rdi; lpValue
0x18001caed  xor     edx, edx; lpSubKey
0x18001caef  mov     rcx, [rbp+57h+hkey]; hkey
0x18001caf3  call    cs:__imp_RegGetValueW
0x18001cafa  nop     dword ptr [rax+rax+00h]
0x18001caff  test    eax, eax
0x18001cb01  jz      short loc_18001CB22
0x18001cb03  mov     rcx, [rbp+5Fh]; this
0x18001cb07  mov     r9d, eax; char *
0x18001cb0a  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001cb11  mov     edx, 1B4h; void *
0x18001cb16  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001cb1b  mov     ebx, eax
0x18001cb1d  jmp     loc_18001CA6A
0x18001cb22  mov     rcx, [rbp+57h+hkey]; hKey
0x18001cb26  test    rcx, rcx
0x18001cb29  jz      loc_18001CC79
0x18001cb2f  call    cs:__imp_RegCloseKey
0x18001cb36  nop     dword ptr [rax+rax+00h]
0x18001cb3b  jmp     loc_18001CC79
0x18001cb40  movups  [rbp+57h+var_60], xmm0
0x18001cb44  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001cb4c  movdqu  [rbp+57h+var_50], xmm1
0x18001cb51  mov     word ptr [rbp+57h+var_60], r14w
0x18001cb56  cmp     qword ptr [rdx+18h], 7
0x18001cb5b  jbe     short loc_18001CB60
0x18001cb5d  mov     rdi, [rdx]
0x18001cb60  lea     rdx, [rbp+57h+var_60]
0x18001cb64  mov     rcx, rdi
0x18001cb67  call    ?GetStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x18001cb6c  mov     ebx, eax
0x18001cb6e  test    eax, eax
0x18001cb70  jns     short loc_18001CB99
0x18001cb72  mov     rcx, [rbp+5Fh]; this
0x18001cb76  mov     r9d, eax; char *
0x18001cb79  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001cb80  mov     edx, 1BAh; void *
0x18001cb85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cb8a  nop
0x18001cb8b  lea     rcx, [rbp+57h+var_60]
0x18001cb8f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cb94  jmp     loc_18001CCD0
0x18001cb99  mov     [rbp+57h+string], r14
0x18001cb9d  lea     rcx, [rbp+57h+var_60]
0x18001cba1  cmp     qword ptr [rbp+57h+var_50+8], 7
0x18001cba6  cmova   rcx, qword ptr [rbp+57h+var_60]
0x18001cbab  lea     rdx, [rbp+57h+string]
0x18001cbaf  call    ?ReadFromFile@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x18001cbb4  mov     ebx, eax
0x18001cbb6  test    eax, eax
0x18001cbb8  jns     short loc_18001CBEA
0x18001cbba  mov     rcx, [rbp+5Fh]; this
0x18001cbbe  mov     r9d, eax; char *
0x18001cbc1  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001cbc8  mov     edx, 1BDh; void *
0x18001cbcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cbd2  nop
0x18001cbd3  mov     rcx, [rbp+57h+string]; string
0x18001cbd7  test    rcx, rcx
0x18001cbda  jz      short loc_18001CB8B
0x18001cbdc  call    cs:__imp_WindowsDeleteString
0x18001cbe3  nop     dword ptr [rax+rax+00h]
0x18001cbe8  jmp     short loc_18001CB8B
0x18001cbea  xor     edx, edx; length
0x18001cbec  mov     rcx, [rbp+57h+string]; string
0x18001cbf0  call    cs:__imp_WindowsGetStringRawBuffer
0x18001cbf7  nop     dword ptr [rax+rax+00h]
0x18001cbfc  xorps   xmm0, xmm0
0x18001cbff  movups  [rbp+57h+var_40], xmm0
0x18001cc03  xorps   xmm1, xmm1
0x18001cc06  movdqu  [rbp+57h+var_30], xmm1
0x18001cc0b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001cc0f  inc     r8
0x18001cc12  cmp     [rax+r8*2], r14w
0x18001cc17  jnz     short loc_18001CC0F
0x18001cc19  mov     rdx, rax
0x18001cc1c  lea     rcx, [rbp+57h+var_40]
0x18001cc20  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001cc25  lea     rcx, [rbp+57h+Src]
0x18001cc29  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cc2e  movups  xmm0, [rbp+57h+var_40]
0x18001cc32  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18001cc36  movups  xmm1, [rbp+57h+var_30]
0x18001cc3a  movups  [rbp+57h+var_70], xmm1
0x18001cc3e  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001cc46  movdqu  [rbp+57h+var_30], xmm0
0x18001cc4b  mov     word ptr [rbp+57h+var_40], r14w
0x18001cc50  lea     rcx, [rbp+57h+var_40]
0x18001cc54  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cc59  nop
0x18001cc5a  mov     rcx, [rbp+57h+string]; string
0x18001cc5e  test    rcx, rcx
0x18001cc61  jz      short loc_18001CC70
0x18001cc63  call    cs:__imp_WindowsDeleteString
0x18001cc6a  nop     dword ptr [rax+rax+00h]
0x18001cc6f  nop
0x18001cc70  lea     rcx, [rbp+57h+var_60]
0x18001cc74  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cc79  lea     rax, [rbp+57h+Src]
0x18001cc7d  mov     rcx, [rbp+57h+Src]
0x18001cc81  cmp     qword ptr [rbp+57h+var_70+8], 7
0x18001cc86  cmova   rax, rcx
0x18001cc8a  mov     rdx, qword ptr [rbp+57h+var_70]
0x18001cc8e  lea     rbx, [rax+rdx*2]
0x18001cc92  ja      short loc_18001CCA2
0x18001cc94  lea     rax, [rbp+57h+Src]
0x18001cc98  lea     rdx, [rax+rdx*2]
0x18001cc9c  lea     rcx, [rbp+57h+Src]
0x18001cca0  jmp     short loc_18001CCA6
0x18001cca2  lea     rdx, [rcx+rdx*2]
0x18001cca6  xor     r8d, r8d
0x18001cca9  call    __std_find_trivial_2
0x18001ccae  mov     r9, rbx
0x18001ccb1  mov     r8, rax
0x18001ccb4  lea     rdx, [rbp+57h+var_88]
0x18001ccb8  lea     rcx, [rbp+57h+Src]
0x18001ccbc  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@0@Z; std::wstring::erase(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x18001ccc1  lea     rdx, [rbp+57h+Src]
0x18001ccc5  mov     rcx, rsi
0x18001ccc8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001cccd  mov     ebx, r14d
0x18001ccd0  lea     rcx, [rbp+57h+Src]
0x18001ccd4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ccd9  mov     eax, ebx
0x18001ccdb  mov     rcx, [rbp+57h+var_20]
0x18001ccdf  xor     rcx, rsp; StackCookie
0x18001cce2  call    __security_check_cookie
0x18001cce7  lea     r11, [rsp+0E0h+var_10]
0x18001ccef  mov     rbx, [r11+20h]
0x18001ccf3  mov     rsi, [r11+38h]
0x18001ccf7  mov     rsp, r11
0x18001ccfa  pop     r14
0x18001ccfc  pop     rdi
0x18001ccfd  pop     rbp
0x18001ccfe  retn
```
