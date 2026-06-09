# Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(Microsoft::Windows::Autopilot::StorageMethod,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18001ca58`
- end: `0x18001cbe1`
- name: `?WriteStringToStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V67@@Z`
- size: `393`
- prototype: `__int64 __fastcall(int, __int64, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800193e4`
- `0x1800197f4`
- `0x180019ad4`
- `0x180019c14`
- `0x18001c894`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x1800166dc`
- `0x1800174f0`
- `0x18001ca58`
- `0x18002588c`
- `0x18002661c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001caef`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001caef`

## string_xrefs

- `0x18001cb02`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001cb5f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(
        int a1,
        __int64 a2,
        const unsigned __int16 *a3)
{
  const WCHAR *v4; // r8
  unsigned int v5; // ebx
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  DWORD cbData; // ecx
  const unsigned __int16 *v9; // rax
  unsigned int v10; // eax
  bool v11; // cc
  int StateSeparationAwareExpandedFilePath; // eax
  __int64 v13; // rdx
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // rcx
  int lpData; // [rsp+20h] [rbp-48h]
  unsigned int lpDataa; // [rsp+20h] [rbp-48h]
  unsigned __int16 *v19[2]; // [rsp+30h] [rbp-38h] BYREF
  __m128i si128; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = (const WCHAR *)a2;
  if ( !a1 )
  {
    v11 = *(_QWORD *)(a2 + 24) <= 7u;
    *(_OWORD *)v19 = 0;
    LOWORD(v19[0]) = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    if ( !v11 )
      v4 = *(const WCHAR **)a2;
    StateSeparationAwareExpandedFilePath = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(
                                             v4,
                                             v19);
    v5 = StateSeparationAwareExpandedFilePath;
    if ( StateSeparationAwareExpandedFilePath >= 0 )
    {
      if ( *((_QWORD *)a3 + 3) <= 7u )
        v14 = a3;
      else
        v14 = *(const unsigned __int16 **)a3;
      v15 = (const unsigned __int16 *)v19;
      if ( si128.m128i_i64[1] > 7uLL )
        v15 = v19[0];
      StateSeparationAwareExpandedFilePath = Microsoft::Windows::Autopilot::AutoPilotStringFile::WriteToFile(v15, v14);
      v5 = StateSeparationAwareExpandedFilePath;
      if ( StateSeparationAwareExpandedFilePath >= 0 )
      {
        std::wstring::_Tidy_deallocate(v19);
        goto LABEL_29;
      }
      v13 = 486;
    }
    else
    {
      v13 = 484;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)StateSeparationAwareExpandedFilePath,
      lpData);
    std::wstring::_Tidy_deallocate(v19);
    goto LABEL_30;
  }
  if ( a1 == 1 )
  {
    if ( *((_QWORD *)a3 + 3) <= 7u )
      v6 = a3;
    else
      v6 = *(const unsigned __int16 **)a3;
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    cbData = 2 * v7 + 2;
    if ( *((_QWORD *)a3 + 3) <= 7u )
      v9 = a3;
    else
      v9 = *(const unsigned __int16 **)a3;
    if ( *(_QWORD *)(a2 + 24) > 7u )
      v4 = *(const WCHAR **)a2;
    v10 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Provisioning\\HardwareInfo", v4, 1u, v9, cbData);
    if ( v10 )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1DE,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
             (const char *)v10,
             lpDataa);
      goto LABEL_30;
    }
LABEL_29:
    v5 = 0;
    goto LABEL_30;
  }
  v5 = -2147418113;
LABEL_30:
  std::wstring::_Tidy_deallocate(a3);
  return v5;
}

