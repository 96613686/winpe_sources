# Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize(SERVICE_STATUS_HANDLE__ *)

- ea: `0x180027724`
- end: `0x1800278fb`
- name: `?Initialize@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@QEAAJPEAUSERVICE_STATUS_HANDLE__@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation *__hidden this, struct SERVICE_STATUS_HANDLE__ *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800275ac`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013618`
- `0x180013de4`
- `0x180017a20`
- `0x18001982c`
- `0x180027018`
- `0x1800272f0`
- `0x180027394`
- `0x180027724`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180027745`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180027745`

## string_xrefs

- `0x1800277b2`: `%windir%\ServiceState\wmansvc`
- `0x1800277cc`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18002789f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18002777a`: `%windir%\ServiceState\autopilot`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize(
        Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation *this,
        struct SERVICE_STATUS_HANDLE__ *a2)
{
  int NonStateSeparationAwareExpandedFilePath; // eax
  __int128 *v4; // rbx
  int v5; // eax
  unsigned int v6; // edi
  const char *v7; // r9
  __int64 result; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rdi
  __int128 *v11; // r8
  __int64 v12; // rcx
  __int128 *v13; // r8
  int FolderHierarchyWithAcls; // esi
  __int64 v15; // rcx
  int v16; // [rsp+20h] [rbp-38h]
  __int128 v17; // [rsp+28h] [rbp-30h] BYREF
  __m128i si128; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_BYTE *)this = (unsigned __int8)RtlIsStateSeparationEnabled(this, a2) != 0;
  v17 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v17) = 0;
  NonStateSeparationAwareExpandedFilePath = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(
                                              L"%windir%\\ServiceState\\autopilot",
                                              &v17);
  try
  {
    if ( NonStateSeparationAwareExpandedFilePath >= 0
      && (unsigned __int8)Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(&v17) )
    {
      v4 = (__int128 *)((char *)this + 8);
      std::wstring::operator=(v4, &v17);
    }
    else
    {
      v4 = (__int128 *)((char *)this + 8);
      v5 = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(
             L"%windir%\\ServiceState\\wmansvc",
             v4);
      v6 = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
          (const char *)(unsigned int)v5,
          v16);
        std::wstring::_Tidy_deallocate(&v17);
        return v6;
      }
    }
    std::wstring::_Tidy_deallocate(&v17);
    v10 = (_QWORD *)v4 + 3;
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) != 0 )
    {
      if ( *v10 <= 7u )
        v11 = v4;
      else
        v11 = *(__int128 **)v4;
      McTemplateU0z_EventWriteTransfer(v9, ManagementServiceStateSeparationFolderPath, v11);
    }
    if ( !(unsigned __int8)Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(v4) )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) != 0 )
      {
        if ( *v10 <= 7u )
          v13 = v4;
        else
          v13 = *(__int128 **)v4;
        McTemplateU0z_EventWriteTransfer(v12, ManagementServiceStateSeparationFolderNotFound, v13);
      }
      v17 = 0;
      si128 = 0;
      std::wstring::_Construct<1,unsigned short const *>(
        &v17,
        L"D:PAI(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)(A;OICI;FA;;;SU)(A;OICI;FR;;;WD)");
      FolderHierarchyWithAcls = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls(
                                  v4,
                                  (__int64)&v17);
      std::wstring::_Tidy_deallocate(&v17);
      if ( FolderHierarchyWithAcls < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
          (const char *)(unsigned int)FolderHierarchyWithAcls,
          v16);
        return (unsigned int)FolderHierarchyWithAcls;
      }
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) != 0 )
      {
        if ( *v10 > 7u )
          v4 = *(__int128 **)v4;
        McTemplateU0z_EventWriteTransfer(v15, ManagementServiceStateSeparationFolderCreated, v4);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6C,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x180027724  mov     [rsp+arg_8], rbx
0x180027729  mov     [rsp+arg_10], rsi
0x18002772e  push    rdi
0x18002772f  sub     rsp, 50h
0x180027733  mov     rax, cs:__security_cookie
0x18002773a  xor     rax, rsp
0x18002773d  mov     [rsp+58h+var_10], rax
0x180027742  mov     rbx, rcx
0x180027745  call    cs:__imp_RtlIsStateSeparationEnabled
0x18002774c  nop     dword ptr [rax+rax+00h]
0x180027751  test    al, al
0x180027753  setnz   al
0x180027756  mov     [rbx], al
0x180027758  xorps   xmm0, xmm0
0x18002775b  movups  [rsp+58h+var_30], xmm0
0x180027760  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180027768  movdqu  [rsp+58h+var_20], xmm1
0x18002776e  xor     eax, eax
0x180027770  mov     word ptr [rsp+58h+var_30], ax
0x180027775  lea     rdx, [rsp+58h+var_30]
0x18002777a  lea     rcx, Src; "%windir%\\ServiceState\\autopilot"
0x180027781  call    ?GetNonStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x180027786  test    eax, eax
0x180027788  js      short loc_1800277AB
0x18002778a  lea     rcx, [rsp+58h+var_30]
0x18002778f  call    ?DirectoryExists@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(std::wstring const &)
0x180027794  test    al, al
0x180027796  jz      short loc_1800277AB
0x180027798  add     rbx, 8
0x18002779c  lea     rdx, [rsp+58h+var_30]
0x1800277a1  mov     rcx, rbx
0x1800277a4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800277a9  jmp     short loc_1800277EF
0x1800277ab  add     rbx, 8
0x1800277af  mov     rdx, rbx
0x1800277b2  lea     rcx, aWindirServices_0; "%windir%\\ServiceState\\wmansvc"
0x1800277b9  call    ?GetNonStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x1800277be  mov     edi, eax
0x1800277c0  test    eax, eax
0x1800277c2  jns     short loc_1800277EF
0x1800277c4  mov     rcx, [rsp+58h]; this
0x1800277c9  mov     r9d, eax; char *
0x1800277cc  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800277d3  mov     edx, 5Ch ; '\'; void *
0x1800277d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800277dd  nop
0x1800277de  lea     rcx, [rsp+58h+var_30]
0x1800277e3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800277e8  mov     eax, edi
0x1800277ea  jmp     loc_1800278DD
0x1800277ef  lea     rcx, [rsp+58h+var_30]
0x1800277f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800277f9  lea     rdi, [rbx+18h]
0x1800277fd  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 80h
0x180027804  jz      short loc_180027820
0x180027806  cmp     qword ptr [rdi], 7
0x18002780a  jbe     short loc_180027811
0x18002780c  mov     r8, [rbx]
0x18002780f  jmp     short loc_180027814
0x180027811  mov     r8, rbx
0x180027814  lea     rdx, ManagementServiceStateSeparationFolderPath
0x18002781b  call    McTemplateU0z_EventWriteTransfer
0x180027820  mov     rcx, rbx
0x180027823  call    ?DirectoryExists@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(std::wstring const &)
0x180027828  test    al, al
0x18002782a  jnz     loc_1800278D5
0x180027830  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, al
0x180027836  jge     short loc_180027852
0x180027838  cmp     qword ptr [rdi], 7
0x18002783c  jbe     short loc_180027843
0x18002783e  mov     r8, [rbx]
0x180027841  jmp     short loc_180027846
0x180027843  mov     r8, rbx
0x180027846  lea     rdx, ManagementServiceStateSeparationFolderNotFound
0x18002784d  call    McTemplateU0z_EventWriteTransfer
0x180027852  xorps   xmm0, xmm0
0x180027855  movups  [rsp+58h+var_30], xmm0
0x18002785a  xorps   xmm1, xmm1
0x18002785d  movdqu  [rsp+58h+var_20], xmm1
0x180027863  mov     r8d, 45h ; 'E'
0x180027869  lea     rdx, aDPaiAOiciFaBaA; "D:PAI(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)(A"...
0x180027870  lea     rcx, [rsp+58h+var_30]
0x180027875  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002787a  lea     rdx, [rsp+58h+var_30]
0x18002787f  mov     rcx, rbx
0x180027882  call    ?CreateFolderHierarchyWithAcls@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls(std::wstring const &,std::wstring const &)
0x180027887  mov     esi, eax
0x180027889  lea     rcx, [rsp+58h+var_30]
0x18002788e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027893  test    esi, esi
0x180027895  jns     short loc_1800278B4
0x180027897  mov     rcx, [rsp+58h]; this
0x18002789c  mov     r9d, esi; char *
0x18002789f  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800278a6  mov     edx, 66h ; 'f'; void *
0x1800278ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800278b0  mov     eax, esi
0x1800278b2  jmp     short loc_1800278DD
0x1800278b4  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x1800278bb  jge     short loc_1800278D5
0x1800278bd  cmp     qword ptr [rdi], 7
0x1800278c1  jbe     short loc_1800278C6
0x1800278c3  mov     rbx, [rbx]
0x1800278c6  mov     r8, rbx
0x1800278c9  lea     rdx, ManagementServiceStateSeparationFolderCreated
0x1800278d0  call    McTemplateU0z_EventWriteTransfer
0x1800278d5  xor     eax, eax
0x1800278d7  jmp     short loc_1800278DD
0x1800278d9  mov     eax, [rsp+58h+var_38]
0x1800278dd  mov     rcx, [rsp+58h+var_10]
0x1800278e2  xor     rcx, rsp; StackCookie
0x1800278e5  call    __security_check_cookie
0x1800278ea  mov     rbx, [rsp+58h+arg_8]
0x1800278ef  mov     rsi, [rsp+58h+arg_10]
0x1800278f4  add     rsp, 50h
0x1800278f8  pop     rdi
0x1800278f9  retn
```
