# SrSettings::CSrSettings::GetSetting(ushort const *,ushort const *,ushort const *,bool,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x18000a520`
- end: `0x18000a7c5`
- name: `?GetSetting@CSrSettings@SrSettings@@AEAAJPEBG00_NAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `677`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x18000a1c0`
- `0x18000a7d0`
- `0x18000a8c0`
- `0x18000c260`
- `0x18000c410`

## callees

- `0x180006c00`
- `0x18000a520`
- `0x180010a0c`
- `0x180011ac0`
- `0x180011c80`
- `0x180012d7c`
- `0x1800142d2`
- `0x180014310`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a5f5`
- `KERNEL32!GetLastError` at `0x18000a603`
- `KERNEL32!GetLastError` at `0x18000a64f`
- `KERNEL32!GetLastError` at `0x18000a671`
- `KERNEL32!GetLastError` at `0x18000a6c4`
- `KERNEL32!GetLastError` at `0x18000a701`
- `KERNEL32!GetLastError` at `0x18000a722`
- `KERNEL32!GetLastError` at `0x18000a5f5`
- `KERNEL32!GetLastError` at `0x18000a603`
- `KERNEL32!GetLastError` at `0x18000a64f`
- `KERNEL32!GetLastError` at `0x18000a671`
- `KERNEL32!GetLastError` at `0x18000a6c4`
- `KERNEL32!GetLastError` at `0x18000a701`
- `KERNEL32!GetLastError` at `0x18000a722`
- `KERNEL32!GetPrivateProfileStringW` at `0x18000a5e7`
- `KERNEL32!GetPrivateProfileStringW` at `0x18000a641`
- `KERNEL32!GetPrivateProfileStringW` at `0x18000a5e7`
- `KERNEL32!GetPrivateProfileStringW` at `0x18000a641`

## string_xrefs

- `0x18000a5ac`: `Test mode enabled. Check setting %s from test config file`
- `0x18000a60c`: `Failed to get setting %s from test config file. Error: %d`
- `0x18000a6e9`: `Setting %s found in test config file`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::GetSetting(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        const WCHAR *a4,
        char a5,
        __int64 a6)
{
  __int64 v10; // rbx
  __int64 v11; // r8
  DWORD LastError; // eax
  signed int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  DWORD nSize[2]; // [rsp+20h] [rbp-268h]
  DWORD nSizea[2]; // [rsp+20h] [rbp-268h]
  DWORD nSizeb[2]; // [rsp+20h] [rbp-268h]
  LPCWSTR lpFileName; // [rsp+28h] [rbp-260h]
  WCHAR ReturnedString[264]; // [rsp+30h] [rbp-258h] BYREF

  if ( !a2 || !a3 || !a4 )
    return 2147942487LL;
  memset_0(ReturnedString, 0, 0x208u);
  v10 = -1;
  if ( *(_BYTE *)(a1 + 3947) && (unsigned int)FileExists(*(_QWORD *)(a1 + 136)) )
  {
    SrSettings::CSrSettings::Trace(a1, 0, L"Test mode enabled. Check setting %s from test config file", a4);
    if ( GetPrivateProfileStringW(L"Recovery", a4, &Default, ReturnedString, 0x104u, *(LPCWSTR *)(a1 + 136))
      || !GetLastError() )
    {
      v11 = -1;
      do
        ++v11;
      while ( ReturnedString[v11] );
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                              a6,
                              ReturnedString) )
      {
        SrSettings::CSrSettings::Trace(a1, 0, L"Setting %s found in test config file", a4);
        return 0;
      }
      LastError = GetLastError();
      SrSettings::CSrSettings::Trace(a1, 1, L"Failed to assign test setting value to string. Error: %d", LastError);
    }
    else
    {
      nSize[0] = GetLastError();
      SrSettings::CSrSettings::Trace(
        a1,
        1,
        L"Failed to get setting %s from test config file. Error: %d",
        a4,
        *(_QWORD *)nSize);
    }
  }
  if ( !GetPrivateProfileStringW(a3, a4, &Default, ReturnedString, 0x104u, a2) && GetLastError() )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::GetImpl'::`2'::impl) )
    {
      LODWORD(lpFileName) = GetLastError();
      SrSettings::CSrSettings::Trace(
        a1,
        (_DWORD)lpFileName != 2 ? 2 : 0,
        L"Failed to get setting %s from %s. Error: %d",
        a4,
        a2,
        lpFileName);
    }
    else
    {
      nSizea[0] = GetLastError();
      SrSettings::CSrSettings::Trace(a1, 2, L"Failed to get setting %s. Error: %d", a4, *(_QWORD *)nSizea);
    }
    v14 = GetLastError();
    v15 = v14;
    if ( v14 > 0 )
      v15 = (unsigned __int16)v14 | 0x80070000;
    if ( !a5 )
      return v15;
    v16 = SrSettings::CSrSettings::CheckDefaultValue(a1, a4, a6);
    if ( v16 < 0 )
    {
      nSizeb[0] = v16;
      SrSettings::CSrSettings::Trace(
        a1,
        2,
        L"Failed to get default value for setting %s. Error: 0x%08x",
        a4,
        *(_QWORD *)nSizeb);
      return v15;
    }
    return 0;
  }
  do
    ++v10;
  while ( ReturnedString[v10] );
  return (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            a6,
                            ReturnedString) == 0
       ? 0x80070008
       : 0;
}

