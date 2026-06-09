# Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize(SERVICE_STATUS_HANDLE__ *)

- ea: `0x180026794`
- end: `0x180026989`
- name: `?Initialize@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@QEAAJPEAUSERVICE_STATUS_HANDLE__@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation *__hidden this, struct SERVICE_STATUS_HANDLE__ *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002661c`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x180013370`
- `0x180013a40`
- `0x1800174f0`
- `0x180019230`
- `0x180026100`
- `0x180026430`
- `0x180026794`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800267b5`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800267b5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180026805`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800268aa`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180026805`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800268aa`

## string_xrefs

- `0x18002682e`: `%windir%\ServiceState\wmansvc`
- `0x180026848`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18002692d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x1800267e4`: `%windir%\ServiceState\autopilot`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize(
        Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation *this,
        struct SERVICE_STATUS_HANDLE__ *a2)
{
  int NonStateSeparationAwareExpandedFilePath; // eax
  const WCHAR *v4; // rcx
  DWORD FileAttributesW; // eax
  _QWORD *v6; // rbx
  int v7; // eax
  unsigned int v8; // edi
  const char *v9; // r9
  __int64 result; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rdi
  _QWORD *v13; // r8
  const WCHAR *v14; // rcx
  DWORD v15; // eax
  __int64 v16; // rcx
  _QWORD *v17; // r8
  int FolderHierarchyWithAcls; // esi
  __int64 v19; // rcx
  int v20; // [rsp+20h] [rbp-38h]
  LPCWSTR lpFileName[2]; // [rsp+28h] [rbp-30h] BYREF
  __m128i si128; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_BYTE *)this = (unsigned __int8)RtlIsStateSeparationEnabled(this, a2) != 0;
  *(_OWORD *)lpFileName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpFileName[0]) = 0;
  NonStateSeparationAwareExpandedFilePath = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(L"%windir%\\ServiceState\\autopilot");
  try
  {
    if ( NonStateSeparationAwareExpandedFilePath < 0 )
      goto LABEL_8;
    v4 = (const WCHAR *)lpFileName;
    if ( si128.m128i_i64[1] > 7uLL )
      v4 = lpFileName[0];
    FileAttributesW = GetFileAttributesW(v4);
    if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
    {
LABEL_8:
      v6 = (_QWORD *)((char *)this + 8);
      v7 = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(L"%windir%\\ServiceState\\wmansvc");
      v8 = v7;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
          (const char *)(unsigned int)v7,
          v20);
        std::wstring::_Tidy_deallocate(lpFileName);
        return v8;
      }
    }
    else
    {
      v6 = (_QWORD *)((char *)this + 8);
      std::wstring::operator=(v6, lpFileName);
    }
    std::wstring::_Tidy_deallocate(lpFileName);
    v12 = v6 + 3;
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) != 0 )
    {
      if ( *v12 <= 7u )
        v13 = v6;
      else
        v13 = (_QWORD *)*v6;
      McTemplateU0z_EventWriteTransfer(v11, ManagementServiceStateSeparationFolderPath, v13);
    }
    if ( *v12 <= 7u )
      v14 = (const WCHAR *)v6;
    else
      v14 = (const WCHAR *)*v6;
    v15 = GetFileAttributesW(v14);
    if ( v15 == -1 || (v15 & 0x10) == 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) != 0 )
      {
        if ( *v12 <= 7u )
          v17 = v6;
        else
          v17 = (_QWORD *)*v6;
        McTemplateU0z_EventWriteTransfer(v16, ManagementServiceStateSeparationFolderNotFound, v17);
      }
      *(_OWORD *)lpFileName = 0;
      si128 = 0;
      std::wstring::_Construct<1,unsigned short const *>(
        lpFileName,
        L"D:PAI(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)(A;OICI;FA;;;SU)(A;OICI;FR;;;WD)",
        69);
      FolderHierarchyWithAcls = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls(
                                  v6,
                                  (__int64)lpFileName);
      std::wstring::_Tidy_deallocate(lpFileName);
      if ( FolderHierarchyWithAcls < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
          (const char *)(unsigned int)FolderHierarchyWithAcls,
          v20);
        return (unsigned int)FolderHierarchyWithAcls;
      }
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) != 0 )
      {
        if ( *v12 > 7u )
          v6 = (_QWORD *)*v6;
        McTemplateU0z_EventWriteTransfer(v19, ManagementServiceStateSeparationFolderCreated, v6);
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
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x180026794  mov     [rsp+arg_8], rbx
0x180026799  mov     [rsp+arg_10], rsi
0x18002679e  push    rdi
0x18002679f  sub     rsp, 50h
0x1800267a3  mov     rax, cs:__security_cookie
0x1800267aa  xor     rax, rsp
0x1800267ad  mov     [rsp+58h+var_10], rax
0x1800267b2  mov     rbx, rcx
0x1800267b5  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800267bb  test    al, al
0x1800267bd  setnz   al
0x1800267c0  mov     [rbx], al
0x1800267c2  xorps   xmm0, xmm0
0x1800267c5  movups  xmmword ptr [rsp+58h+lpFileName], xmm0
0x1800267ca  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800267d2  movdqu  [rsp+58h+var_20], xmm1
0x1800267d8  xor     eax, eax
0x1800267da  mov     word ptr [rsp+58h+lpFileName], ax
0x1800267df  lea     rdx, [rsp+58h+lpFileName]
0x1800267e4  lea     rcx, Src; "%windir%\\ServiceState\\autopilot"
0x1800267eb  call    ?GetNonStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x1800267f0  test    eax, eax
0x1800267f2  js      short loc_180026827
0x1800267f4  lea     rcx, [rsp+58h+lpFileName]
0x1800267f9  cmp     qword ptr [rsp+58h+var_20+8], 7
0x1800267ff  cmova   rcx, [rsp+58h+lpFileName]; lpFileName
0x180026805  call    cs:__imp_GetFileAttributesW
0x18002680b  cmp     eax, 0FFFFFFFFh
0x18002680e  jz      short loc_180026827
0x180026810  test    al, 10h
0x180026812  jz      short loc_180026827
0x180026814  add     rbx, 8
0x180026818  lea     rdx, [rsp+58h+lpFileName]
0x18002681d  mov     rcx, rbx
0x180026820  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180026825  jmp     short loc_18002686B
0x180026827  add     rbx, 8
0x18002682b  mov     rdx, rbx
0x18002682e  lea     rcx, aWindirServices_0; "%windir%\\ServiceState\\wmansvc"
0x180026835  call    ?GetNonStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x18002683a  mov     edi, eax
0x18002683c  test    eax, eax
0x18002683e  jns     short loc_18002686B
0x180026840  mov     rcx, [rsp+58h]; this
0x180026845  mov     r9d, eax; char *
0x180026848  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002684f  mov     edx, 5Ch ; '\'; void *
0x180026854  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026859  nop
0x18002685a  lea     rcx, [rsp+58h+lpFileName]
0x18002685f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026864  mov     eax, edi
0x180026866  jmp     loc_18002696B
0x18002686b  lea     rcx, [rsp+58h+lpFileName]
0x180026870  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026875  lea     rdi, [rbx+18h]
0x180026879  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x180026880  jge     short loc_18002689C
0x180026882  cmp     qword ptr [rdi], 7
0x180026886  jbe     short loc_18002688D
0x180026888  mov     r8, [rbx]
0x18002688b  jmp     short loc_180026890
0x18002688d  mov     r8, rbx
0x180026890  lea     rdx, ManagementServiceStateSeparationFolderPath
0x180026897  call    McTemplateU0z_EventWriteTransfer
0x18002689c  cmp     qword ptr [rdi], 7
0x1800268a0  jbe     short loc_1800268A7
0x1800268a2  mov     rcx, [rbx]
0x1800268a5  jmp     short loc_1800268AA
0x1800268a7  mov     rcx, rbx; lpFileName
0x1800268aa  call    cs:__imp_GetFileAttributesW
0x1800268b0  cmp     eax, 0FFFFFFFFh
0x1800268b3  jz      short loc_1800268BD
0x1800268b5  test    al, 10h
0x1800268b7  jnz     loc_180026963
0x1800268bd  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x1800268c4  jge     short loc_1800268E0
0x1800268c6  cmp     qword ptr [rdi], 7
0x1800268ca  jbe     short loc_1800268D1
0x1800268cc  mov     r8, [rbx]
0x1800268cf  jmp     short loc_1800268D4
0x1800268d1  mov     r8, rbx
0x1800268d4  lea     rdx, ManagementServiceStateSeparationFolderNotFound
0x1800268db  call    McTemplateU0z_EventWriteTransfer
0x1800268e0  xorps   xmm0, xmm0
0x1800268e3  movups  xmmword ptr [rsp+58h+lpFileName], xmm0
0x1800268e8  xorps   xmm1, xmm1
0x1800268eb  movdqu  [rsp+58h+var_20], xmm1
0x1800268f1  mov     r8d, 45h ; 'E'
0x1800268f7  lea     rdx, aDPaiAOiciFaBaA; "D:PAI(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)(A"...
0x1800268fe  lea     rcx, [rsp+58h+lpFileName]
0x180026903  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180026908  lea     rdx, [rsp+58h+lpFileName]
0x18002690d  mov     rcx, rbx
0x180026910  call    ?CreateFolderHierarchyWithAcls@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls(std::wstring const &,std::wstring const &)
0x180026915  mov     esi, eax
0x180026917  lea     rcx, [rsp+58h+lpFileName]
0x18002691c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026921  test    esi, esi
0x180026923  jns     short loc_180026942
0x180026925  mov     rcx, [rsp+58h]; this
0x18002692a  mov     r9d, esi; char *
0x18002692d  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026934  mov     edx, 66h ; 'f'; void *
0x180026939  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002693e  mov     eax, esi
0x180026940  jmp     short loc_18002696B
0x180026942  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x180026949  jge     short loc_180026963
0x18002694b  cmp     qword ptr [rdi], 7
0x18002694f  jbe     short loc_180026954
0x180026951  mov     rbx, [rbx]
0x180026954  mov     r8, rbx
0x180026957  lea     rdx, ManagementServiceStateSeparationFolderCreated
0x18002695e  call    McTemplateU0z_EventWriteTransfer
0x180026963  xor     eax, eax
0x180026965  jmp     short loc_18002696B
0x180026967  mov     eax, [rsp+58h+var_38]
0x18002696b  mov     rcx, [rsp+58h+var_10]
0x180026970  xor     rcx, rsp; StackCookie
0x180026973  call    __security_check_cookie
0x180026978  mov     rbx, [rsp+58h+arg_8]
0x18002697d  mov     rsi, [rsp+58h+arg_10]
0x180026982  add     rsp, 50h
0x180026986  pop     rdi
0x180026987  retn
```
