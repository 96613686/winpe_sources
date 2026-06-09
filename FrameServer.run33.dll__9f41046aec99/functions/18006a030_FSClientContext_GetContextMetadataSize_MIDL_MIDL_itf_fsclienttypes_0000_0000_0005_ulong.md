# FSClientContext::GetContextMetadataSize(__MIDL___MIDL_itf_fsclienttypes_0000_0000_0005,ulong *)

- ea: `0x18006a030`
- end: `0x18006a59b`
- name: `?GetContextMetadataSize@FSClientContext@@UEAAJW4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0005@@PEAK@Z`
- size: `1387`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x1800096f4`
- `0x18006a030`
- `0x180073c8c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006a243`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006a35a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006a243`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006a35a`
- `MFPlat!MFCreateAttributes` at `0x18006a265`
- `MFPlat!MFCreateAttributes` at `0x18006a37c`
- `MFPlat!MFCreateAttributes` at `0x18006a265`
- `MFPlat!MFCreateAttributes` at `0x18006a37c`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x18006a17f`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x18006a1c3`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x18006a42a`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x18006a4ab`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x18006a17f`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x18006a1c3`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x18006a42a`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x18006a4ab`

## pseudocode

```c
__int64 __fastcall FSClientContext::GetContextMetadataSize(__int64 a1, int a2, UINT32 *a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  UINT32 v8; // eax
  __int64 v9; // r14
  __int64 (__fastcall *v10)(__int64, IMFAttributes **); // rbx
  HRESULT v11; // eax
  __int64 v12; // rdx
  IMFAttributes *v13; // rcx
  HRESULT v14; // eax
  __int64 v15; // rdx
  IMFAttributes **v16; // r14
  char v17; // al
  __int64 v18; // r8
  char v19; // al
  IMFAttributes *v20; // rcx
  UINT32 v22[4]; // [rsp+40h] [rbp-10h] BYREF
  UINT32 pcbBufSize; // [rsp+90h] [rbp+40h] BYREF
  IMFAttributes *pAttributes; // [rsp+98h] [rbp+48h] BYREF

  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 273, &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids, a1, a2);
  if ( !a3 )
  {
    v6 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_77;
    v7 = 274;
LABEL_76:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids, a1, v6);
    goto LABEL_77;
  }
  v6 = 0;
  *a3 = 0;
  switch ( a2 )
  {
    case 1:
      v8 = *(_DWORD *)(a1 + 808);
LABEL_71:
      *a3 = v8;
      goto LABEL_72;
    case 2:
      v9 = *(_QWORD *)(a1 + 864);
      pAttributes = 0;
      pcbBufSize = 0;
      if ( !v9 )
      {
        v6 = -1072875819;
        if ( g_wppLevels >= 8u )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            275,
            &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids,
            a1,
            -1072875819);
        goto LABEL_12;
      }
      v10 = *(__int64 (__fastcall **)(__int64, IMFAttributes **))(*(_QWORD *)v9 + 64LL);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&pAttributes);
      v11 = v10(v9, &pAttributes);
      v6 = v11;
      if ( v11 >= 0 )
      {
        v11 = MFGetAttributesAsBlobSize(pAttributes, &pcbBufSize);
        v6 = v11;
        if ( v11 >= 0 )
        {
          *a3 = pcbBufSize;
LABEL_12:
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&pAttributes);
          goto LABEL_72;
        }
        if ( !g_wppLevels )
          goto LABEL_17;
        v12 = 277;
      }
      else
      {
        if ( !g_wppLevels )
        {
LABEL_17:
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&pAttributes);
          goto LABEL_68;
        }
        v12 = 276;
      }
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids, a1, v11);
      goto LABEL_17;
    case 3:
      v13 = *(IMFAttributes **)(a1 + 960);
      if ( !v13 )
        goto LABEL_72;
      pcbBufSize = 0;
      v14 = MFGetAttributesAsBlobSize(v13, &pcbBufSize);
      v6 = v14;
      if ( v14 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_68;
        v15 = 278;
        goto LABEL_67;
      }
