# FSLoadAllAppsDeviceConfiguration_Base

- ea: `0x180071e68`
- end: `0x1800721a9`
- name: `FSLoadAllAppsDeviceConfiguration_Base`
- size: `833`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180070948`

## callees

- `0x1800049b0`
- `0x180005b90`
- `0x180005fa0`
- `0x180008f9c`
- `0x18000c348`
- `0x180010914`
- `0x180016328`
- `0x18001635c`
- `0x18002d02c`
- `0x180044b28`
- `0x180071608`
- `0x180071e68`
- `0x180077010`

## string_xrefs

- `0x180071ff3`: `FRAMESERVER_CONFIGURATION_ALL_APPS`
- `0x180072078`: `FRAMESERVER_CONFIGURATION_ALL_APPS`

## pseudocode

```c
__int64 __fastcall FSLoadAllAppsDeviceConfiguration_Base(
        LPCWSTR pszDeviceInterface,
        const struct _DEVPROPKEY *a2,
        bool a3,
        struct IFSConfiguration **a4)
{
  WCHAR *v4; // rsi
  unsigned __int16 *v5; // r14
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  void **unique; // rax
  void *v14; // rcx
  __int64 v15; // rdx
  void **v16; // rax
  void *v17; // rcx
  struct IFSConfigurationKey *v18; // rcx
  __int64 v19; // rdx
  unsigned int v21; // [rsp+30h] [rbp-30h] BYREF
  struct IFSConfigurationKey *v22; // [rsp+38h] [rbp-28h] BYREF
  void *Block; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR pszDeviceInterfacea; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v25; // [rsp+50h] [rbp-10h] BYREF
  void *v27; // [rsp+A8h] [rbp+48h] BYREF

  v4 = 0;
  v22 = 0;
  v5 = 0;
  pszDeviceInterfacea = 0;
  v25 = 0;
  LODWORD(v27) = 0;
  v21 = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      238,
      &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
      pszDeviceInterface);
  if ( !a4 )
  {
    v9 = -2147467261;
    if ( g_wppLevels )
    {
      v10 = 239;
LABEL_6:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v9);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  *a4 = 0;
  if ( !pszDeviceInterface )
  {
    v9 = -2147024809;
    if ( g_wppLevels )
    {
      v10 = 240;
      goto LABEL_6;
    }
LABEL_44:
    if ( !byte_18008D62D )
      goto LABEL_49;
    v19 = 249;
    goto LABEL_48;
  }
  v11 = FSGetUniqueSymbolicName(pszDeviceInterface, 0, 0, (unsigned int *)&v27);
  v9 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_43;
    v12 = 241;
    goto LABEL_42;
  }
  unique = (void **)wil::make_unique_nothrow<unsigned short [0]>(&Block, (unsigned int)v27);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
    (void **)&pszDeviceInterfacea,
    unique);
  v14 = Block;
  Block = 0;
  if ( v14 )
    operator delete(v14);
  v4 = (WCHAR *)pszDeviceInterfacea;
  if ( !pszDeviceInterfacea )
  {
    v9 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_44;
    v15 = 242;
LABEL_19:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
      0,
      -2147024882);
    goto LABEL_44;
  }
  v11 = FSGetUniqueSymbolicName(
          pszDeviceInterface,
          (unsigned __int16 *)pszDeviceInterfacea,
          (unsigned int)v27,
          (unsigned int *)&v27);
  v9 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_43;
    v12 = 243;
    goto LABEL_42;
  }
  v11 = FSTagPackageFamilyName(L"FRAMESERVER_CONFIGURATION_ALL_APPS", 0, 0, &v21);
  v9 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_43;
    v12 = 244;
    goto LABEL_42;
  }
  v16 = (void **)wil::make_unique_nothrow<unsigned short [0]>(&v27, v21);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v25, v16);
  v17 = v27;
  v27 = 0;
  if ( v17 )
    operator delete(v17);
  v5 = v25;
  if ( !v25 )
  {
    v9 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_44;
    v15 = 245;
    goto LABEL_19;
  }
  v11 = FSTagPackageFamilyName(L"FRAMESERVER_CONFIGURATION_ALL_APPS", v25, v21, &v21);
  v9 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_43;
    v12 = 246;
    goto LABEL_42;
  }
  v18 = v22;
  v22 = 0;
  if ( v18 )
    (*(void (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)v18 + 16LL))(v18);
  v11 = FSCreateConfigurationKey(v4);
  v9 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_43;
    v12 = 247;
    goto LABEL_42;
  }
  v11 = FSLoadV1OrV2(v22, a2, a3, a4);
  v9 = v11;
  if ( v11 >= 0 )
    goto LABEL_46;
  if ( g_wppLevels >= 8u )
  {
    v12 = 248;
LABEL_42:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v11);
  }
