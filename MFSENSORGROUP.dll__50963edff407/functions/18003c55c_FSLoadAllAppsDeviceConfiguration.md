# FSLoadAllAppsDeviceConfiguration

- ea: `0x18003c55c`
- end: `0x18003c8b7`
- name: `FSLoadAllAppsDeviceConfiguration`
- size: `859`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, struct IFSConfiguration **)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180012284`
- `0x180057f50`

## callees

- `0x1800049b0`
- `0x180005b90`
- `0x180005fa0`
- `0x180008f9c`
- `0x180010914`
- `0x180016328`
- `0x18001635c`
- `0x18002d02c`
- `0x18003c55c`
- `0x180044b28`
- `0x180070948`
- `0x180070f44`
- `0x180071be4`
- `0x180071d2c`
- `0x180077010`

## string_xrefs

- `0x18003c76b`: `FRAMESERVER_CONFIGURATION_ALL_APPS`
- `0x18003c7f0`: `FRAMESERVER_CONFIGURATION_ALL_APPS`

## pseudocode

```c
__int64 __fastcall FSLoadAllAppsDeviceConfiguration(LPCWSTR pszDeviceInterface, struct IFSConfiguration **a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rdx
  void **unique; // rax
  void *v10; // rcx
  WCHAR *v11; // rdi
  int v12; // eax
  __int64 v13; // rdx
  void **v14; // rax
  void *v15; // rcx
  unsigned __int16 *v16; // r14
  int v17; // eax
  __int64 v18; // rdx
  struct IFSConfigurationKey *v19; // rcx
  struct IFSConfigurationKey *v21; // [rsp+30h] [rbp-20h] BYREF
  void *Block; // [rsp+38h] [rbp-18h] BYREF
  LPCWSTR pszDeviceInterfacea; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v24; // [rsp+48h] [rbp-8h] BYREF
  void *v25; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v26; // [rsp+98h] [rbp+48h] BYREF

  v4 = FSLoadAllAppsDeviceConfiguration_Internal(pszDeviceInterface, a2);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraManagedModePolicy>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CameraManagedModePolicy>::GetImpl'::`2'::impl) )
    return v4;
  if ( (v4 & 0x80000000) != 0 )
  {
    if ( v4 != -1072875819 )
      return v4;
    v21 = 0;
    pszDeviceInterfacea = 0;
    LODWORD(v25) = 0;
    v24 = 0;
    v26 = 0;
    if ( (unsigned __int8)byte_18008D62D >= 8u )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        91,
        &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
        pszDeviceInterface);
    if ( !a2 )
    {
      v4 = -2147467261;
      if ( g_wppLevels )
      {
        v6 = 92;
LABEL_12:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v4);
        goto LABEL_52;
      }
      goto LABEL_52;
    }
    *a2 = 0;
    if ( !pszDeviceInterface )
    {
      v4 = -2147024809;
      if ( g_wppLevels )
      {
        v6 = 93;
        goto LABEL_12;
      }
LABEL_52:
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v21);
      return v4;
    }
    v7 = FSGetUniqueSymbolicName(pszDeviceInterface, 0, 0, (unsigned int *)&v25);
    v4 = v7;
    if ( v7 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_52;
      v8 = 94;
LABEL_20:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v7);
      goto LABEL_52;
    }
    unique = (void **)wil::make_unique_nothrow<unsigned short [0]>(&Block, (unsigned int)v25);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
      (void **)&pszDeviceInterfacea,
      unique);
    v10 = Block;
    Block = 0;
    if ( v10 )
      operator delete(v10);
    v11 = (WCHAR *)pszDeviceInterfacea;
    if ( !pszDeviceInterfacea )
    {
      v7 = -2147024882;
      v4 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_52;
      v8 = (unsigned int)((_DWORD)pszDeviceInterfacea + 95);
      goto LABEL_20;
    }
    v12 = FSGetUniqueSymbolicName(
            pszDeviceInterface,
            (unsigned __int16 *)pszDeviceInterfacea,
            (unsigned int)v25,
            (unsigned int *)&v25);
    v4 = v12;
    if ( v12 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_50;
      v13 = 96;
      goto LABEL_29;
    }
    v12 = FSTagPackageFamilyName(L"FRAMESERVER_CONFIGURATION_ALL_APPS", 0, 0, &v26);
    v4 = v12;
    if ( v12 < 0 )
    {
      if ( g_wppLevels )
      {
        v13 = 97;
LABEL_29:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v12);
        goto LABEL_50;
      }
      goto LABEL_50;
    }
    v14 = (void **)wil::make_unique_nothrow<unsigned short [0]>(&v25, v26);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v24, v14);
    v15 = v25;
    v25 = 0;
    if ( v15 )
      operator delete(v15);
    v16 = v24;
    if ( !v24 )
    {
      v12 = -2147024882;
      v4 = -2147024882;
      if ( g_wppLevels )
      {
        v13 = (unsigned int)((_DWORD)v24 + 98);
        goto LABEL_29;
      }
LABEL_50:
      if ( v11 )
        operator delete(v11);
      goto LABEL_52;
    }
    v17 = FSTagPackageFamilyName(L"FRAMESERVER_CONFIGURATION_ALL_APPS", v24, v26, &v26);
    v4 = v17;
    if ( v17 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_48;
      v18 = 99;
      goto LABEL_41;
    }
    v19 = v21;
    v21 = 0;
    if ( v19 )
      (*(void (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)v19 + 16LL))(v19);
    v17 = FSCreateConfigurationKey(v11);
    v4 = v17;
    if ( v17 >= 0 )
    {
      v4 = FSLoadCameraManagedModePolicyConfiguration(v21, a2);
    }
    else if ( g_wppLevels )
    {
      v18 = 100;
LABEL_41:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v17);
    }