LABEL_70:
      v8 = pcbBufSize;
      goto LABEL_71;
  }
  if ( a2 != 5 )
  {
    if ( a2 != 6 )
    {
      v6 = -2147467263;
      if ( !g_wppLevels )
        goto LABEL_77;
      v7 = 288;
      goto LABEL_76;
    }
    v20 = *(IMFAttributes **)(a1 + 792);
    pcbBufSize = 0;
    if ( !v20 )
    {
      v6 = -1072875819;
      if ( g_wppLevels >= 8u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          286,
          &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids,
          a1,
          -1072875819);
      goto LABEL_72;
    }
    v14 = MFGetAttributesAsBlobSize(v20, &pcbBufSize);
    v6 = v14;
    if ( v14 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_68;
      v15 = 287;
      goto LABEL_67;
    }
    goto LABEL_70;
  }
  v16 = (IMFAttributes **)(a1 + 976);
  if ( *(_QWORD *)(a1 + 976) )
    goto LABEL_72;
  pcbBufSize = 0;
  LODWORD(pAttributes) = 4;
  v22[0] = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Photos\\OEM\\RegionalSettings\\Camera",
          L"CameraSoundLevel",
          0x10u,
          0,
          &pcbBufSize,
          (LPDWORD)&pAttributes) )
  {
    v17 = pcbBufSize;
    if ( pcbBufSize )
    {
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(a1 + 976);
      v14 = MFCreateAttributes((IMFAttributes **)(a1 + 976), 1u);
      v6 = v14;
      if ( v14 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_68;
        v15 = 279;
        goto LABEL_67;
      }
      v18 = 100;
      if ( pcbBufSize < 0x64 )
        v18 = pcbBufSize;
      v14 = ((__int64 (__fastcall *)(IMFAttributes *, void *, __int64))(*v16)->lpVtbl->SetUINT32)(
              *v16,
              &MF_FRAMESERVER_CAMERA_REGIONAL_SOUND_LEVEL,
              v18);
      v6 = v14;
      if ( v14 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_68;
        v15 = 280;
        goto LABEL_67;
      }
      v17 = pcbBufSize;
    }
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_qSSd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (__int64)L"SOFTWARE\\Microsoft\\Photos\\OEM\\RegionalSettings\\Camera",
        (__int64)L"CameraSoundLevel",
        v17);
  }
  if ( !*v16 )
  {
    pcbBufSize = 1;
    LODWORD(pAttributes) = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Photos\\OEM",
            L"ShutterSoundUnlocked",
            0x10u,
            0,
            &pcbBufSize,
            (LPDWORD)&pAttributes) )
    {
      v19 = pcbBufSize;
      if ( !pcbBufSize )
      {
        wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(a1 + 976);
        v14 = MFCreateAttributes((IMFAttributes **)(a1 + 976), 1u);
        v6 = v14;
        if ( v14 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_68;
          v15 = 282;
          goto LABEL_67;
        }
        v14 = ((__int64 (__fastcall *)(IMFAttributes *, void *, __int64))(*v16)->lpVtbl->SetUINT32)(
                *v16,
                &MF_FRAMESERVER_CAMERA_REGIONAL_SOUND_LEVEL,
                100);
        v6 = v14;
        if ( v14 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_68;
          v15 = 283;
          goto LABEL_67;
        }
        v19 = pcbBufSize;
      }
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_qSSd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          (__int64)L"SOFTWARE\\Microsoft\\Photos\\OEM",
          (__int64)L"ShutterSoundUnlocked",
          v19);
    }
  }
  if ( !*v16 || (v14 = MFGetAttributesAsBlobSize(*v16, v22), v6 = v14, v14 >= 0) )
  {
    *a3 = v22[0];
    if ( v6 >= 0 )
      goto LABEL_72;
    goto LABEL_68;
  }
  if ( g_wppLevels )
  {
    v15 = 285;
LABEL_67:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids, a1, v14);
  }
