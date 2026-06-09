# Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(Microsoft::Windows::Autopilot::StorageMethod,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18001d1c0`
- end: `0x18001d350`
- name: `?WriteStringToStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V67@@Z`
- size: `400`
- prototype: `__int64 __fastcall(int, __int64, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800199e4`
- `0x180019e18`
- `0x18001a0f8`
- `0x18001a238`
- `0x18001cff4`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180016b80`
- `0x180017a20`
- `0x18001d1c0`
- `0x18002672c`
- `0x1800275ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001d257`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001d257`

## string_xrefs

- `0x18001d270`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001d2cd`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

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
0x18001d1c0  mov     [rsp+arg_0], rbx
0x18001d1c5  mov     [rsp+arg_18], rsi
0x18001d1ca  push    rdi
0x18001d1cb  sub     rsp, 60h
0x18001d1cf  mov     rax, cs:__security_cookie
0x18001d1d6  xor     rax, rsp
0x18001d1d9  mov     [rsp+68h+var_18], rax
0x18001d1de  xor     esi, esi
0x18001d1e0  mov     rdi, r8
0x18001d1e3  mov     r8, rdx
0x18001d1e6  test    ecx, ecx
0x18001d1e8  jz      loc_18001D28B
0x18001d1ee  cmp     ecx, 1
0x18001d1f1  jz      short loc_18001D1FD
0x18001d1f3  mov     ebx, 8000FFFFh
0x18001d1f8  jmp     loc_18001D326
0x18001d1fd  cmp     qword ptr [rdi+18h], 7
0x18001d202  jbe     short loc_18001D209
0x18001d204  mov     rcx, [rdi]
0x18001d207  jmp     short loc_18001D20C
0x18001d209  mov     rcx, rdi
0x18001d20c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d210  inc     rax
0x18001d213  cmp     [rcx+rax*2], si
0x18001d217  jnz     short loc_18001D210
0x18001d219  cmp     qword ptr [rdi+18h], 7
0x18001d21e  lea     rcx, ds:2[rax*2]
0x18001d226  jbe     short loc_18001D22D
0x18001d228  mov     rax, [rdi]
0x18001d22b  jmp     short loc_18001D230
0x18001d22d  mov     rax, rdi
0x18001d230  cmp     qword ptr [rdx+18h], 7
0x18001d235  jbe     short loc_18001D23A
0x18001d237  mov     r8, [rdx]; lpValueName
0x18001d23a  mov     [rsp+68h+cbData], ecx; cbData
0x18001d23e  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Provisioning\\Hard"...
0x18001d245  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d24c  mov     [rsp+68h+lpData], rax; unsigned int
0x18001d251  mov     r9d, 1; dwType
0x18001d257  call    cs:__imp_RegSetKeyValueW
0x18001d25e  nop     dword ptr [rax+rax+00h]
0x18001d263  test    eax, eax
0x18001d265  jz      loc_18001D324
0x18001d26b  mov     rcx, [rsp+68h]; this
0x18001d270  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001d277  mov     r9d, eax; char *
0x18001d27a  mov     edx, 1DEh; void *
0x18001d27f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001d284  mov     ebx, eax
0x18001d286  jmp     loc_18001D326
0x18001d28b  cmp     qword ptr [rdx+18h], 7
0x18001d290  xorps   xmm0, xmm0
0x18001d293  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001d29b  movups  xmmword ptr [rsp+68h+var_38], xmm0
0x18001d2a0  mov     word ptr [rsp+68h+var_38], si
0x18001d2a5  movdqu  [rsp+68h+var_28], xmm1
0x18001d2ab  jbe     short loc_18001D2B0
0x18001d2ad  mov     r8, [rdx]
0x18001d2b0  lea     rdx, [rsp+68h+var_38]
0x18001d2b5  mov     rcx, r8
0x18001d2b8  call    ?GetStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x18001d2bd  mov     ebx, eax
0x18001d2bf  test    eax, eax
0x18001d2c1  jns     short loc_18001D2E8
0x18001d2c3  mov     edx, 1E4h; void *
0x18001d2c8  mov     rcx, [rsp+68h]; this
0x18001d2cd  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001d2d4  mov     r9d, eax; char *
0x18001d2d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d2dc  lea     rcx, [rsp+68h+var_38]
0x18001d2e1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d2e6  jmp     short loc_18001D326
0x18001d2e8  cmp     qword ptr [rdi+18h], 7
0x18001d2ed  jbe     short loc_18001D2F4
0x18001d2ef  mov     rdx, [rdi]
0x18001d2f2  jmp     short loc_18001D2F7
0x18001d2f4  mov     rdx, rdi; unsigned __int16 *
0x18001d2f7  cmp     qword ptr [rsp+68h+var_28+8], 7
0x18001d2fd  lea     rcx, [rsp+68h+var_38]
0x18001d302  cmova   rcx, [rsp+68h+var_38]; unsigned __int16 *
0x18001d308  call    ?WriteToFile@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBG0@Z; Microsoft::Windows::Autopilot::AutoPilotStringFile::WriteToFile(ushort const *,ushort const *)
0x18001d30d  mov     ebx, eax
0x18001d30f  test    eax, eax
0x18001d311  jns     short loc_18001D31A
0x18001d313  mov     edx, 1E6h
0x18001d318  jmp     short loc_18001D2C8
0x18001d31a  lea     rcx, [rsp+68h+var_38]
0x18001d31f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d324  mov     ebx, esi
0x18001d326  mov     rcx, rdi
0x18001d329  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d32e  mov     eax, ebx
0x18001d330  mov     rcx, [rsp+68h+var_18]
0x18001d335  xor     rcx, rsp; StackCookie
0x18001d338  call    __security_check_cookie
0x18001d33d  lea     r11, [rsp+68h+var_8]
0x18001d342  mov     rbx, [r11+10h]
0x18001d346  mov     rsi, [r11+28h]
0x18001d34a  mov     rsp, r11
0x18001d34d  pop     rdi
0x18001d34e  retn
```