```

## disassembly

```asm
0x18001ca58  mov     [rsp+arg_0], rbx
0x18001ca5d  mov     [rsp+arg_18], rsi
0x18001ca62  push    rdi
0x18001ca63  sub     rsp, 60h
0x18001ca67  mov     rax, cs:__security_cookie
0x18001ca6e  xor     rax, rsp
0x18001ca71  mov     [rsp+68h+var_18], rax
0x18001ca76  xor     esi, esi
0x18001ca78  mov     rdi, r8
0x18001ca7b  mov     r8, rdx
0x18001ca7e  test    ecx, ecx
0x18001ca80  jz      loc_18001CB1D
0x18001ca86  cmp     ecx, 1
0x18001ca89  jz      short loc_18001CA95
0x18001ca8b  mov     ebx, 8000FFFFh
0x18001ca90  jmp     loc_18001CBB8
0x18001ca95  cmp     qword ptr [rdi+18h], 7
0x18001ca9a  jbe     short loc_18001CAA1
0x18001ca9c  mov     rcx, [rdi]
0x18001ca9f  jmp     short loc_18001CAA4
0x18001caa1  mov     rcx, rdi
0x18001caa4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001caa8  inc     rax
0x18001caab  cmp     [rcx+rax*2], si
0x18001caaf  jnz     short loc_18001CAA8
0x18001cab1  cmp     qword ptr [rdi+18h], 7
0x18001cab6  lea     rcx, ds:2[rax*2]
0x18001cabe  jbe     short loc_18001CAC5
0x18001cac0  mov     rax, [rdi]
0x18001cac3  jmp     short loc_18001CAC8
0x18001cac5  mov     rax, rdi
0x18001cac8  cmp     qword ptr [rdx+18h], 7
0x18001cacd  jbe     short loc_18001CAD2
0x18001cacf  mov     r8, [rdx]; lpValueName
0x18001cad2  mov     [rsp+68h+cbData], ecx; cbData
0x18001cad6  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Provisioning\\Hard"...
0x18001cadd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cae4  mov     [rsp+68h+lpData], rax; unsigned int
0x18001cae9  mov     r9d, 1; dwType
0x18001caef  call    cs:__imp_RegSetKeyValueW
0x18001caf5  test    eax, eax
0x18001caf7  jz      loc_18001CBB6
0x18001cafd  mov     rcx, [rsp+68h]; this
0x18001cb02  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001cb09  mov     r9d, eax; char *
0x18001cb0c  mov     edx, 1DEh; void *
0x18001cb11  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001cb16  mov     ebx, eax
0x18001cb18  jmp     loc_18001CBB8
0x18001cb1d  cmp     qword ptr [rdx+18h], 7
0x18001cb22  xorps   xmm0, xmm0
0x18001cb25  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001cb2d  movups  xmmword ptr [rsp+68h+var_38], xmm0
0x18001cb32  mov     word ptr [rsp+68h+var_38], si
0x18001cb37  movdqu  [rsp+68h+var_28], xmm1
0x18001cb3d  jbe     short loc_18001CB42
0x18001cb3f  mov     r8, [rdx]
0x18001cb42  lea     rdx, [rsp+68h+var_38]
0x18001cb47  mov     rcx, r8
0x18001cb4a  call    ?GetStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x18001cb4f  mov     ebx, eax
0x18001cb51  test    eax, eax
0x18001cb53  jns     short loc_18001CB7A
0x18001cb55  mov     edx, 1E4h; void *
0x18001cb5a  mov     rcx, [rsp+68h]; this
0x18001cb5f  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001cb66  mov     r9d, eax; char *
0x18001cb69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cb6e  lea     rcx, [rsp+68h+var_38]
0x18001cb73  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cb78  jmp     short loc_18001CBB8
0x18001cb7a  cmp     qword ptr [rdi+18h], 7
0x18001cb7f  jbe     short loc_18001CB86
0x18001cb81  mov     rdx, [rdi]
0x18001cb84  jmp     short loc_18001CB89
0x18001cb86  mov     rdx, rdi; unsigned __int16 *
0x18001cb89  cmp     qword ptr [rsp+68h+var_28+8], 7
0x18001cb8f  lea     rcx, [rsp+68h+var_38]
0x18001cb94  cmova   rcx, [rsp+68h+var_38]; unsigned __int16 *
0x18001cb9a  call    ?WriteToFile@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBG0@Z; Microsoft::Windows::Autopilot::AutoPilotStringFile::WriteToFile(ushort const *,ushort const *)
0x18001cb9f  mov     ebx, eax
0x18001cba1  test    eax, eax
0x18001cba3  jns     short loc_18001CBAC
0x18001cba5  mov     edx, 1E6h
0x18001cbaa  jmp     short loc_18001CB5A
0x18001cbac  lea     rcx, [rsp+68h+var_38]
0x18001cbb1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cbb6  mov     ebx, esi
0x18001cbb8  mov     rcx, rdi
0x18001cbbb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cbc0  mov     eax, ebx
0x18001cbc2  mov     rcx, [rsp+68h+var_18]
0x18001cbc7  xor     rcx, rsp; StackCookie
0x18001cbca  call    __security_check_cookie
0x18001cbcf  lea     r11, [rsp+68h+var_8]
0x18001cbd4  mov     rbx, [r11+10h]
0x18001cbd8  mov     rsi, [r11+28h]
0x18001cbdc  mov     rsp, r11
0x18001cbdf  pop     rdi
0x18001cbe0  retn
```