LABEL_68:
  if ( v6 != -1072875819 )
  {
LABEL_77:
    if ( byte_18010EC4D )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 289, &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids, a1, v6);
    return (unsigned int)v6;
  }
LABEL_72:
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 27), 290, &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids, a1, v6, *a3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006a030  mov     [rsp-28h+arg_0], rbx
0x18006a035  mov     [rsp-28h+arg_8], rsi
0x18006a03a  push    rbp
0x18006a03b  push    rdi
0x18006a03c  push    r13
0x18006a03e  push    r14
0x18006a040  push    r15
0x18006a042  mov     rbp, rsp
0x18006a045  sub     rsp, 50h
0x18006a049  mov     r15, r8
0x18006a04c  mov     r14d, edx
0x18006a04f  mov     rdi, rcx
0x18006a052  cmp     cs:byte_18010EC4D, 8
0x18006a059  lea     r13, WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids
0x18006a060  jb      short loc_18006A085
0x18006a062  mov     r9, rcx
0x18006a065  mov     dword ptr [rsp+50h+pdwType], r14d
0x18006a06a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a071  mov     edx, 111h
0x18006a076  mov     r8, r13
0x18006a079  mov     rcx, [rcx+0D8h]
0x18006a080  call    WPP_SF_qD
0x18006a085  test    r15, r15
0x18006a088  jnz     short loc_18006A0AA
0x18006a08a  mov     ebx, 80004003h
0x18006a08f  lea     esi, [r15+1]
0x18006a093  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006a09a  jb      loc_18006A555
0x18006a0a0  mov     edx, 112h
0x18006a0a5  jmp     loc_18006A53B
0x18006a0aa  xor     ebx, ebx
0x18006a0ac  mov     [r15], ebx
0x18006a0af  lea     esi, [rbx+1]
0x18006a0b2  cmp     r14d, esi
0x18006a0b5  jnz     short loc_18006A0C2
0x18006a0b7  mov     eax, [rdi+328h]
0x18006a0bd  jmp     loc_18006A4ED
0x18006a0c2  cmp     r14d, 2
0x18006a0c6  jnz     loc_18006A1A6
0x18006a0cc  mov     r14, [rdi+360h]
0x18006a0d3  mov     [rbp+pAttributes], rbx
0x18006a0d7  mov     [rbp+pcbBufSize], ebx
0x18006a0da  test    r14, r14
0x18006a0dd  jnz     short loc_18006A11C
0x18006a0df  mov     eax, 0C00D36D5h
0x18006a0e4  mov     ebx, eax
0x18006a0e6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x18006a0ed  jb      short loc_18006A10E
0x18006a0ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a0f6  mov     edx, 113h
0x18006a0fb  mov     r9, rdi
0x18006a0fe  mov     dword ptr [rsp+50h+pdwType], eax
0x18006a102  mov     r8, r13
0x18006a105  mov     rcx, [rcx+10h]
0x18006a109  call    WPP_SF_qD
0x18006a10e  lea     rcx, [rbp+pAttributes]; void *
0x18006a112  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18006a117  jmp     loc_18006A4F0
0x18006a11c  mov     rax, [r14]
0x18006a11f  lea     rcx, [rbp+pAttributes]
0x18006a123  mov     rbx, [rax+40h]
0x18006a127  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18006a12c  lea     rdx, [rbp+pAttributes]
0x18006a130  mov     rcx, r14
0x18006a133  mov     rax, rbx
0x18006a136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a13b  mov     ebx, eax
0x18006a13d  test    eax, eax
0x18006a13f  jns     short loc_18006A177
0x18006a141  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006a148  jb      short loc_18006A169
0x18006a14a  mov     edx, 114h
0x18006a14f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a156  mov     r9, rdi
0x18006a159  mov     r8, r13
0x18006a15c  mov     dword ptr [rsp+50h+pdwType], eax
0x18006a160  mov     rcx, [rcx+10h]
0x18006a164  call    WPP_SF_qD
0x18006a169  lea     rcx, [rbp+pAttributes]; void *
0x18006a16d  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18006a172  jmp     loc_18006A4DF
0x18006a177  mov     rcx, [rbp+pAttributes]; pAttributes
0x18006a17b  lea     rdx, [rbp+pcbBufSize]; pcbBufSize
0x18006a17f  call    cs:__imp_MFGetAttributesAsBlobSize
0x18006a185  mov     ebx, eax
0x18006a187  test    eax, eax
0x18006a189  jns     short loc_18006A19B
0x18006a18b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006a192  jb      short loc_18006A169
0x18006a194  mov     edx, 115h
0x18006a199  jmp     short loc_18006A14F
0x18006a19b  mov     eax, [rbp+pcbBufSize]
0x18006a19e  mov     [r15], eax
0x18006a1a1  jmp     loc_18006A10E
0x18006a1a6  cmp     r14d, 3
0x18006a1aa  jnz     short loc_18006A1EA
0x18006a1ac  mov     rcx, [rdi+3C0h]; pAttributes
0x18006a1b3  test    rcx, rcx
0x18006a1b6  jz      loc_18006A4F0
0x18006a1bc  lea     rdx, [rbp+pcbBufSize]; pcbBufSize
0x18006a1c0  mov     [rbp+pcbBufSize], ebx
0x18006a1c3  call    cs:__imp_MFGetAttributesAsBlobSize
0x18006a1c9  mov     ebx, eax
0x18006a1cb  test    eax, eax
0x18006a1cd  jns     loc_18006A4EA
0x18006a1d3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006a1da  jb      loc_18006A4DF
0x18006a1e0  mov     edx, 116h
0x18006a1e5  jmp     loc_18006A4C5
0x18006a1ea  cmp     r14d, 5
0x18006a1ee  jnz     loc_18006A45D
0x18006a1f4  lea     r14, [rdi+3D0h]
0x18006a1fb  cmp     [r14], rbx
0x18006a1fe  jnz     loc_18006A4F0
0x18006a204  lea     rax, [rbp+pAttributes]
0x18006a208  mov     [rbp+pcbBufSize], ebx
0x18006a20b  mov     [rsp+50h+pcbData], rax; pcbData
0x18006a210  lea     r8, aCamerasoundlev; "CameraSoundLevel"
0x18006a217  lea     rax, [rbp+pcbBufSize]
0x18006a21b  mov     dword ptr [rbp+pAttributes], 4
0x18006a222  mov     [rsp+50h+pvData], rax; pvData
0x18006a227  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Photos\\OEM\\Regio"...
0x18006a22e  mov     r9d, 10h; dwFlags
0x18006a234  mov     [rsp+50h+pdwType], rbx; pdwType
0x18006a239  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18006a240  mov     [rbp+var_10], ebx
0x18006a243  call    cs:__imp_RegGetValueW
0x18006a249  test    eax, eax
0x18006a24b  jnz     loc_18006A310
0x18006a251  mov     eax, [rbp+pcbBufSize]
0x18006a254  test    eax, eax
0x18006a256  jz      short loc_18006A2D0
0x18006a258  mov     rcx, r14
0x18006a25b  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18006a260  mov     edx, esi; cInitialSize
0x18006a262  mov     rcx, r14; ppMFAttributes
0x18006a265  call    cs:__imp_MFCreateAttributes
0x18006a26b  mov     ebx, eax
0x18006a26d  test    eax, eax
0x18006a26f  jns     short loc_18006A288
0x18006a271  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006a278  jb      loc_18006A4DF
0x18006a27e  mov     edx, 117h
0x18006a283  jmp     loc_18006A4C5
0x18006a288  mov     rcx, [r14]
0x18006a28b  lea     rdx, MF_FRAMESERVER_CAMERA_REGIONAL_SOUND_LEVEL
0x18006a292  mov     r8d, 64h ; 'd'
0x18006a298  cmp     [rbp+pcbBufSize], r8d
0x18006a29c  mov     rax, [rcx]
0x18006a29f  cmovb   r8d, [rbp+pcbBufSize]
0x18006a2a4  mov     rax, [rax+0A8h]
0x18006a2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2b0  mov     ebx, eax
0x18006a2b2  test    eax, eax
0x18006a2b4  jns     short loc_18006A2CD
0x18006a2b6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006a2bd  jb      loc_18006A4DF
0x18006a2c3  mov     edx, 118h
0x18006a2c8  jmp     loc_18006A4C5
0x18006a2cd  mov     eax, [rbp+pcbBufSize]
0x18006a2d0  cmp     cs:byte_18010EC4D, 8
0x18006a2d7  jb      short loc_18006A310
0x18006a2d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a2e0  mov     edx, 119h
0x18006a2e5  mov     dword ptr [rsp+50h+pcbData], eax; char
0x18006a2e9  mov     r9, rdi
0x18006a2ec  lea     rax, aCamerasoundlev; "CameraSoundLevel"
0x18006a2f3  mov     [rsp+50h+pvData], rax; __int64
0x18006a2f8  lea     rax, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Photos\\OEM\\Regio"...
0x18006a2ff  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18006a306  mov     [rsp+50h+pdwType], rax; __int64
0x18006a30b  call    WPP_SF_qSSd
0x18006a310  cmp     qword ptr [r14], 0
0x18006a314  jnz     loc_18006A41E
0x18006a31a  lea     rax, [rbp+pAttributes]
0x18006a31e  mov     [rbp+pcbBufSize], esi
0x18006a321  mov     [rsp+50h+pcbData], rax; pcbData
0x18006a326  lea     r8, aShuttersoundun; "ShutterSoundUnlocked"
0x18006a32d  lea     rax, [rbp+pcbBufSize]
0x18006a331  mov     dword ptr [rbp+pAttributes], 4
0x18006a338  mov     [rsp+50h+pvData], rax; pvData
0x18006a33d  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Photos\\OEM"
0x18006a344  mov     r9d, 10h; dwFlags
0x18006a34a  mov     [rsp+50h+pdwType], 0; pdwType
0x18006a353  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18006a35a  call    cs:__imp_RegGetValueW
0x18006a360  test    eax, eax
0x18006a362  jnz     loc_18006A41E
0x18006a368  mov     eax, [rbp+pcbBufSize]
0x18006a36b  test    eax, eax
0x18006a36d  jnz     short loc_18006A3DE
0x18006a36f  mov     rcx, r14
0x18006a372  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18006a377  mov     edx, esi; cInitialSize
0x18006a379  mov     rcx, r14; ppMFAttributes
0x18006a37c  call    cs:__imp_MFCreateAttributes
0x18006a382  mov     ebx, eax
0x18006a384  test    eax, eax
0x18006a386  jns     short loc_18006A39F
0x18006a388  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006a38f  jb      loc_18006A4DF
0x18006a395  mov     edx, 11Ah
0x18006a39a  jmp     loc_18006A4C5
0x18006a39f  mov     rcx, [r14]
0x18006a3a2  lea     rdx, MF_FRAMESERVER_CAMERA_REGIONAL_SOUND_LEVEL
0x18006a3a9  mov     r8d, 64h ; 'd'
0x18006a3af  mov     rax, [rcx]
0x18006a3b2  mov     rax, [rax+0A8h]
0x18006a3b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a3be  mov     ebx, eax
0x18006a3c0  test    eax, eax
0x18006a3c2  jns     short loc_18006A3DB
0x18006a3c4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006a3cb  jb      loc_18006A4DF
0x18006a3d1  mov     edx, 11Bh
0x18006a3d6  jmp     loc_18006A4C5
0x18006a3db  mov     eax, [rbp+pcbBufSize]
0x18006a3de  cmp     cs:byte_18010EC4D, 8
0x18006a3e5  jb      short loc_18006A41E
0x18006a3e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a3ee  mov     edx, 11Ch
0x18006a3f3  mov     dword ptr [rsp+50h+pcbData], eax; char
0x18006a3f7  mov     r9, rdi
0x18006a3fa  lea     rax, aShuttersoundun; "ShutterSoundUnlocked"
0x18006a401  mov     [rsp+50h+pvData], rax; __int64
0x18006a406  lea     rax, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Photos\\OEM"
0x18006a40d  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18006a414  mov     [rsp+50h+pdwType], rax; __int64
0x18006a419  call    WPP_SF_qSSd
0x18006a41e  mov     rcx, [r14]; pAttributes
0x18006a421  test    rcx, rcx
0x18006a424  jz      short loc_18006A44A
0x18006a426  lea     rdx, [rbp+var_10]; pcbBufSize
0x18006a42a  call    cs:__imp_MFGetAttributesAsBlobSize
0x18006a430  mov     ebx, eax
0x18006a432  test    eax, eax
0x18006a434  jns     short loc_18006A44A
0x18006a436  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006a43d  jb      loc_18006A4DF
0x18006a443  mov     edx, 11Dh
0x18006a448  jmp     short loc_18006A4C5
0x18006a44a  mov     eax, [rbp+var_10]
0x18006a44d  mov     [r15], eax
0x18006a450  test    ebx, ebx
0x18006a452  jns     loc_18006A4F0
0x18006a458  jmp     loc_18006A4DF
0x18006a45d  cmp     r14d, 6
0x18006a461  jnz     loc_18006A528
0x18006a467  mov     rcx, [rdi+318h]; pAttributes
0x18006a46e  mov     [rbp+pcbBufSize], ebx
0x18006a471  test    rcx, rcx
0x18006a474  jnz     short loc_18006A4A7
0x18006a476  mov     eax, 0C00D36D5h
0x18006a47b  mov     ebx, eax
0x18006a47d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x18006a484  jb      short loc_18006A4F0
0x18006a486  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a48d  mov     edx, 11Eh
0x18006a492  mov     r9, rdi
0x18006a495  mov     dword ptr [rsp+50h+pdwType], eax
0x18006a499  mov     r8, r13
0x18006a49c  mov     rcx, [rcx+10h]
0x18006a4a0  call    WPP_SF_qD
0x18006a4a5  jmp     short loc_18006A4F0
0x18006a4a7  lea     rdx, [rbp+pcbBufSize]; pcbBufSize
0x18006a4ab  call    cs:__imp_MFGetAttributesAsBlobSize
0x18006a4b1  mov     ebx, eax
0x18006a4b3  test    eax, eax
0x18006a4b5  jns     short loc_18006A4EA
0x18006a4b7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006a4be  jb      short loc_18006A4DF
0x18006a4c0  mov     edx, 11Fh
0x18006a4c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a4cc  mov     r9, rdi
0x18006a4cf  mov     r8, r13
0x18006a4d2  mov     dword ptr [rsp+50h+pdwType], eax
0x18006a4d6  mov     rcx, [rcx+10h]
0x18006a4da  call    WPP_SF_qD
0x18006a4df  mov     eax, 0C00D36D5h
0x18006a4e4  cmp     ebx, eax
0x18006a4e6  jz      short loc_18006A4F0
0x18006a4e8  jmp     short loc_18006A555
0x18006a4ea  mov     eax, [rbp+pcbBufSize]
0x18006a4ed  mov     [r15], eax
0x18006a4f0  cmp     cs:byte_18010EC4D, 8
0x18006a4f7  jb      loc_18006A580
0x18006a4fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a504  mov     edx, 122h
0x18006a509  mov     eax, [r15]
0x18006a50c  mov     r9, rdi
0x18006a50f  mov     dword ptr [rsp+50h+pvData], eax
0x18006a513  mov     r8, r13
0x18006a516  mov     dword ptr [rsp+50h+pdwType], ebx
0x18006a51a  mov     rcx, [rcx+0D8h]
0x18006a521  call    WPP_SF_qDD
0x18006a526  jmp     short loc_18006A580
0x18006a528  mov     ebx, 80004001h
0x18006a52d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006a534  jb      short loc_18006A555
0x18006a536  mov     edx, 120h
  ... truncated ...
```