LABEL_48:
    if ( v16 )
      operator delete(v16);
    goto LABEL_50;
  }
  v5 = SetPolicyToDeviceConfiguration(*a2);
  v4 = v5;
  if ( v5 < 0 && g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v5);
  return v4;
}

```

## disassembly

```asm
0x18003c55c  mov     [rsp-28h+arg_0], rbx
0x18003c561  push    rbp
0x18003c562  push    rsi
0x18003c563  push    rdi
0x18003c564  push    r14
0x18003c566  push    r15
0x18003c568  mov     rbp, rsp
0x18003c56b  sub     rsp, 50h
0x18003c56f  mov     r15, rdx
0x18003c572  mov     r14, rcx
0x18003c575  call    ?FSLoadAllAppsDeviceConfiguration_Internal@@YAJPEBGPEAPEAUIFSConfiguration@@@Z; FSLoadAllAppsDeviceConfiguration_Internal(ushort const *,IFSConfiguration * *)
0x18003c57a  mov     ebx, eax
0x18003c57c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CameraManagedModePolicy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CameraManagedModePolicy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraManagedModePolicy> `wil::Feature<__WilFeatureTraits_Feature_CameraManagedModePolicy>::GetImpl(void)'::`2'::impl
0x18003c583  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CameraManagedModePolicy@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraManagedModePolicy>::__private_IsEnabled(void)
0x18003c588  test    al, al
0x18003c58a  jz      loc_18003C8A1
0x18003c590  test    ebx, ebx
0x18003c592  js      short loc_18003C5DB
0x18003c594  mov     rcx, [r15]; struct IFSConfiguration *
0x18003c597  call    ?SetPolicyToDeviceConfiguration@@YAJPEAUIFSConfiguration@@@Z; SetPolicyToDeviceConfiguration(IFSConfiguration *)
0x18003c59c  mov     ebx, eax
0x18003c59e  test    eax, eax
0x18003c5a0  jns     loc_18003C8A1
0x18003c5a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c5ad  jb      loc_18003C8A1
0x18003c5b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c5ba  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18003c5c1  mov     edx, 5Ah ; 'Z'
0x18003c5c6  mov     [rsp+50h+var_30], eax
0x18003c5ca  xor     r9d, r9d
0x18003c5cd  mov     rcx, [rcx+10h]
0x18003c5d1  call    WPP_SF_qD
0x18003c5d6  jmp     loc_18003C8A1
0x18003c5db  cmp     ebx, 0C00D36D5h
0x18003c5e1  jnz     loc_18003C8A1
0x18003c5e7  mov     [rbp+var_20], 0
0x18003c5ef  mov     [rbp+pszDeviceInterface], 0
0x18003c5f7  mov     dword ptr [rbp+arg_10], 0
0x18003c5fe  mov     [rbp+var_8], 0
0x18003c606  mov     [rbp+arg_18], 0
0x18003c60d  cmp     cs:byte_18008D62D, 8
0x18003c614  lea     rsi, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18003c61b  jb      short loc_18003C63B
0x18003c61d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c624  mov     edx, 5Bh ; '['
0x18003c629  mov     r9, r14
0x18003c62c  mov     r8, rsi
0x18003c62f  mov     rcx, [rcx+0D8h]
0x18003c636  call    WPP_SF_S
0x18003c63b  test    r15, r15
0x18003c63e  jnz     short loc_18003C675
0x18003c640  mov     ebx, 80004003h
0x18003c645  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c64c  jb      loc_18003C898
0x18003c652  lea     edx, [r15+5Ch]
0x18003c656  mov     [rsp+50h+var_30], ebx
0x18003c65a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c661  xor     r9d, r9d
0x18003c664  mov     r8, rsi
0x18003c667  mov     rcx, [rcx+10h]
0x18003c66b  call    WPP_SF_qD
0x18003c670  jmp     loc_18003C898
0x18003c675  mov     qword ptr [r15], 0
0x18003c67c  test    r14, r14
0x18003c67f  jnz     short loc_18003C699
0x18003c681  mov     ebx, 80070057h
0x18003c686  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c68d  jb      loc_18003C898
0x18003c693  lea     edx, [r14+5Dh]
0x18003c697  jmp     short loc_18003C656
0x18003c699  lea     r9, [rbp+arg_10]; unsigned int *
0x18003c69d  xor     r8d, r8d; unsigned int
0x18003c6a0  xor     edx, edx; unsigned __int16 *
0x18003c6a2  mov     rcx, r14; pszDeviceInterface
0x18003c6a5  call    ?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z; FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)
0x18003c6aa  mov     ebx, eax
0x18003c6ac  test    eax, eax
0x18003c6ae  jns     short loc_18003C6C8
0x18003c6b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c6b7  jb      loc_18003C898
0x18003c6bd  mov     edx, 5Eh ; '^'
0x18003c6c2  mov     [rsp+50h+var_30], eax
0x18003c6c6  jmp     short loc_18003C65A
0x18003c6c8  mov     edx, dword ptr [rbp+arg_10]
0x18003c6cb  lea     rcx, [rbp+Block]
0x18003c6cf  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18003c6d4  mov     rdx, rax
0x18003c6d7  lea     rcx, [rbp+pszDeviceInterface]
0x18003c6db  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003c6e0  mov     rcx, [rbp+Block]; Block
0x18003c6e4  mov     [rbp+Block], 0
0x18003c6ec  test    rcx, rcx
0x18003c6ef  jz      short loc_18003C6F6
0x18003c6f1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003c6f6  mov     rdi, [rbp+pszDeviceInterface]
0x18003c6fa  test    rdi, rdi
0x18003c6fd  jnz     short loc_18003C718
0x18003c6ff  mov     eax, 8007000Eh
0x18003c704  mov     ebx, eax
0x18003c706  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c70d  jb      loc_18003C898
0x18003c713  lea     edx, [rdi+5Fh]
0x18003c716  jmp     short loc_18003C6C2
0x18003c718  mov     r8d, dword ptr [rbp+arg_10]; unsigned int
0x18003c71c  lea     r9, [rbp+arg_10]; unsigned int *
0x18003c720  mov     rdx, rdi; unsigned __int16 *
0x18003c723  mov     rcx, r14; pszDeviceInterface
0x18003c726  call    ?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z; FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)
0x18003c72b  mov     ebx, eax
0x18003c72d  test    eax, eax
0x18003c72f  jns     short loc_18003C762
0x18003c731  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c738  jb      loc_18003C88B
0x18003c73e  mov     edx, 60h ; '`'
0x18003c743  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c74a  xor     r9d, r9d
0x18003c74d  mov     r8, rsi
0x18003c750  mov     [rsp+50h+var_30], eax
0x18003c754  mov     rcx, [rcx+10h]
0x18003c758  call    WPP_SF_qD
0x18003c75d  jmp     loc_18003C88B
0x18003c762  lea     r9, [rbp+arg_18]; unsigned int *
0x18003c766  xor     r8d, r8d; unsigned int
0x18003c769  xor     edx, edx; unsigned __int16 *
0x18003c76b  lea     rcx, aFrameserverCon; "FRAMESERVER_CONFIGURATION_ALL_APPS"
0x18003c772  call    ?FSTagPackageFamilyName@@YAJPEBGPEAGKPEAK@Z; FSTagPackageFamilyName(ushort const *,ushort *,ulong,ulong *)
0x18003c777  mov     ebx, eax
0x18003c779  test    eax, eax
0x18003c77b  jns     short loc_18003C791
0x18003c77d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c784  jb      loc_18003C88B
0x18003c78a  mov     edx, 61h ; 'a'
0x18003c78f  jmp     short loc_18003C743
0x18003c791  mov     edx, [rbp+arg_18]
0x18003c794  lea     rcx, [rbp+arg_10]
0x18003c798  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18003c79d  mov     rdx, rax
0x18003c7a0  lea     rcx, [rbp+var_8]
0x18003c7a4  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003c7a9  mov     rcx, [rbp+arg_10]; Block
0x18003c7ad  mov     [rbp+arg_10], 0
0x18003c7b5  test    rcx, rcx
0x18003c7b8  jz      short loc_18003C7BF
0x18003c7ba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003c7bf  mov     r14, [rbp+var_8]
0x18003c7c3  test    r14, r14
0x18003c7c6  jnz     short loc_18003C7E5
0x18003c7c8  mov     eax, 8007000Eh
0x18003c7cd  mov     ebx, eax
0x18003c7cf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c7d6  jb      loc_18003C88B
0x18003c7dc  lea     edx, [r14+62h]
0x18003c7e0  jmp     loc_18003C743
0x18003c7e5  mov     r8d, [rbp+arg_18]; unsigned int
0x18003c7e9  lea     r9, [rbp+arg_18]; unsigned int *
0x18003c7ed  mov     rdx, r14; unsigned __int16 *
0x18003c7f0  lea     rcx, aFrameserverCon; "FRAMESERVER_CONFIGURATION_ALL_APPS"
0x18003c7f7  call    ?FSTagPackageFamilyName@@YAJPEBGPEAGKPEAK@Z; FSTagPackageFamilyName(ushort const *,ushort *,ulong,ulong *)
0x18003c7fc  mov     ebx, eax
0x18003c7fe  test    eax, eax
0x18003c800  jns     short loc_18003C82C
0x18003c802  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c809  jb      short loc_18003C87E
0x18003c80b  mov     edx, 63h ; 'c'
0x18003c810  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c817  xor     r9d, r9d
0x18003c81a  mov     r8, rsi
0x18003c81d  mov     [rsp+50h+var_30], eax
0x18003c821  mov     rcx, [rcx+10h]
0x18003c825  call    WPP_SF_qD
0x18003c82a  jmp     short loc_18003C87E
0x18003c82c  mov     rcx, [rbp+var_20]
0x18003c830  mov     [rbp+var_20], 0
0x18003c838  test    rcx, rcx
0x18003c83b  jz      short loc_18003C849
0x18003c83d  mov     rax, [rcx]
0x18003c840  mov     rax, [rax+10h]
0x18003c844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c849  lea     r9, [rbp+var_20]
0x18003c84d  mov     r8, r14
0x18003c850  xor     edx, edx
0x18003c852  mov     rcx, rdi; pszDeviceInterface
0x18003c855  call    FSCreateConfigurationKey
0x18003c85a  mov     ebx, eax
0x18003c85c  test    eax, eax
0x18003c85e  jns     short loc_18003C870
0x18003c860  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c867  jb      short loc_18003C87E
0x18003c869  mov     edx, 64h ; 'd'
0x18003c86e  jmp     short loc_18003C810
0x18003c870  mov     rcx, [rbp+var_20]; struct IFSConfigurationKey *
0x18003c874  mov     rdx, r15; struct IFSConfiguration **
0x18003c877  call    ?FSLoadCameraManagedModePolicyConfiguration@@YAJPEAUIFSConfigurationKey@@PEAPEAUIFSConfiguration@@@Z; FSLoadCameraManagedModePolicyConfiguration(IFSConfigurationKey *,IFSConfiguration * *)
0x18003c87c  mov     ebx, eax
0x18003c87e  test    r14, r14
0x18003c881  jz      short loc_18003C88B
0x18003c883  mov     rcx, r14; Block
0x18003c886  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003c88b  test    rdi, rdi
0x18003c88e  jz      short loc_18003C898
0x18003c890  mov     rcx, rdi; Block
0x18003c893  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003c898  lea     rcx, [rbp+var_20]
0x18003c89c  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18003c8a1  mov     eax, ebx
0x18003c8a3  mov     rbx, [rsp+50h+arg_0]
0x18003c8ab  add     rsp, 50h
0x18003c8af  pop     r15
0x18003c8b1  pop     r14
0x18003c8b3  pop     rdi
0x18003c8b4  pop     rsi
0x18003c8b5  pop     rbp
0x18003c8b6  retn
```