```

## disassembly

```asm
0x18000a520  push    rbx
0x18000a522  push    rbp
0x18000a523  push    rsi
0x18000a524  push    rdi
0x18000a525  push    r12
0x18000a527  push    r14
0x18000a529  push    r15
0x18000a52b  sub     rsp, 250h
0x18000a532  mov     rax, cs:__security_cookie
0x18000a539  xor     rax, rsp
0x18000a53c  mov     [rsp+288h+var_48], rax
0x18000a544  mov     r15, [rsp+288h+arg_28]
0x18000a54c  xor     r12d, r12d
0x18000a54f  mov     rsi, r9
0x18000a552  mov     r14, r8
0x18000a555  mov     rbp, rdx
0x18000a558  mov     rdi, rcx
0x18000a55b  test    rdx, rdx
0x18000a55e  jz      loc_18000A79E
0x18000a564  test    r8, r8
0x18000a567  jz      loc_18000A79E
0x18000a56d  test    r9, r9
0x18000a570  jz      loc_18000A79E
0x18000a576  xor     edx, edx; Val
0x18000a578  lea     rcx, [rsp+288h+ReturnedString]; void *
0x18000a57d  mov     r8d, 208h; Size
0x18000a583  call    memset_0
0x18000a588  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000a58c  cmp     [rdi+0F6Bh], r12b
0x18000a593  jz      loc_18000A622
0x18000a599  mov     rcx, [rdi+88h]
0x18000a5a0  call    FileExists
0x18000a5a5  test    eax, eax
0x18000a5a7  jz      short loc_18000A622
0x18000a5a9  mov     r9, rsi
0x18000a5ac  lea     r8, aTestModeEnable; "Test mode enabled. Check setting %s fro"...
0x18000a5b3  xor     edx, edx
0x18000a5b5  mov     rcx, rdi
0x18000a5b8  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000a5bd  mov     rax, [rdi+88h]
0x18000a5c4  lea     r9, [rsp+288h+ReturnedString]; lpReturnedString
0x18000a5c9  mov     [rsp+288h+lpFileName], rax; lpFileName
0x18000a5ce  lea     r8, Default; lpDefault
0x18000a5d5  mov     rdx, rsi; lpKeyName
0x18000a5d8  mov     [rsp+288h+nSize], 104h; nSize
0x18000a5e0  lea     rcx, aRecovery; "Recovery"
0x18000a5e7  call    cs:__imp_GetPrivateProfileStringW
0x18000a5ed  test    eax, eax
0x18000a5ef  jnz     loc_18000A6A1
0x18000a5f5  call    cs:__imp_GetLastError
0x18000a5fb  test    eax, eax
0x18000a5fd  jz      loc_18000A6A1
0x18000a603  call    cs:__imp_GetLastError
0x18000a609  mov     r9, rsi
0x18000a60c  lea     r8, aFailedToGetSet_0; "Failed to get setting %s from test conf"...
0x18000a613  lea     edx, [rbx+2]
0x18000a616  mov     [rsp+288h+nSize], eax
0x18000a61a  mov     rcx, rdi
0x18000a61d  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000a622  mov     [rsp+288h+lpFileName], rbp; lpFileName
0x18000a627  lea     r9, [rsp+288h+ReturnedString]; lpReturnedString
0x18000a62c  lea     r8, Default; lpDefault
0x18000a633  mov     [rsp+288h+nSize], 104h; nSize
0x18000a63b  mov     rdx, rsi; lpKeyName
0x18000a63e  mov     rcx, r14; lpAppName
0x18000a641  call    cs:__imp_GetPrivateProfileStringW
0x18000a647  test    eax, eax
0x18000a649  jnz     loc_18000A772
0x18000a64f  call    cs:__imp_GetLastError
0x18000a655  test    eax, eax
0x18000a657  jz      loc_18000A772
0x18000a65d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::GetImpl(void)'::`2'::impl
0x18000a664  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::__private_IsEnabled(void)
0x18000a669  test    al, al
0x18000a66b  jz      loc_18000A701
0x18000a671  call    cs:__imp_GetLastError
0x18000a677  mov     dword ptr [rsp+288h+lpFileName], eax
0x18000a67b  mov     r9, rsi
0x18000a67e  lea     r8, aFailedToGetSet_1; "Failed to get setting %s from %s. Error"...
0x18000a685  mov     qword ptr [rsp+288h+nSize], rbp
0x18000a68a  lea     ecx, [rax-2]
0x18000a68d  neg     ecx
0x18000a68f  mov     rcx, rdi
0x18000a692  sbb     edx, edx
0x18000a694  and     edx, 2
0x18000a697  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000a69c  jmp     loc_18000A722
0x18000a6a1  lea     rax, [rsp+288h+ReturnedString]
0x18000a6a6  mov     r8, rbx
0x18000a6a9  inc     r8
0x18000a6ac  cmp     [rax+r8*2], r12w
0x18000a6b1  jnz     short loc_18000A6A9
0x18000a6b3  lea     rdx, [rsp+288h+ReturnedString]
0x18000a6b8  mov     rcx, r15
0x18000a6bb  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000a6c0  test    al, al
0x18000a6c2  jnz     short loc_18000A6E6
0x18000a6c4  call    cs:__imp_GetLastError
0x18000a6ca  lea     r8, aFailedToAssign_0; "Failed to assign test setting value to "...
0x18000a6d1  mov     edx, 1
0x18000a6d6  mov     r9d, eax
0x18000a6d9  mov     rcx, rdi
0x18000a6dc  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000a6e1  jmp     loc_18000A622
0x18000a6e6  mov     r9, rsi
0x18000a6e9  lea     r8, aSettingSFoundI; "Setting %s found in test config file"
0x18000a6f0  xor     edx, edx
0x18000a6f2  mov     rcx, rdi
0x18000a6f5  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000a6fa  xor     eax, eax
0x18000a6fc  jmp     loc_18000A7A3
0x18000a701  call    cs:__imp_GetLastError
0x18000a707  mov     r9, rsi
0x18000a70a  lea     r8, aFailedToGetSet; "Failed to get setting %s. Error: %d"
0x18000a711  mov     edx, 2
0x18000a716  mov     [rsp+288h+nSize], eax
0x18000a71a  mov     rcx, rdi
0x18000a71d  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000a722  call    cs:__imp_GetLastError
0x18000a728  mov     ebx, eax
0x18000a72a  test    eax, eax
0x18000a72c  jle     short loc_18000A737
0x18000a72e  movzx   ebx, ax
0x18000a731  or      ebx, 80070000h
0x18000a737  cmp     [rsp+288h+arg_20], r12b
0x18000a73f  jz      short loc_18000A76E
0x18000a741  mov     r8, r15
0x18000a744  mov     rdx, rsi
0x18000a747  mov     rcx, rdi
0x18000a74a  call    ?CheckDefaultValue@CSrSettings@SrSettings@@AEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SrSettings::CSrSettings::CheckDefaultValue(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18000a74f  test    eax, eax
0x18000a751  jns     short loc_18000A6FA
0x18000a753  mov     r9, rsi
0x18000a756  mov     [rsp+288h+nSize], eax
0x18000a75a  lea     r8, aFailedToGetDef; "Failed to get default value for setting"...
0x18000a761  mov     edx, 2
0x18000a766  mov     rcx, rdi
0x18000a769  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000a76e  mov     eax, ebx
0x18000a770  jmp     short loc_18000A7A3
0x18000a772  lea     rax, [rsp+288h+ReturnedString]
0x18000a777  inc     rbx
0x18000a77a  cmp     [rax+rbx*2], r12w
0x18000a77f  jnz     short loc_18000A777
0x18000a781  mov     r8, rbx
0x18000a784  lea     rdx, [rsp+288h+ReturnedString]
0x18000a789  mov     rcx, r15
0x18000a78c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000a791  neg     al
0x18000a793  sbb     eax, eax
0x18000a795  not     eax
0x18000a797  and     eax, 80070008h
0x18000a79c  jmp     short loc_18000A7A3
0x18000a79e  mov     eax, 80070057h
0x18000a7a3  mov     rcx, [rsp+288h+var_48]
0x18000a7ab  xor     rcx, rsp; StackCookie
0x18000a7ae  call    __security_check_cookie
0x18000a7b3  add     rsp, 250h
0x18000a7ba  pop     r15
0x18000a7bc  pop     r14
0x18000a7be  pop     r12
0x18000a7c0  pop     rdi
0x18000a7c1  pop     rsi
0x18000a7c2  pop     rbp
0x18000a7c3  pop     rbx
0x18000a7c4  retn
```