LABEL_43:
  if ( v9 != -1072875819 )
    goto LABEL_44;
LABEL_46:
  if ( (unsigned __int8)byte_18008D62D < 8u )
    goto LABEL_49;
  v19 = 250;
LABEL_48:
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), v19, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, v9);
LABEL_49:
  if ( v5 )
    operator delete(v5);
  if ( v4 )
    operator delete(v4);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v22);
  return v9;
}

```

## disassembly

```asm
0x180071e68  mov     [rsp-28h+arg_0], rbx
0x180071e6d  mov     [rsp-28h+arg_10], rsi
0x180071e72  mov     [rsp-28h+arg_8], rdx
0x180071e77  push    rbp
0x180071e78  push    r12
0x180071e7a  push    r13
0x180071e7c  push    r14
0x180071e7e  push    r15
0x180071e80  mov     rbp, rsp
0x180071e83  sub     rsp, 60h
0x180071e87  xor     esi, esi
0x180071e89  mov     [rbp+var_28], 0
0x180071e91  xor     r14d, r14d
0x180071e94  mov     [rbp+pszDeviceInterface], rsi
0x180071e98  mov     [rbp+var_10], r14
0x180071e9c  mov     r12, r9
0x180071e9f  mov     r13b, r8b
0x180071ea2  mov     dword ptr [rbp+arg_18], esi
0x180071ea5  mov     r15, rcx
0x180071ea8  mov     [rbp+var_30], esi
0x180071eab  cmp     cs:byte_18008D62D, 8
0x180071eb2  jb      short loc_180071ED6
0x180071eb4  mov     r9, rcx
0x180071eb7  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180071ebe  mov     rcx, cs:WPP_GLOBAL_Control
0x180071ec5  mov     edx, 0EEh
0x180071eca  mov     rcx, [rcx+0D8h]
0x180071ed1  call    WPP_SF_S
0x180071ed6  test    r12, r12
0x180071ed9  jnz     short loc_180071F15
0x180071edb  mov     ebx, 80004003h
0x180071ee0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071ee7  jb      loc_18007212F
0x180071eed  mov     edx, 0EFh
0x180071ef2  mov     [rsp+60h+var_40], ebx
0x180071ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x180071efd  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180071f04  xor     r9d, r9d
0x180071f07  mov     rcx, [rcx+10h]
0x180071f0b  call    WPP_SF_qD
0x180071f10  jmp     loc_18007212F
0x180071f15  mov     [r12], rsi
0x180071f19  test    r15, r15
0x180071f1c  jnz     short loc_180071F37
0x180071f1e  mov     ebx, 80070057h
0x180071f23  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071f2a  jb      loc_18007212F
0x180071f30  mov     edx, 0F0h
0x180071f35  jmp     short loc_180071EF2
0x180071f37  lea     r9, [rbp+arg_18]; unsigned int *
0x180071f3b  xor     r8d, r8d; unsigned int
0x180071f3e  xor     edx, edx; unsigned __int16 *
0x180071f40  mov     rcx, r15; pszDeviceInterface
0x180071f43  call    ?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z; FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)
0x180071f48  mov     ebx, eax
0x180071f4a  test    eax, eax
0x180071f4c  jns     short loc_180071F65
0x180071f4e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071f55  jb      loc_180072127
0x180071f5b  mov     edx, 0F1h
0x180071f60  jmp     loc_180072109
0x180071f65  mov     edx, dword ptr [rbp+arg_18]
0x180071f68  lea     rcx, [rbp+Block]
0x180071f6c  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180071f71  mov     rdx, rax
0x180071f74  lea     rcx, [rbp+pszDeviceInterface]
0x180071f78  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180071f7d  mov     rcx, [rbp+Block]; Block
0x180071f81  mov     [rbp+Block], rsi
0x180071f85  test    rcx, rcx
0x180071f88  jz      short loc_180071F8F
0x180071f8a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180071f8f  mov     rsi, [rbp+pszDeviceInterface]
0x180071f93  test    rsi, rsi
0x180071f96  jnz     short loc_180071FBA
0x180071f98  mov     eax, 8007000Eh
0x180071f9d  mov     ebx, eax
0x180071f9f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071fa6  jb      loc_18007212F
0x180071fac  mov     edx, 0F2h
0x180071fb1  mov     [rsp+60h+var_40], eax
0x180071fb5  jmp     loc_180071EF6
0x180071fba  mov     r8d, dword ptr [rbp+arg_18]; unsigned int
0x180071fbe  lea     r9, [rbp+arg_18]; unsigned int *
0x180071fc2  mov     rdx, rsi; unsigned __int16 *
0x180071fc5  mov     rcx, r15; pszDeviceInterface
0x180071fc8  call    ?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z; FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)
0x180071fcd  mov     ebx, eax
0x180071fcf  test    eax, eax
0x180071fd1  jns     short loc_180071FEA
0x180071fd3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071fda  jb      loc_180072127
0x180071fe0  mov     edx, 0F3h
0x180071fe5  jmp     loc_180072109
0x180071fea  lea     r9, [rbp+var_30]; unsigned int *
0x180071fee  xor     r8d, r8d; unsigned int
0x180071ff1  xor     edx, edx; unsigned __int16 *
0x180071ff3  lea     rcx, aFrameserverCon; "FRAMESERVER_CONFIGURATION_ALL_APPS"
0x180071ffa  call    ?FSTagPackageFamilyName@@YAJPEBGPEAGKPEAK@Z; FSTagPackageFamilyName(ushort const *,ushort *,ulong,ulong *)
0x180071fff  mov     ebx, eax
0x180072001  test    eax, eax
0x180072003  jns     short loc_18007201C
0x180072005  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007200c  jb      loc_180072127
0x180072012  mov     edx, 0F4h
0x180072017  jmp     loc_180072109
0x18007201c  mov     edx, [rbp+var_30]
0x18007201f  lea     rcx, [rbp+arg_18]
0x180072023  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180072028  mov     rdx, rax
0x18007202b  lea     rcx, [rbp+var_10]
0x18007202f  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180072034  mov     rcx, [rbp+arg_18]; Block
0x180072038  mov     [rbp+arg_18], r14
0x18007203c  test    rcx, rcx
0x18007203f  jz      short loc_180072046
0x180072041  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180072046  mov     r14, [rbp+var_10]
0x18007204a  test    r14, r14
0x18007204d  jnz     short loc_18007206D
0x18007204f  mov     eax, 8007000Eh
0x180072054  mov     ebx, eax
0x180072056  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007205d  jb      loc_18007212F
0x180072063  mov     edx, 0F5h
0x180072068  jmp     loc_180071FB1
0x18007206d  mov     r8d, [rbp+var_30]; unsigned int
0x180072071  lea     r9, [rbp+var_30]; unsigned int *
0x180072075  mov     rdx, r14; unsigned __int16 *
0x180072078  lea     rcx, aFrameserverCon; "FRAMESERVER_CONFIGURATION_ALL_APPS"
0x18007207f  call    ?FSTagPackageFamilyName@@YAJPEBGPEAGKPEAK@Z; FSTagPackageFamilyName(ushort const *,ushort *,ulong,ulong *)
0x180072084  mov     ebx, eax
0x180072086  test    eax, eax
0x180072088  jns     short loc_18007209E
0x18007208a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072091  jb      loc_180072127
0x180072097  mov     edx, 0F6h
0x18007209c  jmp     short loc_180072109
0x18007209e  mov     rcx, [rbp+var_28]
0x1800720a2  mov     [rbp+var_28], 0
0x1800720aa  test    rcx, rcx
0x1800720ad  jz      short loc_1800720BB
0x1800720af  mov     rax, [rcx]
0x1800720b2  mov     rax, [rax+10h]
0x1800720b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800720bb  lea     r9, [rbp+var_28]
0x1800720bf  mov     r8, r14
0x1800720c2  xor     edx, edx
0x1800720c4  mov     rcx, rsi; pszDeviceInterface
0x1800720c7  call    FSCreateConfigurationKey
0x1800720cc  mov     ebx, eax
0x1800720ce  test    eax, eax
0x1800720d0  jns     short loc_1800720E2
0x1800720d2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800720d9  jb      short loc_180072127
0x1800720db  mov     edx, 0F7h
0x1800720e0  jmp     short loc_180072109
0x1800720e2  mov     rdx, [rbp+arg_8]; struct _DEVPROPKEY *
0x1800720e6  mov     r9, r12; struct IFSConfiguration **
0x1800720e9  mov     rcx, [rbp+var_28]; struct IFSConfigurationKey *
0x1800720ed  mov     r8b, r13b; bool
0x1800720f0  call    ?FSLoadV1OrV2@@YAJPEAUIFSConfigurationKey@@AEBU_DEVPROPKEY@@_NPEAPEAUIFSConfiguration@@@Z; FSLoadV1OrV2(IFSConfigurationKey *,_DEVPROPKEY const &,bool,IFSConfiguration * *)
0x1800720f5  mov     ebx, eax
0x1800720f7  test    eax, eax
0x1800720f9  jns     short loc_18007213F
0x1800720fb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180072102  jb      short loc_180072127
0x180072104  mov     edx, 0F8h
0x180072109  mov     rcx, cs:WPP_GLOBAL_Control
0x180072110  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180072117  xor     r9d, r9d
0x18007211a  mov     [rsp+60h+var_40], eax
0x18007211e  mov     rcx, [rcx+10h]
0x180072122  call    WPP_SF_qD
0x180072127  cmp     ebx, 0C00D36D5h
0x18007212d  jz      short loc_18007213F
0x18007212f  cmp     cs:byte_18008D62D, 1
0x180072136  jb      short loc_18007216A
0x180072138  mov     edx, 0F9h
0x18007213d  jmp     short loc_18007214D
0x18007213f  cmp     cs:byte_18008D62D, 8
0x180072146  jb      short loc_18007216A
0x180072148  mov     edx, 0FAh
0x18007214d  mov     rcx, cs:WPP_GLOBAL_Control
0x180072154  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18007215b  mov     r9d, ebx
0x18007215e  mov     rcx, [rcx+0D8h]
0x180072165  call    WPP_SF_d
0x18007216a  test    r14, r14
0x18007216d  jz      short loc_180072177
0x18007216f  mov     rcx, r14; Block
0x180072172  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180072177  test    rsi, rsi
0x18007217a  jz      short loc_180072184
0x18007217c  mov     rcx, rsi; Block
0x18007217f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180072184  lea     rcx, [rbp+var_28]
0x180072188  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18007218d  lea     r11, [rsp+60h+var_s0]
0x180072192  mov     eax, ebx
0x180072194  mov     rbx, [r11+30h]
0x180072198  mov     rsi, [r11+40h]
0x18007219c  mov     rsp, r11
0x18007219f  pop     r15
0x1800721a1  pop     r14
0x1800721a3  pop     r13
0x1800721a5  pop     r12
0x1800721a7  pop     rbp
0x1800721a8  retn
```
